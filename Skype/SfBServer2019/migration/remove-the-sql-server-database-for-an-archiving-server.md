---
title: Entfernen der SQL Server-Datenbank für einen Archivierungsserver
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Archivierungsserver entfernen möchten, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet. Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.
ms.openlocfilehash: acb402dd6cb28be5b607b8a358524dfc0c1fea69
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875440"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Entfernen der SQL Server-Datenbank für einen Archivierungsserver

Nachdem Sie einen Archivierungsserver entfernen möchten, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet. Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Entfernen die SQL Server-Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie auf der Skype für Business Server 2019 Front-End-Server Topologie-Generator.
    
2. Navigieren Sie im Topologie-Generator zu **Freigegebene Komponenten** und klicken Sie dann auf **SQL Server-Speicher**, mit der rechten Maustaste in der SQL Server-Instanz verknüpft ist, zu dem entfernten oder neu konfiguriert Archivierungsserver, und klicken Sie dann auf **Löschen**.
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>Entfernen Sie die Datenbankdateien vom SQL Server

1. Zum Entfernen der Datenbanken auf dem SQL Server müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server sein, von dem die Datenbankdateien entfernt werden. 
    
2. Öffnen Sie die Skype für Business Server-Verwaltungsshell.
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Wobei _ \<FQDN\> _ wird der vollqualifizierten Domänennamen (FQDN) des Datenbankservers, und _ \<Instanz\> _ wird die benannte Datenbankinstanz (sofern eine definiert wurde). 
    
4. Wenn das Cmdlet **Uninstall-CsDataBase** aufgefordert werden, bestätigen Sie Aktionen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken N und dann die EINGABETASTE, wenn Sie das Cmdlet (falls Fehler aufgetreten sind) beenden möchten. 
    

