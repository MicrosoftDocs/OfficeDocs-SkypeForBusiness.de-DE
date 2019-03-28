---
title: Einrichten von Cloud-Voicemail
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: 8219934b8e95962f0e9ea81f4965ad9e5c55fb34
ms.sourcegitcommit: 5b33cfc828906917f76b0d2a9ae402c9336388a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30934772"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="a299c-103">Einrichten von Cloud-Voicemail</span><span class="sxs-lookup"><span data-stu-id="a299c-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="a299c-104">Dieser Artikel ist für die [Office 365-Admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , möchte das Cloud-Voicemail-Feature für alle Benutzer im Unternehmen eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="a299c-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="a299c-105">Cloud Voicemail unterstützt Voicemailnachrichten Hinterlegung nur in einem Exchange-Postfach und Drittanbieter-e-Mail-Systemen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a299c-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> <span data-ttu-id="a299c-106">Als ein Sicherungsmechanismus Cloud Voicemail-Nachrichten mithilfe von SMTP, d. h., Benutzer mit einem Postfach auf einem Drittanbieter-e-Mail-System erhalten ihre Voicemail-Nachrichten mit keine zuverlässiger Dienst Betriebszeit oder andere Voicemail-Features, beispielsweise ändern senden können ihre Ansagen und andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a299c-106">As a fallback mechanism, Cloud Voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="a299c-107">Nur-Cloud-Umgebungen: Einrichten von Cloud-Voicemail</span><span class="sxs-lookup"><span data-stu-id="a299c-107">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="a299c-108">Cloud-Voicemail wird für Skype für Benutzer Online Business und plant aufrufen einrichten und für Benutzer bereitgestellt werden, nachdem Sie ihnen eine Lizenz **Telefonsystem** und eine Telefonnummer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a299c-108">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="a299c-109">Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen.</span><span class="sxs-lookup"><span data-stu-id="a299c-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="a299c-110">Sie müssen möglicherweise auch eine Exchange Online-Lizenz kaufen.</span><span class="sxs-lookup"><span data-stu-id="a299c-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="a299c-111">Finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a299c-111">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="a299c-112">[Zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md)und die Exchange Online Lizenzen an die Personen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="a299c-112">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="a299c-113">After you do that, they will be able to receive voicemail messages!</span><span class="sxs-lookup"><span data-stu-id="a299c-113">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="a299c-p104">Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="a299c-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="a299c-116">Telefonsystem in lokalen Umgebungen</span><span class="sxs-lookup"><span data-stu-id="a299c-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="a299c-117">Die folgenden Informationen sind zum Konfigurieren von Cloud-Voicemail lokale aufrufen planen Umgebungen entwickelt.</span><span class="sxs-lookup"><span data-stu-id="a299c-117">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="a299c-118">Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen.</span><span class="sxs-lookup"><span data-stu-id="a299c-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="a299c-119">Sie müssen auch eine Exchange Online-Lizenz kaufen.</span><span class="sxs-lookup"><span data-stu-id="a299c-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="a299c-120">Finden Sie unter [Microsoft-Teams, Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="a299c-120">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="a299c-121">[Zuweisen oder Entfernen von Lizenzen für Office 365 für Unternehmen](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Microsoft-Teams, Zuweisen von Lizenzen](assign-teams-licenses.md)und die Exchange Online Lizenzen an die Personen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="a299c-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="a299c-122">Befolgen Sie die Anweisungen im Abschnitt **Aktivieren von Benutzern für Telefonsystem Sprach- und Voicemail-Dienste** von der [Skype für Business Cloud Connector Edition Handbuch konfigurieren](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="a299c-122">Follow the instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span>

4. <span data-ttu-id="a299c-p106">Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="a299c-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="a299c-125">Unter [Unterstützung für Azure-PBX-Voicemail für Exchange Server](https://support.microsoft.com/kb/3195158) können Sie nachlesen, wie Sie die Übermittlung von Azure-Voicemailnachrichten für Telefonsystembenutzer mit lokalen Postfächern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a299c-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>

6. <span data-ttu-id="a299c-126">Wenden Sie sich auch lesen und befolgen Sie die Schritte im folgenden Dokument: [Hybrid-Konfigurations-Assistenten](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span><span class="sxs-lookup"><span data-stu-id="a299c-126">Please also read and follow the steps outlined in the following document: [Hybrid Configuration wizard](https://docs.microsoft.com/exchange/hybrid-configuration-wizard)</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="a299c-127">Einrichten von Voicemailrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a299c-127">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="a299c-128">Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) und [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) steuern.</span><span class="sxs-lookup"><span data-stu-id="a299c-128">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a299c-129">Sie können eine neue Richtlinieninstanz für Umsetzung und Lautschrift Gotteslästerung maskieren mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** erstellen, und eine vorhandene Richtlinieninstanz mithilfe des Cmdlets **Remove-CsOnlineVoiceMailPolicy** kann nicht entfernt werden .</span><span class="sxs-lookup"><span data-stu-id="a299c-129">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="a299c-130">Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten.</span><span class="sxs-lookup"><span data-stu-id="a299c-130">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="a299c-131">Um alle verfügbaren Voicemail-Richtlinieninstanzen angezeigt wird, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a299c-131">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="a299c-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="a299c-132">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy Ergebnisfenster.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="a299c-134">Deaktivieren der Aufzeichnung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="a299c-134">Turning off transcription for your organization</span></span>

<span data-ttu-id="a299c-p108">Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) deaktivieren. Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a299c-p108">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="a299c-137">Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="a299c-137">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="a299c-138">Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a299c-138">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="a299c-139">Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a299c-139">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="a299c-140">Zu diesem Zweck führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a299c-140">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="a299c-141">Aufzeichnung für einen Benutzer deaktivieren</span><span class="sxs-lookup"><span data-stu-id="a299c-141">Turning off transcription for a user</span></span>

<span data-ttu-id="a299c-142">Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="a299c-142">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="a299c-143">Wenn Voicemail Lautschrift für alle Benutzer aktiviert ist, können Sie beispielsweise eine Richtlinie Lautschrift für einen bestimmten Benutzer zu deaktivieren, indem Sie mit dem Cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a299c-143">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="a299c-144">Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:</span><span class="sxs-lookup"><span data-stu-id="a299c-144">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="a299c-145">Profanitäts-Maskierung während der Transkription für einen Benutzer aktivieren</span><span class="sxs-lookup"><span data-stu-id="a299c-145">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="a299c-146">Um die Profanität-Maskierung während der Transkription für einen bestimmten Benutzer zu aktivieren, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) der Profanität-Maskierung während der Transkription eine Gruppenrichtlinie für die Aktivierung für einen bestimmten Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a299c-146">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="a299c-147">Um die Profanitäts-Maskierung während der Transkription für einen einzelnen Benutzer zu aktivieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="a299c-147">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="a299c-p111">Der Voicemaildienst in Office 365 cacht Voicemailrichtlinien und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a299c-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="a299c-150">Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a299c-150">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="a299c-p112">Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:</span><span class="sxs-lookup"><span data-stu-id="a299c-p112">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="a299c-153">[Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.</span><span class="sxs-lookup"><span data-stu-id="a299c-153">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="a299c-154">Skype for Business 2016-Schulung</span><span class="sxs-lookup"><span data-stu-id="a299c-154">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="a299c-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a299c-155">Related topics</span></span>
[<span data-ttu-id="a299c-156">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="a299c-156">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="a299c-157">Das bekommen Sie mit Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="a299c-157">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)


