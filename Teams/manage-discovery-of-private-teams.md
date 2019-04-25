---
title: Verwalten der Suche von privaten Teams in Microsoft-Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie gesteuert wird, ob private Teams durch Microsoft-Teams, Benutzer über Vorschläge in die Team-Katalog und die Suchergebnisse ermittelt werden können.
ms.openlocfilehash: 70d5b81bba719a9e6cc6a51d38d58fd309e07a3b
ms.sourcegitcommit: 9329d740a2060f9c055c5c0c03107a9268c0df5b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2019
ms.locfileid: "33262758"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="a229b-103">Verwalten der Suche von privaten Teams in Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="a229b-103">Manage discovery of private teams in Microsoft Teams</span></span>

<span data-ttu-id="a229b-104">Administratoren und Team Besitzer können gesteuert wird, ob private Teams von Benutzern in Ihrer Organisation Microsoft-Teams, der ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="a229b-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="a229b-105">Wenn eine private Team sichtbar ist, wird in den Suchergebnissen und in Vorschläge im Katalog Team zusammen mit öffentlichen Teams in Teams enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a229b-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="a229b-106">Dies erleichtert Benutzern suchen, und suchen Sie nach der privaten Teams, die sie teilnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="a229b-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="a229b-107">Benutzer können auf einem privaten Team stoßen, das Teambesitzer einer genehmigen oder verweigern kann anfordern.</span><span class="sxs-lookup"><span data-stu-id="a229b-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="a229b-108">Übersicht über öffentliche Teams, private Teams und Erkennung in Teams</span><span class="sxs-lookup"><span data-stu-id="a229b-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="a229b-109">Die meisten Organisationen verfügen über die folgenden Arten von Teams - öffentliche Teams, eDiscovery-fähigen private Teams und nicht erkennbaren private Teams.</span><span class="sxs-lookup"><span data-stu-id="a229b-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Team-Katalog](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="a229b-111">Öffentliche teams</span><span class="sxs-lookup"><span data-stu-id="a229b-111">Public teams</span></span>

<span data-ttu-id="a229b-112">Öffentliche Teams stehen für alle Benutzer in Ihrer Organisation zur Teilnahme an.</span><span class="sxs-lookup"><span data-stu-id="a229b-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="a229b-113">Öffentliche Teams für alle Benutzer in der Galerie Teams sichtbar sind, und Benutzer können eine öffentliche Team teilnehmen, ohne Genehmigung vom Teambesitzer erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="a229b-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="a229b-114">Beispiele für Öffentliche Teams sind ein Team um Neuigkeiten in Technologie, ein Team, Dogfood Feedback für Ihre Produkte zu erhalten und ein Team für Personen Fahrgemeinschaften zu besprechen.</span><span class="sxs-lookup"><span data-stu-id="a229b-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="a229b-115">EDiscovery-fähigen private teams</span><span class="sxs-lookup"><span data-stu-id="a229b-115">Discoverable private teams</span></span>

<span data-ttu-id="a229b-116">EDiscovery-fähigen private Teams können nur hinzugefügt werden, wenn der Teambesitzer für diese Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a229b-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="a229b-117">Wenn Sie einen privaten Team auffindbar sind, ist das Team in der Liste der vorgeschlagenen Teams und der Suchergebnisse im Katalog Teams enthalten.</span><span class="sxs-lookup"><span data-stu-id="a229b-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="a229b-118">Verwenden Sie eDiscovery-fähigen private Teams für Projekte und Gruppen in Ihrer Organisation, die jeder kennt und dabei den Zugriff auf Unterhaltungen und Dateien in das Team gesteuert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="a229b-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="a229b-119">Beispiele sind ein Team für die HR-Abteilung, ein Team für alle Führungskräfte in Ihrer Organisation und ein Team für einen Manager und ihre Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="a229b-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="a229b-120">Nicht sichtbar private teams</span><span class="sxs-lookup"><span data-stu-id="a229b-120">Non-discoverable private teams</span></span>

<span data-ttu-id="a229b-121">Nicht sichtbar private Teams können nur hinzugefügt werden, wenn der Teambesitzer für diese Benutzer hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a229b-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="a229b-122">Wenn Sie einen privaten Team nicht auffindbar zu machen, hat sie aus der Liste der vorgeschlagenen Teams ausgeblendet und aus den Suchergebnissen in der Galerie Teams entfernt.</span><span class="sxs-lookup"><span data-stu-id="a229b-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="a229b-123">Verwenden Sie nicht erkennbaren Teams, um vertrauliche und streng vertraulich Themen zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a229b-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="a229b-124">Beispiele: ein Team, um eine bevorstehende Übernahme zu besprechen und ein Team eine Änderung in Ihrer Organisation strategische Ausrichtung besprechen.</span><span class="sxs-lookup"><span data-stu-id="a229b-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="a229b-125">Festlegen Sie, ob neue private Teams erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="a229b-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="a229b-126">Wenn ein Teambesitzer ein privates Teams erstellt, können sie es sichtbar machen, indem Sie das Team Discovery-Einstellung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a229b-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="a229b-127">Standardmäßig sind neue private Teams durchsuchbar und sichtbar.</span><span class="sxs-lookup"><span data-stu-id="a229b-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="a229b-128">Wenn Teambesitzer das private Team in den Suchergebnissen und Vorschläge angezeigt wird nicht möchte, können sie die Einstellung deaktivieren, durch Auswählen der **Einstellung ändern** **dieses Team durchsuchbar und sichtbar ist**.</span><span class="sxs-lookup"><span data-stu-id="a229b-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Discovery-Einstellung für neue private teams](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="a229b-130">Festlegen Sie, ob die vorhandenen privaten Teams erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="a229b-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="a229b-131">Team Besitzer können die Discovery-Einstellung für eine vorhandene private Team direkt in die Team-Einstellungen und Administratoren können dazu mithilfe von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a229b-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="a229b-132">In den Team-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="a229b-132">In team settings</span></span>

<span data-ttu-id="a229b-133">Wechseln Sie in Teams, an das Team der private, klicken Sie auf **Weitere Optionen ˙˙˙** > **Team verwalten**.</span><span class="sxs-lookup"><span data-stu-id="a229b-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="a229b-134">Auf der Registerkarte **Einstellungen** **Team Discovery**, erweitern und deaktivieren oder aktivieren Sie das Kontrollkästchen **Auffindbarkeit zu aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="a229b-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Discovery-Einstellung für vorhandene private teams](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="a229b-136">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="a229b-136">Using PowerShell</span></span>

<span data-ttu-id="a229b-137">Verwenden Sie das Cmdlet " **Set-Team** " zu deaktivieren oder aktivieren auf der Discovery-Einstellung für eine vorhandene private Team.</span><span class="sxs-lookup"><span data-stu-id="a229b-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="a229b-138">Es folgt ein Beispiel dafür, wie Sie ein Team auffindbar sind:</span><span class="sxs-lookup"><span data-stu-id="a229b-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="a229b-139">Dieses Cmdlet können in einem Skript Sie die Ermittlung der vorhandenen privaten Teams in einer Sammeloperation eingestellt.</span><span class="sxs-lookup"><span data-stu-id="a229b-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="a229b-140">Festlegen Sie, ob Benutzer private Teams erkennen können</span><span class="sxs-lookup"><span data-stu-id="a229b-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="a229b-141">Als Administrator können Sie auch steuern, private Teams in den Suchergebnissen und Vorschläge in Teams ermitteln können, welche Benutzer in Ihrer Organisation zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a229b-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="a229b-142">Erstellen Sie eine Richtlinie mit dem Cmdlet **New-CsTeamsChannelsPolicy** , und weisen Sie die Richtlinie für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a229b-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="a229b-143">Legen Sie den **AllowPrivateTeamDiscovery** -Parameter auf **true fest,** um Benutzern zu ermöglichen, die die Richtlinie für eDiscovery-fähigen private Teams in Suchergebnissen und Vorschläge finden Sie unter zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="a229b-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="a229b-144">Den Parameter **AllowPrivateTeamDiscovery** auf **false** festlegen entfernt alle eDiscovery-fähigen private Teams aus den Suchergebnissen und Vorschläge für Benutzer, die die Richtlinie zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="a229b-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="a229b-145">**AllowPrivateTeamDiscovery** ist standardmäßig auf **"true"** für alle Benutzer in einer Organisation festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a229b-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="a229b-146">In diesem Beispiel erstellen wir eine Richtlinie mit dem Namen VendorPolicy, die verhindert, dass Benutzer ermitteln private Teams, die sichtbar gemacht werden, und klicken Sie dann weisen wir die Richtlinie für einen Benutzer mit dem Namen vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="a229b-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="a229b-147">Private Teams, die nicht sichtbar sind werden nie in den Suchergebnissen und Vorschläge, ungeachtet der richtlinieneinstellung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a229b-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="a229b-148">Beispielsweise wenn Sie die Discovery-Einstellung für eine private Team deaktivieren, können Benutzer nicht ermitteln können, das Team, obwohl der **AllowPrivateTeamDiscovery** -Parameter auf **"true"** in der richtlinieneinstellung für diesen Benutzer festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a229b-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a229b-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a229b-149">Related topics</span></span>
- [<span data-ttu-id="a229b-150">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a229b-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)