---
title: 'Lync Server 2013: Dialog Feld Tabelle'
description: 'Lync Server 2013: Dialog Feld Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialog table
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398313(v=OCS.15)
ms:contentKeyID: 48184068
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ae93b8ca9f1146b7dc164803f27cbeeadc66777
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559721"
---
# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="19640-103">Dialog Tabelle in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19640-103">Dialog table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19640-104">_**Letztes Änderungsstand des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="19640-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="19640-105">Bei der Dialog-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird; jeder Datensatz steht für einen SIP-Dialog (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="19640-105">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19640-106"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="19640-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="19640-107"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="19640-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="19640-108"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="19640-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="19640-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="19640-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19640-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="19640-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="19640-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="19640-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="19640-112">Primary</span><span class="sxs-lookup"><span data-stu-id="19640-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="19640-p101">Zeitpunkt, zu dem der QoE-Agent (Quality of Excellence) den ersten Bericht von einem Anrufer oder Angerufenen empfängt. Wird zusammen mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="19640-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19640-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="19640-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="19640-116">int</span><span class="sxs-lookup"><span data-stu-id="19640-116">int</span></span></p></td>
<td><p><span data-ttu-id="19640-117">Primary</span><span class="sxs-lookup"><span data-stu-id="19640-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="19640-118">Sequenznummer zur Unterscheidung von Sitzungen, die dieselbe ConferenceDateTime aufweisen.</span><span class="sxs-lookup"><span data-stu-id="19640-118">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19640-119"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="19640-119"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="19640-120">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="19640-120">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="19640-121">Dialog-ID, die global eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="19640-121">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19640-122"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="19640-122"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="19640-123">int</span><span class="sxs-lookup"><span data-stu-id="19640-123">int</span></span></p></td>
<td><p><span data-ttu-id="19640-124">Index</span><span class="sxs-lookup"><span data-stu-id="19640-124">index</span></span></p></td>
<td><p><span data-ttu-id="19640-125">Prüfsumme der Dialog-ID.</span><span class="sxs-lookup"><span data-stu-id="19640-125">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

