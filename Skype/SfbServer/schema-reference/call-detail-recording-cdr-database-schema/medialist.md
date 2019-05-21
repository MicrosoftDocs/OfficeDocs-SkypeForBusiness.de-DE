---
title: MediaList-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.
ms.openlocfilehash: 308a9eee57089a02b8e3ff9924e0d9d34162f33e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295982"
---
# <a name="medialist-table"></a><span data-ttu-id="9f6de-103">MediaList-Tabelle</span><span class="sxs-lookup"><span data-stu-id="9f6de-103">MediaList table</span></span>
 
<span data-ttu-id="9f6de-104">Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="9f6de-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="9f6de-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="9f6de-105">**Column**</span></span>|<span data-ttu-id="9f6de-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="9f6de-106">**Data Type**</span></span>|<span data-ttu-id="9f6de-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="9f6de-107">**Key/Index**</span></span>|<span data-ttu-id="9f6de-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="9f6de-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9f6de-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="9f6de-109">**MediaId**</span></span> <br/> |<span data-ttu-id="9f6de-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f6de-110">tinyint</span></span>  <br/> |<span data-ttu-id="9f6de-111">Primary</span><span class="sxs-lookup"><span data-stu-id="9f6de-111">Primary</span></span>  <br/> |<span data-ttu-id="9f6de-112">Werte: 1-7</span><span class="sxs-lookup"><span data-stu-id="9f6de-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="9f6de-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="9f6de-113">**Media**</span></span> <br/> |<span data-ttu-id="9f6de-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9f6de-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9f6de-115">Statische Zuordnung von MediaID- und Media-Werten</span><span class="sxs-lookup"><span data-stu-id="9f6de-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="9f6de-116">1 – Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="9f6de-116">1 -- IM</span></span> <br/>  <span data-ttu-id="9f6de-117">2-Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="9f6de-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="9f6de-118">3 – Remote Unterstützung</span><span class="sxs-lookup"><span data-stu-id="9f6de-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="9f6de-119">4 – Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="9f6de-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="9f6de-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="9f6de-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="9f6de-121">6 – Video</span><span class="sxs-lookup"><span data-stu-id="9f6de-121">6 -- Video</span></span> <br/>  <span data-ttu-id="9f6de-122">7-App-Einladung</span><span class="sxs-lookup"><span data-stu-id="9f6de-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="9f6de-123">Wenn Sie versuchen, den Modalitätstyp für die Werte in LcsCDR.SessionDetailsView.MediaTypes zu bestimmen, müssen Sie das folgende Join-Snippet verwenden: </span><span class="sxs-lookup"><span data-stu-id="9f6de-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
