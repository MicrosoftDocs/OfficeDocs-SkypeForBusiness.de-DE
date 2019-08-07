---
title: Anrufpläne in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: Startseite des Anruf Plans
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b9d1a012c545dbaf8f8c65d87f58718bda13946
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2019
ms.locfileid: "34381837"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="63282-103">Welcher Anrufplan ist das richtige für Sie?</span><span class="sxs-lookup"><span data-stu-id="63282-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="63282-104">Sie haben die ersten [Schritte](get-started-with-teams-quick-start.md)abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="63282-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="63282-105">Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="63282-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="63282-106">Vielleichthaben Sie [Besprechungen #a0 Konferenzen](deploy-meetings-microsoft-teams-landing-page.md)bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="63282-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="63282-107">Nun können Sie Cloud-sprach Auslastungen hinzufügen, und Sie haben sich entschieden, Microsoft Phone System mit einem Anrufplan zu verwenden, um eine Verbindung mit dem öffentlichen Telefonnetz (PSTN) herzustellen.</span><span class="sxs-lookup"><span data-stu-id="63282-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="63282-108">In diesem Artikel werden die wichtigsten Bereitstellungsentscheidungen für Anrufpläne sowie weitere Überlegungen beschrieben, die Sie basierend auf den Anforderungen Ihrer Organisation möglicherweise konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="63282-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="63282-109">Sie sollten auch [Cloud-VoIP in Microsoft Teams](cloud-voice-landing-page.md) lesen, um weitere Informationen zu den Cloud-sprach angeboten von Microsoft zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="63282-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="63282-110">Weitere Informationen zu Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="63282-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="63282-111">In den folgenden Artikeln finden Sie weitere Informationen zur Bereitstellung und Verwendung von Microsoft-Anrufplänen:</span><span class="sxs-lookup"><span data-stu-id="63282-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="63282-112">Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="63282-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="63282-113">Anrufpläne für Office 365</span><span class="sxs-lookup"><span data-stu-id="63282-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="63282-114">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="63282-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="63282-115">Zentrale Entscheidungen bei der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="63282-115">Core deployment decisions</span></span>

<span data-ttu-id="63282-116">Wenn Sie Microsoft als Telefonnetzbetreiber verwenden möchten, müssen Sie Lizenzen für den Anrufplan erwerben und diese ihren Telefon System Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="63282-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="63282-117">Es stehen zwei Arten von Anrufplänen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="63282-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="63282-118">Tarife für Inlandsanrufe</span><span class="sxs-lookup"><span data-stu-id="63282-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="63282-119">Tarife für Inlands-und Auslandsgespräche</span><span class="sxs-lookup"><span data-stu-id="63282-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="63282-120">Frage</span><span class="sxs-lookup"><span data-stu-id="63282-120">Ask yourself</span></span>|<span data-ttu-id="63282-121">Aktion</span><span class="sxs-lookup"><span data-stu-id="63282-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="63282-122">Sind Anrufpläne in meinem Gebiet verfügbar?</span><span class="sxs-lookup"><span data-stu-id="63282-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="63282-123">An welchen Speicherorten des Benutzers wird ein Anruf Plan Dienst durchgestellt?</span><span class="sxs-lookup"><span data-stu-id="63282-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="63282-124">Weitere Informationen finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenz-und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="63282-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="63282-125">Benötigen meine Nutzer Auslandsanrufe?</span><span class="sxs-lookup"><span data-stu-id="63282-125">Do my users need international calling?</span></span> | <span data-ttu-id="63282-126">Weitere Informationen finden Sie unter [Aufrufen von Plänen für Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="63282-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="63282-127">Verfügen meine Benutzer über Anruf Plan Lizenzen?</span><span class="sxs-lookup"><span data-stu-id="63282-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="63282-128">Informationen zum kaufen und Zuweisen von Lizenzen finden Sie unter [Schritt 2: erwerben und Zuweisen von Lizenzen](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="63282-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="63282-129">Haben meine Benutzer jeweils eine direkte Durchwahl (DID)?</span><span class="sxs-lookup"><span data-stu-id="63282-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="63282-130">Informationen zum Abrufen von Telefonnummern finden Sie unter [Schritt 3: Abrufen von Telefonnummern](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="63282-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="63282-131">Übertragen von Telefonnummern zu Office 365</span><span class="sxs-lookup"><span data-stu-id="63282-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="63282-132">Es ist einfach, ihre Telefonnummern von Ihrem aktuellen Dienstanbieter in Teams zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="63282-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="63282-133">Nachdem Sie Ihre Telefonnummern in Teams portiert haben, wird Microsoft Ihr Dienstanbieter und berechnet Ihnen diese Telefonnummern.</span><span class="sxs-lookup"><span data-stu-id="63282-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="63282-134">Weitere Informationen finden Sie unter [übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="63282-134">For more information, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="63282-135">Telefonnummern und Notfallstandorte</span><span class="sxs-lookup"><span data-stu-id="63282-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="63282-136">Bei Anrufplänen in Office 365 muss jeder Benutzer in Ihrer Organisation über eine eindeutige direkte Durchwahl (DID)-Telefonnummer und eine entsprechende validierte Notfalladresse verfügen.</span><span class="sxs-lookup"><span data-stu-id="63282-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="63282-137">Sie können auch einen Notfall Standort innerhalb der Notfalladresse angeben (beispielsweise eine Büro-oder Boden Nummer).</span><span class="sxs-lookup"><span data-stu-id="63282-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="63282-138">Frage</span><span class="sxs-lookup"><span data-stu-id="63282-138">Ask yourself</span></span>|<span data-ttu-id="63282-139">Aktion</span><span class="sxs-lookup"><span data-stu-id="63282-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="63282-140">Wie detailliert soll die Notfalladresse und die Standortinformationen sein?</span><span class="sxs-lookup"><span data-stu-id="63282-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="63282-141">Weitere Informationen finden Sie unter [Was sind Notfall Standorte, Adressen und Anrufweiterleitung?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="63282-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="63282-142">Identität des Anrufs</span><span class="sxs-lookup"><span data-stu-id="63282-142">Calling identity</span></span>

<span data-ttu-id="63282-143">Standardmäßig verwenden alle ausgehenden Anrufe die zugewiesene Telefonnummer als Anruf Identität (Rufnummernanzeige).</span><span class="sxs-lookup"><span data-stu-id="63282-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="63282-144">Der Empfänger des Anrufs kann den Anrufer schnell identifizieren und entscheiden, ob er den Anruf annehmen oder ablehnen möchte.</span><span class="sxs-lookup"><span data-stu-id="63282-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="63282-145">Frage</span><span class="sxs-lookup"><span data-stu-id="63282-145">Ask yourself</span></span>|<span data-ttu-id="63282-146">Aktion</span><span class="sxs-lookup"><span data-stu-id="63282-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="63282-147">Soll die Rufnummernanzeige maskiert oder deaktiviert werden?</span><span class="sxs-lookup"><span data-stu-id="63282-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="63282-148">Informationen zum Ändern oder Blockieren der Rufnummernanzeige finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="63282-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




