---
title: Administratoren Skype for Business-Einstellungen für einzelne Benutzer konfigurieren
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 9dde738431e8afac4837b6f4bcab9b955787927a
ms.sourcegitcommit: 6ad3ce36140464319f5957652331acd6a4273f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2018
ms.locfileid: "26561686"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="d16f4-103">Administratoren: Skype for Business-Einstellungen für einzelne Benutzer konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d16f4-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="d16f4-104">In diesem Artikel wird erläutert, wie Administratoren Skype for Business für eine kleine Anzahl von Benutzern einrichten.</span><span class="sxs-lookup"><span data-stu-id="d16f4-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="d16f4-105">Klicken Sie dazu diese Schritte in einer Sammeloperation haben wir Links zu Windows PowerShell-Cmdlets enthalten, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="d16f4-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="d16f4-106">Informationen darüber, wie Sie zulassen (bzw. blockieren), dass alle Personen in Ihrem Unternehmen mit Personen außerhalb des Unternehmens kommunizieren können, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="d16f4-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="d16f4-107">[Wenden Sie sich an externe Skype für Unternehmensbenutzer durch Benutzer zulassen](allow-users-to-contact-external-skype-for-business-users.md): Sie können Ihrer Organisation verwenden können erweiterte Skype für Business-Features (Desktops freigeben, suchen Sie nach, wer online, usw. ist) kommunizieren mit Personen in einem bestimmten vertrauenswürdigen (verbundgeschäftspartner).</span><span class="sxs-lookup"><span data-stu-id="d16f4-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="d16f4-108">Der Artikel wird auch die Kommunikation mit bestimmten Domänen blockieren erläutert.</span><span class="sxs-lookup"><span data-stu-id="d16f4-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="d16f4-109">[Lassen Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="d16f4-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="d16f4-110">Sie können zulassen, dass die Benutzer in Ihrer Organisation mit der kostenlosen App Skype for Business andere Skype-Benutzer suchen und mit diesen chatten können.</span><span class="sxs-lookup"><span data-stu-id="d16f4-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="d16f4-111">Konfigurieren von allgemeinen Einstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d16f4-111">Configure general settings for one user</span></span>
<span data-ttu-id="d16f4-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="d16f4-112"></span></span>

<span data-ttu-id="d16f4-113">Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , um diese Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d16f4-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="d16f4-114">![SFB-Logo-30x30.png](../images/sfb-logo-30x30.png) **mithilfe der Skype für Business Administrationscenter**</span><span class="sxs-lookup"><span data-stu-id="d16f4-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="d16f4-115">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="d16f4-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="d16f4-116">Wählen Sie **Admin Center** > **Skype for Business** aus.</span><span class="sxs-lookup"><span data-stu-id="d16f4-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="d16f4-117">Wählen Sie **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="d16f4-117">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="d16f4-119">Wählen Sie aus, welche Benutzer Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="d16f4-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="d16f4-120">Wählen Sie im rechten Bereich **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d16f4-120">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="d16f4-122">Aktivieren oder deaktivieren Sie auf der Optionsseite **Allgemein** die Kontrollkästchen neben den Funktionen, die Sie ändern möchten, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="d16f4-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="d16f4-123">**Option**</span><span class="sxs-lookup"><span data-stu-id="d16f4-123">**Option**</span></span>|<span data-ttu-id="d16f4-124">**Details**</span><span class="sxs-lookup"><span data-stu-id="d16f4-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d16f4-125">Audio und HD-Video</span><span class="sxs-lookup"><span data-stu-id="d16f4-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="d16f4-126">Diese Person audio Besprechungen aufzuzeichnen, Audio- und Videodaten Besprechungen zulassen oder nicht ermöglicht es ihnen, alle Besprechungen (kein Rahmen) planen.</span><span class="sxs-lookup"><span data-stu-id="d16f4-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="d16f4-127">Unterhaltungen und Besprechungen aufzeichnen</span><span class="sxs-lookup"><span data-stu-id="d16f4-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="d16f4-128">Wählen Sie aus, was diese Person aufzeichnen darf.</span><span class="sxs-lookup"><span data-stu-id="d16f4-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="d16f4-129">Diese Option ist nicht mit Skype für Business Basic verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d16f4-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="d16f4-130">Nicht archivierte Funktionen aus Konformitätsgründen deaktivieren</span><span class="sxs-lookup"><span data-stu-id="d16f4-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="d16f4-131">Wählen Sie diese Option aus, wenn Sie rechtlich zur Aufbewahrung elektronisch gespeicherter Informationen verpflichtet sind.</span><span class="sxs-lookup"><span data-stu-id="d16f4-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="d16f4-132">Durch Auswählen dieser Option wird deaktiviert Features, die erfasst werden nicht, wenn Sie eine [Compliance-Archiv](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) in der Exchange-Verwaltungskonsole eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="d16f4-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="d16f4-133">Die folgenden Features werden deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="d16f4-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="d16f4-134">Dateiübertragung mittels Chat</span><span class="sxs-lookup"><span data-stu-id="d16f4-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="d16f4-135">Freigegebene OneNote-Seiten</span><span class="sxs-lookup"><span data-stu-id="d16f4-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="d16f4-136">PowerPoint-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="d16f4-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="d16f4-137">Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d16f4-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="d16f4-138">Finden Sie unter [Einrichten des Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d16f4-138">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="d16f4-139">Sperren der externen Kommunikation</span><span class="sxs-lookup"><span data-stu-id="d16f4-139">Block external communications</span></span>
<span data-ttu-id="d16f4-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="d16f4-140"></span></span>

<span data-ttu-id="d16f4-141">Nachdem Sie die [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) für alle Benutzer in Ihrem Unternehmen aktiviert haben, können Sie unter Ausführung der folgenden Schritte einzelne externe Kommunikationen für bestimmte Benutzer sperren.</span><span class="sxs-lookup"><span data-stu-id="d16f4-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="d16f4-142">Wählen Sie **Benutzer**, wählen Sie die Benutzer, dessen Einstellungen Sie deaktivieren möchten, und wählen Sie dann auf **Bearbeiten** ![bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="d16f4-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="d16f4-143">Wählen Sie **Externe Kommunikation** aus, und deaktivieren Sie dann die Optionen Ihren Anforderungen entsprechend:</span><span class="sxs-lookup"><span data-stu-id="d16f4-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="d16f4-144">**Externe Skype for Business-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Skype for Business-Benutzern in Partnerdomänen kommunizieren soll.</span><span class="sxs-lookup"><span data-stu-id="d16f4-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="d16f4-145">**Externe Skype-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Personen kommunizieren soll, die die kostenlose Skype-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="d16f4-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="d16f4-146">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d16f4-146">Click **Save**.</span></span>
    
<span data-ttu-id="d16f4-147">Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d16f4-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="d16f4-148">Finden Sie unter [Einrichten des Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="d16f4-148">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="d16f4-149">Bearbeiten von Audiokonferenzen-Einstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="d16f4-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="d16f4-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="d16f4-150"></span></span>

1. <span data-ttu-id="d16f4-151">Wählen Sie **Benutzer**aus, wählen Sie den Benutzer, dessen Sie um zu bearbeiten, WAN-Audiokonferenzen Einstellungen, und wählen Sie dann auf **Bearbeiten** ![bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="d16f4-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="d16f4-152">Wählen Sie **Audiokonferenzen**, wählen Sie Ihren Audiokonferenz-Anbieter, geben Sie oder ändern Sie die angeforderte Informationen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d16f4-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="d16f4-153">**Audiokonferenzeinstellung**</span><span class="sxs-lookup"><span data-stu-id="d16f4-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="d16f4-154">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="d16f4-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d16f4-155">**Name des Anbieters**</span><span class="sxs-lookup"><span data-stu-id="d16f4-155">**Provider name**</span></span> <br/> |<span data-ttu-id="d16f4-156">Wählen Sie aus der Liste der Anbieter.</span><span class="sxs-lookup"><span data-stu-id="d16f4-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="d16f4-157">**Gebührenpflichtige Nummer** (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="d16f4-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="d16f4-158">Für ein Drittanbieter-ACP sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="d16f4-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="d16f4-159">Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d16f4-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="d16f4-160">Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d16f4-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="d16f4-161">**Gebührenfreien Nummer**</span><span class="sxs-lookup"><span data-stu-id="d16f4-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="d16f4-162">Für ein Drittanbieter-ACP sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="d16f4-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="d16f4-163">Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet, sind dies die Nummern, die für die Audiokonferenz-Brücke festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="d16f4-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="d16f4-164">Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d16f4-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="d16f4-165">**Konferenz-ID und PIN-Nummer** (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="d16f4-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="d16f4-166">Die Teilnehmer PIN oder Konferenz Code verwendet, um an Besprechungen teilnehmen, die von diesem Benutzer geplant werden und werden von einem Drittanbieter-Audiokonferenz-Anbieter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="d16f4-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="d16f4-167">Wenn der Benutzer Microsoft als Audiokonferenz-Anbieter verwendet, wird nicht erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="d16f4-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="d16f4-168">Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d16f4-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="d16f4-169">Finden Sie unter [Einrichten des Computers für Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) [gewählte Nummern auf enthalten invites Telefonnummern festgelegt](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) .</span><span class="sxs-lookup"><span data-stu-id="d16f4-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="d16f4-170">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d16f4-170">Related topics</span></span> 

[<span data-ttu-id="d16f4-171">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d16f4-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="d16f4-172">Add-On-Lizenzierung für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d16f4-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 