---
title: Schnellstarthandbuch – Konfigurieren von Anrufplänen in Microsoft Teams
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
search.appverid: MET150
description: Schnellstarthandbuch für das Konfigurieren von Anrufplänen in Microsoft Teams
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc1c20f87103dc91a317e58dac03389275b255f2
ms.sourcegitcommit: c7c8e5f6d8b25e68bf071745517d38eb45c1e172
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2019
ms.locfileid: "28694697"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="63987-103">Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63987-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="63987-104">Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.</span><span class="sxs-lookup"><span data-stu-id="63987-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="63987-105">Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).</span><span class="sxs-lookup"><span data-stu-id="63987-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="63987-106">Wir empfehlen, bei der Planung und Umsetzung eines erfolgreichen Rollouts neben diesem Schnellstarthandbuch unsere [praktischen Anleitungen](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) und [FastTrack](https://aka.ms/cloudvoice) zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="63987-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="63987-107">Durch Hinzufügen von Anrufplänen – einer Office 365-Funktion, die von Skype for Business unterstützt wird – können Sie jetzt mit Microsoft Teams Festnetz- und Mobiltelefone über das Telefonfestnetz (Public Switched Telephone Network, PSTN) anrufen oder von diesen angerufen werden.</span><span class="sxs-lookup"><span data-stu-id="63987-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Anrufe in Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="63987-109">Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63987-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="63987-110">Zum Aktivieren der Registerkarte **Anrufe** in Teams benötigen Benutzer 1:1 aktiviert werden, Teams aufrufen und Verwenden von Clientidentität Teams, die 1:1-Teams aufrufen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63987-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="63987-111">Weitere Informationen zum Verwalten von 1:1 einwählen, Teams lesen Sie [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="63987-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="63987-112">Um zu erfahren, welche Clients aufrufen unterstützen, lesen Sie [Grenzwerte und Spezifikationen für Microsoft-Teams](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="63987-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/en-us/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="63987-113">Derzeit wird Voicemail in der Registerkarte Anrufe nicht verfügbar, wenn der Benutzer für PSTN-Anrufe aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="63987-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="63987-114">Voraussetzungen für das **Wähltastenfeld** im Teams aktivieren</span><span class="sxs-lookup"><span data-stu-id="63987-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="63987-115">Zum Aktivieren der Registerkarte **Wähltastatur** in Teams und ermöglichen die Benutzer das tätigen und annehmen von PSTN-Anrufe müssen Sie die Bereitstellung von Benutzern für Telefonsystem und plant aufrufen.</span><span class="sxs-lookup"><span data-stu-id="63987-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="63987-116">Zum Aufrufen von plant einrichten finden Sie unter [Einrichten von plant aufrufen](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="63987-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/en-us/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="63987-117">Sie können auch direkten Routing zulassen, dass Ihre Benutzer zu Erf und PSTN-Anrufe empfangen.</span><span class="sxs-lookup"><span data-stu-id="63987-117">You can also use Direct Routing to allow your users to mand and receive PSTN calls.</span></span> <span data-ttu-id="63987-118">Weitere Informationen zum Einrichten der direkten Routing lesen Sie [Direkten Routing konfigurieren](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="63987-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="63987-119">Konfiguration der Interop-Richtlinie für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63987-119">Teams interop policy configuration</span></span>
<span data-ttu-id="63987-120">Um Teams beginnen annehmen von Anrufen zu aktivieren, müssen Sie zum Aktualisieren des Teams und Teams Interop-Richtlinie, über [Microsoft-Teams & Skype für Business-Verwaltungskonsole](https://aka.ms/teamsadmincenter) oder mithilfe von remote Windows PowerShell-Sitzung mit dem Skype für Unternehmen [ `*-CsTeamsUpgradePolicy`und `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) -Cmdlets zum Umleiten von Anrufen an Teams.</span><span class="sxs-lookup"><span data-stu-id="63987-120">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="63987-121">Weitere Informationen zu Upgrades Teams und Teams Interop-Richtlinie finden Sie unter [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="63987-121">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="63987-122">Um den PowerShell-Cmdlets zu suchen, die Sie benötigen, geben Sie "CsTeamsUpgradePolicy" oder "CsTeamsInteropPolicy" im Feld **Filter** in der [Skype für Business PowerShell-Cmdlet-Dokumentation](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="63987-122">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="63987-123">Standard-Teams Upgrade und Interop-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="63987-123">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="63987-124">Microsoft Teams enthält eine Standardrichtlinienkonfiguration, die sicherstellen soll, dass vorhandene Geschäftsworkflows bei der Bereitstellung von Microsoft Teams nicht gestört werden.</span><span class="sxs-lookup"><span data-stu-id="63987-124">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="63987-125">VoIP-, PSTN- und Partneranrufe an Ihre Benutzer werden standardmäßig weiterhin an Skype for Business weitergeleitet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe in Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="63987-125">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="63987-126">Dadurch werden unbeabsichtigte Unterbrechungen der VoIP-Dienste vermieden, wenn Sie mit dem Pilotprojekt und der Bereitstellung von Microsoft Teams beginnen.</span><span class="sxs-lookup"><span data-stu-id="63987-126">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="63987-127">Upgrade Richtlinie in der Standardeinstellung ist bei legacy-Modus, die berücksichtigt werden Teams Interop-Richtlinie, um festzustellen, wo Chats und Anrufe weitergeleitet werden – stehen aufbewahrt Teams Teams oder Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="63987-127">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="63987-128">Die Verhalten des Teams aktualisieren Richtlinie und Teams Interop-Richtlinie wird bald ändern, wie beschrieben in [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="63987-128">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="63987-129">So sieht die Standardkonfiguration der Interop-Richtlinie für Microsoft Teams aus:</span><span class="sxs-lookup"><span data-stu-id="63987-129">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="63987-130">Die Standardkonfiguration sieht die folgenden Verhaltensweisen vor:</span><span class="sxs-lookup"><span data-stu-id="63987-130">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="63987-131">**Für bestehende Skype for Business-Kunden** soll die Richtlinie sicherstellen, dass Skype for Business-Anrufe an Skype for Business und Microsoft Teams-Anrufe an Microsoft Teams geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="63987-131">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="63987-132">PSTN-Anrufe und Partneranrufe werden an Skype for Business geleitet, wenn diese Richtlinie wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="63987-132">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="63987-133">**Für Kunden ohne Skype for Business** sind, wenn die Richtlinie wirksam ist, zusätzlich zu den Anrufen zwischen Microsoft Teams-Benutzern nur ausgehende PSTN-Anrufe in Microsoft Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="63987-133">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="63987-134">Sie müssen die Ihren Benutzern zugewiesene Interop-Richtlinie für Microsoft Teams ändern, damit PSTN-Anrufe in Microsoft Teams empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="63987-134">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="63987-135">Für Benutzer, für die Telefonsystem- und Anrufplanlizenzen zur Verwendung mit Skype for Business Online bereitgestellt sind und für die die standardmäßige globale Interop-Richtlinie für Microsoft Teams konfiguriert ist, gilt Folgendes. Die Registerkarte „Anrufe“ in Microsoft Teams ist aktiviert, und sie können ausgehende PSTN-Anrufe tätigen, ohne dass Administratoren tätig werden müssen.</span><span class="sxs-lookup"><span data-stu-id="63987-135">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="63987-136">Konfigurieren von Microsoft Teams für den Empfang von eingehenden PSTN-Anrufen</span><span class="sxs-lookup"><span data-stu-id="63987-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="63987-137">Wenn in Teams eingehende PSTN-Anrufe annehmen möchten, müssen Sie Teams als Standardgerät für Anrufe Anwendung durch die Anwendung Teams Upgrade Gruppenrichtlinien mit der entsprechenden Teams Interop-Richtlinie, die festlegt konfigurieren `CallingDefaultClient` Parameter Teams.</span><span class="sxs-lookup"><span data-stu-id="63987-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63987-138">Wir empfehlen, diese Konfiguration zunächst auf eine Gruppe von Benutzern anzuwenden. Dann können sich diese Benutzer mit den nützlichen neuen Anruffunktionen in Microsoft Teams vertraut machen, bevor Sie allgemeinere oder die ganze Organisation betreffende Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="63987-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="63987-139">Wenn Sie weiterhin der Richtlinie der Vorversion Upgrade Teams verwenden auswählen, verwenden Sie die folgenden vorkonfigurierte Teams Interop-Richtlinie eingehenden PSTN-Anrufe zu Teams weiterleiten:</span><span class="sxs-lookup"><span data-stu-id="63987-139">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="63987-140">Wenn Sie die aktualisierte Teams Richtlinie Upgrade verwenden, müssen Sie TeamsOnly Modus, die Benutzern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="63987-140">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="63987-141">Die oben gezeigte Richtlinie legt die folgenden Verhaltensweisen fest:</span><span class="sxs-lookup"><span data-stu-id="63987-141">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="63987-142">**Für bestehende Skype for Business-Kunden** leitet diese Richtlinie eingehende Anrufe an Microsoft Teams um.</span><span class="sxs-lookup"><span data-stu-id="63987-142">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="63987-143">Dies gilt sowohl für VoIP-Anrufe (aus Microsoft Teams und Skype for Business) als auch für PSTN-Anrufe.</span><span class="sxs-lookup"><span data-stu-id="63987-143">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="63987-144">**Kunden ohne Skype for Business** empfangen, wenn die Richtlinie wirksam ist, PSTN-Anrufe in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="63987-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="63987-145">Zurzeit wirkt sich das Ändern von `CallingDefaultClient` in Microsoft Teams auch auf Anrufe an Skype for Business-IP-Telefone aus.</span><span class="sxs-lookup"><span data-stu-id="63987-145">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="63987-146">Eingehende Anrufe werden nicht an den Telefonen empfangen und klingeln nur bei Microsoft Teams-Clients.</span><span class="sxs-lookup"><span data-stu-id="63987-146">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="63987-147">Informationen zur Unterstützung von vorhandenen zertifizierten SIP-Telefone finden Sie in der [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap) .</span><span class="sxs-lookup"><span data-stu-id="63987-147">Please consult the [Microsoft 365 Roadmap](https://aka.ms/O365Roadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="63987-148">Zum Konfigurieren von Benutzern Empfang von PSTN-Anrufe in Teams</span><span class="sxs-lookup"><span data-stu-id="63987-148">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="63987-149">Bei Verwendung der Richtlinie der Vorversion Upgrade Teams gelten Sie die Teams Interop-Richtlinie wie oben über Skype für Business remote Windows PowerShell-Sitzung zum Umleiten von Anrufen an Teams beschrieben:</span><span class="sxs-lookup"><span data-stu-id="63987-149">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="63987-150">Wenn Sie entscheiden, TeamsOnly-Modus verwenden, können Sie die Benutzermodus Koexistenz zu TeamsOnly über Microsoft-Teams & Skype für Business-Verwaltungskonsole oder über Skype für Business remote Windows PowerShell-Sitzung zum Umleiten von Anrufen an Teams ändern:</span><span class="sxs-lookup"><span data-stu-id="63987-150">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="63987-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63987-151">See also</span></span>
[<span data-ttu-id="63987-152">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="63987-152">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="63987-153">Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="63987-153">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="63987-154">Praktische Anleitungen für Telefonsysteme mit Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63987-154">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="63987-155">PowerShell-Cmdlet-Referenz für Skype for Business</span><span class="sxs-lookup"><span data-stu-id="63987-155">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="63987-156">PowerShell-Cmdlet-Referenz für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63987-156">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
