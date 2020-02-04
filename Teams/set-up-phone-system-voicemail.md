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
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Hier erfahren Sie, wie Sie Cloud Voicemail für Ihre Benutzer einrichten. '
ms.openlocfilehash: 1e33928c8ebd241d37f572d80eb895a0164e0d41
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693820"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="de1f2-103">Einrichten von Cloudvoicemail</span><span class="sxs-lookup"><span data-stu-id="de1f2-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="de1f2-104">Dieser Artikel richtet sich an den [Office 365-Administrator](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) , der die Cloud-Voicemail-Funktion für alle Personen im Unternehmen einrichten möchte.</span><span class="sxs-lookup"><span data-stu-id="de1f2-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="de1f2-105">Cloud Voicemail unterstützt das Hinterlegen von Voicemail-Nachrichten nur in einem Exchange-Postfach und unterstützt keine e-Mail-Systeme von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="de1f2-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="de1f2-106">Cloud-only-Umgebungen: Einrichten von Cloud-Voicemail</span><span class="sxs-lookup"><span data-stu-id="de1f2-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="de1f2-107">Bei Skype for Business Online-und Anruf Plan Benutzern wird Cloud Voicemail automatisch für Benutzer eingerichtet und bereitgestellt, nachdem Sie Ihnen eine **Telefon System** Lizenz und eine Telefonnummer zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="de1f2-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="de1f2-108">Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="de1f2-109">Sie müssen möglicherweise auch eine Exchange Online-Lizenz kaufen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="de1f2-110">Weitere Informationen finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="de1f2-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="de1f2-111">[Zuweisen oder Entfernen von Lizenzen für Office 365 for Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md)und Exchange Online-Lizenzen für die Personen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="de1f2-112">Anschließend können sie Voicemailnachrichten empfangen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="de1f2-p103">Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="de1f2-115">Telefonsystem in lokalen Umgebungen</span><span class="sxs-lookup"><span data-stu-id="de1f2-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="de1f2-116">Die folgenden Informationen bezieht sich auf die Konfiguration von Cloud Voicemail für die Arbeit mit lokalen Anruf Plan Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="de1f2-117">Wenn die Telefonsystemfunktion nicht in Ihrem Plan enthalten ist, müssen Sie möglicherweise Lizenzen für das **Telefonsystem**-Add-On kaufen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="de1f2-118">Sie müssen auch eine Exchange Online-Lizenz kaufen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="de1f2-119">Weitere Informationen finden Sie unter [Microsoft Teams-Add-on-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="de1f2-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="de1f2-120">[Zuweisen oder Entfernen von Lizenzen für Office 365 for Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [Zuweisen von Microsoft Teams-Lizenzen](assign-teams-licenses.md)und Exchange Online-Lizenzen für die Personen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-120">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="de1f2-121">Befolgen Sie die Anweisungen für die lokale PSTN-Anruf Lösung, die für Ihre Benutzer bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="de1f2-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="de1f2-122">Befolgen Sie für Cloud Connector Edition die Anweisungen im Abschnitt **Benutzer für Telefon System-sprach-und Voicemail-Dienste aktivieren** des [Skype for Business Cloud Connector Edition-Handbuchs](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="de1f2-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="de1f2-123">Für PSTN-Anrufe mit Skype for Business Server, folgen Sie [Aktivieren der Benutzer für Enterprise-VoIP lokal](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="de1f2-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="de1f2-124">Wenn Sie das direkte Routing von Teams ausführen möchten, folgen Sie dem Abschnitt konfigurieren **der Telefonnummer und Aktivieren von Enterprise-VoIP und Voicemail** unter [Konfigurieren des direkten Routings](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span><span class="sxs-lookup"><span data-stu-id="de1f2-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="de1f2-p106">Seit März 2017 ist die Unterstützung für Voicemailtranskription standardmäßig für alle Organisationen und Benutzer aktiviert. Sie können die Transkription für Ihre Organisation mithilfe von Windows PowerShell deaktivieren, indem Sie die folgenden Schritte ausführen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="de1f2-127">Voicemail-Nachrichten werden an das Exchange-Postfach der Benutzer über einen SMTP-Router über den Exchange Online-Schutz übermittelt.</span><span class="sxs-lookup"><span data-stu-id="de1f2-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="de1f2-128">Um eine erfolgreiche Zustellung dieser Nachrichten zu ermöglichen, stellen Sie sicher, dass Exchange-Connectors zwischen Ihren Exchange-Servern und dem Exchange Online-Schutz ordnungsgemäß konfiguriert sind. [Verwenden Sie Connectors zum Konfigurieren des Nachrichtenflusses](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="de1f2-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="de1f2-129">Um Voicemail-Features wie das Anpassen von Begrüßungen und visuelle Voicemail in Skype for Business-Clients zu aktivieren, ist die Konnektivität von Office 365 mit dem Exchange Server-Postfach über Exchange-Webdienste erforderlich.</span><span class="sxs-lookup"><span data-stu-id="de1f2-129">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="de1f2-130">Um diese Verbindung zu aktivieren, müssen Sie das neue Exchange OAuth-Authentifizierungsprotokoll konfigurieren, das unter [Konfigurieren der OAuth-Authentifizierung zwischen Exchange-und Exchange Online-Organisationen](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)beschrieben wird, oder den Exchange-Hybrid-Assistenten in Exchange 2013 CU5 oder höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-130">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="de1f2-131">Darüber hinaus müssen Sie die Integration und die OAuth zwischen Skype for Business Online und Exchange Server konfigurieren, die unter [Konfigurieren von Integration und OAuth zwischen Skype for Business Online und Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="de1f2-131">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="de1f2-132">Einrichten von Voicemailrichtlinien in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="de1f2-132">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="de1f2-133">Bei Skype for Business-Kunden kann das Deaktivieren von Voicemail über eine Microsoft Teams-Anrufrichtlinie auch den Voicemaildienst für Ihre Skype for Business-Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="de1f2-133">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="de1f2-134">Voicemail-Transkription ist standardmäßig aktiviert und die Profanitäts-Maskierung während der Transkription ist standardmäßig für alle Organisationen und Benutzer deaktiviert. Sie können sie jedoch mithilfe der Cmdlets [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) und [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) steuern.</span><span class="sxs-lookup"><span data-stu-id="de1f2-134">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="de1f2-135">Voicemail-Nachrichten, die von Benutzern in Ihrer Organisation empfangen werden, werden in der Region transkribiert, in der Ihr Office 365-Mandant gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="de1f2-135">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 tenant is hosted.</span></span> <span data-ttu-id="de1f2-136">Der Bereich, in dem der Mandant gehostet wird, ist möglicherweise nicht derselbe Bereich, in dem sich der Benutzer befindet, der die Sprachnachricht empfängt.</span><span class="sxs-lookup"><span data-stu-id="de1f2-136">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="de1f2-137">Um die Region anzuzeigen, in der Ihr Mandant gehostet wird, wechseln Sie zur Seite [Organisationsprofil](https://go.microsoft.com/fwlink/p/?linkid=2067339) , und klicken Sie dann neben **Datenspeicherort**auf **Details anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="de1f2-137">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="de1f2-138">Mit dem Cmdlet **New-CsOnlineVoiceMailPolicy** können Sie keine neue Richtlinieninstanz für Transkriptions-und Transkriptions Obszönitäten erstellen, und Sie können eine vorhandene Richtlinieninstanz nicht mithilfe des Cmdlets **Remove-CsOnlineVoiceMailPolicy** entfernen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-138">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="de1f2-139">Sie können die Transkriptionseinstellungen für Ihre Benutzer mit Voicemailrichtlinien verwalten.</span><span class="sxs-lookup"><span data-stu-id="de1f2-139">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="de1f2-140">Um alle verfügbaren Voicemail-Richtlinieninstanzen anzuzeigen, können Sie das Cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) verwenden.</span><span class="sxs-lookup"><span data-stu-id="de1f2-140">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="de1f2-141">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="de1f2-141">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy Ergebnisfenster.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="de1f2-143">Deaktivieren der Aufzeichnung für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="de1f2-143">Turning off transcription for your organization</span></span>

<span data-ttu-id="de1f2-p111">Die Transkription ist standardmäßig für Ihre Organisation aktiviert. Sie können sie aber mit dem Cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) deaktivieren. Führen Sie dazu Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="de1f2-p111">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="de1f2-146">Aktivieren der Profanitäts-Maskierung während der Transkription für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="de1f2-146">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="de1f2-147">Profanität-Maskierung während der Transkription ist standardmäßig für Ihre Organisation deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="de1f2-147">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="de1f2-148">Falls es eine Geschäftsanforderung ist, diese zu aktivieren, können Sie die Profanitäts-Maskierung während der Transkription mithilfe von [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="de1f2-148">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="de1f2-149">Führen Sie dazu die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="de1f2-149">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="de1f2-150">Aufzeichnung für einen Benutzer deaktivieren</span><span class="sxs-lookup"><span data-stu-id="de1f2-150">Turning off transcription for a user</span></span>

<span data-ttu-id="de1f2-151">Benutzerrichtlinien werden vor den Standardeinstellungen für die Organisation ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="de1f2-151">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="de1f2-152">Wenn beispielsweise die Voicemail-Transkription für alle Benutzer aktiviert ist, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) eine Richtlinie zum Deaktivieren der Transkription für einen bestimmten Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-152">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="de1f2-153">Führen Sie zum Deaktivieren eines einzelnen Benutzers den folgenden Dienst aus:</span><span class="sxs-lookup"><span data-stu-id="de1f2-153">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="de1f2-154">Profanitäts-Maskierung während der Transkription für einen Benutzer aktivieren</span><span class="sxs-lookup"><span data-stu-id="de1f2-154">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="de1f2-155">Um die Profanität-Maskierung während der Transkription für einen bestimmten Benutzer zu aktivieren, können Sie mithilfe des Cmdlets [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) der Profanität-Maskierung während der Transkription eine Gruppenrichtlinie für die Aktivierung für einen bestimmten Benutzer zuweisen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-155">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="de1f2-156">Um die Profanitäts-Maskierung während der Transkription für einen einzelnen Benutzer zu aktivieren, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="de1f2-156">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="de1f2-p114">Der Voicemaildienst in Office 365 cacht Voicemailrichtlinien und aktualisiert den Cache alle 4 Stunden. Es kann also bis zu 4 Stunden dauern, bis die von Ihnen vorgenommenen Richtlinienänderungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="de1f2-p114">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="de1f2-159">Unterstützen Sie Ihre Benutzer bei der Verwendung der Skype for Business-Voicemail-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="de1f2-159">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="de1f2-p115">Wir bieten Schulungsinformationen und Artikel an, damit Ihre Benutzer erfolgreich mit Skype for Business-Voicemail arbeiten können. Machen Sie Ihre Benutzer auf folgende Artikel aufmerksam:</span><span class="sxs-lookup"><span data-stu-id="de1f2-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="de1f2-162">[Prüfen von Skype for Business-Voicemail und -Optionen](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): In diesem Artikel wird erläutert, wie Sie Ihre Voicemail in Skype for Business abhören, Ihre Voicemailansage ändern und sich Ihre Voicemail in unterschiedlichen Geschwindigkeiten anhören.</span><span class="sxs-lookup"><span data-stu-id="de1f2-162">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="de1f2-163">Skype for Business 2016-Schulung</span><span class="sxs-lookup"><span data-stu-id="de1f2-163">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="de1f2-164">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="de1f2-164">Related topics</span></span>
[<span data-ttu-id="de1f2-165">Einrichten von Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="de1f2-165">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="de1f2-166">Das Telefonsystem in Office 365 bietet Ihnen Folgendes</span><span class="sxs-lookup"><span data-stu-id="de1f2-166">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="de1f2-167">Planen der Migration von Skype for Business Server und Exchange Server</span><span class="sxs-lookup"><span data-stu-id="de1f2-167">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)


