---
title: ClientVersions-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: ClientVersions-Ansicht speichert Informationen über die verschiedenen Clienttypen und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht steht für eine Clientversion. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: cc4024a7e2644a177eb6962c8fdc7078fd6b397d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901522"
---
# <a name="clientversions-view"></a><span data-ttu-id="192bd-105">ClientVersions-Ansicht</span><span class="sxs-lookup"><span data-stu-id="192bd-105">ClientVersions view</span></span>
 
<span data-ttu-id="192bd-106">ClientVersions-Ansicht speichert Informationen über die verschiedenen Clienttypen und Versionen, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="192bd-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="192bd-107">Jeder Datensatz in der Ansicht steht für eine Clientversion.</span><span class="sxs-lookup"><span data-stu-id="192bd-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="192bd-108">Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="192bd-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="192bd-109">Möglicherweise gibt es mehrere Datensätze für bestimmte Spalten.</span><span class="sxs-lookup"><span data-stu-id="192bd-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="192bd-110">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="192bd-110">**Column**</span></span>|<span data-ttu-id="192bd-111">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="192bd-111">**Data Type**</span></span>|<span data-ttu-id="192bd-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="192bd-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="192bd-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="192bd-113">**VersionId**</span></span> <br/> |<span data-ttu-id="192bd-114">int</span><span class="sxs-lookup"><span data-stu-id="192bd-114">int</span></span>  <br/> |<span data-ttu-id="192bd-115">Eindeutige Zahl, identifiziert dieser Clienttyp und Version.</span><span class="sxs-lookup"><span data-stu-id="192bd-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="192bd-116">**Version**</span><span class="sxs-lookup"><span data-stu-id="192bd-116">**Version**</span></span> <br/> |<span data-ttu-id="192bd-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="192bd-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="192bd-118">Stellt den Benutzer-Agent.</span><span class="sxs-lookup"><span data-stu-id="192bd-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="192bd-119">**Clienttyp**</span><span class="sxs-lookup"><span data-stu-id="192bd-119">**ClientType**</span></span> <br/> |<span data-ttu-id="192bd-120">int</span><span class="sxs-lookup"><span data-stu-id="192bd-120">int</span></span>  <br/> |<span data-ttu-id="192bd-121">Der Typ des Clients.</span><span class="sxs-lookup"><span data-stu-id="192bd-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="192bd-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="192bd-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="192bd-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="192bd-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="192bd-124">Kategorie, zu der Client gehört.</span><span class="sxs-lookup"><span data-stu-id="192bd-124">Category that the client belongs to.</span></span> <span data-ttu-id="192bd-125">Der Client Conferencing_Attendant_1.0 beispielsweise die ClientCategory CAA gehört.</span><span class="sxs-lookup"><span data-stu-id="192bd-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

