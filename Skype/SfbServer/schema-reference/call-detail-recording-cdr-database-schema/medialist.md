---
title: MediaList-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.
ms.openlocfilehash: 3eaa40cb5ae03129edaa36effa7b40012fc38429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930651"
---
# <a name="medialist-table"></a><span data-ttu-id="6986d-103">MediaList-Tabelle</span><span class="sxs-lookup"><span data-stu-id="6986d-103">MediaList table</span></span>
 
<span data-ttu-id="6986d-104">Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="6986d-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="6986d-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="6986d-105">**Column**</span></span>|<span data-ttu-id="6986d-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="6986d-106">**Data Type**</span></span>|<span data-ttu-id="6986d-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="6986d-107">**Key/Index**</span></span>|<span data-ttu-id="6986d-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="6986d-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6986d-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="6986d-109">**MediaId**</span></span> <br/> |<span data-ttu-id="6986d-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="6986d-110">tinyint</span></span>  <br/> |<span data-ttu-id="6986d-111">Primary</span><span class="sxs-lookup"><span data-stu-id="6986d-111">Primary</span></span>  <br/> |<span data-ttu-id="6986d-112">Werte: 1-7</span><span class="sxs-lookup"><span data-stu-id="6986d-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="6986d-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="6986d-113">**Media**</span></span> <br/> |<span data-ttu-id="6986d-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6986d-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="6986d-115">Statische Zuordnung von MediaID- und Media-Werten</span><span class="sxs-lookup"><span data-stu-id="6986d-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="6986d-116">1 – Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="6986d-116">1 -- IM</span></span> <br/>  <span data-ttu-id="6986d-117">2 – Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="6986d-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="6986d-118">3 – Remoteunterstützung</span><span class="sxs-lookup"><span data-stu-id="6986d-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="6986d-119">4 – Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="6986d-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="6986d-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="6986d-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="6986d-121">6 – Video</span><span class="sxs-lookup"><span data-stu-id="6986d-121">6 -- Video</span></span> <br/>  <span data-ttu-id="6986d-122">7 – Anwendungseinladung</span><span class="sxs-lookup"><span data-stu-id="6986d-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="6986d-123">Wenn Sie versuchen, den Modalitätstyp für die Werte in LcsCDR.SessionDetailsView.MediaTypes zu bestimmen, müssen Sie das folgende Join-Snippet verwenden: </span><span class="sxs-lookup"><span data-stu-id="6986d-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
