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
ms.openlocfilehash: 243fd3fb705826584f4e786441cdc1faa9075777
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992925"
---
# <a name="medialist-table"></a><span data-ttu-id="8eb10-103">MediaList-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8eb10-103">MediaList table</span></span>
 
<span data-ttu-id="8eb10-104">Die MediaList-Tabelle ist eine statische Tabelle, in der die Liste der verschiedenen Medientypen gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="8eb10-104">The MediaList table is a static table that stores the list of various media types.</span></span>
  
|<span data-ttu-id="8eb10-105">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="8eb10-105">**Column**</span></span>|<span data-ttu-id="8eb10-106">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8eb10-106">**Data Type**</span></span>|<span data-ttu-id="8eb10-107">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="8eb10-107">**Key/Index**</span></span>|<span data-ttu-id="8eb10-108">**Details**</span><span class="sxs-lookup"><span data-stu-id="8eb10-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8eb10-109">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="8eb10-109">**MediaId**</span></span> <br/> |<span data-ttu-id="8eb10-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="8eb10-110">tinyint</span></span>  <br/> |<span data-ttu-id="8eb10-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8eb10-111">Primary</span></span>  <br/> |<span data-ttu-id="8eb10-112">Werte: 1-7</span><span class="sxs-lookup"><span data-stu-id="8eb10-112">Values: 1-7</span></span>  <br/> |
|<span data-ttu-id="8eb10-113">**Media**</span><span class="sxs-lookup"><span data-stu-id="8eb10-113">**Media**</span></span> <br/> |<span data-ttu-id="8eb10-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8eb10-114">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="8eb10-115">Statische Zuordnung von MediaID- und Media-Werten</span><span class="sxs-lookup"><span data-stu-id="8eb10-115">Static mapping of MediaID and Media values:</span></span> <br/>  <span data-ttu-id="8eb10-116">1 – Sofortnachrichten</span><span class="sxs-lookup"><span data-stu-id="8eb10-116">1 -- IM</span></span> <br/>  <span data-ttu-id="8eb10-117">2-Dateiübertragung</span><span class="sxs-lookup"><span data-stu-id="8eb10-117">2 - File Transfer</span></span> <br/>  <span data-ttu-id="8eb10-118">3 – Remote Unterstützung</span><span class="sxs-lookup"><span data-stu-id="8eb10-118">3 - Remote Assistance</span></span> <br/>  <span data-ttu-id="8eb10-119">4 – Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="8eb10-119">4 - Application Sharing</span></span> <br/>  <span data-ttu-id="8eb10-120">5 – Audio</span><span class="sxs-lookup"><span data-stu-id="8eb10-120">5 -- Audio</span></span> <br/>  <span data-ttu-id="8eb10-121">6 – Video</span><span class="sxs-lookup"><span data-stu-id="8eb10-121">6 -- Video</span></span> <br/>  <span data-ttu-id="8eb10-122">7-App-Einladung</span><span class="sxs-lookup"><span data-stu-id="8eb10-122">7 - App Invite</span></span> <br/> |
   
<span data-ttu-id="8eb10-123">Wenn Sie versuchen, den Modalitätstyp für die Werte in LcsCDR.SessionDetailsView.MediaTypes zu bestimmen, müssen Sie das folgende Join-Snippet verwenden: </span><span class="sxs-lookup"><span data-stu-id="8eb10-123">If you are trying to determine the modality type for the values in LcsCDR.SessionDetailsView.MediaTypes, then you need to use the following Join snippet:</span></span> 
  
```json
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
