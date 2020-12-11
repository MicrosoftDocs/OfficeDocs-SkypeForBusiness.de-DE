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
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- LIL_Placement
description: 'Hier erfahren Sie, wie Sie Einwahl- oder Audiokonferenzen für Personen in Ihrem Unternehmen einrichten, die telefonisch an Konferenzanrufen teilnehmen müssen. '
ms.openlocfilehash: d1596a650507938e8dc3e87fb02dec68e415f6d6
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031421"
---
# <a name="set-up-audio-conferencing-for-microsoft-teams"></a><span data-ttu-id="ab5c2-103">Einrichten von Audiokonferenzen für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab5c2-103">Set up Audio Conferencing for Microsoft Teams</span></span>

<span data-ttu-id="ab5c2-104">In einigen Fällen müssen Mitarbeiter in Ihrer Organisation sich über ein Telefon in eine Besprechung einwählen.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-104">Sometimes people in your organization will need to use a phone to call in to a meeting.</span></span> <span data-ttu-id="ab5c2-105">Microsoft Teams bietet genau für solche Situationen das Audiokonferenz-Feature!</span><span class="sxs-lookup"><span data-stu-id="ab5c2-105">Microsoft Teams includes the audio conferencing feature for just this situation!</span></span> <span data-ttu-id="ab5c2-106">Personen können sich in Teams-Besprechungen mit einem Telefon einwählen, anstatt die Microsoft Teams-App auf einem mobilen Gerät oder einem PC zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-106">People can call in to Teams meetings using a phone, instead of using the Teams app on a mobile device or PC.</span></span> 
  
<span data-ttu-id="ab5c2-p102">Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Besprechungsteilnehmer, die sich einwählen, benötigen keine ihnen zugewiesenen Lizenzen oder andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-p102">You only need to set up Audio Conferencing for people who plan to schedule or lead meetings. Meeting attendees who dial in don't need any licenses assigned to them or other setup.</span></span>
  
<span data-ttu-id="ab5c2-109">Häufig gestellte Fragen zu Audiokonferenzen finden Sie unter [Häufig gestellte Fragen zu Audiokonferenzen](audio-conferencing-common-questions.md).</span><span class="sxs-lookup"><span data-stu-id="ab5c2-109">For frequently asked questions about Audio Conferencing, see [Audio Conferencing common questions](audio-conferencing-common-questions.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="step-1-find-out-if-audio-conferencing-is-available-in-your-countryregion"></a><span data-ttu-id="ab5c2-110">Schritt 1: Stellen Sie fest, ob Audiokonferenzen in Ihrem Land/Ihrer Region verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="ab5c2-110">Step 1: Find out if Audio Conferencing is available in your country/region</span></span>
<span data-ttu-id="ab5c2-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ab5c2-111"><a name="__top"> </a></span></span>

<span data-ttu-id="ab5c2-112">Gehen Sie auf [Länder- und Regionenverfügbarkeit für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) und wählen Sie Ihr Land oder Ihre Region aus, um Verfügbarkeitsinformationen über Audiokonferenzen sowie Informationen über Telefonanlage, Anrufpläne, gebührenfreie Nummern und Guthaben für Kommunikationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-112">Go to [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) and select your country or region to get availability information about Audio Conferencing, as well as information about Phone System, Calling Plans, toll and toll-free numbers, and Communications Credits.</span></span> 
 
## <a name="step-2-get-and-assign-licenses"></a><span data-ttu-id="ab5c2-113">Schritt 2: Abrufen und Zuweisen von Lizenzen</span><span class="sxs-lookup"><span data-stu-id="ab5c2-113">Step 2: Get and assign licenses</span></span>
 
1. <span data-ttu-id="ab5c2-114">Für Audiokonferenzen benötigen Sie eine Lizenz für jeden Benutzer, der Einwahlbesprechungen einrichtet.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-114">For Audio Conferencing, you need a license for each user who will set up dial-in meetings.</span></span> <span data-ttu-id="ab5c2-115">Informationen dazu, welche Lizenzen Sie für Audiokonferenzen erwerben müssen und was diese kosten, erhalten Sie unter [Add-On-Lizenzierung für Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span><span class="sxs-lookup"><span data-stu-id="ab5c2-115">To learn which licenses you need to buy for Audio Conferencing and how much they will cost, see [Microsoft Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing).</span></span>

    >[!NOTE] 
    > <span data-ttu-id="ab5c2-116">Audiokonferenzen sind in Office 365 Enterprise E5-Lizenzen und als Add-On enthalten.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-116">Audio Conferencing is included in Office 365 Enterprise E5 licenses and as an add-on.</span></span>
        
2. <span data-ttu-id="ab5c2-117">Nachdem Sie die Audiokonferenz-Lizenzen erworben haben, müssen Sie diese den Personen in Ihrer Organisation zuweisen, die Besprechungen planen oder leiten werden.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-117">After you buy the Audio Conferencing licenses, you will need to assign them to those people in your organization who are going to schedule or lead meetings.</span></span> <span data-ttu-id="ab5c2-118">Lesen Sie dazu [Zuweisen von Lizenzen an Benutzer in Microsoft 365 oder Office 365 Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc). Dies gilt für Lizenzen, die Sie für die Personen in Ihrer Organisation erworben haben, die Besprechungen planen oder leiten werden.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-118">See [Assign licenses to users in Microsoft 365 or Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) you purchased to the people in your organization who are going to schedule or lead meetings.</span></span>
    
3. <span data-ttu-id="ab5c2-119">Wir empfehlen auch, dass Sie Guthaben für Kommunikations-Lizenzen (sie kosten nichts) denselben Personen zuweisen, denen Sie im vorherigen Schritt Lizenzen zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-119">We also recommend that you assign Communications Credits licenses (they don’t cost anything) to the same people you assigned licenses to in the previous step.</span></span> <span data-ttu-id="ab5c2-120">Weitere Informationen zum Guthaben für Kommunikationen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](set-up-communications-credits-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="ab5c2-120">To learn how to set up Communications Credits, see [Set up Communications Credits for your organization](set-up-communications-credits-for-your-organization.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="ab5c2-121">Sie können auch [Audiokonferenzen mit Minutenabrechnung](audio-conferencing-pay-per-minute.md) einrichten.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-121">You can also set up [pay-per-minute Audio Conferencing](audio-conferencing-pay-per-minute.md).</span></span>

## <a name="step-3-get-service-numbers-for-your-conferencing-bridges"></a><span data-ttu-id="ab5c2-122">Schritt 3: Servicenummern für Ihre Konferenzbrücken anfordern</span><span class="sxs-lookup"><span data-stu-id="ab5c2-122">Step 3: Get service numbers for your conferencing bridges</span></span>
<span data-ttu-id="ab5c2-123"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ab5c2-123"><a name="__top"> </a></span></span>

<span data-ttu-id="ab5c2-124">Für Audiokonferenzen können Sie keine Benutzertelefonnummern verwenden; Sie müssen Servicenummern anfordern.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-124">For Audio Conferencing, you can’t use phone numbers for users; you will need to get service numbers.</span></span> <span data-ttu-id="ab5c2-125">Sie können für Ihre Konferenzbrücken gebührenpflichtige oder gebührenfreie Servicenummern abrufen.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-125">You can get either toll or toll-free service numbers for your conferencing bridges.</span></span> <span data-ttu-id="ab5c2-126">Es gibt drei Möglichkeiten, gebührenpflichtige und gebührenfreie Servicenummern zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="ab5c2-126">There are three ways to get toll and toll-free service numbers:</span></span> 
  
- <span data-ttu-id="ab5c2-127">**Über das Microsoft Teams Admin Center**.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-127">**Use the Microsoft Teams admin center**.</span></span> <span data-ttu-id="ab5c2-128">Für einige Länder/Regionen können Sie Servicenummern für Ihre Konferenzbrücken über das Microsoft Teams Admin Center erhalten.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-128">For some countries/regions, you can get service numbers for your conferencing bridges using the Microsoft Teams admin center.</span></span> <span data-ttu-id="ab5c2-129">Siehe [Abrufen von Servicetelefonnummern](/microsoftteams/getting-service-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="ab5c2-129">See [Getting service phone numbers](/microsoftteams/getting-service-phone-numbers).</span></span>
    
- <span data-ttu-id="ab5c2-130">**Portieren von bestehenden Servicenummern**.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-130">**Port your existing service numbers**.</span></span> <span data-ttu-id="ab5c2-131">Portieren oder übertragen Sie vorhandene Telefonnummern von Ihrem derzeitigen Dienstanbieter oder Netzbetreiber zu Microsoft 365 oder Office 365.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-131">To port or transfer existing numbers from your current service provider or phone carrier to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="ab5c2-132">Über [Übertragen von Telefonnummern zu Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) oder [Rufnummern für Ihre Organisation verwalten](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) erhalten Sie weitere hilfreiche Informationen.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-132">You can see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md) or [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information to help you do this.</span></span>  
  
- <span data-ttu-id="ab5c2-133">**Verwenden eines Anforderungsformulars für neue Telefonnummern**.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-133">**Use a request form for new numbers**.</span></span> <span data-ttu-id="ab5c2-134">Manchmal können Sie (je nach Land/Region) Ihre neuen Servicenummern nicht über das Microsoft Teams Admin Center beziehen, oder Sie benötigen bestimmte Telefonnummern oder Ortsvorwahlen.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-134">Sometimes (depending on your country/region) you won't be able to get your new service numbers using the Microsoft Teams admin center, or you will need specific phone numbers or area codes.</span></span> <span data-ttu-id="ab5c2-135">Wenn dies der Fall ist, müssen Sie ein Formular herunterladen und an uns zurücksenden.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-135">If so, you will need to download a form and send it back to us.</span></span> <span data-ttu-id="ab5c2-136">Weitere Informationen finden Sie unter [Verwalten von Rufnummern für Ihre Organisation](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="ab5c2-136">See [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) for more information.</span></span> 
    
## <a name="step-4-assign-a-service-number-to-the-conferencing-bridge"></a><span data-ttu-id="ab5c2-137">Schritt 4: Zuweisen einer Servicenummer zur Konferenzbrücke</span><span class="sxs-lookup"><span data-stu-id="ab5c2-137">Step 4: Assign a service number to the conferencing bridge</span></span>
<span data-ttu-id="ab5c2-138"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ab5c2-138"><a name="__top"> </a></span></span>

<span data-ttu-id="ab5c2-139">Sobald Sie Ihre gebührenpflichtigen und/oder gebührenfreien Telefonnummern für Ihre Konferenzbrücke erhalten, müssen Sie die Nummern zuweisen, damit sie für die Einladungen zu den Besprechungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-139">Once you get your toll and/or toll-free phone numbers for your conferencing bridge, you need to assign the numbers so they can be used on meeting invitations.</span></span>  

<span data-ttu-id="ab5c2-140">Führen Sie die folgenden Schritte aus, um Ihrer Audiokonferenzbrücke eine neue Rufnummer zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="ab5c2-140">Follow these steps to assign a new phone number to your audio conferencing bridge.</span></span>

<span data-ttu-id="ab5c2-141">![Ein Symbol mit dem Skype for Business-Logo](media/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers:**</span><span class="sxs-lookup"><span data-stu-id="ab5c2-141">![An icon showing the Skype for Business logo](media/sfb-logo-30x30.png) **Using the Skype for Business admin center:**</span></span>

 1. <span data-ttu-id="ab5c2-142">Wechselns Sie zum **Microsoft 365 Admin Center** > **Admin Center** > **Teams** > **Altes Portal**.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-142">Go to the **Microsoft 365 admin center** > **Admin centers** > **Teams** > **Legacy portal**.</span></span>
 2. <span data-ttu-id="ab5c2-143">Wählen Sie **Anruf** > **Telefonnummern** aus.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-143">Select **Voice** > **Phone numbers**.</span></span>
 3. <span data-ttu-id="ab5c2-144">Wählen Sie die entsprechende Telefonnummer aus, und klicken Sie auf **Zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-144">Select the phone number, and click **Assign**.</span></span>

<span data-ttu-id="ab5c2-145">Weitere Informationen finden Sie unter [Ändern der Telefonnummern Ihrer Audiokonferenzbrücke](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="ab5c2-145">For more details, see [Change the phone numbers on your Audio Conferencing bridge](change-the-phone-numbers-on-your-audio-conferencing-bridge.md).</span></span>

## <a name="step-5-set-the-default-and-alternate-languages-for-a-conferencing-bridge"></a><span data-ttu-id="ab5c2-146">Schritt 5: Legen Sie die Standard- und Alternativsprachen für eine Konferenzbrücke fest</span><span class="sxs-lookup"><span data-stu-id="ab5c2-146">Step 5: Set the default and alternate languages for a conferencing bridge</span></span>
<span data-ttu-id="ab5c2-147"><a name="__top"> </a> Als Nächstes sollten Sie die [Sprachen für die automatische Telefonzentrale für Audiokonferenzen in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) festlegen, die die automatische Telefonkonferenzzentrale verwendet, um einen Anrufer zu begrüßen, wenn er sich mit einer Telefonnummer für Audiokonferenzen einwählt.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-147"><a name="__top"> </a> Next, you want to [Set auto attendant languages for Audio Conferencing in Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) that the conferencing auto attendant uses to greet callers when they dial in to a phone number for Audio Conferencing.</span></span> 

<span data-ttu-id="ab5c2-148">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**:</span><span class="sxs-lookup"><span data-stu-id="ab5c2-148">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="ab5c2-149">Wechseln Sie über das Dashboard zu **Besprechungen** > **Konferenzbrücken**.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-149">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="ab5c2-150">Wählen Sie die Telefonnummer der Konferenzbrücke, klicken Sie auf **Bearbeiten**, und wählen Sie dann die Standardsprache aus.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-150">Select the conferencing bridge phone number, click **Edit**, and then choose the default language.</span></span>

## <a name="step-6-set-your-conferencing-bridge-settings"></a><span data-ttu-id="ab5c2-151">Schritt 6: Servicenummern für Ihre Konferenzbrücken einstellen</span><span class="sxs-lookup"><span data-stu-id="ab5c2-151">Step 6: Set your conferencing bridge settings</span></span>
<span data-ttu-id="ab5c2-152"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ab5c2-152"><a name="__top"> </a></span></span>
    
<span data-ttu-id="ab5c2-153">Nachdem Sie Ihre Konferenzbrücke eingerichtet haben, vergewissern Sie sich, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten; wenn nicht, können Sie sie ändern.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-153">After setting up your conferencing bridge, verify that the default settings such as entry/exit notifications and PIN length are the ones you want to use; if they're not, you can change them.</span></span> 

<span data-ttu-id="ab5c2-154">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**:</span><span class="sxs-lookup"><span data-stu-id="ab5c2-154">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="ab5c2-155">Wechseln Sie über das Dashboard zu **Besprechungen** > **Konferenzbrücken**.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-155">From the Dashboard, go to **Meetings** > **Conference bridges**.</span></span>
2. <span data-ttu-id="ab5c2-156">Wählen Sie **Brückeneinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-156">Select **Bridge settings**.</span></span> <span data-ttu-id="ab5c2-157">Der **Brücke**-Einstellungsbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-157">This will open the **Bridge settings** pane.</span></span> 

<span data-ttu-id="ab5c2-158">Weitere Informationen finden Sie unter [Einstellungen für eine Audiokonferenzbrücke ändern](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="ab5c2-158">For more details, see [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>

## <a name="step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings"></a><span data-ttu-id="ab5c2-159">Schritt 7: Zuweisen von Einwahlnummern für Benutzer, die Besprechungen leiten</span><span class="sxs-lookup"><span data-stu-id="ab5c2-159">Step 7: Assign dial-in phone numbers for users who lead meetings</span></span>

<span data-ttu-id="ab5c2-160">Nachdem Sie eine Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und gebührenfreien Nummern für Ihre Benutzer festlegen.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-160">After you have created an Audio Conferencing bridge, you need to set the toll and toll-free numbers for your users.</span></span>

<span data-ttu-id="ab5c2-161">Sie müssen dies für alle Personen in Ihrer Organisation tun, die Besprechungen leiten oder planen.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-161">You will need to do this for all of the people in your organization who lead or schedule meetings.</span></span> 

<span data-ttu-id="ab5c2-162">![Ein Symbol mit dem Microsoft Teams-Logo](media/teams-logo-30x30.png) **Unter Verwendung des Microsoft Teams Admin Centers**:</span><span class="sxs-lookup"><span data-stu-id="ab5c2-162">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**:</span></span>

1. <span data-ttu-id="ab5c2-163">Klicken Sie im Dashboard auf **Benutzer**, wählen Sie den entsprechenden Benutzer aus der Liste aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-163">From the Dashboard, click **Users**, select the user from the list, and select **Edit**.</span></span>
2. <span data-ttu-id="ab5c2-164">Klicken Sie neben **Audiokonferenzen** auf **Bearbeiten**, und wählen Sie dann im Bereich **Audiokonferenzen** eine Nummer aus den Listen der **gebührenpflichtigen** und **gebührenfreien** Telefonnummern aus.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-164">Select **Edit** next to **Audio Conferencing**, and then in the **Audio Conferencing** pane, choose a number in the **Toll number** and **Toll-free** number lists.</span></span>

<span data-ttu-id="ab5c2-165">Weitere Informationen finden Sie unter [Zuweisen von Microsoft als Anbieter von Audiokonferenzen](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="ab5c2-165">If you need more details, see [Assign Microsoft as the audio conferencing provider](/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>


## <a name="step-8-set-up-meeting-invitations-optional"></a><span data-ttu-id="ab5c2-166">Schritt 8: Besprechungseinladungen einrichten (optional)</span><span class="sxs-lookup"><span data-stu-id="ab5c2-166">Step 8: Set up meeting invitations (optional)</span></span>
<span data-ttu-id="ab5c2-167"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="ab5c2-167"><a name="__top"> </a></span></span>
 
<span data-ttu-id="ab5c2-168">Die für den Nutzer festgelegten Einwahlnummern werden automatisch den Besprechungseinladungen hinzugefügt, die Besprechungsteilnehmern zugesendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-168">The dial-in numbers that are set for the user will be automatically added to the meeting invitations that are sent to meeting attendees.</span></span> <span data-ttu-id="ab5c2-169">Sie können jedoch Ihre eigenen Hilfe- und rechtliche Links, eine SMS und eine kleine Firmengrafik hinzufügen, wenn Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="ab5c2-169">However, you can add your own help and legal links, a text message, and small company graphic if you want.</span></span> <span data-ttu-id="ab5c2-170">Siehe [Anpassen von Besprechungseinladungen](meeting-settings-in-teams.md#customize-meeting-invitations).</span><span class="sxs-lookup"><span data-stu-id="ab5c2-170">See [Customize meeting invitations](meeting-settings-in-teams.md#customize-meeting-invitations).</span></span>
   
## <a name="related-topics"></a><span data-ttu-id="ab5c2-171">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ab5c2-171">Related topics</span></span>

[<span data-ttu-id="ab5c2-172">Allgemeine Fragen zu Audiokonferenzen</span><span class="sxs-lookup"><span data-stu-id="ab5c2-172">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
  
[<span data-ttu-id="ab5c2-173">Telefonnummern für Audiokonferenzen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab5c2-173">Phone numbers for Audio Conferencing in Microsoft Teams</span></span>](phone-numbers-for-audio-conferencing-in-teams.md)
  
[<span data-ttu-id="ab5c2-174">Festlegen von Optionen für Onlinebesprechungen und Telefonkonferenzen</span><span class="sxs-lookup"><span data-stu-id="ab5c2-174">Set options for online meetings and conference calls</span></span>](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)
