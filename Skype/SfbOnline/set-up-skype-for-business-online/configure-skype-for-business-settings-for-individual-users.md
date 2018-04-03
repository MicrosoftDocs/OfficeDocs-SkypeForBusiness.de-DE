---
title: Administratoren Skype for Business-Einstellungen für einzelne Benutzer konfigurieren
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
ms.openlocfilehash: 8659434542696ccb37a0353cd491cc0d01f01e30
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="28acb-103">Administratoren: Skype for Business-Einstellungen für einzelne Benutzer konfigurieren</span><span class="sxs-lookup"><span data-stu-id="28acb-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="28acb-104">In diesem Artikel wird erläutert, wie Administratoren Skype for Business für eine kleine Anzahl von Benutzern einrichten.</span><span class="sxs-lookup"><span data-stu-id="28acb-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="28acb-105">Klicken Sie dazu diese Schritte in einer Sammeloperation haben wir Links zu Windows PowerShell-Cmdlets enthalten, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="28acb-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="28acb-106">Informationen darüber, wie Sie zulassen (bzw. blockieren), dass alle Personen in Ihrem Unternehmen mit Personen außerhalb des Unternehmens kommunizieren können, finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="28acb-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="28acb-107">[Wenden Sie sich an externe Skype für Unternehmensbenutzer durch Benutzer zulassen](allow-users-to-contact-external-skype-for-business-users.md): Sie können Ihrer Organisation verwenden können erweiterte Skype für Business-Features (Desktops freigeben, suchen Sie nach, wer online, usw. ist) kommunizieren mit Personen in einem bestimmten vertrauenswürdigen (verbundgeschäftspartner).</span><span class="sxs-lookup"><span data-stu-id="28acb-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="28acb-108">Der Artikel wird auch die Kommunikation mit bestimmten Domänen blockieren erläutert.</span><span class="sxs-lookup"><span data-stu-id="28acb-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="28acb-109">[Lassen Sie Skype für Unternehmensbenutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="28acb-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="28acb-110">Sie können zulassen, dass die Benutzer in Ihrer Organisation mit der kostenlosen App Skype for Business andere Skype-Benutzer suchen und mit diesen chatten können.</span><span class="sxs-lookup"><span data-stu-id="28acb-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="28acb-111">Konfigurieren von allgemeinen Einstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="28acb-111">Configure general settings for one user</span></span>
<span data-ttu-id="28acb-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="28acb-112"></span></span>

<span data-ttu-id="28acb-113">Sie benötigen [Administratorberechtigungen](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , um diese Schritte auszuführen.</span><span class="sxs-lookup"><span data-stu-id="28acb-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="28acb-114">Melden Sie sich bei Office 365 mit Ihrem Firmen- oder Schulkonto an.</span><span class="sxs-lookup"><span data-stu-id="28acb-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="28acb-115">Wählen Sie **Admin Center** > **Skype for Business** aus.</span><span class="sxs-lookup"><span data-stu-id="28acb-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="28acb-116">Wählen Sie **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="28acb-116">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="28acb-118">Wählen Sie aus, welche Benutzer Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="28acb-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="28acb-119">Wählen Sie im rechten Bereich **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="28acb-119">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="28acb-121">Aktivieren oder deaktivieren Sie auf der Optionsseite **Allgemein** die Kontrollkästchen neben den Funktionen, die Sie ändern möchten, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="28acb-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="28acb-122">**Option**</span><span class="sxs-lookup"><span data-stu-id="28acb-122">**Option**</span></span>|<span data-ttu-id="28acb-123">**Details**</span><span class="sxs-lookup"><span data-stu-id="28acb-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28acb-124">Audio und HD-Video</span><span class="sxs-lookup"><span data-stu-id="28acb-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="28acb-125">Zulassen, dass diese Person Audiobesprechungen bzw. Audio- und Videobesprechungen aufzeichnen kann, oder die Planung von Besprechungen für keinen Benutzer zulassen (Keiner).</span><span class="sxs-lookup"><span data-stu-id="28acb-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="28acb-126">Unterhaltungen und Besprechungen aufzeichnen</span><span class="sxs-lookup"><span data-stu-id="28acb-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="28acb-127">Wählen Sie aus, was diese Person aufzeichnen darf.</span><span class="sxs-lookup"><span data-stu-id="28acb-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="28acb-128">Diese Option ist nicht mit Skype für Business Basic verfügbar.</span><span class="sxs-lookup"><span data-stu-id="28acb-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="28acb-129">Nicht archivierte Funktionen aus Konformitätsgründen deaktivieren</span><span class="sxs-lookup"><span data-stu-id="28acb-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="28acb-130">Wählen Sie diese Option aus, wenn Sie rechtlich zur Aufbewahrung elektronisch gespeicherter Informationen verpflichtet sind.</span><span class="sxs-lookup"><span data-stu-id="28acb-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="28acb-131">Durch Auswählen dieser Option wird deaktiviert Features, die erfasst werden nicht, wenn Sie eine [Compliance-Archiv](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) im Exchange Administrationscenter in eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="28acb-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="28acb-132">Die folgenden Features werden deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="28acb-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="28acb-133">Dateiübertragung mittels Chat</span><span class="sxs-lookup"><span data-stu-id="28acb-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="28acb-134">Freigegebene OneNote-Seiten</span><span class="sxs-lookup"><span data-stu-id="28acb-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="28acb-135">PowerPoint-Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="28acb-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="28acb-136">Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28acb-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="28acb-137">Finden Sie unter [Verwalten von Richtlinien in Skype für Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="28acb-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="28acb-138">Sperren der externen Kommunikation</span><span class="sxs-lookup"><span data-stu-id="28acb-138">Block external communications</span></span>
<span data-ttu-id="28acb-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="28acb-139"></span></span>

<span data-ttu-id="28acb-140">Nachdem Sie die [Zulassen, dass Skype for Business-Benutzer Skype-Kontakte hinzufügen](let-skype-for-business-users-add-skype-contacts.md) für alle Benutzer in Ihrem Unternehmen aktiviert haben, können Sie unter Ausführung der folgenden Schritte einzelne externe Kommunikationen für bestimmte Benutzer sperren.</span><span class="sxs-lookup"><span data-stu-id="28acb-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="28acb-141">Wählen Sie **Benutzer**, wählen Sie die Benutzer, dessen Einstellungen Sie deaktivieren möchten, und wählen Sie dann auf **Bearbeiten** ![bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="28acb-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="28acb-142">Wählen Sie **Externe Kommunikation** aus, und deaktivieren Sie dann die Optionen Ihren Anforderungen entsprechend:</span><span class="sxs-lookup"><span data-stu-id="28acb-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="28acb-143">**Externe Skype for Business-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Skype for Business-Benutzern in Partnerdomänen kommunizieren soll.</span><span class="sxs-lookup"><span data-stu-id="28acb-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="28acb-144">**Externe Skype-Benutzer**: Deaktivieren Sie dieses Kontrollkästchen, wenn der Benutzer nicht mit Personen kommunizieren soll, die die kostenlose Skype-App verwenden.</span><span class="sxs-lookup"><span data-stu-id="28acb-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="28acb-145">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="28acb-145">Click **Save**.</span></span>
    
<span data-ttu-id="28acb-146">Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28acb-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="28acb-147">Finden Sie unter [Verwalten der Kommunikation in Skype für Business Online mit externen Benutzern und Organisationen](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="28acb-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="28acb-148">Bearbeiten von Audiokonferenzen-Einstellungen für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="28acb-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="28acb-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="28acb-149"></span></span>

1. <span data-ttu-id="28acb-150">Wählen Sie **Benutzer**aus, wählen Sie den Benutzer, dessen Sie um zu bearbeiten, WAN-Audiokonferenzen Einstellungen, und wählen Sie dann auf **Bearbeiten** ![bearbeiten](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="28acb-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="28acb-151">Wählen Sie **Audiokonferenzen**, wählen Sie Ihren Audiokonferenz-Anbieter, geben Sie oder ändern Sie die angeforderte Informationen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="28acb-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="28acb-152">**Audiokonferenzeinstellung**</span><span class="sxs-lookup"><span data-stu-id="28acb-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="28acb-153">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="28acb-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28acb-154">**Name des Anbieters**</span><span class="sxs-lookup"><span data-stu-id="28acb-154">**Provider name**</span></span> <br/> |<span data-ttu-id="28acb-155">Wählen Sie aus der Liste der Anbieter.</span><span class="sxs-lookup"><span data-stu-id="28acb-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="28acb-156">**Gebührenpflichtige Nummer** (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="28acb-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="28acb-157">Für ein Drittanbieter-ACP sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="28acb-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="28acb-158">Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet wird, werden diese Zahlen, die für die audiokonferenzbrücke festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="28acb-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="28acb-159">Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="28acb-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="28acb-160">**Gebührenfreien Nummer**</span><span class="sxs-lookup"><span data-stu-id="28acb-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="28acb-161">Für ein Drittanbieter-ACP sind diese Rufnummern diejenigen aus, die Sie vom Anbieter von Audiokonferenzen erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="28acb-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="28acb-162">Wenn der Benutzer Microsoft als Anbieter von Audiokonferenzen verwendet wird, werden diese Zahlen, die für die audiokonferenzbrücke festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="28acb-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="28acb-163">Formatieren Sie die Zahlen in Skype für Geschäfts- und Microsoft-Teams, Besprechungsanfragen angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="28acb-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="28acb-164">**Konferenz-ID und PIN-Nummer** (erforderlich)</span><span class="sxs-lookup"><span data-stu-id="28acb-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="28acb-165">Die Teilnehmer PIN oder Konferenz Code verwendet, um an Besprechungen teilnehmen, die von diesem Benutzer geplant werden und werden von einem Drittanbieter-Audiokonferenz-Anbieter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="28acb-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="28acb-166">Wenn der Benutzer Microsoft als Audiokonferenz-Anbieter verwendet, wird nicht erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="28acb-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="28acb-167">Verwenden Sie zum Konfigurieren dieser Einstellungen in einer Sammeloperation PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28acb-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="28acb-168">Finden Sie unter [Einrichten des Telefons, Zahlen auf enthalten lädt](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="28acb-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="28acb-169">See Also</span><span class="sxs-lookup"><span data-stu-id="28acb-169">Related topics</span></span> 

[<span data-ttu-id="28acb-170">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="28acb-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="28acb-171">Add-On-Lizenzierung für Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="28acb-171">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 