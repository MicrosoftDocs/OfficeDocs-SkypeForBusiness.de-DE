---
title: Entfernen der SQL Server-Datenbank für einen Monitoring Server
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
description: Nachdem Sie eine Monitoring Server entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Server Daten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
ms.openlocfilehash: 829e55175c9b9c85582aafe996bbbee0afdffa62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753327"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Entfernen der SQL Server-Datenbank für einen Monitoring Server

Nachdem Sie eine Monitoring Server entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Server Daten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie im Skype for Business Server 2019 Front-End-Server den Topologie-Generator.
    
2. Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** , klicken Sie dann **SQL Server speichern**mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Monitoring Server zugeordnet ist, und klicken Sie dann auf **Löschen**.
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>So entfernen Sie die Datenbankdateien vom SQL Server-basierten Server

1. Zum Entfernen der Datenbanken auf dem SQL Server basierten Server müssen Sie Mitglied der Gruppe "SQL Server Sysadmins" für den SQL Server Server sein, auf dem Sie die Datenbankdateien entfernen.
    
2. Öffnen Sie die Skype for Business Server Management-Shell.
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dabei _\<FQDN\>_ ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Datenbankservers und _\<instance\>_ die optionale benannte Datenbankinstanz. 
    
4. Wenn Sie vom Cmdlet " **Uninstall-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann j (oder Enter), um den Vorgang fortzusetzen, oder drücken Sie N und dann die EINGABETASTE, wenn das Cmdlet beendet werden soll (falls Fehler vorliegen). 
    

