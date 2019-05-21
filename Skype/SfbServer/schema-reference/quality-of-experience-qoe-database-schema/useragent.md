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
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294586"
---
# <a name="useragent-table"></a><span data-ttu-id="0904a-104">UserAgent-Tabelle</span><span class="sxs-lookup"><span data-stu-id="0904a-104">UserAgent table</span></span>
 
<span data-ttu-id="0904a-105">Die UserAgent-Tabelle ist eine unterstützende Tabelle, in der eine Liste der verschiedenen Benutzer-Agents gespeichert ist, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="0904a-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="0904a-106">Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent</span><span class="sxs-lookup"><span data-stu-id="0904a-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="0904a-107">**Spalte**</span><span class="sxs-lookup"><span data-stu-id="0904a-107">**Column**</span></span>|<span data-ttu-id="0904a-108">**Datentyp**</span><span class="sxs-lookup"><span data-stu-id="0904a-108">**Data Type**</span></span>|<span data-ttu-id="0904a-109">**Schlüssel/Index**</span><span class="sxs-lookup"><span data-stu-id="0904a-109">**Key/Index**</span></span>|<span data-ttu-id="0904a-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="0904a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0904a-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="0904a-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="0904a-112">int</span><span class="sxs-lookup"><span data-stu-id="0904a-112">int</span></span>  <br/> |<span data-ttu-id="0904a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0904a-113">Primary</span></span>  <br/> |<span data-ttu-id="0904a-114">Eindeutige Nummer, die diesen Benutzer-Agent kennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="0904a-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="0904a-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="0904a-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="0904a-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0904a-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0904a-117">Eindeutigen</span><span class="sxs-lookup"><span data-stu-id="0904a-117">Unique</span></span>  <br/> |<span data-ttu-id="0904a-118">Benutzer-Agent-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0904a-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="0904a-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="0904a-119">**UAType**</span></span> <br/> |<span data-ttu-id="0904a-120">smallint</span><span class="sxs-lookup"><span data-stu-id="0904a-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="0904a-121">1 ist ein Vermittlungs Server.</span><span class="sxs-lookup"><span data-stu-id="0904a-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="0904a-122">2 ist ein/V-Konferenz Server.</span><span class="sxs-lookup"><span data-stu-id="0904a-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="0904a-123">4 ist Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="0904a-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="0904a-124">8 ist IP Phone.</span><span class="sxs-lookup"><span data-stu-id="0904a-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="0904a-125">16 ist eine Live Meeting-Konsole.</span><span class="sxs-lookup"><span data-stu-id="0904a-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="0904a-126">32 ist ein Bereitstellungs Überprüfungs Tool (Thrombose).</span><span class="sxs-lookup"><span data-stu-id="0904a-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="0904a-127">64 ist Skype for Business Server auf Macintosh-Computern.</span><span class="sxs-lookup"><span data-stu-id="0904a-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="0904a-128">128 ist Skype for Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="0904a-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="0904a-129">256 ist ein Konferenzankündigungsdienst.</span><span class="sxs-lookup"><span data-stu-id="0904a-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="0904a-130">512 ist eine automatische Konferenzzentrale.</span><span class="sxs-lookup"><span data-stu-id="0904a-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="0904a-131">1024 ist eine reaktionsgruppenanwendung.</span><span class="sxs-lookup"><span data-stu-id="0904a-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="0904a-132">2048 ist außerhalb der Sprachsteuerung.</span><span class="sxs-lookup"><span data-stu-id="0904a-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

