---
title: 'Lync Server 2013: tblPreference'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615052(v=OCS.15)
ms:contentKeyID: 48185913
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef0ee11cd780037410ea1d7e0d94c83e139d8418
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523772"
---
# <a name="tblpreference-in-lync-server-2013"></a><span data-ttu-id="507ba-102">tblPreference in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="507ba-102">tblPreference in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="507ba-103">_**Letztes Änderungsstand des Themas:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="507ba-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="507ba-104">tblPreference enthält die Clienteinstellungen der Benutzer.</span><span class="sxs-lookup"><span data-stu-id="507ba-104">tblPreference contains the users’ client preferences.</span></span> <span data-ttu-id="507ba-105">Dies wird in der Regel von Clients vor lync 2013 verwendet.</span><span class="sxs-lookup"><span data-stu-id="507ba-105">This is generally used by clients previous to Lync 2013.</span></span>

### <a name="columns"></a><span data-ttu-id="507ba-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="507ba-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="507ba-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="507ba-107">Column</span></span></th>
<th><span data-ttu-id="507ba-108">Typ</span><span class="sxs-lookup"><span data-stu-id="507ba-108">Type</span></span></th>
<th><span data-ttu-id="507ba-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="507ba-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="507ba-110">prefLabel</span><span class="sxs-lookup"><span data-stu-id="507ba-110">prefLabel</span></span></p></td>
<td><p><span data-ttu-id="507ba-111">nvarchar (255), nicht NULL</span><span class="sxs-lookup"><span data-stu-id="507ba-111">nvarchar (255), not null</span></span></p></td>
<td><p><span data-ttu-id="507ba-112">Bezeichnungsfeld mit einem Format wie: &lt; User SIP URI &gt; | username. &lt; Voreinstellungsgruppe &gt; .</span><span class="sxs-lookup"><span data-stu-id="507ba-112">Label with a format such as: &lt;user sip uri&gt;|username.&lt;preference set&gt;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="507ba-113">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="507ba-113">prefSeqID</span></span></p></td>
<td><p><span data-ttu-id="507ba-114">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="507ba-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="507ba-115">Eine fortlaufende Zahl (pro Bezeichnung) für die Versionsverwaltung.</span><span class="sxs-lookup"><span data-stu-id="507ba-115">A sequential number (per label) for versioning purposes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="507ba-116">prefContent</span><span class="sxs-lookup"><span data-stu-id="507ba-116">prefContent</span></span></p></td>
<td><p><span data-ttu-id="507ba-117">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="507ba-117">nvarchar (max)</span></span></p></td>
<td><p><span data-ttu-id="507ba-118">Codierte Inhalte.</span><span class="sxs-lookup"><span data-stu-id="507ba-118">Encoded content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="507ba-119">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="507ba-119">lastModifiedBy</span></span></p></td>
<td><p><span data-ttu-id="507ba-120">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="507ba-120">int, not null</span></span></p></td>
<td><p><span data-ttu-id="507ba-121">ID des Prinzipals, der die Einstellung aktualisiert hat.</span><span class="sxs-lookup"><span data-stu-id="507ba-121">ID of the principal that updated the preference.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="507ba-122">Key</span><span class="sxs-lookup"><span data-stu-id="507ba-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="507ba-123">Spalte</span><span class="sxs-lookup"><span data-stu-id="507ba-123">Column</span></span></th>
<th><span data-ttu-id="507ba-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="507ba-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="507ba-125">&lt;prefLabel, prefSeqID&gt;</span><span class="sxs-lookup"><span data-stu-id="507ba-125">&lt;prefLabel, prefSeqID&gt;</span></span></p></td>
<td><p><span data-ttu-id="507ba-126">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="507ba-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

