---
title: 'Lync Server 2013: Dialogs-Tabelle'
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
ms.openlocfilehash: 326ecac8df81eeba11ed29ff9f1968b681cdb98f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dialogs-table-in-lync-server-2013"></a><span data-ttu-id="fb075-102">Dialogs-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fb075-102">Dialogs table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb075-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fb075-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fb075-104">Die Tabelle Dialogfelder ist eine unterstützende Tabelle, in der die Informationen zu DialogIDs für Peer-to-Peer-Sitzungen gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="fb075-104">The Dialogs table is a supporting table that stores the information about DialogIDs for peer-to-peer sessions.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb075-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="fb075-105">Column</span></span></th>
<th><span data-ttu-id="fb075-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="fb075-106">Data Type</span></span></th>
<th><span data-ttu-id="fb075-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="fb075-107">Key/Index</span></span></th>
<th><span data-ttu-id="fb075-108">Details</span><span class="sxs-lookup"><span data-stu-id="fb075-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb075-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="fb075-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fb075-110">datetime</span><span class="sxs-lookup"><span data-stu-id="fb075-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="fb075-111">Primary</span><span class="sxs-lookup"><span data-stu-id="fb075-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="fb075-112">Uhrzeit der Sitzungsanforderung; wird in Verbindung mit SessionIDSeq verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fb075-112">Time of session request; used in conjunction with SessionIDSeq to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb075-113"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fb075-113"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fb075-114">int</span><span class="sxs-lookup"><span data-stu-id="fb075-114">int</span></span></p></td>
<td><p><span data-ttu-id="fb075-115">Primary</span><span class="sxs-lookup"><span data-stu-id="fb075-115">Primary</span></span></p></td>
<td><p><span data-ttu-id="fb075-116">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fb075-116">ID number to identify the session.</span></span> <span data-ttu-id="fb075-117">Wird in Verbindung mit SessionID-Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="fb075-117">Used in conjunction with SessionIDTime to uniquely identify a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb075-118"><strong>ExternalChecksum</strong></span><span class="sxs-lookup"><span data-stu-id="fb075-118"><strong>ExternalChecksum</strong></span></span></p></td>
<td><p><span data-ttu-id="fb075-119">int</span><span class="sxs-lookup"><span data-stu-id="fb075-119">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fb075-120">Prüfsumme der externen-Nr.</span><span class="sxs-lookup"><span data-stu-id="fb075-120">Checksum of the ExternalID.</span></span> <span data-ttu-id="fb075-121">Dieses Feld wird verwendet, um die Geschwindigkeit von Datenbanksuchen zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="fb075-121">This field is used to increase the speed of database searches.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb075-122"><strong>ExternalId</strong></span><span class="sxs-lookup"><span data-stu-id="fb075-122"><strong>ExternalId</strong></span></span></p></td>
<td><p><span data-ttu-id="fb075-123">varbinary (775)</span><span class="sxs-lookup"><span data-stu-id="fb075-123">varbinary(775)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fb075-124">SIP-Dialogfeld-ID, als Binärdatei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fb075-124">SIP dialog ID, stored as a binary.</span></span> <span data-ttu-id="fb075-125">Das Format der Binärdatei lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fb075-125">The format of the binary is:</span></span></p>
<p><span data-ttu-id="fb075-126">Dialogfeld; from-Tag; to-Tag</span><span class="sxs-lookup"><span data-stu-id="fb075-126">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="fb075-127">Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:</span><span class="sxs-lookup"><span data-stu-id="fb075-127">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

