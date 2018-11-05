---
title: Verwalten von Watcher-Knoten
TOCTitle: Verwalten von Watcher-Knoten
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49890773
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwalten von Watcher-Knoten

 

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

Mit dem **Set-CsWatcherNodeConfiguration**-Cmdlet können Administratoren nicht nur die auf einem Watcher-Knoten ausgeführten synthetischen Transaktionen ändern, sondern auch noch zwei andere wichtige Aufgaben durchführen: das Aktivieren und Deaktivieren des Watcher-Knotens sowie das Konfigurieren des Watcher-Knotens zur Verwendung interner oder externer URLs beim Durchführen seiner Tests.

In der Standardeinstellung führen Watcher-Knoten in regelmäßigen Abständen alle für sie aktivierten synthetischen Transaktionen aus. Manchmal müssen solche Transaktionen jedoch angehalten werden. Wenn der Watcher-Knoten zum Beispiel vorübergehend vom Netzwerk getrennt ist, liegt kein Grund vor, dass die synthetischen Transaktionen ausgeführt werden. Ohne Verbindung mit dem Netzwerk würden solche Transaktionen nur fehlerhaft sein. Wenn Sie einen Watcher-Knoten vorübergehend deaktivieren möchten, führen Sie in der Lync Server-Verwaltungsshell einen Befehl aus, der in etwa so aussieht:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Dieser Befehl deaktiviert die Ausführung synthetischer Transaktionen auf dem Watcher-Knoten "atl-watcher- 001.litwareinc.com". Wenn die synthetischen Transaktionen wieder aufgenommen werden sollen, setzen Sie die Eigenschaft "Enabled" wieder zurück auf "True" ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True


> [!NOTE]
> Mithilfe der Eigenschaft "Enabled" können Watcher-Knoten ein- und ausgeschaltet werden. Wenn Sie einen Watcher-Knoten dauerhaft löschen möchten, verwenden Sie das <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>-Cmdlet:<BR>Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"<BR>Dieser Befehl entfernt auf dem angegebenen Computer alle Konfigurationseinstellungen für Watcher-Knoten, sodass auf diesem Computer keine synthetischen Transaktionen mehr automatisch ausgeführt werden. Allerdings werden dabei weder die System Center-Agentdateien noch die Lync Server 2013-Systemdateien deinstalliert.



In der Standardeinstellung verwenden Watcher-Knoten bei der Durchführung ihrer Tests externe URLs des Unternehmens. Es ist jedoch auch möglich, die Verwendung interner URLs zu konfigurieren. Dies ermöglicht es Administratoren, den URL-Zugriff für innerhalb des Umkreisnetzwerks befindliche Benutzer zu überprüfen. Wenn Sie einen Watcher-Knoten so konfigurieren möchten, dass er interne anstatt externe URLs verwendet, legen Sie die Eigenschaft "UseInternalWebUrls" auf "True" ($True) fest:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Wenn Sie diese Eigenschaft auf ihren Standardwert ($False) zurücksetzen, wird der Watcher-Knoten wieder externe URLs verwenden:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

