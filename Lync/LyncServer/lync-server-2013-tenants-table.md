---
title: 'Lync Server 2013: Mandantentabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 091a1db8f19e44277d71371aa14c14635e6fba6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521752"
---
# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="79135-102">Tabelle "Mandanten" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="79135-102">Tenants table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79135-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="79135-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="79135-p101">Bei der Tenants-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste verschiedener Mandanten gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="79135-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="79135-106">Bei der lokalen Bereitstellung wird die integrierte Mandanten-ID von der Aufzeichnung von Kommunikationsdatensätzen (KDS) zur Angabe verschiedener Authentifizierungstypen verwendet, wie z. B. Verbindung mit öffentlichen Chatdiensten, Partner und Anonym.</span><span class="sxs-lookup"><span data-stu-id="79135-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79135-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="79135-107">Column</span></span></th>
<th><span data-ttu-id="79135-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="79135-108">Data Type</span></span></th>
<th><span data-ttu-id="79135-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="79135-109">Key/Index</span></span></th>
<th><span data-ttu-id="79135-110">Details</span><span class="sxs-lookup"><span data-stu-id="79135-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79135-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="79135-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="79135-112">int</span><span class="sxs-lookup"><span data-stu-id="79135-112">int</span></span></p></td>
<td><p><span data-ttu-id="79135-113">Primary</span><span class="sxs-lookup"><span data-stu-id="79135-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="79135-114">Eindeutige Zahl, die diese Mandanten-ID identifiziert.</span><span class="sxs-lookup"><span data-stu-id="79135-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79135-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="79135-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="79135-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="79135-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="79135-117">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="79135-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="79135-118">00000000-0000-0000-0000-000000000000 – Enterprise</span><span class="sxs-lookup"><span data-stu-id="79135-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="79135-119">00000000-0000-0000-0000-000000000001 – Verbund</span><span class="sxs-lookup"><span data-stu-id="79135-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="79135-120">00000000-0000-0000-0000-000000000002 – Anonym</span><span class="sxs-lookup"><span data-stu-id="79135-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="79135-121">00000000-0000-0000-0000-000000000003 – Verbindung mit öffentlichen Chatdiensten</span><span class="sxs-lookup"><span data-stu-id="79135-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

