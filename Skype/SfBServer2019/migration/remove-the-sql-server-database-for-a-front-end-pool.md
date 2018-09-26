---
title: Entfernen der SQL Server-Datenbank für einen Front-End-pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Front-End-Pool entfernen oder neu konfigurieren, den Pool aus, um eine andere Datenbank verwenden, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet. Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.
ms.openlocfilehash: 65fd0367051e32aa081fa13859632504e1331669
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028607"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Entfernen der SQL Server-Datenbank für einen Front-End-pool

Nachdem Sie einen Front-End-Pool entfernen oder neu konfigurieren, den Pool aus, um eine andere Datenbank verwenden, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet. Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Entfernen die SQL Server-Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie den Topologie-Generator die Skype für Business Server 2019 Front-End-Server und Laden Sie die vorhandene Topologie. 
    
2. Navigieren Sie im Topologie-Generator zu **Freigegebene Komponenten** und klicken Sie dann auf **SQL Server-Speicher**, mit der rechten Maustaste in der SQL Server-Instanz, die dem entfernten oder neukonfigurierten Front-End-Pool zugeordnet, und klicken Sie dann auf **Löschen**.
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>So entfernen Benutzer- und Anwendungsdatenbanken vom SQLServer

1. Zum Entfernen der Datenbanken auf dem SQLServer müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQLServer sein, von dem die Datenbankdateien entfernt werden. 
    
2. Öffnen Sie Skype für Business Server-Verwaltungsshell.
    
3. Um die Datenbank für den poolbenutzerspeicher zu entfernen, geben Sie Folgendes ein:
    
  ```
  Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    Wobei _ \<FQDN\> _ wird der vollqualifizierten Domänennamen (FQDN) des Datenbankservers, und _ \<Instanz\> _ wird die benannte Datenbankinstanz (sofern eine definiert wurde). 
    
4. Um die Datenbank für den poolanwendungsspeicher zu entfernen, geben Sie Folgendes ein:
    
  ```
  Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    Wobei _ \<FQDN\> _ ist der FQDN des Datenbankservers und _ \<Instanz\> _ wird die benannte Datenbankinstanz (sofern eine definiert wurde). 
    
5. Wenn das Cmdlet **Uninstall-CsDataBase** aufgefordert werden, bestätigen Sie Aktionen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken N und dann die EINGABETASTE, wenn Sie das Cmdlet (falls Fehler aufgetreten sind) beenden möchten. 
    

