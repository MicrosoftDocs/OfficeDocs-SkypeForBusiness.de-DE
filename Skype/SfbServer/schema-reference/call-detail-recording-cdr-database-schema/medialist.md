---
title: MediaList-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.
ms.openlocfilehash: b44a6dd8a4263f50cd187b6c4b154815e1e6350a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="medialist-table"></a><span data-ttu-id="72794-103">MediaList-Tabelle</span><span class="sxs-lookup"><span data-stu-id="72794-103">MediaList table</span></span>
 
<span data-ttu-id="72794-104">Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="72794-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="72794-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="72794-105">**Column**</span></span>|<span data-ttu-id="72794-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="72794-106">**Data Type**</span></span>|<span data-ttu-id="72794-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="72794-107">**Key/Index**</span></span>|<span data-ttu-id="72794-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="72794-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="72794-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="72794-109">**MediaId**</span></span> <br/> |<span data-ttu-id="72794-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="72794-110">tinyint</span></span>  <br/> |<span data-ttu-id="72794-111">Primary</span><span class="sxs-lookup"><span data-stu-id="72794-111">Primary</span></span>  <br/> |<span data-ttu-id="72794-112">Werte: 1-7</span><span class="sxs-lookup"><span data-stu-id="72794-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="72794-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="72794-113">**Media**</span></span> <br/> |<span data-ttu-id="72794-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="72794-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="72794-115">Statische Zuordnung von MediaID- und Media-Werten</span><span class="sxs-lookup"><span data-stu-id="72794-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="72794-116">1 – Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="72794-116">1 -- IM</span></span> <br/>  <span data-ttu-id="72794-117">2 – Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="72794-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="72794-118">3 – Remoteunterstützung</span><span class="sxs-lookup"><span data-stu-id="72794-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="72794-119">4 – Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="72794-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="72794-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="72794-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="72794-121">6 – Video</span><span class="sxs-lookup"><span data-stu-id="72794-121">6 -- Video</span></span> <br/>  <span data-ttu-id="72794-122">7 – Anwendungseinladung</span><span class="sxs-lookup"><span data-stu-id="72794-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="72794-123">Wenn Sie versuchen, den Modalitätstyp für die Werte in LcsCDR.SessionDetailsView.MediaTypes zu bestimmen, müssen Sie das folgende Join-Snippet verwenden: </span><span class="sxs-lookup"><span data-stu-id="72794-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```


