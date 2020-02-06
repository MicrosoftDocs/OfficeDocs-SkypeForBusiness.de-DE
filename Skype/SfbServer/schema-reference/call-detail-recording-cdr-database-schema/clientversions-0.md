---
title: ClientVersions-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und-Versionen gespeichert, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Ansicht stellt eine Client Version dar. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815413"
---
# <a name="clientversions-view"></a><span data-ttu-id="4c26e-105">ClientVersions-Ansicht</span><span class="sxs-lookup"><span data-stu-id="4c26e-105">ClientVersions view</span></span>
 
<span data-ttu-id="4c26e-106">In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und-Versionen gespeichert, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="4c26e-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="4c26e-107">Jeder Datensatz in der Ansicht stellt eine Client Version dar.</span><span class="sxs-lookup"><span data-stu-id="4c26e-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="4c26e-108">Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4c26e-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4c26e-109">Für bestimmte Spalten können mehrere Datensätze vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4c26e-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="4c26e-110">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="4c26e-110">**Column**</span></span>|<span data-ttu-id="4c26e-111">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="4c26e-111">**Data Type**</span></span>|<span data-ttu-id="4c26e-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="4c26e-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4c26e-113">**VersionID**</span><span class="sxs-lookup"><span data-stu-id="4c26e-113">**VersionId**</span></span> <br/> |<span data-ttu-id="4c26e-114">int</span><span class="sxs-lookup"><span data-stu-id="4c26e-114">int</span></span>  <br/> |<span data-ttu-id="4c26e-115">Eindeutige Nummer, die diesen Clienttyp und die Version identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4c26e-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="4c26e-116">**Version**</span><span class="sxs-lookup"><span data-stu-id="4c26e-116">**Version**</span></span> <br/> |<span data-ttu-id="4c26e-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="4c26e-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="4c26e-118">Stellt den Benutzer-Agent dar.</span><span class="sxs-lookup"><span data-stu-id="4c26e-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="4c26e-119">**Clienttyp**</span><span class="sxs-lookup"><span data-stu-id="4c26e-119">**ClientType**</span></span> <br/> |<span data-ttu-id="4c26e-120">int</span><span class="sxs-lookup"><span data-stu-id="4c26e-120">int</span></span>  <br/> |<span data-ttu-id="4c26e-121">Der Typ des Clients.</span><span class="sxs-lookup"><span data-stu-id="4c26e-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="4c26e-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="4c26e-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="4c26e-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="4c26e-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="4c26e-124">Die Kategorie, zu der der Client gehört.</span><span class="sxs-lookup"><span data-stu-id="4c26e-124">Category that the client belongs to.</span></span> <span data-ttu-id="4c26e-125">Beispielsweise gehört der Client Conferencing_Attendant_1 .0 zu ClientCategory CAA.</span><span class="sxs-lookup"><span data-stu-id="4c26e-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

