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
description: Erfahren Sie, wie Sie in Microsoft Teams die Verwendung von Tags in Ihrer Organisation verwalten können.
ms.openlocfilehash: 3ade2f47474fe8aaf16c568e8c141dcd84526d86
ms.sourcegitcommit: 561b9bab7d6f5a621436bc85ea28ea14657e7868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034504"
---
# <a name="manage-tags-in-microsoft-teams"></a><span data-ttu-id="d6fdb-103">Verwalten von Tags in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d6fdb-103">Manage tags in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="d6fdb-104">Diese Funktion wird im Microsoft Teams Admin Center noch nicht angezeigt?</span><span class="sxs-lookup"><span data-stu-id="d6fdb-104">Don't see this feature in the Microsoft Teams admin center yet?</span></span> <span data-ttu-id="d6fdb-105">Sie wird zurzeit bereitgestellt und ist möglicherweise noch nicht in Ihrer Organisation verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-105">It's currently being rolled out and might not be available in your organization yet.</span></span> <span data-ttu-id="d6fdb-106">Schauen Sie sich die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams)an, um über die bevorstehenden Teams-Features auf dem Laufenden zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-106">To stay on top of upcoming Teams features, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=microsoft%2Cteams).</span></span>

<span data-ttu-id="d6fdb-107">Mithilfe von Tags in Microsoft Teams können Benutzer mit einer Teilmenge von Personen in einem Team kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-107">Tags in Microsoft Teams let users communicate with a subset of people on a team.</span></span> <span data-ttu-id="d6fdb-108">Tags können einem oder mehreren Teammitgliedern hinzugefügt werden, um problemlos eine Verbindung mit der richtigen Teilmenge der Personen herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-108">Tags can be added to one or multiple team members to easily connect with the right subset of people.</span></span> <span data-ttu-id="d6fdb-109">Team Besitzer und-Mitglieder (wenn das Feature für Sie aktiviert ist) können einer Person eine oder mehrere Kategorien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-109">Team owners and members (if the feature is enabled for them) can add one or more tags to a person.</span></span> <span data-ttu-id="d6fdb-110">Die Tags können dann in @Mentions von jeder Person im Team in einem Kanal Beitrag verwendet werden, um nur mit Personen zu kommunizieren, denen diese Kategorie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-110">The tags can then be used in @mentions by anyone on the team in a channel post to communicate with only those people who are assigned that tag.</span></span>

> [!NOTE]
> <span data-ttu-id="d6fdb-111">Tags werden in privaten Kanälen noch nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-111">Tags are not yet supported in private channels.</span></span>

## <a name="how-tags-work"></a><span data-ttu-id="d6fdb-112">Funktionsweise von Tags</span><span class="sxs-lookup"><span data-stu-id="d6fdb-112">How tags work</span></span>

<span data-ttu-id="d6fdb-113">Eine Kategorie kann einer Person in einem bestimmten Team hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-113">A tag can be added to a person on a specific team.</span></span> <span data-ttu-id="d6fdb-114">Nachdem eine Kategorie hinzugefügt wurde, kann Sie in @Mentions in einem beliebigen Standardkanal des Teams verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-114">After a tag is added, it can be used in @mentions in any standard channel of the team.</span></span> <span data-ttu-id="d6fdb-115">Nachfolgend finden Sie einige Beispiele für die Verwendung von Tags in Teams:</span><span class="sxs-lookup"><span data-stu-id="d6fdb-115">Here's some examples of how tags can be used in Teams:</span></span>

- <span data-ttu-id="d6fdb-116">Ein Store Manager möchte eine Ankündigung in einem Kanal Posten und alle Kassierer benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-116">A store manager wants to post an announcement to a channel and notify all cashiers.</span></span>
- <span data-ttu-id="d6fdb-117">Ein Group Product Manager möchte alle Produktmanager in einem Kanal Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-117">A group product manager wants to message all product managers in a channel.</span></span>
- <span data-ttu-id="d6fdb-118">Ein Krankenhaus Administrator möchte eine Nachricht an alle Radiologen in einem Kanal senden.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-118">A hospital administrator wants to send a message to all radiologists in a channel.</span></span>

<span data-ttu-id="d6fdb-119">Weitere Informationen finden Sie [unter Verwenden von Tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span><span class="sxs-lookup"><span data-stu-id="d6fdb-119">To learn more, check out [Using tags in Teams](https://support.office.com/article/using-tags-in-teams-667bd56f-32b8-4118-9a0b-56807c96d91e).</span></span>

## <a name="manage-tags-for-your-organization"></a><span data-ttu-id="d6fdb-120">Verwalten von Tags für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="d6fdb-120">Manage tags for your organization</span></span>

<span data-ttu-id="d6fdb-121">Als Administrator können Sie steuern, wer Kategorien hinzufügen kann und wie Tags in Ihrer Organisation im Microsoft Teams Admin Center verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-121">As an admin, you can control who can add tags and how tags are used across your organization in the Microsoft Teams admin center.</span></span>

![Screenshot der Kennzeichnungs Einstellungen im Microsoft Teams Admin Center](media/manage-tags-admin-settings.png)

### <a name="set-who-can-add-tags"></a><span data-ttu-id="d6fdb-123">Bestimmen, wer Kategorien hinzufügen kann</span><span class="sxs-lookup"><span data-stu-id="d6fdb-123">Set who can add tags</span></span>

<span data-ttu-id="d6fdb-124">Standardmäßig können Teambesitzer Kategorien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-124">By default, team owners can add tags.</span></span> <span data-ttu-id="d6fdb-125">Sie können diese Einstellung ändern, um Teambesitzern und Teammitgliedern das Hinzufügen von Kategorien zu ermöglichen, oder Sie können Kategorien für Ihre Organisation deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-125">You can change this setting to allow team owners and team members to add tags or you can turn off tags for your organization.</span></span>

1. <span data-ttu-id="d6fdb-126">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **organisationsweite Einstellungen** > **Teams Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-126">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="d6fdb-127">Wählen Sie unter **Tagging**neben **Tagging ist aktiviert für**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="d6fdb-127">Under **Tagging**, next to **Tagging is enabled for**, select one of the following options:</span></span>

    - <span data-ttu-id="d6fdb-128">**Teambesitzer und Mitglieder**: zulassen, dass Teambesitzer und Mitgliederkategorien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-128">**Team owners and members**: Allow team owners and members to add tags.</span></span>
    - <span data-ttu-id="d6fdb-129">**Teambesitzer**: zulassen, dass Teambesitzer Kategorien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-129">**Team owners**: Allow team owners to add tags.</span></span>
    - <span data-ttu-id="d6fdb-130">**Deaktiviert**: Deaktivieren von Tags</span><span class="sxs-lookup"><span data-stu-id="d6fdb-130">**Disabled**: Turn off tags.</span></span>

### <a name="configure-tags-settings"></a><span data-ttu-id="d6fdb-131">Konfigurieren von Tags-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="d6fdb-131">Configure tags settings</span></span>

<span data-ttu-id="d6fdb-132">Sie können die folgenden Tags-Einstellungen konfigurieren, um zu steuern, wie Transponder in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-132">You can configure the following tags settings to control how tags are used across your organization.</span></span>

1. <span data-ttu-id="d6fdb-133">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **organisationsweite Einstellungen** > **Teams Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-133">In the left navigation of the Microsoft Teams admin center, click **Org-wide settings** > **Teams settings**.</span></span>
2. <span data-ttu-id="d6fdb-134">Setzen Sie unter **Tagging**die folgenden Optionen, abhängig von den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-134">Under **Tagging**, set the following, depending on the needs of your organization.</span></span>

    - <span data-ttu-id="d6fdb-135">**Der Teambesitzer kann überschreiben, wer Tags anwenden kann**: Wenn dies aktiviert ist, können Teambesitzer Mitgliedern das Hinzufügen von Kategorien in Team Einstellungen erlauben oder verbieten.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-135">**Team owner can override who can apply tags**: When this is turned on, team owners can allow or disallow members to add tags in team settings.</span></span>
    - <span data-ttu-id="d6fdb-136">**Mitglieder können weitere Kategorien hinzufügen**: Wenn Sie Teammitgliedern das Hinzufügen von Kategorien gestatten, aktivieren Sie diese Option, damit die Teammitglieder andere Tags als die von Ihnen festgelegten vorgeschlagenen Standardkategorien hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-136">**Members can add additional tags**: If you allow team members to add tags, turn this on to let team members add tags other than the suggested default tags that you set.</span></span> <span data-ttu-id="d6fdb-137">Wenn diese Option deaktiviert ist, können Teammitglieder nur die Standardkategorien verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-137">If this is turned off, team members can only use the default tags.</span></span>
    - <span data-ttu-id="d6fdb-138">**Vorgeschlagene Standardtags**: Hier können Sie eine Reihe von Standardkategorien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-138">**Suggested default tags**: Use this to add a set of default tags.</span></span> <span data-ttu-id="d6fdb-139">Sie können bis zu 25 Kategorien hinzufügen, und jede Kategorie kann maximal 25 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-139">You can add up to 25 tags, and each tag can contain a maximum of 25 characters.</span></span> <span data-ttu-id="d6fdb-140">Team Besitzer und-Mitglieder (wenn das Feature für Sie aktiviert ist) können diese Vorschläge verwenden, Ihnen hinzufügen oder einen neuen Satz von Tags erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-140">Team owners and members (if the feature is enabled for them) can use these suggestions, add to them, or create a new set of tags.</span></span>

## <a name="manage-tags-settings-for-a-team"></a><span data-ttu-id="d6fdb-141">Verwalten von Kategorien Einstellungen für ein Team</span><span class="sxs-lookup"><span data-stu-id="d6fdb-141">Manage tags settings for a team</span></span>

<span data-ttu-id="d6fdb-142">Wenn Sie den Teambesitzer aktiviert haben, können Sie festlegen, wer Tags im Microsoft Teams Admin Center **anwenden kann** , können Teambesitzer festlegen, ob Mitgliederkategorien auf Teamebene hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-142">If you turned on the **Team owner can override who can apply tags** setting in the Microsoft Teams admin center, team owners can set whether members can add tags at the team level.</span></span> <span data-ttu-id="d6fdb-143">Wechseln Sie dazu auf der Registerkarte **Einstellungen** für ein Team zu **Tags**, und wählen Sie dann aus, wer Kategorien hinzufügen kann.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-143">To do this, on the **Settings** tab for a team, go to **Tags**, and then choose who can add tags.</span></span>

![Screenshot der Einstellung "Tags" auf Teamebene](media/manage-tags-team-settings.png)

## <a name="add-tags-in-teams"></a><span data-ttu-id="d6fdb-145">Hinzufügen von Kategorien in Teams</span><span class="sxs-lookup"><span data-stu-id="d6fdb-145">Add tags in Teams</span></span>

<span data-ttu-id="d6fdb-146">In Teams umfasst die Registerkarte **Mitglieder** der Seite Team verwalten für ein Team eine Spalte **Kategorien** .</span><span class="sxs-lookup"><span data-stu-id="d6fdb-146">In Teams, the **Members** tab of the Manage team page for a team includes a **Tags** column.</span></span> <span data-ttu-id="d6fdb-147">Team Besitzer und-Mitglieder (wenn das Feature für Sie aktiviert ist) können auf Tags neben einem Mitglied **Verwalten** klicken, um die Liste der vorgeschlagenen Kategorien für dieses Mitglied anzuzeigen und der Liste Kategorien hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d6fdb-147">Team owners and members (if the feature is enabled for them) can click **Manage tags** next to a member to see the list of suggested tags for that member and add tags to the list.</span></span>

![<span data-ttu-id="d6fdb-148">Screenshot zum Anwenden von Tags im Teams-Client</span><span class="sxs-lookup"><span data-stu-id="d6fdb-148">Screenshot of how to apply tags in the Teams client</span></span> ](media/manage-tags-teams.png) 
