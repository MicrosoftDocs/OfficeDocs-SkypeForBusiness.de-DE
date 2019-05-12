---
title: Schnellstarthandbuch – Konfigurieren von Anrufplänen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Schnellstarthandbuch für das Konfigurieren von Anrufplänen in Microsoft Teams
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- Teams_ITAdmin_Training
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fd1e9484b522a657a92916815c1ae8940dcc2117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898523"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="ffdc8-103">Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ffdc8-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="ffdc8-104">Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="ffdc8-105">Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).</span><span class="sxs-lookup"><span data-stu-id="ffdc8-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="ffdc8-106">Es wird empfohlen, die gleichzeitig mit diesem Schnellstart-Handbuch, lesen Sie die [Telefonsystem mit Aufrufen plant](calling-plan-landing-page.md) und [schnelle](https://aka.ms/cloudvoice) zur Planung und Laufwerk eine erfolgreiche Einführung.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="ffdc8-107">Durch Hinzufügen von Anrufplänen – einer Office 365-Funktion, die von Skype for Business unterstützt wird – können Sie jetzt mit Microsoft Teams Festnetz- und Mobiltelefone über das Telefonfestnetz (Public Switched Telephone Network, PSTN) anrufen oder von diesen angerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Anrufe in Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="ffdc8-109">Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ffdc8-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="ffdc8-110">Zum Aktivieren der Registerkarte **Anrufe** in Teams benötigen Benutzer 1:1 aktiviert werden, Teams aufrufen und Verwenden von Clientidentität Teams, die 1:1-Teams aufrufen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="ffdc8-111">Weitere Informationen zum Verwalten von 1:1 einwählen, Teams lesen Sie [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ffdc8-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="ffdc8-112">Um zu erfahren, welche Clients aufrufen unterstützen, lesen Sie [Grenzwerte und Spezifikationen für Microsoft-Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="ffdc8-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="ffdc8-113">Derzeit wird Voicemail in der Registerkarte Anrufe nicht verfügbar, wenn der Benutzer für PSTN-Anrufe aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="ffdc8-114">Voraussetzungen für das **Wähltastenfeld** im Teams aktivieren</span><span class="sxs-lookup"><span data-stu-id="ffdc8-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="ffdc8-115">Zum Aktivieren der Registerkarte **Wähltastatur** in Teams und ermöglichen die Benutzer das tätigen und annehmen von PSTN-Anrufe müssen Sie die Bereitstellung von Benutzern für Telefonsystem und plant aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="ffdc8-116">Zum Aufrufen von plant einrichten finden Sie unter [Einrichten von plant aufrufen](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="ffdc8-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="ffdc8-117">Direktes Routing können auch Ihre Benutzerberechtigungen zum tätigen und annehmen von PSTN-Anrufe.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="ffdc8-118">Weitere Informationen zum Einrichten der direkten Routing lesen Sie [Direkten Routing konfigurieren](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="ffdc8-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="ffdc8-119">Verwenden von TeamsUpgradePolicy zum Steuerelement sorgt, in dem Anrufe</span><span class="sxs-lookup"><span data-stu-id="ffdc8-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="ffdc8-120">Administratoren verwenden um zu steuern, ob eingehende Anrufe (und Chats) in Teams oder Skype für Unternehmen sorgt TeamsUpgradePolicy, verwenden entweder [Microsoft-Teams-Verwaltungskonsole](https://aka.ms/teamsadmincenter) oder mithilfe einer Windows PowerShell-Remotesitzung mit der [Skype für Business](https://docs.microsoft.com/powershell/module/skype) Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="ffdc8-121">Die Standardkonfiguration der TeamsUpgradePolicy ist Inseln-Modus, die entworfen wurde, um sicherzustellen, dass diese vorhandenen Business, Workflows nicht während der Bereitstellung Teams unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="ffdc8-122">Standardmäßig werden VoIP, PSTN und Verbundpartner Anrufe an Ihre Benutzer weiterhin an Skype für Unternehmen weitergeleitet werden, bis Sie die Richtlinie so aktivieren eingehenden Anrufe von Teams aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="ffdc8-123">Wenn Empfänger im Modus Inseln sind:</span><span class="sxs-lookup"><span data-stu-id="ffdc8-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="ffdc8-124">Eingehende VOIP ruft diese originated in Skype für Unternehmen immer Flächen, die in der Aufgabenliste des Empfängers Skype für Business-Client.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="ffdc8-125">Eingehende VOIP aufruft, die in Teams Land in Teams, *Wenn der Absender und Empfänger in derselben mandantenorganisation sind*stammt.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="ffdc8-126">Eingehende federated VOIP (unabhängig von der Clientcomputer stammt) und PSTN-immer Anrufe Flächen, die in der Aufgabenliste des Empfängers Skype für Business-Client.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="ffdc8-127">Um sicherzustellen, dass eingehende VoIP- und PSTN-Anrufe immer Land Teams-Client des Benutzers, Aktualisierungsmodus des Benutzers Koexistenz um TeamsOnly werden (d. h. diese Instanz "UpgradeToTeams" von TeamsUpgradePolicy zuordnen.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="ffdc8-128">Weitere Informationen zu Koexistenz Modi und TeamsUpgradePolicy finden Sie unter [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="ffdc8-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="ffdc8-129">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="ffdc8-129">**NOTES**</span></span>
 - <span data-ttu-id="ffdc8-130">Skype für Business IP-Telefone erhält Anrufe, selbst wenn der Benutzer im TeamsOnly Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="ffdc8-131">Benutzer, die mit Telefonsystem und Pläne Aufrufen von Lizenzen für die Verwendung mit Skype für Business Online (z. B. haben sie einen Wert von OnlineVoiceRoutingPolicy zugewiesen wurde), wird die Registerkarte Anrufe in Teams aktiviert haben und ausgehende PSTN-Anrufe von bereitgestellt wurden Teams ohne Administratoren administrative Maßnahmen ergreifen müssen.</span><span class="sxs-lookup"><span data-stu-id="ffdc8-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="ffdc8-132">Zum Konfigurieren von Benutzern Empfang alle eingehenden VoIP- und PSTN-Anrufe in Teams</span><span class="sxs-lookup"><span data-stu-id="ffdc8-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="ffdc8-133">Um sicherzustellen, dass Benutzer in Teams alle eingehenden VoIP- und PSTN-Anrufe empfangen, legen Sie die Benutzermodus Koexistenz auf TeamsOnly in der Verwaltungskonsole von Microsoft-Teams, oder verwenden Sie Skype für Business remote Windows PowerShell-Sitzung TeamsUpgradePolicy wie folgt aktualisiert:</span><span class="sxs-lookup"><span data-stu-id="ffdc8-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="ffdc8-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffdc8-134">See also</span></span>
[<span data-ttu-id="ffdc8-135">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="ffdc8-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="ffdc8-136">Anleitungen zur Migration und Interoperabilität für Organisationen, die Microsoft Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="ffdc8-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="ffdc8-137">Telefonsystem mit dem Aufrufen der Pläne</span><span class="sxs-lookup"><span data-stu-id="ffdc8-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="ffdc8-138">Skype für Referenz Business PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ffdc8-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

