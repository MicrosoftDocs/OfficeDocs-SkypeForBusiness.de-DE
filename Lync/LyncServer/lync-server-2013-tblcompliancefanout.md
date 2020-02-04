---
title: 'Lync Server 2013: tblComplianceFanout'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceFanout
ms:assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615050(v=OCS.15)
ms:contentKeyID: 48185828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196911f4fdcb7f2713ed25cca114ff9954b0c6e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcompliancefanout-in-lync-server-2013"></a><span data-ttu-id="508d8-102">tblComplianceFanout in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="508d8-102">tblComplianceFanout in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="508d8-103">_**Letztes Änderungsdatum des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="508d8-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="508d8-104">tblComplianceFanout enthält alle Server, die ein Compliance-Ereignis verarbeitet haben.</span><span class="sxs-lookup"><span data-stu-id="508d8-104">tblComplianceFanout contains all servers that processed a compliance event.</span></span>

### <a name="columns"></a><span data-ttu-id="508d8-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="508d8-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="508d8-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="508d8-106">Column</span></span></th>
<th><span data-ttu-id="508d8-107">Typ</span><span class="sxs-lookup"><span data-stu-id="508d8-107">Type</span></span></th>
<th><span data-ttu-id="508d8-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="508d8-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="508d8-109">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="508d8-109">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="508d8-110">int</span><span class="sxs-lookup"><span data-stu-id="508d8-110">int</span></span></p></td>
<td><p><span data-ttu-id="508d8-111">Ereignis-ID.</span><span class="sxs-lookup"><span data-stu-id="508d8-111">Event ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="508d8-112">fanoutServerID</span><span class="sxs-lookup"><span data-stu-id="508d8-112">fanoutServerID</span></span></p></td>
<td><p><span data-ttu-id="508d8-113">int</span><span class="sxs-lookup"><span data-stu-id="508d8-113">int</span></span></p></td>
<td><p><span data-ttu-id="508d8-114">Serveridentität (entsprechend der Tabelle "tblServerIdentity. Serverkennung").</span><span class="sxs-lookup"><span data-stu-id="508d8-114">Server identity (corresponding to tblServerIdentity.serverID table).</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="508d8-115">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="508d8-115">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="508d8-116">Spalte</span><span class="sxs-lookup"><span data-stu-id="508d8-116">Column</span></span></th>
<th><span data-ttu-id="508d8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="508d8-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="508d8-118">fanoutEventID</span><span class="sxs-lookup"><span data-stu-id="508d8-118">fanoutEventID</span></span></p></td>
<td><p><span data-ttu-id="508d8-119">Fremdschlüssel mit Lookup in der tblComplianceData. cmplEventID-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="508d8-119">Foreign key with lookup in tblComplianceData.cmplEventID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

