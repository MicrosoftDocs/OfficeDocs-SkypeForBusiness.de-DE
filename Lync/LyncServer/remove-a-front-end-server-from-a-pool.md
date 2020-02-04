---
title: Entfernen eines Front-End-Servers aus einem Pool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="84e51-102">Entfernen eines Front-End-Servers aus einem Pool</span><span class="sxs-lookup"><span data-stu-id="84e51-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84e51-103">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="84e51-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="84e51-104">Der Microsoft lync Server 2010 Enterprise Edition-Front-End-Server kann nicht als eigenständiger Computer vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="84e51-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="84e51-105">Es muss als Front-End-Pool definiert werden, auch wenn es nur einen einzelnen Computer im Pool gibt.</span><span class="sxs-lookup"><span data-stu-id="84e51-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="84e51-106">Dieses Thema führt Sie durch den Vorgang zum Entfernen eines einzelnen Front-End-Servers aus einem vorhandenen Front-End-Pool.</span><span class="sxs-lookup"><span data-stu-id="84e51-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="84e51-107">Wenn der Front-End-Server der letzte Server im Pool ist oder wenn Sie den Pool vollständig entfernen, lesen Sie [Entfernen des Front-End-Pools oder des Standard Edition-Servers](remove-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="84e51-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="84e51-108">Es ist nicht erforderlich, die einzelnen Front-End-Server zu entfernen, bevor Sie den Front-End-Pool entfernen.</span><span class="sxs-lookup"><span data-stu-id="84e51-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="84e51-109">Wenn Sie den Pool entfernen, entfernen Sie jeden Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="84e51-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="84e51-110">So entfernen Sie einen Front-End-Server aus einem Pool</span><span class="sxs-lookup"><span data-stu-id="84e51-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="84e51-111">Öffnen Sie den lync Server 2013-Front-End-Server, öffnen Sie den Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="84e51-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="84e51-112">Navigieren Sie zum lync Server 2010-Knoten.</span><span class="sxs-lookup"><span data-stu-id="84e51-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="84e51-113">Erweitern Sie **Enterprise Edition-Front-End-Pools**, erweitern Sie den Front-End-Pool mit dem zu entfernenden Front-End-Server, klicken Sie mit der rechten Maustaste auf den Front-End-Server, den Sie entfernen möchten, und klicken Sie dann auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="84e51-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

