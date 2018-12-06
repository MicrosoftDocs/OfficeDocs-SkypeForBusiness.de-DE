---
title: Upgraden oder Updaten eines Back-End-Servers oder Standard Edition-Servers in Lync Server 2013
TOCTitle: Upgraden oder Updaten eines Back-End-Servers oder Standard Edition-Servers in Lync Server 2013
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49891029
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Upgraden oder Updaten eines Back-End-Servers oder Standard Edition-Servers in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

In diesem Thema wird erklärt, wie Sie ein Update auf einem Enterprise Edition-Back-End-Server oder einem Standard Edition-Server installieren.

Wenn ein Back-End-Server mindestens 30 Minuten lang ausfällt, während Sie ein Upgrade durchführen, können die Benutzer in den Ausfallsicherheitsmodus geschaltet werden. Nach Abschluss des Upgrades und nachdem der Back-End-Server wieder eine Verbindung mit den Front-End-Servern im Pool hat, erhalten die Benutzer die volle Funktionalität zurück. Dauert das Upgrade weniger als 30 Minuten, sind die Benutzer davon nicht betroffen.

## So updaten Sie einen Back-End-Server oder einen Standard Edition-Server

1.  Melden Sie sich am Server, für den Sie das Upgrade vornehmen, als Mitglied der Rolle **CsAdministrator** an.

2.  Laden Sie das Update herunter, und extrahieren Sie es auf die lokale Festplatte.

3.  Starten Sie die Lync Server-Verwaltungsshell: Klicken Sie im Startmenü auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

4.  Beenden Sie die Lync Server-Dienste. Geben Sie an der Befehlszeile Folgendes ein:
    
        Stop-CsWindowsService

5.  Beenden Sie den WWW-Dienst (World Wide Web). Geben Sie an der Befehlszeile Folgendes ein:
    
        net stop w3svc

6.  Schließen Sie alle Fenster der Lync Server-Verwaltungsshell.

7.  Installieren Sie das Update.

8.  Starten Sie die Lync Server-Verwaltungsshell: Klicken Sie im Startmenü auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Verwaltungsshell**.

9.  Beenden Sie die Lync Server-Dienste erneut, um Assemblys vom Typ des globalen Assemblycache (GAC) –d zu erfassen. Geben Sie an der Befehlszeile Folgendes ein:
    
        Stop-CsWindowsService

10. Starten Sie den WWW-Dienst neu. Geben Sie an der Befehlszeile Folgendes ein:
    
        net start w3svc

11. Übernehmen Sie die mit **LyncServerUpdateInstaller.exe** vorgenommenen Änderungen für die SQL Server-Datenbanken, indem Sie einen der folgenden Schritte ausführen:
    
      - Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und sich auf diesem Server keine gemeinsam ausgeführten Datenbanken befinden, z. B. Archivierungs- oder Überwachungsdatenbanken, geben Sie an der Befehlszeile Folgendes ein:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - Wenn es sich um einen Enterprise Edition-Back-End-Server handelt und auf diesem Server gemeinsam ausgeführte Datenbanken vorhanden sind, geben Sie an der Befehlszeile Folgendes ein:
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - Wenn es sich um einen Standard Edition-Server handelt, geben Sie an der Befehlszeile Folgendes ein:
        
            Install-CsDatabase -Update -LocalDatabases

