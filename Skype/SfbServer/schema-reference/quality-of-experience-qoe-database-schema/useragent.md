---
title: UserAgent-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805053"
---
# <a name="useragent-table"></a><span data-ttu-id="8b259-104">UserAgent-Tabelle</span><span class="sxs-lookup"><span data-stu-id="8b259-104">UserAgent table</span></span>
 
<span data-ttu-id="8b259-105">Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="8b259-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="8b259-106">Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent</span><span class="sxs-lookup"><span data-stu-id="8b259-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="8b259-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="8b259-107">**Column**</span></span>|<span data-ttu-id="8b259-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="8b259-108">**Data Type**</span></span>|<span data-ttu-id="8b259-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="8b259-109">**Key/Index**</span></span>|<span data-ttu-id="8b259-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="8b259-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b259-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="8b259-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="8b259-112">int</span><span class="sxs-lookup"><span data-stu-id="8b259-112">int</span></span>  <br/> |<span data-ttu-id="8b259-113">Primary</span><span class="sxs-lookup"><span data-stu-id="8b259-113">Primary</span></span>  <br/> |<span data-ttu-id="8b259-114">Eindeutige Nummer, die diesen Benutzer-Agent kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="8b259-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="8b259-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="8b259-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="8b259-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b259-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8b259-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="8b259-117">Unique</span></span>  <br/> |<span data-ttu-id="8b259-118">Benutzer-Agent-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8b259-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="8b259-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="8b259-119">**UAType**</span></span> <br/> |<span data-ttu-id="8b259-120">smallint</span><span class="sxs-lookup"><span data-stu-id="8b259-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="8b259-121">1 ist ein Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="8b259-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="8b259-122">2 ist ein/V-Konferenz Server.</span><span class="sxs-lookup"><span data-stu-id="8b259-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="8b259-123">4 ist Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8b259-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="8b259-124">8 ist IP Phone.</span><span class="sxs-lookup"><span data-stu-id="8b259-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="8b259-125">16 ist eine Live Meeting-Konsole.</span><span class="sxs-lookup"><span data-stu-id="8b259-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="8b259-126">32 ist ein Bereitstellungs Überprüfungs Tool (Thrombose).</span><span class="sxs-lookup"><span data-stu-id="8b259-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="8b259-127">64 ist Skype for Business Server auf Macintosh-Computern.</span><span class="sxs-lookup"><span data-stu-id="8b259-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="8b259-128">128 ist Skype for Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="8b259-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="8b259-129">256 ist ein Konferenzankündigungsdienst.</span><span class="sxs-lookup"><span data-stu-id="8b259-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="8b259-130">512 ist eine automatische Konferenzzentrale.</span><span class="sxs-lookup"><span data-stu-id="8b259-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="8b259-131">1024 ist eine reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="8b259-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="8b259-132">2048 ist außerhalb der Sprachsteuerung.</span><span class="sxs-lookup"><span data-stu-id="8b259-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

