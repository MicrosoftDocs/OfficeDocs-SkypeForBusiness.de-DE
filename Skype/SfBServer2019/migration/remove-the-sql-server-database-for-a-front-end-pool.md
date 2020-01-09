---
title: Entfernen der SQL Server-Datenbank für einen Front-End-Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Front-End-Pool entfernt oder den Pool neu konfiguriert haben, um eine andere Datenbank zu verwenden, können Sie die SQL Server-Datenbanken entfernen, die die Pooldaten gehostet haben. Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
ms.openlocfilehash: f26cf1f93abb8538c068a4ab2d6f81c9c36d759d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989090"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Entfernen der SQL Server-Datenbank für einen Front-End-Pool

Nachdem Sie einen Front-End-Pool entfernt oder den Pool neu konfiguriert haben, um eine andere Datenbank zu verwenden, können Sie die SQL Server-Datenbanken entfernen, die die Pooldaten gehostet haben. Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators

1. Öffnen Sie im Skype for Business Server 2019-Front-End-Server den Topologie-Generator, und laden Sie die vorhandene Topologie herunter. 
    
2. Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** und dann zu **SQL Server-speichern**, klicken Sie mit der rechten Maustaste auf die SQL Server-Instanz, die dem entfernten oder neu konfigurierten Front-End-Pool zugeordnet ist, und klicken Sie dann auf **Löschen**.
    
3. Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus. 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>So entfernen Sie Benutzer-und Anwendungsdatenbanken aus dem SQL Server

1. Um die Datenbanken auf dem SQL Server zu entfernen, müssen Sie ein Mitglied der Gruppe SQL Server Sysadmins für den SQL Server sein, auf dem Sie die Datenbankdateien entfernen. 
    
2. Öffnen Sie die Skype for Business Server-Verwaltungsshell.
    
3. Wenn Sie die Datenbank für den Pool Benutzerspeicher entfernen möchten, geben Sie Folgendes ein:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Hierbei handelt es _ \<sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Datenbankservers, wobei es sich bei der Instanz um die benannte Datenbankinstanz handelt (also, wenn eine definiert wurde).\> _ _ \<\> _ 
    
4. Wenn Sie die Datenbank für den Pool-Anwendungsspeicher entfernen möchten, geben Sie Folgendes ein:
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    Dabei _ \<ist\> FQDN_ der FQDN des Datenbankservers, und _ \<Instanz\> _ ist die benannte Datenbankinstanz (also, wenn eine definiert wurde). 
    
5. Wenn Sie vom Cmdlet " **deinstallieren-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken Sie N, und geben Sie dann ein, wenn das Cmdlet beendet werden soll (wenn Fehler auftreten). 
    

