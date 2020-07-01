---
title: Verwalten von Teamrichtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informationen zur Verwendung und Verwaltung von Teamrichtlinien in Ihrer Organisation, damit Sie steuern können, wozu Benutzer in Teams und Kanälen berechtigt sind.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938144"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="4ba30-103">Verwalten von Teamrichtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ba30-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="4ba30-104">Als Administrator können Sie mithilfe von Teamrichtlinien in Microsoft Teams steuern, wozu Benutzer in Ihrer Organisation in Teams und Kanälen berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="4ba30-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="4ba30-105">Sie können z. B. festlegen, ob private Teams für Benutzer in den Suchergebnissen und im Teamkatalog sichtbar sind und ob Benutzer private Kanäle erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="4ba30-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="4ba30-106">Zum Verwalten von Teamrichtlinien wechseln Sie im Microsoft Teams Admin Center zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="4ba30-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4ba30-107">Sie können die globale Standardrichtlinie (org-Wide) verwenden oder benutzerdefinierte Richtlinien erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4ba30-107">You can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="4ba30-108">Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="4ba30-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="4ba30-109">Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4ba30-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="4ba30-110">Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="4ba30-110">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="4ba30-111">Erstellen einer benutzerdefinierten Teamrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="4ba30-111">Create a custom teams policy</span></span>

1. <span data-ttu-id="4ba30-112">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="4ba30-112">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="4ba30-113">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="4ba30-113">Click **Add**.</span></span>
3. <span data-ttu-id="4ba30-114">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="4ba30-114">Enter a name and description for the policy.</span></span>

    ![Screenshot der Richtlinieneinstellungen für Teams](media/teams-policies.png)
4. <span data-ttu-id="4ba30-116">Wählen Sie die gewünschten Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="4ba30-116">Choose the settings that you want:</span></span>

- <span data-ttu-id="4ba30-117">**Entdecken privater Teams** (in der privaten Vorschau)<a name="discoverteams"> </a> : Aktivieren Sie diese Einstellung, damit Benutzer private Teams in Suchergebnissen und im Team Katalog entdecken können.</span><span class="sxs-lookup"><span data-stu-id="4ba30-117">**Discover private teams** (in private preview):<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="4ba30-118">**Private Kanäle erstellen**: <a name="createchannels"> </a>aktivieren Sie diese Einstellung, damit Benutzer private Kanäle erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4ba30-118">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="4ba30-119">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ba30-119">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="4ba30-120">Bearbeiten einer Teamrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4ba30-120">Edit a teams policy</span></span>

<span data-ttu-id="4ba30-121">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4ba30-121">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="4ba30-122">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams** > **Teamrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="4ba30-122">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="4ba30-123">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="4ba30-123">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4ba30-124">Aktivieren oder deaktivieren Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="4ba30-124">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="4ba30-125">Zuweisen einer benutzerdefinierten Teamrichtlinie an Benutzer</span><span class="sxs-lookup"><span data-stu-id="4ba30-125">Assign a custom teams policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a><span data-ttu-id="4ba30-126">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4ba30-126">Related topics</span></span>

[<span data-ttu-id="4ba30-127">Verwalten der Sichtbarkeit privater Teams unter Teams</span><span class="sxs-lookup"><span data-stu-id="4ba30-127">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)

[<span data-ttu-id="4ba30-128">Private Kanäle in Teams</span><span class="sxs-lookup"><span data-stu-id="4ba30-128">Private channels in Teams</span></span>](private-channels.md)

[<span data-ttu-id="4ba30-129">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4ba30-129">Assign policies to your users in Teams</span></span>](assign-policies.md)
