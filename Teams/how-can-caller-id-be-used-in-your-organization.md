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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: Die Rufnummernanzeige kann für eingehende und ausgehende Anrufe für Telefon System Benutzer unter Verwendung einer Richtlinie mit dem Namen CallingLineIdentity gesteuert werden.
ms.openlocfilehash: af578cf92f6c19e8ac612dfe8301914c9e55833b
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836307"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="0069e-103">Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="0069e-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="0069e-104">Die Rufnummernanzeige kann für eingehende und ausgehende Anrufe für Telefon System Benutzer unter Verwendung einer Richtlinie mit dem Namen CallingLineIdentity gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="0069e-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="0069e-105">Die Rufnummernanzeige Funktion steht allen Telefon System Benutzern unabhängig von der PSTN-Konnektivität zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="0069e-105">The Caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="0069e-106">Online-PSTN-Anbindung</span><span class="sxs-lookup"><span data-stu-id="0069e-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="0069e-107">Lokale PSTN-Anbindung mit Skype for Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 oder höher)</span><span class="sxs-lookup"><span data-stu-id="0069e-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="0069e-108">Lokale PSTN-Anbindung mit Skype for Business Server (erfordert Skype for Business Server 2015 CU5 oder höher)</span><span class="sxs-lookup"><span data-stu-id="0069e-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="0069e-109">Diese Richtlinie ist in Skype for Business Server 2015 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0069e-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="0069e-110">Ausgehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="0069e-110">Outbound caller ID</span></span>

<span data-ttu-id="0069e-111">Für die ausgehende PSTN-Anrufer-ID sind drei Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="0069e-111">There are three options available for outbound PSTN Caller ID:</span></span>
  
- <span data-ttu-id="0069e-112">Die dem Benutzer zugewiesene Telefonnummer, die der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="0069e-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="0069e-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="0069e-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="0069e-115">Auf „Anonym" festgelegt</span><span class="sxs-lookup"><span data-stu-id="0069e-115">Set to anonymous.</span></span>
    
<span data-ttu-id="0069e-116">Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:</span><span class="sxs-lookup"><span data-stu-id="0069e-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="0069e-117">Alle Telefonnummern, die in ihren Anrufplänen als *Benutzer* klassifiziert sind Telefonnummern Inventar</span><span class="sxs-lookup"><span data-stu-id="0069e-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="0069e-118">Lokale Skype for Business Server-Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="0069e-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="0069e-119">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="0069e-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="0069e-120">Steuerung der ausgehenden Anrufer-ID durch Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="0069e-120">End User Control of Outbound Caller ID</span></span>

<span data-ttu-id="0069e-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span><span class="sxs-lookup"><span data-stu-id="0069e-p102">The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="0069e-124">Ihre Endbenutzer können Ihre Rufnummernanzeige auf **Anonym** festlegen, indem Sie auf der Registerkarte **Einstellungen** im Skype for Business-Desktop Client die Option **Anrufe an Endbenutzer** auswählen (sofern vom Administrator aktiviert) die Option **meine Telefonnummer und Profilinformationen für alle Anrufe verbergen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="0069e-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="0069e-125">**Windows**</span><span class="sxs-lookup"><span data-stu-id="0069e-125">**Windows**</span></span> <br/> |<span data-ttu-id="0069e-126">**Version**</span><span class="sxs-lookup"><span data-stu-id="0069e-126">**Version**</span></span> <br/> |<span data-ttu-id="0069e-127">**Unterstützt**</span><span class="sxs-lookup"><span data-stu-id="0069e-127">**Supported**</span></span> <br/> |
|<span data-ttu-id="0069e-128">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="0069e-128">Click-to-Run</span></span>  <br/> |<span data-ttu-id="0069e-129">Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="0069e-129">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="0069e-130">Ja</span><span class="sxs-lookup"><span data-stu-id="0069e-130">Yes</span></span>  <br/> |
|<span data-ttu-id="0069e-131">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="0069e-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="0069e-132">First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="0069e-132">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="0069e-133">Ja</span><span class="sxs-lookup"><span data-stu-id="0069e-133">Yes</span></span>  <br/> |
|<span data-ttu-id="0069e-134">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="0069e-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="0069e-135">Veröffentlichung im verzögerten Kanal am 13. Juni 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="0069e-135">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="0069e-136">Ja</span><span class="sxs-lookup"><span data-stu-id="0069e-136">Yes</span></span>  <br/> |
|<span data-ttu-id="0069e-137">MSI</span><span class="sxs-lookup"><span data-stu-id="0069e-137">MSI</span></span>  <br/> |<span data-ttu-id="0069e-138">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0069e-138">Skype for Business</span></span>  <br/> |<span data-ttu-id="0069e-139">Nein</span><span class="sxs-lookup"><span data-stu-id="0069e-139">No</span></span>  <br/> |
|<span data-ttu-id="0069e-140">Mac</span><span class="sxs-lookup"><span data-stu-id="0069e-140">Mac</span></span>  <br/> |<span data-ttu-id="0069e-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0069e-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="0069e-142">Nein</span><span class="sxs-lookup"><span data-stu-id="0069e-142">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="0069e-143">Eingehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="0069e-143">Inbound Caller ID</span></span>

<span data-ttu-id="0069e-144">Das Telefon System zeigt die benannte ID für eine externe Telefonnummer an, wenn die Nummer einem Benutzer in Azure AD zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0069e-144">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="0069e-145">Wenn sich die Telefonnummer nicht in Azure AD befindet, wird der von Telco bereitgestellte Anzeigename angezeigt, wenn er verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0069e-145">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="0069e-146">Mit dem Attribut BlockIncomingCallerID können Sie die Anrufer-ID Für eingehende PSTN-Anrufe blockieren.</span><span class="sxs-lookup"><span data-stu-id="0069e-146">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="0069e-147">Sie können dieses Attribut festlegen, das jedoch für Ihre Endbenutzer auf der Seite "Benutzereinstellungen" nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="0069e-147">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="0069e-148">Außerdem ist das Attribut zurzeit nur für Online-PSTN-Anbindung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0069e-148">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="0069e-149">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="0069e-149">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0069e-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0069e-150">Related topics</span></span>
[<span data-ttu-id="0069e-151">Übertragen von Telefonnummern – häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="0069e-151">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="0069e-152">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="0069e-152">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="0069e-153">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="0069e-153">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="0069e-154">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="0069e-154">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="0069e-155">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="0069e-155">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
