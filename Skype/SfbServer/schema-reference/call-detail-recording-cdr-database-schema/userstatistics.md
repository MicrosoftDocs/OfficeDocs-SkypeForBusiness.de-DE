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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: Die Tabelle UserStatistics ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zur Verwendung des Systems durch einen einzelnen Benutzer. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814793"
---
# <a name="userstatistics-table"></a><span data-ttu-id="c8d50-105">UserStatistics-Tabelle</span><span class="sxs-lookup"><span data-stu-id="c8d50-105">UserStatistics table</span></span>
 
<span data-ttu-id="c8d50-106">Die Tabelle UserStatistics ist eine unterstützende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c8d50-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="c8d50-107">Jeder Datensatz in der Tabelle speichert Informationen zur Verwendung des Systems durch einen einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="c8d50-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="c8d50-108">Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c8d50-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c8d50-109">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="c8d50-109">**Column**</span></span>|<span data-ttu-id="c8d50-110">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="c8d50-110">**Data Type**</span></span>|<span data-ttu-id="c8d50-111">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="c8d50-111">**Key/Index**</span></span>|<span data-ttu-id="c8d50-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="c8d50-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c8d50-113">**UserID**</span><span class="sxs-lookup"><span data-stu-id="c8d50-113">**UserId**</span></span> <br/> |<span data-ttu-id="c8d50-114">int</span><span class="sxs-lookup"><span data-stu-id="c8d50-114">int</span></span>  <br/> |<span data-ttu-id="c8d50-115">Primary</span><span class="sxs-lookup"><span data-stu-id="c8d50-115">Primary</span></span>  <br/> |<span data-ttu-id="c8d50-116">Eindeutige Nummer, die diesen Benutzer kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="c8d50-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="c8d50-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="c8d50-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="c8d50-118">datetime</span><span class="sxs-lookup"><span data-stu-id="c8d50-118">datetime</span></span>  <br/> ||<span data-ttu-id="c8d50-119">Zeitpunkt, zu dem sich der Benutzer zuletzt angemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="c8d50-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="c8d50-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="c8d50-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="c8d50-121">datetime</span><span class="sxs-lookup"><span data-stu-id="c8d50-121">datetime</span></span>  <br/> ||<span data-ttu-id="c8d50-122">Der letzte Zeitpunkt, zu dem der Benutzer eine Konferenz organisiert hat.</span><span class="sxs-lookup"><span data-stu-id="c8d50-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="c8d50-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="c8d50-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="c8d50-124">datetime</span><span class="sxs-lookup"><span data-stu-id="c8d50-124">datetime</span></span>  <br/> ||<span data-ttu-id="c8d50-125">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler erlebt hat.</span><span class="sxs-lookup"><span data-stu-id="c8d50-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="c8d50-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="c8d50-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="c8d50-127">datetime</span><span class="sxs-lookup"><span data-stu-id="c8d50-127">datetime</span></span>  <br/> ||<span data-ttu-id="c8d50-128">Der letzte Zeitpunkt, zu dem der Benutzer einen Anruf Fehler als Konferenzorganisator erlebt hat.</span><span class="sxs-lookup"><span data-stu-id="c8d50-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

