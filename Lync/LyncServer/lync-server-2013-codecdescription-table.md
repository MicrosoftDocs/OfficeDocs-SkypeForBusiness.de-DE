---
title: 'Lync Server 2013: CodecDescription-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CodecDescription table
ms:assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204797(v=OCS.15)
ms:contentKeyID: 48183802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a407d8eeb1ad9e318ff2f960f8cb7d62b1e3a9f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757119"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="codecdescription-table-in-lync-server-2013"></a><span data-ttu-id="c4c4d-102">CodecDescription-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c4c4d-102">CodecDescription table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4c4d-103">_**Letztes Änderungsdatum des Themas:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="c4c4d-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="c4c4d-104">Die CodecDescription-Tabelle ordnet eindeutige Codec-IDs dem zugehörigen Codec zu.</span><span class="sxs-lookup"><span data-stu-id="c4c4d-104">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="c4c4d-105">Codecs werden verwendet, um digitale Signale für die Übertragung und Übertragung zu kodieren und diese Signale zur Wiedergabe zu decodieren.</span><span class="sxs-lookup"><span data-stu-id="c4c4d-105">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="c4c4d-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c4c4d-106">This table was introduced in Microsoft Lync Server 2013</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4c4d-107"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="c4c4d-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c4c4d-108"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="c4c4d-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c4c4d-109"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="c4c4d-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c4c4d-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c4c4d-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4c4d-111"><strong>CodecDescriptionKey</strong></span><span class="sxs-lookup"><span data-stu-id="c4c4d-111"><strong>CodecDescriptionKey</strong></span></span></p></td>
<td><p><span data-ttu-id="c4c4d-112">smallint</span><span class="sxs-lookup"><span data-stu-id="c4c4d-112">smallint</span></span></p></td>
<td><p><span data-ttu-id="c4c4d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="c4c4d-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="c4c4d-114">Eindeutiger Bezeichner, der dem Codec zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="c4c4d-114">Unique identifier assigned to the codec.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4c4d-115"><strong>CodecDescription</strong></span><span class="sxs-lookup"><span data-stu-id="c4c4d-115"><strong>CodecDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="c4c4d-116">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="c4c4d-116">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c4c4d-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="c4c4d-117">Unique</span></span></p></td>
<td><p><span data-ttu-id="c4c4d-118">Eindeutige Beschreibung des Codecs, der dem CodecDescriptionKey entspricht.</span><span class="sxs-lookup"><span data-stu-id="c4c4d-118">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

