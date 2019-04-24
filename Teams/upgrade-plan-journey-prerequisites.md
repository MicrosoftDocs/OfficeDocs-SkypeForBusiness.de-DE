---
title: Microsoft-Teams, erforderliche Komponenten | Abhängigkeiten Annahme des Upgrades
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: Verwenden Sie diese Anleitung über die erforderlichen Komponenten und der Umwelt Abhängigkeiten Teams in Ihrer Organisation bereitstellen
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39483e7b3c8e511f2081f907b187d97dbbaf526f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203342"
---
<span data-ttu-id="383d1-103">![Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft] (media/upgrade-banner-tech-readiness.png "Phasen der Upgrade Reise, mit Schwerpunkt auf die Phase technische Bereitschaft")</span><span class="sxs-lookup"><span data-stu-id="383d1-103">![Stages of the upgrade journey, with emphasis on the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="383d1-104">Dieser Artikel ist Teil technische Bereitschaft Stufe des Ihrem Upgrade Weg, eine Aktivität, die gleichzeitig mit der User Readiness Phase ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="383d1-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="383d1-105">Bevor Sie fortfahren, vergewissern Sie sich, dass Sie diese Aktivitäten aus vorherigen Phasen abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="383d1-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="383d1-106">Ihre Projektbeteiligten eingetragen</span><span class="sxs-lookup"><span data-stu-id="383d1-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="383d1-107">Definiert die Projektumfang</span><span class="sxs-lookup"><span data-stu-id="383d1-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="383d1-108">Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden</span><span class="sxs-lookup"><span data-stu-id="383d1-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="383d1-109">Ihre Reise Upgrade ausgewählt</span><span class="sxs-lookup"><span data-stu-id="383d1-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="383d1-110">Erforderliche Komponenten und Umwelt Abhängigkeiten für Teams</span><span class="sxs-lookup"><span data-stu-id="383d1-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="383d1-111">Teams kombiniert mehrere Office 365-Dienste und ist daher die richtige Implementierung und Betrieb dieser Dienste abhängig.</span><span class="sxs-lookup"><span data-stu-id="383d1-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="383d1-112">Zu diesen Diensten gehören, aber nicht beschränkt auf – SharePoint Online, Exchange Online und OneDrive für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="383d1-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="383d1-113">Obwohl nicht alle Dienste erforderlich sind, empfohlen dringend, dass Sie alle implementieren.</span><span class="sxs-lookup"><span data-stu-id="383d1-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="383d1-114">Wenn Sie nicht bestimmte Dienste zu implementieren, wirkt die Funktionalität sich, dass Teams Ihrem Unternehmen bieten können.</span><span class="sxs-lookup"><span data-stu-id="383d1-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="383d1-115">Angenommen, obwohl Sie SharePoint Online implementiert haben, Teams beruht auf SharePoint Online für bestimmte Funktionen wie Dateifreigabe in Gruppe Unterhaltungen, damit dieser Dienst nicht implementieren reduziert, die über die Funktionalität der Kunde.</span><span class="sxs-lookup"><span data-stu-id="383d1-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="383d1-116">Finden Sie die folgenden Artikel enthalten Informationen zu Voraussetzungen und Interaktion mit anderen Technologien von Teams aus:</span><span class="sxs-lookup"><span data-stu-id="383d1-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="383d1-117">Wenn Ihre Organisation eine beliebige Office 365-Arbeitslasten bereitgestellt noch nicht, finden Sie unter [Erste Schritte mit Office 365 für Unternehmen](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="383d1-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="383d1-118">Wenn Ihre Organisation noch nicht hinzugefügt oder konfiguriert eine überprüfte Domäne für Office 365, finden Sie unter [Überprüfen der Office 365-Domäne](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="383d1-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="383d1-119">Wenn Ihre Organisation Identitäten für Azure Active Directory synchronisiert noch nicht, finden Sie unter [Modelle Identität und Authentifizierung in Microsoft-Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="383d1-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="383d1-120">Wenn Ihre Organisation doesn¹t Exchange Online haben, finden Sie unter [machen Sie sich mit Interaktion von Exchange und Microsoft-Teams](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="383d1-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="383d1-121">Wenn Ihre Organisation SharePoint Online vorhanden ist, finden Sie unter [machen Sie sich mit Interaktion von SharePoint Online und OneDrive für Unternehmen mit Microsoft-Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="383d1-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="383d1-122">Hier erfahren Sie, wie [Office 365-Gruppen und Microsoft-Teams interagieren](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="383d1-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="383d1-123">Wenn Ihre Organisation eine Bildungseinrichtung ist, und Sie eine Student Information System verwenden vor der Bereitstellung von Microsoft-Teams [Schule Daten Sync bereitstellen](https://docs.microsoft.com/schooldatasync) .</span><span class="sxs-lookup"><span data-stu-id="383d1-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="383d1-124">Nachdem Sie haben überprüft, ob die Umgebung alle erforderlichen Komponenten zutreffende, [Bewerten der aktuellen Umgebung für Teams](upgrade-plan-journey-evaluate-environment.md)erfüllt.</span><span class="sxs-lookup"><span data-stu-id="383d1-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>