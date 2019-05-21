---
title: UserStatistics-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die Tabelle UserStatistics ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Verwendung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295692"
---
# <a name="userstatistics-table"></a><span data-ttu-id="b6cc7-105">UserStatistics-Tabelle</span><span class="sxs-lookup"><span data-stu-id="b6cc7-105">UserStatistics table</span></span>
 
<span data-ttu-id="b6cc7-106">Die Tabelle UserStatistics ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b6cc7-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="b6cc7-107">Jeder Datensatz in der Tabelle speichert Informationen zur Verwendung des Systems durch einen einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="b6cc7-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="b6cc7-108">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b6cc7-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b6cc7-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="b6cc7-109">**Column**</span></span>|<span data-ttu-id="b6cc7-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="b6cc7-110">**Data Type**</span></span>|<span data-ttu-id="b6cc7-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="b6cc7-111">**Key/Index**</span></span>|<span data-ttu-id="b6cc7-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="b6cc7-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b6cc7-113">**UserID**</span><span class="sxs-lookup"><span data-stu-id="b6cc7-113">**UserId**</span></span> <br/> |<span data-ttu-id="b6cc7-114">int</span><span class="sxs-lookup"><span data-stu-id="b6cc7-114">int</span></span>  <br/> |<span data-ttu-id="b6cc7-115">Primary</span><span class="sxs-lookup"><span data-stu-id="b6cc7-115">Primary</span></span>  <br/> |<span data-ttu-id="b6cc7-116">Eindeutige Nummer, die diesen Benutzer kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="b6cc7-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="b6cc7-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="b6cc7-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="b6cc7-118">datetime</span><span class="sxs-lookup"><span data-stu-id="b6cc7-118">datetime</span></span>  <br/> ||<span data-ttu-id="b6cc7-119">Zeitpunkt, zu dem sich der Benutzer zuletzt angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="b6cc7-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="b6cc7-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="b6cc7-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="b6cc7-121">datetime</span><span class="sxs-lookup"><span data-stu-id="b6cc7-121">datetime</span></span>  <br/> ||<span data-ttu-id="b6cc7-122">Der letzte Zeitpunkt, zu dem der Benutzer eine Konferenz organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="b6cc7-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="b6cc7-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="b6cc7-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="b6cc7-124">datetime</span><span class="sxs-lookup"><span data-stu-id="b6cc7-124">datetime</span></span>  <br/> ||<span data-ttu-id="b6cc7-125">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler erlebt hat.</span><span class="sxs-lookup"><span data-stu-id="b6cc7-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="b6cc7-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="b6cc7-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="b6cc7-127">datetime</span><span class="sxs-lookup"><span data-stu-id="b6cc7-127">datetime</span></span>  <br/> ||<span data-ttu-id="b6cc7-128">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler als Konferenzorganisator erlebt hat.</span><span class="sxs-lookup"><span data-stu-id="b6cc7-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

