---
title: Entfernen der SQL Server-Datenbank für einen Front-End-Pool
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
description: Nachdem Sie einen Front-End-Pool entfernt oder den Pool für die Verwendung einer anderen Datenbank neu konfiguriert haben, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen, und entfernen Sie dann die Datenbank und Protokolldateien vom Datenbankserver.
ms.openlocfilehash: 01a28beabb85aa7cda25043680537f519872d58654dee5418f03ae9f5f702a19
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340321"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Entfernen der SQL Server-Datenbank für einen Front-End-Pool

Nachdem Sie einen Front-End-Pool entfernt oder den Pool für die Verwendung einer anderen Datenbank neu konfiguriert haben, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen, und entfernen Sie dann die Datenbank und Protokolldateien vom Datenbankserver.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 den Topologie-Generator, und laden Sie die vorhandene Topologie herunter. 
    
2. Navigieren Sie im Topologie-Generator zu **"Freigegebene Komponenten",** und klicken Sie dann **SQL Server Speicher,** klicken Sie mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Front-End-Pool zugeordnet ist, und klicken Sie dann auf **"Löschen".**
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>So entfernen Sie Benutzer- und Anwendungsdatenbanken vom SQL Server

1. Um die Datenbanken auf dem SQL Server zu entfernen, müssen Sie Mitglied der Gruppe SQL Server Sysadmins für den SQL Server sein, auf dem Sie die Datenbankdateien entfernen. 
    
2. Öffnen Sie Skype for Business Server Verwaltungsshell.
    
3. Geben Sie Folgendes ein, um die Datenbank für den Poolbenutzerspeicher zu entfernen:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Gibt an, wo  _\<FQDN\>_ sich der vollqualifizierte Domänenname (FQDN) des Datenbankservers und  _\<instance\>_ die benannte Datenbankinstanz befindet (d. a. wenn eine definiert wurde). 
    
4. Geben Sie Folgendes ein, um die Datenbank für den Poolanwendungsspeicher zu entfernen:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Wo  _\<FQDN\>_ befindet sich der FQDN des Datenbankservers und ist die benannte  _\<instance\>_ Datenbankinstanz (d. a. wenn eine definiert wurde). 
    
5. Wenn Sie vom Cmdlet **Uninstall-CsDataBase** aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken Sie N und geben Sie dann ein, wenn Sie das Cmdlet beenden möchten (wenn Fehler auftreten). 
    

