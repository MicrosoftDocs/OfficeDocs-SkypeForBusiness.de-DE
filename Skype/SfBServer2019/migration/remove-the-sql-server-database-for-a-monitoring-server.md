---
title: Entfernen der SQL Server-Datenbank für einen Überwachungsserver
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
description: Nachdem Sie einen Monitoring Server entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Serverdaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen, und entfernen Sie dann die Datenbank und Protokolldateien vom Datenbankserver.
ms.openlocfilehash: cadb24e2dcbe88e643c234dd8559d07406e5566e3e7eea0e33eec796cd98cf52
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280390"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Entfernen der SQL Server-Datenbank für einen Überwachungsserver

Nachdem Sie einen Monitoring Server entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Serverdaten gehostet haben. Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen, und entfernen Sie dann die Datenbank und Protokolldateien vom Datenbankserver.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie auf dem Front-End-Server Skype for Business Server 2019 den Topologie-Generator.
    
2. Navigieren Sie im Topologie-Generator zu **"Freigegebene Komponenten",** und klicken Sie dann **SQL Server Speicher,** klicken Sie mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Monitoring Server zugeordnet ist, und klicken Sie dann auf **"Löschen".**
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>So entfernen Sie die Datenbankdateien vom SQL Server-basierten Server

1. Um die Datenbanken auf dem SQL Server-basierten Server zu entfernen, müssen Sie Mitglied der Gruppe SQL Server Sysadmins für den SQL Server Server sein, auf dem Sie die Datenbankdateien entfernen.
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Gibt an, wo  _\<FQDN\>_ sich der vollqualifizierte Domänenname (FQDN) des Datenbankservers und  _\<instance\>_ die optionale benannte Datenbankinstanz befindet. 
    
4. Wenn Sie vom Cmdlet **Uninstall-CsDataBase** aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken Sie N und geben Sie dann ein, wenn Sie das Cmdlet beenden möchten (wenn Fehler auftreten). 
    

