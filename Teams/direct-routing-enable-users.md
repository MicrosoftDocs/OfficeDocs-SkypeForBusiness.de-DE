---
title: Aktivieren von Benutzern für das direkte Routing
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie Benutzern das direkte Routing von Microsoft Phone-Systemen ermöglichen.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655482"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="6ddaf-103">Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail</span><span class="sxs-lookup"><span data-stu-id="6ddaf-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="6ddaf-104">In diesem Artikel wird beschrieben, wie Benutzer für das direkte Routing von Telefonsystemen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="6ddaf-105">Schritt 2 der folgenden Schritte zum Konfigurieren des direkten Routings:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="6ddaf-106">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-106">Step 1.</span></span> [<span data-ttu-id="6ddaf-107">Verbinden des SBC mit dem Microsoft Phone-System und Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="6ddaf-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="6ddaf-108">**Schritt 2. Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail**   (dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="6ddaf-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="6ddaf-109">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-109">Step 3.</span></span> [<span data-ttu-id="6ddaf-110">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="6ddaf-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="6ddaf-111">Schritt 4:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-111">Step 4.</span></span> [<span data-ttu-id="6ddaf-112">Übersetzen von Zahlen in ein anderes Format</span><span class="sxs-lookup"><span data-stu-id="6ddaf-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="6ddaf-113">Informationen zu allen Schritten, die für das Einrichten des direkten Routings erforderlich sind, finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="6ddaf-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="6ddaf-114">Wenn Sie bereit sind, Benutzer für die direkte Weiterleitung zu aktivieren, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="6ddaf-115">Erstellen Sie einen Benutzer in Microsoft 365 oder Office 365, und weisen Sie eine Telefon System Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="6ddaf-116">Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="6ddaf-117">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="6ddaf-118">Weisen Sie den Benutzern nur den Modus "nur Teams" zu.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="6ddaf-119">Erstellen eines Benutzers und Zuweisen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="6ddaf-119">Create a user and assign the license</span></span> 

<span data-ttu-id="6ddaf-120">Es gibt zwei Möglichkeiten zum Erstellen eines neuen Benutzers in Microsoft 365 oder Office 365.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="6ddaf-121">Microsoft empfiehlt allerdings, dass Ihre Organisation eine Option zum Vermeiden von Routingproblemen wählt:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="6ddaf-122">Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie ihn mit der Cloud.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="6ddaf-123">Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="6ddaf-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="6ddaf-124">Erstellen Sie den Benutzer direkt im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="6ddaf-125">Weitere Informationen finden Sie unter [Hinzufügen von Benutzern einzeln oder in Massen zu Microsoft 365 oder Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="6ddaf-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="6ddaf-126">Wenn Ihre Skype for Business Online-Bereitstellung mit Skype for Business 2015 oder lync 2010 oder 2013 lokal koexistiert, besteht die einzige unterstützte Option darin, den Benutzer im lokalen Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1).</span><span class="sxs-lookup"><span data-stu-id="6ddaf-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="6ddaf-127">Informationen zu den Lizenzanforderungen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements) in [Planen des direkten Routings](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="6ddaf-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="6ddaf-128">Stellen Sie sicher, dass der Benutzer online ist und die Telefonnummer nicht von lokal synchronisiert wird (anwendbar für Skype for Business Server Enterprise-sprachaktivierte Benutzer, die in Teams Direct Routing migriert werden).</span><span class="sxs-lookup"><span data-stu-id="6ddaf-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="6ddaf-129">Für die direkte Weiterleitung muss der Benutzer online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="6ddaf-130">Sie können überprüfen, indem Sie den RegistrarPool-Parameter sehen, der einen Wert in der Infra.lync.com-Domäne aufweisen muss.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="6ddaf-131">Der OnPremLineUriManuallySet-Parameter sollte ebenfalls auf true festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="6ddaf-132">Dies wird erreicht, indem die Telefonnummer konfiguriert und Enterprise-VoIP und Voicemail mithilfe von Skype for Business Online PowerShell aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="6ddaf-133">Verbinden Sie eine Skype for Business Online PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="6ddaf-134">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="6ddaf-135">Wenn OnPremLineUriManuallySet auf "false" festgelegt ist und LineUri mit einer <E. 164-Telefonnummer> gefüllt ist, bereinigen Sie die Parameter mithilfe der lokalen Skype for Business-Verwaltungsshell, bevor Sie die Telefonnummer mit Skype for Business Online PowerShell konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="6ddaf-136">Geben Sie in der Skype for Business-Verwaltungsshell den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="6ddaf-137">Nachdem die Änderungen mit Office 365 synchronisiert wurden, lautet die erwartete Ausgabe wie `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` folgt:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="6ddaf-138">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="6ddaf-139">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, die Telefonnummer und die Voicemail des Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="6ddaf-140">So fügen Sie die Telefonnummer hinzu und aktivieren für Voicemail:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="6ddaf-141">Verbinden Sie eine Skype for Business Online PowerShell-Sitzung.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="6ddaf-142">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="6ddaf-143">Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="6ddaf-144">Wenn die Benutzer "Spencer Low" und "Stacy Quinn" dieselbe Basisnummer mit eindeutigen Erweiterungen verwenden, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="6ddaf-145">Es wird empfohlen, aber nicht erforderlich, dass die verwendete Telefonnummer als vollständige E. 164-Telefonnummer mit Landesvorwahl konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="6ddaf-146">Es wird unterstützt, Telefonnummern mit Erweiterungen zu konfigurieren, die verwendet werden, um Benutzer zu lookupen, wenn der Verweis auf die Basisnummer mehr als ein Ergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="6ddaf-147">So können Unternehmen Telefonnummern mit der gleichen Basisnummer und eindeutigen Erweiterungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="6ddaf-148">Damit Lookup erfolgreich ist, muss die Einladung die vollständige Nummer mit der Erweiterung wie folgt aufweisen:</span><span class="sxs-lookup"><span data-stu-id="6ddaf-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="6ddaf-149">Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business-Verwaltungsshell oder die Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="6ddaf-150">Konfigurieren des direkten Sendens von Anrufen an Voicemail</span><span class="sxs-lookup"><span data-stu-id="6ddaf-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="6ddaf-151">Mit der direkten Weiterleitung können Sie den Anruf an einen Benutzer beenden und ihn direkt an die Voicemail des Benutzers senden.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="6ddaf-152">Wenn Sie den Anruf direkt an Voicemail senden möchten, fügen Sie Opaque = App: Voicemail an den URI-Header der Anforderung an.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="6ddaf-153">Beispielsweise "SIP: User@yourdomain. com; Opaque = App: Voicemail".</span><span class="sxs-lookup"><span data-stu-id="6ddaf-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="6ddaf-154">In diesem Fall erhält der Benutzer des Teams keine Anrufbenachrichtigung, der Anruf wird direkt mit der Voicemail des Benutzers verbunden.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="6ddaf-155">Zuweisen des Modus "nur Teams" für Benutzer, um sicherzustellen, dass Anrufe in Microsoft Teams landen</span><span class="sxs-lookup"><span data-stu-id="6ddaf-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="6ddaf-156">Das direkte Routing setzt voraus, dass Benutzer nur im Modus "Teams" angemeldet sind, um sicherzustellen, dass eingehende Anrufe im Team-Client landen.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="6ddaf-157">Um Benutzer nur im Modus "Teams" zu platzieren, weisen Sie Ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="6ddaf-158">Weitere Informationen finden Sie unter [Upgrade-Anleitung für IT-Administratoren](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="6ddaf-158">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="6ddaf-159">Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel, um Informationen zur Interoperabilität zwischen Skype und Teams zu erhalten: [Migration und Interoperabilität mit Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="6ddaf-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ddaf-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6ddaf-160">See also</span></span>

[<span data-ttu-id="6ddaf-161">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="6ddaf-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="6ddaf-162">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="6ddaf-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
