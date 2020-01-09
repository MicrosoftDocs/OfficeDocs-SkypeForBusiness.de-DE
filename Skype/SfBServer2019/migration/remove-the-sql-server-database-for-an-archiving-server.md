---
title: Entfernen der SQL Server-Datenbank für einen Archivierungsserver
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Archivierungs Server entfernt haben, können Sie die SQL Server-Datenbanken entfernen, die die Pooldaten gehostet haben. Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
ms.openlocfilehash: 149342f49fded4af294f76028140a9f76f190ed1
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989000"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="44952-104">Entfernen der SQL Server-Datenbank für einen Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="44952-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="44952-105">Nachdem Sie einen Archivierungs Server entfernt haben, können Sie die SQL Server-Datenbanken entfernen, die die Pooldaten gehostet haben.</span><span class="sxs-lookup"><span data-stu-id="44952-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="44952-106">Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="44952-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="44952-107">So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="44952-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="44952-108">Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="44952-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="44952-109">Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** und dann zu **SQL Server-speichern**, klicken Sie mit der rechten Maustaste auf die SQL Server-Instanz, die dem entfernten oder neu konfigurierten Archivierungs Server zugeordnet ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="44952-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="44952-110">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="44952-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="44952-111">So entfernen Sie die Datenbankdateien aus dem SQL Server</span><span class="sxs-lookup"><span data-stu-id="44952-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="44952-112">Um die Datenbanken auf dem SQL Server zu entfernen, müssen Sie ein Mitglied der Gruppe SQL Server Sysadmins für den SQL Server sein, auf dem Sie die Datenbankdateien entfernen.</span><span class="sxs-lookup"><span data-stu-id="44952-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="44952-113">Öffnen Sie die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="44952-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="44952-114">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="44952-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="44952-115">Hierbei handelt es _ \<sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Datenbankservers, wobei es sich bei der Instanz um die benannte Datenbankinstanz handelt (also, wenn eine definiert wurde).\> _ _ \<\> _</span><span class="sxs-lookup"><span data-stu-id="44952-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="44952-116">Wenn Sie vom Cmdlet " **deinstallieren-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken Sie N, und geben Sie dann ein, wenn das Cmdlet beendet werden soll (wenn Fehler auftreten).</span><span class="sxs-lookup"><span data-stu-id="44952-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

