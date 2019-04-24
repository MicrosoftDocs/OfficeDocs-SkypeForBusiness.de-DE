---
title: Entfernen der SQL Server-Datenbank für einen Front-End-Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Front-End-Pool entfernen oder neu konfigurieren, den Pool aus, um eine andere Datenbank verwenden, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet. Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.
ms.openlocfilehash: 4ba60a905d5f4cda56cf5277e1be2db80d906ca0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231444"
---
# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="e3d3e-104">Entfernen der SQL Server-Datenbank für einen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="e3d3e-104">Remove the SQL Server database for a Front End pool</span></span>

<span data-ttu-id="e3d3e-105">Nachdem Sie einen Front-End-Pool entfernen oder neu konfigurieren, den Pool aus, um eine andere Datenbank verwenden, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet.</span><span class="sxs-lookup"><span data-stu-id="e3d3e-105">After you remove a Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="e3d3e-106">Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.</span><span class="sxs-lookup"><span data-stu-id="e3d3e-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="e3d3e-107">Entfernen die SQL Server-Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="e3d3e-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="e3d3e-108">Öffnen Sie den Topologie-Generator die Skype für Business Server 2019 Front-End-Server und Laden Sie die vorhandene Topologie.</span><span class="sxs-lookup"><span data-stu-id="e3d3e-108">From the Skype for Business Server 2019 Front End Server, open Topology Builder and download the existing topology.</span></span> 
    
2. <span data-ttu-id="e3d3e-109">Navigieren Sie im Topologie-Generator zu **Freigegebene Komponenten** und klicken Sie dann auf **SQL Server-Speicher**, mit der rechten Maustaste in der SQL Server-Instanz, die dem entfernten oder neukonfigurierten Front-End-Pool zugeordnet, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="e3d3e-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="e3d3e-110">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="e3d3e-110">Publish the topology, and then check the replication status.</span></span> 
    
## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="e3d3e-111">So entfernen Benutzer- und Anwendungsdatenbanken vom SQLServer</span><span class="sxs-lookup"><span data-stu-id="e3d3e-111">To remove user and application databases from the SQL server</span></span>

1. <span data-ttu-id="e3d3e-112">Zum Entfernen der Datenbanken auf dem SQLServer müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQLServer sein, von dem die Datenbankdateien entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="e3d3e-112">To remove the databases on the SQL server, you must be a member of the SQL Server sysadmins group for the SQL server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="e3d3e-113">Öffnen Sie Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="e3d3e-113">Open Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="e3d3e-114">Um die Datenbank für den poolbenutzerspeicher zu entfernen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e3d3e-114">To remove the database for the pool user store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="e3d3e-115">Wobei _ \<FQDN\> _ wird der vollqualifizierten Domänennamen (FQDN) des Datenbankservers, und _ \<Instanz\> _ wird die benannte Datenbankinstanz (sofern eine definiert wurde).</span><span class="sxs-lookup"><span data-stu-id="e3d3e-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="e3d3e-116">Um die Datenbank für den poolanwendungsspeicher zu entfernen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e3d3e-116">To remove the database for the pool application store, type:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="e3d3e-117">Wobei _ \<FQDN\> _ ist der FQDN des Datenbankservers und _ \<Instanz\> _ wird die benannte Datenbankinstanz (sofern eine definiert wurde).</span><span class="sxs-lookup"><span data-stu-id="e3d3e-117">Where  _\<FQDN\>_ is the FQDN of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
5. <span data-ttu-id="e3d3e-118">Wenn das Cmdlet **Uninstall-CsDataBase** aufgefordert werden, bestätigen Sie Aktionen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken N und dann die EINGABETASTE, wenn Sie das Cmdlet (falls Fehler aufgetreten sind) beenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e3d3e-118">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

