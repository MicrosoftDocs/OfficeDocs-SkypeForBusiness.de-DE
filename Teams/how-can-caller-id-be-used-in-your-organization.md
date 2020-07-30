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
ms.openlocfilehash: 5c20f439d156997c89ca54c2a3bf39e9c3a42ae4
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506198"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="b7358-103">Verwendungsmöglichkeiten der Anrufer-ID in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="b7358-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="b7358-104">Die Rufnummernanzeige kann für eingehende und ausgehende Anrufe für Telefon System Benutzer unter Verwendung einer Richtlinie mit dem Namen CallingLineIdentity gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="b7358-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="b7358-105">Die Rufnummernanzeige Funktion steht allen Telefon System Benutzern unabhängig von der PSTN-Konnektivität zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b7358-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="b7358-106">Microsoft-Anrufpläne</span><span class="sxs-lookup"><span data-stu-id="b7358-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="b7358-107">Direktes Routing für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="b7358-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="b7358-108">Online-PSTN-Anbindung</span><span class="sxs-lookup"><span data-stu-id="b7358-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="b7358-109">Lokale PSTN-Anbindung mit Skype for Business Cloud Connector Edition (erfordert Cloud Connector Edition 1.4.2 oder höher)</span><span class="sxs-lookup"><span data-stu-id="b7358-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="b7358-110">Lokale PSTN-Anbindung mit Skype for Business Server (erfordert Skype for Business Server 2015 CU5 oder höher)</span><span class="sxs-lookup"><span data-stu-id="b7358-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="b7358-111">Diese Richtlinie ist in Skype for Business Server 2015 nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7358-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="b7358-112">Ausgehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="b7358-112">Outbound caller ID</span></span>

<span data-ttu-id="b7358-113">Für ausgehende PSTN-Rufnummernanzeige stehen drei Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="b7358-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="b7358-114">Die dem Benutzer zugewiesene Telefonnummer, die der Standardwert ist.</span><span class="sxs-lookup"><span data-stu-id="b7358-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="b7358-115">Eine Telefonnummer, die als *Service* *-und gebührenfreie* Nummer in der Telefonnummern Inventur Ihres Anruf Plans eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="b7358-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="b7358-116">Sie wird normalerweise einer automatischen Telefonzentrale oder einer Anruf-Warteschleife Ihrer Organisation zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b7358-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="b7358-117">Auf „Anonym" festgelegt</span><span class="sxs-lookup"><span data-stu-id="b7358-117">Set to anonymous.</span></span>
    
<span data-ttu-id="b7358-118">Die folgenden Arten von Telefonnummern können Sie jedoch nicht als ausgehende Anrufer-ID nicht zuweisen:</span><span class="sxs-lookup"><span data-stu-id="b7358-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="b7358-119">Alle Telefonnummern, die in ihren Anrufplänen als *Benutzer* klassifiziert sind Telefonnummern Inventar</span><span class="sxs-lookup"><span data-stu-id="b7358-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="b7358-120">Lokale Skype for Business Server-Telefonnummern</span><span class="sxs-lookup"><span data-stu-id="b7358-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="b7358-121">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="b7358-121">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="b7358-122">Endbenutzer Steuerung der ausgehenden Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="b7358-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="b7358-123">Das EnableUserOverride-Attribut ermöglicht es einzelnen oder mehreren Benutzern, Ihre Einstellungen für die Rufnummernanzeige in **Anonymous**zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b7358-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="b7358-124">Dies gilt nur, wenn eine CallingLineIdentity -Richtlinie mit dem CallingIDSubstitute -Parameter LineURI oder Substitute konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b7358-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="b7358-125">Der Standardwert von EnableUserOverride lautet False.</span><span class="sxs-lookup"><span data-stu-id="b7358-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="b7358-126">Ihre Endbenutzer können Ihre Anrufer-ID auf **Anonym** festlegen, indem Sie auf der Registerkarte **Einstellungen** im Skype for Business-Desktop Client die Option **Endbenutzer anrufen** (sofern vom Administrator aktiviert) auswählen und dann **meine Telefonnummer und Profilinformationen für alle Anrufe verbergen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="b7358-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="b7358-127">In Teams können Benutzer in der oberen rechten Ecke zu Ihrem Profilbild wechseln, **Einstellungen**  >  **anrufen**auswählen und dann unter **Rufnummern**Anzeige die Option **meine Telefonnummer und Profilinformationen für alle Anrufe verbergen**auswählen.</span><span class="sxs-lookup"><span data-stu-id="b7358-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="b7358-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="b7358-128">**Windows**</span></span> <br/> |<span data-ttu-id="b7358-129">**Version**</span><span class="sxs-lookup"><span data-stu-id="b7358-129">**Version**</span></span> <br/> |<span data-ttu-id="b7358-130">**Unterstützt**</span><span class="sxs-lookup"><span data-stu-id="b7358-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="b7358-131">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="b7358-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="b7358-132">Aktueller Kanal, Veröffentlichung am 6. Dezember 2016 - Version 1611 (Build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="b7358-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="b7358-133">Ja</span><span class="sxs-lookup"><span data-stu-id="b7358-133">Yes</span></span>  <br/> |
|<span data-ttu-id="b7358-134">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="b7358-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="b7358-135">First Release für verzögerten Kanal, Veröffentlichung am 22. Februar 2017 - Version 1701 (Build 7766.2060)</span><span class="sxs-lookup"><span data-stu-id="b7358-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="b7358-136">Ja</span><span class="sxs-lookup"><span data-stu-id="b7358-136">Yes</span></span>  <br/> |
|<span data-ttu-id="b7358-137">Klick-und-Los</span><span class="sxs-lookup"><span data-stu-id="b7358-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="b7358-138">Veröffentlichung im verzögerten Kanal am 13. Juni 2017 - Version 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="b7358-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="b7358-139">Ja</span><span class="sxs-lookup"><span data-stu-id="b7358-139">Yes</span></span>  <br/> |
|<span data-ttu-id="b7358-140">MSI</span><span class="sxs-lookup"><span data-stu-id="b7358-140">MSI</span></span>  <br/> |<span data-ttu-id="b7358-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b7358-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="b7358-142">Nein</span><span class="sxs-lookup"><span data-stu-id="b7358-142">No</span></span>  <br/> |
|<span data-ttu-id="b7358-143">Mac</span><span class="sxs-lookup"><span data-stu-id="b7358-143">Mac</span></span>  <br/> |<span data-ttu-id="b7358-144">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b7358-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="b7358-145">Nein</span><span class="sxs-lookup"><span data-stu-id="b7358-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="b7358-146">Eingehende Anrufer-ID</span><span class="sxs-lookup"><span data-stu-id="b7358-146">Inbound caller ID</span></span>

<span data-ttu-id="b7358-147">Das Telefon System zeigt die benannte ID für eine externe Telefonnummer an, wenn die Nummer einem Benutzer in Azure AD zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b7358-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="b7358-148">Wenn sich die Telefonnummer nicht in Azure AD befindet, wird der von Telco bereitgestellte Anzeigename angezeigt, wenn er verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b7358-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="b7358-149">Mit dem Attribut BlockIncomingCallerID können Sie die Anrufer-ID Für eingehende PSTN-Anrufe blockieren.</span><span class="sxs-lookup"><span data-stu-id="b7358-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="b7358-150">Sie können dieses Attribut festlegen, das jedoch für Ihre Endbenutzer auf der Seite "Benutzereinstellungen" nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b7358-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="b7358-151">Außerdem ist das Attribut zurzeit nur für Online-PSTN-Anbindung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b7358-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="b7358-152">Informationen zum Festlegen der ausgehenden Anrufer-ID finden Sie unter [Festlegen der Anrufer-ID für einen Benutzer](/microsoftteams/set-the-caller-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="b7358-152">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b7358-153">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b7358-153">Related topics</span></span>
[<span data-ttu-id="b7358-154">Übertragen von Telefonnummern – häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="b7358-154">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="b7358-155">Verschiedene Arten von Telefonnummern, die für Anrufpläne verwendet werden</span><span class="sxs-lookup"><span data-stu-id="b7358-155">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="b7358-156">Verwalten von Telefonnummern für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="b7358-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="b7358-157">Nutzungsbedingungen für Notrufe</span><span class="sxs-lookup"><span data-stu-id="b7358-157">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="b7358-158">[Skype for Business Online: Aufkleber mit Haftungsausschluss für Notrufe](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="b7358-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
