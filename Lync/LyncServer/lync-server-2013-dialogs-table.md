---
title: 'Lync Server 2013: Dialogfelder (Tabelle)'
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
ms.openlocfilehash: 4782c8de23daa16bc43f40ac3e4bbf62c06c5e3e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="5757e-102">Dialogfelder (Tabelle) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5757e-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5757e-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5757e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5757e-104">Die Tabelle Dialoge ist eine unterstützende Tabelle, in der die Informationen zu DialogIDs für Peer-zu-Peer-Sitzungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="5757e-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5757e-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="5757e-105">Column</span></span></th>
<th><span data-ttu-id="5757e-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="5757e-106">Data Type</span></span></th>
<th><span data-ttu-id="5757e-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="5757e-107">Key/Index</span></span></th>
<th><span data-ttu-id="5757e-108">Details</span><span class="sxs-lookup"><span data-stu-id="5757e-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5757e-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="5757e-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5757e-110">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="5757e-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="5757e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="5757e-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="5757e-112">Zeitpunkt der Sitzungsanforderung; wird in Verbindung mit SessionIDSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5757e-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5757e-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5757e-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5757e-114">int</span><span class="sxs-lookup"><span data-stu-id="5757e-114">int</span></span></p></td>
<td><p><span data-ttu-id="5757e-115">Primary</span><span class="sxs-lookup"><span data-stu-id="5757e-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="5757e-116">ID zur Identifikation der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="5757e-116">ID number to identify the session.</span></span> <span data-ttu-id="5757e-117">Wird in Verbindung mit SessionID verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="5757e-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5757e-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="5757e-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="5757e-119">int</span><span class="sxs-lookup"><span data-stu-id="5757e-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5757e-120">Prüfsumme der externen-Nr.</span><span class="sxs-lookup"><span data-stu-id="5757e-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="5757e-121">Dieses Feld wird verwendet, um die Geschwindigkeit der Datenbanksuche zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="5757e-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5757e-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="5757e-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="5757e-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="5757e-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="5757e-124">SIP-Dialogfeld-ID, gespeichert als Binärdatei.</span><span class="sxs-lookup"><span data-stu-id="5757e-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="5757e-125">Das Format der Binärdatei lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5757e-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="5757e-126">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="5757e-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="5757e-127">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="5757e-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

