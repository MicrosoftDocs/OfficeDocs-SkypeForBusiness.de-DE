---
title: Upgrade auf Microsoft Teams | Roadmap für Skype for Business Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Wählen Sie Ihren Upgrade-Pfad zu Microsoft Teams basierend auf Ihrer aktuellen Skype for Business-Bereitstellung aus.
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
ms.openlocfilehash: 8038b1d04c3deda955465d6262982d0e216e8f23
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836297"
---
<span data-ttu-id="e6d92-103">![Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt](media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")</span><span class="sxs-lookup"><span data-stu-id="e6d92-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e6d92-104">Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise.</span><span class="sxs-lookup"><span data-stu-id="e6d92-104">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e6d92-105">Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:</span><span class="sxs-lookup"><span data-stu-id="e6d92-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="e6d92-106">Ernennen der Projektbeteiligten</span><span class="sxs-lookup"><span data-stu-id="e6d92-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e6d92-107">Definieren des Projektumfangs</span><span class="sxs-lookup"><span data-stu-id="e6d92-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="e6d92-108">Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e6d92-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="e6d92-109">Auswählen der Upgrade-Strategie</span><span class="sxs-lookup"><span data-stu-id="e6d92-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="e6d92-110">Ihre Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="e6d92-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="e6d92-111">Vorbereiten Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="e6d92-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)




# <a name="overview"></a><span data-ttu-id="e6d92-112">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e6d92-112">Overview</span></span>

<span data-ttu-id="e6d92-113">Die Schritte, die Sie zum Durchführen des Upgrades für Teams ausführen, sind von der aktuellen Bereitstellung von Skype for Business abhängig:</span><span class="sxs-lookup"><span data-stu-id="e6d92-113">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

1. <span data-ttu-id="e6d92-114">Bevor Sie mit dem Upgrade beginnen, stellen Sie sicher, dass Sie [einen Benutzer Pilot durchführen](pilot-essentials.md).</span><span class="sxs-lookup"><span data-stu-id="e6d92-114">Before beginning your upgrade, be sure you [conduct a user pilot](pilot-essentials.md).</span></span>

2.  <span data-ttu-id="e6d92-115">Wählen Sie als nächstes basierend auf Ihrer aktuellen Umgebung ihren Ausgangspunkt aus:</span><span class="sxs-lookup"><span data-stu-id="e6d92-115">Next, based on your current environment, choose your starting point:</span></span>  

    - <span data-ttu-id="e6d92-116">**Wenn Sie von Skype for Business Online auf Teams aktualisieren**, führen Sie die Schritte unter [Upgrade von Skype for Business Online auf Teams](https://aka.ms/SkypeToTeams-UpgradeOnline)aus.</span><span class="sxs-lookup"><span data-stu-id="e6d92-116">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

    -  <span data-ttu-id="e6d92-117">**Wenn Sie ein Upgrade von einer lokalen Skype for Business-Umgebung**durchführen, müssen Sie einige zusätzliche Schritte ausführen, um die Konnektivität zwischen Ihren lokalen und Online Umgebungen einzurichten, bevor Sie Ihre Benutzer in Teams verschieben.</span><span class="sxs-lookup"><span data-stu-id="e6d92-117">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="e6d92-118">Weitere Informationen finden Sie unter [Upgrade von Skype for Business lokal in Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="e6d92-118">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
