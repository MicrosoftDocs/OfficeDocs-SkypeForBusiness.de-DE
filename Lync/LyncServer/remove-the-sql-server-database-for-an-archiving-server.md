---
title: Entfernen der SQL Server Datenbank für einen Archivierungs Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1891e9a0ab61a64f74e877722689ce1e4d25231
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a><span data-ttu-id="9ff65-102">Entfernen der SQL Server Datenbank für einen Archivierungs Server</span><span class="sxs-lookup"><span data-stu-id="9ff65-102">Remove the SQL Server database for an Archiving server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ff65-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="9ff65-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="9ff65-104">Nachdem Sie eine Microsoft lync Server 2010 Archivierungsserver entfernt haben, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben.</span><span class="sxs-lookup"><span data-stu-id="9ff65-104">After you remove a Microsoft Lync Server 2010 Archiving Server, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="9ff65-105">Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="9ff65-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="9ff65-106">So entfernen Sie die SQL Server Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="9ff65-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="9ff65-107">Öffnen Sie im lync Server 2013 Front-End-Server den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="9ff65-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="9ff65-108">Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** , klicken Sie dann **SQL Server speichern**mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Archivierungsserver zugeordnet ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="9ff65-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Archiving Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="9ff65-109">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="9ff65-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="9ff65-110">So entfernen Sie die Datenbankdateien vom SQL Server-basierten Server</span><span class="sxs-lookup"><span data-stu-id="9ff65-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="9ff65-111">Zum Entfernen der Datenbanken vom SQL Server-basierten Server müssen Sie Mitglied der SQL Server-Gruppe sysadmins für den SQL Server-basierten Server sein, von dem die Datenbankdateien entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="9ff65-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="9ff65-112">Öffnen Sie die Lync Server-Verwaltungsshell.</span><span class="sxs-lookup"><span data-stu-id="9ff65-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="9ff65-113">Geben Sie an der Befehlszeile Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="9ff65-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="9ff65-114">Dabei \<ist\> FQDN der vollqualifizierte Domänenname (FQDN) des Datenbankservers, und \<Instanz\> ist die benannte Datenbankinstanz (also, wenn eine definiert wurde).</span><span class="sxs-lookup"><span data-stu-id="9ff65-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="9ff65-115">Wenn Sie vom **Uninstall-CsDataBase**-Cmdlet aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann **J** (oder die EINGABETASTE), oder drücken Sie **N** und dann die EINGABETASTE, wenn Sie die Ausführung des Cmdlets beenden möchten (im Falle von Fehlern).</span><span class="sxs-lookup"><span data-stu-id="9ff65-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

