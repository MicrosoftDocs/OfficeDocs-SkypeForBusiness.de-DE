---
title: Aufrufen von Plänen in Microsoft-Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: crowe
search.appverid: MET150
description: Aufrufen von Plan Zielseite
appliesto:
- Microsoft Teams
ms.openlocfilehash: d3299460eeb504c53737d163a6026081775fce5d
ms.sourcegitcommit: 3a0b90af8eb3c10579b9eea7837c60a19a577881
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2019
ms.locfileid: "29595400"
---
# <a name="phone-system-with-calling-plans"></a><span data-ttu-id="1c14d-103">Telefonsystem mit Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="1c14d-103">Phone System with Calling Plans</span></span> 

<span data-ttu-id="1c14d-104">Sie haben das [Erste Schritte](get-started-with-teams-quick-start.md)abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1c14d-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="1c14d-105">Sie haben, Teams mit [Chat, Teams, Kanäle, &-apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1c14d-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="1c14d-106">Vielleicht haben Sie [Besprechungen & Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="1c14d-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="1c14d-107">Sie können nun Cloud VoIP Arbeitslasten hinzufügen, und Sie haben entschieden, Microsoft Telefonsystem mit Aufrufen planen Verbindung zu im Public Switched Telephone Network, (PSTN) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c14d-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="1c14d-108">Dieser Artikel beschreibt Core Bereitstellung Entscheidungen für das Aufrufen von plant sowie weitere Aspekte zu beachten, dass Sie möglicherweise konfigurieren möchten, basierend auf der Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1c14d-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="1c14d-109">[Cloud-VoIP in Microsoft-Teams,](cloud-voice-landing-page.md) lesen Sie auch weitere Informationen zu VoIP Cloudlösungen von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c14d-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="1c14d-110">Erfahren Sie mehr über die Pläne aufrufen</span><span class="sxs-lookup"><span data-stu-id="1c14d-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="1c14d-111">Die folgenden Artikel enthalten weitere Informationen zur Bereitstellung und Verwendung von Microsoft plant aufrufen:</span><span class="sxs-lookup"><span data-stu-id="1c14d-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="1c14d-112">Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="1c14d-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="1c14d-113">Anrufpläne für Office 365</span><span class="sxs-lookup"><span data-stu-id="1c14d-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="1c14d-114">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="1c14d-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="1c14d-115">Zentrale Bereitstellung Entscheidungen</span><span class="sxs-lookup"><span data-stu-id="1c14d-115">Core deployment decisions</span></span>

<span data-ttu-id="1c14d-116">Um Microsoft als Ihr Netzbetreiber Telefonie verwenden, müssen Sie planen der Aufruf von Lizenzen zu erhalten, und weisen Sie diese den Benutzern Telefonsystem.</span><span class="sxs-lookup"><span data-stu-id="1c14d-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="1c14d-117">Es gibt zwei Arten von Aufrufen Pläne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="1c14d-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="1c14d-118">Anrufe von nationalen Pläne</span><span class="sxs-lookup"><span data-stu-id="1c14d-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="1c14d-119">Aufrufen von nationalen und internationalen Pläne</span><span class="sxs-lookup"><span data-stu-id="1c14d-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="1c14d-120">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="1c14d-120">Ask yourself</span></span>|<span data-ttu-id="1c14d-121">Aktion</span><span class="sxs-lookup"><span data-stu-id="1c14d-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="1c14d-122">Stehen plant aufrufen im Bereich Meine?</span><span class="sxs-lookup"><span data-stu-id="1c14d-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="1c14d-123">Welche Benutzerstandorte müssen Service aufrufen planen?</span><span class="sxs-lookup"><span data-stu-id="1c14d-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="1c14d-124">Weitere Informationen finden Sie unter [Ländern und Regionen Verfügbarkeit für Audiokonferenzen und plant aufrufen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="1c14d-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="1c14d-125">Benötigen die Benutzer internationaler?</span><span class="sxs-lookup"><span data-stu-id="1c14d-125">Do my users need international calling?</span></span> | <span data-ttu-id="1c14d-126">Weitere Informationen finden Sie unter [Aufrufen für Office 365 Plans](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1c14d-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="1c14d-127">Müssen meine Benutzer Lizenzen plant aufrufen?</span><span class="sxs-lookup"><span data-stu-id="1c14d-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="1c14d-128">Zu erwerben, Lizenzen zuweisen, finden Sie unter [Schritt2: kaufen und Zuweisen von Lizenzen](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="1c14d-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="1c14d-129">Sind meine Benutzer ein direkt nach innen (DID) Telefonnummer vorhanden?</span><span class="sxs-lookup"><span data-stu-id="1c14d-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="1c14d-130">Wenn Sie Rufnummern erhalten möchten, finden Sie unter [Schritt 3: Abrufen von Telefonnummern](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="1c14d-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="1c14d-131">Übertragen von Telefonnummern zu Office 365</span><span class="sxs-lookup"><span data-stu-id="1c14d-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="1c14d-132">Es ist einfach, Ihre Rufnummern aus Ihren aktuellen Dienstanbieter Teams übertragen.</span><span class="sxs-lookup"><span data-stu-id="1c14d-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="1c14d-133">Nachdem Sie Ihre Rufnummern Teams port, wird Microsoft Ihr Dienstanbieter und Sie für diese Nummern Rechnung wird.</span><span class="sxs-lookup"><span data-stu-id="1c14d-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="1c14d-134">Weitere Informationen finden Sie unter [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1c14d-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="1c14d-135">Telefonnummern und Notfallstandorte</span><span class="sxs-lookup"><span data-stu-id="1c14d-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="1c14d-136">Mit Aufrufen in Office 365-Pläne () jedem Benutzer in Ihrer Organisation muss eine eindeutige nach innen Durchwahl Anzahl und eine entsprechende überprüfte Notfall Adresse Telefon.</span><span class="sxs-lookup"><span data-stu-id="1c14d-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="1c14d-137">Sie können auch einen Notfall Ort innerhalb der Notfall Adresse (zum Beispiel geschäftliche Rufnummer oder Floor-Nummer) angeben.</span><span class="sxs-lookup"><span data-stu-id="1c14d-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="1c14d-138">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="1c14d-138">Ask yourself</span></span>|<span data-ttu-id="1c14d-139">Aktion</span><span class="sxs-lookup"><span data-stu-id="1c14d-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="1c14d-140">Wie detailliert soll ich die Notfall-Adresse und den Ort Informationen werden?</span><span class="sxs-lookup"><span data-stu-id="1c14d-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="1c14d-141">Weitere Informationen finden Sie unter [Was notfallstandorten, Adressen und Anrufrouting sind?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="1c14d-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="1c14d-142">Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="1c14d-142">Calling identity</span></span>

<span data-ttu-id="1c14d-143">Alle ausgehenden Anrufe verwenden standardmäßig die zugewiesene Telefonnummer als aufrufende Identität (Anrufer-ID).</span><span class="sxs-lookup"><span data-stu-id="1c14d-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="1c14d-144">Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.</span><span class="sxs-lookup"><span data-stu-id="1c14d-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="1c14d-145">Fragen Sie sich</span><span class="sxs-lookup"><span data-stu-id="1c14d-145">Ask yourself</span></span>|<span data-ttu-id="1c14d-146">Aktion</span><span class="sxs-lookup"><span data-stu-id="1c14d-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="1c14d-147">Soll so aktivieren oder Deaktivieren der Anrufer-ID werden?</span><span class="sxs-lookup"><span data-stu-id="1c14d-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="1c14d-148">Ändern oder die Anrufer-ID zu blockieren, finden Sie unter [Legen Sie die Anrufer-ID für einen Benutzer](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="1c14d-148">To change or block the caller ID, see [Set the caller ID for a user](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user).</span></span> |
|||




