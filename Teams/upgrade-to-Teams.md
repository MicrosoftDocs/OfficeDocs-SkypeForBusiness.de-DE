---
title: Übersicht über die Implementierung des Upgrades für Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Ermitteln Sie den optimalen Upgrade-Pfad zu Microsoft Teams basierend auf Ihrer aktuellen Skype for Business-Bereitstellung.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0db2e752bb163f806c5dcba7aa56fc36bae7c2ef
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578358"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="1bd44-103">Übersicht über die Implementierung des Upgrades</span><span class="sxs-lookup"><span data-stu-id="1bd44-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="1bd44-104">![Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt](media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")</span><span class="sxs-lookup"><span data-stu-id="1bd44-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="1bd44-105">Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise.</span><span class="sxs-lookup"><span data-stu-id="1bd44-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="1bd44-106">Voraussetzungen für Planungsaktivitäten</span><span class="sxs-lookup"><span data-stu-id="1bd44-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bd44-107">Bevor Sie mit der Upgrade-Implementierung fortfahren, vergewissern Sie sich, dass Sie die Planungsinhalte gelesen haben, beginnend mit [Planen des Upgrades](upgrade-plan-journey.md) , um sicherzustellen, dass Sie alle Voraussetzungen für Planungsaktivitäten abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="1bd44-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="1bd44-108">Ernennen der Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="1bd44-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1bd44-109">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="1bd44-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="1bd44-110">Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1bd44-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="1bd44-111">Auswählen der Upgrade-Strategie</span><span class="sxs-lookup"><span data-stu-id="1bd44-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="1bd44-112">Geplanter Benutzer Pilot</span><span class="sxs-lookup"><span data-stu-id="1bd44-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="1bd44-113">Ihre Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="1bd44-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="1bd44-114">Vorbereiten Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="1bd44-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="1bd44-115">Auswählen des Ausgangspunkts für das Upgrade</span><span class="sxs-lookup"><span data-stu-id="1bd44-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="1bd44-116">Die Schritte, die Sie zum Durchführen des Upgrades für Teams ausführen, sind von der aktuellen Bereitstellung von Skype for Business abhängig:</span><span class="sxs-lookup"><span data-stu-id="1bd44-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="1bd44-117">Wählen Sie basierend auf Ihrer aktuellen Umgebung ihren Ausgangspunkt aus:</span><span class="sxs-lookup"><span data-stu-id="1bd44-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="1bd44-118">**Wenn Sie von Skype for Business Online auf Teams aktualisieren**, führen Sie die Schritte unter [Upgrade von Skype for Business Online auf Teams](https://aka.ms/SkypeToTeams-UpgradeOnline)aus.</span><span class="sxs-lookup"><span data-stu-id="1bd44-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="1bd44-119">**Wenn Sie ein Upgrade von einer lokalen Skype for Business-Umgebung** durchführen, müssen Sie einige zusätzliche Schritte ausführen, um die Konnektivität zwischen Ihren lokalen und Online Umgebungen einzurichten, bevor Sie Ihre Benutzer in Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="1bd44-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="1bd44-120">Weitere Informationen finden Sie unter [Upgrade von Skype for Business lokal in Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="1bd44-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
