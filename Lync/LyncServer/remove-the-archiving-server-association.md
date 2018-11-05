---
title: Entfernen der Zuordnung des Archivierungsservers
TOCTitle: Entfernen der Zuordnung des Archivierungsservers
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49890967
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen der Zuordnung des Archivierungsservers

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Zum Entfernen eines Archivierungsservers müssen Sie die Abhängigkeit vom zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch-Anwendung und Survivable Branch-Server ändern oder löschen. Zum Entfernen der Abhängigkeit bearbeiten Sie die Eigenschaften von Front-End-Pool, Front-End-Server, Survivable Branch-Anwendung und Survivable Branch-Server. Nach dem Entfernen der Abhängigkeit und dem Löschen des Servers im Topologie-Generator werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicherobjekt im Topologie-Generator ebenfalls gelöscht wird.

## So entfernen Sie die Zuordnung des Archivierungsservers

1.  Öffnen Sie den Lync Server 2013-Front-End-Server, und öffnen Sie dann den Topologie-Generator.

2.  Navigieren Sie zum Knoten Lync Server 2010.

3.  Erweitern Sie im Topologie-Generator die Optionen **Enterprise Edition-Front-End-Pools** , **Standard Edition-Front-End-Server** oder **Zweigniederlassungen** , abhängig davon, an welcher Stelle der Archivierungsserver definiert ist.

4.  Bei einer Zuordnung von Survivable Branch-Server erweitern Sie **Zweigniederlassungen** , den Namen des Zweigniederlassung und dann **Survivable Branch Appliances** .
    

    > [!NOTE]
    > <STRONG>Survivable Branch Appliances</STRONG> auf der Benutzeroberfläche gilt sowohl für Survivable Branch-Server als auch für Survivable Branch-Anwendung.



5.  Klicken Sie mit der rechten Maustaste auf den Pool, Server oder das Gerät, der bzw. das dem Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten** .

6.  Deaktivieren Sie in **Eigenschaften bearbeiten** , unter **Allgemein** , unter **Zuordnungen** das Kontrollkästchen **Archivierungsserver zuordnen** , und klicken Sie dann auf **OK** .

7.  Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Archivierungsserver zugeordnet sind, der entfernt werden soll.

8.  Klicken Sie mit der rechten Maustaste auf den Archivierungsserver, und klicken Sie dann auf **Löschen** .

9.  Klicken Sie unter **Abhängige Speicher löschen** auf **OK** .

10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann je nach Bedarf den Lync Server-Bereitstellungs-Assistenten aus.

