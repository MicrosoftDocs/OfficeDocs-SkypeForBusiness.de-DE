---
title: Entfernen der SQL Server-Datenbank für einen Archivierungsserver
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
description: Nachdem Sie einen Archivierungsserver entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen, und entfernen Sie dann die Datenbank und Protokolldateien vom Datenbankserver.
ms.openlocfilehash: 3b0b41944941cd6984dec72c52405a1bce63fd8bff87e14cfd94fc723e262d49
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54279563"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Entfernen der SQL Server-Datenbank für einen Archivierungsserver

Nachdem Sie einen Archivierungsserver entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen, und entfernen Sie dann die Datenbank und Protokolldateien vom Datenbankserver.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 den Topologie-Generator.
    
2. Navigieren Sie im Topologie-Generator zu **"Freigegebene Komponenten",** und klicken Sie dann **SQL Server Speicher,** klicken Sie mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Archivierungsserver zugeordnet ist, und klicken Sie dann auf **"Löschen".**
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>So entfernen Sie die Datenbankdateien vom SQL Server-basierten Server

1. Zum Entfernen der Datenbanken vom SQL Server-basierten Server müssen Sie Mitglied der SQL Server-Gruppe sysadmins für den SQL Server-basierten Server sein, von dem die Datenbankdateien entfernt werden. 
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Gibt an, wo  _\<FQDN\>_ sich der vollqualifizierte Domänenname (FQDN) des Datenbankservers und  _\<instance\>_ die benannte Datenbankinstanz befindet (d. a. wenn eine definiert wurde). 
    
4. Wenn Sie vom Cmdlet **Uninstall-CsDataBase** aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken Sie N und geben Sie dann ein, wenn Sie das Cmdlet beenden möchten (wenn Fehler auftreten). 
    

