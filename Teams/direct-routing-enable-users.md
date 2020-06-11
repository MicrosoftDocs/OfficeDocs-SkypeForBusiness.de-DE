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
ms.openlocfilehash: 2ae485398cef1cef2444de07dcabc4bf3f949ad5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691371"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="e84a1-103">Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail</span><span class="sxs-lookup"><span data-stu-id="e84a1-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="e84a1-104">In diesem Artikel wird beschrieben, wie Benutzer für das direkte Routing von Telefonsystemen aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e84a1-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="e84a1-105">Schritt 2 der folgenden Schritte zum Konfigurieren des direkten Routings:</span><span class="sxs-lookup"><span data-stu-id="e84a1-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="e84a1-106">Schritt 1:</span><span class="sxs-lookup"><span data-stu-id="e84a1-106">Step 1.</span></span> [<span data-ttu-id="e84a1-107">Verbinden des SBC mit dem Microsoft Phone-System und Überprüfen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="e84a1-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="e84a1-108">**Schritt 2. Aktivieren von Benutzern für Direct Routing, Voicemail und Voicemail** (dieser Artikel)</span><span class="sxs-lookup"><span data-stu-id="e84a1-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**    (This article)</span></span>
- <span data-ttu-id="e84a1-109">Schritt 3:</span><span class="sxs-lookup"><span data-stu-id="e84a1-109">Step 3.</span></span> [<span data-ttu-id="e84a1-110">Konfigurieren des VoIP-Routings</span><span class="sxs-lookup"><span data-stu-id="e84a1-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="e84a1-111">Schritt 4:</span><span class="sxs-lookup"><span data-stu-id="e84a1-111">Step 4.</span></span> [<span data-ttu-id="e84a1-112">Übersetzen von Zahlen in ein anderes Format</span><span class="sxs-lookup"><span data-stu-id="e84a1-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="e84a1-113">Informationen zu allen Schritten, die für das Einrichten des direkten Routings erforderlich sind, finden Sie unter [Konfigurieren des direkten Routings](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="e84a1-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="e84a1-114">Wenn Sie bereit sind, Benutzer für die direkte Weiterleitung zu aktivieren, führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e84a1-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="e84a1-115">Erstellen Sie einen Benutzer in Microsoft 365 oder Office 365, und weisen Sie eine Telefon System Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="e84a1-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="e84a1-116">Stellen Sie sicher, dass der Benutzer in Skype for Business Online verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="e84a1-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="e84a1-117">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="e84a1-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="e84a1-118">Weisen Sie den Benutzern nur den Modus "nur Teams" zu.</span><span class="sxs-lookup"><span data-stu-id="e84a1-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="e84a1-119">Erstellen eines Benutzers und Zuweisen der Lizenz</span><span class="sxs-lookup"><span data-stu-id="e84a1-119">Create a user and assign the license</span></span> 

<span data-ttu-id="e84a1-120">Es gibt zwei Möglichkeiten zum Erstellen eines neuen Benutzers in Microsoft 365 oder Office 365.</span><span class="sxs-lookup"><span data-stu-id="e84a1-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="e84a1-121">Microsoft empfiehlt allerdings, dass Ihre Organisation eine Option zum Vermeiden von Routingproblemen wählt:</span><span class="sxs-lookup"><span data-stu-id="e84a1-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="e84a1-122">Erstellen Sie den Benutzer im lokalen Active Directory, und synchronisieren Sie ihn mit der Cloud.</span><span class="sxs-lookup"><span data-stu-id="e84a1-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="e84a1-123">Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Verzeichnisse in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="e84a1-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="e84a1-124">Erstellen Sie den Benutzer direkt im Microsoft 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="e84a1-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e84a1-125">Weitere Informationen finden Sie unter [Hinzufügen von Benutzern einzeln oder in Massen zu Microsoft 365 oder Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span><span class="sxs-lookup"><span data-stu-id="e84a1-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="e84a1-126">Wenn Ihre Skype for Business Online-Bereitstellung mit Skype for Business 2015 oder lync 2010 oder 2013 lokal koexistiert, besteht die einzige unterstützte Option darin, den Benutzer im lokalen Active Directory zu erstellen und den Benutzer mit der Cloud zu synchronisieren (Option 1).</span><span class="sxs-lookup"><span data-stu-id="e84a1-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="e84a1-127">Informationen zu den Lizenzanforderungen finden Sie unter [Lizenzierung und andere Anforderungen](direct-routing-plan.md#licensing-and-other-requirements) in [Planen des direkten Routings](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="e84a1-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a><span data-ttu-id="e84a1-128">Sicherstellen, dass der Benutzer in Skype for Business Online verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="e84a1-128">Ensure that the user is homed in Skype for Business Online</span></span> 

<span data-ttu-id="e84a1-129">Für die direkte Weiterleitung muss der Benutzer in Skype for Business Online verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e84a1-129">Direct Routing requires the user to be homed in Skype for Business Online.</span></span> <span data-ttu-id="e84a1-130">Sie können überprüfen, indem Sie den RegistrarPool-Parameter sehen, der einen Wert in der Infra.lync.com-Domäne aufweisen muss.</span><span class="sxs-lookup"><span data-stu-id="e84a1-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span>

1. <span data-ttu-id="e84a1-131">Herstellen einer Verbindung mit der Remote-PowerShell</span><span class="sxs-lookup"><span data-stu-id="e84a1-131">Connect to remote PowerShell.</span></span>
2. <span data-ttu-id="e84a1-132">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e84a1-132">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="e84a1-133">Konfigurieren Sie die Telefonnummer, und aktivieren Sie Enterprise-VoIP und Voicemail.</span><span class="sxs-lookup"><span data-stu-id="e84a1-133">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="e84a1-134">Nachdem Sie den Benutzer erstellt und eine Lizenz zugewiesen haben, besteht der nächste Schritt darin, die Telefonnummer und die Voicemail des Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e84a1-134">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="e84a1-135">So fügen Sie die Telefonnummer hinzu und aktivieren für Voicemail:</span><span class="sxs-lookup"><span data-stu-id="e84a1-135">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="e84a1-136">Stellen Sie eine Verbindung mit einer PowerShell-Remotesitzung her.</span><span class="sxs-lookup"><span data-stu-id="e84a1-136">Connect to a remote PowerShell session.</span></span> 
2. <span data-ttu-id="e84a1-137">Geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="e84a1-137">Enter the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

    <span data-ttu-id="e84a1-138">Wenn Sie beispielsweise eine Telefonnummer für den Benutzer "Spencer Low" hinzufügen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e84a1-138">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="e84a1-139">Die verwendete Telefonnummer muss als vollständige E. 164-Telefonnummer mit Landesvorwahl konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e84a1-139">The phone number used has to be configured as a full E.164 phone number with country code.</span></span> 

      > [!NOTE]
      > <span data-ttu-id="e84a1-140">Wenn die Telefonnummer des Benutzers lokal verwaltet wird, verwenden Sie die lokale Skype for Business-Verwaltungsshell oder die Systemsteuerung, um die Telefonnummer des Benutzers zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e84a1-140">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="e84a1-141">Konfigurieren des direkten Sendens von Anrufen an Voicemail</span><span class="sxs-lookup"><span data-stu-id="e84a1-141">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="e84a1-142">Mit der direkten Weiterleitung können Sie den Anruf an einen Benutzer beenden und ihn direkt an die Voicemail des Benutzers senden.</span><span class="sxs-lookup"><span data-stu-id="e84a1-142">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="e84a1-143">Wenn Sie den Anruf direkt an Voicemail senden möchten, fügen Sie Opaque = App: Voicemail an den URI-Header der Anforderung an.</span><span class="sxs-lookup"><span data-stu-id="e84a1-143">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="e84a1-144">Beispielsweise "SIP: User@yourdomain. com; Opaque = App: Voicemail".</span><span class="sxs-lookup"><span data-stu-id="e84a1-144">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="e84a1-145">In diesem Fall erhält der Benutzer des Teams keine Anrufbenachrichtigung, der Anruf wird direkt mit der Voicemail des Benutzers verbunden.</span><span class="sxs-lookup"><span data-stu-id="e84a1-145">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="e84a1-146">Zuweisen des Modus "nur Teams" für Benutzer, um sicherzustellen, dass Anrufe in Microsoft Teams landen</span><span class="sxs-lookup"><span data-stu-id="e84a1-146">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="e84a1-147">Das direkte Routing setzt voraus, dass Benutzer nur im Modus "Teams" angemeldet sind, um sicherzustellen, dass eingehende Anrufe im Team-Client landen.</span><span class="sxs-lookup"><span data-stu-id="e84a1-147">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="e84a1-148">Um Benutzer nur im Modus "Teams" zu platzieren, weisen Sie Ihnen die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu.</span><span class="sxs-lookup"><span data-stu-id="e84a1-148">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="e84a1-149">Weitere Informationen finden Sie unter [Upgrade-Anleitung für IT-Administratoren](upgrade-to-teams-on-prem-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e84a1-149">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="e84a1-150">Wenn Ihre Organisation Skype for Business Server oder Skype for Business Online verwendet, lesen Sie den folgenden Artikel, um Informationen zur Interoperabilität zwischen Skype und Teams zu erhalten: [Migration und Interoperabilität mit Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="e84a1-150">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e84a1-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e84a1-151">See also</span></span>

[<span data-ttu-id="e84a1-152">Planen von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="e84a1-152">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="e84a1-153">Konfigurieren von direktem Routing</span><span class="sxs-lookup"><span data-stu-id="e84a1-153">Configure Direct Routing</span></span>](direct-routing-configure.md)
