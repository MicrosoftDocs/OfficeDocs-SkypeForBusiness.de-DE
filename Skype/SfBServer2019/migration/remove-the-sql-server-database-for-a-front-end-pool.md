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
description: Nachdem Sie einen Front-End-Pool entfernt oder den Pool neu konfiguriert haben, um eine andere Datenbank zu verwenden, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
ms.openlocfilehash: 9047486708b92c07e6ec099fce43ec4c708fa900
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753407"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Entfernen der SQL Server-Datenbank für einen Front-End-Pool

Nachdem Sie einen Front-End-Pool entfernt oder den Pool neu konfiguriert haben, um eine andere Datenbank zu verwenden, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie im Skype for Business Server 2019 Front-End-Server den Topologie-Generator, und laden Sie die vorhandene Topologie herunter. 
    
2. Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** , klicken Sie dann **SQL Server speichern**mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Front-End-Pool zugeordnet ist, und klicken Sie dann auf **Löschen**.
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>So entfernen Sie Benutzer-und Anwendungsdatenbanken von SQL Server

1. Zum Entfernen der Datenbanken auf dem SQL-Server müssen Sie Mitglied der Gruppe "SQL Server Sysadmins" für den SQL Server sein, auf dem Sie die Datenbankdateien entfernen. 
    
2. Öffnen Sie Skype for Business Server Management Shell.
    
3. Geben Sie Folgendes ein, um die Datenbank für den Poolbenutzerspeicher zu entfernen:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dabei _\<FQDN\>_ ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Datenbankservers und _\<instance\>_ die benannte Datenbankinstanz (sofern eine definiert wurde). 
    
4. Geben Sie Folgendes ein, um die Datenbank für den Poolanwendungsspeicher zu entfernen:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dabei _\<FQDN\>_ ist der FQDN des Datenbankservers und _\<instance\>_ die benannte Datenbankinstanz (sofern eine definiert wurde). 
    
5. Wenn Sie vom Cmdlet " **Uninstall-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann j (oder Enter), um den Vorgang fortzusetzen, oder drücken Sie N und dann die EINGABETASTE, wenn das Cmdlet beendet werden soll (falls Fehler vorliegen). 
    

