---
title: 'Lync Server 2013: Kapazitätsplanung für Reaktionsgruppen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Response Group
ms:assetid: a2459a69-1f45-4f2f-bca5-d4f442708e44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412754(v=OCS.15)
ms:contentKeyID: 48184951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc7c17146c3cd5913ae82c84b8d7ae292db990f7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="876dd-102">Kapazitätsplanung für Reaktionsgruppen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="876dd-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="876dd-103">_**Letztes Änderungsstand des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="876dd-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="876dd-104">In der folgenden Tabelle wird das Benutzermodell der Reaktionsgruppe beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="876dd-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="876dd-p101">Bei den Zahlen in der folgenden Tabelle wird davon ausgegangen, dass Sie 16-kHz-, Mono-, 16-Bit-WAV-Dateien für alle Audiodateien für Reaktionsgruppen verwenden. Wenn Sie andere Dateiformate, z. B. Windows Media Audio (WMA), einsetzen, können die Zahlen abweichen.</span><span class="sxs-lookup"><span data-stu-id="876dd-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="876dd-107">Bedenken Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitslasten für alle Reaktionsgruppen in beiden Pools zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="876dd-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="876dd-108">Benutzermodell für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="876dd-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="876dd-109">Metrik</span><span class="sxs-lookup"><span data-stu-id="876dd-109">Metric</span></span></th>
<th><span data-ttu-id="876dd-110">Pro Enterprise Edition-Pool (mit 8 Front-End-Servern)</span><span class="sxs-lookup"><span data-stu-id="876dd-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="876dd-111">Pro Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="876dd-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="876dd-112">Eingehende Anrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="876dd-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="876dd-113">16 </span><span class="sxs-lookup"><span data-stu-id="876dd-113">16</span></span></p></td>
<td><p><span data-ttu-id="876dd-114">2</span><span class="sxs-lookup"><span data-stu-id="876dd-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="876dd-115">Gleichzeitige mit interaktiver Sprachantwort (IVR) oder Wartemusik (MoH) verbundene Anrufe</span><span class="sxs-lookup"><span data-stu-id="876dd-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="876dd-116">480</span><span class="sxs-lookup"><span data-stu-id="876dd-116">480</span></span></p></td>
<td><p><span data-ttu-id="876dd-117">60</span><span class="sxs-lookup"><span data-stu-id="876dd-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="876dd-118">Gleichzeitige anonyme Sitzungen (ohne Instant Messaging)</span><span class="sxs-lookup"><span data-stu-id="876dd-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="876dd-119">224</span><span class="sxs-lookup"><span data-stu-id="876dd-119">224</span></span></p></td>
<td><p><span data-ttu-id="876dd-120">28</span><span class="sxs-lookup"><span data-stu-id="876dd-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="876dd-121">Gleichzeitige anonyme Sitzungen (mit Instant Messaging)</span><span class="sxs-lookup"><span data-stu-id="876dd-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="876dd-122">64</span><span class="sxs-lookup"><span data-stu-id="876dd-122">64</span></span></p></td>
<td><p><span data-ttu-id="876dd-123">8 </span><span class="sxs-lookup"><span data-stu-id="876dd-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="876dd-124">Aktive Agents (formell und informell)</span><span class="sxs-lookup"><span data-stu-id="876dd-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="876dd-125">1200</span><span class="sxs-lookup"><span data-stu-id="876dd-125">1200</span></span></p></td>
<td><p><span data-ttu-id="876dd-126">1200</span><span class="sxs-lookup"><span data-stu-id="876dd-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="876dd-127">Anzahl der Sammelanschlüsse</span><span class="sxs-lookup"><span data-stu-id="876dd-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="876dd-128">400</span><span class="sxs-lookup"><span data-stu-id="876dd-128">400</span></span></p></td>
<td><p><span data-ttu-id="876dd-129">400</span><span class="sxs-lookup"><span data-stu-id="876dd-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="876dd-130">Anzahl der IVR-Gruppen (Verwendung der Spracherkennung)</span><span class="sxs-lookup"><span data-stu-id="876dd-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="876dd-131">200</span><span class="sxs-lookup"><span data-stu-id="876dd-131">200</span></span></p></td>
<td><p><span data-ttu-id="876dd-132">200</span><span class="sxs-lookup"><span data-stu-id="876dd-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

