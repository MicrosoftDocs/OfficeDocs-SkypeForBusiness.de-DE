---
title: UserAgent-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Die UserAgent-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer-Agenten gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben. Jeder Datensatz in der Tabelle steht für eine Benutzer-agent
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893104"
---
# <a name="useragent-table"></a><span data-ttu-id="ffe59-104">UserAgent-Tabelle</span><span class="sxs-lookup"><span data-stu-id="ffe59-104">UserAgent table</span></span>
 
<span data-ttu-id="ffe59-105">Die UserAgent-Tabelle ist eine Tabelle, die eine Liste der verschiedenen Benutzer-Agenten gespeichert, die in der Datenbank aufgezeichnet Sitzungen teilgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="ffe59-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ffe59-106">Jeder Datensatz in der Tabelle steht für eine Benutzer-agent</span><span class="sxs-lookup"><span data-stu-id="ffe59-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="ffe59-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="ffe59-107">**Column**</span></span>|<span data-ttu-id="ffe59-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="ffe59-108">**Data Type**</span></span>|<span data-ttu-id="ffe59-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="ffe59-109">**Key/Index**</span></span>|<span data-ttu-id="ffe59-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="ffe59-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ffe59-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="ffe59-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="ffe59-112">int</span><span class="sxs-lookup"><span data-stu-id="ffe59-112">int</span></span>  <br/> |<span data-ttu-id="ffe59-113">Primary</span><span class="sxs-lookup"><span data-stu-id="ffe59-113">Primary</span></span>  <br/> |<span data-ttu-id="ffe59-114">Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ffe59-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="ffe59-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="ffe59-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="ffe59-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ffe59-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ffe59-117">Eindeutige</span><span class="sxs-lookup"><span data-stu-id="ffe59-117">Unique</span></span>  <br/> |<span data-ttu-id="ffe59-118">Benutzeragenten-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ffe59-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="ffe59-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="ffe59-119">**UAType**</span></span> <br/> |<span data-ttu-id="ffe59-120">smallint</span><span class="sxs-lookup"><span data-stu-id="ffe59-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="ffe59-121">1: Vermittlungsserver.</span><span class="sxs-lookup"><span data-stu-id="ffe59-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="ffe59-122">2 ist die A / V-Konferenzserver.</span><span class="sxs-lookup"><span data-stu-id="ffe59-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="ffe59-123">4 ist Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="ffe59-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="ffe59-124">8: IP-Telefon</span><span class="sxs-lookup"><span data-stu-id="ffe59-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="ffe59-125">16 ist Live Meeting-Konsole.</span><span class="sxs-lookup"><span data-stu-id="ffe59-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="ffe59-126">32 ist Deployment Validation Tool (DVT).</span><span class="sxs-lookup"><span data-stu-id="ffe59-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="ffe59-127">64: Skype für Business Server auf Macintosh-Computern.</span><span class="sxs-lookup"><span data-stu-id="ffe59-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="ffe59-128">128 ist Skype für Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="ffe59-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="ffe59-129">256 ist konferenzankündigungsdienst.</span><span class="sxs-lookup"><span data-stu-id="ffe59-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="ffe59-130">512 ist die automatische Konferenzzentrale.</span><span class="sxs-lookup"><span data-stu-id="ffe59-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="ffe59-131">1024 ist die Anwendung "Reaktionsgruppe".</span><span class="sxs-lookup"><span data-stu-id="ffe59-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="ffe59-132">2048 ist Lautstärkeregler.</span><span class="sxs-lookup"><span data-stu-id="ffe59-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

