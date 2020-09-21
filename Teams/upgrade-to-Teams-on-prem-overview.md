---
title: Upgrade auf Teams über eine lokale Skype for Business-Bereitstellung – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Upgrade von Skype for Business auf Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e146394b5f000ce984d7bfaff5e6674c2c091b98
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955887"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="c8514-103">Upgrade von Skype for Business auf Teams &mdash; für IT-Administratoren</span><span class="sxs-lookup"><span data-stu-id="c8514-103">Upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

## <a name="overview"></a><span data-ttu-id="c8514-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c8514-104">Overview</span></span>

<span data-ttu-id="c8514-105">Bei der Aktualisierung von Skype for Business auf Teams benötigen einige Organisationen einen progressiven Rollout, der von den IT-Abteilungen geplant und verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="c8514-105">When upgrading from Skype for Business to Teams, some organizations require a progressive rollout that is planned and managed by their IT departments.</span></span> <span data-ttu-id="c8514-106">Die Artikel in diesem Abschnitt gelten in erster Linie für IT-Administratoren in Großunternehmen.</span><span class="sxs-lookup"><span data-stu-id="c8514-106">The articles in this section apply primarily to IT administrators in large organizations.</span></span> <span data-ttu-id="c8514-107">Diese Organisationen sind in der Regel lokal, können aber auch große Skype for Business Online-Organisationen sein.</span><span class="sxs-lookup"><span data-stu-id="c8514-107">These organizations are typically on-premises, but they might also be large Skype for Business Online organizations.</span></span> <span data-ttu-id="c8514-108">Bevor Sie diese Artikel lesen, lesen Sie [Erste Schritte mit Ihrem Team-Upgrade](upgrade-start-here.md) und [das Upgrade-Framework](upgrade-framework.md).</span><span class="sxs-lookup"><span data-stu-id="c8514-108">Before reading these articles, be sure to read [Getting started with your Teams Upgrade](upgrade-start-here.md) and [About the Upgrade framework](upgrade-framework.md).</span></span>


<span data-ttu-id="c8514-109">In den folgenden Artikeln wird der Upgradeprozess für Ihre Organisation erläutert:</span><span class="sxs-lookup"><span data-stu-id="c8514-109">The following articles will guide you through the upgrade process for your organization:</span></span> 

- [<span data-ttu-id="c8514-110">Upgrade-Methoden</span><span class="sxs-lookup"><span data-stu-id="c8514-110">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="c8514-111">Tools zum Verwalten des Upgrades</span><span class="sxs-lookup"><span data-stu-id="c8514-111">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="c8514-112">Weitere Überlegungen für Organisationen mit Skype for Business lokal</span><span class="sxs-lookup"><span data-stu-id="c8514-112">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- [<span data-ttu-id="c8514-113">Implementieren des Upgrades</span><span class="sxs-lookup"><span data-stu-id="c8514-113">Implement your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="c8514-114">Überlegungen zum Public Switched Telephone Network (PSTN)</span><span class="sxs-lookup"><span data-stu-id="c8514-114">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="c8514-115">Darüber hinaus werden in den folgenden Artikeln wichtige Upgrade-Konzepte und Koexistenz-Verhaltensweisen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="c8514-115">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="c8514-116">Koexistenz von Teams und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c8514-116">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="c8514-117">Koexistenzmodus – Referenz</span><span class="sxs-lookup"><span data-stu-id="c8514-117">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="c8514-118">Führt Kundenerfahrung und Konformität mit Koexistenzmodi zusammen</span><span class="sxs-lookup"><span data-stu-id="c8514-118">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
><span data-ttu-id="c8514-119">In diesen Artikeln werden die Begriffe Skype for Business Online, Skype for Business Server lokal und Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8514-119">These articles use the terms Skype for Business Online, Skype for Business Server on-premises, and Skype for Business.</span></span> <span data-ttu-id="c8514-120">Der letzte Ausdruck bezieht sich auf sowohl online als auch lokale Versionen.</span><span class="sxs-lookup"><span data-stu-id="c8514-120">The latter term refers to both online and on-premises versions.</span></span>

<span data-ttu-id="c8514-121">Bevor Sie beginnen, sollten Sie beachten, dass ein Benutzer, der in Teams migriert wurde, keinen Skype for Business-Client mehr verwendet, außer an einer in Skype for Business gehosteten Besprechung teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="c8514-121">Before you get started, be aware that a user who has been migrated to Teams no longer uses a Skype for Business client except to join a meeting hosted in Skype for Business.</span></span>  <span data-ttu-id="c8514-122">Alle eingehenden Chats und Anrufe landen im Team-Client des Benutzers, unabhängig davon, ob der Absender Teams oder Skype for Business verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8514-122">All incoming chats and calls land in the user’s Teams client, regardless of whether the sender uses Teams or Skype for Business.</span></span> <span data-ttu-id="c8514-123">Alle neuen Besprechungen, die vom migrierten Benutzer organisiert werden, werden als Teams-Besprechungen geplant.</span><span class="sxs-lookup"><span data-stu-id="c8514-123">Any new meetings organized by the migrated user will be scheduled as Teams meetings.</span></span> <span data-ttu-id="c8514-124">Wenn der Benutzer versucht, den Skype for Business-Client zu verwenden, wird das Initiieren von Chats und anrufen blockiert.</span><span class="sxs-lookup"><span data-stu-id="c8514-124">If the user attempts to use the Skype for Business client, initiation of chats and calls is blocked.</span></span>  <span data-ttu-id="c8514-125">Allerdings kann der Benutzer den Skype for Business-Client weiterhin verwenden, um an Skype for Business-Besprechungen teilzunehmen, zu denen er eingeladen wurde.</span><span class="sxs-lookup"><span data-stu-id="c8514-125">However, the user can (and must) still use the Skype for Business client to join Skype for Business meetings they are invited to.</span></span> <span data-ttu-id="c8514-126">(Ältere Skype for Business-Clients, die vor 2017 ausgeliefert wurden, Ehren TeamsUpgradePolicy nicht.</span><span class="sxs-lookup"><span data-stu-id="c8514-126">(Older Skype for Business clients that shipped before 2017 do not honor TeamsUpgradePolicy.</span></span> <span data-ttu-id="c8514-127">Stellen Sie sicher, dass Sie den neuesten Skype for Business-Client verwenden.)</span><span class="sxs-lookup"><span data-stu-id="c8514-127">Make sure you are using the latest Skype for Business client.)</span></span>
 
<span data-ttu-id="c8514-128">Sie verwalten den Übergang des Benutzers zu Teams mithilfe des Konzepts des [Modus](migration-interop-guidance-for-teams-with-skype.md), bei dem es sich um eine Eigenschaft von [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)handelt.</span><span class="sxs-lookup"><span data-stu-id="c8514-128">You manage your user's transition to Teams using the concept of [mode](migration-interop-guidance-for-teams-with-skype.md), which is a property of [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> <span data-ttu-id="c8514-129">Ein Benutzer, der wie oben beschrieben zu Teams migriert wurde, befindet sich im Modus "TeamsOnly".</span><span class="sxs-lookup"><span data-stu-id="c8514-129">A user who has been migrated to Teams as described above is in “TeamsOnly” mode.</span></span>  <span data-ttu-id="c8514-130">Für eine Organisation, die zu Teams migriert, besteht das ultimative Ziel darin, alle Benutzer in den TeamsOnly-Modus zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="c8514-130">For an organization that is migrating to Teams, the ultimate goal is to move all users to TeamsOnly mode.</span></span>

<span data-ttu-id="c8514-131">Okay.</span><span class="sxs-lookup"><span data-stu-id="c8514-131">OK.</span></span> <span data-ttu-id="c8514-132">Fangen wir an.</span><span class="sxs-lookup"><span data-stu-id="c8514-132">Let's get started.</span></span>  <span data-ttu-id="c8514-133">Der erste Schritt besteht darin [, die für Sie verfügbaren Aktualisierungsmethoden zu](upgrade-to-teams-on-prem-upgrade-methods.md)verstehen.</span><span class="sxs-lookup"><span data-stu-id="c8514-133">The first step is understanding the [upgrade methods available to you](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>







   

## <a name="related-links"></a><span data-ttu-id="c8514-134">Verwandte Links</span><span class="sxs-lookup"><span data-stu-id="c8514-134">Related links</span></span>

[<span data-ttu-id="c8514-135">Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden</span><span class="sxs-lookup"><span data-stu-id="c8514-135">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="c8514-136">Konfigurieren der Hybrid Konnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="c8514-136">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="c8514-137">Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud</span><span class="sxs-lookup"><span data-stu-id="c8514-137">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="c8514-138">Festlegen Ihrer Einstellungen für Koexistenz und Upgrades</span><span class="sxs-lookup"><span data-stu-id="c8514-138">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="c8514-139">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="c8514-139">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="c8514-140">Verwenden des Besprechungs Migrations Diensts (MMS)</span><span class="sxs-lookup"><span data-stu-id="c8514-140">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

