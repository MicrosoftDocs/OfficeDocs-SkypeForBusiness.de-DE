---
title: 'Lync Server 2013: medialist-Tabelle'
description: 'Lync Server 2013: medialist-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaList table
ms:assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398279(v=OCS.15)
ms:contentKeyID: 48183579
ms.date: 07/12/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e54535cd4a081657e7dcd59446cf65aaa3af7cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572071"
---
# <a name="medialist-table-in-lync-server-2013"></a><span data-ttu-id="461b2-103">Medialist-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="461b2-103">MediaList table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="461b2-104">_**Letztes Änderungsstand des Themas:** 2016-07-12_</span><span class="sxs-lookup"><span data-stu-id="461b2-104">_**Topic Last Modified:** 2016-07-12_</span></span>

<span data-ttu-id="461b2-105">Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="461b2-105">The MediaList table is a static table that stores the list of various media types.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="461b2-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="461b2-106">Column</span></span></th>
<th><span data-ttu-id="461b2-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="461b2-107">Data Type</span></span></th>
<th><span data-ttu-id="461b2-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="461b2-108">Key/Index</span></span></th>
<th><span data-ttu-id="461b2-109">Details</span><span class="sxs-lookup"><span data-stu-id="461b2-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="461b2-110"><strong>Mediaid</strong></span><span class="sxs-lookup"><span data-stu-id="461b2-110"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="461b2-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="461b2-111">tinyint</span></span></p></td>
<td><p><span data-ttu-id="461b2-112">Primary</span><span class="sxs-lookup"><span data-stu-id="461b2-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="461b2-113">Werte: 1-7</span><span class="sxs-lookup"><span data-stu-id="461b2-113">Values: 1-7</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="461b2-114"><strong>Medien</strong></span><span class="sxs-lookup"><span data-stu-id="461b2-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="461b2-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="461b2-115">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="461b2-116">Statische Zuordnung von Medien-und Medien Werten:</span><span class="sxs-lookup"><span data-stu-id="461b2-116">Static mapping of MediaID and Media values:</span></span></p>
<ul>
<li><p><span data-ttu-id="461b2-117">1 – Chat</span><span class="sxs-lookup"><span data-stu-id="461b2-117">1 – IM</span></span></p></li>
<li><p><span data-ttu-id="461b2-118">2 – Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="461b2-118">2 – File Transfer</span></span></p></li>
<li><p><span data-ttu-id="461b2-119">3 – Remoteunterstützung</span><span class="sxs-lookup"><span data-stu-id="461b2-119">3 – Remote Assistance</span></span></p></li>
<li><p><span data-ttu-id="461b2-120">4 – Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="461b2-120">4 – Application Sharing</span></span></p></li>
<li><p><span data-ttu-id="461b2-121">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="461b2-121">5 – Audio</span></span></p></li>
<li><p><span data-ttu-id="461b2-122">6 – Video</span><span class="sxs-lookup"><span data-stu-id="461b2-122">6 – Video</span></span></p></li>
<li><p><span data-ttu-id="461b2-123">7 – Anwendungseinladung</span><span class="sxs-lookup"><span data-stu-id="461b2-123">7 – App Invite</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="461b2-124">Wenn Sie den modaltyp für die Werte in LcsCDR. SessionDetailsView. mediatypes zu bestimmen ermitteln möchten, müssen Sie den folgenden Join-Codeausschnitt verwenden:</span><span class="sxs-lookup"><span data-stu-id="461b2-124">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span>

    LEFT JOIN on Media.MediaId = MediaList.MediaId

</div>

<span> </span>

</div>

</div>

</div>

