---
title: Verwalten von Tags in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: acolonna
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie die Verwendung von Tags in Microsoft Teams in Ihrer Organisation verwalten können.
ms.openlocfilehash: cd2c2e69054923ccf287f35a15fcebb870d6a5d5
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928448"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="7c35b-103">Verwalten von Tags in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c35b-103">Manage tags in Microsoft Teams</span></span>

<span data-ttu-id="7c35b-104">Mithilfe von Tags in Microsoft Teams können Benutzer mit einer Teilmenge von Personen in einem Team kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="7c35b-104">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="7c35b-105">Tags können einem oder mehreren Teammitgliedern hinzugefügt werden, um auf einfache Weise mit einer bestimmten Gruppe von Personen in Kontakt zu treten.</span><span class="sxs-lookup"><span data-stu-id="7c35b-105">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="7c35b-106">Teambesitzer und -mitglieder können einer Person ein oder mehrere Tags hinzufügen (wenn das Feature für sie aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="7c35b-106">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="7c35b-107">Die Tags können dann von jedem Teammitglied in @Erwähnungen in Kanalbeiträgen verwendet werden, oder um eine Unterhaltung nur mit den Personen zu starten, denen das entsprechende Tag zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="7c35b-107">The tags can then be used in @mentions by anyone on the team in a channel post or to start a conversation with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="7c35b-108">Tags werden in privaten Kanälen noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7c35b-108">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="7c35b-109">Funktionsweise von Tags</span><span class="sxs-lookup"><span data-stu-id="7c35b-109">How tags work</span></span>

<span data-ttu-id="7c35b-110">Ein Tag kann einer Person in einem bestimmten Team hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="7c35b-110">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="7c35b-111">Nachdem ein Tag hinzugefügt wurde, kann es in @Erwähnungen in einem Chat oder in einem beliebigen Standardkanal des Teams verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c35b-111">After a tag is added, it can be used in @mentions in a chat or in any standard channel of the team.</span></span> <span data-ttu-id="7c35b-112">Nachfolgend finden Sie einige Beispiele für die Verwendung von Tags in Teams:</span><span class="sxs-lookup"><span data-stu-id="7c35b-112">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="7c35b-113">Ein Verkaufsleiter möchte eine Ankündigung in einem Kanal posten und alle Kassierer benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="7c35b-113">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="7c35b-114">Ein Produktmanager möchte Nachrichten an alle Produktmanager in einem Kanal senden.</span><span class="sxs-lookup"><span data-stu-id="7c35b-114">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="7c35b-115">Ein Krankenhausleiter möchte allen Radiologen in einem Kanal eine Nachricht senden.</span><span class="sxs-lookup"><span data-stu-id="7c35b-115">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>
- <span data-ttu-id="7c35b-116">Ein Marketingmanager möchte einen Gruppenchat mit allen Designern beginnen.</span><span class="sxs-lookup"><span data-stu-id="7c35b-116">A marketing manager wants to start a group chat with all designers.</span></span> 

<span data-ttu-id="7c35b-117">Wenn Sie mehr erfahren möchten, lesen Sie [Verwenden von Tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span><span class="sxs-lookup"><span data-stu-id="7c35b-117">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="7c35b-118">Verwalten von Tags für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="7c35b-118">Manage tags for your organization</span></span>

<span data-ttu-id="7c35b-119">Als Administrator können Sie im Microsoft Teams Admin Center steuern, wer Tags hinzufügen kann und wie Tags in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c35b-119">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Screenshot der Einstellungen für das Tagging im Microsoft Teams Admin Center](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="7c35b-121">Festlegen, wer Tags hinzufügen kann</span><span class="sxs-lookup"><span data-stu-id="7c35b-121">Set who can add tags</span></span>

<span data-ttu-id="7c35b-122">Standardmäßig können Teambesitzer Tags hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7c35b-122">By default, team owners can add tags.</span></span> <span data-ttu-id="7c35b-123">Sie können diese Einstellung ändern, damit Teambesitzer und Teammitglieder Tags hinzufügen können, oder Sie können Tags für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="7c35b-123">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="7c35b-124">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="7c35b-124">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="7c35b-125">Wählen Sie unter **Tagging** neben **Tagging aktivieren für** eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="7c35b-125">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="7c35b-126">**Teambesitzer und -mitglieder**: Zulassen, dass Teambesitzer und -mitglieder Tags hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7c35b-126">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="7c35b-127">**Teambesitzer**: Zulassen, dass Teambesitzer Tags hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7c35b-127">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="7c35b-128">**Deaktiviert**: Deaktivieren von Tags.</span><span class="sxs-lookup"><span data-stu-id="7c35b-128">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="7c35b-129">Konfigurieren von Tag-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="7c35b-129">Configure tags settings</span></span>

<span data-ttu-id="7c35b-130">Sie können die folgenden Tag-Einstellungen konfigurieren, um zu steuern, wie Tags in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c35b-130">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="7c35b-131">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Organisationsweite Einstellungen** > **Teams-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="7c35b-131">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="7c35b-132">Legen Sie unter **Tagging** je nach den Anforderungen Ihrer Organisation Folgendes fest.</span><span class="sxs-lookup"><span data-stu-id="7c35b-132">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="7c35b-133">**Teambesitzer kann überschreiben, wer Tags anwenden kann**: Wenn diese Option aktiviert ist, können Teambesitzer zulassen oder verhindern, dass Mitglieder Tags in Teameinstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7c35b-133">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="7c35b-134">**Mitglieder können zusätzliche Tags hinzufügen**: Wenn Sie Teammitgliedern erlauben, Tags hinzuzufügen, aktivieren Sie diese Option, damit Teammitglieder andere Tags als die von Ihnen festgelegten empfohlenen Standardtags hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="7c35b-134">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="7c35b-135">Ist diese Option deaktiviert, können Teammitglieder nur die Standardtags verwenden.</span><span class="sxs-lookup"><span data-stu-id="7c35b-135">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="7c35b-136">**Vorgeschlagene Standardtags**: Hiermit können Sie eine Reihe von Standardtags hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7c35b-136">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="7c35b-137">Sie können bis zu 25 Tags hinzufügen, und jedes Tag kann maximal 25 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7c35b-137">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="7c35b-138">Teambesitzer und -mitglieder können diese Vorschläge verwenden, weitere hinzufügen oder einen neuen Satz von Tags erstellen (wenn das Feature für sie aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="7c35b-138">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="7c35b-139">Verwalten von Tag-Einstellungen für ein Team</span><span class="sxs-lookup"><span data-stu-id="7c35b-139">Manage tags settings for a team</span></span>

<span data-ttu-id="7c35b-140">Wenn Sie die Einstellung **Teambesitzer kann überschreiben, wer Tags anwenden kann** im Microsoft Teams Admin Center aktiviert haben, können Teambesitzer festlegen, ob Mitglieder auf Teamebene Tags hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="7c35b-140">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="7c35b-141">Wechseln Sie dazu auf der Registerkarte **Einstellungen** für ein Team zu **Tags**, und wählen Sie dann aus, wer Tags hinzufügen kann.</span><span class="sxs-lookup"><span data-stu-id="7c35b-141">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![Screenshot der Tag-Einstellung auf Teamebene](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="7c35b-143">Hinzufügen von Tags in Teams</span><span class="sxs-lookup"><span data-stu-id="7c35b-143">Add tags in Teams</span></span>

<span data-ttu-id="7c35b-144">In Teams enthält die Registerkarte **Mitglieder** der Seite "Team verwalten" für ein Team eine Spalte **Tags**.</span><span class="sxs-lookup"><span data-stu-id="7c35b-144">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="7c35b-145">Teambesitzer und -mitglieder können auf **Tags verwalten** neben einem Mitglied klicken, um die Liste der vorgeschlagenen Tags für dieses Mitglied anzuzeigen und der Liste Tags hinzuzufügen (wenn das Feature für sie aktiviert ist).</span><span class="sxs-lookup"><span data-stu-id="7c35b-145">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="7c35b-146">Screenshot zum Anwenden von Tags im Teams-Client </span><span class="sxs-lookup"><span data-stu-id="7c35b-146">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
