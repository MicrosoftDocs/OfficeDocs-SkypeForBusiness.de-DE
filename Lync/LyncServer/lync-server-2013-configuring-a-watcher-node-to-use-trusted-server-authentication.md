---
title: Konfigurieren eines Watcher-Knotens für die Verwendung der Authentifizierung über vertrauenswürdige Server
TOCTitle: Konfigurieren eines Watcher-Knotens für die Verwendung der Authentifizierung über vertrauenswürdige Server
ms:assetid: 42d879ac-aa90-4ed6-b5e2-1e208711672a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204852(v=OCS.15)
ms:contentKeyID: 49293828
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines Watcher-Knotens für die Verwendung der Authentifizierung über vertrauenswürdige Server

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Wenn sich Ihr Watcher-Knoten-Computer innerhalb des Umkreisnetzes befindet, können die Administrationsaufgaben zur Beibehaltung eines einzelnen Zertifikats anstelle zahlreicher Kennwörter für Benutzerkonten mithilfe der Trusted Server-Authentifizierung stark reduziert werden.

Der erste Schritt bei der Konfiguration der Trusted Server-Authentifizierung ist die Erstellung eines Pools vertrauenswürdiger Anwendungen zum Hosten des Watcher-Knoten-Computers. Nach der Erstellung des Pools vertrauenswürdiger Anwendungen müssen Sie synthetische Transaktionen auf diesem Watcher-Knoten erstellen, die als vertrauenswürdige Anwendungen ausgeführt werden sollen.


> [!NOTE]
> Eine vertrauenswürdige Anwendung ist eine Anwendung, der ein Vertrauensstatus zur Ausführung als Teil von Lync Server 2013 zugewiesen wurde, die jedoch nicht in das Produkt integriert ist. Vertrauensstatus bedeutet, dass nicht bei jeder Ausführung der Anwendung eine Authentifizierung angefordert wird.



Öffnen Sie zum Erstellen eines vertrauenswürdigen Anwendungspools den Verwaltungsshell für Lync Server 2013, und führen Sie einen Befehl wie den folgenden aus:

    New-CsTrustedApplicationPool -Identity atl-watcher-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -ThrottleAsServer $True -TreatAsAuthenticated $True -OutboundOnly $False -RequiresReplication $True -ComputerFqdn atl-watcher-001.litwareinc.com -Site Redmond


> [!NOTE]
> Ausführliche Informationen zu den im vorstehenden Befehl verwendeten Parametern erhalten Sie, wenn Sie an der Lync Server-Verwaltungsshell-Eingabeaufforderung Folgendes eingeben:<BR>Get-Help New-CsTrustedApplicationPool -Full | more



Konfigurieren Sie nach der Erstellung des Pools vertrauenswürdiger Anwendungen, den Watcher-Knoten-Computer für die Ausführung synthetischer Transaktionen als vertrauenswürdige Anwendung. Verwenden Sie dazu das **New-CsTrustedApplication**-Cmdlet und einen Befehl wie den folgenden:

    New-CsTrustedApplication -ApplicationId STWatcherNode -TrustedApplicationPoolFqdn atl-watcher-001.litwareinc.com -Port 5061

Wenn der vorstehende Befehl abgeschlossen ist und die vertrauenswürdige Anwendung erstellt wurde, führen Sie "Enable-CsTopology" aus, um sicherzustellen, dass die Änderungen wirksam werden:

    Enable-CsTopology

Nach Ausführung von "Enable-CsTopology" wird empfohlen, den Computer neu zu starten.

Um zu überprüfen, ob die neue vertrauenswürdige Anwendung erstellt wurde, geben Sie an der Lync Server-Verwaltungsshell-Eingabeaufforderung Folgendes ein:

    Get-CsTrustedApplication -Identity "atl-watcher-001.litwareinc.com/urn:application:STWatcherNode"

## Konfigurieren eines Standardzertifikats auf dem Watcher-Knoten

Jeder Watcher-Knoten muss ein Standardzertifikat besitzen, das ihm mithilfe des Lync Server-Bereitstellungs-Assistents zugewiesen wurde.

**So weisen Sie ein Standardzertifikat zu**

1.  Klicken Sie auf **Start**, auf **Alle Programme**, auf **Lync Server** und dann auf **Lync Server-Bereitstellungs-Assistent**.

2.  Klicken Sie im Lync Server-Bereitstellungs-Assistent auf **Installieren oder Aktualisieren des Lync Server-Systems** und anschließend unter dem Titel **Zertifikat anfordern, installieren oder zuweisen** auf **Ausführen**.
    

    > [!NOTE]
    > Wenn die Schaltfläche <STRONG>Ausführen</STRONG> deaktiviert ist, müssen Sie möglicherweise zunächst unter <STRONG>Lokalen Konfigurationsspeicher installieren</STRONG> auf <STRONG>Ausführen</STRONG> klicken.



3.  Führen Sie einen der folgenden Schritte aus:
    
      - Wenn Sie bereits ein Zertifikat besitzen, das als Standardzertifikat verwendet werden kann, klicken Sie im Zertifikat-Assistenten auf **Standard** und anschließend auf **Zuweisen**. Befolgen Sie die Anweisungen des Zertifikat-Assistenten, um das Zertifikat zuzuweisen.
    
      - Wenn Sie ein Zertifikat für die Verwendung als Standardzertifikat anfordern müssen, klicken Sie auf **Anforderung**, und folgen Sie den Schritten im Zertifikatanforderungs-Assistenten, um das Zertifikat anzufordern. Wenn Sie die Standardwerte für das Webserver-Zertifikat verwenden, erhalten Sie ein Zertifikat, das Sie als Standardzertifikat zuweisen können.

## Installieren und Konfigurieren eines Watcher-Knotens

Nachdem Sie den Watcher-Knoten-Computer neu gestartet und ein Zertifikat konfiguriert haben, müssen Sie die Datei "Watchernode.msi" ausführen. (Sie müssen "Watchernode.msi" auf einem Computer ausführen, auf dem sowohl die Operations Manager-Agent-Dateien als auch die Lync Server 2013-Kernkomponenten installiert sind.)

**So installieren und konfigurieren Sie einen Watcher-Knoten**

1.  Öffnen Sie den Lync Server-Verwaltungsshell, indem Sie auf **Start**, auf **Alle Programme**, auf **Lync Server** und schließlich auf **Lync Server-Verwaltungsshell** klicken.

2.  Geben Sie in der Lync Server-Verwaltungsshell den folgenden Befehl ein, und drücken Sie die EINGABETASTE (geben Sie den tatsächlichen Pfad Ihrer Kopie von "Watchernode.msi" ein):
    
        C:\Tools\Watchernode.msi Authentication=TrustedServer
    

    > [!NOTE]
    > Sie können "Watchernode.msi" auch aus einem Befehlsfenster ausführen. Um ein Befehlsfenster zu öffnen, klicken Sie auf <STRONG>Start</STRONG>, klicken Sie mit der rechten Maustaste auf <STRONG>Eingabeaufforderung</STRONG>, und klicken Sie auf <STRONG>Als Administrator ausführen</STRONG>. Wenn das Befehlsfenster geöffnet wird, geben Sie denselben vorstehenden Befehl ein.



Beachten Sie, dass beim Namen/Wertpaar im vorstehenden Befehl "Authentication=TrustedServer" Groß-/Kleinschreibung beachtet wird. Geben Sie es genau wie angezeigt ein. Bei der Ausführung des folgenden Befehls tritt ein Fehler auf, weil nicht die richtige Folge von Klein- und Großbuchstaben verwendet wird:

C:\\Tools\\Watchernode.msi authentication=trustedserver

Sie können den TrustedServer-Modus nur auf Computern verwenden, die sich im Umkreisnetzwerk befinden. Wenn ein Watcher-Knoten im TrustedServer-Modus ausgeführt wird, müssen Administratoren keine Kennwörter für Testbenutzer auf dem Computer beibehalten.

