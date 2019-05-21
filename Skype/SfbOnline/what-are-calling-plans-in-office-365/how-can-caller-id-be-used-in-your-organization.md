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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Die Rufnummernanzeige kann für eingehende und ausgehende Anrufe für Telefon System Benutzer unter Verwendung einer Richtlinie mit dem Namen CallingLineIdentity gesteuert werden.
ms.openlocfilehash: 9d15d51d0044ae15b04572f0b64a21912cea720a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305433"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="64036-103">Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="64036-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="64036-104">Die Rufnummernanzeige kann für eingehende und ausgehende Anrufe für Telefon System Benutzer unter Verwendung einer Richtlinie mit dem Namen CallingLineIdentity gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="64036-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="64036-105">Die Rufnummernanzeige Funktion steht allen Telefon System Benutzern unabhängig von der PSTN-Konnektivität zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="64036-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="64036-106">Online-PSTN-Anbindung</span><span class="sxs-lookup"><span data-stu-id="64036-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="64036-107">Lokale PSTN-Anbindung mit Skype for Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 oder höher)</span><span class="sxs-lookup"><span data-stu-id="64036-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="64036-108">Lokale PSTN-Anbindung mit Skype for Business Server (erfordert Skype for Business Server 2015 CU5 oder höher)</span><span class="sxs-lookup"><span data-stu-id="64036-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="64036-109">Diese Richtlinie ist in Skype for Business Server 2015 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="64036-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="64036-110">Ausgehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="64036-110">Outbound caller ID</span></span>

<span data-ttu-id="64036-111">Für die ausgehende PSTN-Anrufer-ID sind drei Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="64036-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="64036-112">Die dem Benutzer zugewiesene Telefonnummer, die der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="64036-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="64036-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="64036-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="64036-115">Auf „Anonym" festgelegt</span><span class="sxs-lookup"><span data-stu-id="64036-115">Set to anonymous.</span></span>
    
<span data-ttu-id="64036-116">Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:</span><span class="sxs-lookup"><span data-stu-id="64036-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="64036-117">Alle Telefonnummern, die in ihren Anrufplänen als *Benutzer* klassifiziert sind Telefonnummern Inventar</span><span class="sxs-lookup"><span data-stu-id="64036-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="64036-118">Lokale Skype for Business Server-Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="64036-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="64036-119">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="64036-119">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="64036-120">Steuerung der ausgehenden Anrufer-ID durch Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="64036-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="64036-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span><span class="sxs-lookup"><span data-stu-id="64036-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="64036-124">Ihre Endbenutzer können Ihre Anrufer-ID auf **Anonym** festlegen, indem Sie auf der Registerkarte **Einstellungen** im Skype for Business-Desktop Client die Option **Anrufe an Endbenutzer** auswählen (sofern vom Administrator aktiviert), die Option \*\*meine Telefonnummer und Profilinformationen für alle Anrufe verbergen auswählen. \*\*.</span><span class="sxs-lookup"><span data-stu-id="64036-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="64036-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="64036-125">**Windows**</span></span> <br/> |<span data-ttu-id="64036-126">**Version**</span><span class="sxs-lookup"><span data-stu-id="64036-126">**Version**</span></span> <br/> |<span data-ttu-id="64036-127">**Unterstützt**</span><span class="sxs-lookup"><span data-stu-id="64036-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="64036-128">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="64036-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="64036-129">Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="64036-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="64036-130">Ja</span><span class="sxs-lookup"><span data-stu-id="64036-130">Yes</span></span>  <br/> |
|<span data-ttu-id="64036-131">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="64036-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="64036-132">First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="64036-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="64036-133">Ja</span><span class="sxs-lookup"><span data-stu-id="64036-133">Yes</span></span>  <br/> |
|<span data-ttu-id="64036-134">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="64036-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="64036-135">Veröffentlichung im verzögerten Kanal am 13. Juni 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="64036-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="64036-136">Ja</span><span class="sxs-lookup"><span data-stu-id="64036-136">Yes</span></span>  <br/> |
|<span data-ttu-id="64036-137">MSI</span><span class="sxs-lookup"><span data-stu-id="64036-137">MSI</span></span>  <br/> |<span data-ttu-id="64036-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="64036-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="64036-139">Nein</span><span class="sxs-lookup"><span data-stu-id="64036-139">No</span></span>  <br/> |
|<span data-ttu-id="64036-140">Mac</span><span class="sxs-lookup"><span data-stu-id="64036-140">Mac</span></span>  <br/> |<span data-ttu-id="64036-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="64036-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="64036-142">Nein</span><span class="sxs-lookup"><span data-stu-id="64036-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="64036-143">Eingehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="64036-143">Inbound Caller ID</span></span>

<span data-ttu-id="64036-p103">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.</span><span class="sxs-lookup"><span data-stu-id="64036-p103">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="64036-147">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="64036-147">To set the outbound caller ID, see [Set the Caller ID for a user](set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="64036-148">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="64036-148">Related topics</span></span>
[<span data-ttu-id="64036-149">Allgemeine Fragen zum Übertragen von Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="64036-149">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="64036-150">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="64036-150">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="64036-151">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="64036-151">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="64036-152">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="64036-152">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="64036-153">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="64036-153">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
