---
title: "Schnellstarthandbuch – Konfigurieren von Anrufplänen in Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: lolaj
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
description: "Schnellstarthandbuch für das Konfigurieren von Anrufplänen in Microsoft Teams"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: bf2aa9b698516882ed5e48b4d9b7b639b74af40e
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2017
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="c9fad-103">Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9fad-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="c9fad-104">Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.</span><span class="sxs-lookup"><span data-stu-id="c9fad-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="c9fad-105">Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).</span><span class="sxs-lookup"><span data-stu-id="c9fad-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="c9fad-106">Wir empfehlen, bei der Planung und Umsetzung eines erfolgreichen Rollouts neben diesem Schnellstarthandbuch unsere [praktischen Anleitungen](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) und [FastTrack](https://aka.ms/cloudvoice) zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="c9fad-106">We recommend that, in parallel with this quick-start guide, you use our [practical guidance](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="c9fad-107">Durch Hinzufügen von Anrufplänen – einer Office 365-Funktion, die von Skype for Business unterstützt wird – können Sie jetzt mit Microsoft Teams Festnetz- und Mobiltelefone über das Telefonfestnetz (Public Switched Telephone Network, PSTN) anrufen oder von diesen angerufen werden.</span><span class="sxs-lookup"><span data-stu-id="c9fad-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Anrufe in Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="c9fad-109">Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9fad-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="c9fad-110">Um die Registerkarte **Anrufe** in Microsoft Teams zu aktivieren und Ihren Benutzern das Tätigen und Empfangen von PSTN-Anrufen zu ermöglichen, müssen Sie Benutzer für das Telefonsystem und Anrufpläne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c9fad-110">To enable the **Calls** tab in Teams and allow your users to make and receive PSTN calls, you will need provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="c9fad-111">Eine entsprechende Anleitung finden Sie unter [Einrichten von Anrufplänen](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span><span class="sxs-lookup"><span data-stu-id="c9fad-111">To learn how to set this up, read [Set up Calling Plans](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9fad-112">Beachten Sie beim Konfigurieren von Anrufplänen in Microsoft Teams die folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="c9fad-112">Before configuring Calling Plans in Teams, please be aware of the following limitations:</span></span>
> * <span data-ttu-id="c9fad-113">**Hybridtelefonie wird in Microsoft Teams nicht unterstützt.** – Hybridtelefonie wird zurzeit in Microsoft Teams nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9fad-113">**Hybrid Voice is not supported in Teams** - Hybrid Voice is currently not supported in Teams.</span></span> <span data-ttu-id="c9fad-114">Kunden, die Hybridtelefonie nutzen, sollten die Richtlinien für den Empfang von Anrufen in Microsoft Teams nicht ändern, da dies zu Dienstunterbrechungen führt.</span><span class="sxs-lookup"><span data-stu-id="c9fad-114">Hybrid Voice customers are not advised to change any of the policies to receive calls in Teams, as this will cause service interruptions.</span></span>
> * <span data-ttu-id="c9fad-115">**Partneranrufe werden in Microsoft Teams nicht unterstützt.** – Partneranrufe (Anrufe zwischen Mandanten/Firmen) werden zurzeit in Microsoft Teams nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9fad-115">**Federated calling is not supported in Teams** - Federated calling (calling between tenants/companies) is currently not supported in Teams.</span></span> <span data-ttu-id="c9fad-116">Solange die Unterstützung in Microsoft Teams nicht vorhanden ist, werden Partneranrufe immer an Skype for Business weitergeleitet. Dabei spielt es keine Rolle, wie Sie die Anruffunktion konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c9fad-116">Federated calls will always be routed to Skype for Business regardless of how you configure calling, until it's supported in Teams.</span></span>

## <a name="teams-interop-policy-configuration"></a><span data-ttu-id="c9fad-117">Konfiguration der Interop-Richtlinie für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9fad-117">Teams interop policy configuration</span></span>
<span data-ttu-id="c9fad-118">Um in Microsoft Teams Anrufe empfangen zu können, müssen Sie die Interop-Richtlinie für Microsoft Teams aktualisieren. Verwenden Sie dazu eine Windows PowerShell-Sitzung und die [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype)-Cmdlets für Skype for Business, um Anrufe an Microsoft Teams umzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c9fad-118">To enable Teams to begin receiving calls, you'll need to update Teams interop policy, using a remote Windows PowerShell session with the Skype for Business [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) cmdlets, to redirect calls to Teams.</span></span> <span data-ttu-id="c9fad-119">Weitere Informationen zur Interop-Richtlinie für Microsoft Teams finden Sie unter [Interoperabilität von Microsoft Teams und Skype for Business](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span><span class="sxs-lookup"><span data-stu-id="c9fad-119">For more information about Teams interop policy, see [Microsoft Teams and Skype for Business Interoperability](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).</span></span>

> [!TIP]
> <span data-ttu-id="c9fad-120">Die benötigten PowerShell-Cmdlets finden Sie, indem Sie „CsTeamsInteropPolicy“ in das Feld **Filter** in der [Dokumentation zu den PowerShell-Cmdlets für Skype for Business](https://docs.microsoft.com/powershell/module/skype) eingeben.</span><span class="sxs-lookup"><span data-stu-id="c9fad-120">To find the PowerShell cmdlets you need, type "CsTeamsInteropPolicy" in the **Filter** box in the [Skype for Business PowerShell cmdlet documentation](https://docs.microsoft.com/powershell/module/skype).</span></span>

### <a name="default-teams-interop-policy"></a><span data-ttu-id="c9fad-121">Interop-Standardrichtlinie für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9fad-121">Default Teams interop policy</span></span>
<span data-ttu-id="c9fad-122">Microsoft Teams enthält eine Standardrichtlinienkonfiguration, die sicherstellen soll, dass vorhandene Geschäftsworkflows bei der Bereitstellung von Microsoft Teams nicht gestört werden.</span><span class="sxs-lookup"><span data-stu-id="c9fad-122">Teams has a default policy configuration designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="c9fad-123">VoIP-, PSTN- und Partneranrufe an Ihre Benutzer werden standardmäßig weiterhin an Skype for Business weitergeleitet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe in Microsoft Teams zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c9fad-123">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span> <span data-ttu-id="c9fad-124">Dadurch werden unbeabsichtigte Unterbrechungen der VoIP-Dienste vermieden, wenn Sie mit dem Pilotprojekt und der Bereitstellung von Microsoft Teams beginnen.</span><span class="sxs-lookup"><span data-stu-id="c9fad-124">This ensures that there are no unintended interruptions in voice services as you start to pilot and deploy Teams.</span></span>

<span data-ttu-id="c9fad-125">So sieht die Standardkonfiguration der Interop-Richtlinie für Microsoft Teams aus:</span><span class="sxs-lookup"><span data-stu-id="c9fad-125">Teams interop policy has the following default configuration:</span></span>

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="c9fad-126">Die Standardkonfiguration sieht die folgenden Verhaltensweisen vor:</span><span class="sxs-lookup"><span data-stu-id="c9fad-126">The behaviors of the default configuration are the following:</span></span>
* <span data-ttu-id="c9fad-127">**Für bestehende Skype for Business-Kunden** soll die Richtlinie sicherstellen, dass Skype for Business-Anrufe an Skype for Business und Microsoft Teams-Anrufe an Microsoft Teams geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c9fad-127">**For existing Skype for Business customers**, this policy is designed to ensure that Skype for Business calls are directed to Skype for Business, and Teams calls are directed to Teams.</span></span> <span data-ttu-id="c9fad-128">PSTN-Anrufe und Partneranrufe werden an Skype for Business geleitet, wenn diese Richtlinie wirksam ist.</span><span class="sxs-lookup"><span data-stu-id="c9fad-128">PSTN and federated calls will be directed to Skype for Business when this policy is in effect.</span></span>
* <span data-ttu-id="c9fad-129">**Für Kunden ohne Skype for Business** sind, wenn die Richtlinie wirksam ist, zusätzlich zu den Anrufen zwischen Microsoft Teams-Benutzern nur ausgehende PSTN-Anrufe in Microsoft Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c9fad-129">**For customers without Skype for Business**, when in effect, in addition to calls among Teams users, only outbound PSTN calling will be available in Teams.</span></span> <span data-ttu-id="c9fad-130">Sie müssen die Ihren Benutzern zugewiesene Interop-Richtlinie für Microsoft Teams ändern, damit PSTN-Anrufe in Microsoft Teams empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="c9fad-130">You will need to alter the Teams interop policy assigned to your users to receive PSTN calls in Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="c9fad-131">Für Benutzer, für die Telefonsystem- und Anrufplanlizenzen zur Verwendung mit Skype for Business Online bereitgestellt sind und für die die standardmäßige globale Interop-Richtlinie für Microsoft Teams konfiguriert ist, gilt Folgendes. Die Registerkarte „Anrufe“ in Microsoft Teams ist aktiviert, und sie können ausgehende PSTN-Anrufe tätigen, ohne dass Administratoren tätig werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c9fad-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online, and configured with the default global Teams interop policy, will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a><span data-ttu-id="c9fad-132">Konfigurieren von Microsoft Teams für die Verwendung der Standardrichtlinie</span><span class="sxs-lookup"><span data-stu-id="c9fad-132">How to configure Teams to use the default policy</span></span>
<span data-ttu-id="c9fad-133">Die globale Interop-Richtlinie für Microsoft Teams wird standardmäßig auf alle Benutzer in Ihrem Mandanten angewendet. Sie ist mit den oben beschriebenen Standardeinstellungen konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c9fad-133">By default, global Teams interop policy is applied to all users in your tenant, and it is configured with the default settings as described above.</span></span> <span data-ttu-id="c9fad-134">Wenn Sie aus einem bestimmten Grund Ihren Benutzern andere Richtlinien zugewiesen haben und die Standardeinstellung wiederherstellen möchten, müssen Sie die globale Interop-Richtlinie für Microsoft Teams über eine Windows PowerShell-Remotesitzung mit Skype for Business anwenden:</span><span class="sxs-lookup"><span data-stu-id="c9fad-134">If for some reason you have granted different policies to your users and would like to revert to the default setting, you will need to apply the global Teams interop policy via Skype for Business remote Windows PowerShell session:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> <span data-ttu-id="c9fad-135">Es ist zwar möglich, die globale Interop-Richtlinie für Microsoft Teams zu ändern, sodass nicht die Standardwerte verwendet werden, aber wir raten dringend davon ab.</span><span class="sxs-lookup"><span data-stu-id="c9fad-135">While it is possible to modify the global Teams interop policy from the default values, we strongly advise against it.</span></span> 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a><span data-ttu-id="c9fad-136">Konfigurieren von Microsoft Teams für den Empfang von eingehenden PSTN-Anrufen</span><span class="sxs-lookup"><span data-stu-id="c9fad-136">Configuring Teams to receive inbound PSTN calls</span></span>
<span data-ttu-id="c9fad-137">Um eingehende PSTN-Anrufe in Microsoft Teams zu empfangen, müssen Sie Microsoft Teams als Standardanwendung für Anrufe konfigurieren. Dazu wenden Sie die Interop-Richtlinie für Microsoft Teams an und legen dabei den Parameter `CallingDefaultClient` auf „Teams“ (Microsoft Teams) fest.</span><span class="sxs-lookup"><span data-stu-id="c9fad-137">To receive inbound PSTN calls in Teams, you will need to configure Teams as the default calling application by applying Teams interop policy with `CallingDefaultClient` parameter set to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c9fad-138">Wir empfehlen, diese Konfiguration zunächst auf eine Gruppe von Benutzern anzuwenden. Dann können sich diese Benutzer mit den nützlichen neuen Anruffunktionen in Microsoft Teams vertraut machen, bevor Sie allgemeinere oder die ganze Organisation betreffende Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c9fad-138">We recommend that you apply this configuration to an initial set of users to explore these exciting new calling capabilities in Teams prior to making wider or organization-level changes.</span></span>

<span data-ttu-id="c9fad-139">Mit der folgenden vorkonfigurierten Interop-Richtlinie für Microsoft Teams können Sie eingehende PSTN-Anrufe an Microsoft Teams weiterleiten:</span><span class="sxs-lookup"><span data-stu-id="c9fad-139">Consider using the following preconfigured Teams interop policy to route inbound PSTN calling to Teams:</span></span>

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

<span data-ttu-id="c9fad-140">Die oben gezeigte Richtlinie legt die folgenden Verhaltensweisen fest:</span><span class="sxs-lookup"><span data-stu-id="c9fad-140">The behaviors of the policy above are the following:</span></span>
* <span data-ttu-id="c9fad-141">**Für bestehende Skype for Business-Kunden** leitet diese Richtlinie eingehende Anrufe an Microsoft Teams um.</span><span class="sxs-lookup"><span data-stu-id="c9fad-141">**For existing Skype for Business customers**, this policy is designed to redirect incoming calls to Teams.</span></span> <span data-ttu-id="c9fad-142">Dies gilt sowohl für VoIP-Anrufe (aus Microsoft Teams und Skype for Business) als auch für PSTN-Anrufe.</span><span class="sxs-lookup"><span data-stu-id="c9fad-142">This includes both VoIP (from Teams and Skype for Business) and PSTN calls.</span></span> <span data-ttu-id="c9fad-143">Partneranrufe werden weiterhin in Skype for Business empfangen.</span><span class="sxs-lookup"><span data-stu-id="c9fad-143">Federated calls will continue to be received in Skype for Business.</span></span> 
* <span data-ttu-id="c9fad-144">**Kunden ohne Skype for Business** empfangen, wenn die Richtlinie wirksam ist, PSTN-Anrufe in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c9fad-144">**For customers without Skype for Business**, when in effect, PSTN calls will be received in Teams.</span></span> <span data-ttu-id="c9fad-145">Partneranrufe werden zurzeit in Microsoft Teams **nicht unterstützt**.</span><span class="sxs-lookup"><span data-stu-id="c9fad-145">Federated calling is currently **not supported** in Teams.</span></span>

> [!WARNING]
> <span data-ttu-id="c9fad-146">Zurzeit wirkt sich das Ändern von `CallingDefaultClient` in Microsoft Teams auch auf Anrufe an Skype for Business-IP-Telefone aus.</span><span class="sxs-lookup"><span data-stu-id="c9fad-146">Currently, changing `CallingDefaultClient` to Teams will also affect calls to Skype for Business IP phones.</span></span> <span data-ttu-id="c9fad-147">Eingehende Anrufe werden nicht an den Telefonen empfangen und klingeln nur bei Microsoft Teams-Clients.</span><span class="sxs-lookup"><span data-stu-id="c9fad-147">Incoming calls will not be received on the phones and will only ring Teams clients.</span></span> <span data-ttu-id="c9fad-148">Weitere Informationen zu vorhandenen zertifizierten SIP-Telefonen finden Sie unter [Von Skype for Business zu Microsoft Teams: Roadmap der Funktionen](https://aka.ms/skype2teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="c9fad-148">Please consult the [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) for information about support for existing certified SIP phones.</span></span>

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a><span data-ttu-id="c9fad-149">Konfigurieren von Microsoft Teams für den Empfang von PSTN-Anrufen</span><span class="sxs-lookup"><span data-stu-id="c9fad-149">How to configure Teams to receive PSTN calls</span></span>
<span data-ttu-id="c9fad-150">Wenden Sie die Interop-Richtlinie für Microsoft Teams wie oben beschrieben über eine Windows PowerShell-Remotesitzung mit Skype for Business an, um Anrufe an Microsoft Teams umzuleiten:</span><span class="sxs-lookup"><span data-stu-id="c9fad-150">Apply the Teams interop policy as described above via Skype for Business remote Windows PowerShell session to redirect calls to Teams:</span></span>

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a><span data-ttu-id="c9fad-151">Konfigurieren von Microsoft Teams, um Benutzern das Ändern ihrer bevorzugten Anrufanwendung zu ermöglichen</span><span class="sxs-lookup"><span data-stu-id="c9fad-151">Configuring Teams to allow users to change their preferred calling experience</span></span>
<span data-ttu-id="c9fad-152">Wenn Sie es den Benutzern ermöglichen möchten, selbst über ihre bevorzugte Anrufanwendung zu entscheiden (Empfang von Anrufen in Microsoft Teams oder in Skype for Business), müssen Sie eine benutzerdefinierte Interop-Richtlinie für Microsoft Teams erstellen, die den Parameter `AllowEndUserClientOverride` aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c9fad-152">To let users to make their own decision over the preferred calling experience, whether to receive calls in Teams or Skype for Business, you need to create a custom Teams interop policy that enables `AllowEndUserClientOverride` parameter.</span></span>

<span data-ttu-id="c9fad-153">Das folgende Beispiel zeigt, wie Sie in der Interop-Richtlinie für Microsoft Teams die Auswahl der bevorzugten Anrufanwendung durch die Benutzer aktivieren:</span><span class="sxs-lookup"><span data-stu-id="c9fad-153">The following is the example of Teams interop policy to enable user choice of the preferred calling experience:</span></span>

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

<span data-ttu-id="c9fad-154">Wenn Sie diese Richtlinie auf die Benutzer angewendet haben, ist im Microsoft Teams-Client die Option zum Ändern der bevorzugten Anrufanwendung verfügbar, und die Benutzer können die Änderungen selbst vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c9fad-154">Once this custom policy is applied to the users, the option to change the preferred calling application will be available in Teams client for users to make the changes themselves.</span></span>

![Option „Bevorzugte Anrufanwendung“](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> <span data-ttu-id="c9fad-156">Wir empfehlen, diese Konfiguration zunächst auf eine Gruppe von Benutzern anzuwenden, bevor Sie allgemeinere oder die ganze Organisation betreffende Änderungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="c9fad-156">It is recommended that you apply this configuration to an initial set of users prior to making wider or organization level changes.</span></span>

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a><span data-ttu-id="c9fad-157">Erstellen und Anwenden der benutzerdefinierten Interop-Richtlinie für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9fad-157">How to create and apply the custom Teams interop policy</span></span>
<span data-ttu-id="c9fad-158">Um die benutzerdefinierte Interop-Richtlinie für Microsoft Teams wie oben beschrieben über eine Windows PowerShell-Remotesitzung mit Skype for Business zu erstellen, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="c9fad-158">To create the custom Teams interop policy as described above via Skype for Business remote Windows PowerShell session, perform the following:</span></span>

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a><span data-ttu-id="c9fad-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9fad-159">See also</span></span>
[<span data-ttu-id="c9fad-160">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="c9fad-160">Set up Calling Plans</span></span>](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[<span data-ttu-id="c9fad-161">Interoperabilität von Microsoft Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c9fad-161">Microsoft Teams and Skype for Business Interoperability</span></span>](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[<span data-ttu-id="c9fad-162">Praktische Anleitungen für Telefonsysteme mit Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9fad-162">Practical Guidance for Phone System with Calling Plans in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[<span data-ttu-id="c9fad-163">PowerShell-Cmdlet-Referenz für Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c9fad-163">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

[<span data-ttu-id="c9fad-164">PowerShell-Cmdlet-Referenz für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c9fad-164">PowerShell cmdlet reference for Teams</span></span>](https://docs.microsoft.com/powershell/module/teams)
