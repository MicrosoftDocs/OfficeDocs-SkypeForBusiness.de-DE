---
title: 'Lync Server 2013: SIPResponseMetaData-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIPResponseMetaData table
ms:assetid: cf723737-4a75-4352-829b-f4954aa59716
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205294(v=OCS.15)
ms:contentKeyID: 48185510
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0143bdd74b955f2cba5f68540be7c969f748aa47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181798"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="e9e55-102">SIPResponseMetaData-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9e55-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9e55-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e9e55-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e9e55-p101">Die SIPResponseMetaData-Tabelle enthält eine Liste der SIP-Antwortcodes und die Klassifizierung und Definition für jeden dieser Codes. Diese Codes werden als Reaktion auf Ereignisse generiert, die SIP-Geräte und SIP-Kommunikationssitzungen betreffen. Beispielsweise wird der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung ausstellt, aber der Server diese Anforderung ablehnt.</span><span class="sxs-lookup"><span data-stu-id="e9e55-p101">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="e9e55-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e9e55-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9e55-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="e9e55-107">Column</span></span></th>
<th><span data-ttu-id="e9e55-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="e9e55-108">Data Type</span></span></th>
<th><span data-ttu-id="e9e55-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="e9e55-109">Key/Index</span></span></th>
<th><span data-ttu-id="e9e55-110">Details</span><span class="sxs-lookup"><span data-stu-id="e9e55-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9e55-111"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e9e55-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e55-112">int</span><span class="sxs-lookup"><span data-stu-id="e9e55-112">int</span></span></p></td>
<td><p><span data-ttu-id="e9e55-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e9e55-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e9e55-114">Numerischer Wert, der den SIP-Antwortcode repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="e9e55-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9e55-115"><strong>Klasse</strong></span><span class="sxs-lookup"><span data-stu-id="e9e55-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e55-116">int</span><span class="sxs-lookup"><span data-stu-id="e9e55-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9e55-p102">Allgemeine Klassifizierung für den Antwortcode. Es gibt folgende Klassifizierungen:</span><span class="sxs-lookup"><span data-stu-id="e9e55-p102">General classification for the response code. Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="e9e55-119">1 – Informative Antworten</span><span class="sxs-lookup"><span data-stu-id="e9e55-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="e9e55-120">2 – Erfolgreiche Antworten</span><span class="sxs-lookup"><span data-stu-id="e9e55-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="e9e55-121">3 – Umleitungsantworten</span><span class="sxs-lookup"><span data-stu-id="e9e55-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="e9e55-122">4 – Clientfehlerantworten</span><span class="sxs-lookup"><span data-stu-id="e9e55-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="e9e55-123">5--Server Fehlerantworten</span><span class="sxs-lookup"><span data-stu-id="e9e55-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="e9e55-124">6 – Globale Fehlerantworten</span><span class="sxs-lookup"><span data-stu-id="e9e55-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9e55-125"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="e9e55-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="e9e55-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e9e55-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9e55-p103">Beschreibung des SIP-Antwortcodes. Beispielsweise gibt es für den Antwortcode 181 die folgende Beschreibung:</span><span class="sxs-lookup"><span data-stu-id="e9e55-p103">Description of the SIP response code. For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="e9e55-129">Anruf wird weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="e9e55-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

