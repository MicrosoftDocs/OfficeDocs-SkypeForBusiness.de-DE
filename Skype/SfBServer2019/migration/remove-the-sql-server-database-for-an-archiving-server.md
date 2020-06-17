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
description: Nachdem Sie eine Archivierungsserver entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
ms.openlocfilehash: f8a08b7ea73fa954726bdef986e5a28919c90ceb
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753307"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Entfernen der SQL Server-Datenbank für einen Archivierungsserver

Nachdem Sie eine Archivierungsserver entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie im Skype for Business Server 2019 Front-End-Server den Topologie-Generator.
    
2. Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** , klicken Sie dann **SQL Server speichern**mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Löschen**.
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus. 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>So entfernen Sie die Datenbankdateien vom SQL Server-basierten Server

1. Zum Entfernen der Datenbanken vom SQL Server-basierten Server müssen Sie Mitglied der SQL Server-Gruppe sysadmins für den SQL Server-basierten Server sein, von dem die Datenbankdateien entfernt werden. 
    
2. Öffnen Sie die Skype for Business Server Management-Shell.
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dabei _\<FQDN\>_ ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Datenbankservers und _\<instance\>_ die benannte Datenbankinstanz (sofern eine definiert wurde). 
    
4. Wenn Sie vom Cmdlet " **Uninstall-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann j (oder Enter), um den Vorgang fortzusetzen, oder drücken Sie N und dann die EINGABETASTE, wenn das Cmdlet beendet werden soll (falls Fehler vorliegen). 
    

