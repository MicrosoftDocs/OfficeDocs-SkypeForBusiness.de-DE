---
title: 'Lync Server 2013: tblPrincipalMeta'
description: 'Lync Server 2013: tblPrincipalMeta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalMeta
ms:assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615009(v=OCS.15)
ms:contentKeyID: 48184648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 899fd1e450dac52afa56c1ee1de86da82b2db309
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573641"
---
# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="cc893-103">tblPrincipalMeta in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cc893-103">tblPrincipalMeta in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc893-104">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="cc893-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="cc893-105">tblPrincipalMeta enthält die Prinzipale, die aus Active Directory-Domänendienste aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cc893-105">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="cc893-106">Spalten</span><span class="sxs-lookup"><span data-stu-id="cc893-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc893-107">Spalte</span><span class="sxs-lookup"><span data-stu-id="cc893-107">Column</span></span></th>
<th><span data-ttu-id="cc893-108">Typ</span><span class="sxs-lookup"><span data-stu-id="cc893-108">Type</span></span></th>
<th><span data-ttu-id="cc893-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc893-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc893-110">prinID</span><span class="sxs-lookup"><span data-stu-id="cc893-110">prinID</span></span></p></td>
<td><p><span data-ttu-id="cc893-111">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="cc893-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="cc893-112">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="cc893-112">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc893-113">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="cc893-113">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="cc893-114">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="cc893-114">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cc893-115">TRUE, wenn Prinzipalzuordnungen aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cc893-115">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc893-116">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="cc893-116">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="cc893-117">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="cc893-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cc893-118">TRUE, wenn Prinzipalattribute aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="cc893-118">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc893-119">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="cc893-119">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="cc893-120">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="cc893-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="cc893-121">TRUE, wenn der Prinzipal gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="cc893-121">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc893-122">tryCount</span><span class="sxs-lookup"><span data-stu-id="cc893-122">tryCount</span></span></p></td>
<td><p><span data-ttu-id="cc893-123">int</span><span class="sxs-lookup"><span data-stu-id="cc893-123">int</span></span></p></td>
<td><p><span data-ttu-id="cc893-124">Anzahl der Versuche, den Prinzipal über AD DS zu aktualisieren, die bisher ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="cc893-124">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc893-125">lastTry</span><span class="sxs-lookup"><span data-stu-id="cc893-125">lastTry</span></span></p></td>
<td><p><span data-ttu-id="cc893-126">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="cc893-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="cc893-p101">Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren. Kann NULL sein, wenn bisher kein Aktualisierungsversuch unternommen wurde.</span><span class="sxs-lookup"><span data-stu-id="cc893-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cc893-129">nextTry</span><span class="sxs-lookup"><span data-stu-id="cc893-129">nextTry</span></span></p></td>
<td><p><span data-ttu-id="cc893-130">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="cc893-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="cc893-p102">Zeitstempel für die nächste geplante Aktualisierung. Kann NULL sein, wenn keine weitere Aktualisierung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="cc893-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="cc893-133">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="cc893-133">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cc893-134">Spalte</span><span class="sxs-lookup"><span data-stu-id="cc893-134">Column</span></span></th>
<th><span data-ttu-id="cc893-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cc893-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cc893-136">prinID</span><span class="sxs-lookup"><span data-stu-id="cc893-136">prinID</span></span></p></td>
<td><p><span data-ttu-id="cc893-137">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="cc893-137">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cc893-138">prinID</span><span class="sxs-lookup"><span data-stu-id="cc893-138">prinID</span></span></p></td>
<td><p><span data-ttu-id="cc893-139">Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="cc893-139">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

