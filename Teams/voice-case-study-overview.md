---
title: Teams Voice Contoso-Fallstudie
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Teams Voice Case Study für Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701223"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="178cf-103">Contoso-Fallstudie: Übersicht über die VoIP-Migration von Teams</span><span class="sxs-lookup"><span data-stu-id="178cf-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="178cf-104">In diesem Artikel wird eine Fallstudie vorgestellt, die zeigt, wie eine fiktive Multi-National Corporation, Contoso, eine Teams-Sprachlösung für Ihre Organisation implementiert hat.</span><span class="sxs-lookup"><span data-stu-id="178cf-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="178cf-105">Contoso hat Microsoft 365 Enterprise bereitgestellt und wichtige Entwurfsentscheidungen und Implementierungsdetails für folgende Themen behandelt: Netzwerk, Identität, Windows 10 Enterprise, Office 365 ProPlus, Verwaltung mobiler Geräte, Informationsschutz, Sicherheit, Upgrade von Skype for Business auf Teams, Telefon System und Audiokonferenzen.</span><span class="sxs-lookup"><span data-stu-id="178cf-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="178cf-106">In diesem Artikel wird erläutert, wie Contoso ihre lokalen Benutzer in Teams für einheitliche Kommunikation, Zusammenarbeit und Sprache migriert hat.</span><span class="sxs-lookup"><span data-stu-id="178cf-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="178cf-107">Hintergrundinformationen dazu, wie Contoso Ihre digitale Transformation mithilfe der Microsoft-Cloud-Dienste beschleunigt hat, finden Sie in den wichtigsten Artikeln, die mit der [Übersicht über die Contoso-Fallstudie](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)beginnen.</span><span class="sxs-lookup"><span data-stu-id="178cf-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="178cf-108">In den wichtigsten Artikeln finden Sie Informationen zu den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="178cf-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="178cf-109">Anforderungen der IT-Infrastruktur von Contoso</span><span class="sxs-lookup"><span data-stu-id="178cf-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="178cf-110">Netzwerk</span><span class="sxs-lookup"><span data-stu-id="178cf-110">Networking</span></span>
- <span data-ttu-id="178cf-111">Identität </span><span class="sxs-lookup"><span data-stu-id="178cf-111">Identity</span></span>
- <span data-ttu-id="178cf-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="178cf-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="178cf-113">Office 365 pro Plus</span><span class="sxs-lookup"><span data-stu-id="178cf-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="178cf-114">Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="178cf-114">Mobile device management</span></span>
- <span data-ttu-id="178cf-115">Informationsschutz</span><span class="sxs-lookup"><span data-stu-id="178cf-115">Information protection</span></span>
- <span data-ttu-id="178cf-116">Zusammenfassung der Microsoft 365 Enterprise-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="178cf-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="178cf-117">Team für ein Top-Secret-Projekt</span><span class="sxs-lookup"><span data-stu-id="178cf-117">Team for a top-secret project</span></span>
- <span data-ttu-id="178cf-118">SharePoint Online-Website für hoch vertrauliche digitale Ressourcen</span><span class="sxs-lookup"><span data-stu-id="178cf-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="178cf-119">Informationen zum Planen eines Upgrades finden Sie unter [Erste Schritte mit dem Upgrade für Microsoft Teams](upgrade-start-here.md).</span><span class="sxs-lookup"><span data-stu-id="178cf-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="178cf-120">Contoso-Geschäftsziele für Teams</span><span class="sxs-lookup"><span data-stu-id="178cf-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="178cf-121">Um Ihre lokalen Benutzer zu Teams für Unified Communication, Collaboration und Voice zu migrieren, hat Contoso die folgenden Unternehmensziele beschlossen:</span><span class="sxs-lookup"><span data-stu-id="178cf-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="178cf-122">Teams-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="178cf-122">Teams enablement</span></span> 

  <span data-ttu-id="178cf-123">Das Unified Communication-und Zusammenarbeits Team von Contoso hat Teams mit den richtigen Richtlinien für die Steuerung und die sichere interne und externe Zusammenarbeit aktiviert.</span><span class="sxs-lookup"><span data-stu-id="178cf-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="178cf-124">Upgrade von Skype for Business auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="178cf-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="178cf-125">Skype for Business wurde in contoso umfassend bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="178cf-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="178cf-126">Mit der Notwendigkeit, Legacy-Systeme zu entfernen, beschloss contoso, Ihre Skype for Business-Benutzer auf Teams zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="178cf-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="178cf-127">Weitere Informationen finden Sie unter [contoso-Fallstudie: Upgradeplan für Teams](voice-case-study-migration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="178cf-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="178cf-128">Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="178cf-128">Phone System</span></span>  

  <span data-ttu-id="178cf-129">Skype for Business mit Enterprise-VoIP wurde in contoso umfassend bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="178cf-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="178cf-130">Mit der Notwendigkeit, Legacy-Systeme zu entfernen, die den nächsten Hop für Ihre Vermittlungsserver waren, migrierte Contoso Ihre Skype for Business Enterprise-VoIP-Benutzer in das Telefon System.</span><span class="sxs-lookup"><span data-stu-id="178cf-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="178cf-131">Contoso-Websites haben Microsoft-Anrufplan, direktes Telefon System-Routing oder eine Kombination aus beidem verwendet.</span><span class="sxs-lookup"><span data-stu-id="178cf-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="178cf-132">Weitere Informationen finden Sie unter [contoso-Fallstudie: Telefon System](voice-case-study-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="178cf-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="178cf-133">Standortbasiertes Routing</span><span class="sxs-lookup"><span data-stu-id="178cf-133">Location-Based Routing</span></span> 

  <span data-ttu-id="178cf-134">Mit Office-Standorten in Telefon regulierten Ländern musste Contoso das Location-Based-Routing, das in Skype for Business vorhanden war, in der Bereitstellung Ihres Telefonsystems neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="178cf-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="178cf-135">Weitere Informationen finden Sie unter [contoso-Fallstudie: Location-Based-Routing](voice-case-study-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="178cf-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="178cf-136">Notrufe</span><span class="sxs-lookup"><span data-stu-id="178cf-136">Emergency Calling</span></span> 

  <span data-ttu-id="178cf-137">Bei der Implementierung von Direct Routing richtete Contoso Notrufe mit genehmigten Drittanbietern ein.</span><span class="sxs-lookup"><span data-stu-id="178cf-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="178cf-138">Weitere Informationen finden Sie unter [contoso-Fallstudie: Notrufe](voice-case-study-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="178cf-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="178cf-139">Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="178cf-139">Audio Conferencing</span></span> 

  <span data-ttu-id="178cf-140">Contoso richtete Audiokonferenz-Dienstnummern ein, die im SIP-Stamm Ihres PSTN-Anbieters gehostet wurden.</span><span class="sxs-lookup"><span data-stu-id="178cf-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="178cf-141">Weitere Informationen finden Sie unter [contoso-Fallstudie: Audiokonferenzen](voice-case-study-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="178cf-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="178cf-142">Lokale Medienoptimierung</span><span class="sxs-lookup"><span data-stu-id="178cf-142">Local Media Optimization</span></span> 

  <span data-ttu-id="178cf-143">Contoso nutzte die lokale Medienoptimierung an Orten, an denen Sie über einen direkten Routen trunk zu einem Microsoft Phone-System verfügten, das von Remotestandorten genutzt wurde.</span><span class="sxs-lookup"><span data-stu-id="178cf-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="178cf-144">Weitere Informationen finden Sie unter [Planen der lokalen Medienoptimierung](direct-routing-media-optimization.md) und [Konfigurieren der lokalen Medienoptimierung](direct-routing-media-optimization-configure.md).</span><span class="sxs-lookup"><span data-stu-id="178cf-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="178cf-145">Automatische Telefonzentralen und Anrufwarteschlangen</span><span class="sxs-lookup"><span data-stu-id="178cf-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="178cf-146">Als Ergebnis von Covid-19 wollte Contoso die Unterstützung der Rezeption zur Verfügung stellen, während die Mitarbeiter Remote arbeiten.</span><span class="sxs-lookup"><span data-stu-id="178cf-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="178cf-147">Contoso hat automatische Telefonzentralen und Anrufwarteschlangen verwendet, um eingehende Anrufe an die Telefonnummer Ihres Rezeptionisten zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="178cf-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="178cf-148">Weitere Informationen finden Sie unter [contoso-Fallstudie: automatische Telefonzentralen und Anrufwarteschlangen](voice-case-study-call-queues.md).</span><span class="sxs-lookup"><span data-stu-id="178cf-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


