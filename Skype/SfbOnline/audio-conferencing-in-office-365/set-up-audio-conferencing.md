---
title: Einrichten von Audiokonferenzen für Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365P_DialInConfDesc
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Hier erfahren Sie, wie Sie Einwahl- oder Audiokonferenzen für Personen in Ihrem Unternehmen einrichten, die telefonisch an Konferenzanrufen teilnehmen müssen. '
ms.openlocfilehash: 499a8a8ef05d23c74b030536d33b7a02cd6d9a1a
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2019
ms.locfileid: "37924976"
---
# <a name="set-up-audio-conferencing-for-skype-for-business"></a><span data-ttu-id="1ff4b-103">Einrichten von Audiokonferenzen für Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1ff4b-103">Set up Audio Conferencing for Skype for Business</span></span>

<span data-ttu-id="1ff4b-p101">Manchmal müssen Mitarbeiter in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen. Für genau diese Situation ist die Audiokonferenzfunktion in Skype for Business gedacht. Teilnehmer können sich mit einem Telefon in Skype for Business-Besprechungen einwählen, anstatt die Skype for Business-App auf einem Mobilgerät oder PC zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-p101">Sometimes people in your organization will need to use a phone to call in to a meeting. Skype for Business includes the audio conferencing feature for just this situation! People can call in to Skype for Business meetings using a phone, instead of using the Skype for Business app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="1ff4b-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="1ff4b-109">Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](/MicrosoftTeams/audio-conferencing-common-questions).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](/MicrosoftTeams/audio-conferencing-common-questions).</span></span>

## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="1ff4b-110">Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="1ff4b-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="1ff4b-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1ff4b-111"><a name="__top"> </a></span></span>

<span data-ttu-id="1ff4b-112">Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="1ff4b-113">Schritt 2: Abrufen und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="1ff4b-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="1ff4b-p103">Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichten wird. Informationen darüber, welche Lizenzen Sie für Audiokonferenzen erwerben müssen und wie viel sie kosten, finden Sie unter [Lizenzierung des Skype for Business-Add-Ons](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-p103">For Audio Conferencing, you need a license for each user who will set up dial-in meetings. To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="1ff4b-116">Audiokonferenzen sind in Office 365 Enterprise E5-Lizenzen und als Add-On enthalten.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="1ff4b-117">Nachdem Sie die Audiokonferenz-Lizenzen erworben haben, müssen Sie diese den Personen in Ihrer Organisation zuweisen, die Besprechungen planen oder leiten werden.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="1ff4b-118">Siehe [Zuweisen oder Entfernen von Lizenzen für Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) an die Mitarbeiter in Ihrer Organisation, die Besprechungen planen oder leiten werden.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-118">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="1ff4b-119">Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="1ff4b-120">Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](/microsoftteams/set-up-communications-credits-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](/microsoftteams/set-up-communications-credits-for-your-organization).</span></span>
    
> [!NOTE]
> <span data-ttu-id="1ff4b-121">Sie können auch [Audiokonferenzen mit Minutenabrechnung](/microsoftteams/audio-conferencing-pay-per-minute) einrichten.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-121">You can also set up [pay-per-minute Audio Conferencing](/microsoftteams/audio-conferencing-pay-per-minute).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="1ff4b-122">Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern</span><span class="sxs-lookup"><span data-stu-id="1ff4b-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="1ff4b-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1ff4b-123"><a name="__top"> </a></span></span>

<span data-ttu-id="1ff4b-124">Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="1ff4b-125">Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="1ff4b-126">Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="1ff4b-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="1ff4b-127">**Verwenden des Skype for Business Admin Centers**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-127">**Use the Skype for Business admin center**.</span></span> <span data-ttu-id="1ff4b-128">Für einige Länder/Regionen können Sie Servicenummern für Ihre Konferenzbrücken über das Skype for Business Admin Center erhalten.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Skype for Business admin center.</span></span> <span data-ttu-id="1ff4b-129">Siehe [Abrufen von Servicetelefonnummern](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="1ff4b-130">**Portieren von bestehenden Servicenummern**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="1ff4b-131">Portieren oder übertragen Sie vorhandene Telefonnummern von Ihrem derzeitigen Dienstanbieter oder Netzbetreiber zu Office 365.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="1ff4b-132">Über [Übertragen von Telefonnummern zu Teams](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) oder [Rufnummern für Ihre Organisation verwalten](/microsoftteams/manage-phone-numbers-for-your-organization) erhalten Sie weitere hilfreiche Informationen.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-132">You can see [Transfer phone numbers to Office 365](/microsoftteams/phone-number-calling-plans/transfer-phone-numbers-to-teams) or [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="1ff4b-133">**Verwenden eines Anforderungsformulars für neue Telefonnummern**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="1ff4b-134">Manchmal können Sie (je nach Land/Region) Ihre neuen Servicenummern nicht über das Skype for Business Admin Center beziehen, oder Sie benötigen bestimmte Telefonnummern oder Ortsvorwahlen.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Skype for Business admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="1ff4b-135">Wenn dies der Fall ist, müssen Sie ein Formular herunterladen und an uns zurücksenden.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="1ff4b-136">Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](/microsoftteams/manage-phone-numbers-for-your-organization).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-136">See [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="1ff4b-137">Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="1ff4b-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="1ff4b-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1ff4b-138"><a name="__top"> </a></span></span>

<span data-ttu-id="1ff4b-139">Sobald Sie Ihre gebührenpflichtigen und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten, müssen Sie die Nummern zuweisen, damit sie für die Einladungen zu den Besprechungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="1ff4b-140">So weisen Sie Ihrer Audiokonferenzbrücke eine neue Rufnummer zu:</span><span class="sxs-lookup"><span data-stu-id="1ff4b-140">To assign a new phone number to your audio conferencing bridge:</span></span>

<span data-ttu-id="1ff4b-141">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers:**</span><span class="sxs-lookup"><span data-stu-id="1ff4b-141">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="1ff4b-142">Wechselns Sie zum **Microsoft 365 Admin Center** > **Admin Center** > **Teams** > **Altes Portal**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="1ff4b-143">Wählen Sie **Anruf** > **Telefonnummern** aus.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="1ff4b-144">Wählen Sie die entsprechende Telefonnummer aus, und klicken Sie auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="1ff4b-145">Weitere Informationen finden Sie unter [Ändern der Telefonnummern Ihrer Audiokonferenzbrücke](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-145">For more details, see [Change the phone numbers on your audio conferencing bridge](/MicrosoftTeams/change-the-phone-numbers-on-your-audio-conferencing-bridge).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="1ff4b-146">Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest</span><span class="sxs-lookup"><span data-stu-id="1ff4b-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="1ff4b-147"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1ff4b-147"><a name="__top"> </a></span></span>

<span data-ttu-id="1ff4b-148">Als Nächstes sollten Sie die [Sprachen für die automatische Telefonzentrale für Audiokonferenzen festlegen](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md), die die automatische Telefonkonferenzzentrale verwendet, um einen Anrufer zu begrüßen, wenn er sich mit einer Telefonnummer für Audiokonferenzen einwählt.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-148">Next, you want to [Set auto attendant languages for Audio Conferencing](../audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="1ff4b-149">![Ein Symbol mit dem Microsoft Teams-Logo](../images/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**:</span><span class="sxs-lookup"><span data-stu-id="1ff4b-149">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="1ff4b-150">Wechseln Sie über das Dashboard zu **Besprechungen** > **Konferenzbrücken**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-150">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="1ff4b-151">Wählen Sie die Telefonnummer der Konferenzbrücke, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-151">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

<span data-ttu-id="1ff4b-152">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**:</span><span class="sxs-lookup"><span data-stu-id="1ff4b-152">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**:</span></span>

1. <span data-ttu-id="1ff4b-153">Wechselns Sie zum Admin Center > **Admin Center** > **Teams** > **Altes Portal**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-153">Go to the admin center > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="1ff4b-154">WählenSie **Audiokonferenzen** > **Microsoft Bridge** aus.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-154">Select **Audio conferencing** > **Microsoft bridge**.</span></span> 
3. <span data-ttu-id="1ff4b-155">Wählen Sie die Telefonnummer der Konferenzbrücke, klicken Sie auf **Sprachen festlegen**, und wählen Sie dann die Standardsprache aus.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-155">Select the conferencing bridge phone number, select **Set languages**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="1ff4b-156">Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen</span><span class="sxs-lookup"><span data-stu-id="1ff4b-156">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="1ff4b-157"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1ff4b-157"><a name="__top"> </a></span></span>
    
<span data-ttu-id="1ff4b-158">Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-158">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="1ff4b-159">![Ein Symbol mit dem Microsoft Teams-Logo](../images/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**:</span><span class="sxs-lookup"><span data-stu-id="1ff4b-159">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="1ff4b-160">Wechseln Sie über das Dashboard zu **Besprechungen** > **Konferenzbrücken**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-160">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="1ff4b-161">Wählen Sie **Brückeneinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-161">Select **Bridge settings**.</span></span> <span data-ttu-id="1ff4b-162">Der **Brücke**-Einstellungsbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-162">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="1ff4b-163">Siehe [Ändern der Einstellungen für eine Audiokonferenzbrücke](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-163">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

<span data-ttu-id="1ff4b-164">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers:**</span><span class="sxs-lookup"><span data-stu-id="1ff4b-164">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="1ff4b-165">Wechselns Sie zum **Microsoft 365 Admin Center** > **Admin Center** > **Teams** > **Altes Portal**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-165">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="1ff4b-166">WählenSie **Audiokonferenzen** > **Einstellungen von Microsoft Bridge** aus.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-166">Select **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="1ff4b-167">Die Seite **Microsoft Brückeneinstellungen** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-167">This will open the **Microsoft bridge settings** page.</span></span> 

<span data-ttu-id="1ff4b-168">Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-168">For more details, see [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="1ff4b-169">Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten</span><span class="sxs-lookup"><span data-stu-id="1ff4b-169">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="1ff4b-170">Nachdem Sie eine Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und gebührenfreien Nummern für Ihre Benutzer festlegen.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-170">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="1ff4b-171">Sie müssen dies für alle Personen in Ihrer Organisation tun, die Besprechungen leiten oder planen.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-171">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="1ff4b-172">![Ein Symbol mit dem Microsoft Teams-Logo](../images/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**:</span><span class="sxs-lookup"><span data-stu-id="1ff4b-172">![An icon showing the Microsoft Teams logo](../images/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="1ff4b-173">Klicken Sie im Dashboard auf **Benutzer**, wählen Sie den entsprechenden Benutzer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-173">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="1ff4b-174">Klicken Sie neben **Audiokonferenzen** auf **Bearbeiten**, und wählen Sie dann im Bereich **Audiokonferenzen** eine Nummer aus den Listen der **gebührenpflichtigen** und **gebührenfreien** Telefonnummern aus.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-174">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="1ff4b-175">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers:**</span><span class="sxs-lookup"><span data-stu-id="1ff4b-175">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

1. <span data-ttu-id="1ff4b-176">Wechselns Sie zum **Microsoft 365 Admin Center** > **Teams** > **Altes Portal**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-176">Go to the **Microsoft 365 admin center** > **Teams** > **Legacy portal**.</span></span>
2. <span data-ttu-id="1ff4b-177">Wählen Sie **Audiokonferenzen** > **Benutzer**, wählen Sie Benutzer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-177">Select **Audio conferencing** > **Users**, and then select the user from the list and click **Edit**.</span></span> 

<span data-ttu-id="1ff4b-178">Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-178">If you need more details, see [Assign Microsoft as the audio conferencing provider](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="1ff4b-179">Schritt 8: Besprechungseinladungen einrichten (optional)</span><span class="sxs-lookup"><span data-stu-id="1ff4b-179">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="1ff4b-180"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="1ff4b-180"><a name="__top"> </a></span></span>
 
<span data-ttu-id="1ff4b-181">Die für den Nutzer festgelegten Einwahlnummern werden automatisch den Besprechungseinladungen hinzugefügt, die Besprechungsteilnehmern zugesendet werden.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-181">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="1ff4b-182">Sie können jedoch Ihre eigenen Hilfe- und rechtliche Links, eine SMS und eine kleine Firmengrafik hinzufügen, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="1ff4b-182">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="1ff4b-183">Siehe [Anpassen von Besprechungseinladungen](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="1ff4b-183">See [Customize meeting invitations](../set-up-skype-for-business-online/customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="1ff4b-184">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1ff4b-184">Related topics</span></span>

[<span data-ttu-id="1ff4b-185">Allgemeine Fragen zu Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="1ff4b-185">Audio Conferencing common questions</span></span>](/MicrosoftTeams/audio-conferencing-common-questions)
  
[<span data-ttu-id="1ff4b-186">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1ff4b-186">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[<span data-ttu-id="1ff4b-187">Telefonnummern für Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="1ff4b-187">Phone numbers for Audio Conferencing</span></span>](phone-numbers-for-audio-conferencing.md)
  
[<span data-ttu-id="1ff4b-188">Festlegen von Optionen für Onlinebesprechungen und Telefonkonferenzen</span><span class="sxs-lookup"><span data-stu-id="1ff4b-188">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
