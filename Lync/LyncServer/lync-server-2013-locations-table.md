---
title: 'Lync Server 2013: Locations-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6b26f8c30c0d26fd265d95542b79f919153bc15
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="52925-102">Locations-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52925-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52925-103">_**Letztes Änderungsdatum des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="52925-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="52925-104">Jeder Datensatz steht in einem Notruf wie ein E9-1-1-Anruf für einen standortbezug.</span><span class="sxs-lookup"><span data-stu-id="52925-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52925-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="52925-105">Column</span></span></th>
<th><span data-ttu-id="52925-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="52925-106">Data Type</span></span></th>
<th><span data-ttu-id="52925-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="52925-107">Key/Index</span></span></th>
<th><span data-ttu-id="52925-108">Details</span><span class="sxs-lookup"><span data-stu-id="52925-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52925-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="52925-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="52925-110">datetime</span><span class="sxs-lookup"><span data-stu-id="52925-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="52925-111">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="52925-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="52925-112">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="52925-112">Time of session request.</span></span> <span data-ttu-id="52925-113">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="52925-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="52925-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52925-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52925-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="52925-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="52925-116">int</span><span class="sxs-lookup"><span data-stu-id="52925-116">int</span></span></p></td>
<td><p><span data-ttu-id="52925-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="52925-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="52925-118">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="52925-118">ID number to identify the session.</span></span> <span data-ttu-id="52925-119">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="52925-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="52925-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="52925-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52925-121"><strong>Standort</strong></span><span class="sxs-lookup"><span data-stu-id="52925-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="52925-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="52925-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="52925-123">Ort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="52925-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

