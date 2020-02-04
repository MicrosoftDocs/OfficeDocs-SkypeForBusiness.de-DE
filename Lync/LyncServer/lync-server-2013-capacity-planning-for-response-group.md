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
ms.openlocfilehash: 5efb1b928ce7b4bafbbff20ad31872fe12735fe0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736993"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-response-group-in-lync-server-2013"></a><span data-ttu-id="5b035-102">Kapazitätsplanung für Reaktionsgruppen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b035-102">Capacity planning for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b035-103">_**Letztes Änderungsdatum des Themas:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="5b035-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="5b035-104">In der folgenden Tabelle wird das Benutzermodell der Reaktionsgruppe beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5b035-104">The following table describes the Response Group user model that you can use as the basis for capacity planning requirements.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5b035-p101">Bei den Zahlen in der folgenden Tabelle wird davon ausgegangen, dass Sie 16-kHz-, Mono-, 16-Bit-WAV-Dateien für alle Audiodateien für Reaktionsgruppen verwenden. Wenn Sie andere Dateiformate, z. B. Windows Media Audio (WMA), einsetzen, können die Zahlen abweichen.</span><span class="sxs-lookup"><span data-stu-id="5b035-p101">The numbers in the following table assume that you use 16 kHz, mono, 16-bit Wave (.wav) files for all response group audio files. If you use other file formats, such as Windows Media Audio (.wma), the numbers may vary.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="5b035-107">Bedenken Sie bei der Kapazitätsplanung für die Notfallwiederherstellung, dass jeder Pool eines Poolpaars in der Lage sein sollte, die Arbeitslasten für alle Reaktionsgruppen in beiden Pools zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="5b035-107">Keep in mind that for disaster recovery capacity planning, each pool of a paired pool should be able to handle the workloads for all the response groups in both pools.</span></span>



</div>

### <a name="response-group-user-model"></a><span data-ttu-id="5b035-108">Benutzermodell für Reaktionsgruppen</span><span class="sxs-lookup"><span data-stu-id="5b035-108">Response Group User Model</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b035-109">Metrik</span><span class="sxs-lookup"><span data-stu-id="5b035-109">Metric</span></span></th>
<th><span data-ttu-id="5b035-110">Pro Enterprise Edition-Pool (mit 8 Front-End-Servern)</span><span class="sxs-lookup"><span data-stu-id="5b035-110">Per Enterprise Edition pool (With 8 Front End Servers)</span></span></th>
<th><span data-ttu-id="5b035-111">Pro Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="5b035-111">Per Standard Edition server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b035-112">Eingehende Anrufe pro Sekunde</span><span class="sxs-lookup"><span data-stu-id="5b035-112">Incoming calls per second</span></span></p></td>
<td><p><span data-ttu-id="5b035-113">16</span><span class="sxs-lookup"><span data-stu-id="5b035-113">16</span></span></p></td>
<td><p><span data-ttu-id="5b035-114">2</span><span class="sxs-lookup"><span data-stu-id="5b035-114">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b035-115">Gleichzeitige mit interaktiver Sprachantwort (IVR) oder Wartemusik (MoH) verbundene Anrufe</span><span class="sxs-lookup"><span data-stu-id="5b035-115">Concurrent calls connected to IVR or MoH</span></span></p></td>
<td><p><span data-ttu-id="5b035-116">480</span><span class="sxs-lookup"><span data-stu-id="5b035-116">480</span></span></p></td>
<td><p><span data-ttu-id="5b035-117">60</span><span class="sxs-lookup"><span data-stu-id="5b035-117">60</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b035-118">Gleichzeitige anonyme Sitzungen (ohne Chat)</span><span class="sxs-lookup"><span data-stu-id="5b035-118">Concurrent anonymous sessions (without IM)</span></span></p></td>
<td><p><span data-ttu-id="5b035-119">224</span><span class="sxs-lookup"><span data-stu-id="5b035-119">224</span></span></p></td>
<td><p><span data-ttu-id="5b035-120">28</span><span class="sxs-lookup"><span data-stu-id="5b035-120">28</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b035-121">Gleichzeitige anonyme Sitzungen (mit Chat)</span><span class="sxs-lookup"><span data-stu-id="5b035-121">Concurrent anonymous sessions (with IM)</span></span></p></td>
<td><p><span data-ttu-id="5b035-122">64</span><span class="sxs-lookup"><span data-stu-id="5b035-122">64</span></span></p></td>
<td><p><span data-ttu-id="5b035-123">8</span><span class="sxs-lookup"><span data-stu-id="5b035-123">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b035-124">Aktive Agents (formell und informell)</span><span class="sxs-lookup"><span data-stu-id="5b035-124">Active agents (formal and informal)</span></span></p></td>
<td><p><span data-ttu-id="5b035-125">1200</span><span class="sxs-lookup"><span data-stu-id="5b035-125">1200</span></span></p></td>
<td><p><span data-ttu-id="5b035-126">1200</span><span class="sxs-lookup"><span data-stu-id="5b035-126">1200</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b035-127">Anzahl der Sammelanschlüsse</span><span class="sxs-lookup"><span data-stu-id="5b035-127">Number of hunt groups</span></span></p></td>
<td><p><span data-ttu-id="5b035-128">400</span><span class="sxs-lookup"><span data-stu-id="5b035-128">400</span></span></p></td>
<td><p><span data-ttu-id="5b035-129">400</span><span class="sxs-lookup"><span data-stu-id="5b035-129">400</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b035-130">Anzahl der IVR-Gruppen (Verwendung der Spracherkennung)</span><span class="sxs-lookup"><span data-stu-id="5b035-130">Number of IVR groups (use speech recognition)</span></span></p></td>
<td><p><span data-ttu-id="5b035-131">200</span><span class="sxs-lookup"><span data-stu-id="5b035-131">200</span></span></p></td>
<td><p><span data-ttu-id="5b035-132">200</span><span class="sxs-lookup"><span data-stu-id="5b035-132">200</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

