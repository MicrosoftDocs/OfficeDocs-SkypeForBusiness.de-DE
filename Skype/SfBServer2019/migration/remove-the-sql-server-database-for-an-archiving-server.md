---
title: Entfernen der SQL Server-Datenbank für einen Archivierungsserver
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Archivierungsserver entfernen möchten, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet. Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.
ms.openlocfilehash: acb402dd6cb28be5b607b8a358524dfc0c1fea69
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875440"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="384a7-104">Entfernen der SQL Server-Datenbank für einen Archivierungsserver</span><span class="sxs-lookup"><span data-stu-id="384a7-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="384a7-105">Nachdem Sie einen Archivierungsserver entfernen möchten, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet.</span><span class="sxs-lookup"><span data-stu-id="384a7-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="384a7-106">Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.</span><span class="sxs-lookup"><span data-stu-id="384a7-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="384a7-107">Entfernen die SQL Server-Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="384a7-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="384a7-108">Öffnen Sie auf der Skype für Business Server 2019 Front-End-Server Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="384a7-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="384a7-109">Navigieren Sie im Topologie-Generator zu **Freigegebene Komponenten** und klicken Sie dann auf **SQL Server-Speicher**, mit der rechten Maustaste in der SQL Server-Instanz verknüpft ist, zu dem entfernten oder neu konfiguriert Archivierungsserver, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="384a7-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="384a7-110">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="384a7-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="384a7-111">Entfernen Sie die Datenbankdateien vom SQL Server</span><span class="sxs-lookup"><span data-stu-id="384a7-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="384a7-112">Zum Entfernen der Datenbanken auf dem SQL Server müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server sein, von dem die Datenbankdateien entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="384a7-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="384a7-113">Öffnen Sie die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="384a7-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="384a7-114">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="384a7-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="384a7-115">Wobei _ \<FQDN\> _ wird der vollqualifizierten Domänennamen (FQDN) des Datenbankservers, und _ \<Instanz\> _ wird die benannte Datenbankinstanz (sofern eine definiert wurde).</span><span class="sxs-lookup"><span data-stu-id="384a7-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="384a7-116">Wenn das Cmdlet **Uninstall-CsDataBase** aufgefordert werden, bestätigen Sie Aktionen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken N und dann die EINGABETASTE, wenn Sie das Cmdlet (falls Fehler aufgetreten sind) beenden möchten.</span><span class="sxs-lookup"><span data-stu-id="384a7-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

