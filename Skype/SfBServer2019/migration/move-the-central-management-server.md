---
title: Verschieben des zentralen Verwaltungsservers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Nach der Migration zu Skype for Business Server 2019 müssen Sie den zentralen Verwaltungsserver auf den Front-End-Server oder -Pool Skype for Business Server 2019 verschieben, bevor Sie den Legacyserver entfernen können.
ms.openlocfilehash: 5c3d090f762904aa5f076033a68e46139b1e84e4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618281"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Verschieben des zentralen Legacyverwaltungsservers auf Skype for Business Server 2019

Nach der Migration zu Skype for Business Server 2019 und bevor Sie den Legacyserver entfernen können, müssen Sie den zentralen Verwaltungsserver auf den Front-End-Server oder -Pool Skype for Business Server 2019 verschieben. 
  
Der zentrale Verwaltungsserver ist ein einzelnes Master-/Mehrfachreplikatsystem, in dem sich die Kopie der Datenbank mit Lese-/Schreibzugriff auf dem Front-End-Server befindet, der den zentralen Verwaltungsserver enthält. Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver enthält, verfügt über eine schreibgeschützte Kopie der Daten des zentralen Verwaltungsspeichers in der SQL Server Datenbank (standardmäßig RTCLOCAL genannt), die während des Setups und der Bereitstellung auf dem Computer installiert ist. Die lokale Datenbank empfängt Replikataktualisierungen über den Skype for Business Server Replikatreplikationsdienst-Agent, der als Dienst auf allen Computern ausgeführt wird. Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungsserver und das lokale Replikat ist XDS, das aus den Dateien "xds.mdf" und "xds.ldf" besteht. Auf den Speicherort der Masterdatenbank wird von einem Dienststeuerungspunkt (Service Control Point, SCP) in Active Directory Domain Services verwiesen. Alle Tools, die den zentralen Verwaltungsserver zum Verwalten und Konfigurieren Skype for Business Server verwenden den SCP, um den zentralen Verwaltungsspeicher zu suchen.
  
Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die Datenbanken des zentralen Verwaltungsservers vom ursprünglichen Front-End-Server entfernen. Informationen zum Entfernen der Datenbanken des zentralen Verwaltungsservers finden Sie unter [Entfernen der SQL Server-Datenbank für einen Front-End-Pool.](remove-the-sql-server-database-for-a-front-end-pool.md)
  
Sie verwenden das Windows PowerShell Cmdlet **Move-CsManagementServer** in der Skype for Business Server-Verwaltungsshell, um die Datenbank von der Legacyinstallationsdatenbank SQL Server in die datenbank Skype for Business Server 2019 SQL Server zu verschieben, und aktualisieren dann die SCP so, dass sie auf den Speicherort des zentralen Verwaltungsservers Skype for Business Server 2019 verweist. 
  
Verwenden Sie die Verfahren in diesem Abschnitt, um die Skype for Business Server 2019 Front-End-Server vorzubereiten, bevor Sie den zentralen Verwaltungsserver verschieben.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>So bereiten Sie einen Enterprise Edition Front-End-Pool vor

1. Melden Sie sich auf dem Skype for Business Server 2019-Enterprise Edition Front-End-Pool, in den Sie den zentralen Verwaltungsserver verschieben möchten, auf dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der Gruppe **"RTCUniversalServerAdmins"** installiert ist. Sie müssen auch SQL Server Datenbank sysadmin-Benutzerrechte und -berechtigungen für die Datenbank haben, in der Sie den zentralen Verwaltungsspeicher installieren möchten. 
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
3. Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers in der Skype for Business Server 2019 SQL Server-Datenbank in der Skype for Business Server Verwaltungsshell Folgendes ein:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Vergewissern Sie sich, dass der Status des **Skype for Business Server Front-End-Diensts** **gestartet** wurde.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>So bereiten Sie einen Standard Edition Front-End-Server vor

1. Melden Sie sich auf dem Skype for Business Server 2019-Standard Edition Front-End-Server, auf den Sie den zentralen Verwaltungsserver verschieben möchten, auf dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der Gruppe **"RTCUniversalServerAdmins"** installiert ist. 
    
2. Öffnen Sie den Skype for Business Server-Bereitstellungs-Assistenten.
    
3. Klicken Sie im Skype for Business Server Bereitstellungs-Assistenten auf **"Vorbereiten" Standard Edition Servers.**
    
4. Auf der Seite **"Befehle ausführen"** wird SQL Server Express als zentraler Verwaltungsserver installiert. Die erforderlichen Firewallregeln werden erstellt. Klicken Sie auf **Fertig stellen**, wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist.
    
    > [!NOTE]
    > Die Erstinstallation kann einige Zeit in Anspruch nehmen, und auf dem Zusammenfassungsbildschirm zur Befehlsausgabe werden keine Aktualisierungen angezeigt. Dies ist auf die Installation von SQL Server Express zurückzuführen. Sie können den Fortschritt der Datenbankinstallation im Task-Manager überwachen. 
  
5. Geben Sie zum Erstellen des neuen zentralen Verwaltungsspeichers auf dem Skype for Business Server 2019 Standard Edition Front-End-Server in der Skype for Business Server Verwaltungsshell Folgendes ein: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Vergewissern Sie sich, dass der Status des **Skype for Business Server Front-End-Diensts** **gestartet** wurde.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>So verschieben Sie die Legacyinstallation des zentralen Verwaltungsservers auf Skype for Business Server 2019

1. Melden Sie sich auf dem Skype for Business Server 2019-Server, der der zentrale Verwaltungsserver sein wird, bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der Gruppe **"RTCUniversalServerAdmins"** installiert ist. Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank. 
    
2. Öffnen Sie Skype for Business Server Verwaltungsshell (als Administrator ausführen).
    
3. Geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Wenn `Enable-CsTopology` der Vorgang nicht erfolgreich ist, beheben Sie das Problem, das verhindert, dass der Befehl abgeschlossen wird, bevor Sie fortfahren. Wenn **Enable-CsTopology** nicht erfolgreich ist, schlägt die Verschiebung fehl, und ihre Topologie befindet sich möglicherweise in einem Zustand, in dem kein zentraler Verwaltungsspeicher vorhanden ist. 
  
4. Geben Sie auf dem Skype for Business Server 2019 Front-End-Server oder Front-End-Pool in der Skype for Business Server-Verwaltungsshell Folgendes ein: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. Skype for Business Server Die Verwaltungsshell zeigt die Server, Dateispeicher, Datenbankspeicher und die Dienstverbindungspunkte des aktuellen und des vorgeschlagenen Status an. Lesen Sie die Informationen sorgfältig durch, und vergewissern Sie sich, dass dies die beabsichtigte Quelle und das Ziel ist. Geben Sie **Y** ein, um fortzufahren, oder **N,** um die Verschiebung zu beenden. 
    
6. Überprüfen Sie etwaige Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie diese. 
    
7. Öffnen Sie auf dem Server Skype for Business Server 2019 den Skype for Business Server-Bereitstellungs-Assistenten. 
    
8. Klicken Sie in Skype for Business Server Bereitstellungs-Assistenten auf **"Skype for Business Server System installieren oder aktualisieren",** klicken Sie auf **Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten,** klicken Sie auf **"Weiter",** überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **"Fertig stellen".** 
    
9. Öffnen Sie auf dem Legacyinstallationsserver den Bereitstellungs-Assistenten. 
    
10. Klicken Sie in Skype for Business Server Bereitstellungs-Assistenten auf **"Skype for Business Server System installieren oder aktualisieren",** klicken Sie auf **Schritt 2: Einrichten oder Entfernen Skype for Business Server Komponenten,** klicken Sie auf **"Weiter",** überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **"Fertig stellen".** 
    
11. Starten Sie den Skype for Business Server 2019-Server neu. Dies ist aufgrund einer Änderung der Gruppenmitgliedschaft erforderlich, um auf die Datenbank des zentralen Verwaltungsservers zuzugreifen.
    
12. Um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher erfolgt, geben Sie in der Skype for Business Server Verwaltungsshell Folgendes ein: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Bei der Replikation kann es eine Weile dauern, bis alle aktuellen Replikate aktualisiert wurden. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>So entfernen Sie Legacyinstallationsdateien für den zentralen Verwaltungsspeicher nach einer Verschiebung

1. Melden Sie sich auf dem Legacyinstallationsserver beim Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der Gruppe **"RTCUniversalServerAdmins"** installiert ist. Darüber hinaus benötigen Sie Administratorrechte und -berechtigungen für die SQL Server-Datenbank. 
    
2. Öffnen Skype for Business Server-Verwaltungsshell
    
    > [!CAUTION]
    > Fahren Sie erst mit dem Entfernen der vorherigen Datenbankdateien fort, wenn die Replikation abgeschlossen und stabil ist. Wenn Sie die Dateien vor Abschluss der Replikation entfernen, unterbrechen Sie den Replikationsprozess und lassen den neu verschobenen zentralen Verwaltungsserver in einem unbekannten Zustand. Verwenden Sie das Cmdlet **"Get-CsManagementStoreReplicationStatus",** um den Replikationsstatus zu bestätigen. 
  
3. Geben Sie Folgendes ein, um die Datenbankdateien des zentralen Verwaltungsspeichers aus der Legacyinstallation des zentralen Verwaltungsservers zu entfernen:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Zum Beispiel:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Dabei handelt es sich _\<FQDN of SQL Server\>_ entweder um den Legacyinstallations-Back-End-Server in einer Enterprise Edition-Bereitstellung oder den FQDN des Standard Edition Servers. 
    

