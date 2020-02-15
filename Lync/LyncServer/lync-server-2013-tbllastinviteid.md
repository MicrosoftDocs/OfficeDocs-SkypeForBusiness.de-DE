---
title: 'Lync Server 2013: tblLastInviteId'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblLastInviteId
ms:assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558625(v=OCS.15)
ms:contentKeyID: 48183608
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b58f43c696a6218d0dd9b670615cc0f73b0b7ae3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42024726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbllastinviteid-in-lync-server-2013"></a><span data-ttu-id="6e5cb-102">tblLastInviteId in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e5cb-102">tblLastInviteId in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e5cb-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="6e5cb-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="6e5cb-104">"tblLastInviteId" enthält die letzte Einladungs-ID, die für jeden Benutzer generiert (und in der tblPrincipalInvites-Tabelle) verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>

### <a name="columns"></a><span data-ttu-id="6e5cb-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="6e5cb-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e5cb-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="6e5cb-106">Column</span></span></th>
<th><span data-ttu-id="6e5cb-107">Typ</span><span class="sxs-lookup"><span data-stu-id="6e5cb-107">Type</span></span></th>
<th><span data-ttu-id="6e5cb-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e5cb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e5cb-109">prinID</span><span class="sxs-lookup"><span data-stu-id="6e5cb-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="6e5cb-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="6e5cb-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6e5cb-111">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="6e5cb-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5cb-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="6e5cb-112">lastInviteID</span></span></p></td>
<td><p><span data-ttu-id="6e5cb-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="6e5cb-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="6e5cb-114">Zuletzt verwendete INVITE-ID.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-114">Last used invite ID.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="6e5cb-115">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="6e5cb-115">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e5cb-116">Spalte</span><span class="sxs-lookup"><span data-stu-id="6e5cb-116">Column</span></span></th>
<th><span data-ttu-id="6e5cb-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e5cb-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e5cb-118">prinID</span><span class="sxs-lookup"><span data-stu-id="6e5cb-118">prinID</span></span></p></td>
<td><p><span data-ttu-id="6e5cb-119">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="6e5cb-119">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e5cb-120">prinID</span><span class="sxs-lookup"><span data-stu-id="6e5cb-120">prinID</span></span></p></td>
<td><p><span data-ttu-id="6e5cb-121">Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6e5cb-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="6e5cb-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e5cb-122">See Also</span></span>


[<span data-ttu-id="6e5cb-123">tblPrincipalInvites in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6e5cb-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

