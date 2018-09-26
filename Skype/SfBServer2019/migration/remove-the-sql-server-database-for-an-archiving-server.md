---
title: Entfernen der SQL Server-Datenbank eines Archivierungsservers
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Nachdem Sie einen Archivierungsserver entfernen möchten, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet. Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.
ms.openlocfilehash: c82f718cf86de653f6c1340d38e21e96cbaa150d
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027963"
---
# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="8ea42-104">Entfernen der SQL Server-Datenbank eines Archivierungsservers</span><span class="sxs-lookup"><span data-stu-id="8ea42-104">Remove the SQL Server database for an Archiving server</span></span>

<span data-ttu-id="8ea42-105">Nachdem Sie einen Archivierungsserver entfernen möchten, können Sie die SQL Server-Datenbanken entfernen, die die Daten Pool gehostet.</span><span class="sxs-lookup"><span data-stu-id="8ea42-105">After you remove an Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="8ea42-106">Gehen Sie folgendermaßen vor, um die Definitionen Topologie-Generator zu entfernen, und entfernen Sie die Datenbank- und Protokolldateien Dateien vom Datenbankserver.</span><span class="sxs-lookup"><span data-stu-id="8ea42-106">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>
  
## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="8ea42-107">Entfernen die SQL Server-Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="8ea42-107">To remove the SQL Server database using Topology Builder</span></span>

1. <span data-ttu-id="8ea42-108">Öffnen Sie auf der Skype für Business Server 2019 Front-End-Server Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="8ea42-108">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="8ea42-109">Navigieren Sie im Topologie-Generator zu **Freigegebene Komponenten** und klicken Sie dann auf **SQL Server-Speicher**, mit der rechten Maustaste in der SQL Server-Instanz verknüpft ist, zu dem entfernten oder neu konfiguriert Archivierungsserver, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="8ea42-109">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>
    
3. <span data-ttu-id="8ea42-110">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="8ea42-110">Publish the topology, and then check replication status.</span></span> 
    
## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="8ea42-111">Entfernen Sie die Datenbankdateien vom SQL Server</span><span class="sxs-lookup"><span data-stu-id="8ea42-111">To remove the database files from the SQL Server</span></span>

1. <span data-ttu-id="8ea42-112">Zum Entfernen der Datenbanken auf dem SQL Server müssen Sie Mitglied der Gruppe der SQL Server-Sysadmins für den SQL Server sein, von dem die Datenbankdateien entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8ea42-112">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span> 
    
2. <span data-ttu-id="8ea42-113">Öffnen Sie die Skype für Business Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="8ea42-113">Open the Skype for Business Server Management Shell.</span></span>
    
3. <span data-ttu-id="8ea42-114">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="8ea42-114">At the command line, type the following:</span></span>
    
  ```
  Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
  ```

    <span data-ttu-id="8ea42-115">Wobei _ \<FQDN\> _ wird der vollqualifizierten Domänennamen (FQDN) des Datenbankservers, und _ \<Instanz\> _ wird die benannte Datenbankinstanz (sofern eine definiert wurde).</span><span class="sxs-lookup"><span data-stu-id="8ea42-115">Where  _\<FQDN\>_ is the fully qualified domain name (FQDN) of the database server, and  _\<instance\>_ is the named database instance (that is, if one was defined).</span></span> 
    
4. <span data-ttu-id="8ea42-116">Wenn das Cmdlet **Uninstall-CsDataBase** aufgefordert werden, bestätigen Sie Aktionen, lesen Sie die Informationen, und drücken Sie dann Y (oder EINGABETASTE), um fortzufahren, oder drücken N und dann die EINGABETASTE, wenn Sie das Cmdlet (falls Fehler aufgetreten sind) beenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8ea42-116">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press Y (or Enter) to proceed, or press N and then Enter if you want to stop the cmdlet (if there are errors).</span></span> 
    

