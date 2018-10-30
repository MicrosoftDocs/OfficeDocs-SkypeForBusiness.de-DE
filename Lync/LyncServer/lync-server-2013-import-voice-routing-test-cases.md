---
title: 'Lync Server 2013: Importieren von Testfällen für das VoIP-Routing'
TOCTitle: Importieren von Testfällen für das VoIP-Routing
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398460(v=OCS.15)
ms:contentKeyID: 49294223
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Importieren von Testfällen für das VoIP-Routing in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Testfälle bieten Ihnen die Möglichkeit, VoIP-Routen in Ihrer Organisation zu testen: So legen Sie zum Beispiel fest, welche Nummer gewählt werden soll und welche Wähleinstellungen und VoIP-Richtlinie verwendet werden sollen, und Lync Server 2013 überprüft dann, ob die angegebene Nummer unter diesen Bedingungen erfolgreich in das PSTN-Netzwerk geroutet werden kann.

Testfälle, die mithilfe der Lync Server-Systemsteuerung erstellt werden können, werden für gewöhnlich nur auf dem Server gespeichert, auf dem sie ursprünglich erstellt und ausgeführt wurden. Sie können jedoch in Form von XML-Dateien (mit der Erweiterung VTEST) exportiert und dann auf anderen Servern importiert werden. Auf diese Weise können Sie den gleichen Test auf verschiedenen Computern, die sich an unterschiedlichen Stellen in Ihrer Topologie befinden, ausführen.

## So importieren Sie einen Testfall für das VoIP-Routing

1.  Melden Sie sich auf dem Computer als Mitglied der Gruppe "RTCUniversalServerAdmins" oder als Benutzer mit der Rolle "CsVoiceAdministrator", "CsServerAdministrator" oder "CsAdministrator" an. Ausführliche Informationen finden Sie unter [Delegieren von Setupberechtigungen in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** .

4.  Klicken Sie im Menü **Aktionen** auf **Testfälle importieren** .

5.  Suchen Sie nach der Testfalldatei (.VTEST), die Sie importieren möchten, und klicken Sie dann auf **Öffnen** .

6.  Klicken Sie auf **Commit** und anschließend auf **Commit für alle** .
    

    > [!NOTE]
    > Jedes Mal, wenn Sie eine VTEST-Datei importieren, müssen Sie den Befehl <STRONG>Commit für alle</STRONG> ausführen, um den Testfall zu veröffentlichen. Einzelheiten dazu finden Sie in der Betriebsdokumentation unter <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Veröffentlichen von ausstehenden Änderungen an der VoIP-Routingkonfiguration in Lync Server 2013</A>.



## Siehe auch

#### Aufgaben

[Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)

