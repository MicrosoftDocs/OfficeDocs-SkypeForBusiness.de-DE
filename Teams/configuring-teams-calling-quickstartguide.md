---
title: Schnellstarthandbuch – Konfigurieren von Anrufplänen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 8/21/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: rowille, crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Schnellstarthandbuch für die Konfiguration von Anrufplänen in Microsoft Teams, damit Sie eine Reihe von Benutzern in Betrieb nehmen können.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f95a38727a886187e6bf01b0a4ec64e5546b627d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689651"
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a><span data-ttu-id="413b1-103">Schnellstarthandbuch: Konfigurieren von Anrufplänen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="413b1-103">Quick start guide: Configuring Calling Plans in Microsoft Teams</span></span>
==============================================================

<span data-ttu-id="413b1-104">Dieses Handbuch soll Ihnen helfen, eine Gruppe von Benutzern vorzubereiten, damit sie sich mit Anrufplänen in Microsoft Teams vertraut machen können.</span><span class="sxs-lookup"><span data-stu-id="413b1-104">This guide will help you get a set of users up and running so they can explore Calling Plans in Teams.</span></span>

<span data-ttu-id="413b1-105">Lesen Sie die Ankündigung vom 12. Dezember 2017 zu Anrufplänen in Microsoft Teams: [Der nächste Schritt bei der intelligenten Kommunikation: Anrufe in Microsoft Teams](https://aka.ms/ipyqus).</span><span class="sxs-lookup"><span data-stu-id="413b1-105">Read the December 12, 2017, announcement of Calling Plans in Teams: [Intelligent Communications takes the next step with calling in Teams](https://aka.ms/ipyqus)</span></span>

> [!NOTE]
> <span data-ttu-id="413b1-106">Wir empfehlen, dass Sie parallel zu diesem Schnellstarthandbuch das [Telefon System mit Anrufplänen](calling-plan-landing-page.md) und Kurzübersicht lesen [, um einen](https://aka.ms/cloudvoice) erfolgreichen Rollout zu planen und voranzutreiben.</span><span class="sxs-lookup"><span data-stu-id="413b1-106">We recommend that, in parallel with this quick-start guide, you read [Phone System with Calling Plans](calling-plan-landing-page.md) and [FastTrack](https://aka.ms/cloudvoice) to plan and drive a successful rollout.</span></span>

<span data-ttu-id="413b1-107">Durch das Hinzufügen von Anrufplänen – einem Microsoft 365-und Office 365-Feature, das von Skype for Business unterstützt wird – können Sie über das öffentlich geschaltete Telefonnetz (PSTN) jetzt mit Teams Telefonanrufe an Festnetz-und Mobilfunkanschlüsse tätigen und empfangen.</span><span class="sxs-lookup"><span data-stu-id="413b1-107">By adding Calling Plans - a Microsoft 365 and Office 365 feature powered by Skype for Business - you can now use Teams to make and receive phone calls to or from land lines and mobile phones via the public switched telephone network (PSTN).</span></span>

![Screenshot mit der Seite "Kontakte" in Microsoft Teams](media/Calling_in_Teams.png)
## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a><span data-ttu-id="413b1-109">Voraussetzungen für das Aktivieren der Registerkarte **Anrufe** in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="413b1-109">Prerequisites for enabling the **Calls** tab in Teams</span></span>
<span data-ttu-id="413b1-110">Um die Registerkarte " **Anrufe** " in Teams zu aktivieren, müssen die Benutzer 1:1-Anrufe in Teams aktiviert haben und einen Teams-Client verwenden, der 1:1 Teams unterstützt.</span><span class="sxs-lookup"><span data-stu-id="413b1-110">To enable the **Calls** tab in Teams users need to have 1:1 calling enabled in Teams and using a Teams client that supports 1:1 Teams calling.</span></span> <span data-ttu-id="413b1-111">Informationen zum Verwalten von 1:1-anrufen in Teams finden Sie unter [CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="413b1-111">To learn how to manage 1:1 calling in Teams, read [Set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).</span></span> <span data-ttu-id="413b1-112">Wenn Sie wissen möchten, welche Kundenanrufe unterstützen, lesen Sie die [Grenzwerte und Spezifikationen für Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span><span class="sxs-lookup"><span data-stu-id="413b1-112">To learn which clients support calling, please read [Limits and specifications for Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams).</span></span>

> [!NOTE]
> <span data-ttu-id="413b1-113">Voicemail steht zurzeit nicht auf der Registerkarte Anrufe zur Verfügung, es sei denn, der Benutzer ist für PSTN-Anrufe aktiviert.</span><span class="sxs-lookup"><span data-stu-id="413b1-113">Currently, Voicemail will not be available in the Calls tab unless the user is enabled for PSTN calls.</span></span> 

## <a name="prerequisites-for-enabling-the-dial-pad-in-teams"></a><span data-ttu-id="413b1-114">Voraussetzungen für die Aktivierung der **Wähltastatur** in Teams</span><span class="sxs-lookup"><span data-stu-id="413b1-114">Prerequisites for enabling the **Dial Pad** in Teams</span></span>
<span data-ttu-id="413b1-115">Um die Registerkarte **Wähltastatur** in Teams zu aktivieren und ihren Benutzern die Möglichkeit zu bieten, PSTN-Anrufe zu tätigen und zu empfangen, müssen Sie die Benutzer für Telefon System-und Anrufpläne bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="413b1-115">To enable the **Dial Pad** tab in Teams and allow your users to make and receive PSTN calls you will need to provision users for Phone System and Calling Plans.</span></span> <span data-ttu-id="413b1-116">Informationen zum Einrichten von Anrufplänen finden Sie unter [Einrichten von Anrufplänen](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="413b1-116">To learn how to set up Calling Plans, read [Set up Calling Plans](https://docs.microsoft.com/microsoftteams/set-up-calling-plans).</span></span>
<span data-ttu-id="413b1-117">Darüber hinaus müssen Sie für Teams nur Benutzer sicherstellen, dass in der Anrufrichtlinie für Teams "private Anrufe zulassen" aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="413b1-117">Additionally, for Teams only users, you must ensure that "Allow private calling" is enabled in the Teams calling policy.</span></span> <span data-ttu-id="413b1-118">Weitere Informationen finden Sie unter [Verwalten von Teams während des Übergangs zum neuen Microsoft Teams Admin Center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) .</span><span class="sxs-lookup"><span data-stu-id="413b1-118">See [Manage Teams during the transition to the new Microsoft Teams admin center](https://docs.microsoft.com/microsoftteams/manage-teams-skypeforbusiness-admin-center) for more information.</span></span>
> [!NOTE]
> <span data-ttu-id="413b1-119">Sie können auch die direkte Weiterleitung verwenden, um es Ihren Benutzern zu ermöglichen, PSTN-Anrufe zu tätigen und zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="413b1-119">You can also use Direct Routing to allow your users to make and receive PSTN calls.</span></span> <span data-ttu-id="413b1-120">Informationen zum Einrichten des direkten Routings finden Sie unter [Konfigurieren des direkten Routings](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span><span class="sxs-lookup"><span data-stu-id="413b1-120">To learn how to set up Direct Routing, read [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure).</span></span>

## <a name="using-teamsupgradepolicy-to-control-where-calls-land"></a><span data-ttu-id="413b1-121">Verwenden von TeamsUpgradePolicy, um zu steuern, wo Anrufe landen</span><span class="sxs-lookup"><span data-stu-id="413b1-121">Using TeamsUpgradePolicy to control where calls land</span></span>
<span data-ttu-id="413b1-122">Um zu steuern, ob eingehende Anrufe (und Chats) in Teams oder Skype for Business landen, verwenden Administratoren TeamsUpgradePolicy entweder mithilfe von [Microsoft Teams Admin Center](https://aka.ms/teamsadmincenter) oder mithilfe einer Remote-Windows PowerShell-Sitzung mit den [Skype for Business](https://docs.microsoft.com/powershell/module/skype) -Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="413b1-122">To control whether incoming calls (and chats) land in Teams or Skype for Business, administrators use TeamsUpgradePolicy, using either [Microsoft Teams admin center](https://aka.ms/teamsadmincenter) or using a remote Windows PowerShell session with the [Skype for Business](https://docs.microsoft.com/powershell/module/skype) cmdlets.</span></span>


<span data-ttu-id="413b1-123">Die Standardkonfiguration von TeamsUpgradePolicy ist der Inseln-Modus, mit dem sichergestellt werden soll, dass vorhandene Geschäftsworkflows während einer Team Bereitstellung nicht unterbrochen werden.</span><span class="sxs-lookup"><span data-stu-id="413b1-123">The default configuration of TeamsUpgradePolicy is Islands mode, which is designed to ensure that existing business workflows are not interrupted during a Teams deployment.</span></span> <span data-ttu-id="413b1-124">Standardmäßig werden VoIP-, PSTN-und Verbund Anrufe an Ihre Benutzer weiter an Skype for Business weitergeleitet, bis Sie die Richtlinie aktualisieren, um eingehende Anrufe an Teams zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="413b1-124">By default, VoIP, PSTN, and federated calls to your users will continue to be routed to Skype for Business until you update the policy to enable inbound calling to Teams.</span></span>  <span data-ttu-id="413b1-125">Wenn sich die Empfänger im Inseln-Modus befinden:</span><span class="sxs-lookup"><span data-stu-id="413b1-125">When recipients are in islands mode:</span></span>

 - <span data-ttu-id="413b1-126">Eingehende VoIP-Anrufe, die von Skype for Business stammen, landen immer im Skype for Business-Client des Empfängers.</span><span class="sxs-lookup"><span data-stu-id="413b1-126">Incoming VOIP calls that originated in Skype for Business always land in the recipient's Skype for Business client.</span></span>
 - <span data-ttu-id="413b1-127">Eingehende VoIP-Anrufe, die in Teams entstanden sind, landen in Teams, *Wenn sich Absender und Empfänger im gleichen Mandanten befinden*.</span><span class="sxs-lookup"><span data-stu-id="413b1-127">Incoming VOIP calls that originated in Teams land in Teams, *if the sender and receiver are in the same tenant*.</span></span>
 - <span data-ttu-id="413b1-128">Eingehendes Federated-VoIP (unabhängig davon, welcher Client stammt) und PSTN-Anrufe landen immer im Skype for Business-Client des Empfängers.</span><span class="sxs-lookup"><span data-stu-id="413b1-128">Incoming federated VOIP (regardless of which client originates) and PSTN calls always land in the recipient's Skype for Business client.</span></span>
 
<span data-ttu-id="413b1-129">Um sicherzustellen, dass eingehende VoIP-und PSTN-Anrufe immer im Team-Client eines Benutzers landen, aktualisieren Sie den Koexistenzmodus des Benutzers auf TeamsOnly (was bedeutet, weisen Sie ihm die "UpgradeToTeams"-Instanz von TeamsUpgradePolicy zu.</span><span class="sxs-lookup"><span data-stu-id="413b1-129">To ensure that incoming VOIP and PSTN calls always land in a user's Teams client, update the user's coexistence mode to be TeamsOnly (which means, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span>  <span data-ttu-id="413b1-130">Weitere Informationen zu den Modi für Koexistenz und TeamsUpgradePolicy finden Sie unter [Leitfaden zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="413b1-130">For more information on coexistence modes and TeamsUpgradePolicy, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)</span></span>

<span data-ttu-id="413b1-131">**Notizen**</span><span class="sxs-lookup"><span data-stu-id="413b1-131">**NOTES**</span></span>
 - <span data-ttu-id="413b1-132">Skype for Business-IP-Telefone empfangen Anrufe, auch wenn sich der Benutzer im TeamsOnly-Modus befindet.</span><span class="sxs-lookup"><span data-stu-id="413b1-132">Skype for Business IP phones will receive calls, even if the user is in TeamsOnly mode.</span></span>  
 - <span data-ttu-id="413b1-133">Benutzer, die über Telefon System-und Anruf Plan Lizenzen für die Nutzung mit Skype for Business Online bereitgestellt wurden (beispielsweise, dass Ihnen ein Wert von OnlineVoiceRoutingPolicy zugewiesen wurde), verfügen über die Registerkarte "Anrufe" in Teams und können ausgehende PSTN-Anrufe von Teams aus tätigen, ohne dass Administratoren administrative Schritte Unternehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="413b1-133">Users that have been provisioned with Phone System and Calling Plans licenses for use with Skype for Business Online (e.g. they have been assigned a value of OnlineVoiceRoutingPolicy) , will have the Calls tab enabled in Teams and can place outbound PSTN calls from Teams without administrators having to take any administrative action.</span></span>


### <a name="how-to-configure-users-to-receive-all-incoming-voip-and-pstn-calls-in-teams"></a><span data-ttu-id="413b1-134">Konfigurieren von Benutzern für den Empfang aller eingehenden VoIP-und PSTN-Anrufe in Teams</span><span class="sxs-lookup"><span data-stu-id="413b1-134">How to configure users to receive all incoming VOIP and PSTN calls in Teams</span></span>
<span data-ttu-id="413b1-135">Wenn Sie sicherstellen möchten, dass Benutzer alle eingehenden VoIP-und PSTN-Anrufe in Teams empfangen, legen Sie den Koexistenzmodus des Benutzers im Microsoft Teams Admin Center auf TeamsOnly fest, oder verwenden Sie die Skype for Business-Remote-Windows PowerShell-Sitzung, um TeamsUpgradePolicy wie folgt zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="413b1-135">To ensure users receive all incoming VOIP and PSTN calls in Teams, set the user's coexistence mode to TeamsOnly in the Microsoft Teams admin center, or use Skype for Business remote Windows PowerShell session to update TeamsUpgradePolicy as follows:</span></span>

    Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity user@contoso.com


## <a name="see-also"></a><span data-ttu-id="413b1-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="413b1-136">See also</span></span>
[<span data-ttu-id="413b1-137">Einrichten von Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="413b1-137">Set up Calling Plans</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

[<span data-ttu-id="413b1-138">Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="413b1-138">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](https://docs.microsoft.com/MicrosoftTeams/migration-interop-guidance-for-teams-with-skype)

[<span data-ttu-id="413b1-139">Telefonsystem mit Anrufplänen</span><span class="sxs-lookup"><span data-stu-id="413b1-139">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

[<span data-ttu-id="413b1-140">Skype for Business PowerShell-Cmdlet-Referenz</span><span class="sxs-lookup"><span data-stu-id="413b1-140">Skype for Business PowerShell cmdlet reference</span></span>](https://docs.microsoft.com/powershell/module/skype)

