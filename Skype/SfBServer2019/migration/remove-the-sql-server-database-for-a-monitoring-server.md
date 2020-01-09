---
title: Entfernen der SQL Server-Datenbank für einen Monitoring Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Überwachungs Server entfernt haben, können Sie die SQL Server-Datenbanken entfernen, die die Server Daten gehostet haben. Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
ms.openlocfilehash: 94081aa7ec4b32797dedaaa2a89dc7221b04bd97
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989010"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Entfernen der SQL Server-Datenbank für einen Monitoring Server

Nachdem Sie einen Überwachungs Server entfernt haben, können Sie die SQL Server-Datenbanken entfernen, die die Server Daten gehostet haben. Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server den Topologie-Generator.
    
2. Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** und dann zu **SQL Server-speichern**, klicken Sie mit der rechten Maustaste auf die SQL Server-Instanz, die dem entfernten oder neu konfigurierten Überwachungs Server zugeordnet ist, und klicken Sie dann auf **Löschen**.
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a>So entfernen Sie die Datenbankdateien aus dem SQL Server

1. Um die Datenbanken auf dem SQL Server-basierten Server zu entfernen, müssen Sie ein Mitglied der Gruppe SQL Server-Sysadmins für den SQL Server-Server sein, auf dem Sie die Datenbankdateien entfernen.
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
3. Geben Sie an der Befehlszeile Folgendes ein:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    _ \<\> _ _ \<Hierbei handelt es sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Datenbankservers, und Instanz\> _ ist die optionale benannte Datenbankinstanz. 
    
4. Wenn Sie vom Cmdlet " **deinstallieren-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken Sie N, und geben Sie dann ein, wenn das Cmdlet beendet werden soll (wenn Fehler auftreten). 
    

