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
ms.openlocfilehash: c9309219399fac30e318f8e112dd82269fff5ac2
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569768"
---
# <a name="medialist-table"></a><span data-ttu-id="06c0e-103">MediaList-Tabelle</span><span class="sxs-lookup"><span data-stu-id="06c0e-103">MediaList table</span></span>
 
<span data-ttu-id="06c0e-104">Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="06c0e-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="06c0e-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="06c0e-105">**Column**</span></span>|<span data-ttu-id="06c0e-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="06c0e-106">**Data Type**</span></span>|<span data-ttu-id="06c0e-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="06c0e-107">**Key/Index**</span></span>|<span data-ttu-id="06c0e-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="06c0e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="06c0e-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="06c0e-109">**MediaId**</span></span> <br/> |<span data-ttu-id="06c0e-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="06c0e-110">tinyint</span></span>  <br/> |<span data-ttu-id="06c0e-111">Primary</span><span class="sxs-lookup"><span data-stu-id="06c0e-111">Primary</span></span>  <br/> |<span data-ttu-id="06c0e-112">Werte: 1-7</span><span class="sxs-lookup"><span data-stu-id="06c0e-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="06c0e-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="06c0e-113">**Media**</span></span> <br/> |<span data-ttu-id="06c0e-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="06c0e-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="06c0e-115">Statische Zuordnung von MediaID- und Media-Werten</span><span class="sxs-lookup"><span data-stu-id="06c0e-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="06c0e-116">1 – Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="06c0e-116">1 -- IM</span></span> <br/>  <span data-ttu-id="06c0e-117">2 – Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="06c0e-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="06c0e-118">3 – Remoteunterstützung</span><span class="sxs-lookup"><span data-stu-id="06c0e-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="06c0e-119">4 – Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="06c0e-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="06c0e-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="06c0e-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="06c0e-121">6 – Video</span><span class="sxs-lookup"><span data-stu-id="06c0e-121">6 -- Video</span></span> <br/>  <span data-ttu-id="06c0e-122">7 – Anwendungseinladung</span><span class="sxs-lookup"><span data-stu-id="06c0e-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="06c0e-123">Wenn Sie versuchen, den Modalitätstyp für die Werte in LcsCDR.SessionDetailsView.MediaTypes zu bestimmen, müssen Sie das folgende Join-Snippet verwenden: </span><span class="sxs-lookup"><span data-stu-id="06c0e-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```