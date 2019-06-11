---
title: 'Lync Server 2013: Tenants-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7da863aa2b713f874aba00f5a4f481f45fb79b3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="f0940-102">Tenants-Tabelle in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0940-102">Tenants table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0940-103">_**Letztes Änderungsdatum des Themas:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f0940-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f0940-104">Die Tabelle Mandanten ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Mandanten gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="f0940-104">The Tenants table is a supporting table that stores a list of the various tenants.</span></span> <span data-ttu-id="f0940-105">Jeder Datensatz in der Tabelle steht für einen Mandanten.</span><span class="sxs-lookup"><span data-stu-id="f0940-105">Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f0940-106">In der lokalen Bereitstellung verwendet CdR die integrierte Mandanten-ID, um einen anderen Authentifizierungstyp anzugeben, beispielsweise öffentliche im-Konnektivität, Federated und Anonymous.</span><span class="sxs-lookup"><span data-stu-id="f0940-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



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
<th><span data-ttu-id="f0940-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="f0940-107">Column</span></span></th>
<th><span data-ttu-id="f0940-108">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f0940-108">Data Type</span></span></th>
<th><span data-ttu-id="f0940-109">Schlüssel/Index</span><span class="sxs-lookup"><span data-stu-id="f0940-109">Key/Index</span></span></th>
<th><span data-ttu-id="f0940-110">Details</span><span class="sxs-lookup"><span data-stu-id="f0940-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0940-111"><strong>Mandanten</strong></span><span class="sxs-lookup"><span data-stu-id="f0940-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="f0940-112">int</span><span class="sxs-lookup"><span data-stu-id="f0940-112">int</span></span></p></td>
<td><p><span data-ttu-id="f0940-113">Primary</span><span class="sxs-lookup"><span data-stu-id="f0940-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0940-114">Eindeutige Nummer, die diese Mandanten-ID kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="f0940-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0940-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="f0940-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="f0940-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f0940-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0940-117">Zulässige Werte:</span><span class="sxs-lookup"><span data-stu-id="f0940-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="f0940-118">00000000-0000-0000-0000-000000000000 – Enterprise</span><span class="sxs-lookup"><span data-stu-id="f0940-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="f0940-119">00000000-0000-0000-0000-000000000001 – Federated</span><span class="sxs-lookup"><span data-stu-id="f0940-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="f0940-120">00000000-0000-0000-0000-000000000002 – anonym</span><span class="sxs-lookup"><span data-stu-id="f0940-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="f0940-121">00000000-0000-0000-0000-000000000003 – Konnektivität für öffentliche Chats</span><span class="sxs-lookup"><span data-stu-id="f0940-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

