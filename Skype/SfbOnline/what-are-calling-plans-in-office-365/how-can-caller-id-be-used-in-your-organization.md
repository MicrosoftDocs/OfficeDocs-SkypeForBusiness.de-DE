---
title: Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Anrufer-ID kann mithilfe einer Richtlinie aufgerufen CallingLineIdentity für eingehende und ausgehende Anrufe für Benutzer Telefonsystem gesteuert werden.
ms.openlocfilehash: df6c7c053b5dce4ffb1d121a1adbf829efda9943
ms.sourcegitcommit: 60e8365281ec6d780f1b2439bedef0bd71f002d8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "30047897"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="74e69-103">Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="74e69-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="74e69-104">Anrufer-ID kann mithilfe einer Richtlinie aufgerufen CallingLineIdentity für eingehende und ausgehende Anrufe für Benutzer Telefonsystem gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="74e69-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="74e69-105">Die Anrufer-ID-Funktionalität ist für alle Telefonsystem Benutzer unabhängig von PSTN-Anbindung verfügbar:</span><span class="sxs-lookup"><span data-stu-id="74e69-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="74e69-106">Online-PSTN-Anbindung</span><span class="sxs-lookup"><span data-stu-id="74e69-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="74e69-107">Lokale PSTN-Anbindung mit Skype for Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 oder höher)</span><span class="sxs-lookup"><span data-stu-id="74e69-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="74e69-108">Lokale PSTN-Anbindung mit Skype for Business Server (erfordert Skype for Business Server 2015 CU5 oder höher)</span><span class="sxs-lookup"><span data-stu-id="74e69-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="74e69-109">Diese Richtlinie ist in Skype for Business Server 2015 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="74e69-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="74e69-110">Ausgehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="74e69-110">Outbound caller ID</span></span>

<span data-ttu-id="74e69-111">Für die ausgehende PSTN-Anrufer-ID sind drei Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="74e69-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="74e69-112">Die Telefonnummer für den Benutzer, die Standardeinstellung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="74e69-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="74e69-113">Eine Telefonnummer, die als *Servicerufnummer* und *gebührenfreie* Nummer in Ihrem Nummernverzeichnis für Office 365-Anrufpläne klassifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="74e69-113">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory.</span></span> <span data-ttu-id="74e69-114">Sie wird normalerweise einer automatischen Telefonzentrale oder einer Anruf-Warteschleife Ihrer Organisation zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="74e69-114">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="74e69-115">Auf „Anonym" festgelegt</span><span class="sxs-lookup"><span data-stu-id="74e69-115">Set to anonymous.</span></span>
    
<span data-ttu-id="74e69-116">Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:</span><span class="sxs-lookup"><span data-stu-id="74e69-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="74e69-117">Alle Rufnummern, die als *Benutzer* in Ihrem Telefon aufrufen plant klassifiziert werden Zahl Inventar</span><span class="sxs-lookup"><span data-stu-id="74e69-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="74e69-118">Lokale Skype for Business Server-Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="74e69-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="74e69-119">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="74e69-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="74e69-120">Steuerung der ausgehenden Anrufer-ID durch Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="74e69-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="74e69-121">Mit dem Attribut EnableUserOverride können einzelne oder mehrere Benutzer ihre Anrufer-ID-Einstellung auf **Anonym** festlegen.</span><span class="sxs-lookup"><span data-stu-id="74e69-121">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="74e69-122">Dies gilt nur, wenn eine CallingLineIdentity -Richtlinie mit dem CallingIDSubstitute -Parameter LineURI oder Substitute konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="74e69-122">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="74e69-123">Der Standardwert von EnableUserOverride lautet False.</span><span class="sxs-lookup"><span data-stu-id="74e69-123">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="74e69-124">Endbenutzer können ihre Anrufer-ID auf **Anonym** mithilfe der Registerkarte **Einstellungen** in der Skype für Business desktop Client festgelegt **Aufrufe eines Endbenutzers** (sofern durch den Administrator aktiviert), wählen \*\*Ausblenden mein Handy Anzahl und Profil Informationen für alle Anrufe \*\*.</span><span class="sxs-lookup"><span data-stu-id="74e69-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="74e69-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="74e69-125">**Windows**</span></span> <br/> |<span data-ttu-id="74e69-126">**Version**</span><span class="sxs-lookup"><span data-stu-id="74e69-126">**Version**</span></span> <br/> |<span data-ttu-id="74e69-127">**Unterstützt**</span><span class="sxs-lookup"><span data-stu-id="74e69-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="74e69-128">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="74e69-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="74e69-129">Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="74e69-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="74e69-130">Ja</span><span class="sxs-lookup"><span data-stu-id="74e69-130">Yes</span></span>  <br/> |
|<span data-ttu-id="74e69-131">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="74e69-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="74e69-132">First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="74e69-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="74e69-133">Ja</span><span class="sxs-lookup"><span data-stu-id="74e69-133">Yes</span></span>  <br/> |
|<span data-ttu-id="74e69-134">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="74e69-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="74e69-135">Veröffentlichung im verzögerten Kanal am 13. Juni 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="74e69-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="74e69-136">Ja</span><span class="sxs-lookup"><span data-stu-id="74e69-136">Yes</span></span>  <br/> |
|<span data-ttu-id="74e69-137">MSI</span><span class="sxs-lookup"><span data-stu-id="74e69-137">MSI</span></span>  <br/> |<span data-ttu-id="74e69-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="74e69-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="74e69-139">Nein</span><span class="sxs-lookup"><span data-stu-id="74e69-139">No</span></span>  <br/> |
|<span data-ttu-id="74e69-140">Mac</span><span class="sxs-lookup"><span data-stu-id="74e69-140">Mac</span></span>  <br/> |<span data-ttu-id="74e69-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="74e69-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="74e69-142">Nein</span><span class="sxs-lookup"><span data-stu-id="74e69-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="74e69-143">Eingehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="74e69-143">Inbound Caller ID</span></span>

<span data-ttu-id="74e69-144">Mit dem Attribut BlockIncomingCallerID können Sie die Anrufer-ID Für eingehende PSTN-Anrufe blockieren.</span><span class="sxs-lookup"><span data-stu-id="74e69-144">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="74e69-145">Können Sie dieses Attribut festgelegt, aber es ist nicht verfügbar für die Endbenutzer auf der Seite benutzereinstellungen.</span><span class="sxs-lookup"><span data-stu-id="74e69-145">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="74e69-146">Außerdem ist das Attribut zurzeit nur für Online-PSTN-Anbindung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="74e69-146">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="74e69-147">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="74e69-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="74e69-148">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="74e69-148">Related topics</span></span>
[<span data-ttu-id="74e69-149">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="74e69-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="74e69-150">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="74e69-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="74e69-151">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="74e69-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="74e69-152">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="74e69-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="74e69-153">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="74e69-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
