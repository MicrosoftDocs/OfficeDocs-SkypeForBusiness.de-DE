---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="0f811-102">tblADCookie in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f811-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f811-103">_**Letztes Änderungsdatum des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="0f811-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="0f811-104">tblADCookie enthält die aktuellen LDAP-Synchronisierungs Cookies (Lightweight Directory Access Protocol).</span><span class="sxs-lookup"><span data-stu-id="0f811-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="0f811-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="0f811-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f811-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="0f811-106">Column</span></span></th>
<th><span data-ttu-id="0f811-107">Typ</span><span class="sxs-lookup"><span data-stu-id="0f811-107">Type</span></span></th>
<th><span data-ttu-id="0f811-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f811-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f811-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0f811-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="0f811-110">GUID, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="0f811-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="0f811-111">Prinzipal-GUID der zu überwachenden Domäne.</span><span class="sxs-lookup"><span data-stu-id="0f811-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f811-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="0f811-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="0f811-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="0f811-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="0f811-114">Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des aktuellen Domänencontrollers, der für die Synchronisierung von Active Directory-Domänendiensten verwendet wird. Hat einen Informationswert.</span><span class="sxs-lookup"><span data-stu-id="0f811-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f811-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="0f811-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="0f811-116">Bild (binär)</span><span class="sxs-lookup"><span data-stu-id="0f811-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="0f811-117">Active Directory-Synchronisierungs Cookie</span><span class="sxs-lookup"><span data-stu-id="0f811-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f811-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="0f811-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="0f811-119">datetime</span><span class="sxs-lookup"><span data-stu-id="0f811-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="0f811-120">Zeitstempel mit der Zeilen Aktualisierungszeit.</span><span class="sxs-lookup"><span data-stu-id="0f811-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0f811-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="0f811-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="0f811-122">datetime</span><span class="sxs-lookup"><span data-stu-id="0f811-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="0f811-123">Zeit, bis die Zeile für Änderungen gesperrt ist.</span><span class="sxs-lookup"><span data-stu-id="0f811-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="0f811-124">Dies ist Teil eines Software-Interlock-Mechanismus, der sicherstellt, dass nur einer der Chat Dienste die Active Directory-Synchronisierung gleichzeitig durchführt.</span><span class="sxs-lookup"><span data-stu-id="0f811-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="0f811-125">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="0f811-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0f811-126">Spalte (n)</span><span class="sxs-lookup"><span data-stu-id="0f811-126">Column(s)</span></span></th>
<th><span data-ttu-id="0f811-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f811-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0f811-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0f811-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="0f811-129">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="0f811-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0f811-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="0f811-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="0f811-131">Fremdschlüssel mit Lookup in der Principal. prinGuid-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="0f811-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

