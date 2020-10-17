---
title: 'Lync Server 2013: tblComplianceState'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceState
ms:assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615045(v=OCS.15)
ms:contentKeyID: 48185937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84608b7cb701fe4c394ed413539759d9469a5a4e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509412"
---
# <a name="tblcompliancestate-in-lync-server-2013"></a><span data-ttu-id="5b0f0-102">tblComplianceState in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b0f0-102">tblComplianceState in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b0f0-103">_**Letztes Änderungsstand des Themas:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="5b0f0-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="5b0f0-104">tblComplianceState enthält Informationen zum Pool weiten Kompatibilitätszustand.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-104">tblComplianceState contains pool-wide compliance state information.</span></span>

### <a name="columns"></a><span data-ttu-id="5b0f0-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="5b0f0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5b0f0-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="5b0f0-106">Column</span></span></th>
<th><span data-ttu-id="5b0f0-107">Typ</span><span class="sxs-lookup"><span data-stu-id="5b0f0-107">Type</span></span></th>
<th><span data-ttu-id="5b0f0-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b0f0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5b0f0-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="5b0f0-109">lastProcessedEntryID</span></span></p></td>
<td><p><span data-ttu-id="5b0f0-110">bigint, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5b0f0-110">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="5b0f0-111">ID des letzten verarbeiteten Kompatibilitäts Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-111">ID of the latest processed compliance event.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5b0f0-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="5b0f0-112">activeServerID</span></span></p></td>
<td><p><span data-ttu-id="5b0f0-113">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5b0f0-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="5b0f0-114">ID des Kompatibilitätsservers, der die exklusive Sperre für die Datenbank aufhält, oder-1, wenn keine.</span><span class="sxs-lookup"><span data-stu-id="5b0f0-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5b0f0-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="5b0f0-115">lockExpirationTime</span></span></p></td>
<td><p><span data-ttu-id="5b0f0-116">datetime2, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="5b0f0-116">datetime2, not null</span></span></p></td>
<td><p><span data-ttu-id="5b0f0-117">Sperr Ablaufzeit (wenn activeServerID nicht-1 ist).</span><span class="sxs-lookup"><span data-stu-id="5b0f0-117">Lock expiration time (if activeServerID is not -1).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

