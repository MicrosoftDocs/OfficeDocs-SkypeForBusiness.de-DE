---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66793cc3bd545d343198d00f7fb477c1f9b88fac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839489"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="75b36-102">ConferenceJoinTimeThresholds-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75b36-102">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75b36-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="75b36-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="75b36-104">Die Tabelle "ConferenceJoinTimeThresholds" enthält die Klassifizierungs Grenzen, die vom Zusammenfassungsbericht "Konferenzteilnahme Zeit" verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="75b36-104">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report.</span></span> <span data-ttu-id="75b36-105">Der Bericht "Konferenz Teilzeit-Zusammenfassung" fasst die Zeitspanne zusammen, die der Benutzer für eine erfolgreiche Teilnahme an einer Konferenz benötigt. Diese Zeitwerte werden sowohl als Mittelwert als auch in einer der folgenden Kategorien angezeigt:</span><span class="sxs-lookup"><span data-stu-id="75b36-105">The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="75b36-106">Weniger als 2 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="75b36-106">Less than 2 seconds.</span></span>

  - <span data-ttu-id="75b36-107">Zwischen 2 Sekunden und 5 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="75b36-107">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="75b36-108">Zwischen 5 Sekunden und 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="75b36-108">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="75b36-109">Mehr als 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="75b36-109">More than 10 seconds.</span></span>

<span data-ttu-id="75b36-110">Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungs Werte 2 Sekunden, 5 Sekunden und 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="75b36-110">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="75b36-111">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="75b36-111">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75b36-112">Spalte</span><span class="sxs-lookup"><span data-stu-id="75b36-112">Column</span></span></th>
<th><span data-ttu-id="75b36-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="75b36-113">Data Type</span></span></th>
<th><span data-ttu-id="75b36-114">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="75b36-114">Key/Index</span></span></th>
<th><span data-ttu-id="75b36-115">Details</span><span class="sxs-lookup"><span data-stu-id="75b36-115">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75b36-116"><strong>Schwellenwert</strong></span><span class="sxs-lookup"><span data-stu-id="75b36-116"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="75b36-117">int</span><span class="sxs-lookup"><span data-stu-id="75b36-117">int</span></span></p></td>
<td><p><span data-ttu-id="75b36-118">Primary</span><span class="sxs-lookup"><span data-stu-id="75b36-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="75b36-119">Eindeutiger Bezeichner für die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="75b36-119">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75b36-120"><strong>ThresholdValue</strong></span><span class="sxs-lookup"><span data-stu-id="75b36-120"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="75b36-121">int</span><span class="sxs-lookup"><span data-stu-id="75b36-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="75b36-122">Obergrenze für die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="75b36-122">Upper limit for the classification.</span></span> <span data-ttu-id="75b36-123">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="75b36-123">Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="75b36-124">2</span><span class="sxs-lookup"><span data-stu-id="75b36-124">2</span></span></p></li>
<li><p><span data-ttu-id="75b36-125">5</span><span class="sxs-lookup"><span data-stu-id="75b36-125">5</span></span></p></li>
<li><p><span data-ttu-id="75b36-126">10</span><span class="sxs-lookup"><span data-stu-id="75b36-126">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

