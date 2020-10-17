---
title: 'Lync Server 2013: Dialogfelder (Tabelle)'
description: 'Lync Server 2013: Dialogs-Tabelle.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dialogs table
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425954(v=OCS.15)
ms:contentKeyID: 48184001
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2c9cf9ec59fc48f7f5ffc6232980e3f8aa68c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559701"
---
# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="b3ab0-103">Dialogfelder (Tabelle) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3ab0-103">Dialogs table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3ab0-104">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b3ab0-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b3ab0-105">Die Tabelle Dialoge ist eine unterstützende Tabelle, in der die Informationen zu DialogIDs für Peer-zu-Peer-Sitzungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="b3ab0-105">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3ab0-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="b3ab0-106">Column</span></span></th>
<th><span data-ttu-id="b3ab0-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="b3ab0-107">Data Type</span></span></th>
<th><span data-ttu-id="b3ab0-108">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="b3ab0-108">Key/Index</span></span></th>
<th><span data-ttu-id="b3ab0-109">Details</span><span class="sxs-lookup"><span data-stu-id="b3ab0-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3ab0-110"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="b3ab0-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ab0-111">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="b3ab0-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3ab0-112">Primary</span><span class="sxs-lookup"><span data-stu-id="b3ab0-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="b3ab0-113">Zeitpunkt der Sitzungsanforderung; wird in Verbindung mit SessionIDSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b3ab0-113">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3ab0-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b3ab0-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ab0-115">int</span><span class="sxs-lookup"><span data-stu-id="b3ab0-115">int</span></span></p></td>
<td><p><span data-ttu-id="b3ab0-116">Primary</span><span class="sxs-lookup"><span data-stu-id="b3ab0-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="b3ab0-117">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="b3ab0-117">ID number to identify the session.</span></span> <span data-ttu-id="b3ab0-118">Wird in Verbindung mit SessionID verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="b3ab0-118">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3ab0-119"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="b3ab0-119"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ab0-120">int</span><span class="sxs-lookup"><span data-stu-id="b3ab0-120">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3ab0-121">Prüfsumme der externen-Nr.</span><span class="sxs-lookup"><span data-stu-id="b3ab0-121">Checksum of the ExternalID.</span></span> <span data-ttu-id="b3ab0-122">Dieses Feld wird verwendet, um die Geschwindigkeit der Datenbanksuche zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="b3ab0-122">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3ab0-123"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="b3ab0-123"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="b3ab0-124">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="b3ab0-124">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="b3ab0-125">SIP-Dialogfeld-ID, gespeichert als Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="b3ab0-125">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="b3ab0-126">Das Format der Binärdatei lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="b3ab0-126">The format of the binary is:</span></span></p>
<p><span data-ttu-id="b3ab0-127">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="b3ab0-127">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="b3ab0-128">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="b3ab0-128">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

