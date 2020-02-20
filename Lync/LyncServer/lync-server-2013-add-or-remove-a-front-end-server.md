---
title: 'Lync Server 2013: Hinzufügen oder Entfernen eines Front-End-Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add or remove a Front End Server
ms:assetid: ab748733-6bad-4c93-8dda-db8d5271653d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205153(v=OCS.15)
ms:contentKeyID: 48185050
ms.date: 01/21/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29c1b3800b05ac4318f853ece95b935c6e65c16c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-or-remove-a-front-end-server-in-lync-server-2013"></a><span data-ttu-id="b19ee-102">Hinzufügen oder Entfernen eines Front-End-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b19ee-102">Add or remove a Front End Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b19ee-103">_**Letztes Änderungsstand des Themas:** 2016-01-21_</span><span class="sxs-lookup"><span data-stu-id="b19ee-103">_**Topic Last Modified:** 2016-01-21_</span></span>

<span data-ttu-id="b19ee-p101">Wenn Sie einem Pool einen Front-End-Server hinzufügen oder einen Front-End-Server aus einem Pool entfernen, müssen Sie den Pool anschließend neu starten. Wenden Sie beim Hinzufügen oder Entfernen eines Front-End-Servers das folgende Verfahren an, um Dienstunterbrechungen für die Benutzer zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="b19ee-p101">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool. To prevent any interruption of service to users, use the following procedure when adding or removing a Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b19ee-106">Wenn Sie dem Pool neue Server hinzufügen, aktualisieren Sie die neuen Pool Server so, dass Sie auf der gleichen kumulativen Update Ebene wie die vorhandenen Server im Pool sind.</span><span class="sxs-lookup"><span data-stu-id="b19ee-106">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span>



</div>

<div>

## <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="b19ee-107">So können Sie Front-End-Server hinzufügen oder entfernen</span><span class="sxs-lookup"><span data-stu-id="b19ee-107">To add or remove Front End servers</span></span>

1.  <span data-ttu-id="b19ee-p102">Wenn Sie Front-End-Server entfernen, beenden Sie zunächst neue Verbindungen mit diesen Servern. Dazu können Sie das folgende Cmdlet verwenden:</span><span class="sxs-lookup"><span data-stu-id="b19ee-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
        Stop-CsWindowsServices -Graceful

2.  <span data-ttu-id="b19ee-110">Wenn auf den zu entfernenden Servern keine aktuellen Sitzungen vorhanden sind, halten Sie die Lync Server-Dienste auf diesen Servern an.</span><span class="sxs-lookup"><span data-stu-id="b19ee-110">When the servers being removed have no current sessions, stop Lync Server services on them.</span></span>

3.  <span data-ttu-id="b19ee-111">Öffnen Sie den Topologie-Generator, und fügen Sie die benötigten Server hinzu, oder entfernen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="b19ee-111">Open Topology Builder, and add or remove the necessary servers.</span></span>

4.  <span data-ttu-id="b19ee-112">Veröffentlichen Sie die Topologie.</span><span class="sxs-lookup"><span data-stu-id="b19ee-112">Publish the topology.</span></span>

5.  <span data-ttu-id="b19ee-113">Wenn der Pool von zwei Front-End-Servern auf mehr als zwei oder von mehr als zwei Servern auf genau zwei fortgegangen ist, müssen Sie das folgende Cmdlet eingeben:</span><span class="sxs-lookup"><span data-stu-id="b19ee-113">If the pool has gone from having two Front End Servers to more than two, or gone from more than two servers to exactly two, you need to type the following cmdlet:</span></span>
    
        Reset-CsPoolRegistrarState-ResetType FullReset -PoolFqdn <PoolFqdn>
    
    <span data-ttu-id="b19ee-114">Wenn der Pool drei oder mehr Server aufweist, müssen beim Eingeben dieses Cmdlets mindestens drei dieser Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b19ee-114">If the pool has three or more servers, then at least three of those servers must be running when you type this cmdlet.</span></span>

6.  <span data-ttu-id="b19ee-115">Starten Sie alle Front-End-Server im Pool nacheinander neu.</span><span class="sxs-lookup"><span data-stu-id="b19ee-115">Restart all Front End Servers in the pool, one at a time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

