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
- Teams_ITAdmin_Help
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Informationen Sie zum Einrichten von Voicemail Cloud für Ihre Benutzer. '
ms.openlocfilehash: 827c52bf526ba84e4f571102354a096e2dc8e2f4
ms.sourcegitcommit: a46dad8dfc685534d81bb011f3c099c6f59ce2e0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2019
ms.locfileid: "33882869"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="e08f1-103">Einrichten von Cloudvoicemail</span><span class="sxs-lookup"><span data-stu-id="e08f1-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="e08f1-104">Dieser Artikel ist für die [Office 365-Admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , möchte das Cloud-Voicemail-Feature für alle Benutzer im Unternehmen eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="e08f1-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="e08f1-105">Cloud Voicemail unterstützt Voicemailnachrichten Hinterlegung nur in einem Exchange-Postfach und Drittanbieter-e-Mail-Systemen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e08f1-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="e08f1-106">Nur-Cloud-Umgebungen: Einrichten von Cloud-Voicemail</span><span class="sxs-lookup"><span data-stu-id="e08f1-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="e08f1-107">Cloud-Voicemail wird für Skype für Benutzer Online Business und plant aufrufen einrichten und für Benutzer bereitgestellt werden, nachdem Sie ihnen eine Lizenz **Telefonsystem** und eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="e08f1-108">Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e08f1-109">Sie müssen möglicherweise auch eine Exchange Online-Lizenz kaufen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="e08f1-110">Finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e08f1-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e08f1-111">[Zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md)und die Exchange Online Lizenzen an die Personen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="e08f1-112">Anschließend können sie Voicemailnachrichten empfangen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="e08f1-p103">Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="e08f1-115">Telefonsystem in lokalen Umgebungen</span><span class="sxs-lookup"><span data-stu-id="e08f1-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="e08f1-116">Die folgenden Informationen sind zum Konfigurieren von Cloud-Voicemail lokale aufrufen planen Umgebungen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="e08f1-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="e08f1-117">Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="e08f1-118">Sie müssen auch eine Exchange Online-Lizenz kaufen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="e08f1-119">Finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="e08f1-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="e08f1-120">[Zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md)und die Exchange Online Lizenzen an die Personen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="e08f1-121">Führen Sie die Anweisungen übereinstimmenden lokale öffentliche Telefonnetz für Ihre Benutzer bereitgestellte Lösung.</span><span class="sxs-lookup"><span data-stu-id="e08f1-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="e08f1-122">Befolgen Sie die Anweisungen im Abschnitt über das [Konfigurieren von Skype für Business Cloud Connector Edition Handbuch](https://technet.microsoft.com/library/mt605228.aspx) **Aktivieren von Benutzern für Telefonsystem Sprach- und Voicemail-Dienste** , für die Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="e08f1-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="e08f1-123">Führen Sie für PSTN durch den Aufruf von Skype für Business Server [Aktivieren Sie die Benutzer für Enterprise-VoIP lokal](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="e08f1-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="e08f1-124">Führen Sie für Teams direkten Routing im Abschnitt **Enterprise-VoIP aktivieren und konfigurieren Sie die Telefonnummer und Voicemail** [direkte](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail)Routing konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e08f1-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="e08f1-p106">Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="e08f1-127">Voicemailnachrichten werden mit Exchange-Postfach der Benutzer über SMTP über Exchange Online Protection weitergeleitet übermittelt.</span><span class="sxs-lookup"><span data-stu-id="e08f1-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="e08f1-128">Werden Sie um die erfolgreiche Übermittlung dieser Nachrichten zu aktivieren, sicher, dass die Exchange-Connectors zwischen Exchange-Servern und Exchange Online Protection korrekt konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="e08f1-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection.</span></span> <span data-ttu-id="e08f1-129">[Verwendung Connectors zu E-Mail-Fluss zu konfigurieren](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="e08f1-129">[Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

6. <span data-ttu-id="e08f1-130">Verbindung zwischen Office 365 und Exchange Server-Postfachs über Exchange-Webdienste ist erforderlich, um Voicemail-Features wie beispielsweise anpassen Ansagen und visual Voicemail in Skype für Business-Clients zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e08f1-130">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="e08f1-131">Um diese Konnektivität zu aktivieren müssen Sie konfigurieren die neue Exchange-Oauth-Authentifizierungsprotokoll beschreiben in [Konfigurieren der OAuth-Authentifizierung zwischen Exchange- und Exchange Online-Organisationen](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span><span class="sxs-lookup"><span data-stu-id="e08f1-131">To enable this connectivity you must configure the new Exchange Oauth authentication protocol describe in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)</span></span> 

> [!NOTE]
> <span data-ttu-id="e08f1-132">Die Exchange-Hybrid-Assistenten ausführen von Exchange 2013 CU5 oder höher wird automatisch die Anforderungen in die Schritte 5 und 6 behandelt.</span><span class="sxs-lookup"><span data-stu-id="e08f1-132">The Exchange Hybrid Wizard run from Exchange 2013 CU5 or greater will handle the requirements in steps 5 and 6 automatically.</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="e08f1-133">Einrichten von Voicemailrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="e08f1-133">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="e08f1-134">Für Skype für Geschäftskunden möglicherweise die Deaktivieren von Voicemail über ein Microsoft-Teams, Richtlinie Aufrufen den Voicemail-Dienst für Ihre Skype für Unternehmensbenutzer auch deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e08f1-134">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="e08f1-135">Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) und [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) steuern.</span><span class="sxs-lookup"><span data-stu-id="e08f1-135">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e08f1-136">Sie können eine neue Richtlinieninstanz für Umsetzung und Lautschrift Gotteslästerung maskieren mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** erstellen, und eine vorhandene Richtlinieninstanz mithilfe des Cmdlets **Remove-CsOnlineVoiceMailPolicy** kann nicht entfernt werden .</span><span class="sxs-lookup"><span data-stu-id="e08f1-136">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="e08f1-137">Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten.</span><span class="sxs-lookup"><span data-stu-id="e08f1-137">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="e08f1-138">Um alle verfügbaren Voicemail-Richtlinieninstanzen angezeigt wird, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e08f1-138">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="e08f1-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="e08f1-139">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy Ergebnisfenster.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="e08f1-141">Deaktivieren der Aufzeichnung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="e08f1-141">Turning off transcription for your organization</span></span>

<span data-ttu-id="e08f1-p110">Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) deaktivieren. Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e08f1-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="e08f1-144">Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="e08f1-144">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="e08f1-145">Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e08f1-145">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="e08f1-146">Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e08f1-146">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="e08f1-147">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e08f1-147">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="e08f1-148">Aufzeichnung für einen Benutzer deaktivieren</span><span class="sxs-lookup"><span data-stu-id="e08f1-148">Turning off transcription for a user</span></span>

<span data-ttu-id="e08f1-149">Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="e08f1-149">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="e08f1-150">Wenn Voicemail Lautschrift für alle Benutzer aktiviert ist, können Sie beispielsweise eine Richtlinie Lautschrift für einen bestimmten Benutzer zu deaktivieren, indem Sie mit dem Cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-150">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e08f1-151">Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:</span><span class="sxs-lookup"><span data-stu-id="e08f1-151">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="e08f1-152">Profanitäts-Maskierung während der Transkription für einen Benutzer aktivieren</span><span class="sxs-lookup"><span data-stu-id="e08f1-152">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="e08f1-153">Um die Profanität-Maskierung während der Transkription für einen bestimmten Benutzer zu aktivieren, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) der Profanität-Maskierung während der Transkription eine Gruppenrichtlinie für die Aktivierung für einen bestimmten Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-153">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="e08f1-154">Um die Profanitäts-Maskierung während der Transkription für einen einzelnen Benutzer zu aktivieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="e08f1-154">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="e08f1-p113">Der Voicemaildienst in Office 365 cacht Voicemailrichtlinien und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e08f1-p113">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="e08f1-157">Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e08f1-157">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="e08f1-p114">Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:</span><span class="sxs-lookup"><span data-stu-id="e08f1-p114">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="e08f1-160">[Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.</span><span class="sxs-lookup"><span data-stu-id="e08f1-160">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="e08f1-161">Skype for Business 2016-Schulung</span><span class="sxs-lookup"><span data-stu-id="e08f1-161">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="e08f1-162">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e08f1-162">Related topics</span></span>
[<span data-ttu-id="e08f1-163">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e08f1-163">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="e08f1-164">Das Telefonsystem in Office 365 bietet Ihnen Folgendes</span><span class="sxs-lookup"><span data-stu-id="e08f1-164">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="e08f1-165">Planen der Migration von Skype for Business Server und Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e08f1-165">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


