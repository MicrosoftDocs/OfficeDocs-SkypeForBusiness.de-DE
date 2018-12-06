---
title: 'Lync Server 2013: Anmelden bei und Verwenden von Lync 2013 auf dem virtuellen Computer'
TOCTitle: Anmelden bei und Verwenden von Lync 2013 auf dem virtuellen Computer
ms:assetid: 6140fc19-5bef-4b58-9b0f-19112b5ecd00
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204948(v=OCS.15)
ms:contentKeyID: 49294173
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anmelden bei und Verwenden von Lync 2013 auf dem virtuellen Computer

 

_**Letztes Änderungsdatum des Themas:** 2012-10-03_

Nach der Aktivierung des VDI-Plug-Ins geschieht Folgendes, wenn sich der Benutzer bei Lync 2013 anmeldet.

1.  Der Benutzer gibt seine Anmeldeinformationen für den Lync 2013-Client ein, der auf der virtuellen Maschine ausgeführt wird.

2.  Nachdem Lync erkannt hat, dass das VDI-Plug-in verfügbar ist, fordert Lync den Benutzer auf, seine Anmeldeinformationen erneut einzugeben. Es wird empfohlen, in diesem Dialogfeld das Kontrollkästchen **Kennwort speichern** zu aktivieren, damit der Benutzer seine Anmeldeinformationen bei folgenden Anmeldevorgängen nicht erneut eingeben muss.

3.  Lync beginnt, eine Kopplung mit dem VDI-Plug-in durchzuführen. Vor Abschluss der Kopplung zeigt der Client zwei Symbole auf der Statusleiste Lync an. Das Symbol links unten zeigt an, dass keine Audiogeräte verfügbar sind, während das blinkende Symbol rechts unten signalisiert, dass der VDI-Kopplungsvorgang gerade durchgeführt wird. Das sieht wie folgt aus:
    
    ![Lync VDI-Symbol mit erfolgreicher Koppelung](images/JJ204713.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI-Symbol mit erfolgreicher Koppelung")  

4.  Nach einer erfolgreichen VDI-Kopplung ändern sich die Symbole und zeigen nun das für Anrufe verwendete Audiogerät bzw. den Erfolg der VDI-Kopplung an:
    
    ![Symbol für Lync VDI-Kopplung mit Erfolgsanzeige](images/JJ204948.57be3387-a3e5-4949-831e-f5ff9fcc5598(OCS.15).png "Symbol für Lync VDI-Kopplung mit Erfolgsanzeige")  

5.  Nach der Kopplung von Lync mit dem VDI-Plug-in kann der Benutzer seine Anwesenheit auf Lync-kompatiblen Geräten erkennen, die mit dem lokalen Computer verbunden sind. Nun kann der Benutzer Anrufe wie gewohnt tätigen oder entgegennehmen.

