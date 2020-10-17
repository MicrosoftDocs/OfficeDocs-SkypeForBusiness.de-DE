---
title: 'Lync Server 2013: UserStatistics-Tabelle'
description: 'Lync Server 2013: UserStatistics-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: UserStatistics table
ms:assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721893(v=OCS.15)
ms:contentKeyID: 49733827
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75b34fa3c34af4cc9cf2cacc6ae7feb4d217114c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548531"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="f5f03-103">UserStatistics-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5f03-103">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5f03-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f5f03-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f5f03-105">Die UserStatistics-Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f5f03-105">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="f5f03-106">Jeder Datensatz in der Tabelle speichert Informationen über die Verwendung des Systems durch einen einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f5f03-106">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="f5f03-107">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f5f03-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f5f03-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="f5f03-108">Column</span></span></th>
<th><span data-ttu-id="f5f03-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f5f03-109">Data Type</span></span></th>
<th><span data-ttu-id="f5f03-110">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="f5f03-110">Key/Index</span></span></th>
<th><span data-ttu-id="f5f03-111">Details</span><span class="sxs-lookup"><span data-stu-id="f5f03-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f5f03-112"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="f5f03-112"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f03-113">int</span><span class="sxs-lookup"><span data-stu-id="f5f03-113">int</span></span></p></td>
<td><p><span data-ttu-id="f5f03-114">Primary</span><span class="sxs-lookup"><span data-stu-id="f5f03-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="f5f03-115">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="f5f03-115">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f03-116"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5f03-116"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f03-117">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f5f03-117">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5f03-118">Der letzte Zeitpunkt, an dem sich der Benutzer angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="f5f03-118">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f03-119"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5f03-119"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f03-120">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f5f03-120">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5f03-121">Der letzte Zeitpunkt, zu dem der Benutzer eine Konferenz organisierte.</span><span class="sxs-lookup"><span data-stu-id="f5f03-121">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f5f03-122"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5f03-122"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f03-123">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f5f03-123">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5f03-124">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f5f03-124">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f5f03-125"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="f5f03-125"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f5f03-126">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="f5f03-126">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f5f03-127">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler als Konferenzorganisator erfuhr.</span><span class="sxs-lookup"><span data-stu-id="f5f03-127">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

