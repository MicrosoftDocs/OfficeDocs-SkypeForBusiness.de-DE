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
ms.openlocfilehash: 55df55ba8c9953a1efce25269c24b43328472d7f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529992"
---
# <a name="userstatistics-table-in-lync-server-2013"></a><span data-ttu-id="20963-102">UserStatistics-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="20963-102">UserStatistics table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20963-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="20963-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="20963-104">Die UserStatistics-Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="20963-104">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="20963-105">Jeder Datensatz in der Tabelle speichert Informationen über die Verwendung des Systems durch einen einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="20963-105">Each record in the table stores information about an individual user’s usage of the system.</span></span> <span data-ttu-id="20963-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="20963-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="20963-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="20963-107">Column</span></span></th>
<th><span data-ttu-id="20963-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="20963-108">Data Type</span></span></th>
<th><span data-ttu-id="20963-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="20963-109">Key/Index</span></span></th>
<th><span data-ttu-id="20963-110">Details</span><span class="sxs-lookup"><span data-stu-id="20963-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="20963-111"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="20963-111"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="20963-112">int</span><span class="sxs-lookup"><span data-stu-id="20963-112">int</span></span></p></td>
<td><p><span data-ttu-id="20963-113">Primary</span><span class="sxs-lookup"><span data-stu-id="20963-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="20963-114">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="20963-114">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20963-115"><strong>LastLogInTime</strong></span><span class="sxs-lookup"><span data-stu-id="20963-115"><strong>LastLogInTime</strong></span></span></p></td>
<td><p><span data-ttu-id="20963-116">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="20963-116">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20963-117">Der letzte Zeitpunkt, an dem sich der Benutzer angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="20963-117">Last time the user logged in.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20963-118"><strong>LastConfOrganizedTime</strong></span><span class="sxs-lookup"><span data-stu-id="20963-118"><strong>LastConfOrganizedTime</strong></span></span></p></td>
<td><p><span data-ttu-id="20963-119">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="20963-119">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20963-120">Der letzte Zeitpunkt, zu dem der Benutzer eine Konferenz organisierte.</span><span class="sxs-lookup"><span data-stu-id="20963-120">Last time the user organized a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="20963-121"><strong>LastCallOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="20963-121"><strong>LastCallOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="20963-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="20963-122">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20963-123">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="20963-123">Last time the user experienced a call failure.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="20963-124"><strong>LastConfOrganizerCallFailureTime</strong></span><span class="sxs-lookup"><span data-stu-id="20963-124"><strong>LastConfOrganizerCallFailureTime</strong></span></span></p></td>
<td><p><span data-ttu-id="20963-125">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="20963-125">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="20963-126">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler als Konferenzorganisator erfuhr.</span><span class="sxs-lookup"><span data-stu-id="20963-126">Last time the user experienced a call failure as a conference organizer.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

