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
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: eea3c6ed4084648877fd31b84bb9cdea26986565
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23856099"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="5a1a0-103">Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a1a0-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="5a1a0-104">Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="5a1a0-105">Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).</span><span class="sxs-lookup"><span data-stu-id="5a1a0-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="5a1a0-106">Wir empfehlen, bei der Planung und Umsetzung eines erfolgreichen Rollouts neben diesem Schnellstarthandbuch unsere [praktischen Anleitungen](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) und [FastTrack](https://aka.ms/cloudvoice) zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="5a1a0-107">Durch Hinzufügen von Anrufplänen – einer Office 365-Funktion, die von Skype for Business unterstützt wird – können Sie jetzt mit Microsoft Teams Festnetz- und Mobiltelefone über das Telefonfestnetz (Public Switched Telephone Network, PSTN) anrufen oder von diesen angerufen werden.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Anrufe in Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="5a1a0-109">Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a1a0-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="5a1a0-110">Um die Registerkarte **Anrufe** in Microsoft Teams zu aktivieren und Ihren Benutzern das Tätigen und Empfangen von PSTN-Anrufen zu ermöglichen, müssen Sie Benutzer für das Telefonsystem und Anrufpläne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="5a1a0-111">Eine entsprechende Anleitung finden Sie unter [Einrichten von Anrufplänen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="5a1a0-111">To learn how to set this up, read [Set up Calling Plans](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans).</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="5a1a0-112">Konfiguration der Interop-Richtlinie für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a1a0-112">Teams interop policy configuration</span></span>
<span data-ttu-id="5a1a0-113">Um Teams beginnen annehmen von Anrufen zu aktivieren, müssen Sie zum Aktualisieren des Teams und Teams Interop-Richtlinie, über [Microsoft-Teams & Skype für Business-Verwaltungskonsole](https://aka.ms/teamsadmincenter) oder mithilfe von remote Windows PowerShell-Sitzung mit der Skype für Unternehmen [ `*-CsTeamsUpgradePolicy`und `*-CsTeamsInteropPolicy` ](https://docs.microsoft.com/powershell/module/skype) -Cmdlets zum Umleiten von Anrufen an Teams.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-113">To enable Teams to begin receiving calls, you'll need to update Teams upgrade policy and Teams interop policy, using [Microsoft Teams & Skype for Business Admin Center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsUpgradePolicy` and `*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span>

<span data-ttu-id="5a1a0-114">Weitere Informationen zu Upgrades Teams und Teams Interop-Richtlinie finden Sie unter [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="5a1a0-114">For more information about Teams upgrade policy and Teams interop policy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype).</span></span>

> [!TIP]
> <span data-ttu-id="5a1a0-115">Um den PowerShell-Cmdlets zu suchen, die Sie benötigen, geben Sie "CsTeamsUpgradePolicy" oder "CsTeamsInteropPolicy" im Feld **Filter** in der [Skype für Business PowerShell-Cmdlet-Dokumentation](https://docs.microsoft.com/powershell/module/skype).</span><span class="sxs-lookup"><span data-stu-id="5a1a0-115">To find the PowerShell cmdlets you need, type "CsTeamsUpgradePolicy" or "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-upgrade-and-interop-policies"></a><span data-ttu-id="5a1a0-116">Standard-Teams Upgrade und Interop-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="5a1a0-116">Default Teams upgrade and interop policies</span></span>
<span data-ttu-id="5a1a0-117">Microsoft Teams enthält eine Standardrichtlinienkonfiguration, die sicherstellen soll, dass vorhandene Geschäftsworkflows bei der Bereitstellung von Microsoft Teams nicht gestört werden.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-117">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="5a1a0-118">VoIP-, PSTN- und Partneranrufe an Ihre Benutzer werden standardmäßig weiterhin an Skype for Business weitergeleitet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe in Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-118">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="5a1a0-119">Dadurch werden unbeabsichtigte Unterbrechungen der VoIP-Dienste vermieden, wenn Sie mit dem Pilotprojekt und der Bereitstellung von Microsoft Teams beginnen.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-119">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="5a1a0-120">Upgrade Richtlinie in der Standardeinstellung ist bei legacy-Modus, die berücksichtigt werden Teams Interop-Richtlinie, um festzustellen, wo Chats und Anrufe weitergeleitet werden – stehen aufbewahrt Teams Teams oder Skype für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-120">Teams upgrade policy by default is kept at legacy mode that will honor Teams interop policy to determine where chats and calls are to be routed--Teams or Skype for Business.</span></span>

> [!NOTE]
> <span data-ttu-id="5a1a0-121">Die Verhalten des Teams aktualisieren Richtlinie und Teams Interop-Richtlinie wird bald ändern, wie beschrieben in [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="5a1a0-121">The behaviors of Teams upgrade policy and Teams interop policy will soon change as described in [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="5a1a0-122">So sieht die Standardkonfiguration der Interop-Richtlinie für Microsoft Teams aus:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-122">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="5a1a0-123">Die Standardkonfiguration sieht die folgenden Verhaltensweisen vor:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-123">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="5a1a0-124">**Für bestehende Skype for Business-Kunden** soll die Richtlinie sicherstellen, dass Skype for Business-Anrufe an Skype for Business und Microsoft Teams-Anrufe an Microsoft Teams geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-124">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="5a1a0-125">PSTN-Anrufe und Partneranrufe werden an Skype for Business geleitet, wenn diese Richtlinie wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-125">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="5a1a0-126">**Für Kunden ohne Skype for Business** sind, wenn die Richtlinie wirksam ist, zusätzlich zu den Anrufen zwischen Microsoft Teams-Benutzern nur ausgehende PSTN-Anrufe in Microsoft Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-126">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="5a1a0-127">Sie müssen die Ihren Benutzern zugewiesene Interop-Richtlinie für Microsoft Teams ändern, damit PSTN-Anrufe in Microsoft Teams empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-127">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="5a1a0-128">Für Benutzer, für die Telefonsystem- und Anrufplanlizenzen zur Verwendung mit Skype for Business Online bereitgestellt sind und für die die standardmäßige globale Interop-Richtlinie für Microsoft Teams konfiguriert ist, gilt Folgendes. Die Registerkarte „Anrufe“ in Microsoft Teams ist aktiviert, und sie können ausgehende PSTN-Anrufe tätigen, ohne dass Administratoren tätig werden müssen.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-128">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="5a1a0-129">Konfigurieren von Microsoft Teams für den Empfang von eingehenden PSTN-Anrufen</span><span class="sxs-lookup"><span data-stu-id="5a1a0-129">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="5a1a0-130">Wenn in Teams eingehende PSTN-Anrufe annehmen möchten, müssen Sie Teams als Standardgerät für Anrufe Anwendung durch die Anwendung Teams Upgrade Gruppenrichtlinien mit der entsprechenden Teams Interop-Richtlinie, die festlegt konfigurieren `CallingDefaultClient` Parameter Teams.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-130">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams upgrade policy with the corresponding Teams interop policy that sets `CallingDefaultClient` parameter to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5a1a0-131">Wir empfehlen, diese Konfiguration zunächst auf eine Gruppe von Benutzern anzuwenden. Dann können sich diese Benutzer mit den nützlichen neuen Anruffunktionen in Microsoft Teams vertraut machen, bevor Sie allgemeinere oder die ganze Organisation betreffende Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-131">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="5a1a0-132">Wenn Sie weiterhin der Richtlinie der Vorversion Upgrade Teams verwenden auswählen, verwenden Sie die folgenden vorkonfigurierte Teams Interop-Richtlinie eingehenden PSTN-Anrufe zu Teams weiterleiten:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-132">If you choose to continue to use the legacy Teams upgrade policy, use the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="5a1a0-133">Wenn Sie die aktualisierte Teams Richtlinie Upgrade verwenden, müssen Sie TeamsOnly Modus, die Benutzern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-133">If you choose to use the updated Teams upgrade policy, you need to assign TeamsOnly mode to your users.</span></span>

<span data-ttu-id="5a1a0-134">Die oben gezeigte Richtlinie legt die folgenden Verhaltensweisen fest:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-134">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="5a1a0-135">**Für bestehende Skype for Business-Kunden** leitet diese Richtlinie eingehende Anrufe an Microsoft Teams um.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-135">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="5a1a0-136">Dies gilt sowohl für VoIP-Anrufe (aus Microsoft Teams und Skype for Business) als auch für PSTN-Anrufe.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-136">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> 
* <span data-ttu-id="5a1a0-137">**Kunden ohne Skype for Business** empfangen, wenn die Richtlinie wirksam ist, PSTN-Anrufe in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-137">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="5a1a0-138">Zurzeit wirkt sich das Ändern von `CallingDefaultClient` in Microsoft Teams auch auf Anrufe an Skype for Business-IP-Telefone aus.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-138">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="5a1a0-139">Eingehende Anrufe werden nicht an den Telefonen empfangen und klingeln nur bei Microsoft Teams-Clients.</span><span class="sxs-lookup"><span data-stu-id="5a1a0-139">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="5a1a0-140">Weitere Informationen zu vorhandenen zertifizierten SIP-Telefonen finden Sie unter [Von Skype for Business zu Microsoft Teams: Roadmap der Funktionen](https://aka.ms/skype2teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="5a1a0-140">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-users-to-receive-pstn-calls-in-teams"></a><span data-ttu-id="5a1a0-141">Zum Konfigurieren von Benutzern Empfang von PSTN-Anrufe in Teams</span><span class="sxs-lookup"><span data-stu-id="5a1a0-141">How to configure users to receive PSTN calls in Teams</span></span>
<span data-ttu-id="5a1a0-142">Bei Verwendung der Richtlinie der Vorversion Upgrade Teams gelten Sie die Teams Interop-Richtlinie wie oben über Skype für Business remote Windows PowerShell-Sitzung zum Umleiten von Anrufen an Teams beschrieben:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-142">When using the legacy Teams upgrade policy, apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

<span data-ttu-id="5a1a0-143">Wenn Sie entscheiden, TeamsOnly-Modus verwenden, können Sie die Benutzermodus Koexistenz zu TeamsOnly über Microsoft-Teams & Skype für Business-Verwaltungskonsole oder über Skype für Business remote Windows PowerShell-Sitzung zum Umleiten von Anrufen an Teams ändern:</span><span class="sxs-lookup"><span data-stu-id="5a1a0-143">If you choose to use TeamsOnly mode, you can change the user's coexistence mode to TeamsOnly via Microsoft Teams & Skype for Business Admin Center, or via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName tag:UpgradeToTeams -Identity user@contoso.com
    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="see-also"></a><span data-ttu-id="5a1a0-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a1a0-144">See also</span></span>
[<span data-ttu-id="5a1a0-145">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="5a1a0-145">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="5a1a0-146">Hinweise zur Migration und Interoperabilität für Organisationen mit Teams zusammen mit Skype für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="5a1a0-146">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="5a1a0-147">Praktische Anleitungen für Telefonsysteme mit Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a1a0-147">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="5a1a0-148">PowerShell-Cmdlet-Referenz für Skype for Business</span><span class="sxs-lookup"><span data-stu-id="5a1a0-148">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="5a1a0-149">PowerShell-Cmdlet-Referenz für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5a1a0-149">Teams PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/teams)
