---
title: 'Lync Server 2013: Phones-Tabelle'
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
ms.openlocfilehash: cddf5eac7cc85852f4a7f61f4b746091158257e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phones-table-in-lync-server-2013"></a><span data-ttu-id="30f28-102">Phones-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="30f28-102">Phones table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="30f28-103">_**Letztes Änderungsdatum des Themas:** 2012-08-20_</span><span class="sxs-lookup"><span data-stu-id="30f28-103">_**Topic Last Modified:** 2012-08-20_</span></span>

<span data-ttu-id="30f28-104">Die Tabelle Telefone ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="30f28-104">The Phones table is a supporting table.</span></span> <span data-ttu-id="30f28-105">Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.</span><span class="sxs-lookup"><span data-stu-id="30f28-105">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="30f28-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="30f28-106">Column</span></span></th>
<th><span data-ttu-id="30f28-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="30f28-107">Data Type</span></span></th>
<th><span data-ttu-id="30f28-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="30f28-108">Key/Index</span></span></th>
<th><span data-ttu-id="30f28-109">Details</span><span class="sxs-lookup"><span data-stu-id="30f28-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="30f28-110"><strong>Telefonnummer</strong></span><span class="sxs-lookup"><span data-stu-id="30f28-110"><strong>PhoneId</strong></span></span></p></td>
<td><p><span data-ttu-id="30f28-111">int</span><span class="sxs-lookup"><span data-stu-id="30f28-111">int</span></span></p></td>
<td><p><span data-ttu-id="30f28-112">Primary</span><span class="sxs-lookup"><span data-stu-id="30f28-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="30f28-113">Eindeutige Nummer, die dieses Telefon kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="30f28-113">Unique number identifying this phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="30f28-114"><strong>PhoneUri</strong></span><span class="sxs-lookup"><span data-stu-id="30f28-114"><strong>PhoneUri</strong></span></span></p></td>
<td><p><span data-ttu-id="30f28-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="30f28-115">nvarchar(450)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="30f28-116">Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="30f28-116">Phone number.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="30f28-117"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="30f28-117"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="30f28-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="30f28-118">dateTime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="30f28-119">Zeitstempel (nur für interne Nutzung).</span><span class="sxs-lookup"><span data-stu-id="30f28-119">Time stamp (for internal use only).</span></span></p>
<p><span data-ttu-id="30f28-120">Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="30f28-120">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

