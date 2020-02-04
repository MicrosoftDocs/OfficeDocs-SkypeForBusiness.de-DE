---
title: 'Lync Server 2013: User-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User table
ms:assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398505(v=OCS.15)
ms:contentKeyID: 48184437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8256dec91c93ca6e8f0fd3cfff65280a417324e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744445"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-table-in-lync-server-2013"></a><span data-ttu-id="f571e-102">User-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f571e-102">User table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f571e-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f571e-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f571e-104">Die Tabelle Benutzer ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="f571e-104">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="f571e-105">Jeder Datensatz in der Tabelle steht für einen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f571e-105">Each record in the table represents one user.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f571e-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f571e-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f571e-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f571e-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f571e-110"><strong>UserKey</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-110"><strong>UserKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f571e-111">int</span><span class="sxs-lookup"><span data-stu-id="f571e-111">int</span></span></p></td>
<td><p><span data-ttu-id="f571e-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f571e-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f571e-113">Eindeutige Nummer, die diesen Benutzer kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f571e-113">Unique number identifying this user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f571e-114"><strong>URI</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-114"><strong>URI</strong></span></span></p></td>
<td><p><span data-ttu-id="f571e-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f571e-115">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f571e-116">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="f571e-116">Unique</span></span></p></td>
<td><p><span data-ttu-id="f571e-117">URI-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f571e-117">URI string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f571e-118"><strong>URIType</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-118"><strong>URIType</strong></span></span></p></td>
<td><p><span data-ttu-id="f571e-119">int</span><span class="sxs-lookup"><span data-stu-id="f571e-119">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f571e-120">1 ist ein Unbekannter URI-Typ.</span><span class="sxs-lookup"><span data-stu-id="f571e-120">1 is unknown URI type.</span></span></p>
<p><span data-ttu-id="f571e-121">2 ist ein Benutzer-URI.</span><span class="sxs-lookup"><span data-stu-id="f571e-121">2 is user URI.</span></span></p>
<p><span data-ttu-id="f571e-122">4 ist Konferenz-URI.</span><span class="sxs-lookup"><span data-stu-id="f571e-122">4 is conference URI.</span></span></p>
<p><span data-ttu-id="f571e-123">8 ist ein Telefon-URI.</span><span class="sxs-lookup"><span data-stu-id="f571e-123">8 is phone URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f571e-124"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-124"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f571e-125">int</span><span class="sxs-lookup"><span data-stu-id="f571e-125">int</span></span></p></td>
<td><p><span data-ttu-id="f571e-126">Fremd</span><span class="sxs-lookup"><span data-stu-id="f571e-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f571e-127">Der Mandant des Benutzers, auf den die Mandantentabelle verweist.</span><span class="sxs-lookup"><span data-stu-id="f571e-127">Tenant of the user, referenced from tenant table.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f571e-128"><strong>LastPoorCallTime</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-128"><strong>LastPoorCallTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f571e-129">datetime</span><span class="sxs-lookup"><span data-stu-id="f571e-129">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f571e-130">Letzter Zeitstempel, wenn der Benutzer einen schlechten Audioanruf hatte.</span><span class="sxs-lookup"><span data-stu-id="f571e-130">Latest time stamp when the user had a poor audio call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f571e-131"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="f571e-131"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="f571e-132">datetime</span><span class="sxs-lookup"><span data-stu-id="f571e-132">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f571e-133">Nur für interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="f571e-133">For internal use only.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

