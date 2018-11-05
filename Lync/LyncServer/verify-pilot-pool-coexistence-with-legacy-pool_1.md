---
title: Überprüfen der Koexistenz der Pilotinstallation mit Legacypools
TOCTitle: Überprüfen der Koexistenz der Pilotinstallation mit Legacypools
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204914(v=OCS.15)
ms:contentKeyID: 49294092
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Überprüfen der Koexistenz der Pilotinstallation mit Legacypools

 

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

## Überprüfen des Pools im Office Communications Server 2007 R2-Verwaltungstool

1.  Öffnen Sie das Verwaltungstool von Office Communications Server 2007 R2.

2.  Erweitern Sie den Knoten **Gesamtstruktur** , den Knoten **Standard Edition-Server** oder **Enterprise-Pools** und dann den Pool- oder Servernamen.

3.  Stellen Sie sicher, dass die Office Communications Server 2007 R2-Dienste im Pool ausgeführt werden.
    
    ![Office Communications Server 2007 R2-Verwaltungskonsole](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2-Verwaltungskonsole")  

## Überprüfen des Pilotpools in der Lync Server 2013-Systemsteuerung

1.  Melden Sie sich mit einem Benutzerkonto, das Mitglied der CsAdministrator-Rolle ist, beim Lync Server 2013-Front-End-Server an.

2.  Öffnen Sie ein Browserfenster, und geben Sie die Admin-URL ein, um die Lync Server-Systemsteuerung zu öffnen. Informationen zu den verschiedenen Methoden zum Starten der Lync Server-Systemsteuerung finden Sie unter [Öffnen von Lync Server-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Klicken Sie auf **Topologie** .

4.  Vergewissern Sie sich, dass die bereitgestellten Server im Pilotpool vorhanden sind.
    
    ![Lync Server-Systemsteuerung – Topologie (Seite)](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Lync Server-Systemsteuerung – Topologie (Seite)")  

## Start der Lync Server 2013-Dienste sicherstellen

1.  Öffnen Sie auf dem Lync Server 2013-Front-End-Server in der Gruppe **Verwaltungstools** das Applet **Dienste** .

2.  Vergewissern Sie sich, dass die aufgeführten Dienste mit der Liste in der folgenden Abbildung übereinstimmen.
    
    ![Dienstseite mit gestarteten Lync-Diensten](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Dienstseite mit gestarteten Lync-Diensten")

