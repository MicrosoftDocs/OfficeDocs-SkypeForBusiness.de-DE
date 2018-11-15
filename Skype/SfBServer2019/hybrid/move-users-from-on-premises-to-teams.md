---
title: Verschieben von Benutzern von lokalen Teams
ms.author: crowe
author: CarolynRowe
manager: serdars--
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Zusammenfassung: Informationen Sie zum Migrieren von benutzereinstellungen und Migrieren von Benutzern zu Teams.'
ms.openlocfilehash: af0867bfdc2e12a248baf7cc07746845154d27fd
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533141"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="6c54b-103">Verschieben von Benutzern von lokalen Teams</span><span class="sxs-lookup"><span data-stu-id="6c54b-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="6c54b-104">Mit Skype für Business Server 2019 können Sie Ihre lokalen Benutzer Teams wie in diesem Artikel beschriebene migrieren.</span><span class="sxs-lookup"><span data-stu-id="6c54b-104">With Skype for Business Server 2019, you can migrate your on-premises users to Teams as described in this article.</span></span>

<span data-ttu-id="6c54b-105">Beachten Sie, nach dem Verschieben von Ihren Benutzern, Teams:</span><span class="sxs-lookup"><span data-stu-id="6c54b-105">Be aware that after moving your users to Teams:</span></span> 
 
- <span data-ttu-id="6c54b-106">Ihre Besprechungen zu Skype für Business Online migriert werden, und ihre Kontakte zu Teams migriert werden.</span><span class="sxs-lookup"><span data-stu-id="6c54b-106">Their meetings are migrated to Skype for Business Online, and their contacts are migrated to Teams.</span></span> 
- <span data-ttu-id="6c54b-107">Sie können Skype-Besprechungen über die Skype für Business-rich-Client (Benutzer werden nicht für jedes Mal Anmeldung aufgefordert) oder über die Skype Besprechungen App (erfordert eine einmalige herunter, und Anmeldung) teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-107">They can join Skype meetings through the Skype for Business rich client (users are not prompted for sign-in each time) or through the Skype Meetings App (requires a one-time download and sign-in).</span></span> <span data-ttu-id="6c54b-108">Klickt ein Benutzer auf einen Skype für Business Link zur Besprechung innerhalb von Teams, wird die Besprechung in der entsprechenden app gestartet.</span><span class="sxs-lookup"><span data-stu-id="6c54b-108">When a user clicks on a Skype for Business meeting link within Teams, the meeting will launch in the appropriate app.</span></span>

- <span data-ttu-id="6c54b-109">Unter Mobile werden Ihre Benutzer können vorhandene Skype für Business Besprechungen mit native app teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-109">On Mobile, your users will be able to join existing Skype for Business meetings using the native app only.</span></span>

> [!NOTE]
> <span data-ttu-id="6c54b-110">Nachdem ein Benutzer auf den TeamsOnly Modus verschoben wurde, wird der Benutzer in Skype für Business Online, verwaltet.</span><span class="sxs-lookup"><span data-stu-id="6c54b-110">After a user is moved to TeamsOnly mode, the user is homed in Skype for Business Online.</span></span>

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a><span data-ttu-id="6c54b-111">Erforderliche Komponenten zum Verschieben von lokalen Benutzern, Teams</span><span class="sxs-lookup"><span data-stu-id="6c54b-111">Prerequisites for moving on-premises users to Teams</span></span> 

<span data-ttu-id="6c54b-112">Dieser Abschnitt beschreibt die erforderlichen Komponenten für Ihre lokalen Benutzer Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="6c54b-112">This section describes the prerequisites for moving your on-premises users to Teams.</span></span> <span data-ttu-id="6c54b-113">Du musst:</span><span class="sxs-lookup"><span data-stu-id="6c54b-113">You must:</span></span>
- <span data-ttu-id="6c54b-114">[Einrichten von hybridkonnektivität](#set-up-hybrid-connectivity) (Wenn Sie dies nicht bereits geschehen ist)</span><span class="sxs-lookup"><span data-stu-id="6c54b-114">[Set up hybrid connectivity](#set-up-hybrid-connectivity) (if you have not already done so)</span></span>
- <span data-ttu-id="6c54b-115">[Benachrichtigen Sie die Benutzer, der die Verschiebung Teams](#notify-your-users-of-the-move-to-teams) (optional)</span><span class="sxs-lookup"><span data-stu-id="6c54b-115">[Notify your users of the move to Teams](#notify-your-users-of-the-move-to-teams) (optional)</span></span>
- [<span data-ttu-id="6c54b-116">Stellen Sie sicher, dass Ihre Benutzer eine gültige Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-116">Ensure that your users have a valid license</span></span>](#make-sure-your-users-have-a-valid-license)
- [<span data-ttu-id="6c54b-117">Beachten Sie bei Anforderungen für die VoIP-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6c54b-117">Be aware of voice configuration requirements</span></span>](#voice-configuration-requirements)
- <span data-ttu-id="6c54b-118">[Zuweisen einer Richtlinie auf Teams aktualisieren](#assign-a-teams-upgrade-policy) (optional)</span><span class="sxs-lookup"><span data-stu-id="6c54b-118">[Assign a Teams Upgrade policy](#assign-a-teams-upgrade-policy) (optional)</span></span>

## <a name="set-up-hybrid-connectivity"></a><span data-ttu-id="6c54b-119">Einrichten von hybridkonnektivität</span><span class="sxs-lookup"><span data-stu-id="6c54b-119">Set up hybrid connectivity</span></span>
<span data-ttu-id="6c54b-120">Bevor Sie Ihre Benutzer migrieren, wenn Sie nicht bereits getan haben, müssen Sie sicherstellen, dass Sie hybridkonnektivität zwischen Ihrer Skype für Business Server lokalen Umgebung und Skype für Business Online konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="6c54b-120">Before you migrate your users, if you have not already done so, you must ensure that you have configured hybrid connectivity between your Skype for Business Server on-premises environment and Skype for Business Online.</span></span> <span data-ttu-id="6c54b-121">Hybrid-Diensten ist erforderlich, Active Directory-Synchronisierung, Konfigurieren von Verbund und So weiter.</span><span class="sxs-lookup"><span data-stu-id="6c54b-121">Hybrid connectivity requires Active Directory synchronization, configuring federation, and so on.</span></span> <span data-ttu-id="6c54b-122">Weitere Informationen finden Sie unter [Planen von hybridkonnektivität](plan-hybrid-connectivity.md) und [hybridkonnektivität konfigurieren](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="6c54b-122">For more information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

## <a name="notify-your-users-of-the-move-to-teams"></a><span data-ttu-id="6c54b-123">Benachrichtigen Sie die Benutzer, der die Verschiebung Teams</span><span class="sxs-lookup"><span data-stu-id="6c54b-123">Notify your users of the move to Teams</span></span> 
<span data-ttu-id="6c54b-124">Dies ist ein optionaler Schritt, aber eine, die Sie berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="6c54b-124">This is an optional step, but one that you should consider.</span></span> <span data-ttu-id="6c54b-125">Um Benutzer des ausstehenden Teams Upgrades zu benachrichtigen, können Sie die lokale TeamsUpgradePolicy und TeamsUpgradeConfiguration-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="6c54b-125">To notify users of the pending Teams upgrade, you can use the on-premises TeamsUpgradePolicy and TeamsUpgradeConfiguration cmdlets.</span></span> <span data-ttu-id="6c54b-126">Sie können auch automatische automatische-Download von Teams im Hintergrund vor dem Upgrade (nur Win32-Clients) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6c54b-126">You can also configure silent auto-download of Teams in the background prior to upgrade (Win32 clients only).</span></span> 

<span data-ttu-id="6c54b-127">Verwenden Sie, um Benutzer zu benachrichtigen, dass sie Teams aktualisiert werden, beispielsweise das lokale TeamsUpgradePolicy-Cmdlet mit dem Parameter - NotifySbUser.</span><span class="sxs-lookup"><span data-stu-id="6c54b-127">For example, to notify users that they are being upgraded to Teams, use the on-premises TeamsUpgradePolicy cmdlet with the -NotifySbUser parameter.</span></span> <span data-ttu-id="6c54b-128">Sie können die Richtlinie auf global, Standort, Pool oder Benutzer Ebene festlegen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-128">You can set the policy on a global, site, pool, or user level.</span></span> <span data-ttu-id="6c54b-129">Der folgende Befehl erstellt und eine Richtlinie auf Benutzerebene gewährt:</span><span class="sxs-lookup"><span data-stu-id="6c54b-129">The following command creates and grants a user-level policy:</span></span>
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

<span data-ttu-id="6c54b-130">Sie können diese Richtlinie mit dem Cmdlet Get-CsTeamsUpgradePolicy überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-130">You can check this policy by using the Get-csTeamsUpgradePolicy cmdlet.</span></span>

<span data-ttu-id="6c54b-131">Ihre Benutzer werden eine Benachrichtigung über den bevorstehenden Wechsel zu Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c54b-131">Your users will see a notification of the impending move to Teams.</span></span> <span data-ttu-id="6c54b-132">Die Benachrichtigung wird auf Win32, Mac, Mobile und Web-Clients (mit der richtigen Version).</span><span class="sxs-lookup"><span data-stu-id="6c54b-132">The notification occurs on Win32, Mac, Mobile, and Web Clients (with the right version).</span></span>

<span data-ttu-id="6c54b-133">Sie können das automatische Herunterladen-Teams (Win32-Clients) für Benutzer mit dem lokalen TeamsUpgradeConfiguration-Cmdlet mit dem Parameter DownloadTeams aktualisierten angeben.</span><span class="sxs-lookup"><span data-stu-id="6c54b-133">You can specify automatic download of Teams (for Win32 clients) for users being upgraded by using the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="6c54b-134">Legen Sie diese Richtlinie auf der Ebene der Mandanten, und es können angewendet werden soll, klicken Sie auf eine globale, Standort- und pool-Ebene.</span><span class="sxs-lookup"><span data-stu-id="6c54b-134">You set this policy at the tenant level, and it can be applied on a global, site, and pool level.</span></span> <span data-ttu-id="6c54b-135">Der folgende Befehl wird beispielsweise die Richtlinie auf Standortebene:</span><span class="sxs-lookup"><span data-stu-id="6c54b-135">For example, the following command sets the policy at the site level:</span></span>

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

<span data-ttu-id="6c54b-136">Standardmäßig müssen der Wert von DownloadTeams ist True, aber Sie auch NotifySfbUser auf "true", um Teams für einen bestimmten Benutzer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6c54b-136">By default, the value of DownloadTeams is True, but you must also set NotifySfbUser to True to enable Teams for a given user.</span></span> 

## <a name="make-sure-your-users-have-a-valid-license"></a><span data-ttu-id="6c54b-137">Stellen Sie sicher, dass Ihre Benutzer eine gültige Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-137">Make sure your users have a valid license</span></span>  
<span data-ttu-id="6c54b-138">Vor der Migration muss der lokale Benutzer eine gültige Lizenz, wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="6c54b-138">Before migration, the on-premises user must be given a valid license, as follows:</span></span>

-   <span data-ttu-id="6c54b-139">Benutzer benötigen eine Lizenz Teams.</span><span class="sxs-lookup"><span data-stu-id="6c54b-139">User must have a Teams license.</span></span>
-   <span data-ttu-id="6c54b-140">Wenn der Benutzer für die Verwendung von lokalen Enterprise Voice konfiguriert ist, müssen sie eine online Voice-Lizenz verfügen, beim Verschieben.</span><span class="sxs-lookup"><span data-stu-id="6c54b-140">If the user is configured to use on-premises Enterprise Voice, they must have an online voice license when moving.</span></span> 
-   <span data-ttu-id="6c54b-141">Wenn der Benutzer für einwahlkonferenzen lokale konfiguriert ist, müssen sie eine Lizenz für Telefonsystem (Cloud, PBX) verfügen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-141">If the user is configured for on-premises dial-in conferencing, they must have a license for Phone System (Cloud PBX).</span></span>

## <a name="voice-configuration-requirements"></a><span data-ttu-id="6c54b-142">Anforderungen für die VoIP-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="6c54b-142">Voice configuration requirements</span></span>

<span data-ttu-id="6c54b-143">Wenn Ihre lokalen Benutzer lokale VoIP verfügen, haben Sie zwei Optionen:</span><span class="sxs-lookup"><span data-stu-id="6c54b-143">If your on-premises users have on-premises voice, you have two options:</span></span>

-  <span data-ttu-id="6c54b-144">**Migrieren von Benutzern mit Telefoniefunktionen.**</span><span class="sxs-lookup"><span data-stu-id="6c54b-144">**Migrate users with telephony capabilities.**</span></span> <span data-ttu-id="6c54b-145">Benutzer können tätigen und Entgegennehmen von Anrufen über den Client Teams.</span><span class="sxs-lookup"><span data-stu-id="6c54b-145">Users can make and receive calls using the Teams client.</span></span>  <span data-ttu-id="6c54b-146">Sie können entweder Microsoft aufrufen planen direkte Routing oder Teams die Telefondienste Verbindung auswählen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-146">You can choose either Microsoft Calling Plan or Direct Routing to connect the telephony services to Teams.</span></span>  

    -  <span data-ttu-id="6c54b-147">Planen der Aufruf von Microsoft bietet eine all-in-Cloud-VoIP-Lösung.</span><span class="sxs-lookup"><span data-stu-id="6c54b-147">Microsoft Calling Plan provides an all-in-the-cloud voice solution.</span></span> <span data-ttu-id="6c54b-148">Weitere Informationen zu Microsoft aufrufen planen finden Sie unter (Link bald verfügbar).</span><span class="sxs-lookup"><span data-stu-id="6c54b-148">For more information about Microsoft Calling Plan, see (link coming soon).</span></span> 
    -  <span data-ttu-id="6c54b-149">Direktes Routing können Sie nahezu alle PSTN-Trunk verwenden, und Sie können Interoperabilität zwischen im Besitz des Kunden Telefoniegeräten und Microsoft Telefonsystem konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6c54b-149">Direct Routing lets you use virtually any PSTN trunk,  and you can configure interoperability between customer-owned telephony equipment and Microsoft Phone System.</span></span>  <span data-ttu-id="6c54b-150">Weitere Informationen finden Sie unter [Planen der direkten Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan) und [Direkte Routing konfigurieren](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="6c54b-150">For more information, see [Plan Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan) and [Configure Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-configure).</span></span>

-  <span data-ttu-id="6c54b-151">**Migrieren von Benutzern ohne Telefoniefunktionen.**</span><span class="sxs-lookup"><span data-stu-id="6c54b-151">**Migrate users without telephony capabilities.**</span></span> <span data-ttu-id="6c54b-152">Wenn Sie Benutzer migrieren, ohne Telefoniefunktionen beizubehalten, stellen Sie sicher, dass Benutzer in der Cloud entsprechende Lizenzen haben.</span><span class="sxs-lookup"><span data-stu-id="6c54b-152">If you migrate users without preserving  telephony capabilities, make sure users have appropriate licenses in the cloud.</span></span> 

## <a name="assign-a-teams-upgrade-policy"></a><span data-ttu-id="6c54b-153">Zuweisen einer Richtlinie auf Teams aktualisieren</span><span class="sxs-lookup"><span data-stu-id="6c54b-153">Assign a Teams Upgrade policy</span></span>  
<span data-ttu-id="6c54b-154">Online-Tools können zum Verwalten von Richtlinien für Benutzer, wie beispielsweise routing von eingehenden Nachrichten und Anrufe steuern.</span><span class="sxs-lookup"><span data-stu-id="6c54b-154">You can use online tools to manage user policies, such as to control routing of incoming messages and calls.</span></span> <span data-ttu-id="6c54b-155">Weitere Informationen finden Sie unter (Link bald verfügbar).</span><span class="sxs-lookup"><span data-stu-id="6c54b-155">For more information, see (link coming soon).</span></span>

## <a name="move-on-premises-users-to-teams"></a><span data-ttu-id="6c54b-156">Migrieren von lokalen Benutzern zu Teams</span><span class="sxs-lookup"><span data-stu-id="6c54b-156">Move on-premises users to Teams</span></span>

<span data-ttu-id="6c54b-157">Sie können Ihre lokalen Benutzer mithilfe von PowerShell-Cmdlets oder mithilfe der Skype Business Server 2019-Systemsteuerung Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="6c54b-157">You can move your on-premises users to Teams by using PowerShell cmdlets or by using the Skype for Business Server 2019 Control Panel.</span></span>

### <a name="move-users-by-using-powershell"></a><span data-ttu-id="6c54b-158">Verschieben Sie Benutzer mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c54b-158">Move users by using PowerShell</span></span>
<span data-ttu-id="6c54b-159">Um Ihren Benutzern mithilfe von PowerShell Teams zu verschieben, werden Sie das Move-CsUser-Cmdlet mit dem Parameter MoveToTeams wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="6c54b-159">To move your users to Teams by using PowerShell, you’ll use the Move-CsUser cmdlet with the moveToTeams parameter as follows:</span></span>

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

<span data-ttu-id="6c54b-160">($cred = Get-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-160">($cred = get-Credentials.</span></span> <span data-ttu-id="6c54b-161">Sie müssen Office 365-Admin-Anmeldeinformationen angeben.)</span><span class="sxs-lookup"><span data-stu-id="6c54b-161">You must provide Office 365 admin credentials.)</span></span>

> [!NOTE]
> <span data-ttu-id="6c54b-162">Dieser Befehl legt die TeamsUpgradePolicy TeamsOnly Modus.</span><span class="sxs-lookup"><span data-stu-id="6c54b-162">This command sets the TeamsUpgradePolicy to TeamsOnly mode.</span></span> 
 
<span data-ttu-id="6c54b-163">Nachdem der Wechsel zu Teams erfolgreich ist, wird Skype für Business-Client des Benutzers die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6c54b-163">After the move to Teams is successful, the user’s Skype for Business client will display the following message:</span></span> 

![Migration zu Teams Nachricht wurde ordnungsgemäß abgeschlossen](../media/teams-upgrade-complete-message.png)

<span data-ttu-id="6c54b-165">Beachten Sie, dass Skype für Unternehmen, die dem Benutzer mit Ausnahme von zum Teilnehmen an einer Besprechung nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6c54b-165">Note that Skype for Business will no longer be available to the user except to join a meeting.</span></span> 

<span data-ttu-id="6c54b-166">In seltenen Fällen beim Verschieben von Ihren Benutzern, Teams möchten Sie möglicherweise außer Kraft setzen einwahlkonferenzen und cloud-Voice-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-166">In rare cases, when moving your users to Teams, you might want to override dial-in conferencing and cloud voice functionality.</span></span> <span data-ttu-id="6c54b-167">Dazu können Sie mit den folgenden Parametern mit dem Befehl Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="6c54b-167">You can do this by using the following parameters with the Move-CsUser command:</span></span>
- <span data-ttu-id="6c54b-168">**BypassAudioConferencingCheck:** Wenn ein Benutzer einwahlkonferenzen für lokale aktiviert hat, muss der Benutzer auch eine AudioConf Lizenz zugewiesen in Office 365 vor der Migration verfügen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-168">**BypassAudioConferencingCheck:** If a user has dial-in conferencing enabled for on-premises, the user must also have an AudioConf license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="6c54b-169">Nachdem die Cloud migriert werden, wird der Benutzer für Audiokonferenzen in der Cloud bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c54b-169">Once migrated to the cloud, the user will be provisioned for audio conferencing in the cloud.</span></span> <span data-ttu-id="6c54b-170">Wenn aus irgendeinem Grund soll Verschieben eines Benutzers in der Cloud, aber die Audiokonferenz-Funktionalität nicht verwenden, können Sie sie durch die Angabe dieses Parameters überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6c54b-170">If, for some reason, you want to move a user to the cloud, but not use the audio conferencing functionality, you can override it by specifying this parameter.</span></span>
- <span data-ttu-id="6c54b-171">**ByPassEnterpriseVoice:** Wenn ein Benutzer Enterprise-VoIP für lokale aktiviert hat, muss der Benutzer eine zugeordnete in Office 365 vor dem Migrieren von Enterprise-VoIP-Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-171">**ByPassEnterpriseVoice:** If a user has Enterprise Voice enabled for on-premises, the user must have an Enterprise Voice license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="6c54b-172">Nach der Migration zur Cloud wird der Benutzer für VoIP in der Cloud bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6c54b-172">After migration to the cloud, the user will be provisioned for voice in the cloud.</span></span> <span data-ttu-id="6c54b-173">Wenn aus irgendeinem Grund soll Verschieben eines Benutzers in die Cloud aber Cloud Voice-Funktionen nicht verwenden, können Sie die Cloud VoIP durch Angabe dieses Parameters überschreiben.</span><span class="sxs-lookup"><span data-stu-id="6c54b-173">If, for some reason, you want to move a user to the cloud but not use cloud voice functionality, you can override cloud voice by specifying this parameter.</span></span>
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="6c54b-174">Verschieben Sie Benutzer mithilfe der Skype für Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6c54b-174">Move users by using the Skype for Business Server Control Panel</span></span> 

<span data-ttu-id="6c54b-175">So verschieben Sie Benutzer für Teams mithilfe der Skype für die Business-Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="6c54b-175">To move users to Teams by using the Skype for Business Control Panel:</span></span>

1. <span data-ttu-id="6c54b-176">Öffnen Sie die Skype für die Business-Systemsteuerung, und melden Sie sich bei Ihrem Office 365-Konto.</span><span class="sxs-lookup"><span data-stu-id="6c54b-176">Open the Skype for Business Control Panel and sign in to your Office 365 account.</span></span>

2. <span data-ttu-id="6c54b-177">Wählen Sie im linken Navigationsbereich **Benutzer** aus, und wählen Sie die Benutzer zum Migrieren.</span><span class="sxs-lookup"><span data-stu-id="6c54b-177">Select **Users** in the left navigation, and select the users to migrate.</span></span> 
     
3. <span data-ttu-id="6c54b-178">Wählen Sie im Menü **Aktion** **Verschieben Sie ausgewählte Benutzer in Teams**.</span><span class="sxs-lookup"><span data-stu-id="6c54b-178">On the **Action** menu, choose **Move selected users to Teams**.</span></span> 

    ![Durch Klicken auf Weiter, um die Migration zu bestätigen](../media/migration-confirmation.png)
    
4. <span data-ttu-id="6c54b-180">Klicken Sie auf **Weiter** , um Ihre Migration zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="6c54b-180">Click **Next** to confirm your migration.</span></span> 

<span data-ttu-id="6c54b-181">Nachdem der Benutzer auf Teams verschoben wird, sehen Sie Bestätigungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="6c54b-181">After the user is moved to Teams, you will see  confirmations like the following:</span></span>

<span data-ttu-id="6c54b-182">![Verschieben Sie Benutzer zur Bestätigung](../media/move-user-confirmation.png)
</span><span class="sxs-lookup"><span data-stu-id="6c54b-182">![Move users confirmation](../media/move-user-confirmation.png)
</span></span><br/><br/>
<span data-ttu-id="6c54b-183">![Meldung, dass Benutzer verschoben wurden](../media/users-moved-successfully.png)</span><span class="sxs-lookup"><span data-stu-id="6c54b-183">![Message that users have been moved](../media/users-moved-successfully.png)</span></span>

<span data-ttu-id="6c54b-184">Wenn die Verschiebung nicht erfolgreich war, wird eine Meldung wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6c54b-184">If the move was not successful, you will see a message like the following:</span></span>

![Nachricht, die Benutzer konnte nicht verschoben werden](../media/users-not-moved.png)
