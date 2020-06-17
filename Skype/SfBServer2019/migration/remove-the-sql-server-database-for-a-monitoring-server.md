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
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="c0cf9-104">Entfernen der SQL Server-Datenbank für einen Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="c0cf9-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="c0cf9-105">Nachdem Sie eine Monitoring Server entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Server Daten gehostet haben.</span><span class="sxs-lookup"><span data-stu-id="c0cf9-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="c0cf9-106">Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c0cf9-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="c0cf9-107">So entfernen Sie die SQL Server Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="c0cf9-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="c0cf9-108">Öffnen Sie im Skype for Business Server 2019 Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="c0cf9-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="c0cf9-109">Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** , klicken Sie dann **SQL Server speichern**mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Monitoring Server zugeordnet ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="c0cf9-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="c0cf9-110">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="c0cf9-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="c0cf9-111">So entfernen Sie die Datenbankdateien vom SQL Server-basierten Server</span><span class="sxs-lookup"><span data-stu-id="c0cf9-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="c0cf9-112">Zum Entfernen der Datenbanken auf dem SQL Server basierten Server müssen Sie Mitglied der Gruppe "SQL Server Sysadmins" für den SQL Server Server sein, auf dem Sie die Datenbankdateien entfernen.</span><span class="sxs-lookup"><span data-stu-id="c0cf9-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="c0cf9-113">Öffnen Sie die Skype for Business Server Management-Shell.</span><span class="sxs-lookup"><span data-stu-id="c0cf9-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="c0cf9-114">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c0cf9-114">At the command line, type the following:</span></span>
    
   ```PowerShell
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="c0cf9-115">Dabei _\<FQDN\>_ ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Datenbankservers und _\<instance\>_ die optionale benannte Datenbankinstanz.</span><span class="sxs-lookup"><span data-stu-id="c0cf9-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="c0cf9-116">Wenn Sie vom Cmdlet " **Uninstall-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann j (oder Enter), um den Vorgang fortzusetzen, oder drücken Sie N und dann die EINGABETASTE, wenn das Cmdlet beendet werden soll (falls Fehler vorliegen).</span><span class="sxs-lookup"><span data-stu-id="c0cf9-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

