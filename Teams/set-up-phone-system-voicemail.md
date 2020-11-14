---
title: Einrichten von Cloudvoicemail
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Hier erfahren Sie, wie Sie Cloud Voicemail für Ihre Benutzer einrichten. '
ms.openlocfilehash: df8e6d5962e3bff2148165466400e90ee3a4607d
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031071"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="4eee3-103">Einrichten von Cloudvoicemail</span><span class="sxs-lookup"><span data-stu-id="4eee3-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="4eee3-104">Dieser Artikel richtet sich an den Microsoft 365-oder Office 365-Administrator, wie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) beschrieben, die das Feature für die Cloud-Voicemail für alle Personen im Unternehmen einrichten möchten.</span><span class="sxs-lookup"><span data-stu-id="4eee3-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="4eee3-105">Cloud Voicemail unterstützt das Hinterlegen von Voicemail-Nachrichten nur in einem Exchange-Postfach und unterstützt keine e-Mail-Systeme von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="4eee3-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="4eee3-106">Wenn eine Stellvertretung einen Anruf im Namen eines delegierenden beantwortet, sind Benachrichtigungen in Cloud Voicemail nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4eee3-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="4eee3-107">Benutzer können Benachrichtigungen für verpasste Anrufe erhalten.</span><span class="sxs-lookup"><span data-stu-id="4eee3-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="4eee3-108">Cloud-only-Umgebungen: Einrichten von Cloud Voicemail für Online-Telefon System Benutzer</span><span class="sxs-lookup"><span data-stu-id="4eee3-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="4eee3-109">Für Benutzer von Online-Telefonsystemen wird Cloud Voicemail automatisch für Benutzer eingerichtet und bereitgestellt, nachdem Sie den Benutzern eine **Telefonsystem** Lizenz zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="4eee3-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="4eee3-110">Bei Online-Skype for Business-Telefon System Benutzern mit lokal bereitgestellten Telefonnummern müssen Sie möglicherweise die gehostete Voicemail mit der [$true "CsUser-HostedVoicemail](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)" aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4eee3-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="4eee3-111">Einrichten von Cloud Voicemail für Exchange Server-Postfachbenutzer</span><span class="sxs-lookup"><span data-stu-id="4eee3-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="4eee3-112">Die folgenden Informationen besprechen die Konfiguration von Cloud Voicemail für die Arbeit mit Benutzern, die für das Telefon System online sind, aber über Ihr Postfach auf dem Exchange-Server verfügen.</span><span class="sxs-lookup"><span data-stu-id="4eee3-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="4eee3-113">Voicemail-Nachrichten werden an das Exchange-Postfach der Benutzer über einen SMTP-Router über den Exchange Online-Schutz übermittelt.</span><span class="sxs-lookup"><span data-stu-id="4eee3-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="4eee3-114">Um eine erfolgreiche Zustellung dieser Nachrichten zu ermöglichen, stellen Sie sicher, dass Exchange-Connectors zwischen Ihren Exchange-Servern und dem Exchange Online-Schutz ordnungsgemäß konfiguriert sind. [Verwenden Sie Connectors zum Konfigurieren des Nachrichtenflusses](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="4eee3-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="4eee3-115">Um Voicemail-Features wie das Anpassen von Begrüßungen und visuelle Voicemail in Skype for Business-Clients zu aktivieren, ist die Konnektivität von Microsoft 365 oder Office 365 mit dem Exchange Server-Postfach über Exchange-Webdienste erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4eee3-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="4eee3-116">Um diese Verbindung zu aktivieren, müssen Sie das neue Exchange-OAuth-Authentifizierungsprotokoll konfigurieren, das unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange-und Exchange Online-Organisationen](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)beschrieben wird, oder den Exchange-Hybrid-Assistenten in Exchange 2013 CU5 oder höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="4eee3-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="4eee3-117">Darüber hinaus müssen Sie die Integration und die OAuth zwischen Skype for Business Online und Exchange Server konfigurieren, die unter [Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="4eee3-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="4eee3-118">Einrichten von Cloud Voicemail für Skype for Business Server-Benutzer</span><span class="sxs-lookup"><span data-stu-id="4eee3-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="4eee3-119">Informationen zum Konfigurieren von Skype for Business Server-Benutzern für Cloud Voicemail finden Sie unter [Planen des Cloud Voicemail-Diensts für lokale Benutzer](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span><span class="sxs-lookup"><span data-stu-id="4eee3-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="4eee3-120">Aktivieren von geschützter Voicemail in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="4eee3-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="4eee3-121">Wenn jemand eine Sprachnachricht für einen Benutzer in Ihrer Organisation verlässt, wird die Sprachnachricht als Anlage für e-Mail-Nachrichten an das Postfach des Benutzers übermittelt.</span><span class="sxs-lookup"><span data-stu-id="4eee3-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="4eee3-122">Wenn Sie Nachrichtenfluss Regeln verwenden, um die Nachrichtenverschlüsselung anzuwenden, können Sie verhindern, dass diese Voicemail-Nachrichten an andere Empfänger weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="4eee3-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="4eee3-123">Wenn Sie Geschützte Voicemail aktivieren, können Benutzer geschützte Voicemail-Nachrichten abhören, indem Sie in Ihr Voicemail-Postfach anrufen oder die Nachricht in Outlook, Outlook im Web oder in Outlook für Android oder IOS öffnen.</span><span class="sxs-lookup"><span data-stu-id="4eee3-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="4eee3-124">Geschützte Voicemail-Nachrichten können in Skype for Business nicht geöffnet werden.</span><span class="sxs-lookup"><span data-stu-id="4eee3-124">Protected voicemail messages can't be opened in Skype for Business.</span></span>

<span data-ttu-id="4eee3-125">Weitere Informationen zur Nachrichtenverschlüsselung finden Sie unter [e-Mail-Verschlüsselung](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="4eee3-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="4eee3-126">Gehen Sie wie folgt vor, um geschützte Voicemail einzurichten:</span><span class="sxs-lookup"><span data-stu-id="4eee3-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="4eee3-127">Wechseln Sie zu und registrieren Sie sich mit https://admin.microsoft.com einem Konto mit globalen Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="4eee3-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="4eee3-128">Wählen Sie **Alle anzeigen** aus, und wechseln Sie dann zu **Admin Center**  >  **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="4eee3-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="4eee3-129">Wählen Sie im Exchange Admin Center die Option **Nachrichtenfluss**  >  **Regeln** aus.</span><span class="sxs-lookup"><span data-stu-id="4eee3-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="4eee3-130">Wählen Sie **+** **Hinzufügen** aus, und wählen Sie dann **Office 365-Nachrichtenverschlüsselung und-Rechte Schutz auf Nachrichten anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="4eee3-130">Select **+** **Add** , and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="4eee3-131">Geben Sie einen Namen für die neue Nachrichtenfluss Regel ein, und wählen Sie dann unter **diese Regel anwenden, wenn** die **Nachrichteneigenschaften**  >  **den Nachrichtentyp**  >  **Voicemail** enthalten aus.</span><span class="sxs-lookup"><span data-stu-id="4eee3-131">Provide a name for the new mail flow rule and then under **Apply this rule if** , select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="4eee3-132">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="4eee3-132">Select **OK**.</span></span>
6. <span data-ttu-id="4eee3-133">Wählen Sie unter **Folgendes ausführen die** Option **Office 365-Nachrichtenverschlüsselung und-Rechte Schutz auf die Nachricht anwenden** aus, und wählen Sie dann **auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="4eee3-133">Under **Do the following** , select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="4eee3-134">Wählen Sie unter **RMS-Vorlage** die Option **nicht weiterleiten** aus.</span><span class="sxs-lookup"><span data-stu-id="4eee3-134">Under **RMS template** , select **Do not forward**.</span></span> <span data-ttu-id="4eee3-135">Klicken Sie auf **OK** und dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4eee3-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4eee3-136">Wenn die Liste der **RMS-Vorlagen** leer ist, müssen Sie die Nachrichtenverschlüsselung einrichten.</span><span class="sxs-lookup"><span data-stu-id="4eee3-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="4eee3-137">Weitere Informationen zum Einrichten der Nachrichtenverschlüsselung finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="4eee3-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="4eee3-138">Einrichten neuer Nachrichten Verschlüsselungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="4eee3-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="4eee3-139">Konfigurieren und Verwalten von Vorlagen für Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="4eee3-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="4eee3-140">Option "nicht weiterleiten" für e-Mails</span><span class="sxs-lookup"><span data-stu-id="4eee3-140">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="4eee3-141">Einrichten von Voicemailrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="4eee3-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="4eee3-142">Bei Skype for Business-Kunden kann das Deaktivieren von Voicemail über eine Microsoft Teams-Anrufrichtlinie auch den Voicemaildienst für Ihre Skype for Business-Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4eee3-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="4eee3-143">Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) und [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) steuern.</span><span class="sxs-lookup"><span data-stu-id="4eee3-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="4eee3-144">Voicemail-Nachrichten, die von Benutzern in Ihrer Organisation empfangen werden, werden in der Region transkribiert, in der Ihre Microsoft 365-oder Office 365-Organisation gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="4eee3-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="4eee3-145">Der Bereich, in dem der Mandant gehostet wird, ist möglicherweise nicht derselbe Bereich, in dem sich der Benutzer befindet, der die Sprachnachricht empfängt.</span><span class="sxs-lookup"><span data-stu-id="4eee3-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="4eee3-146">Um die Region anzuzeigen, in der Ihr Mandant gehostet wird, wechseln Sie zur Seite [Organisationsprofil](https://go.microsoft.com/fwlink/p/?linkid=2067339) , und klicken Sie dann neben **Datenspeicherort** auf **Details anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="4eee3-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4eee3-147">Mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** können Sie keine neue Richtlinieninstanz für Transkriptions-und Transkriptions Obszönitäten erstellen, und Sie können eine vorhandene Richtlinieninstanz nicht mithilfe des Cmdlets **Remove-CsOnlineVoiceMailPolicy** entfernen.</span><span class="sxs-lookup"><span data-stu-id="4eee3-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="4eee3-148">Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten.</span><span class="sxs-lookup"><span data-stu-id="4eee3-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="4eee3-149">Um alle verfügbaren Voicemail-Richtlinieninstanzen anzuzeigen, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) verwenden.</span><span class="sxs-lookup"><span data-stu-id="4eee3-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="4eee3-150">**PS C: \\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="4eee3-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy Ergebnisfenster.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="4eee3-152">Deaktivieren der Aufzeichnung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4eee3-152">Turning off transcription for your organization</span></span>

<span data-ttu-id="4eee3-p110">Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) deaktivieren. Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4eee3-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="4eee3-155">Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4eee3-155">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="4eee3-156">Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4eee3-156">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="4eee3-157">Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4eee3-157">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="4eee3-158">Führen Sie dazu die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4eee3-158">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="4eee3-159">Aufzeichnung für einen Benutzer deaktivieren</span><span class="sxs-lookup"><span data-stu-id="4eee3-159">Turning off transcription for a user</span></span>

<span data-ttu-id="4eee3-160">Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4eee3-160">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="4eee3-161">Wenn beispielsweise die Voicemail-Transkription für alle Benutzer aktiviert ist, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) eine Richtlinie zum Deaktivieren der Transkription für einen bestimmten Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4eee3-161">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="4eee3-162">Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:</span><span class="sxs-lookup"><span data-stu-id="4eee3-162">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="4eee3-163">Profanitäts-Maskierung während der Transkription für einen Benutzer aktivieren</span><span class="sxs-lookup"><span data-stu-id="4eee3-163">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="4eee3-164">Um die Profanität-Maskierung während der Transkription für einen bestimmten Benutzer zu aktivieren, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) der Profanität-Maskierung während der Transkription eine Gruppenrichtlinie für die Aktivierung für einen bestimmten Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4eee3-164">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="4eee3-165">Um die Profanitäts-Maskierung während der Transkription für einen einzelnen Benutzer zu aktivieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="4eee3-165">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="4eee3-166">Der Voicemaildienst in Microsoft 365 und Office 365 speichert Voicemail-Richtlinien zwischen und aktualisiert den Cache alle 4 Stunden.</span><span class="sxs-lookup"><span data-stu-id="4eee3-166">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="4eee3-167">Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4eee3-167">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="4eee3-168">Unterstützen der Benutzer bei der Sprachnachrichten Funktion von Teams</span><span class="sxs-lookup"><span data-stu-id="4eee3-168">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="4eee3-169">Wir haben die folgenden Informationen für Ihre Benutzer bei der Verwaltung Ihrer Voicemail-Einstellungen sowie anderer Anruffunktionen in Teams:</span><span class="sxs-lookup"><span data-stu-id="4eee3-169">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="4eee3-170">[Verwalten Sie Ihre Anrufeinstellungen in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="4eee3-170">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="4eee3-171">In diesem Artikel wird erläutert, wie alle Anruffeatures für Endbenutzer Teams verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4eee3-171">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="4eee3-172">Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="4eee3-172">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="4eee3-p115">Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:</span><span class="sxs-lookup"><span data-stu-id="4eee3-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="4eee3-175">[Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.</span><span class="sxs-lookup"><span data-stu-id="4eee3-175">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="4eee3-176">Skype for Business 2016-Schulung</span><span class="sxs-lookup"><span data-stu-id="4eee3-176">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="4eee3-177">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4eee3-177">Related topics</span></span>
[<span data-ttu-id="4eee3-178">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4eee3-178">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="4eee3-179">Das Telefonsystem bietet Ihnen Folgendes</span><span class="sxs-lookup"><span data-stu-id="4eee3-179">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="4eee3-180">Planen der Migration von Skype for Business Server und Exchange Server</span><span class="sxs-lookup"><span data-stu-id="4eee3-180">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
