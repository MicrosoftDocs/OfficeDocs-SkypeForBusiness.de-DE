---
title: 'Lync Server 2013: tblADCookie'
description: 'Lync Server 2013: tblADCookie.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c3dde3730ede07b204a473c7fe0a5ab68054d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573721"
---
# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="2eaa4-103">tblADCookie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eaa4-103">tblADCookie in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eaa4-104">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="2eaa4-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="2eaa4-105">"tblADCookie" enthält die aktuellen Cookies für die LDAP-Synchronisierung (Lightweight Directory Access Protocol).</span><span class="sxs-lookup"><span data-stu-id="2eaa4-105">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="2eaa4-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="2eaa4-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2eaa4-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="2eaa4-107">Column</span></span></th>
<th><span data-ttu-id="2eaa4-108">Typ</span><span class="sxs-lookup"><span data-stu-id="2eaa4-108">Type</span></span></th>
<th><span data-ttu-id="2eaa4-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2eaa4-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2eaa4-110">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2eaa4-110">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-111">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="2eaa4-111">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-112">Prinzipal-GUID der überwachten Domäne.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-112">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2eaa4-113">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="2eaa4-113">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-114">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="2eaa4-114">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-115">Vollqualifizierter Domänenname (FQDN) des aktuellen Domänencontrollers, der für Active Directory-Domänendienste Synchronisierung verwendet wird. Weist einen Informationswert auf.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-115">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2eaa4-116">adcContent</span><span class="sxs-lookup"><span data-stu-id="2eaa4-116">adcContent</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-117">image (binary)</span><span class="sxs-lookup"><span data-stu-id="2eaa4-117">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-118">Cookie für die Active Directory-Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-118">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2eaa4-119">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="2eaa4-119">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-120">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="2eaa4-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-121">Zeitstempel der Aktualisierungszeit der Zeile.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-121">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2eaa4-122">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="2eaa4-122">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-123">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="2eaa4-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-p101">Zeitpunkt bis zu dem die Zeile für Änderungen gesperrt ist. Dies ist Teil eines Sperrmechanismus der Software, durch den sichergestellt ist, dass nur jeweils ein Chatdienst die Active Directory-Synchronisierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="2eaa4-126">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="2eaa4-126">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2eaa4-127">Spalte (n)</span><span class="sxs-lookup"><span data-stu-id="2eaa4-127">Column(s)</span></span></th>
<th><span data-ttu-id="2eaa4-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2eaa4-128">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2eaa4-129">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2eaa4-129">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-130">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="2eaa4-130">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2eaa4-131">prinGuid</span><span class="sxs-lookup"><span data-stu-id="2eaa4-131">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="2eaa4-132">Fremdschlüssel mit Abfrage der Principal.prinGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2eaa4-132">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

