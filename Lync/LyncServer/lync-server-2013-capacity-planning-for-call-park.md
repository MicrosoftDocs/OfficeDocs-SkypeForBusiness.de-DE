---
title: 'Lync Server 2013: Kapazitätsplanung für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1192ef9b5b30c722a4f62973cf4992da3ca7300
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a><span data-ttu-id="3eb13-102">Kapazitätsplanung für das Parken von Anrufen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3eb13-102">Capacity planning for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3eb13-103">_**Letztes Änderungsstand des Themas:** 2012-09-13_</span><span class="sxs-lookup"><span data-stu-id="3eb13-103">_**Topic Last Modified:** 2012-09-13_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="3eb13-104">In der folgenden Tabelle wird das Benutzermodell für das Parken von Anrufen beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3eb13-104">The following table describes the Call Park user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3eb13-105">Beachten Sie, dass bei der Kapazitätsplanung für die Notfallwiederherstellung jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitslasten für die Dienste für den Parken von Anrufen in beiden Pools zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3eb13-105">Keep in mind that, for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for Call Park services in both pools.</span></span>



</div>

### <a name="call-park-user-model"></a><span data-ttu-id="3eb13-106">Benutzermodell der Funktion zum Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="3eb13-106">Call Park User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3eb13-107">Metrik</span><span class="sxs-lookup"><span data-stu-id="3eb13-107">Metric</span></span></th>
<th><span data-ttu-id="3eb13-108">Pro Front-End-Pool (mit 8 Front-End-Servern)</span><span class="sxs-lookup"><span data-stu-id="3eb13-108">Per Front End pool (with 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="3eb13-109">Pro Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="3eb13-109">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3eb13-110">Rate für das Parken von Anrufen</span><span class="sxs-lookup"><span data-stu-id="3eb13-110">Park rate</span></span></p></td>
<td><p><span data-ttu-id="3eb13-111">8 pro Minute</span><span class="sxs-lookup"><span data-stu-id="3eb13-111">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="3eb13-112">1 pro Minute</span><span class="sxs-lookup"><span data-stu-id="3eb13-112">1 per minute</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3eb13-113">Rate für das Abrufen geparkter Anrufe</span><span class="sxs-lookup"><span data-stu-id="3eb13-113">Retrieve parked call rate</span></span></p></td>
<td><p><span data-ttu-id="3eb13-114">8 pro Minute</span><span class="sxs-lookup"><span data-stu-id="3eb13-114">8 per minute</span></span></p></td>
<td><p><span data-ttu-id="3eb13-115">1 pro Minute</span><span class="sxs-lookup"><span data-stu-id="3eb13-115">1 per minute</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3eb13-116">Durchschnittliche Parkdauer</span><span class="sxs-lookup"><span data-stu-id="3eb13-116">Average park duration</span></span></p></td>
<td><p><span data-ttu-id="3eb13-117">60 Sekunden</span><span class="sxs-lookup"><span data-stu-id="3eb13-117">60 seconds</span></span></p></td>
<td><p><span data-ttu-id="3eb13-118">60 Sekunden</span><span class="sxs-lookup"><span data-stu-id="3eb13-118">60 seconds</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

