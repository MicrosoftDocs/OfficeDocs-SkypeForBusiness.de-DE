---
title: Entfernen der Zuordnung des Monitoring Servers
TOCTitle: Entfernen der Zuordnung des Monitoring Servers
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49890932
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Entfernen der Zuordnung des Monitoring Servers

 

_**Letztes Änderungsdatum des Themas:** 2012-10-04_

Zum Entfernen des Monitoring-Server müssen Sie die Abhängigkeit vom zugeordneten Front-End-Pool, Front-End-Server, Survivable Branch-Anwendung und Survivable Branch-Server ändern oder löschen. Zum Entfernen der Abhängigkeit bearbeiten Sie die Eigenschaften von Front-End-Pool, Front-End-Server, Survivable Branch-Anwendung und Survivable Branch-Server. Nach dem Entfernen der Abhängigkeit und dem Löschen des Servers im Topologie-Generator werden Sie benachrichtigt, dass das zugeordnete Datenbankspeicherobjekt im Topologie-Generator ebenfalls gelöscht wird.

## So entfernen Sie die Monitoring Server-Zuordnung

1.  Öffnen Sie den Lync Server 2013-Front-End-Server, und öffnen Sie dann den Topologie-Generator.

2.  Navigieren Sie zum Knoten Lync Server 2010.

3.  Erweitern Sie im Topologie-Generator die Optionen **Enterprise Edition-Front-End-Pools** , **Standard Edition-Front-End-Server** oder **Zweigniederlassungen** , abhängig davon, an welcher Stelle der Monitoring-Server definiert ist.

4.  Bei einer Zuordnung von Survivable Branch-Server erweitern Sie **Zweigniederlassungen** , den Namen des Zweigniederlassung und dann **Survivable Branch Appliances** .
    

    > [!NOTE]
    > <STRONG>Survivable Branch Appliances</STRONG> auf der Benutzeroberfläche gilt sowohl für Survivable Branch-Server als auch für Survivable Branch-Anwendung.



5.  Klicken Sie mit der rechten Maustaste auf den Pool, Server oder das Gerät, der bzw. das dem Monitoring-Server zugeordnet ist, und klicken Sie dann auf **Eigenschaften bearbeiten** .

6.  Deaktivieren Sie in **Eigenschaften bearbeiten** , unter **Allgemein** , unter **Zuordnungen** das Kontrollkästchen **Monitoring Server zuordnen** , und klicken Sie dann auf **OK** .

7.  Wiederholen Sie den vorherigen Schritt für alle anderen Pools, Server oder Geräte, die dem Monitoring-Server zugeordnet sind.

8.  Klicken Sie mit der rechten Maustaste auf den Monitoring-Server, und klicken Sie dann auf **Löschen** .

9.  Klicken Sie unter **Abhängige Speicher löschen** auf **OK** .

10. Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, führen Sie bei Bedarf den Lync Server-Bereitstellungs-Assistent aus.

