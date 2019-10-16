---
title: Schnellstarthandbuch – Konfigurieren von Anrufplänen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
description: Schnellstarthandbuch für das Konfigurieren von Anrufplänen in Microsoft Teams
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87670ea398150e4895f2d87ccc48f60aba2d1377
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516480"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="f9d52-103">Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9d52-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="f9d52-104">Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.</span><span class="sxs-lookup"><span data-stu-id="f9d52-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="f9d52-105">Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).</span><span class="sxs-lookup"><span data-stu-id="f9d52-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="f9d52-106">Wir empfehlen, dass Sie parallel zu diesem Schnellstarthandbuch das [Telefon System mit Anrufplänen](calling-plan-landing-page.md) und Kurzübersicht lesen [, um einen](https://aka.ms/cloudvoice) erfolgreichen Rollout zu planen und voranzutreiben.</span><span class="sxs-lookup"><span data-stu-id="f9d52-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="f9d52-107">Durch Hinzufügen von Anrufplänen – einer Office 365-Funktion, die von Skype for Business unterstützt wird – können Sie jetzt mit Microsoft Teams Festnetz- und Mobiltelefone über das Telefonfestnetz (Public Switched Telephone Network, PSTN) anrufen oder von diesen angerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f9d52-107">By adding Calling Plans - an Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Screenshot mit der Seite "Kontakte" in Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="f9d52-109">Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f9d52-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="f9d52-110">Um die Registerkarte " **Anrufe** " in Teams zu aktivieren, müssen die Benutzer 1:1-Anrufe in Teams aktiviert haben und einen Teams-Client verwenden, der 1:1 Teams unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f9d52-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="f9d52-111">Informationen zum Verwalten von 1:1-anrufen in Teams finden Sie unter [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f9d52-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="f9d52-112">Wenn Sie wissen möchten, welche Kundenanrufe unterstützen, lesen Sie die [Grenzwerte und Spezifikationen für Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="f9d52-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="f9d52-113">Voicemail steht zurzeit nicht auf der Registerkarte Anrufe zur Verfügung, es sei denn, der Benutzer ist für PSTN-Anrufe aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f9d52-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="f9d52-114">Voraussetzungen für die Aktivierung der **Wähltastatur** in Teams</span><span class="sxs-lookup"><span data-stu-id="f9d52-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="f9d52-115">Um die Registerkarte **Wähltastatur** in Teams zu aktivieren und ihren Benutzern die Möglichkeit zu bieten, PSTN-Anrufe zu tätigen und zu empfangen, müssen Sie die Benutzer für Telefon System-und Anrufpläne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f9d52-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="f9d52-116">Informationen zum Einrichten von Anrufplänen finden Sie unter [Einrichten von Anrufplänen](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="f9d52-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>

> [!NOTE]
> <span data-ttu-id="f9d52-117">Sie können auch die direkte Weiterleitung verwenden, um es Ihren Benutzern zu ermöglichen, PSTN-Anrufe zu tätigen und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="f9d52-117">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="f9d52-118">Informationen zum Einrichten des direkten Routings finden Sie unter [Konfigurieren des direkten Routings](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="f9d52-118">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="f9d52-119">Verwenden von TeamsUpgradePolicy, um zu steuern, wo Anrufe landen</span><span class="sxs-lookup"><span data-stu-id="f9d52-119">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="f9d52-120">Um zu steuern, ob eingehende Anrufe (und Chats) in Teams oder Skype for Business landen, verwenden Administratoren TeamsUpgradePolicy entweder mithilfe von [Microsoft Teams Admin Center](https://aka.ms/teamsadmincenter) oder mithilfe einer Remote-Windows PowerShell-Sitzung mit dem [Skype for Business](https://docs.microsoft.com/powershell/module/skype) Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="f9d52-120">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="f9d52-121">Die Standardkonfiguration von TeamsUpgradePolicy ist der Inseln-Modus, mit dem sichergestellt werden soll, dass vorhandene Geschäftsworkflows während einer Team Bereitstellung nicht unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="f9d52-121">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="f9d52-122">Standardmäßig werden VoIP-, PSTN-und Verbund Anrufe an Ihre Benutzer weiter an Skype for Business weitergeleitet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe an Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f9d52-122">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="f9d52-123">Wenn sich die Empfänger im Inseln-Modus befinden:</span><span class="sxs-lookup"><span data-stu-id="f9d52-123">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="f9d52-124">Eingehende VoIP-Anrufe, die von Skype for Business stammen, landen immer im Skype for Business-Client des Empfängers.</span><span class="sxs-lookup"><span data-stu-id="f9d52-124">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="f9d52-125">Eingehende VoIP-Anrufe, die in Teams entstanden sind, landen in Teams, *Wenn sich Absender und Empfänger im gleichen Mandanten befinden*.</span><span class="sxs-lookup"><span data-stu-id="f9d52-125">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="f9d52-126">Eingehendes Federated-VoIP (unabhängig davon, welcher Client stammt) und PSTN-Anrufe landen immer im Skype for Business-Client des Empfängers.</span><span class="sxs-lookup"><span data-stu-id="f9d52-126">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="f9d52-127">Um sicherzustellen, dass eingehende VoIP-und PSTN-Anrufe immer im Team-Client eines Benutzers landen, aktualisieren Sie den Koexistenzmodus des Benutzers auf TeamsOnly (was bedeutet, weisen Sie ihm die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu.</span><span class="sxs-lookup"><span data-stu-id="f9d52-127">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="f9d52-128">Weitere Informationen zu den Modi für Koexistenz und TeamsUpgradePolicy finden Sie unter [Leitfaden zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="f9d52-128">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="f9d52-129">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="f9d52-129">**NOTES**</span></span>
 - <span data-ttu-id="f9d52-130">Skype for Business-IP-Telefone empfangen Anrufe, auch wenn sich der Benutzer im TeamsOnly-Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="f9d52-130">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="f9d52-131">Benutzer, die über Telefon System-und Anruf Plan Lizenzen für die Nutzung mit Skype for Business Online bereitgestellt wurden (beispielsweise einem Wert von OnlineVoiceRoutingPolicy), haben die Registerkarte "Anrufe" in Teams aktiviert und können ausgehende PSTN-Anrufe von Teams ohne Administratoren müssen administrative Schritte Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="f9d52-131">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="f9d52-132">Konfigurieren von Benutzern für den Empfang aller eingehenden VoIP-und PSTN-Anrufe in Teams</span><span class="sxs-lookup"><span data-stu-id="f9d52-132">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="f9d52-133">Wenn Sie sicherstellen möchten, dass Benutzer alle eingehenden VoIP-und PSTN-Anrufe in Teams empfangen, legen Sie den Koexistenzmodus des Benutzers im Microsoft Teams Admin Center auf TeamsOnly fest, oder verwenden Sie die Skype for Business-Remote-Windows PowerShell-Sitzung, um TeamsUpgradePolicy wie folgt zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="f9d52-133">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="f9d52-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9d52-134">See also</span></span>
[<span data-ttu-id="f9d52-135">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="f9d52-135">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="f9d52-136">Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="f9d52-136">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="f9d52-137">Telefonsystem mit Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="f9d52-137">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="f9d52-138">Skype for Business PowerShell-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="f9d52-138">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

