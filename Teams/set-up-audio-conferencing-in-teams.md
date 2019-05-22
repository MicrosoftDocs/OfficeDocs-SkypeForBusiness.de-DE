---
title: Einrichten von Audiokonferenzen für Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Hier erfahren Sie, wie Sie Einwahl-oder Audiokonferenzen für die Personen in Ihrem Unternehmen einrichten, die ein Telefon für die Teilnahme an Konferenzgesprächen verwenden müssen. '
ms.openlocfilehash: f0709f2a99524666e3b48992338abae111599b7d
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344210"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="007de-103">Einrichten von Audiokonferenzen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="007de-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="007de-104">Manchmal müssen Personen in Ihrer Organisation ein Telefon nutzen, um sich in eine Besprechung einzuwählen.</span><span class="sxs-lookup"><span data-stu-id="007de-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="007de-105">Microsoft Teams enthält das Feature "Audiokonferenz" für nur diese Situation!</span><span class="sxs-lookup"><span data-stu-id="007de-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="007de-106">Personen können mit einem Telefon in Teams-Besprechungen anrufen, anstatt die Teams-App auf einem mobilen Gerät oder PC zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="007de-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="007de-107">Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten.</span><span class="sxs-lookup"><span data-stu-id="007de-107">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings.</span></span> <span data-ttu-id="007de-108">Besprechungsteilnehmer, die sich einwählen, benötigen keine ihnen zugewiesenen Lizenzen oder andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="007de-108">Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="007de-109">Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="007de-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="007de-110">Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="007de-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="007de-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="007de-111"></span></span>

<span data-ttu-id="007de-112">Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="007de-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="007de-113">Schritt 2: Abrufen und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="007de-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="007de-114">Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichtet.</span><span class="sxs-lookup"><span data-stu-id="007de-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="007de-115">Wenn Sie wissen möchten, welche Lizenzen Sie für Audiokonferenzen kaufen müssen und wie viel Sie Kosten werden, lesen Sie [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="007de-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="007de-116">Audiokonferenzen sind in Office 365 Enterprise E5-Lizenzen und als Add-on enthalten.</span><span class="sxs-lookup"><span data-stu-id="007de-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="007de-117">Nachdem Sie die Audiokonferenz-Lizenzen gekauft haben, müssen Sie diese den Personen in Ihrer Organisation zuweisen, die Besprechungen planen oder leiten.</span><span class="sxs-lookup"><span data-stu-id="007de-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="007de-118">Weitere Informationen finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Office 365 für Unternehmen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) , die Sie für die Personen in Ihrer Organisation erworben haben, die Besprechungen planen oder leiten.</span><span class="sxs-lookup"><span data-stu-id="007de-118">See [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="007de-119">Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="007de-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="007de-120">Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="007de-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="007de-121">Sie können auch eine [Pay-per-Minute](audio-conferencing-pay-per-minute.md)-Audiokonferenz einrichten.</span><span class="sxs-lookup"><span data-stu-id="007de-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="007de-122">Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern</span><span class="sxs-lookup"><span data-stu-id="007de-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="007de-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="007de-123"></span></span>

<span data-ttu-id="007de-124">Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern.</span><span class="sxs-lookup"><span data-stu-id="007de-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="007de-125">Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen.</span><span class="sxs-lookup"><span data-stu-id="007de-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="007de-126">Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="007de-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="007de-127">**Verwenden Sie das Microsoft Teams Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="007de-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="007de-128">In einigen Ländern/Regionen können Sie mithilfe des Microsoft Teams Admin Center Servicenummern für Ihre Konferenz Brücken abrufen.</span><span class="sxs-lookup"><span data-stu-id="007de-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="007de-129">Weitere Informationen finden Sie unter [Abrufen von Telefonnummern für Dienstleistungen](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="007de-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="007de-130">**Portieren Sie Ihre vorhandenen Servicenummern**.</span><span class="sxs-lookup"><span data-stu-id="007de-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="007de-131">Zum Portieren oder übertragen vorhandener Nummern von Ihrem aktuellen Dienstanbieter oder Telefonnetzbetreiber zu Office 365</span><span class="sxs-lookup"><span data-stu-id="007de-131">To port or transfer existing numbers from your current service provider or phone carrier to Office 365.</span></span> <span data-ttu-id="007de-132">Über [Übertragen von Telefonnummern zu Office 365](transfer-phone-numbers-to-office-365.md) oder [Rufnummern für Ihre Organisation verwalten](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) erhalten Sie weitere hilfreiche Informationen.</span><span class="sxs-lookup"><span data-stu-id="007de-132">You can see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="007de-133">**Verwenden Sie ein Anforderungsformular für neue Nummern**.</span><span class="sxs-lookup"><span data-stu-id="007de-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="007de-134">Manchmal (je nach Land/Region) können Sie Ihre neuen Dienstnummern nicht über das Microsoft Teams Admin Center abrufen, oder Sie benötigen bestimmte Telefonnummern oder Ortsvorwahl.</span><span class="sxs-lookup"><span data-stu-id="007de-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="007de-135">In diesem Fall müssen Sie ein Formular herunterladen und an uns senden.</span><span class="sxs-lookup"><span data-stu-id="007de-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="007de-136">Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="007de-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="007de-137">Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="007de-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="007de-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="007de-138"></span></span>

<span data-ttu-id="007de-139">Nachdem Sie Ihre gebührenpflichtigen und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten haben, müssen Sie die Nummern zuweisen, damit Sie für Besprechungseinladungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="007de-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="007de-140">Führen Sie die folgenden Schritte aus, um ihrer Audiokonferenz-Brücke eine neue Telefonnummer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="007de-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="007de-141">![SFB-Logo-30x30. png](media/sfb-logo-30x30.png) **mit dem Skype for Business Admin Center:**</span><span class="sxs-lookup"><span data-stu-id="007de-141">![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="007de-142">Wechseln Sie zum **Microsoft 365 Admin Center** > **Admin** > Center**Teams** > **Legacy-Portal**.</span><span class="sxs-lookup"><span data-stu-id="007de-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="007de-143">Wählen Sie **VoIP** > \*\*\*\*-Rufnummern aus.</span><span class="sxs-lookup"><span data-stu-id="007de-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="007de-144">Wählen Sie die Telefonnummer aus, und klicken Sie auf **zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="007de-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="007de-145">Weitere Informationen finden Sie unter [Ändern der Telefonnummern auf der Audiokonferenz-Brücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="007de-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="007de-146">Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest</span><span class="sxs-lookup"><span data-stu-id="007de-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="007de-147"><a name="__top"></a> Als nächstes möchten Sie die [Sprachen der automatischen Telefonzentrale für Audiokonferenzen in Microsoft Teams fest legen](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) , die von der automatischen Telefonzentrale für Konferenzen verwendet werden, um Anrufer zu grüßen, wenn Sie sich bei einer Telefonnummer für Audiokonferenzen einwählen.</span><span class="sxs-lookup"><span data-stu-id="007de-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="007de-148">![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center**zeigt:</span><span class="sxs-lookup"><span data-stu-id="007de-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="007de-149">Wechseln Sie im Dashboard zu **Besprechungen** > **Konferenz Brücken**.</span><span class="sxs-lookup"><span data-stu-id="007de-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="007de-150">Wählen Sie die Telefonnummer der Konferenzbrücke aus, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache aus.</span><span class="sxs-lookup"><span data-stu-id="007de-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="007de-151">Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen</span><span class="sxs-lookup"><span data-stu-id="007de-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="007de-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="007de-152"></span></span>
    
<span data-ttu-id="007de-153">Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern.</span><span class="sxs-lookup"><span data-stu-id="007de-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="007de-154">![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center**zeigt:</span><span class="sxs-lookup"><span data-stu-id="007de-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="007de-155">Wechseln Sie im Dashboard zu **Besprechungen** > **Konferenz Brücken**.</span><span class="sxs-lookup"><span data-stu-id="007de-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="007de-156">Wählen Sie **Brücken Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="007de-156">Select **Bridge settings**.</span></span> <span data-ttu-id="007de-157">Der **Brücke**-Einstellungsbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="007de-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="007de-158">Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="007de-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="007de-159">Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten</span><span class="sxs-lookup"><span data-stu-id="007de-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="007de-160">Nachdem Sie eine Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und gebührenfreien Nummern für Ihre Benutzer festlegen.</span><span class="sxs-lookup"><span data-stu-id="007de-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="007de-161">Sie müssen dies für alle Personen in Ihrer Organisation tun, die Besprechungen leiten oder planen.</span><span class="sxs-lookup"><span data-stu-id="007de-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="007de-162">![Ein Symbol, das das Microsoft Teams](media/teams-logo-30x30.png) -Logo **mit dem Microsoft Teams Admin Center**zeigt:</span><span class="sxs-lookup"><span data-stu-id="007de-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="007de-163">Klicken Sie im Dashboard auf **Benutzer**, wählen Sie den Benutzer in der Liste aus, und wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="007de-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="007de-164">Wählen Sie neben **Audio-Conferencing**die Option **Bearbeiten** aus, und wählen Sie dann im Bereich Audiokonferenz eine Nummer in den Listen **gebührenpflichtige** Nummer und **gebührenfreie** Nummern aus. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="007de-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="007de-165">Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="007de-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="007de-166">Schritt 8: Besprechungseinladungen einrichten (optional)</span><span class="sxs-lookup"><span data-stu-id="007de-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="007de-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="007de-167"></span></span>
 
<span data-ttu-id="007de-168">Die für den Benutzer festgelegten Einwahlnummern werden automatisch zu den Besprechungseinladungen hinzugefügt, die an Besprechungsteilnehmer gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="007de-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="007de-169">Sie können jedoch Ihre eigenen Hilfe- und rechtliche Links, eine SMS und eine kleine Firmengrafik hinzufügen, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="007de-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="007de-170">Weitere Informationen finden Sie unter [Anpassen von Besprechungseinladungen](customize-meeting-invitations.md).</span><span class="sxs-lookup"><span data-stu-id="007de-170">See [Customize meeting invitations](customize-meeting-invitations.md).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="007de-171">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="007de-171">Related topics</span></span>

[<span data-ttu-id="007de-172">Allgemeine Fragen zu Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="007de-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="007de-173">Telefonnummern für Audiokonferenzen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="007de-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="007de-174">Optionen für Onlinebesprechungen und Telefonkonferenzen festlegen</span><span class="sxs-lookup"><span data-stu-id="007de-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
