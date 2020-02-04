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
ms.openlocfilehash: 1fcd6cb462bd64f6fdcdbae93cfb733de0639898
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sipresponsemetadata-table-in-lync-server-2013"></a><span data-ttu-id="b99ba-102">SIPResponseMetaData-Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b99ba-102">SIPResponseMetaData table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b99ba-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b99ba-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b99ba-104">Das SIPResponseMetaDataTable enthält eine Liste der SIP-Antwortcodes sowie die Klassifizierung und Definition der einzelnen Codes.</span><span class="sxs-lookup"><span data-stu-id="b99ba-104">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="b99ba-105">Diese Codes werden als Reaktion auf Ereignisse generiert, die sich auf SIP-Geräte und SIP-Kommunikationssitzungen auswirken. So wird beispielsweise der Antwortcode 403 generiert, wenn ein SIP-Gerät eine Anforderung stellt, aber der Server lehnt die Anerkennung dieser Anforderung ab.</span><span class="sxs-lookup"><span data-stu-id="b99ba-105">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>

<span data-ttu-id="b99ba-106">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b99ba-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b99ba-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="b99ba-107">Column</span></span></th>
<th><span data-ttu-id="b99ba-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b99ba-108">Data Type</span></span></th>
<th><span data-ttu-id="b99ba-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="b99ba-109">Key/Index</span></span></th>
<th><span data-ttu-id="b99ba-110">Details</span><span class="sxs-lookup"><span data-stu-id="b99ba-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b99ba-111"><strong>Response Code</strong></span><span class="sxs-lookup"><span data-stu-id="b99ba-111"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b99ba-112">int</span><span class="sxs-lookup"><span data-stu-id="b99ba-112">int</span></span></p></td>
<td><p><span data-ttu-id="b99ba-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b99ba-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="b99ba-114">Numerischer Wert, der den SIP-Antwortcode darstellt.</span><span class="sxs-lookup"><span data-stu-id="b99ba-114">Numeric value that represents the SIP response code.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b99ba-115"><strong>Klasse</strong></span><span class="sxs-lookup"><span data-stu-id="b99ba-115"><strong>Class</strong></span></span></p></td>
<td><p><span data-ttu-id="b99ba-116">int</span><span class="sxs-lookup"><span data-stu-id="b99ba-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b99ba-117">Allgemeine Klassifizierung für den Antwortcode.</span><span class="sxs-lookup"><span data-stu-id="b99ba-117">General classification for the response code.</span></span> <span data-ttu-id="b99ba-118">Zu den Klassifizierungen gehören:</span><span class="sxs-lookup"><span data-stu-id="b99ba-118">Classifications include:</span></span></p>
<ul>
<li><p><span data-ttu-id="b99ba-119">1 – Informations Antworten</span><span class="sxs-lookup"><span data-stu-id="b99ba-119">1 – Informational Responses</span></span></p></li>
<li><p><span data-ttu-id="b99ba-120">2 – erfolgreiche Antworten</span><span class="sxs-lookup"><span data-stu-id="b99ba-120">2 – Successful Responses</span></span></p></li>
<li><p><span data-ttu-id="b99ba-121">3 – Umleitungsantworten</span><span class="sxs-lookup"><span data-stu-id="b99ba-121">3 – Redirection Responses</span></span></p></li>
<li><p><span data-ttu-id="b99ba-122">4 – Antworten auf Client Fehler</span><span class="sxs-lookup"><span data-stu-id="b99ba-122">4 – Client Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="b99ba-123">5 – Server Fehlerantworten</span><span class="sxs-lookup"><span data-stu-id="b99ba-123">5 -- Server Failure Responses</span></span></p></li>
<li><p><span data-ttu-id="b99ba-124">6 – globale Fehlerantwort</span><span class="sxs-lookup"><span data-stu-id="b99ba-124">6 – Global Failure Response</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b99ba-125"><strong>Beschreibung</strong></span><span class="sxs-lookup"><span data-stu-id="b99ba-125"><strong>Description</strong></span></span></p></td>
<td><p><span data-ttu-id="b99ba-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="b99ba-126">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b99ba-127">Beschreibung des SIP-Antwortcodes.</span><span class="sxs-lookup"><span data-stu-id="b99ba-127">Description of the SIP response code.</span></span> <span data-ttu-id="b99ba-128">Antwortcode 181 weist beispielsweise die folgende Beschreibung auf:</span><span class="sxs-lookup"><span data-stu-id="b99ba-128">For example, response code 181 has the following description:</span></span></p>
<p><span data-ttu-id="b99ba-129">Anruf wird weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="b99ba-129">Call Is Being Forwarded</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

