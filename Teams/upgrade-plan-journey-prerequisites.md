---
title: Voraussetzungen für Microsoft Teams | Upgrade der Abhängigkeiten
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Verwenden Sie diese Anleitung, um mehr über die Voraussetzungen und die Umgebungs Abhängigkeiten für die Bereitstellung von Teams in Ihrer Organisation zu erfahren.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9a5cd56e367b9255bd4c41b556583dcc921416a
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523198"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="fe597-103">Voraussetzungen und Umgebungs Abhängigkeiten für Teams</span><span class="sxs-lookup"><span data-stu-id="fe597-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="fe597-104">![Diagramm Upgrade-Strategie, mit Betonung der Phase „Technische Bereitschaft“](media/upgrade-banner-tech-readiness.png "Etappen der Upgrade-Tour mit Schwerpunkt auf der Phase „Technische Bereitschaft“")</span><span class="sxs-lookup"><span data-stu-id="fe597-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="fe597-105">Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen.</span><span class="sxs-lookup"><span data-stu-id="fe597-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="fe597-106">Vergewissern Sie sich zunächst, dass diese Aktivitäten aus den vorherigen Phasen abgeschlossen sind:</span><span class="sxs-lookup"><span data-stu-id="fe597-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="fe597-107">Ernennen der Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="fe597-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="fe597-108">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="fe597-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="fe597-109">Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fe597-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="fe597-110">Auswählen der Upgrade-Strategie</span><span class="sxs-lookup"><span data-stu-id="fe597-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="fe597-111">Teams kombiniert mehrere Office 365-Dienste und ist daher von der korrekten Implementierung und dem Betrieb dieser Dienste abhängig.</span><span class="sxs-lookup"><span data-stu-id="fe597-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="fe597-112">Zu diesen Diensten gehören – aber nicht ausschließlich – SharePoint Online, Exchange Online und OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="fe597-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="fe597-113">Obwohl nicht alle Dienste erforderlich sind, wird dringend empfohlen, alle Dienste zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="fe597-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="fe597-114">Wenn Sie bestimmte Dienste nicht implementieren möchten, wirkt sich dies auf die Funktionalität aus, die Teams Ihrer Organisation anbieten können.</span><span class="sxs-lookup"><span data-stu-id="fe597-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="fe597-115">Wenn Sie beispielsweise SharePoint Online nicht implementieren müssen, ist es für Teams auf SharePoint Online für bestimmte Funktionen wie Dateifreigabe in Gruppenunterhaltungen angewiesen, sodass die Funktionalität, die der Client bietet, nicht durch die Implementierung dieses Diensts verringert wird.</span><span class="sxs-lookup"><span data-stu-id="fe597-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="fe597-116">In den folgenden Artikeln finden Sie Informationen zu den Voraussetzungen und dazu, wie Teams mit anderen Technologien interagieren:</span><span class="sxs-lookup"><span data-stu-id="fe597-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="fe597-117">Wenn Ihre Organisation keine Office 365-Arbeitsauslastungen bereitgestellt hat, lesen Sie [Erste Schritte mit Office 365 for Business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="fe597-117">If your organization hasn't deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="fe597-118">Wenn Ihre Organisation keine überprüfte Domäne für Office 365 hinzugefügt oder konfiguriert hat, lesen Sie [Überprüfen Ihrer Office 365-Domäne](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="fe597-118">If your organization hasn't added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="fe597-119">Wenn Ihre Organisation keine Identitäten mit Azure Active Directory synchronisiert hat, lesen Sie [Identitäts Modelle und Authentifizierung in Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="fe597-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="fe597-120">Wenn Ihre Organisation nicht<sup>1</sup>über Exchange Online verfügt, lesen Sie [verstehen, wie Exchange und Microsoft Teams interagieren](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="fe597-120">If your organization doesn<sup>1</sup>t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="fe597-121">Wenn Ihre Organisation nicht über SharePoint Online verfügt, lesen Sie Grund [Legendes zur Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="fe597-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="fe597-122">Hier erfahren Sie [, wie Microsoft 365-Gruppen und Microsoft Teams interagieren](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="fe597-122">Learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="fe597-123">Wenn es sich bei Ihrer Organisation um eine Bildungseinrichtung handelt und Sie ein Kursteilnehmer-Informations System verwenden, [Stellen Sie School Data Sync bereit](https://docs.microsoft.com/schooldatasync) , bevor Sie Microsoft Teams bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="fe597-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="fe597-124">Nachdem Sie überprüft haben, dass Ihre Umgebung alle anwendbaren Voraussetzungen erfüllt, [evaluieren Sie Ihre aktuelle Umgebung für Teams](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="fe597-124">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
