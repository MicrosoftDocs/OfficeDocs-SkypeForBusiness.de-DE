---
title: Entfernen der SQL Server-Datenbank für einen Monitoring server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Monitoring Server entfernt haben, können Sie die SQL Server-Datenbanken entfernen, die die Server-Daten gehostet. Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.
ms.openlocfilehash: 1dc18d520afd67156443ddc2fc22dc838a2aa139
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027977"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="c0595-104">Entfernen der SQL Server-Datenbank für einen Monitoring server</span><span class="sxs-lookup"><span data-stu-id="c0595-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="c0595-105">Nachdem Sie einen Monitoring Server entfernt haben, können Sie die SQL Server-Datenbanken entfernen, die die Server-Daten gehostet.</span><span class="sxs-lookup"><span data-stu-id="c0595-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="c0595-106">Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.</span><span class="sxs-lookup"><span data-stu-id="c0595-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="c0595-107">Entfernen die SQL Server-Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="c0595-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="c0595-108">Öffnen Sie auf der Skype für Business Server 2019 Front-End-Server Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="c0595-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="c0595-109">Navigieren Sie im Topologie-Generator zu **Freigegebene Komponenten** und klicken Sie dann auf **SQL Server-Speicher**, mit der rechten Maustaste in der SQL Server-Instanz verknüpft ist, zu dem entfernten oder neu konfiguriert Monitoring Server, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="c0595-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="c0595-110">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="c0595-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="c0595-111">Entfernen Sie die Datenbankdateien vom SQL Server</span><span class="sxs-lookup"><span data-stu-id="c0595-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="c0595-112">Zum Entfernen der Datenbanken auf dem SQL Server-basierten Server müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server sein, von dem die Datenbankdateien entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c0595-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="c0595-113">Öffnen Sie die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="c0595-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="c0595-114">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c0595-114">At the command line, type the following:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="c0595-115">Wobei _ \<FQDN\> _ wird der vollqualifizierten Domänennamen (FQDN) des Datenbankservers, und _ \<Instanz\> _ ist die optionale benannte Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="c0595-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="c0595-116">Wenn das Cmdlet **Uninstall-CsDataBase** aufgefordert werden, bestätigen Sie Aktionen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken N und dann die EINGABETASTE, wenn Sie das Cmdlet (falls Fehler aufgetreten sind) beenden möchten.</span><span class="sxs-lookup"><span data-stu-id="c0595-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

