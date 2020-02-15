---
title: 'Lync Server 2013: tblADCookie'
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
ms.openlocfilehash: 1f733397483693ad4c18418f3e82b9f99cfa640f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="65ecc-102">tblADCookie in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65ecc-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65ecc-103">_**Letztes Änderungsstand des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="65ecc-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="65ecc-104">"tblADCookie" enthält die aktuellen Cookies für die LDAP-Synchronisierung (Lightweight Directory Access Protocol).</span><span class="sxs-lookup"><span data-stu-id="65ecc-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="65ecc-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="65ecc-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65ecc-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="65ecc-106">Column</span></span></th>
<th><span data-ttu-id="65ecc-107">Typ</span><span class="sxs-lookup"><span data-stu-id="65ecc-107">Type</span></span></th>
<th><span data-ttu-id="65ecc-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65ecc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65ecc-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="65ecc-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="65ecc-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="65ecc-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="65ecc-111">Prinzipal-GUID der überwachten Domäne.</span><span class="sxs-lookup"><span data-stu-id="65ecc-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ecc-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="65ecc-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="65ecc-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="65ecc-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="65ecc-114">Vollqualifizierter Domänenname (FQDN) des aktuellen Domänencontrollers, der für Active Directory-Domänendienste Synchronisierung verwendet wird. Weist einen Informationswert auf.</span><span class="sxs-lookup"><span data-stu-id="65ecc-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ecc-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="65ecc-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="65ecc-116">image (binary)</span><span class="sxs-lookup"><span data-stu-id="65ecc-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="65ecc-117">Cookie für die Active Directory-Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="65ecc-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ecc-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="65ecc-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="65ecc-119">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="65ecc-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="65ecc-120">Zeitstempel der Aktualisierungszeit der Zeile.</span><span class="sxs-lookup"><span data-stu-id="65ecc-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65ecc-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="65ecc-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="65ecc-122">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="65ecc-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="65ecc-p101">Zeitpunkt bis zu dem die Zeile für Änderungen gesperrt ist. Dies ist Teil eines Sperrmechanismus der Software, durch den sichergestellt ist, dass nur jeweils ein Chatdienst die Active Directory-Synchronisierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="65ecc-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="65ecc-125">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="65ecc-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65ecc-126">Spalte (n)</span><span class="sxs-lookup"><span data-stu-id="65ecc-126">Column(s)</span></span></th>
<th><span data-ttu-id="65ecc-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65ecc-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65ecc-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="65ecc-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="65ecc-129">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="65ecc-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65ecc-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="65ecc-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="65ecc-131">Fremdschlüssel mit Abfrage der Principal.prinGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="65ecc-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

