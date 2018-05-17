---
title: Festlegen von Einstelllungen Koexistenz
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Dies hilft Ihnen wählen Sie den Koexistenzmodus und andere Einstellungen Koexistenz festgelegt.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: add6436d66c088d6ffa14867cc03268cb082f0b3
ms.sourcegitcommit: 5a0b3fe49b64f08979c89443f66b15827034e755
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="setting-your-coexistence-settings"></a><span data-ttu-id="e709e-103">Festlegen von Einstelllungen Koexistenz</span><span class="sxs-lookup"><span data-stu-id="e709e-103">Setting your coexistence settings</span></span>


> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<Intro text here>

[<span data-ttu-id="e709e-104">Grundlegendes zu Koexistenz und Aktualisieren von Modi für Skype für Unternehmen und Teams</span><span class="sxs-lookup"><span data-stu-id="e709e-104">Understand coexistence and upgrade modes for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="setting-your-upgrade-options-for-your-users"></a><span data-ttu-id="e709e-105">Festlegen von Optionen für die Aktualisierung für Ihre Benutzer</span><span class="sxs-lookup"><span data-stu-id="e709e-105">Setting your upgrade options for your users</span></span>

<span data-ttu-id="e709e-106">![Teams-Logo-30x30.png](media/teams-logo-30x30.png) **unter Verwendung der Microsoft-Teams und Skype für Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="e709e-106">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="e709e-107">Wechseln Sie im linken Navigationsbereich **Org geltende**Einstellungen > **Teams zu aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="e709e-107">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="e709e-108">Stellen Sie wie folgt geändert am oberen Rand der Seite **Teams Seite ' upgrade '** Wenn sie für Sie geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="e709e-108">At the top of the **Teams upgrade page** page, make the following changes if they will work for you.</span></span>
- <span data-ttu-id="e709e-109">Legen Sie den Modus der **Koexistenz**</span><span class="sxs-lookup"><span data-stu-id="e709e-109">Set the **Coexistence** mode</span></span>
    - <span data-ttu-id="e709e-110">**Inseln** - verwenden Sie diese Einstellung, wenn Sie einige Benutzer auf Skype für Unternehmen und einige Benutzer, mit denen Teams haben.</span><span class="sxs-lookup"><span data-stu-id="e709e-110">**Islands** - use this setting when you have some users on Skype for Business and some users that use Teams.</span></span>
    - <span data-ttu-id="e709e-111">**Für Unternehmen nur Skype** - verwenden Sie diese Einstellung, wenn Sie nur Skype für Unternehmensbenutzer verfügen.</span><span class="sxs-lookup"><span data-stu-id="e709e-111">**Skype for Business only** - use this setting if you only have Skype for Business users.</span></span>
    - <span data-ttu-id="e709e-112">**Nur Teams** - verwenden Sie diese Einstellung, wenn Sie nur Benutzer Teams verfügen.</span><span class="sxs-lookup"><span data-stu-id="e709e-112">**Teams only** - use this setting if you only have Teams users.</span></span>
- <span data-ttu-id="e709e-113">Legen Sie **Benachrichtigen Skype für Unternehmensbenutzer, die Teams für das Upgrade verfügbar ist.**</span><span class="sxs-lookup"><span data-stu-id="e709e-113">Set **Notify Skype for Business users that Teams is available for upgrade.**</span></span>
    - <span data-ttu-id="e709e-114">Wenn Sie diese aktivieren, informiert sie die Skype für Unternehmensbenutzer, die sie für die app Teams aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="e709e-114">If you turn this on, it will tell the Skype for Business users that they can upgrade to the Teams app.</span></span>
- <span data-ttu-id="e709e-115">Legen Sie die **bevorzugte app für Benutzer Skype für Business Besprechungen beitreten** , diese Einstellung bestimmt, welche app wird für die Teilnahme an Skype für Business-Besprechungen verwendet und ist unabhängig vom Wert der Koexistenzmodus berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e709e-115">Set the **Preferred app for users to join Skype for Business meetings**  This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
    - <span data-ttu-id="e709e-116">**Skype-Besprechungen app (Standard)**</span><span class="sxs-lookup"><span data-stu-id="e709e-116">**Skype Meetings app (default)**</span></span>
    - <span data-ttu-id="e709e-117">**Skype für Unternehmen mit begrenzten features**</span><span class="sxs-lookup"><span data-stu-id="e709e-117">**Skype for Business with limited features**</span></span>
- <span data-ttu-id="e709e-118">Festlegen Sie, ob **die app Teams im Hintergrund für Skype für Unternehmensbenutzer** herunterladen diese Einstellung im Hintergrund die app Teams bei Benutzern, die Skype für Unternehmen Windows downloads.</span><span class="sxs-lookup"><span data-stu-id="e709e-118">Set whether to **Download the Teams app in the background for Skype for Business users**  This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="e709e-119">Es wird nur, wenn nur Teams Koexistenzmodus für den Benutzer ist oder wenn Benachrichtigungen über ausstehende in Skype für Unternehmen aktiviert sind, berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e709e-119">It is honored only if coexistence mode for the user is Teams Only, or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
1. <span data-ttu-id="e709e-120">Klicken Sie auf **Speichern** , nachdem Sie die Änderungen vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="e709e-120">Click **Save** after you make your changes.</span></span>


### <a name="related-topics"></a><span data-ttu-id="e709e-121">See Also</span><span class="sxs-lookup"><span data-stu-id="e709e-121">Related topics</span></span>
<span data-ttu-id="e709e-122">[Planen der Weg](upgrade-plan-journey.md)
[Koexistenz verstehen und Durchführen eines Upgrades Modi für Skype für Unternehmen und Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e709e-122">[Plan the journey](upgrade-plan-journey.md)
[Understand coexistence and upgrade modes for Skype for Business and Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span></span>