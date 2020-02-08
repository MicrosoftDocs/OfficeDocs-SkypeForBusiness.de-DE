---
title: Vorbereiten einer Umgebung für das Upgrade von Skype for Business auf Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Überprüfen Sie Ihre Umgebung und Netzwerk Bereitschaft, bevor Sie mit dem Upgrade von Skype for Business auf Teams beginnen.
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
ms.openlocfilehash: 82b9418f2e87550667cbc163f8f37a0989ec2b30
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863436"
---
<span data-ttu-id="ef208-103">![Diagramm zum Upgrade von Fahrten mit Hervorhebung der technischen Bereitschaftsstufe](media/upgrade-banner-tech-readiness.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der technischen Bereitschaftsstufe liegt")</span><span class="sxs-lookup"><span data-stu-id="ef208-103">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="ef208-104">Dieser Artikel ist Bestandteil der Phase „Technische Bereitschaft“ Ihrer Upgrade-Strategie, einer Aktivität, die Sie parallel zur Phase „Benutzerbereitschaft“ durchführen.</span><span class="sxs-lookup"><span data-stu-id="ef208-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="ef208-105">Vergewissern Sie sich zunächst, dass diese Aktivitäten aus den vorherigen Phasen abgeschlossen sind:</span><span class="sxs-lookup"><span data-stu-id="ef208-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="ef208-106">Ernennen der Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="ef208-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ef208-107">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="ef208-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ef208-108">Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ef208-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ef208-109">Auswählen der Upgrade-Strategie</span><span class="sxs-lookup"><span data-stu-id="ef208-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="ef208-110">Vorbereiten Ihrer Umgebung für das Upgrade auf Teams</span><span class="sxs-lookup"><span data-stu-id="ef208-110">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="ef208-111">Um ein erfolgreiches Teams-Upgrade in Ihrer Organisation voranzutreiben, ist es wichtig, dass Sie Ihre aktuelle Skype for Business-Umgebung und Ihre Netzwerk Bereitschaft überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ef208-111">To drive a successful Teams upgrade in your organization, it’s important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="ef208-112">Wenn Sie Ihre aktuelle Umgebung vorbereiten, können Sie eine qualitativ hochwertige Benutzeroberfläche und die Qualität der Benutzerfreundlichkeit in Microsoft Teams verbessern.</span><span class="sxs-lookup"><span data-stu-id="ef208-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="ef208-113">Wenn Sie sich die Zeit für die Planung einzelner Schritte nehmen, können Sie die Bereitstellung beschleunigen und sicherstellen, dass Sie keine wichtigen Aktionselemente übersprungen haben.</span><span class="sxs-lookup"><span data-stu-id="ef208-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven’t skipped any important action items.</span></span>

<span data-ttu-id="ef208-114">Führen Sie diese Aktivitäten parallel zur Vorbereitung der Benutzer Bereitschaft durch:</span><span class="sxs-lookup"><span data-stu-id="ef208-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="ef208-115">[Bereiten Sie Ihre IT-Mitarbeiter](upgrade-prepare-IT-pros.md) vor, damit Sie sicherstellen können, dass Sie für eine erfolgreiche Upgrade-Reise benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="ef208-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="ef208-116">Überprüfen Sie, ob Ihre Umgebung alle [Voraussetzungen](upgrade-plan-journey-prerequisites.md)erfüllt, und verstehen Sie Abhängigkeiten zwischen Office 365-Diensten und-Teams.</span><span class="sxs-lookup"><span data-stu-id="ef208-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Office 365 services and Teams.</span></span>
- <span data-ttu-id="ef208-117">[Bewerten Sie Ihre Umgebung](upgrade-plan-journey-evaluate-environment.md) , indem Sie eine Umgebungs Ermittlung durchführen, indem Sie einen Beispiel Fragebogen verwenden, um die Bereitschaft Ihrer Organisation zu bestätigen, eine erfolgreiche Upgrade-Reise an Teams durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="ef208-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization’s readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="ef208-118">[Bereiten Sie Ihr Netzwerk](prepare-network.md) durch Planung, Vorbereitung und die erforderlichen Behebungsschritte für Ihr Netzwerk zur Unterstützung von Arbeitslasten für Teams vor.</span><span class="sxs-lookup"><span data-stu-id="ef208-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="ef208-119">[Bereiten Sie Ihren Dienst](upgrade-prepare-environment-prepare-service.md) für das Rollout mithilfe von Onboarding-Checklisten vor, um sicherzustellen, dass Ihre Teams-Konfiguration bereit ist, die Migration Ihrer Benutzer von Skype for Business zu Teams zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ef208-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>
