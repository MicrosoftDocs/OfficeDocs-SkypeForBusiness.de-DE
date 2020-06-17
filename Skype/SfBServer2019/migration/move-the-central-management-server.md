---
title: Migrieren des zentralen Verwaltungsservers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Sie die Migration auf Skype for Business Server 2019 durchführen, müssen Sie den zentralen Verwaltungsserver in den Skype for Business Server 2019 Front-End-Server oder Pool verschieben, bevor Sie den Legacy Server entfernen können.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752467"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Migrieren des Legacy-zentralen Verwaltungsservers zu Skype for Business Server 2019

Nachdem Sie die Migration auf Skype for Business Server 2019 durchführen und bevor Sie den Legacy Server entfernen können, müssen Sie den zentralen Verwaltungsserver in den Skype for Business Server 2019 Front-End-Server oder Pool verschieben. 
  
Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Lese-/Schreibzugriff-Kopie der Datenbank von der Front-End-Server gespeichert wird, die den zentralen Verwaltungsserver enthält. Jeder Computer in der Topologie, einschließlich der Front-End-Server, die den zentralen Verwaltungs Server enthält, verfügt über eine schreibgeschützte Kopie der Daten des zentralen Verwaltungsspeichers in der SQL Server Datenbank (standardmäßig RTCLOCAL), die während des Setups und der Bereitstellung auf dem Computer installiert sind. Die lokale Datenbank erhält Replikat Aktualisierungen über den Skype for Business Server Replikat Replikationsdienst-Agent, der auf allen Computern als Dienst ausgeführt wird. Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht. Auf den Speicherort der Master Datenbank wird in Active Directory-Domänendienste von einem Dienststeuerungspunkt (Service Control Points, SCP) verwiesen. Alle Tools, die den zentralen Verwaltungs Server zum Verwalten und konfigurieren Skype for Business Server verwenden den SCP zum Auffinden des zentralen Verwaltungsspeichers.
  
Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die Datenbanken des zentralen Verwaltungsservers aus dem ursprünglichen Front-End-Server entfernen. Informationen zum Entfernen der Datenbanken des zentralen Verwaltungsservers finden Sie unter [Entfernen der SQL Server Datenbank für ein Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Verwenden Sie das Windows PowerShell **-Cmdlet CsManagementServer** in der Skype for Business Server Verwaltungsshell, um die Datenbank aus der Legacy Installations SQL Server Datenbank in die Skype for Business Server 2019 SQL Server Datenbank zu übertragen, und aktualisieren Sie dann den SCP so, dass er auf den Skype for Business Server 2019-Standort des zentralen Verwaltungsservers verweist. 
  
Verwenden Sie die Verfahren in diesem Abschnitt, um die Skype for Business Server 2019-Front-End-Server vorzubereiten, bevor Sie den zentralen Verwaltungs Server migrieren.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>So bereiten Sie eine Enterprise Edition-Front-End-Pool vor

1. Melden Sie sich im Skype for Business Server 2019 Enterprise Edition-Front-End-Pool, in dem Sie den zentralen Verwaltungs Server verschieben möchten, an dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Sie müssen auch SQL Server Datenbank-sysadmin-Benutzerrechte und-Berechtigungen für die Datenbank haben, in der Sie den zentralen Verwaltungsspeicher installieren möchten. 
    
2. Öffnen Sie die Skype for Business Server Management-Shell.
    
3. Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers in der Skype for Business Server 2019 SQL Server-Datenbank in der Skype for Business Server Verwaltungsshell Folgendes ein:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Stellen Sie sicher, dass der Status des **Skype for Business Server-Front-End-** Diensts **gestartet**wurde.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>So bereiten Sie eine Standard Edition vor Front-End-Server

1. Melden Sie sich auf der Skype for Business Server 2019 Standard Edition-Front-End-Server, in der Sie den zentralen Verwaltungs Server verschieben möchten, an dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. 
    
2. Öffnen Sie den Skype for Business Server-Bereitstellungs-Assistenten.
    
3. Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **erste Standard Edition-Server vorbereiten**.
    
4. Auf der Seite **Befehle werden ausgeführt** wird SQL Server Express als zentraler Verwaltungs Server installiert. Die erforderlichen Firewallregeln werden erstellt. Klicken Sie auf **Fertig stellen**, wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist.
    
    > [!NOTE]
    > Die Erstinstallation kann einige Zeit in Anspruch nehmen, und auf dem Zusammenfassungsbildschirm zur Befehlsausgabe werden keine Aktualisierungen angezeigt. Dies ist auf die Installation von SQL Server Express zurückzuführen. Sie können den Fortschritt der Datenbankinstallation im Task-Manager überwachen. 
  
5. Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers auf dem Skype for Business Server 2019 Standard Edition-Front-End-Server in der Skype for Business Server Verwaltungsshell Folgendes ein: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Stellen Sie sicher, dass der Status des **Skype for Business Server-Front-End-** Diensts **gestartet**wurde.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>So migrieren Sie das Legacy installiert den zentralen Verwaltungs Server in Skype for Business Server 2019

1. Melden Sie sich auf dem Skype for Business Server 2019-Server, der als zentraler Verwaltungsserver verwendet wird, an dem Computer an, auf dem die Skype for Business Server Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank. 
    
2. Öffnen Sie Skype for Business Server Management Shell (als Administrator ausführen).
    
3. Geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Wenn `Enable-CsTopology` nicht erfolgreich ist, lösen Sie das Problem, dass der Befehl nicht abgeschlossen ist, bevor Sie fortfahren. Wenn **enable-CsTopology** nicht erfolgreich ist, tritt bei der Migration ein Fehler auf, und Ihre Topologie kann in einem Zustand bleiben, in dem kein zentraler Verwaltungsspeicher vorhanden ist. 
  
4. Geben Sie im Skype for Business Server 2019 Front-End-Server oder Front-End-Pool in der Skype for Business Server Verwaltungsshell Folgendes ein: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. In Skype for Business Server Verwaltungsshell werden die Server, Dateispeicher, Datenbankspeicher und Dienstverbindungspunkte des aktuellen Status und des Status vorgeschlagen angezeigt. Lesen Sie die Informationen sorgfältig, und bestätigen Sie, dass dies die vorgesehene Quelle und das Ziel ist. Geben Sie **Y** ein, um fortzufahren, oder **N** , um die Bewegung zu beenden. 
    
6. Überprüfen Sie etwaige Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie diese. 
    
7. Öffnen Sie auf dem Server mit Skype for Business Server 2019 den Skype for Business Server-Bereitstellungs-Assistenten. 
    
8. Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Skype for Business Server Komponenten einrichten oder entfernen**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**. 
    
9. Öffnen Sie auf dem Legacy Installationsserver den Bereitstellungs-Assistenten. 
    
10. Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Skype for Business Server Komponenten einrichten oder entfernen**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**. 
    
11. Starten Sie den Skype for Business Server 2019-Server neu. Dies ist aufgrund einer Gruppen Mitgliedschaftsänderung für den Zugriff auf die Datenbank des zentralen Verwaltungsservers erforderlich.
    
12. Um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher ausgeführt wird, geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Bei der Replikation kann es eine Weile dauern, bis alle aktuellen Replikate aktualisiert wurden. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>So entfernen Sie nach einer Migration ältere Installationsdateien für den zentralen Verwaltungsspeicher

1. Melden Sie sich auf dem Legacy Installationsserver an dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank. 
    
2. Öffnen Skype for Business Server Verwaltungsshell
    
    > [!CAUTION]
    > Fahren Sie nicht mit dem Entfernen der vorherigen Datenbankdateien fort, bis die Replikation abgeschlossen und stabil ist. Wenn Sie die Dateien vor der Fertigstellung der Replikation entfernen, unterbrechen Sie den Replikationsprozess und lassen den neu verschobenen zentralen Verwaltungs Server in einem unbekannten Zustand wieder. Verwenden Sie das Cmdlet **Get-CsManagementStoreReplicationStatus** , um den Replikationsstatus zu bestätigen. 
  
3. Geben Sie Folgendes ein, um die Datenbankdateien des zentralen Verwaltungsspeichers aus dem Legacy-Installations zentralen Verwaltungs Server zu entfernen:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Zum Beispiel:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Dabei _\<FQDN of SQL Server\>_ handelt es sich um den Legacy-Installations-Back-End-Server in einer Enterprise Edition-Bereitstellung oder den FQDN des Standard Edition-Server. 
    

