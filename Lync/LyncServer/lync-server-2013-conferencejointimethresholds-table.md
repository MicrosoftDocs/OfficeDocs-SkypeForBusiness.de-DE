---
title: 'Lync Server 2013: ConferenceJoinTimeThresholds-Tabelle'
description: 'Lync Server 2013: ConferenceJoinTimeThresholds-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceJoinTimeThresholds table
ms:assetid: 3944d724-bdd8-4d1c-a2af-933ee8141529
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204809(v=OCS.15)
ms:contentKeyID: 48183855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e38c8b99f444e16309882b6a8885d166fdceb9b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561671"
---
# <a name="conferencejointimethresholds-table-in-lync-server-2013"></a><span data-ttu-id="2ac3d-103">ConferenceJoinTimeThresholds-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ac3d-103">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ac3d-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="2ac3d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="2ac3d-p101">Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungsgrenzwerte, die vom zusammenfassenden Bericht über den Zeitpunkt des Konferenzbeitritts verwendet werden. Der Bericht über den Zeitpunkt des Konferenzbeitritts enthält eine Zusammenfassung der Zeit, die Benutzer benötigen, um einer Konferenz erfolgreich beizutreten. Diese Zeitwerte werden sowohl als Durchschnitt als auch in einer der folgenden Kategorien gemeldet:</span><span class="sxs-lookup"><span data-stu-id="2ac3d-p101">The ConferenceJoinTimeThresholds table contains the classification boundaries used by the Conference Join Time Summary Report. The Conference Join Time Summary Report summarizes the amount time required for users to successfully join a conference; these time values are reported both as an average and in one of the following categories:</span></span>

  - <span data-ttu-id="2ac3d-107">Weniger als 2 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="2ac3d-107">Less than 2 seconds.</span></span>

  - <span data-ttu-id="2ac3d-108">Zwischen 2 Sekunden und 5 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="2ac3d-108">Between 2 second and 5 seconds.</span></span>

  - <span data-ttu-id="2ac3d-109">Zwischen 5 Sekunden und 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="2ac3d-109">Between 5 seconds and 10 seconds.</span></span>

  - <span data-ttu-id="2ac3d-110">Mehr als 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="2ac3d-110">More than 10 seconds.</span></span>

<span data-ttu-id="2ac3d-111">Die Tabelle ConferenceJoinTimeThresholds enthält die Klassifizierungswerte 2 Sekunden, 5 Sekunden und 10 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="2ac3d-111">The ConferenceJoinTimeThresholds table contains the classification values 2 seconds, 5 seconds, and 10 seconds.</span></span>

<span data-ttu-id="2ac3d-112">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="2ac3d-112">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ac3d-113">Spalte</span><span class="sxs-lookup"><span data-stu-id="2ac3d-113">Column</span></span></th>
<th><span data-ttu-id="2ac3d-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2ac3d-114">Data Type</span></span></th>
<th><span data-ttu-id="2ac3d-115">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="2ac3d-115">Key/Index</span></span></th>
<th><span data-ttu-id="2ac3d-116">Details</span><span class="sxs-lookup"><span data-stu-id="2ac3d-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ac3d-117"><strong>Schwellenwert</strong></span><span class="sxs-lookup"><span data-stu-id="2ac3d-117"><strong>ThresholdId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ac3d-118">int</span><span class="sxs-lookup"><span data-stu-id="2ac3d-118">int</span></span></p></td>
<td><p><span data-ttu-id="2ac3d-119">Primary</span><span class="sxs-lookup"><span data-stu-id="2ac3d-119">Primary</span></span></p></td>
<td><p><span data-ttu-id="2ac3d-120">Eindeutige ID für die Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="2ac3d-120">Unique identifier for the classification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ac3d-121"><strong>Schwellenwert</strong></span><span class="sxs-lookup"><span data-stu-id="2ac3d-121"><strong>ThresholdValue</strong></span></span></p></td>
<td><p><span data-ttu-id="2ac3d-122">int</span><span class="sxs-lookup"><span data-stu-id="2ac3d-122">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="2ac3d-p102">Oberer Grenzwert für die Klassifizierung. Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="2ac3d-p102">Upper limit for the classification. Allowed values are:</span></span></p>
<ol>
<li><p><span data-ttu-id="2ac3d-125">2</span><span class="sxs-lookup"><span data-stu-id="2ac3d-125">2</span></span></p></li>
<li><p><span data-ttu-id="2ac3d-126">5 </span><span class="sxs-lookup"><span data-stu-id="2ac3d-126">5</span></span></p></li>
<li><p><span data-ttu-id="2ac3d-127">10 </span><span class="sxs-lookup"><span data-stu-id="2ac3d-127">10</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

