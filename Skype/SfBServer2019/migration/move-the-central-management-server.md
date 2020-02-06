---
title: Verschieben des zentralen Verwaltungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie den zentralen Verwaltungsserver auf den Front-End-Server oder Pool von Skype for Business Server 2019 verschieben, bevor Sie den Legacy Server entfernen können.
ms.openlocfilehash: 6f78a242ce42a3dca56cc1e4e1f2fa604611d68c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813243"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Verschieben des Legacy-zentralen Verwaltungsservers in Skype for Business Server 2019

Nachdem Sie zu Skype for Business Server 2019 migriert haben, müssen Sie den zentralen Verwaltungsserver auf den Front-End-Server oder Pool von Skype for Business Server 2019 verschieben, bevor Sie den Legacy Server entfernen können. 
  
Bei dem zentralen Verwaltungsserver handelt es sich um ein einzelnes Master/Multiple-Replikat System, bei dem die Kopie der Datenbank vom Front-End-Server, auf dem sich der zentrale Verwaltungsserver befindet, gelesen/geschrieben wird. Jeder Computer in der Topologie, einschließlich des Front-End-Servers, der den zentralen Verwaltungsserver enthält, verfügt über eine schreibgeschützte Kopie der zentralen Verwaltungsspeicher Daten in der SQL Server-Datenbank (standardmäßig mit dem Namen RTCLOCAL), die während des Setups auf dem Computer installiert sind, und Bereitstellungs. Die lokale Datenbank erhält Replikat Updates über den Skype for Business Server Replica Replicator-Agent, der auf allen Computern als Dienst ausgeführt wird. Der Name der tatsächlichen Datenbank auf dem zentralen Verwaltungs Server und das lokale Replikat ist XDS, das aus den Dateien XDS. mdf und XDS. ldf besteht. Auf den Speicherort der Master Datenbank wird in den Active Directory-Domänendiensten von einem Dienst Kontrollpunkt (Service Control Point, SCP) verwiesen. Alle Tools, die den zentralen Verwaltungsserver zum Verwalten und Konfigurieren von Skype for Business Server verwenden, verwenden den SCP, um den zentralen Verwaltungsspeicher zu finden.
  
Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die zentralen Verwaltungsserver Datenbanken vom ursprünglichen Front-End-Server entfernen. Informationen zum Entfernen der zentralen Verwaltungs Server-Datenbanken finden Sie unter [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Sie verwenden das Windows PowerShell **-Cmdlet Move-CsManagementServer** in der Skype for Business Server-Verwaltungsshell, um die Datenbank aus der Legacy-Installations-SQL Server-Datenbank in die SQL Server-Datenbank von Skype for Business Server 2019 zu verschieben und dann den SCP so zu aktualisieren, dass er auf den Standort des zentralen Verwaltungsservers von Skype for Business Server 2019 verweist. 
  
Führen Sie die Verfahren in diesem Abschnitt aus, um die Front-End-Server für Skype for Business Server 2019 vorzubereiten, bevor Sie den zentralen Verwaltungs Server verschieben.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Vorbereiten eines Enterprise Edition-Front-End-Pools

1. Melden Sie sich auf dem Skype for Business Server 2019 Enterprise Edition-Front-End-Pool, in dem Sie den zentralen Verwaltungs Server umsiedeln möchten, bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Sie müssen auch über die SQL Server-Datenbank sysadmin-Benutzerrechte und-Berechtigungen für die Datenbank verfügen, in der Sie den zentralen Verwaltungsspeicher installieren möchten. 
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
3. Zum Erstellen des neuen zentralen Verwaltungsspeichers in der Skype for Business Server 2019 SQL Server-Datenbank geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Vergewissern Sie sich, dass der Status des **Skype for Business Server-Front-End-** Diensts **gestartet**wurde.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Vorbereiten eines Standard Edition-Front-End-Servers

1. Melden Sie sich auf dem Skype for Business Server 2019 Standard Edition-Front-End-Server, auf dem Sie den zentralen Verwaltungsserver umsiedeln möchten, bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. 
    
2. Öffnen Sie den Skype for Business Server-Bereitstellungs-Assistenten.
    
3. Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **First Standard Edition-Server vorbereiten**.
    
4. Auf der Seite **Ausführungsbefehle** wird SQL Server Express als zentraler Verwaltungs Server installiert. Es werden erforderliche Firewallregeln erstellt. Wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    
    > [!NOTE]
    > Die anfängliche Installation kann einige Zeit in Anspruch nehmen, ohne dass die Anzeige des Befehlsausgabe Zusammenfassungsbildschirms sichtbar wird. Dies ist auf die Installation von SQL Server Express zurückzuführen. Wenn Sie die Installation der Datenbank überwachen müssen, verwenden Sie den Task-Manager, um das Setup zu überwachen. 
  
5. Zum Erstellen des neuen zentralen Verwaltungsspeichers auf dem Skype for Business Server 2019 Standard Edition-Front-End-Server geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Vergewissern Sie sich, dass der Status des **Skype for Business Server-Front-End-** Diensts **gestartet**wurde.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>So verschieben Sie die Legacy Installation des zentralen Verwaltungsservers in Skype for Business Server 2019

1. Melden Sie sich auf dem Skype for Business Server 2019-Server, der der zentrale Verwaltungsserver sein soll, bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Sie müssen auch über die Benutzerrechte und-Berechtigungen des SQL Server-Datenbankadministrators verfügen. 
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell (als Administrator ausführen).
    
3. Geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Wenn `Enable-CsTopology` dies nicht der Fall ist, beheben Sie das Problem, das verhindert, dass der Befehl abgeschlossen wird, bevor Sie fortfahren. Wenn **enable-CsTopology** nicht erfolgreich ist, schlägt die Verschiebung fehl, und Sie verlässt Ihre Topologie möglicherweise in einem Zustand, in dem kein zentraler Verwaltungsspeicher vorhanden ist. 
  
4. Geben Sie auf dem Skype for Business Server 2019-Front-End-Server oder-Front-End-Pool in der Skype for Business Server-Verwaltungsshell Folgendes ein: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. In der Skype for Business Server-Verwaltungsshell werden die Server, Dateispeicher, Datenbankspeicher und die Dienstverbindungspunkte des aktuellen Zustands sowie der vorgeschlagene Status angezeigt. Lesen Sie die Informationen sorgfältig durch, und bestätigen Sie, dass dies die beabsichtigte Quelle und das Ziel ist. Geben Sie **Y** ein, um fortzufahren, oder **N** , um die Verschiebung zu beenden. 
    
6. Überprüfen Sie alle Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert wurden, und beheben Sie Sie. 
    
7. Öffnen Sie auf dem Skype for Business Server 2019-Server den Bereitstellungs-Assistenten für Skype for Business Server. 
    
8. Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**. 
    
9. Öffnen Sie auf dem Legacy Installationsserver den Bereitstellungs-Assistenten. 
    
10. Klicken Sie im Skype for Business Server-Bereitstellungs-Assistenten auf **Skype for Business Server System installieren oder aktualisieren**, klicken Sie auf **Schritt 2: Einrichten oder Entfernen von Skype for Business Server-Komponenten**, klicken Sie auf **weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf **Fertig stellen**. 
    
11. Starten Sie den Skype for Business Server 2019-Server neu. Dies ist aufgrund einer Änderung der Gruppenmitgliedschaft für den Zugriff auf die zentrale Verwaltungs Server-Datenbank erforderlich.
    
12. Um zu bestätigen, dass die Replikation mit dem neuen zentralen Verwaltungsspeicher erfolgt, geben Sie in der Skype for Business Server-Verwaltungsshell Folgendes ein: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Die Replikation kann einige Zeit dauern, bis alle aktuellen Replikate aktualisiert wurden. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>So entfernen Sie Legacy-Installationen von Central Management Store-Dateien nach einem Umzug

1. Melden Sie sich auf dem Legacy Installationsserver bei dem Computer an, auf dem die Skype for Business Server-Verwaltungsshell als Mitglied der **RTCUniversalServerAdmins** -Gruppe installiert ist. Sie müssen auch über die Benutzerrechte und-Berechtigungen des SQL Server-Datenbankadministrators verfügen. 
    
2. Öffnen der Skype for Business Server-Verwaltungsshell
    
    > [!CAUTION]
    > Gehen Sie nicht mit dem Entfernen der vorherigen Datenbankdateien fort, bis die Replikation abgeschlossen und stabil ist. Wenn Sie die Dateien vor dem Abschließen der Replikation entfernen, werden Sie den Replikationsprozess unterbrechen und den neu verschobenen zentralen Verwaltungs Server in einem unbekannten Zustand belässt. Verwenden Sie das Cmdlet **Get-CsManagementStoreReplicationStatus** , um den Replikationsstatus zu bestätigen. 
  
3. Geben Sie Folgendes ein, um die Datenbankdateien des zentralen Verwaltungsspeichers aus dem Legacy install Central-Verwaltungs Server zu entfernen:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Beispiel:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Hierbei handelt es sich bei dem _ \<FQDN von SQL Server\> _ entweder um den Legacy-Installations-Back-End-Server in einer Enterprise Edition-Bereitstellung oder um den FQDN des Standard Edition-Servers. 
    

