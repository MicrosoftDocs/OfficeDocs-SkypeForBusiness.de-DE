---
title: 'Lync Server 2013: Dialog-Tabelle'
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
ms.openlocfilehash: 2f0ef564ad1224ba9970b7cceb5db60e0eb344da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialog-table-in-lync-server-2013"></a><span data-ttu-id="1f683-102">Dialog-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f683-102">Dialog table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f683-103">_**Letztes Änderungsdatum des Themas:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1f683-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1f683-104">Die Dialog Tabelle ist eine unterstützende Tabelle; Jeder Datensatz steht für ein SIP-Dialogfeld (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="1f683-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f683-105"><strong>Spalte</strong></span><span class="sxs-lookup"><span data-stu-id="1f683-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1f683-106"><strong>Datentyp</strong></span><span class="sxs-lookup"><span data-stu-id="1f683-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1f683-107"><strong>Schlüssel/Index</strong></span><span class="sxs-lookup"><span data-stu-id="1f683-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1f683-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="1f683-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f683-109"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f683-109"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f683-110">datetime</span><span class="sxs-lookup"><span data-stu-id="1f683-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="1f683-111">Primary</span><span class="sxs-lookup"><span data-stu-id="1f683-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="1f683-112">Zeitpunkt, zu dem der Quality of Excellence (QoE)-Agent den ersten Bericht von einem Anrufer oder angerufenen erhält.</span><span class="sxs-lookup"><span data-stu-id="1f683-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="1f683-113">Wird in Verbindung mit SessionSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1f683-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f683-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1f683-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1f683-115">int</span><span class="sxs-lookup"><span data-stu-id="1f683-115">int</span></span></p></td>
<td><p><span data-ttu-id="1f683-116">Primary</span><span class="sxs-lookup"><span data-stu-id="1f683-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="1f683-117">Sequenznummer, um Sitzungen zu unterscheiden, wenn Sie dieselbe ConferenceDateTime haben.</span><span class="sxs-lookup"><span data-stu-id="1f683-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f683-118"><strong>Dialogfeld-Nr</strong></span><span class="sxs-lookup"><span data-stu-id="1f683-118"><strong>DialogID</strong></span></span></p></td>
<td><p><span data-ttu-id="1f683-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="1f683-119">varchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1f683-120">Dialog Feld-ID, die global eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="1f683-120">Dialog ID which is globally unique.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f683-121"><strong>DialogIDChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="1f683-121"><strong>DialogIDChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="1f683-122">int</span><span class="sxs-lookup"><span data-stu-id="1f683-122">int</span></span></p></td>
<td><p><span data-ttu-id="1f683-123">Index</span><span class="sxs-lookup"><span data-stu-id="1f683-123">index</span></span></p></td>
<td><p><span data-ttu-id="1f683-124">Die Prüfsumme der Dialog Feld-ID.</span><span class="sxs-lookup"><span data-stu-id="1f683-124">Checksum of the Dialog ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

