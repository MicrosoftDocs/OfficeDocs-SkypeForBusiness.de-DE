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
ms.openlocfilehash: 27e8ac831f7009a373b2ed28d484f00f9462ef12
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030784"
---
# <a name="move-users-from-on-premises-to-teams"></a><span data-ttu-id="5bfd6-103">Verschieben von Benutzern von lokalen Teams</span><span class="sxs-lookup"><span data-stu-id="5bfd6-103">Move users from on-premises to Teams</span></span>

<span data-ttu-id="5bfd6-104">Mit Skype für Business Server 2019 können Sie Ihre lokalen Benutzer Teams wie in diesem Artikel beschriebene migrieren.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-104">With Skype for Business Server 2019, you can migrate your on-premises users to Teams as described in this article.</span></span>

<span data-ttu-id="5bfd6-105">Beachten Sie, nach dem Verschieben von Ihren Benutzern, Teams:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-105">Be aware that after moving your users to Teams:</span></span> 
 
- <span data-ttu-id="5bfd6-106">Ihre Besprechungen zu Skype für Business Online migriert werden, und ihre Kontakte zu Teams migriert werden.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-106">Their meetings are migrated to Skype for Business Online, and their contacts are migrated to Teams.</span></span> 
- <span data-ttu-id="5bfd6-107">Sie können Skype-Besprechungen über die Skype für Business-rich-Client (Benutzer werden nicht für jedes Mal Anmeldung aufgefordert) oder über die Skype Besprechungen App (erfordert eine einmalige herunter, und Anmeldung) teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-107">They can join Skype meetings through the Skype for Business rich client (users are not prompted for sign-in each time) or through the Skype Meetings App (requires a one-time download and sign-in).</span></span> <span data-ttu-id="5bfd6-108">Klickt ein Benutzer auf einen Skype für Business Link zur Besprechung innerhalb von Teams, wird die Besprechung in der entsprechenden app gestartet.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-108">When a user clicks on a Skype for Business meeting link within Teams, the meeting will launch in the appropriate app.</span></span>

- <span data-ttu-id="5bfd6-109">Unter Mobile werden Ihre Benutzer können vorhandene Skype für Business Besprechungen mit native app teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-109">On Mobile, your users will be able to join existing Skype for Business meetings using the native app only.</span></span>

    ![Mobile Skype-Besprechung](../media/mobile-skype-meeting.png)

> [!NOTE]
> <span data-ttu-id="5bfd6-111">Nachdem ein Benutzer auf den TeamsOnly Modus verschoben wurde, wird der Benutzer in Skype für Business Online, verwaltet.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-111">After a user is moved to TeamsOnly mode, the user is homed in Skype for Business Online.</span></span>

## <a name="prerequisites-for-moving-on-premises-users-to-teams"></a><span data-ttu-id="5bfd6-112">Erforderliche Komponenten zum Verschieben von lokalen Benutzern, Teams</span><span class="sxs-lookup"><span data-stu-id="5bfd6-112">Prerequisites for moving on-premises users to Teams</span></span> 

<span data-ttu-id="5bfd6-113">Dieser Abschnitt beschreibt die erforderlichen Komponenten für Ihre lokalen Benutzer Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-113">This section describes the prerequisites for moving your on-premises users to Teams.</span></span> <span data-ttu-id="5bfd6-114">Du musst:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-114">You must:</span></span>
- <span data-ttu-id="5bfd6-115">[Einrichten von hybridkonnektivität](#set-up-hybrid-connectivity) (Wenn Sie dies nicht bereits geschehen ist)</span><span class="sxs-lookup"><span data-stu-id="5bfd6-115">[Set up hybrid connectivity](#set-up-hybrid-connectivity) (if you have not already done so)</span></span>
- <span data-ttu-id="5bfd6-116">[Benachrichtigen Sie die Benutzer, der die Verschiebung Teams](#notify-your-users-of-the-move-to-teams) (optional)</span><span class="sxs-lookup"><span data-stu-id="5bfd6-116">[Notify your users of the move to Teams](#notify-your-users-of-the-move-to-teams) (optional)</span></span>
- [<span data-ttu-id="5bfd6-117">Stellen Sie sicher, dass Ihre Benutzer eine gültige Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-117">Ensure that your users have a valid license</span></span>](#make-sure-your-users-have-a-valid-license)
- [<span data-ttu-id="5bfd6-118">Beachten Sie bei Anforderungen für die VoIP-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5bfd6-118">Be aware of voice configuration requirements</span></span>](#voice-configuration-requirements)
- <span data-ttu-id="5bfd6-119">[Zuweisen einer Richtlinie auf Teams aktualisieren](#assign-a-teams-upgrade-policy) (optional)</span><span class="sxs-lookup"><span data-stu-id="5bfd6-119">[Assign a Teams Upgrade policy](#assign-a-teams-upgrade-policy) (optional)</span></span>

## <a name="set-up-hybrid-connectivity"></a><span data-ttu-id="5bfd6-120">Einrichten von hybridkonnektivität</span><span class="sxs-lookup"><span data-stu-id="5bfd6-120">Set up hybrid connectivity</span></span>
<span data-ttu-id="5bfd6-121">Bevor Sie Ihre Benutzer migrieren, wenn Sie nicht bereits getan haben, müssen Sie sicherstellen, dass Sie hybridkonnektivität zwischen Ihrer Skype für Business Server lokalen Umgebung und Skype für Business Online konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-121">Before you migrate your users, if you have not already done so, you must ensure that you have configured hybrid connectivity between your Skype for Business Server on-premises environment and Skype for Business Online.</span></span> <span data-ttu-id="5bfd6-122">Hybrid-Diensten ist erforderlich, Active Directory-Synchronisierung, Konfigurieren von Verbund und So weiter.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-122">Hybrid connectivity requires Active Directory synchronization, configuring federation, and so on.</span></span> <span data-ttu-id="5bfd6-123">Weitere Informationen finden Sie unter [Planen von hybridkonnektivität](plan-hybrid-connectivity.md) und [hybridkonnektivität konfigurieren](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="5bfd6-123">For more information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span>

## <a name="notify-your-users-of-the-move-to-teams"></a><span data-ttu-id="5bfd6-124">Benachrichtigen Sie die Benutzer, der die Verschiebung Teams</span><span class="sxs-lookup"><span data-stu-id="5bfd6-124">Notify your users of the move to Teams</span></span> 
<span data-ttu-id="5bfd6-125">Dies ist ein optionaler Schritt, aber eine, die Sie berücksichtigen sollten.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-125">This is an optional step, but one that you should consider.</span></span> <span data-ttu-id="5bfd6-126">Um Benutzer des ausstehenden Teams Upgrades zu benachrichtigen, können Sie die lokale TeamsUpgradePolicy und TeamsUpgradeConfiguration-Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-126">To notify users of the pending Teams upgrade, you can use the on-premises TeamsUpgradePolicy and TeamsUpgradeConfiguration cmdlets.</span></span> <span data-ttu-id="5bfd6-127">Sie können auch automatische automatische-Download von Teams im Hintergrund vor dem Upgrade (nur Win32-Clients) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-127">You can also configure silent auto-download of Teams in the background prior to upgrade (Win32 clients only).</span></span> 

<span data-ttu-id="5bfd6-128">Verwenden Sie, um Benutzer zu benachrichtigen, dass sie Teams aktualisiert werden, beispielsweise das lokale TeamsUpgradePolicy-Cmdlet mit dem Parameter - NotifySbUser.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-128">For example, to notify users that they are being upgraded to Teams, use the on-premises TeamsUpgradePolicy cmdlet with the -NotifySbUser parameter.</span></span> <span data-ttu-id="5bfd6-129">Sie können die Richtlinie auf global, Standort, Pool oder Benutzer Ebene festlegen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-129">You can set the policy on a global, site, pool, or user level.</span></span> <span data-ttu-id="5bfd6-130">Der folgende Befehl erstellt und eine Richtlinie auf Benutzerebene gewährt:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-130">The following command creates and grants a user-level policy:</span></span>
 
```
New-CsTeamsUpgradePolicy -Identity UpgradeNotice -NotifySfbUser $true 
Grant-CsTeamsUpgradePolicy -Identity user01 -PolicyName “UpgradeNotice”
```

<span data-ttu-id="5bfd6-131">Sie können diese Richtlinie mit dem Cmdlet Get-CsTeamsUpgradePolicy überprüfen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-131">You can check this policy by using the Get-csTeamsUpgradePolicy cmdlet.</span></span>

<span data-ttu-id="5bfd6-132">Ihre Benutzer werden eine Benachrichtigung über den bevorstehenden Wechsel zu Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-132">Your users will see a notification of the impending move to Teams.</span></span> <span data-ttu-id="5bfd6-133">Die Benachrichtigung wird auf Win32, Mac, Mobile und Web-Clients (mit der richtigen Version).</span><span class="sxs-lookup"><span data-stu-id="5bfd6-133">The notification occurs on Win32, Mac, Mobile, and Web Clients (with the right version).</span></span>

<span data-ttu-id="5bfd6-134">Sie können das automatische Herunterladen-Teams (Win32-Clients) für Benutzer mit dem lokalen TeamsUpgradeConfiguration-Cmdlet mit dem Parameter DownloadTeams aktualisierten angeben.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-134">You can specify automatic download of Teams (for Win32 clients) for users being upgraded by using the on-premises TeamsUpgradeConfiguration cmdlet with the DownloadTeams parameter.</span></span> <span data-ttu-id="5bfd6-135">Legen Sie diese Richtlinie auf der Ebene der Mandanten, und es können angewendet werden soll, klicken Sie auf eine globale, Standort- und pool-Ebene.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-135">You set this policy at the tenant level, and it can be applied on a global, site, and pool level.</span></span> <span data-ttu-id="5bfd6-136">Der folgende Befehl wird beispielsweise die Richtlinie auf Standortebene:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-136">For example, the following command sets the policy at the site level:</span></span>

```
New-CsTeamsUpgradeConfiguration -Identity “site:redmond1” 
```

<span data-ttu-id="5bfd6-137">Standardmäßig müssen der Wert von DownloadTeams ist True, aber Sie auch NotifySfbUser auf "true", um Teams für einen bestimmten Benutzer zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-137">By default, the value of DownloadTeams is True, but you must also set NotifySfbUser to True to enable Teams for a given user.</span></span> 

## <a name="make-sure-your-users-have-a-valid-license"></a><span data-ttu-id="5bfd6-138">Stellen Sie sicher, dass Ihre Benutzer eine gültige Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-138">Make sure your users have a valid license</span></span>  
<span data-ttu-id="5bfd6-139">Vor der Migration muss der lokale Benutzer eine gültige Lizenz, wie folgt angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-139">Before migration, the on-premises user must be given a valid license, as follows:</span></span>

-   <span data-ttu-id="5bfd6-140">Benutzer benötigen eine Lizenz Teams.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-140">User must have a Teams license.</span></span>
-   <span data-ttu-id="5bfd6-141">Wenn der Benutzer für die Verwendung von lokalen Enterprise Voice konfiguriert ist, müssen sie eine online Voice-Lizenz verfügen, beim Verschieben.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-141">If the user is configured to use on-premises Enterprise Voice, they must have an online voice license when moving.</span></span> 
-   <span data-ttu-id="5bfd6-142">Wenn der Benutzer für einwahlkonferenzen lokale konfiguriert ist, müssen sie eine Lizenz für Telefonsystem (Cloud, PBX) verfügen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-142">If the user is configured for on-premises dial-in conferencing, they must have a license for Phone System (Cloud PBX).</span></span>

## <a name="voice-configuration-requirements"></a><span data-ttu-id="5bfd6-143">Anforderungen für die VoIP-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5bfd6-143">Voice configuration requirements</span></span>

<span data-ttu-id="5bfd6-144">Wenn Ihre lokalen Benutzer lokale VoIP verfügen, haben Sie zwei Optionen:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-144">If your on-premises users have on-premises voice, you have two options:</span></span>

-  <span data-ttu-id="5bfd6-145">**Migrieren von Benutzern mit Telefoniefunktionen.**</span><span class="sxs-lookup"><span data-stu-id="5bfd6-145">**Migrate users with telephony capabilities.**</span></span> <span data-ttu-id="5bfd6-146">Benutzer können tätigen und Entgegennehmen von Anrufen über den Client Teams.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-146">Users can make and receive calls using the Teams client.</span></span>  <span data-ttu-id="5bfd6-147">Sie können entweder Microsoft aufrufen planen direkte Routing oder Teams die Telefondienste Verbindung auswählen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-147">You can choose either Microsoft Calling Plan or Direct Routing to connect the telephony services to Teams.</span></span>  

    -  <span data-ttu-id="5bfd6-148">Planen der Aufruf von Microsoft bietet eine all-in-Cloud-VoIP-Lösung.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-148">Microsoft Calling Plan provides an all-in-the-cloud voice solution.</span></span> <span data-ttu-id="5bfd6-149">Weitere Informationen zu Microsoft aufrufen planen finden Sie unter (Link bald verfügbar).</span><span class="sxs-lookup"><span data-stu-id="5bfd6-149">For more information about Microsoft Calling Plan, see (link coming soon).</span></span> 
    -  <span data-ttu-id="5bfd6-150">Direktes Routing können Sie nahezu alle PSTN-Trunk verwenden, und Sie können Interoperabilität zwischen im Besitz des Kunden Telefoniegeräten und Microsoft Telefonsystem konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-150">Direct Routing lets you use virtually any PSTN trunk,  and you can configure interoperability between customer-owned telephony equipment and Microsoft Phone System.</span></span>  <span data-ttu-id="5bfd6-151">Weitere Informationen finden Sie unter [Planen der direkten Routing](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan) und [Direkte Routing konfigurieren](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="5bfd6-151">For more information, see [Plan Direct Routing](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan) and [Configure Direct Routing](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-configure).</span></span>

-  <span data-ttu-id="5bfd6-152">**Migrieren von Benutzern ohne Telefoniefunktionen.**</span><span class="sxs-lookup"><span data-stu-id="5bfd6-152">**Migrate users without telephony capabilities.**</span></span> <span data-ttu-id="5bfd6-153">Wenn Sie Benutzer migrieren, ohne Telefoniefunktionen beizubehalten, stellen Sie sicher, dass Benutzer in der Cloud entsprechende Lizenzen haben.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-153">If you migrate users without preserving  telephony capabilities, make sure users have appropriate licenses in the cloud.</span></span> 

## <a name="assign-a-teams-upgrade-policy"></a><span data-ttu-id="5bfd6-154">Zuweisen einer Richtlinie auf Teams aktualisieren</span><span class="sxs-lookup"><span data-stu-id="5bfd6-154">Assign a Teams Upgrade policy</span></span>  
<span data-ttu-id="5bfd6-155">Online-Tools können zum Verwalten von Richtlinien für Benutzer, wie beispielsweise routing von eingehenden Nachrichten und Anrufe steuern.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-155">You can use online tools to manage user policies, such as to control routing of incoming messages and calls.</span></span> <span data-ttu-id="5bfd6-156">Weitere Informationen finden Sie unter (Link bald verfügbar).</span><span class="sxs-lookup"><span data-stu-id="5bfd6-156">For more information, see (link coming soon).</span></span>

## <a name="move-on-premises-users-to-teams"></a><span data-ttu-id="5bfd6-157">Migrieren von lokalen Benutzern zu Teams</span><span class="sxs-lookup"><span data-stu-id="5bfd6-157">Move on-premises users to Teams</span></span>

<span data-ttu-id="5bfd6-158">Sie können Ihre lokalen Benutzer mithilfe von PowerShell-Cmdlets oder mithilfe der Skype Business Server 2019-Systemsteuerung Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-158">You can move your on-premises users to Teams by using PowerShell cmdlets or by using the Skype for Business Server 2019 Control Panel.</span></span>

### <a name="move-users-by-using-powershell"></a><span data-ttu-id="5bfd6-159">Verschieben Sie Benutzer mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="5bfd6-159">Move users by using PowerShell</span></span>
<span data-ttu-id="5bfd6-160">Um Ihren Benutzern mithilfe von PowerShell Teams zu verschieben, werden Sie das Move-CsUser-Cmdlet mit dem Parameter MoveToTeams wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-160">To move your users to Teams by using PowerShell, you’ll use the Move-CsUser cmdlet with the moveToTeams parameter as follows:</span></span>

```
Move-CsUser -Identity user0 -Target sipfed.online.lync.com -moveToTeams -credentials $cred. 
```

<span data-ttu-id="5bfd6-161">($cred = Get-Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-161">($cred = get-Credentials.</span></span> <span data-ttu-id="5bfd6-162">Sie müssen Office 365-Admin-Anmeldeinformationen angeben.)</span><span class="sxs-lookup"><span data-stu-id="5bfd6-162">You must provide Office 365 admin credentials.)</span></span>

> [!NOTE]
> <span data-ttu-id="5bfd6-163">Dieser Befehl legt die TeamsInteropPolicy Teams und der TeamsUpgradePolicy TeamsOnly-Modus.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-163">This command sets the TeamsInteropPolicy to Teams and sets the TeamsUpgradePolicy to TeamsOnly mode.</span></span> 
 
<span data-ttu-id="5bfd6-164">Nachdem der Wechsel zu Teams erfolgreich ist, wird Skype für Business-Client des Benutzers die folgende Meldung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-164">After the move to Teams is successful, the user’s Skype for Business client will display the following message:</span></span> 

![Migration zu Teams Nachricht wurde ordnungsgemäß abgeschlossen](../media/teams-upgrade-complete-message.png)

<span data-ttu-id="5bfd6-166">Beachten Sie, dass Skype für Unternehmen, die dem Benutzer mit Ausnahme von zum Teilnehmen an einer Besprechung nicht mehr verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-166">Note that Skype for Business will no longer be available to the user except to join a meeting.</span></span> 

<span data-ttu-id="5bfd6-167">In seltenen Fällen beim Verschieben von Ihren Benutzern, Teams möchten Sie möglicherweise außer Kraft setzen einwahlkonferenzen und cloud-Voice-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-167">In rare cases, when moving your users to Teams, you might want to override dial-in conferencing and cloud voice functionality.</span></span> <span data-ttu-id="5bfd6-168">Dazu können Sie mit den folgenden Parametern mit dem Befehl Move-CsUser:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-168">You can do this by using the following parameters with the Move-CsUser command:</span></span>
- <span data-ttu-id="5bfd6-169">**BypassAudioConferencingCheck:** Wenn ein Benutzer einwahlkonferenzen für lokale aktiviert hat, muss der Benutzer auch eine AudioConf Lizenz zugewiesen in Office 365 vor der Migration verfügen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-169">**BypassAudioConferencingCheck:** If a user has dial-in conferencing enabled for on-premises, the user must also have an AudioConf license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="5bfd6-170">Nachdem die Cloud migriert werden, wird der Benutzer für Audiokonferenzen in der Cloud bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-170">Once migrated to the cloud, the user will be provisioned for audio conferencing in the cloud.</span></span> <span data-ttu-id="5bfd6-171">Wenn aus irgendeinem Grund soll Verschieben eines Benutzers in der Cloud, aber die Audiokonferenz-Funktionalität nicht verwenden, können Sie sie durch die Angabe dieses Parameters überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-171">If, for some reason, you want to move a user to the cloud, but not use the audio conferencing functionality, you can override it by specifying this parameter.</span></span>
- <span data-ttu-id="5bfd6-172">**ByPassEnterpriseVoice:** Wenn ein Benutzer Enterprise-VoIP für lokale aktiviert hat, muss der Benutzer eine zugeordnete in Office 365 vor dem Migrieren von Enterprise-VoIP-Lizenz verfügen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-172">**ByPassEnterpriseVoice:** If a user has Enterprise Voice enabled for on-premises, the user must have an Enterprise Voice license assigned in Office 365 before migrating.</span></span> <span data-ttu-id="5bfd6-173">Nach der Migration zur Cloud wird der Benutzer für VoIP in der Cloud bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-173">After migration to the cloud, the user will be provisioned for voice in the cloud.</span></span> <span data-ttu-id="5bfd6-174">Wenn aus irgendeinem Grund soll Verschieben eines Benutzers in die Cloud aber Cloud Voice-Funktionen nicht verwenden, können Sie die Cloud VoIP durch Angabe dieses Parameters überschreiben.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-174">If, for some reason, you want to move a user to the cloud but not use cloud voice functionality, you can override cloud voice by specifying this parameter.</span></span>
 
### <a name="move-users-by-using-the-skype-for-business-server-control-panel"></a><span data-ttu-id="5bfd6-175">Verschieben Sie Benutzer mithilfe der Skype für Business Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="5bfd6-175">Move users by using the Skype for Business Server Control Panel</span></span> 

<span data-ttu-id="5bfd6-176">So verschieben Sie Benutzer für Teams mithilfe der Skype für die Business-Systemsteuerung:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-176">To move users to Teams by using the Skype for Business Control Panel:</span></span>

1. <span data-ttu-id="5bfd6-177">Öffnen Sie die Skype für die Business-Systemsteuerung, und melden Sie sich bei Ihrem Office 365-Konto.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-177">Open the Skype for Business Control Panel and sign in to your Office 365 account.</span></span>

2. <span data-ttu-id="5bfd6-178">Wählen Sie im linken Navigationsbereich **Benutzer** aus, und wählen Sie die Benutzer zum Migrieren.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-178">Select **Users** in the left navigation, and select the users to migrate.</span></span> 
     
3. <span data-ttu-id="5bfd6-179">Wählen Sie im Menü **Aktion** **Verschieben Sie ausgewählte Benutzer in Teams**.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-179">On the **Action** menu, choose **Move selected users to Teams**.</span></span> 

    ![Durch Klicken auf Weiter, um die Migration zu bestätigen](../media/migration-confirmation.png)
    
4. <span data-ttu-id="5bfd6-181">Klicken Sie auf **Weiter** , um Ihre Migration zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="5bfd6-181">Click **Next** to confirm your migration.</span></span> 

<span data-ttu-id="5bfd6-182">Nachdem der Benutzer auf Teams verschoben wird, sehen Sie Bestätigungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-182">After the user is moved to Teams, you will see  confirmations like the following:</span></span>

<span data-ttu-id="5bfd6-183">![Verschieben Sie Benutzer zur Bestätigung](../media/move-user-confirmation.png)
</span><span class="sxs-lookup"><span data-stu-id="5bfd6-183">![Move users confirmation](../media/move-user-confirmation.png)
</span></span><br/><br/>
<span data-ttu-id="5bfd6-184">![Meldung, dass Benutzer verschoben wurden](../media/users-moved-successfully.png)</span><span class="sxs-lookup"><span data-stu-id="5bfd6-184">![Message that users have been moved](../media/users-moved-successfully.png)</span></span>

<span data-ttu-id="5bfd6-185">Wenn die Verschiebung nicht erfolgreich war, wird eine Meldung wie die folgende angezeigt:</span><span class="sxs-lookup"><span data-stu-id="5bfd6-185">If the move was not successful, you will see a message like the following:</span></span>

![Nachricht, die Benutzer konnte nicht verschoben werden](../media/users-not-moved.png)