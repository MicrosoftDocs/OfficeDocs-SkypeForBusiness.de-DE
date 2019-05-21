---
title: Entfernen der SQL Server-Datenbank für einen Monitoring Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Überwachungs Server entfernt haben, können Sie die SQL Server-Datenbanken entfernen, die die Server Daten gehostet haben. Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.
ms.openlocfilehash: 2f4a6feb78adb9daa15cb8d59c2041740e45a19d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301083"
---
# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="89e76-104">Entfernen der SQL Server-Datenbank für einen Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="89e76-104">Remove the SQL Server database for a Monitoring server</span></span>

<span data-ttu-id="89e76-105">Nachdem Sie einen Überwachungs Server entfernt haben, können Sie die SQL Server-Datenbanken entfernen, die die Server Daten gehostet haben.</span><span class="sxs-lookup"><span data-stu-id="89e76-105">After you remove a Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="89e76-106">Gehen Sie wie folgt vor, um die Definitionen aus dem Topology Builder zu entfernen und dann die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="89e76-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="89e76-107">So entfernen Sie die SQL Server-Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="89e76-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="89e76-108">Öffnen Sie auf dem Skype for Business Server 2019-Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="89e76-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="89e76-109">Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** und dann zu **SQL Server-speichern**, klicken Sie mit der rechten Maustaste auf die SQL Server-Instanz, die dem entfernten oder neu konfigurierten Überwachungs Server zugeordnet ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="89e76-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="89e76-110">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="89e76-110">Publish the topology, and then check replication status.</span></span>
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="89e76-111">So entfernen Sie die Datenbankdateien aus dem SQL Server</span><span class="sxs-lookup"><span data-stu-id="89e76-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="89e76-112">Um die Datenbanken auf dem SQL Server-basierten Server zu entfernen, müssen Sie ein Mitglied der Gruppe SQL Server-Sysadmins für den SQL Server-Server sein, auf dem Sie die Datenbankdateien entfernen.</span><span class="sxs-lookup"><span data-stu-id="89e76-112">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>
    
2. <span data-ttu-id="89e76-113">Öffnen Sie die Skype for Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="89e76-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="89e76-114">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="89e76-114">At the command line, type the following:</span></span>
    
   ```
   Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
   ```

    <span data-ttu-id="89e76-115">Hierbei handelt es sich um den vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Datenbankservers, und _ \<Instanz\> _ ist die optionale benannte Datenbankinstanz. _ \<\> _</span><span class="sxs-lookup"><span data-stu-id="89e76-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the optional named database instance.</span></span> 
    
4. <span data-ttu-id="89e76-116">Wenn Sie vom Cmdlet " **deinstallieren-CsDataBase** " aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken Sie N, und geben Sie dann ein, wenn das Cmdlet beendet werden soll (wenn Fehler auftreten).</span><span class="sxs-lookup"><span data-stu-id="89e76-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

