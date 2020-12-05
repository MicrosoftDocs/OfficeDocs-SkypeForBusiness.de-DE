---
title: Vorbereiten der Umgebung für ein Upgrade auf Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Überprüfen Sie Ihre Umgebung und Netzwerkbereitschaft, bevor Sie mit dem Upgrade von Skype for Business zu Teams beginnen.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cb736a0398d1ab77ed67919f02a80400bd2ae19e
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578248"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="ced54-103">Vorbereiten der Umgebung für ein Upgrade auf Teams</span><span class="sxs-lookup"><span data-stu-id="ced54-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="ced54-104">![Diagramm Upgrade-Strategie, mit Betonung der Phase „Technische Bereitschaft“](media/upgrade-banner-tech-readiness.png "Etappen der Upgrade-Tour mit Schwerpunkt auf der Phase „Technische Bereitschaft“")</span><span class="sxs-lookup"><span data-stu-id="ced54-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="ced54-105">Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen.</span><span class="sxs-lookup"><span data-stu-id="ced54-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="ced54-106">Vergewissern Sie sich zunächst, dass diese Aktivitäten aus den vorherigen Phasen abgeschlossen sind:</span><span class="sxs-lookup"><span data-stu-id="ced54-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="ced54-107">Ernennen der Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="ced54-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ced54-108">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="ced54-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ced54-109">Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ced54-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ced54-110">Auswählen der Upgrade-Strategie</span><span class="sxs-lookup"><span data-stu-id="ced54-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="ced54-111">Zur erfolgreichen Durchführung eines Teams-Upgrades in Ihrer Organisation müssen Sie Ihre aktuelle Skype for Business-Umgebung und Ihre Netzwerkbereitschaft überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ced54-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="ced54-112">Indem Sie Ihre aktuelle Umgebung vorbereiten, können Sie eine qualitativ hochwertige Benutzererfahrung sicherstellen und dabei gleichzeitig die Qualität der Benutzererfahrung in Teams verbessern.</span><span class="sxs-lookup"><span data-stu-id="ced54-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="ced54-113">Wenn Sie sich Zeit nehmen, um die einzelnen Schritte zu planen, können Sie die Bereitstellung beschleunigen und sicherstellen, dass Ihnen keine wichtigen Aktionselemente entgangen sind.</span><span class="sxs-lookup"><span data-stu-id="ced54-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="ced54-114">Führen Sie diese Aktivitäten parallel zur Vorbereitung der Benutzervorbereitung durch:</span><span class="sxs-lookup"><span data-stu-id="ced54-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="ced54-115">[Bereiten Sie Ihre IT-Mitarbeiter](upgrade-prepare-IT-pros.md) vor, um sicherzustellen, dass sie alles haben, was sie für eine erfolgreiche Upgrade-Strategie benötigen.</span><span class="sxs-lookup"><span data-stu-id="ced54-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="ced54-116">Überprüfen Sie, ob Ihre Umgebung alle [Voraussetzungen](upgrade-plan-journey-prerequisites.md)erfüllt, und verstehen Sie Abhängigkeiten zwischen Microsoft 365-oder Office 365-Diensten und-Teams.</span><span class="sxs-lookup"><span data-stu-id="ced54-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="ced54-117">[Auswerten Ihrer Umgebung](upgrade-plan-journey-evaluate-environment.md), indem Umweltentdeckungen anhand eines Stichproben Fragebogens durchgeführt werden, um zu bestätigen, dass Ihre Organisation bereit ist, eine erfolgreiche Upgrade-Strategie auf Teams durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ced54-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="ced54-118">[Vorbereiten ihres Netzwerks](prepare-network.md) durch Planung, Vorbereitung und Durchführung aller notwendigen Gegenmaßnahmen, damit Ihr Netzwerk die Arbeitsauslastung des Teams unterstützen kann.</span><span class="sxs-lookup"><span data-stu-id="ced54-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="ced54-119">[Vorbereitung Ihres Dienstes](upgrade-prepare-environment-prepare-service.md) für die Einführung mithilfe von Onboarding-Checklisten, um sicherzustellen, dass Ihre Teams-Konfiguration bereit ist, die Migration Ihrer Benutzer von Skype for Business zu Teams zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ced54-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>
