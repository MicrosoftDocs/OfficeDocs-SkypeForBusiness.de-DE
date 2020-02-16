---
title: Administratoren Skype for Business-Einstellungen für einzelne Benutzer konfigurieren
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Hier erfahren Sie, wie Sie die Skype for Business-Einstellungen für einzelne Benutzer ändern, beispielsweise Audio-und Videokonferenzen, Aufzeichnung von Anrufen und Besprechungen. '
ms.openlocfilehash: 756de9829194139f39c7618e0c8bbd74f3418264
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010888"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="784a2-103">Administratoren: Skype for Business-Einstellungen für einzelne Benutzer konfigurieren</span><span class="sxs-lookup"><span data-stu-id="784a2-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="784a2-104">In diesem Artikel wird erläutert, wie Administratoren Skype for Business für eine kleine Anzahl von Benutzern einrichten.</span><span class="sxs-lookup"><span data-stu-id="784a2-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="784a2-105">Um diese Schritte in Massen durchführen zu können, haben wir Links zu den Windows PowerShell-Cmdlets hinzugefügt, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="784a2-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="784a2-106">Informationen darüber, wie Sie zulassen (bzw. blockieren), dass alle Personen in Ihrem Unternehmen mit Personen außerhalb des Unternehmens kommunizieren können, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="784a2-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="784a2-107">[Zulassen, dass Benutzer externe Skype for Business-Benutzer kontaktieren](allow-users-to-contact-external-skype-for-business-users.md): Sie können Ihrer Organisation erweiterte Skype for Business-Funktionen (Freigeben von Desktops, suchen nach Online-Nutzern usw.) für die Kommunikation mit Personen in einem bestimmten vertrauenswürdigen Unternehmen zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="784a2-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="784a2-108">In diesem Artikel wird auch erläutert, wie Sie die Kommunikation mit bestimmten Domänen blockieren.</span><span class="sxs-lookup"><span data-stu-id="784a2-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="784a2-109">[Lassen Sie Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="784a2-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="784a2-110">Sie können zulassen, dass die Benutzer in Ihrer Organisation mit der kostenlosen App Skype for Business andere Skype-Benutzer suchen und mit diesen chatten können.</span><span class="sxs-lookup"><span data-stu-id="784a2-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="784a2-111">Konfigurieren von allgemeinen Einstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="784a2-111">Configure general settings for one user</span></span>
<span data-ttu-id="784a2-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="784a2-112"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="784a2-113">Sie müssen über [Administratorberechtigungen](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) verfügen, um diese Schritte ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="784a2-113">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="784a2-114">![Ein Symbol mit dem Skype for Business-Logo](../images/sfb-logo-30x30.png) **Unter Verwendung des Skype for Business Admin Centers**</span><span class="sxs-lookup"><span data-stu-id="784a2-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="784a2-115">Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto bei Office 365 an.</span><span class="sxs-lookup"><span data-stu-id="784a2-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="784a2-116">Wählen Sie **Admin Center** > **Skype for Business** aus.</span><span class="sxs-lookup"><span data-stu-id="784a2-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="784a2-117">Wählen Sie **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="784a2-117">Choose **Users**.</span></span>
    
    ![Wählen Sie im Skype for Business Admin Centerdie Option Benutzer aus.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="784a2-119">Wählen Sie aus, welche Benutzer Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="784a2-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="784a2-120">Wählen Sie im rechten Bereich **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="784a2-120">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="784a2-122">Aktivieren oder deaktivieren Sie auf der Optionsseite **Allgemein** die Kontrollkästchen neben den Funktionen, die Sie ändern möchten, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="784a2-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="784a2-123">**Option**</span><span class="sxs-lookup"><span data-stu-id="784a2-123">**Option**</span></span>|<span data-ttu-id="784a2-124">**Details**</span><span class="sxs-lookup"><span data-stu-id="784a2-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="784a2-125">Audio und HD-Video</span><span class="sxs-lookup"><span data-stu-id="784a2-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="784a2-126">Dieser Person gestatten, audiobesprechungen, Audio-und Videobesprechungen aufzuzeichnen oder keine Besprechungen zu planen (keine).</span><span class="sxs-lookup"><span data-stu-id="784a2-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="784a2-127">Unterhaltungen und Besprechungen aufzeichnen</span><span class="sxs-lookup"><span data-stu-id="784a2-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="784a2-128">Wählen Sie aus, was diese Person aufzeichnen darf.</span><span class="sxs-lookup"><span data-stu-id="784a2-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="784a2-129">Diese Option steht in Skype for Business Basic nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="784a2-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="784a2-130">Nicht archivierte Funktionen aus Konformitätsgründen deaktivieren</span><span class="sxs-lookup"><span data-stu-id="784a2-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="784a2-131">Wählen Sie diese Option aus, wenn Sie rechtlich zur Aufbewahrung elektronisch gespeicherter Informationen verpflichtet sind.</span><span class="sxs-lookup"><span data-stu-id="784a2-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="784a2-132">Wenn Sie diese Option auswählen, werden Features deaktiviert, die nicht erfasst werden, wenn Sie im Exchange Admin Center einen [in-situ-](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) Speicher eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="784a2-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="784a2-133">Die folgenden Features werden deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="784a2-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="784a2-134">Dateiübertragung mittels Chat</span><span class="sxs-lookup"><span data-stu-id="784a2-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="784a2-135">Freigegebene OneNote-Seiten</span><span class="sxs-lookup"><span data-stu-id="784a2-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="784a2-136">PowerPoint-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="784a2-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="784a2-137">Wenn Sie diese Einstellungen massenhaft konfigurieren möchten, verwenden Sie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="784a2-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="784a2-138">Weitere Informationen finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="784a2-138">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="784a2-139">Sperren der externen Kommunikation</span><span class="sxs-lookup"><span data-stu-id="784a2-139">Block external communications</span></span>
<span data-ttu-id="784a2-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="784a2-140"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="784a2-141">Nachdem Sie die [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) für alle Benutzer in Ihrem Unternehmen aktiviert haben, können Sie unter Ausführung der folgenden Schritte einzelne externe Kommunikationen für bestimmte Benutzer sperren.</span><span class="sxs-lookup"><span data-stu-id="784a2-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="784a2-142">Wählen Sie **Benutzer**aus, wählen Sie die Benutzer aus, deren Einstellungen Sie deaktivieren möchten, **und wählen Sie dann bearbeiten aus** ![](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="784a2-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="784a2-143">Wählen Sie **Externe Kommunikation** aus, und deaktivieren Sie dann die Optionen Ihren Anforderungen entsprechend:</span><span class="sxs-lookup"><span data-stu-id="784a2-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="784a2-144">**Externe Skype for Business-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Skype for Business-Benutzern in Partnerdomänen kommunizieren soll.</span><span class="sxs-lookup"><span data-stu-id="784a2-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="784a2-145">**Externe Skype-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Personen kommunizieren soll, die die kostenlose Skype-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="784a2-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="784a2-146">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="784a2-146">Click **Save**.</span></span>
    
<span data-ttu-id="784a2-147">Wenn Sie diese Einstellungen massenhaft konfigurieren möchten, verwenden Sie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="784a2-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="784a2-148">Weitere Informationen finden Sie unter [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="784a2-148">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="784a2-149">Bearbeiten von Audio-Konferenzeinstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="784a2-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="784a2-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="784a2-150"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="784a2-151">Wählen Sie **Benutzer**aus, wählen Sie den Benutzer aus, dessen audiokonferenzeinstellungen Sie bearbeiten möchten, **und wählen Sie dann bearbeiten aus** ![](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="784a2-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="784a2-152">Wählen Sie **Audiokonferenzen**aus, wählen Sie Ihren Audiokonferenz-Anbieter aus, geben Sie die angeforderten Informationen ein, oder ändern Sie Sie, und klicken Sie auf **Speichern**</span><span class="sxs-lookup"><span data-stu-id="784a2-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="784a2-153">**Audiokonferenzeinstellung**</span><span class="sxs-lookup"><span data-stu-id="784a2-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="784a2-154">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="784a2-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="784a2-155">**Anbietername**</span><span class="sxs-lookup"><span data-stu-id="784a2-155">**Provider name**</span></span> <br/> |<span data-ttu-id="784a2-156">Wählen Sie Ihren Anbieter in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="784a2-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="784a2-157">**Gebührenpflichtige Nummer** (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="784a2-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="784a2-158">Bei einem Drittanbieter-ACP sind diese Telefonnummern diejenigen, die Sie vom Audiokonferenz-Anbieter erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="784a2-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="784a2-159">Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="784a2-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="784a2-160">Formatieren Sie die Zahlen so, wie Sie in Skype for Business-und Microsoft Teams-Besprechungsanfragen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="784a2-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="784a2-161">**Gebührenfreien Nummer**</span><span class="sxs-lookup"><span data-stu-id="784a2-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="784a2-162">Bei einem Drittanbieter-ACP sind diese Telefonnummern diejenigen, die Sie vom Audiokonferenz-Anbieter erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="784a2-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="784a2-163">Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="784a2-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="784a2-164">Formatieren Sie die Zahlen so, wie Sie in Skype for Business-und Microsoft Teams-Besprechungsanfragen angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="784a2-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="784a2-165">**Konferenz-ID und PIN** (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="784a2-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="784a2-166">Die Teilnehmer-PIN oder der konferenzcode, der für die Teilnahme an Besprechungen verwendet wird, die von diesem Benutzer geplant werden und von einem Drittanbieter für Audiokonferenzen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="784a2-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="784a2-167">Wenn der Benutzer Microsoft als Audiokonferenz-Anbieter verwendet, ist dies nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="784a2-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="784a2-168">Wenn Sie diese Einstellungen massenhaft konfigurieren möchten, verwenden Sie PowerShell.</span><span class="sxs-lookup"><span data-stu-id="784a2-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="784a2-169">Weitere Informationen finden Sie unter [Einrichten der Telefonnummern in Einladungen](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Einrichten Ihres Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="784a2-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="784a2-170">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="784a2-170">Related topics</span></span> 

[<span data-ttu-id="784a2-171">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="784a2-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="784a2-172">Add-On-Lizenzierung für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="784a2-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
