---
title: UserStatistics-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die UserStatistics-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung eines einzelnen Benutzers des Systems. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: c2e0acffa7b75b3c54781e3e4e9a8b033be5e440
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929980"
---
# <a name="userstatistics-table"></a><span data-ttu-id="b520f-105">UserStatistics-Tabelle</span><span class="sxs-lookup"><span data-stu-id="b520f-105">UserStatistics table</span></span>
 
<span data-ttu-id="b520f-106">Die UserStatistics-Tabelle ist eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b520f-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="b520f-107">Jeder Datensatz in der Tabelle speichert Informationen zur Nutzung eines einzelnen Benutzers des Systems.</span><span class="sxs-lookup"><span data-stu-id="b520f-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="b520f-108">Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b520f-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b520f-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b520f-109">**Column**</span></span>|<span data-ttu-id="b520f-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b520f-110">**Data Type**</span></span>|<span data-ttu-id="b520f-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="b520f-111">**Key/Index**</span></span>|<span data-ttu-id="b520f-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="b520f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b520f-113">**Benutzer-ID**</span><span class="sxs-lookup"><span data-stu-id="b520f-113">**UserId**</span></span> <br/> |<span data-ttu-id="b520f-114">int</span><span class="sxs-lookup"><span data-stu-id="b520f-114">int</span></span>  <br/> |<span data-ttu-id="b520f-115">Primary</span><span class="sxs-lookup"><span data-stu-id="b520f-115">Primary</span></span>  <br/> |<span data-ttu-id="b520f-116">Eindeutige Zahl, die diesen Benutzer identifiziert.</span><span class="sxs-lookup"><span data-stu-id="b520f-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="b520f-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="b520f-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="b520f-118">datetime</span><span class="sxs-lookup"><span data-stu-id="b520f-118">datetime</span></span>  <br/> ||<span data-ttu-id="b520f-119">Zuletzt der Benutzer angemeldet.</span><span class="sxs-lookup"><span data-stu-id="b520f-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="b520f-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="b520f-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="b520f-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b520f-121">datetime</span></span>  <br/> ||<span data-ttu-id="b520f-122">Zuletzt organisiert der Benutzer eine Konferenz.</span><span class="sxs-lookup"><span data-stu-id="b520f-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="b520f-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="b520f-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="b520f-124">datetime</span><span class="sxs-lookup"><span data-stu-id="b520f-124">datetime</span></span>  <br/> ||<span data-ttu-id="b520f-125">Zuletzt der Benutzer einen anruffehler.</span><span class="sxs-lookup"><span data-stu-id="b520f-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="b520f-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="b520f-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="b520f-127">datetime</span><span class="sxs-lookup"><span data-stu-id="b520f-127">datetime</span></span>  <br/> ||<span data-ttu-id="b520f-128">Zuletzt der Benutzer einen anruffehler als Konferenzorganisator.</span><span class="sxs-lookup"><span data-stu-id="b520f-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

