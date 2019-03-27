---
title: UserStatistics-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die UserStatistics-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung eines einzelnen Benutzers des Systems. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883595"
---
# <a name="userstatistics-table"></a><span data-ttu-id="3ca0f-105">UserStatistics-Tabelle</span><span class="sxs-lookup"><span data-stu-id="3ca0f-105">UserStatistics table</span></span>
 
<span data-ttu-id="3ca0f-106">Die UserStatistics-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3ca0f-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="3ca0f-107">Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung eines einzelnen Benutzers des Systems.</span><span class="sxs-lookup"><span data-stu-id="3ca0f-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="3ca0f-108">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3ca0f-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3ca0f-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="3ca0f-109">**Column**</span></span>|<span data-ttu-id="3ca0f-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="3ca0f-110">**Data Type**</span></span>|<span data-ttu-id="3ca0f-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="3ca0f-111">**Key/Index**</span></span>|<span data-ttu-id="3ca0f-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="3ca0f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3ca0f-113">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="3ca0f-113">**UserId**</span></span> <br/> |<span data-ttu-id="3ca0f-114">int</span><span class="sxs-lookup"><span data-stu-id="3ca0f-114">int</span></span>  <br/> |<span data-ttu-id="3ca0f-115">Primary</span><span class="sxs-lookup"><span data-stu-id="3ca0f-115">Primary</span></span>  <br/> |<span data-ttu-id="3ca0f-116">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3ca0f-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="3ca0f-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="3ca0f-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="3ca0f-118">datetime</span><span class="sxs-lookup"><span data-stu-id="3ca0f-118">datetime</span></span>  <br/> ||<span data-ttu-id="3ca0f-119">Zuletzt der Benutzer angemeldet.</span><span class="sxs-lookup"><span data-stu-id="3ca0f-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="3ca0f-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="3ca0f-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="3ca0f-121">datetime</span><span class="sxs-lookup"><span data-stu-id="3ca0f-121">datetime</span></span>  <br/> ||<span data-ttu-id="3ca0f-122">Zuletzt organisiert der Benutzer eine Konferenz.</span><span class="sxs-lookup"><span data-stu-id="3ca0f-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="3ca0f-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="3ca0f-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="3ca0f-124">datetime</span><span class="sxs-lookup"><span data-stu-id="3ca0f-124">datetime</span></span>  <br/> ||<span data-ttu-id="3ca0f-125">Zuletzt der Benutzer einen anruffehler.</span><span class="sxs-lookup"><span data-stu-id="3ca0f-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="3ca0f-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="3ca0f-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="3ca0f-127">datetime</span><span class="sxs-lookup"><span data-stu-id="3ca0f-127">datetime</span></span>  <br/> ||<span data-ttu-id="3ca0f-128">Zuletzt der Benutzer einen anruffehler als Konferenzorganisator.</span><span class="sxs-lookup"><span data-stu-id="3ca0f-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

