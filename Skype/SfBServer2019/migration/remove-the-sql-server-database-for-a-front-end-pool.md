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
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="600c6-104">Entfernen der SQL Server-Datenbank für einen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="600c6-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="600c6-105">Nachdem Sie einen Front-End-Pool entfernt oder den Pool neu konfiguriert haben, um eine andere Datenbank zu verwenden, können Sie die SQL Server-Datenbanken entfernen, die die Pooldaten gehostet haben.</span><span class="sxs-lookup"><span data-stu-id="600c6-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="600c6-106">Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="600c6-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="600c6-107">So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="600c6-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="600c6-108">Öffnen Sie im Skype for Business Server 2019-Front-End-Server den Topologie-Generator, und laden Sie die vorhandene Topologie herunter.</span><span class="sxs-lookup"><span data-stu-id="600c6-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="600c6-109">Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** und dann zu **SQL Server-speichern**, klicken Sie mit der rechten Maustaste auf die SQL Server-Instanz, die dem entfernten oder neu konfigurierten Front-End-Pool zugeordnet ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="600c6-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="600c6-110">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="600c6-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="600c6-111">So entfernen Sie Benutzer-und Anwendungsdatenbanken aus dem SQL Server</span><span class="sxs-lookup"><span data-stu-id="600c6-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="600c6-112">Um die Datenbanken auf dem SQL Server zu entfernen, müssen Sie ein Mitglied der Gruppe SQL Server Sysadmins für den SQL Server sein, auf dem Sie die Datenbankdateien entfernen.</span><span class="sxs-lookup"><span data-stu-id="600c6-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="600c6-113">Öffnen Sie die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="600c6-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="600c6-114">Wenn Sie die Datenbank für den Pool Benutzerspeicher entfernen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="600c6-114">To remove the database for the pool user store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="600c6-115">Hierbei handelt es _ \<sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Datenbankservers, wobei es sich bei der Instanz um die benannte Datenbankinstanz handelt (also, wenn eine definiert wurde).\> _ _ \<\> _</span><span class="sxs-lookup"><span data-stu-id="600c6-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="600c6-116">Wenn Sie die Datenbank für den Pool-Anwendungsspeicher entfernen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="600c6-116">To remove the database for the pool application store, type:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="600c6-117">Dabei _ \<ist\> FQDN_ der FQDN des Datenbankservers, und _ \<Instanz\> _ ist die benannte Datenbankinstanz (also, wenn eine definiert wurde).</span><span class="sxs-lookup"><span data-stu-id="600c6-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="600c6-118">Wenn Sie vom Cmdlet " **deinstallieren-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken Sie N, und geben Sie dann ein, wenn das Cmdlet beendet werden soll (wenn Fehler auftreten).</span><span class="sxs-lookup"><span data-stu-id="600c6-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

