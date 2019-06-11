---
title: 'Lync Server 2013: MediaList-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fa53ff1ce4ce419a4e7a29124593c7b01006a3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="9cacd-102">MediaList-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9cacd-102">MediaList table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cacd-103">_**Letztes Änderungsdatum des Themas:** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="9cacd-103">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="9cacd-104">Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="9cacd-104">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9cacd-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="9cacd-105">Column</span></span></th>
<th><span data-ttu-id="9cacd-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9cacd-106">Data Type</span></span></th>
<th><span data-ttu-id="9cacd-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="9cacd-107">Key/Index</span></span></th>
<th><span data-ttu-id="9cacd-108">Details</span><span class="sxs-lookup"><span data-stu-id="9cacd-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9cacd-109"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="9cacd-109"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="9cacd-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="9cacd-110">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9cacd-111">Primary</span><span class="sxs-lookup"><span data-stu-id="9cacd-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="9cacd-112">Werte: 1-7</span><span class="sxs-lookup"><span data-stu-id="9cacd-112">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9cacd-113"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="9cacd-113"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="9cacd-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9cacd-114">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9cacd-115">Statische Zuordnung von MediaID- und Media-Werten</span><span class="sxs-lookup"><span data-stu-id="9cacd-115">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="9cacd-116">1 – im</span><span class="sxs-lookup"><span data-stu-id="9cacd-116">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="9cacd-117">2 - Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="9cacd-117">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="9cacd-118">3 – Remoteunterstützung</span><span class="sxs-lookup"><span data-stu-id="9cacd-118">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="9cacd-119">4 – Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="9cacd-119">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="9cacd-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="9cacd-120">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="9cacd-121">6 – Video</span><span class="sxs-lookup"><span data-stu-id="9cacd-121">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="9cacd-122">7 – Anwendungseinladung</span><span class="sxs-lookup"><span data-stu-id="9cacd-122">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9cacd-123">Wenn Sie versuchen, den Modalitätstyp für die Werte in LcsCDR.SessionDetailsView.MediaTypes zu bestimmen, müssen Sie das folgende Join-Snippet verwenden: </span><span class="sxs-lookup"><span data-stu-id="9cacd-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

