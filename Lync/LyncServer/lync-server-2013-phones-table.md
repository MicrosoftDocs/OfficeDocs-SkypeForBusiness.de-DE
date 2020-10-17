---
title: 'Lync Server 2013: Phones-Tabelle'
description: 'Lync Server 2013: Phones-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Phones table
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425923(v=OCS.15)
ms:contentKeyID: 48183996
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c62fffecd2442b79aefde77eb037dca4bffc9d4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554811"
---
# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="a09d5-103">Phones-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a09d5-103">Phones table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a09d5-104">_**Letztes Änderungsstand des Themas:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="a09d5-104">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="a09d5-105">Die Phones-Tabelle ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a09d5-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="a09d5-106">Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="a09d5-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a09d5-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="a09d5-107">Column</span></span></th>
<th><span data-ttu-id="a09d5-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="a09d5-108">Data Type</span></span></th>
<th><span data-ttu-id="a09d5-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="a09d5-109">Key/Index</span></span></th>
<th><span data-ttu-id="a09d5-110">Details</span><span class="sxs-lookup"><span data-stu-id="a09d5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a09d5-111"><strong>Telefonnummer</strong></span><span class="sxs-lookup"><span data-stu-id="a09d5-111"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="a09d5-112">int</span><span class="sxs-lookup"><span data-stu-id="a09d5-112">int</span></span></p></td>
<td><p><span data-ttu-id="a09d5-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a09d5-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="a09d5-114">Eindeutige Nummer, die dieses Telefon identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a09d5-114">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a09d5-115"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="a09d5-115"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="a09d5-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a09d5-116">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="a09d5-117">Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="a09d5-117">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a09d5-118"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="a09d5-118"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="a09d5-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="a09d5-119">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="a09d5-120">Zeitstempel (nur für die interne Verwendung).</span><span class="sxs-lookup"><span data-stu-id="a09d5-120">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="a09d5-121">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="a09d5-121">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

