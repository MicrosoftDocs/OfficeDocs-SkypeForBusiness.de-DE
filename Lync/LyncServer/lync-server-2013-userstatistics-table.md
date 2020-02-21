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
ms.openlocfilehash: 876d861e62014738816c02e2a6c2628f5dd46fc0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212878"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="3db35-102">UserStatistics-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3db35-102">UserStatistics table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3db35-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3db35-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3db35-104">Die UserStatistics-Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3db35-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="3db35-105">Jeder Datensatz in der Tabelle speichert Informationen über die Verwendung des Systems durch einen einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3db35-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="3db35-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3db35-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3db35-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="3db35-107">Column</span></span></th>
<th><span data-ttu-id="3db35-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="3db35-108">Data Type</span></span></th>
<th><span data-ttu-id="3db35-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="3db35-109">Key/Index</span></span></th>
<th><span data-ttu-id="3db35-110">Details</span><span class="sxs-lookup"><span data-stu-id="3db35-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3db35-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="3db35-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="3db35-112">int</span><span class="sxs-lookup"><span data-stu-id="3db35-112">int</span></span></p></td>
<td><p><span data-ttu-id="3db35-113">Primary</span><span class="sxs-lookup"><span data-stu-id="3db35-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3db35-114">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3db35-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3db35-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="3db35-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3db35-116">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="3db35-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3db35-117">Der letzte Zeitpunkt, an dem sich der Benutzer angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="3db35-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3db35-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="3db35-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3db35-119">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="3db35-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3db35-120">Der letzte Zeitpunkt, zu dem der Benutzer eine Konferenz organisierte.</span><span class="sxs-lookup"><span data-stu-id="3db35-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3db35-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="3db35-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3db35-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="3db35-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3db35-123">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="3db35-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3db35-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="3db35-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3db35-125">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="3db35-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3db35-126">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler als Konferenzorganisator erfuhr.</span><span class="sxs-lookup"><span data-stu-id="3db35-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

