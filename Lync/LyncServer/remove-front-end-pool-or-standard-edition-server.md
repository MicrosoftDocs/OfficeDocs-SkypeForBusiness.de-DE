---
title: Entfernen eines Front-End-Pools oder Standard Edition-Servers
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a1c36de9aa3cbd4a46dc0bba4c862734b382ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500052"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="89186-102">Entfernen eines Front-End-Pools oder Standard Edition-Servers</span><span class="sxs-lookup"><span data-stu-id="89186-102">Remove Front End pool or Standard Edition server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89186-103">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="89186-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="89186-104">In diesem Thema werden Sie durch den Vorgang zum Entfernen einer Front-End-Pool oder einer Standard Edition Front-End-Server geführt.</span><span class="sxs-lookup"><span data-stu-id="89186-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="89186-105">Wenn Sie ein Front-End-Pool entfernen, entfernen Sie alle Front-End-Server, die zum Pool gehören, als Teil des Prozesses zur Pool Entfernung.</span><span class="sxs-lookup"><span data-stu-id="89186-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="89186-106">Wenn Sie eine Standard Edition-Front-End-Server entfernen, müssen Sie die SQL-speicherdefinition aus dem Topologie-Generator entfernen.</span><span class="sxs-lookup"><span data-stu-id="89186-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="89186-107">So entfernen Sie einen Front-End-Server-Pool</span><span class="sxs-lookup"><span data-stu-id="89186-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="89186-108">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="89186-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="89186-109">Navigieren Sie zum Knoten lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89186-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="89186-110">Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie die Front-End-Pool, klicken Sie mit der rechten Maustaste auf das Front-End-Pool, das Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="89186-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="89186-111">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die lync Server-Bereitstellung bei Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="89186-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="89186-112">So entfernen Sie einen Standard Edition-Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="89186-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="89186-113">Öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="89186-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="89186-114">Navigieren Sie zum Knoten lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="89186-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="89186-115">Erweitern Sie **Standard Edition-Front-End-Server**, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="89186-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="89186-116">Erweitern Sie **SQL-Speicher**, klicken Sie mit der rechten Maustaste auf die SQL Server Datenbank, die der Standard Edition Front-End-Server zugeordnet ist, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="89186-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="89186-117">Sie müssen die Definition der verbundenen SQL Server Datenbanken aus der Standard Edition Front-End-Server entfernen.</span><span class="sxs-lookup"><span data-stu-id="89186-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="89186-118">Veröffentlichen Sie die Topologie, überprüfen Sie den Replikationsstatus, und führen Sie dann den Assistenten für die lync Server-Bereitstellung bei Bedarf aus.</span><span class="sxs-lookup"><span data-stu-id="89186-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

