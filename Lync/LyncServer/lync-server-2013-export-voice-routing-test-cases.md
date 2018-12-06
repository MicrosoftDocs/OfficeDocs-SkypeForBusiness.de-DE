---
title: 'Lync Server 2013: Exportieren von Testfällen für das VoIP-Routing'
TOCTitle: Exportieren von Testfällen für das VoIP-Routing
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425957(v=OCS.15)
ms:contentKeyID: 49293891
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportieren von Testfällen für das VoIP-Routing in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Testfälle bieten Ihnen die Möglichkeit, VoIP-Routen in Ihrer Organisation zu testen: So legen Sie zum Beispiel fest, welche Nummer gewählt werden soll und welche Wähleinstellungen und VoIP-Richtlinie verwendet werden sollen, und Lync Server überprüft dann, ob die angegebene Nummer unter diesen Bedingungen erfolgreich in das PSTN-Netzwerk geroutet werden kann.

Testfälle, die mithilfe der Lync Server-Systemsteuerung erstellt werden können, werden für gewöhnlich nur auf dem Server gespeichert, auf dem sie ursprünglich erstellt und ausgeführt wurden. Sie können jedoch in Form von XML-Dateien (mit der Erweiterung VTEST) exportiert und dann auf anderen Servern importiert werden. Auf diese Weise können Sie den gleichen Test auf verschiedenen Computern, die sich an unterschiedlichen Stellen in Ihrer Topologie befinden, ausführen.

## So exportieren Sie einen Testfall für das VoIP-Routing

1.  Klicken Sie in Lync Server-Systemsteuerung auf **VoIP-Routing** und dann auf **VoIP-Routing testen** .

2.  Wählen Sie auf der Registerkarte **VoIP-Routing testen** den Testfall (oder die Testfälle) aus, die exportiert werden sollen. Sie können mehrere Fälle auswählen, indem Sie auf den ersten Fall klicken, der exportiert werden soll, und beim Klicken auf weitere Fälle die STRG-Taste gedrückt halten.

3.  Klicken Sie auf **Aktion** und dann auf **Testfälle exportieren** .

4.  Wählen Sie im Dialogfeld **Speichern unter** einen Ordner aus, in dem die exportierten Testfälle gespeichert werden sollen, und geben Sie einen Namen für die resultierende XML-Datei im Feld **Dateiname** ein. Wenn Sie mehrere Testfälle exportieren, werden alle Testfälle in einer einzelnen XML-Datei gespeichert.

5.  Klicken Sie auf **Speichern** , um die Testfälle zu speichern.

## Siehe auch

#### Aufgaben

[Importieren von Testfällen für das VoIP-Routing in Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)

