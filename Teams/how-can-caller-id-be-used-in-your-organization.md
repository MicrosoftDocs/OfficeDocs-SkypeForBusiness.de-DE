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
ms.openlocfilehash: 2547e6ca3aed10d112897aa1b24900a479c5c8ef
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224208"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="3b7c6-103">Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="3b7c6-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="3b7c6-104">Die Rufnummernanzeige kann für eingehende und ausgehende Anrufe für Telefon System Benutzer unter Verwendung einer Richtlinie mit dem Namen CallingLineIdentity gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="3b7c6-105">Die Rufnummernanzeige Funktion steht allen Telefon System Benutzern unabhängig von der PSTN-Konnektivität zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="3b7c6-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="3b7c6-106">Online-PSTN-Anbindung</span><span class="sxs-lookup"><span data-stu-id="3b7c6-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="3b7c6-107">Lokale PSTN-Anbindung mit Skype for Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 oder höher)</span><span class="sxs-lookup"><span data-stu-id="3b7c6-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="3b7c6-108">Lokale PSTN-Anbindung mit Skype for Business Server (erfordert Skype for Business Server 2015 CU5 oder höher)</span><span class="sxs-lookup"><span data-stu-id="3b7c6-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="3b7c6-109">Diese Richtlinie ist in Skype for Business Server 2015 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="3b7c6-110">Ausgehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="3b7c6-110">Outbound caller ID</span></span>

<span data-ttu-id="3b7c6-111">Für ausgehende PSTN-Rufnummernanzeige stehen drei Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="3b7c6-111">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="3b7c6-112">Die dem Benutzer zugewiesene Telefonnummer, die der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="3b7c6-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="3b7c6-115">Auf „Anonym" festgelegt</span><span class="sxs-lookup"><span data-stu-id="3b7c6-115">Set to anonymous.</span></span>
    
<span data-ttu-id="3b7c6-116">Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:</span><span class="sxs-lookup"><span data-stu-id="3b7c6-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="3b7c6-117">Alle Telefonnummern, die in ihren Anrufplänen als *Benutzer* klassifiziert sind Telefonnummern Inventar</span><span class="sxs-lookup"><span data-stu-id="3b7c6-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="3b7c6-118">Lokale Skype for Business Server-Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="3b7c6-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="3b7c6-119">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="3b7c6-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="3b7c6-120">Endbenutzer Steuerung der ausgehenden Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="3b7c6-120">End user control of outbound caller ID</span></span>

<span data-ttu-id="3b7c6-p102">Das EnableUserOverride-Attribut ermöglicht es einzelnen oder mehreren Benutzern, Ihre Einstellungen für die Rufnummernanzeige in **Anonymous**zu ändern. Dies gilt nur, wenn eine CallingLineIdentity-Richtlinie mit einem CallingIDSubstitute-Parameter von LineURI oder Substitute konfiguriert ist. Der Standardwert von EnableUserOverride ist false.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-p102">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="3b7c6-124">Ihre Endbenutzer können Ihre Anrufer-ID auf **Anonym** festlegen, indem Sie auf der Registerkarte **Einstellungen** im Skype for Business-Desktop Client die Option **Endbenutzer anrufen** (sofern vom Administrator aktiviert) auswählen und dann **meine Telefonnummer und Profilinformationen für alle Anrufe verbergen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="3b7c6-125">In Teams können Benutzer in der oberen rechten Ecke zu Ihrem Profilbild wechseln, **Einstellungen**  >  **anrufen**auswählen und dann unter **Rufnummern**Anzeige die Option **meine Telefonnummer und Profilinformationen für alle Anrufe verbergen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-125">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="3b7c6-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="3b7c6-126">**Windows**</span></span> <br/> |<span data-ttu-id="3b7c6-127">**Version**</span><span class="sxs-lookup"><span data-stu-id="3b7c6-127">**Version**</span></span> <br/> |<span data-ttu-id="3b7c6-128">**Unterstützt**</span><span class="sxs-lookup"><span data-stu-id="3b7c6-128">**Supported**</span></span> <br/> |
|<span data-ttu-id="3b7c6-129">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="3b7c6-129">Click-to-Run</span></span>  <br/> |<span data-ttu-id="3b7c6-130">Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="3b7c6-130">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="3b7c6-131">Ja</span><span class="sxs-lookup"><span data-stu-id="3b7c6-131">Yes</span></span>  <br/> |
|<span data-ttu-id="3b7c6-132">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="3b7c6-132">Click-to-Run</span></span>  <br/> |<span data-ttu-id="3b7c6-133">First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="3b7c6-133">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="3b7c6-134">Ja</span><span class="sxs-lookup"><span data-stu-id="3b7c6-134">Yes</span></span>  <br/> |
|<span data-ttu-id="3b7c6-135">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="3b7c6-135">Click-to-Run</span></span>  <br/> |<span data-ttu-id="3b7c6-136">Veröffentlichung im verzögerten Kanal am 13. Juni 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="3b7c6-136">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="3b7c6-137">Ja</span><span class="sxs-lookup"><span data-stu-id="3b7c6-137">Yes</span></span>  <br/> |
|<span data-ttu-id="3b7c6-138">MSI</span><span class="sxs-lookup"><span data-stu-id="3b7c6-138">MSI</span></span>  <br/> |<span data-ttu-id="3b7c6-139">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3b7c6-139">Skype for Business</span></span>  <br/> |<span data-ttu-id="3b7c6-140">Nein</span><span class="sxs-lookup"><span data-stu-id="3b7c6-140">No</span></span>  <br/> |
|<span data-ttu-id="3b7c6-141">Mac</span><span class="sxs-lookup"><span data-stu-id="3b7c6-141">Mac</span></span>  <br/> |<span data-ttu-id="3b7c6-142">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3b7c6-142">Skype for Business</span></span>  <br/> |<span data-ttu-id="3b7c6-143">Nein</span><span class="sxs-lookup"><span data-stu-id="3b7c6-143">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="3b7c6-144">Eingehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="3b7c6-144">Inbound caller ID</span></span>

<span data-ttu-id="3b7c6-145">Das Telefon System zeigt die benannte ID für eine externe Telefonnummer an, wenn die Nummer einem Benutzer in Azure AD zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-145">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="3b7c6-146">Wenn sich die Telefonnummer nicht in Azure AD befindet, wird der von Telco bereitgestellte Anzeigename angezeigt, wenn er verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-146">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="3b7c6-147">Mit dem Attribut BlockIncomingCallerID können Sie die Anrufer-ID Für eingehende PSTN-Anrufe blockieren.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-147">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="3b7c6-148">Sie können dieses Attribut festlegen, das jedoch für Ihre Endbenutzer auf der Seite "Benutzereinstellungen" nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-148">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="3b7c6-149">Außerdem ist das Attribut zurzeit nur für Online-PSTN-Anbindung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3b7c6-149">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="3b7c6-150">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="3b7c6-150">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="3b7c6-151">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3b7c6-151">Related topics</span></span>
[<span data-ttu-id="3b7c6-152">Übertragen von Telefonnummern – häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="3b7c6-152">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="3b7c6-153">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="3b7c6-153">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="3b7c6-154">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="3b7c6-154">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="3b7c6-155">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="3b7c6-155">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="3b7c6-156">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="3b7c6-156">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
