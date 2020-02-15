---
title: 'Lync Server 2013: Client Versions-Ansicht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ClientVersions view
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49733825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a7e62fbf56d270c6d2d0c65415dc28dd30e4449
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clientversions-view-in-lync-server-2013"></a><span data-ttu-id="29262-102">Client Versions-Ansicht in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="29262-102">ClientVersions view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29262-103">_**Letztes Änderungsstand des Themas:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="29262-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="29262-104">In der Client Versions-Ansicht werden Informationen zu den verschiedenen Clienttypen und-Versionen gespeichert, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="29262-104">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="29262-105">Jeder Datensatz in der Ansicht stellt eine Client Version dar.</span><span class="sxs-lookup"><span data-stu-id="29262-105">Each record in the view represents one client version.</span></span> <span data-ttu-id="29262-106">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="29262-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="29262-107">Es kann mehrere Datensätze für bestimmte Spalten geben.</span><span class="sxs-lookup"><span data-stu-id="29262-107">There may be multiple records for certain columns.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29262-108">Spalte</span><span class="sxs-lookup"><span data-stu-id="29262-108">Column</span></span></th>
<th><span data-ttu-id="29262-109">Datentyp</span><span class="sxs-lookup"><span data-stu-id="29262-109">Data Type</span></span></th>
<th><span data-ttu-id="29262-110">Details</span><span class="sxs-lookup"><span data-stu-id="29262-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29262-111"><strong>VersionId</strong></span><span class="sxs-lookup"><span data-stu-id="29262-111"><strong>VersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="29262-112">int</span><span class="sxs-lookup"><span data-stu-id="29262-112">int</span></span></p></td>
<td><p><span data-ttu-id="29262-113">Eindeutige Zahl, die den Clienttyp und die Clientversion identifiziert.</span><span class="sxs-lookup"><span data-stu-id="29262-113">Unique number identifying this client type and version.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29262-114"><strong>Version</strong></span><span class="sxs-lookup"><span data-stu-id="29262-114"><strong>Version</strong></span></span></p></td>
<td><p><span data-ttu-id="29262-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29262-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29262-116">Stellt den Benutzer-Agent dar.</span><span class="sxs-lookup"><span data-stu-id="29262-116">Represents the user agent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29262-117"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="29262-117"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="29262-118">int</span><span class="sxs-lookup"><span data-stu-id="29262-118">int</span></span></p></td>
<td><p><span data-ttu-id="29262-119">Typ des Clients.</span><span class="sxs-lookup"><span data-stu-id="29262-119">Type of client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29262-120"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="29262-120"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="29262-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="29262-121">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="29262-122">Kategorie, zu der der Client gehört.</span><span class="sxs-lookup"><span data-stu-id="29262-122">Category that the client belongs to.</span></span> <span data-ttu-id="29262-123">Beispielsweise gehört der Client Conferencing_Attendant_1 .0 zu ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="29262-123">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

