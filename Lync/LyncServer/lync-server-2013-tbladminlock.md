---
title: 'Lync Server 2013: tblAdminLock'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0cdfbc28f440fe9bbcc186e685cd5efdb5f23498
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a><span data-ttu-id="fd096-102">tblAdminLock in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd096-102">tblAdminLock in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd096-103">_**Letztes Änderungsdatum des Themas:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="fd096-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="fd096-104">tblAdminLock enthält die administratorsperre, die zum Ausführen einiger Administrator Befehle erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fd096-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>

### <a name="columns"></a><span data-ttu-id="fd096-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="fd096-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd096-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="fd096-106">Column</span></span></th>
<th><span data-ttu-id="fd096-107">Typ</span><span class="sxs-lookup"><span data-stu-id="fd096-107">Type</span></span></th>
<th><span data-ttu-id="fd096-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd096-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd096-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="fd096-109">lockExpiresTime</span></span></p></td>
<td><p><span data-ttu-id="fd096-110">DateTime, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fd096-110">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="fd096-111">Ablaufdatum und-Uhrzeit Sperren</span><span class="sxs-lookup"><span data-stu-id="fd096-111">Lock expiration date and time.</span></span> <span data-ttu-id="fd096-112">Der Besitzer kann diesen Wert in regelmäßigen Abständen verlängern.</span><span class="sxs-lookup"><span data-stu-id="fd096-112">The owner can extend this value periodically.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd096-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="fd096-113">lockServerID</span></span></p></td>
<td><p><span data-ttu-id="fd096-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fd096-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fd096-115">Die ID des Servers, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="fd096-115">ID of the server that owns the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd096-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="fd096-116">lockActorID</span></span></p></td>
<td><p><span data-ttu-id="fd096-117">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="fd096-117">int, not null</span></span></p></td>
<td><p><span data-ttu-id="fd096-118">Die ID des Prinzipals, der die Sperre besitzt.</span><span class="sxs-lookup"><span data-stu-id="fd096-118">ID of the principal that owns the lock.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

