---
title: Entfernen der SQL Server-Datenbank für einen Front-End-Pool
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d46868b63236327825f2fe4134330fd055ead2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a><span data-ttu-id="fb540-102">Entfernen der SQL Server-Datenbank für einen Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="fb540-102">Remove the SQL Server database for a Front End pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb540-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="fb540-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="fb540-104">Nachdem Sie ein Microsoft lync Server 2010 entfernt Front-End-Pool oder den Pool neu konfiguriert haben, um eine andere Datenbank zu verwenden, können Sie die SQL Server Datenbanken entfernen, die die Pooldaten gehostet haben.</span><span class="sxs-lookup"><span data-stu-id="fb540-104">After you remove a Microsoft Lync Server 2010 Front End pool or reconfigure the pool to use a different database, you can remove the SQL Server databases that hosted the pool data.</span></span> <span data-ttu-id="fb540-105">Verwenden Sie die folgenden Verfahren, um die Definitionen aus dem Topologie-Generator zu entfernen und anschließend die Datenbank-und Protokolldateien vom Datenbankserver zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fb540-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="fb540-106">So entfernen Sie die SQL Server Datenbank mithilfe des Topologie-Generators</span><span class="sxs-lookup"><span data-stu-id="fb540-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="fb540-107">Öffnen Sie im lync Server 2013 Front-End-Server den Topologie-Generator, und laden Sie die vorhandene Topologie herunter.</span><span class="sxs-lookup"><span data-stu-id="fb540-107">From the Lync Server 2013 Front End Server, open Topology Builder and download the existing topology.</span></span>

2.  <span data-ttu-id="fb540-108">Navigieren Sie im Topologie-Generator zu **freigegebenen Komponenten** , klicken Sie dann **SQL Server speichern**mit der rechten Maustaste auf die SQL Server Instanz, die dem entfernten oder neu konfigurierten Front-End-Pool zugeordnet ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="fb540-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Front End pool, and then click **Delete**.</span></span>

3.  <span data-ttu-id="fb540-109">Veröffentlichen Sie die Topologie, und überprüfen Sie dann den Replikationsstatus.</span><span class="sxs-lookup"><span data-stu-id="fb540-109">Publish the topology, and then check the replication status.</span></span>

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a><span data-ttu-id="fb540-110">So entfernen Sie Benutzer- und Anwendungsdatenbanken aus dem SQL Server-basierten Server</span><span class="sxs-lookup"><span data-stu-id="fb540-110">To remove user and application databases from the SQL Server</span></span>

1.  <span data-ttu-id="fb540-111">Zum Entfernen der Datenbanken vom SQL Server-basierten Server müssen Sie Mitglied der SQL Server-Gruppe sysadmins für den SQL Server-basierten Server sein, von dem die Datenbankdateien entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="fb540-111">To remove the databases on the SQL Server, you must be a member of the SQL Server sysadmins group for the SQL Server where you are removing the database files.</span></span>

2.  <span data-ttu-id="fb540-112">Lync Server-Verwaltungsshell öffnen</span><span class="sxs-lookup"><span data-stu-id="fb540-112">Open Lync Server Management Shell</span></span>

3.  <span data-ttu-id="fb540-113">Geben Sie Folgendes ein, um die Datenbank für den Poolbenutzerspeicher zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="fb540-113">To remove the database for the pool user store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="fb540-114">Dabei \<FQDN\> ist der vollqualifizierte Domänenname (Fully Qualified Domain Name, FQDN) des Datenbankservers und \<instance\> die benannte Datenbankinstanz (sofern eine definiert wurde).</span><span class="sxs-lookup"><span data-stu-id="fb540-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

4.  <span data-ttu-id="fb540-115">Geben Sie Folgendes ein, um die Datenbank für den Poolanwendungsspeicher zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="fb540-115">To remove the database for the pool application store, type:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="fb540-116">Dabei \<FQDN\> ist der FQDN des Datenbankservers und \<instance\> die benannte Datenbankinstanz (sofern eine definiert wurde).</span><span class="sxs-lookup"><span data-stu-id="fb540-116">Where \<FQDN\> is the FQDN of the database server, and \<instance\> is the named database instance (that is, if one was defined).</span></span>

5.  <span data-ttu-id="fb540-117">Wenn Sie vom **Uninstall-CsDataBase**-Cmdlet aufgefordert werden, Aktionen zu bestätigen, lesen Sie die Informationen, und drücken Sie dann **J** (oder die EINGABETASTE), oder drücken Sie **N** und dann die EINGABETASTE, wenn Sie die Ausführung des Cmdlets beenden möchten (im Falle von Fehlern).</span><span class="sxs-lookup"><span data-stu-id="fb540-117">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

