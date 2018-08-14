---
title: Aktualisieren von Skype für Unternehmen Online auf Teams - Microsoft-Teams
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Überlegungen für das Upgrade auf Teams von Skype für Business Online
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: c910a9a206f93b56e5768498fa9e036132b9c368
ms.sourcegitcommit: b45077dd1b5d366fa9a30698aa66ed4b13264eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/25/2018
ms.locfileid: "21148154"
---
<span data-ttu-id="b5998-103">![Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase] (media/upgrade-banner-deployment.png "Phasen der Upgrade Reise, wobei der Schwerpunkt auf der Bereitstellung und Implementierungsphase")</span><span class="sxs-lookup"><span data-stu-id="b5998-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="b5998-104">Dieser Artikel ist Teil der Bereitstellung und Implementierung Stufe der Ihrem Upgrade Weg.</span><span class="sxs-lookup"><span data-stu-id="b5998-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="b5998-105">Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten ausgeführt haben:</span><span class="sxs-lookup"><span data-stu-id="b5998-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="b5998-106">Ihre Projektbeteiligten eingetragen</span><span class="sxs-lookup"><span data-stu-id="b5998-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="b5998-107">Definiert die Projektumfang</span><span class="sxs-lookup"><span data-stu-id="b5998-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="b5998-108">Skype-Interoperabilität und Koexistenz für Unternehmen und Teams verstanden</span><span class="sxs-lookup"><span data-stu-id="b5998-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="b5998-109">Ihre Reise Upgrade ausgewählt</span><span class="sxs-lookup"><span data-stu-id="b5998-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="b5998-110">Die Umgebung vorbereitet</span><span class="sxs-lookup"><span data-stu-id="b5998-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="b5998-111">Ihre Organisation vorbereitet</span><span class="sxs-lookup"><span data-stu-id="b5998-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="b5998-112">Ein Pilotprojekt durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="b5998-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="b5998-113">Aktualisieren von Skype für Unternehmen Online auf Teams</span><span class="sxs-lookup"><span data-stu-id="b5998-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="b5998-114">Führen Sie die Anweisungen in diesem Artikel, wenn Sie vollständig Skype für Business Online bereitgestellt haben und Ihre Benutzer von Skype für Unternehmen, die Teams aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b5998-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="b5998-115">Sie können Benutzer selektiv aktualisieren oder-Ansatz repräsentieren, basierend auf das Upgrade journey, die Ihrer Organisation ausgewählt hat, durch Ihre Benutzer die entsprechenden Koexistenz und Aktualisierungsmodus zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b5998-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="b5998-116">Weisen Sie den Modus für Upgrade und Koexistenz</span><span class="sxs-lookup"><span data-stu-id="b5998-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="b5998-117">Durchführen eines Upgrades auf Teams erfolgt durch Zuweisen von den TeamsOnly Modus der TeamsUpgradePolicy, die mithilfe von Microsoft-Teams & Skype für Business Admin Center oder einen Skype für Business remote Windows Powershell-Sitzung durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b5998-117">Upgrading to Teams can be accomplished by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using Microsoft Teams & Skype for Business Admin Center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="b5998-118">Weitere Informationen finden Sie unter [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) und [TeamsUpgradePolicy: Verwalten von Migration und Koexistenz](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="b5998-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="b5998-119">Upgrade Telefonsystem und Teams</span><span class="sxs-lookup"><span data-stu-id="b5998-119">Phone System and Teams upgrade</span></span>

<span data-ttu-id="b5998-120">Wenn Ihre Skype für Business Online-Bereitstellung Telefonsystem mit Aufrufen plant umfasst und Microsoft Ihren öffentlichen Telefonnetz Netzwerkanbieter (PSTN) ist, wird Aktualisieren Ihrer Benutzer auf Teams automatisch eingehende PSTN-Aufruf von Teams umzustellen.</span><span class="sxs-lookup"><span data-stu-id="b5998-120">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="b5998-121">Wenn Ihre Skype für Business Online Bereitstellung Telefonsystem mit Cloud Connector Edition umfasst, finden Sie unter die [zusätzliche Überlegungen für das Telefon System direkte Routing](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="b5998-121">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>