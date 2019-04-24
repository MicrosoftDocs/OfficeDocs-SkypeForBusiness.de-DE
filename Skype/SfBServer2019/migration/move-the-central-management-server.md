---
title: Verschieben des zentralen Verwaltungsservers
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nach der Migration zu Skype für Business Server 2019, müssen Sie den zentralen Verwaltungsserver an der Skype für Business Server 2019 Front-End-Server oder Pool verschieben, bevor Sie dem-Legacyserver entfernen können.
ms.openlocfilehash: dc85548a3c81e55267bc0ed3a32e53860e4bce09
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231574"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Verschieben der Vorversion zentralen Verwaltungsserver in Skype für Business Server 2019

Nach der Migration zu Skype für Business Server 2019 und bevor Sie dem-Legacyserver entfernen können, müssen Sie den zentralen Verwaltungsserver in der Skype für Business Server 2019 Front-End-Server oder Pool zu verschieben. 
  
Den zentralen Verwaltungsserver ist ein einzelnes Master/mehreren Replikat System, auf dem wird die Lese-Schreib-Kopie der Datenbank vom Front-End-Server gespeichert, der den zentralen Verwaltungsserver enthält. Auf jedem Computer in der Topologie, einschließlich der Front-End-Server, der den zentralen Verwaltungsserver enthält ist eine schreibgeschützte Kopie der zentralen Speicherdaten in SQL Server-Datenbank (namens RTCLOCAL standardmäßig) auf dem Computer während des Setups installiert und Einsatz. Die lokale Datenbank empfängt Replikat Updates über die Skype für Business Server Replikat Replikations-Agent, der als Dienst auf allen Computern ausgeführt wird. Der Name der aktuellen Datenbank auf den zentralen Verwaltungsserver und dem lokalen Replikat ist XDS, die der Dateien xds.mdf und xds.ldf besteht. Einen Dienststeuerungspunkt (SCP) in Active Directory Domain Services verweist auf der Speicherort der master-Datenbank. Alle Tools, die verwenden den zentralen Verwaltungsserver Skype für Business Server konfigurieren und verwalten, mithilfe des zentralen Verwaltungsspeichers Suchen des Dienstverbindungspunkts.
  
Nachdem Sie den zentralen Verwaltungsserver erfolgreich verschoben haben, sollten Sie die Datenbanken zentralen Verwaltungsserver vom ursprünglichen Front-End-Server entfernen. Informationen zum Entfernen von der zentralen Verwaltungsserver-Datenbanken finden Sie unter [Entfernen der SQL Server-Datenbank für einen Front-End-Pool](remove-the-sql-server-database-for-a-front-end-pool.md).
  
Sie verwenden das Windows PowerShell-Cmdlet **Move-CsManagementServer** in der Skype für Business Server-Verwaltungsshell zum Verschieben der Datenbank aus der Vorversion installieren SQL Server-Datenbank die Skype für Business Server 2019 SQL Server-Datenbank, und aktualisieren Sie die SCP So zeigen Sie auf die Skype für Business Server 2019 zentraler Verwaltungsserver Speicherort. 
  
Verwenden Sie die Verfahren in diesem Abschnitt, um die Skype für Business Server 2019 Front-End-Server vorbereiten, bevor Sie den zentralen Verwaltungsserver verschieben.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>So bereiten Sie einen Enterprise Edition-Front-End-Pool vor

1. Klicken Sie auf die Skype für Business Server 2019 Enterprise Edition-Front-End-Pool, in dem Sie den zentralen Verwaltungsserver verschieben möchten, melden Sie sich an dem Computer, auf dem die Skype für Business Server-Verwaltungsshell installiert ist, als Mitglied der **"RTCUniversalServerAdmins" **Gruppe. Auch benötigen SQL Server-Datenbank Sysadmin Benutzerrechte und-Berechtigungen für die Datenbank Sie, wo Sie den zentralen Verwaltungsspeicher installieren möchten. 
    
2. Öffnen Sie die Skype für Business Server-Verwaltungsshell.
    
3. Geben Sie Folgendes ein, um den neuen zentralen Verwaltungsspeicher in der Skype für Business Server 2019 SQL Server-Datenbank in der Skype für Business Server-Verwaltungsshell zu erstellen:
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Vergewissern Sie sich, dass der Status der **Skype für Business Server Front-End** -Dienst **gestartet**wird.
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>So bereiten Sie einen Standard Edition-Front-End-Server vor

1. Melden Sie auf der Skype für Business Server 2019 Standard Edition-Front-End-Server, auf dem Sie den zentralen Verwaltungsserver verschieben möchten sich an dem Computer, auf dem die Skype für Business Server-Verwaltungsshell installiert ist, als Mitglied der **"RTCUniversalServerAdmins" **Gruppe. 
    
2. Öffnen Sie die Skype für Business Server-Bereitstellungs-Assistenten.
    
3. Klicken Sie in der Skype für Business Server-Bereitstellungs-Assistenten **Vorbereiten des ersten Standard Edition-Servers**auf.
    
4. Auf der Seite **Befehle ausführen** ist SQL Server Express als den zentralen Verwaltungsserver installiert. Erforderlichen Firewallregeln erstellt werden. Wenn die Installation der Datenbank und der erforderlichen Software abgeschlossen ist, klicken Sie auf **Fertig stellen**.
    
    > [!NOTE]
    > Die ursprüngliche Installation kann einige Zeit ohne sichtbar Aktualisierung zum Befehl Ausgabe im Fenster Zusammenfassung dauern. Dies ist aufgrund der Installation von SQL Server Express. Wenn Sie die Installation der Datenbank überwachen möchten, verwenden Sie zum Überwachen der Einrichtung Task-Manager. 
  
5. Geben Sie Folgendes ein, um den neuen zentralen Verwaltungsspeicher auf die Skype für Business Server 2019 Standard Edition-Front-End-Server in der Skype für Business Server-Verwaltungsshell zu erstellen: 
    
   ```
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Vergewissern Sie sich, dass der Status der **Skype für Business Server Front-End** -Dienst **gestartet**wird.
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>So verschieben Sie die Vorversion installiert zentralen Verwaltungsserver in Skype für Business Server 2019

1. Melden Sie sich die Skype für Business Server 2019-Server, die den zentralen Verwaltungsserver werden, auf dem Computer, auf dem der Skype für Business Server-Verwaltungsshell, als Mitglied der Gruppe **RTCUniversalServerAdmins installiert ist** an. Sie müssen auch die SQL Server-Datenbank Benutzer Administratorrechte und-Berechtigungen verfügen. 
    
2. Öffnen Sie Skype für Business Server-Verwaltungsshell.
    
3. Geben Sie in der Skype für Business Server-Verwaltungsshell Folgendes ein: 
    
   ```
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Wenn `Enable-CsTopology` ist nicht erfolgreich, lösen Sie das Problem verhindert, dass des Befehls abschließen, bevor Sie fortfahren. Wenn die **Enable-CsTopology** ist nicht erfolgreich, die Verschiebung schlägt fehl und Ihrer Topologie kann in einem Zustand belassen, in denen keine zentralen Verwaltungsspeicher vorhanden ist. 
  
4. Geben Sie auf der Skype für Business Server 2019 Front-End-Server oder Front-End-Pool, in der Skype für Business Server-Verwaltungsshell: 
    
   ```
   Move-CsManagementServer
   ```

5. Skype für Business Server-Verwaltungsshell zeigt den Servern, Dateispeicher, Datenbankspeicher und die Dienstverbindungspunkte aktueller Status und den Zustand vorgeschlagen. Lesen Sie die Informationen sorgfältig, und bestätigen Sie, dass dies die vorgesehene Quell-als auch ist. Geben Sie **Y** , um den Vorgang fortzusetzen oder **N** , um die Verschiebung zu beenden. 
    
6. Überprüfen Sie etwaige Warnungen oder Fehler, die durch den Befehl **Move-CsManagementServer** generiert, und beheben Sie diese. 
    
7. Öffnen Sie auf der Skype für Business Server 2019 Server der Skype für Business Server-Bereitstellungs-Assistenten aus. 
    
8. In Skype für Business Server-Bereitstellungs-Assistenten, klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**, klicken Sie auf **Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten**, klicken Sie auf **Weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf Fertig stellen ** **. 
    
9. Installieren Sie Server auf der Vorgängerversion, und öffnen Sie den Bereitstellungs-Assistenten. 
    
10. In Skype für Business Server-Bereitstellungs-Assistenten, klicken Sie auf **installieren oder aktualisieren Skype für Business Server-System**, klicken Sie auf **Schritt2: Einrichten oder Entfernen von Skype für Business Server-Komponenten**, klicken Sie auf **Weiter**, überprüfen Sie die Zusammenfassung, und klicken Sie dann auf Fertig stellen ** **. 
    
11. Starten Sie die Skype für Business Server 2019 Server neu. Dies ist aufgrund einer Änderung der Gruppenmitgliedschaft Zugriff auf zentraler Verwaltungsserver Datenbank erforderlich.
    
12. Geben Sie Folgendes ein, um zu bestätigen, dass die Replikation mit dem neuen zentralen Management Store in der Skype für Business Server-Verwaltungsshell ausgeführt wird: 
    
    ```
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Die Replikation dauert etwas Zeit, um alle aktuellen Replikate aktualisiert. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>So entfernen Sie legacy installieren zentralen Speicherdateien nach dem Verschieben

1. Klicken Sie auf der Vorgängerversion installieren Sie Server, melden Sie sich an dem Computer, auf dem die Skype für Business Server-Verwaltungsshell als Mitglied der Gruppe **RTCUniversalServerAdmins** installiert ist. Sie müssen auch die SQL Server-Datenbank Benutzer Administratorrechte und-Berechtigungen verfügen. 
    
2. Öffnen von Skype für Business Server-Verwaltungsshell
    
    > [!CAUTION]
    > Fahren Sie mit dem Entfernen der vorherigen Datenbankdateien, bis die Replikation abgeschlossen ist und stabil ist. Wenn Sie die Dateien vor dem Abschluss der Replikation entfernen, Sie Unterbrechen des Replikationsprozesses und lassen Sie den zentralen Verwaltungsserver neu verschobene in einem unbekannten Zustand. Verwenden Sie das **Get-CsManagementStoreReplicationStatus** -Cmdlet, um den Replikationsstatus zu bestätigen. 
  
3. Um die Datenbankdateien des zentralen Speicher aus der Vorversion Installation zentralen Verwaltungsserver zu entfernen, geben Sie Folgendes ein:
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Beispiel:
    
   ```
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    In dem die _ \<FQDN von SQL Server\> _ ist entweder der Vorgängerversion Back-End-Server in einer Enterprise Edition-Bereitstellung oder der FQDN des Standard Edition-Server installieren. 
    

