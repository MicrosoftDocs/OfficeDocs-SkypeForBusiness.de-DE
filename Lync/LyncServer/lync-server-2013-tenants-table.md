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
ms.openlocfilehash: b0d2459c169fb93520125ceef7a8076bd51343db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="9043e-102">Tabelle "Mandanten" in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9043e-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9043e-103">_**Letztes Änderungsstand des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9043e-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9043e-p101">Bei der Tenants-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der eine Liste verschiedener Mandanten gespeichert ist. Jeder Datensatz in der Tabelle steht für einen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="9043e-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9043e-106">Bei der lokalen Bereitstellung wird die integrierte Mandanten-ID von der Aufzeichnung von Kommunikationsdatensätzen (KDS) zur Angabe verschiedener Authentifizierungstypen verwendet, wie z. B. Verbindung mit öffentlichen Chatdiensten, Partner und Anonym.</span><span class="sxs-lookup"><span data-stu-id="9043e-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



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
<th><span data-ttu-id="9043e-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="9043e-107">Column</span></span></th>
<th><span data-ttu-id="9043e-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9043e-108">Data Type</span></span></th>
<th><span data-ttu-id="9043e-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="9043e-109">Key/Index</span></span></th>
<th><span data-ttu-id="9043e-110">Details</span><span class="sxs-lookup"><span data-stu-id="9043e-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9043e-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="9043e-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="9043e-112">int</span><span class="sxs-lookup"><span data-stu-id="9043e-112">int</span></span></p></td>
<td><p><span data-ttu-id="9043e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9043e-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="9043e-114">Eindeutige Zahl, die diese Mandanten-ID identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9043e-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9043e-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="9043e-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="9043e-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9043e-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9043e-117">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="9043e-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="9043e-118">00000000-0000-0000-0000-000000000000 – Enterprise</span><span class="sxs-lookup"><span data-stu-id="9043e-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="9043e-119">00000000-0000-0000-0000-000000000001 – Verbund</span><span class="sxs-lookup"><span data-stu-id="9043e-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="9043e-120">00000000-0000-0000-0000-000000000002 – Anonym</span><span class="sxs-lookup"><span data-stu-id="9043e-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="9043e-121">00000000-0000-0000-0000-000000000003 – Verbindung mit öffentlichen Chatdiensten</span><span class="sxs-lookup"><span data-stu-id="9043e-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

