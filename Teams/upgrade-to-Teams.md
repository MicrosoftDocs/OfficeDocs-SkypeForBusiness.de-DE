---
title: Upgrade auf Microsoft Teams | Roadmap für Skype for Business Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
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
ms.openlocfilehash: 030081b4fbf633e808e1c340f7b88b8224c13700
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905187"
---
# <a name="overview"></a><span data-ttu-id="a22c0-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a22c0-103">Overview</span></span>

<span data-ttu-id="a22c0-104">![Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt](media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")</span><span class="sxs-lookup"><span data-stu-id="a22c0-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="a22c0-105">Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise.</span><span class="sxs-lookup"><span data-stu-id="a22c0-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="a22c0-106">Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="a22c0-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="a22c0-107">Ernennen der Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="a22c0-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="a22c0-108">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="a22c0-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="a22c0-109">Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a22c0-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="a22c0-110">Auswählen der Upgrade-Strategie</span><span class="sxs-lookup"><span data-stu-id="a22c0-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="a22c0-111">Ihre Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="a22c0-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="a22c0-112">Vorbereiten Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="a22c0-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

<span data-ttu-id="a22c0-113">Die Schritte, die Sie zum Durchführen des Upgrades für Teams ausführen, sind von der aktuellen Bereitstellung von Skype for Business abhängig:</span><span class="sxs-lookup"><span data-stu-id="a22c0-113">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

1. <span data-ttu-id="a22c0-114">Bevor Sie mit dem Upgrade beginnen, stellen Sie sicher, dass Sie [einen Benutzer Pilot durchführen](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="a22c0-114">Before beginning your upgrade, be sure you [conduct a user pilot](pilot-essentials.md).</span></span>

2.  <span data-ttu-id="a22c0-115">Wählen Sie als nächstes basierend auf Ihrer aktuellen Umgebung ihren Ausgangspunkt aus:</span><span class="sxs-lookup"><span data-stu-id="a22c0-115">Next, based on your current environment, choose your starting point:</span></span>  

    - <span data-ttu-id="a22c0-116">**Wenn Sie von Skype for Business Online auf Teams aktualisieren**, führen Sie die Schritte unter [Upgrade von Skype for Business Online auf Teams](https://aka.ms/SkypeToTeams-UpgradeOnline)aus.</span><span class="sxs-lookup"><span data-stu-id="a22c0-116">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

    -  <span data-ttu-id="a22c0-117">**Wenn Sie ein Upgrade von einer lokalen Skype for Business-Umgebung**durchführen, müssen Sie einige zusätzliche Schritte ausführen, um die Konnektivität zwischen Ihren lokalen und Online Umgebungen einzurichten, bevor Sie Ihre Benutzer in Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="a22c0-117">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="a22c0-118">Weitere Informationen finden Sie unter [Upgrade von Skype for Business lokal in Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="a22c0-118">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
