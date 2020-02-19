---
title: 'Lync Server 2013: UserStatistics-Tabelle'
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
ms.openlocfilehash: 2758b52b44a58095203deb7e70387934f723ee97
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140688"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="fe52f-102">UserStatistics-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe52f-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe52f-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fe52f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fe52f-104">Die UserStatistics-Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fe52f-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="fe52f-105">Jeder Datensatz in der Tabelle speichert Informationen über die Verwendung des Systems durch einen einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="fe52f-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="fe52f-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fe52f-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fe52f-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="fe52f-107">Column</span></span></th>
<th><span data-ttu-id="fe52f-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="fe52f-108">Data Type</span></span></th>
<th><span data-ttu-id="fe52f-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="fe52f-109">Key/Index</span></span></th>
<th><span data-ttu-id="fe52f-110">Details</span><span class="sxs-lookup"><span data-stu-id="fe52f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fe52f-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="fe52f-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="fe52f-112">int</span><span class="sxs-lookup"><span data-stu-id="fe52f-112">int</span></span></p></td>
<td><p><span data-ttu-id="fe52f-113">Primary</span><span class="sxs-lookup"><span data-stu-id="fe52f-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="fe52f-114">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="fe52f-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe52f-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe52f-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe52f-116">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fe52f-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe52f-117">Der letzte Zeitpunkt, an dem sich der Benutzer angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="fe52f-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe52f-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe52f-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe52f-119">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fe52f-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe52f-120">Der letzte Zeitpunkt, zu dem der Benutzer eine Konferenz organisierte.</span><span class="sxs-lookup"><span data-stu-id="fe52f-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fe52f-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe52f-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe52f-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fe52f-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe52f-123">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="fe52f-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fe52f-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="fe52f-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fe52f-125">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="fe52f-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fe52f-126">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler als Konferenzorganisator erfuhr.</span><span class="sxs-lookup"><span data-stu-id="fe52f-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

