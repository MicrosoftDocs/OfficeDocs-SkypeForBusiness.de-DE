---
title: 'Lync Server 2013: Locations-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Locations table
ms:assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398596(v=OCS.15)
ms:contentKeyID: 48184579
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2d16ffd08184a650f993d175239f5aff72b8b3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="locations-table-in-lync-server-2013"></a><span data-ttu-id="ee144-102">Locations-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee144-102">Locations table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee144-103">_**Letztes Änderungsdatum des Themas:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="ee144-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="ee144-104">Jeder Datensatz steht in einem Notruf wie ein E9-1-1-Anruf für einen standortbezug.</span><span class="sxs-lookup"><span data-stu-id="ee144-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ee144-105">Spalte</span><span class="sxs-lookup"><span data-stu-id="ee144-105">Column</span></span></th>
<th><span data-ttu-id="ee144-106">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ee144-106">Data Type</span></span></th>
<th><span data-ttu-id="ee144-107">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="ee144-107">Key/Index</span></span></th>
<th><span data-ttu-id="ee144-108">Details</span><span class="sxs-lookup"><span data-stu-id="ee144-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ee144-109"><strong>SessionID</strong></span><span class="sxs-lookup"><span data-stu-id="ee144-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ee144-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ee144-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ee144-111">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="ee144-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ee144-112">Uhrzeit der Sitzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="ee144-112">Time of session request.</span></span> <span data-ttu-id="ee144-113">Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ee144-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ee144-114">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ee144-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ee144-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ee144-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ee144-116">int</span><span class="sxs-lookup"><span data-stu-id="ee144-116">int</span></span></p></td>
<td><p><span data-ttu-id="ee144-117">Primär, fremd</span><span class="sxs-lookup"><span data-stu-id="ee144-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ee144-118">Die ID-Nummer, um die Sitzung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ee144-118">ID number to identify the session.</span></span> <span data-ttu-id="ee144-119">Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ee144-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="ee144-120">Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="ee144-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ee144-121"><strong>Standort</strong></span><span class="sxs-lookup"><span data-stu-id="ee144-121"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="ee144-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="ee144-122">nvarchar(max)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ee144-123">Ort des Notrufs.</span><span class="sxs-lookup"><span data-stu-id="ee144-123">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

