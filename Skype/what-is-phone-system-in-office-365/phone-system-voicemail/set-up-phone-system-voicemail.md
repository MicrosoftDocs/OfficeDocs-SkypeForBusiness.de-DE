---
title: Einrichten von Voicemail Telefonsystem
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 7d4ad9fa310ee8b90b813bfe949401c602c6a2f2
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="8cf54-103">Einrichten von Voicemail Telefonsystem</span><span class="sxs-lookup"><span data-stu-id="8cf54-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="8cf54-104">Dieser Artikel ist für die [Office 365-Admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , möchte das Telefonsystem Voicemail-Feature für alle Benutzer im Unternehmen eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="8cf54-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8cf54-p101">Voicemail für Telefonsysteme unterstützt die Ablage von Voicemailnachrichten nur in Exchange-Postfächern. E-Mail-Systeme von Drittanbietern werden nicht unterstützt. Als Ausweichmechanismus kann Voicemail für Telefonsysteme Nachrichten über SMTP erneut senden. Das bedeutet, dass Benutzer mit einem Postfach in einem E-Mail-System eines Drittanbieters ihre Voicemailnachrichten ohne garantierte Dienstbetriebszeit oder andere Voicemailfunktionen (beispielsweise Ändern ihrer Begrüßung und anderer Einstellungen) erhalten.</span><span class="sxs-lookup"><span data-stu-id="8cf54-p101">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="8cf54-107">Reine Cloudumgebungen: Einrichten von Voicemail für Telefonsysteme</span><span class="sxs-lookup"><span data-stu-id="8cf54-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="8cf54-108">Für Benutzer von Skype for Business Online und Anrufplänen wird Voicemail für Telefonsysteme automatisch eingerichtet und für Benutzer bereitgestellt, nachdem Sie den Benutzern eine **Telefonsystemlizenz** und eine Telefonnummer zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="8cf54-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="8cf54-109">Wenn das Telefonsystem Feature nicht in Ihren Plan steht, müssen Sie möglicherweise **Telefonsystem** Add-on-Lizenzen erwerben.</span><span class="sxs-lookup"><span data-stu-id="8cf54-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="8cf54-110">Sie müssen auch eine Exchange Online-Lizenz erwerben.</span><span class="sxs-lookup"><span data-stu-id="8cf54-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="8cf54-111">Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="8cf54-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="8cf54-p103">[Zuweisen oder Entfernen von Lizenzen für Office 365 Business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) und die Exchange Online-Lizenzen den jeweiligen Personen in Ihrem Unternehmen zu. Anschließend können sie Voicemailnachrichten empfangen.</span><span class="sxs-lookup"><span data-stu-id="8cf54-p103">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business. After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="8cf54-p104">Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="8cf54-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="8cf54-116">Telefonsystem in lokalen Umgebungen</span><span class="sxs-lookup"><span data-stu-id="8cf54-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="8cf54-117">Den folgenden Informationen können Sie entnehmen, wie Sie Voicemail für Telefonsysteme für die Verwendung in lokalen Umgebungen mit Anrufplänen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8cf54-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="8cf54-118">Wenn das Telefonsystem Feature nicht in Ihren Plan steht, müssen Sie möglicherweise **Telefonsystem** Add-on-Lizenzen erwerben.</span><span class="sxs-lookup"><span data-stu-id="8cf54-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="8cf54-119">Sie müssen auch eine Exchange Online-Lizenz erwerben.</span><span class="sxs-lookup"><span data-stu-id="8cf54-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="8cf54-120">Finden Sie unter [Skype für Geschäfts- und Microsoft-Teams, Add-On-Lizenzierung](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="8cf54-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="8cf54-121">[Zuweisen oder Entfernen von Lizenzen für Office 365 Business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), die [Zuweisen von Skype for Business- und Microsoft Teams-Lizenzen](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) und die Exchange Online-Lizenzen den jeweiligen Personen in Ihrem Unternehmen zu.</span><span class="sxs-lookup"><span data-stu-id="8cf54-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="8cf54-122">Befolgen Sie die Anweisungen im Abschnitt **Aktivieren von Benutzern für Telefonsystem Sprach- und Voice Mail-Dienste** von der [Skype für Business Cloud Connector Edition Handbuch konfigurieren](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="8cf54-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="8cf54-p106">Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="8cf54-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="8cf54-125">Unter [Unterstützung für Azure-PBX-Voicemail für Exchange Server](https://support.microsoft.com/en-us/kb/3195158) können Sie nachlesen, wie Sie die Übermittlung von Azure-Voicemailnachrichten für Telefonsystembenutzer mit lokalen Postfächern konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8cf54-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="8cf54-126">Einrichten von Voicemailrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="8cf54-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="8cf54-127">Voicemail Lautschrift ist standardmäßig für alle Organisationen und Benutzer aktiviert. jedoch können Sie diese mithilfe des Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) und [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) steuern.</span><span class="sxs-lookup"><span data-stu-id="8cf54-127">Voicemail transcription is enabled by default for all organizations and users; however, you can control it by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8cf54-128">Sie können mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** keine neue Richtlinieninstanz für Transkription erstellen, und Sie können mit dem Cmdlet **Remove-CsOnlineVoiceMailPolicy** keine vorhandene Richtlinieninstanz entfernen.</span><span class="sxs-lookup"><span data-stu-id="8cf54-128">You can't create a new policy instance for transcription using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="8cf54-129">Sie können die Lautschrift-Einstellungen für Ihren Benutzern mit Voicemail-Richtlinien verwalten.</span><span class="sxs-lookup"><span data-stu-id="8cf54-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="8cf54-130">Um alle verfügbaren Voicemail-Richtlinieninstanzen angezeigt wird, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx) verwenden.</span><span class="sxs-lookup"><span data-stu-id="8cf54-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/en-us/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="8cf54-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="8cf54-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="8cf54-133">Deaktivieren der Aufzeichnung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="8cf54-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="8cf54-p108">Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) deaktivieren. Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="8cf54-p108">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="8cf54-136">Aufzeichnung für einen Benutzer deaktivieren</span><span class="sxs-lookup"><span data-stu-id="8cf54-136">Turning off transcription for a user</span></span>

<span data-ttu-id="8cf54-p109">Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet. Wenn Voicemailtranskription beispielsweise für alle Benutzer aktiviert ist, können Sie mit dem Cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) eine Richtlinie zuweisen, um die Transkription für einen bestimmten Benutzer zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8cf54-p109">User policies are evaluated before the organizational default settings. For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="8cf54-139">Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:</span><span class="sxs-lookup"><span data-stu-id="8cf54-139">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="8cf54-p110">Der Voicemaildienst in Office 365 cacht Voicemailrichtlinien und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="8cf54-p110">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="8cf54-142">Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8cf54-142">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="8cf54-p111">Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:</span><span class="sxs-lookup"><span data-stu-id="8cf54-p111">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>
  
- <span data-ttu-id="8cf54-145">[Prüfen von Skype for Business-Voicemail und -Optionen](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.</span><span class="sxs-lookup"><span data-stu-id="8cf54-145">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="8cf54-146">Skype for Business 2016-Schulung</span><span class="sxs-lookup"><span data-stu-id="8cf54-146">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="8cf54-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8cf54-147">Related topics</span></span>
[<span data-ttu-id="8cf54-148">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8cf54-148">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="8cf54-149">Hier ist das Ergebnis in das Telefonsystem in Office 365</span><span class="sxs-lookup"><span data-stu-id="8cf54-149">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)
