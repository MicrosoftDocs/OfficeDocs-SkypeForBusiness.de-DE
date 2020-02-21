---
title: 'Lync Server 2013: tblPrincipalMeta'
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
ms.openlocfilehash: 04ad0fbdb9a4e3bb2e5962089fe1c30f960bdc91
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipalmeta-in-lync-server-2013"></a><span data-ttu-id="ff23b-102">tblPrincipalMeta in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff23b-102">tblPrincipalMeta in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff23b-103">_**Letztes Änderungsstand des Themas:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="ff23b-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="ff23b-104">tblPrincipalMeta enthält die Prinzipale, die aus Active Directory-Domänendienste aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ff23b-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>

### <a name="columns"></a><span data-ttu-id="ff23b-105">Spalten</span><span class="sxs-lookup"><span data-stu-id="ff23b-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff23b-106">Spalte</span><span class="sxs-lookup"><span data-stu-id="ff23b-106">Column</span></span></th>
<th><span data-ttu-id="ff23b-107">Typ</span><span class="sxs-lookup"><span data-stu-id="ff23b-107">Type</span></span></th>
<th><span data-ttu-id="ff23b-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff23b-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff23b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ff23b-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="ff23b-110">int, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ff23b-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="ff23b-111">Prinzipal-ID</span><span class="sxs-lookup"><span data-stu-id="ff23b-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff23b-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="ff23b-112">prinAffiliationsDirty</span></span></p></td>
<td><p><span data-ttu-id="ff23b-113">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ff23b-113">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ff23b-114">TRUE, wenn Prinzipalzuordnungen aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ff23b-114">True if principal affiliations have to be refreshed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff23b-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="ff23b-115">prinAttributesDirty</span></span></p></td>
<td><p><span data-ttu-id="ff23b-116">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ff23b-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ff23b-117">TRUE, wenn Prinzipalattribute aktualisiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ff23b-117">True if principal attributes have to be refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff23b-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="ff23b-118">prinDeleted</span></span></p></td>
<td><p><span data-ttu-id="ff23b-119">bit, nicht NULL</span><span class="sxs-lookup"><span data-stu-id="ff23b-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="ff23b-120">TRUE, wenn der Prinzipal gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="ff23b-120">True if the principal has been deleted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff23b-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="ff23b-121">tryCount</span></span></p></td>
<td><p><span data-ttu-id="ff23b-122">int</span><span class="sxs-lookup"><span data-stu-id="ff23b-122">int</span></span></p></td>
<td><p><span data-ttu-id="ff23b-123">Anzahl der Versuche, den Prinzipal über AD DS zu aktualisieren, die bisher ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="ff23b-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff23b-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="ff23b-124">lastTry</span></span></p></td>
<td><p><span data-ttu-id="ff23b-125">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ff23b-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff23b-p101">Zeitstempel des letzten Versuchs, den Prinzipal zu aktualisieren. Kann NULL sein, wenn bisher kein Aktualisierungsversuch unternommen wurde.</span><span class="sxs-lookup"><span data-stu-id="ff23b-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff23b-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="ff23b-128">nextTry</span></span></p></td>
<td><p><span data-ttu-id="ff23b-129">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="ff23b-129">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff23b-p102">Zeitstempel für die nächste geplante Aktualisierung. Kann NULL sein, wenn keine weitere Aktualisierung geplant ist.</span><span class="sxs-lookup"><span data-stu-id="ff23b-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="ff23b-132">Schlüssel</span><span class="sxs-lookup"><span data-stu-id="ff23b-132">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff23b-133">Spalte</span><span class="sxs-lookup"><span data-stu-id="ff23b-133">Column</span></span></th>
<th><span data-ttu-id="ff23b-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ff23b-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff23b-135">prinID</span><span class="sxs-lookup"><span data-stu-id="ff23b-135">prinID</span></span></p></td>
<td><p><span data-ttu-id="ff23b-136">Primärschlüssel</span><span class="sxs-lookup"><span data-stu-id="ff23b-136">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff23b-137">prinID</span><span class="sxs-lookup"><span data-stu-id="ff23b-137">prinID</span></span></p></td>
<td><p><span data-ttu-id="ff23b-138">Fremdschlüssel mit Abfrage der "tblPrincipal.prinID"-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ff23b-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

