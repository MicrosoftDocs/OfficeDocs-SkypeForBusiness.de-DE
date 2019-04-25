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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229887"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="a3569-103">Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a3569-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="a3569-104">Anrufer-ID kann mithilfe einer Richtlinie aufgerufen CallingLineIdentity für eingehende und ausgehende Anrufe für Benutzer Telefonsystem gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="a3569-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="a3569-105">Die Anrufer-ID-Funktionalität ist für alle Telefonsystem Benutzer unabhängig von PSTN-Anbindung verfügbar:</span><span class="sxs-lookup"><span data-stu-id="a3569-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="a3569-106">Online-PSTN-Anbindung</span><span class="sxs-lookup"><span data-stu-id="a3569-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="a3569-107">Lokale PSTN-Anbindung mit Skype for Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 oder höher)</span><span class="sxs-lookup"><span data-stu-id="a3569-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="a3569-108">Lokale PSTN-Anbindung mit Skype for Business Server (erfordert Skype for Business Server 2015 CU5 oder höher)</span><span class="sxs-lookup"><span data-stu-id="a3569-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="a3569-109">Diese Richtlinie ist in Skype for Business Server 2015 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a3569-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="a3569-110">Ausgehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="a3569-110">Outbound caller ID</span></span>

<span data-ttu-id="a3569-111">Für die ausgehende PSTN-Anrufer-ID sind drei Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="a3569-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="a3569-112">Die Telefonnummer für den Benutzer, die Standardeinstellung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a3569-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="a3569-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="a3569-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="a3569-115">Auf „Anonym" festgelegt</span><span class="sxs-lookup"><span data-stu-id="a3569-115">Set to anonymous.</span></span>
    
<span data-ttu-id="a3569-116">Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:</span><span class="sxs-lookup"><span data-stu-id="a3569-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="a3569-117">Alle Rufnummern, die als *Benutzer* in Ihrem Telefon aufrufen plant klassifiziert werden Zahl Inventar</span><span class="sxs-lookup"><span data-stu-id="a3569-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="a3569-118">Lokale Skype for Business Server-Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="a3569-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="a3569-119">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="a3569-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="a3569-120">Steuerung der ausgehenden Anrufer-ID durch Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="a3569-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="a3569-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span><span class="sxs-lookup"><span data-stu-id="a3569-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="a3569-124">Endbenutzer können ihre Anrufer-ID auf **Anonym** mithilfe der Registerkarte **Einstellungen** in der Skype für Business desktop Client festgelegt **Aufrufe eines Endbenutzers** (sofern durch den Administrator aktiviert), wählen \*\*Ausblenden mein Handy Anzahl und Profil Informationen für alle Anrufe \*\*.</span><span class="sxs-lookup"><span data-stu-id="a3569-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="a3569-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="a3569-125">**Windows**</span></span> <br/> |<span data-ttu-id="a3569-126">**Version**</span><span class="sxs-lookup"><span data-stu-id="a3569-126">**Version**</span></span> <br/> |<span data-ttu-id="a3569-127">**Unterstützt**</span><span class="sxs-lookup"><span data-stu-id="a3569-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="a3569-128">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="a3569-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a3569-129">Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="a3569-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="a3569-130">Ja</span><span class="sxs-lookup"><span data-stu-id="a3569-130">Yes</span></span>  <br/> |
|<span data-ttu-id="a3569-131">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="a3569-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a3569-132">First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="a3569-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="a3569-133">Ja</span><span class="sxs-lookup"><span data-stu-id="a3569-133">Yes</span></span>  <br/> |
|<span data-ttu-id="a3569-134">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="a3569-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="a3569-135">Veröffentlichung im verzögerten Kanal am 13. Juni 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="a3569-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="a3569-136">Ja</span><span class="sxs-lookup"><span data-stu-id="a3569-136">Yes</span></span>  <br/> |
|<span data-ttu-id="a3569-137">MSI</span><span class="sxs-lookup"><span data-stu-id="a3569-137">MSI</span></span>  <br/> |<span data-ttu-id="a3569-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a3569-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="a3569-139">Nein</span><span class="sxs-lookup"><span data-stu-id="a3569-139">No</span></span>  <br/> |
|<span data-ttu-id="a3569-140">Mac</span><span class="sxs-lookup"><span data-stu-id="a3569-140">Mac</span></span>  <br/> |<span data-ttu-id="a3569-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a3569-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="a3569-142">Nein</span><span class="sxs-lookup"><span data-stu-id="a3569-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="a3569-143">Eingehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="a3569-143">Inbound Caller ID</span></span>

<span data-ttu-id="a3569-p103">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.</span><span class="sxs-lookup"><span data-stu-id="a3569-p103">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="a3569-147">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="a3569-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a3569-148">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a3569-148">Related topics</span></span>
[<span data-ttu-id="a3569-149">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="a3569-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="a3569-150">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="a3569-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="a3569-151">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="a3569-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="a3569-152">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="a3569-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="a3569-153">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="a3569-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
