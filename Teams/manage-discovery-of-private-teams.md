---
title: Verwalten der Erkennung privater Teams in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
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
description: Erfahren Sie, wie Sie steuern können, ob private Teams von Microsoft Teams-Benutzern mithilfe von Vorschlägen im Team Katalog und in den Suchergebnissen ermittelt werden können.
ms.openlocfilehash: faae4c53f4fa17668ea69a783211e7ebe01bd4d6
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494626"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="999b4-103">Verwalten der Erkennung privater Teams in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="999b4-103">Manage discovery of private teams in Microsoft Teams</span></span>

> [!INCLUDE [preview feature](includes/preview-feature.md)] 

<span data-ttu-id="999b4-104">Administratoren und Teambesitzer können steuern, ob private Teams von Microsoft Teams-Benutzern in Ihrer Organisation gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="999b4-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="999b4-105">Wenn ein privates Team auffindbar ist, wird es in den Suchergebnissen angezeigt und in den Vorschlägen des Team Katalogs sowie in den öffentlichen Teams in Teams aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="999b4-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="999b4-106">Dadurch ist es für Benutzer einfach, die privaten Teams zu suchen und zu finden, denen Sie beitreten möchten.</span><span class="sxs-lookup"><span data-stu-id="999b4-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="999b4-107">Benutzer können die Teilnahme an einem privaten Team anfordern, das ein Teambesitzer genehmigen oder ablehnen kann.</span><span class="sxs-lookup"><span data-stu-id="999b4-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="999b4-108">Übersicht über öffentliche Teams, private Teams und Discovery in Teams</span><span class="sxs-lookup"><span data-stu-id="999b4-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="999b4-109">Die meisten Organisationen verfügen über die folgenden Arten von Teams: öffentliche Teams, auffindbare private Teams und nicht auffindbare private Teams.</span><span class="sxs-lookup"><span data-stu-id="999b4-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Screenshot des Team Katalogs](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="999b4-111">Öffentliche Teams</span><span class="sxs-lookup"><span data-stu-id="999b4-111">Public teams</span></span>

<span data-ttu-id="999b4-112">Öffentliche Teams stehen allen Benutzern in Ihrer Organisation für die Teilnahme zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="999b4-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="999b4-113">Öffentliche Teams sind für alle Personen im Katalog "Teams" sichtbar, und Benutzer können einem öffentlichen Team beitreten, ohne die Genehmigung des Team Besitzers zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="999b4-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="999b4-114">Beispiele für öffentliche Teams sind ein Team, in dem Sie über Neuigkeiten in der Technologie diskutieren können, ein Team, das Dogfood-Feedback für Ihre Produkte erhält, und ein Team, in dem Personen mit Fahrgemeinschaften arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="999b4-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="999b4-115">Auffindbare private Teams</span><span class="sxs-lookup"><span data-stu-id="999b4-115">Discoverable private teams</span></span>

<span data-ttu-id="999b4-116">Erkennbare private Teams können nur verbunden werden, wenn der Teambesitzer Ihnen Benutzer hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="999b4-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="999b4-117">Wenn Sie ein privates Team auffindbar machen, ist das Team in der Liste der vorgeschlagenen Teams und Suchergebnisse im Katalog "Teams" enthalten.</span><span class="sxs-lookup"><span data-stu-id="999b4-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="999b4-118">Verwenden Sie auffindbare private Teams für Projekte und Gruppen in Ihrer Organisation, die jeder kennt und für die der Zugriff auf Unterhaltungen und Dateien im Team kontrolliert werden muss.</span><span class="sxs-lookup"><span data-stu-id="999b4-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="999b4-119">Beispiele sind ein Team für Ihre Personalabteilung, ein Team für alle Manager in Ihrer Organisation sowie ein Team für einen Manager und deren direkte Berichte.</span><span class="sxs-lookup"><span data-stu-id="999b4-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="999b4-120">Nicht auffindbare private Teams</span><span class="sxs-lookup"><span data-stu-id="999b4-120">Non-discoverable private teams</span></span>

<span data-ttu-id="999b4-121">Nicht auffindbare private Teams können nur verbunden werden, wenn der Teambesitzer Benutzer hinzugefügt hat.</span><span class="sxs-lookup"><span data-stu-id="999b4-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="999b4-122">Wenn Sie ein privates Team nicht auffindbar machen, wird es in der Liste der vorgeschlagenen Teams ausgeblendet und im Katalog "Teams" aus den Suchergebnissen entfernt.</span><span class="sxs-lookup"><span data-stu-id="999b4-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="999b4-123">Verwenden Sie nicht auffindbare Teams, um an vertraulichen und hochgradig vertraulichen Themen zusammenzuarbeiten.</span><span class="sxs-lookup"><span data-stu-id="999b4-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="999b4-124">Beispiele sind ein Team, das eine bevorstehende Akquisition und ein Team besprechen soll, um eine Änderung der strategischen Ausrichtung Ihres Unternehmens zu besprechen.</span><span class="sxs-lookup"><span data-stu-id="999b4-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="999b4-125">Festlegen, ob neue private Teams auffindbar sind</span><span class="sxs-lookup"><span data-stu-id="999b4-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="999b4-126">Wenn ein Teambesitzer ein privates Team erstellt, kann er durch Konfigurieren der Discovery-Einstellung des Teams feststellen, ob es auffindbar ist.</span><span class="sxs-lookup"><span data-stu-id="999b4-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="999b4-127">Neue private Teams können standardmäßig durchsucht und auffindbar sein.</span><span class="sxs-lookup"><span data-stu-id="999b4-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="999b4-128">Wenn der Teambesitzer nicht möchte, dass das private Team in Suchergebnissen und Vorschlägen angezeigt wird, können Sie die Einstellung deaktivieren, indem Sie die Einstellung " **ändern** " neben " **dieses Team ist durchsuchbar und**auffindbar" auswählen.</span><span class="sxs-lookup"><span data-stu-id="999b4-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Screenshot der Ermittlungs Einstellung für neue private Teams](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="999b4-130">Festlegen, ob vorhandene private Teams erkennbar sind</span><span class="sxs-lookup"><span data-stu-id="999b4-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="999b4-131">Teambesitzer können die Ermittlungs Einstellung für ein vorhandenes privates Team direkt in den Team Einstellungen festlegen, und Administratoren können dies mithilfe von PowerShell tun.</span><span class="sxs-lookup"><span data-stu-id="999b4-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="999b4-132">In Team Einstellungen</span><span class="sxs-lookup"><span data-stu-id="999b4-132">In team settings</span></span>

<span data-ttu-id="999b4-133">Wechseln Sie in Microsoft Teams zum privaten Team, klicken Sie auf **Weitere Optionen ̇ ̇ ̇** > **Team verwalten**.</span><span class="sxs-lookup"><span data-stu-id="999b4-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="999b4-134">Erweitern Sie auf der Registerkarte **Einstellungen** die Option **Team Ermittlung**, und deaktivieren oder aktivieren Sie das Kontrollkästchen Verfüg **barkeit aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="999b4-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Screenshot der Ermittlungs Einstellung für vorhandene private Teams](media/private-team-discovery-existing-team.png)

### <a name="using-powershell-coming-soon"></a><span data-ttu-id="999b4-136">Verwenden von PowerShell (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="999b4-136">Using PowerShell (coming soon)</span></span>

<span data-ttu-id="999b4-137">Verwenden Sie das Cmdlet " **Satz-Team** ", um die Ermittlungs Einstellung für ein vorhandenes privates Team zu deaktivieren oder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="999b4-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="999b4-138">Im folgenden finden Sie ein Beispiel dafür, wie Sie ein Team auffindbar machen können:</span><span class="sxs-lookup"><span data-stu-id="999b4-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="999b4-139">Sie können dieses Cmdlet in einem Skript verwenden, um die Ermittlungs Einstellung für vorhandene private Teams massenhaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="999b4-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="999b4-140">Festlegen, ob Benutzer private Teams entdecken können</span><span class="sxs-lookup"><span data-stu-id="999b4-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="999b4-141">Als Administrator können Sie auch steuern, welche Benutzer in Ihrer Organisation private Teams in Suchergebnissen und Vorschlägen in Teams entdecken dürfen.</span><span class="sxs-lookup"><span data-stu-id="999b4-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="999b4-142">Erstellen Sie eine Richtlinie mit dem Cmdlet **New-CsTeamsChannelsPolicy** , und weisen Sie die Richtlinie Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="999b4-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="999b4-143">Legen Sie den **AllowPrivateTeamDiscovery** -Parameter auf " **true** " fest, damit Benutzern, denen die Richtlinie zugewiesen ist, auffindbare private Teams in Suchergebnissen und Vorschlägen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="999b4-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="999b4-144">Durch Festlegen des **AllowPrivateTeamDiscovery** -Parameters auf " **false** " werden alle erkennbaren privaten Teams aus Suchergebnissen und Vorschlägen für Benutzer entfernt, denen die Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="999b4-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="999b4-145">Standardmäßig ist **AllowPrivateTeamDiscovery** für alle Benutzer in einer Organisation auf **true** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="999b4-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="999b4-146">In diesem Beispiel erstellen wir eine Richtlinie mit dem Namen "VendorPolicy", die verhindert, dass Benutzer alle privaten Teams entdecken können, die erkennbar sind, und weisen dann die Richtlinie einem Benutzer mit dem Namen "vendoruser1" zu.</span><span class="sxs-lookup"><span data-stu-id="999b4-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="999b4-147">Private Teams, die nicht auffindbar sind, werden unabhängig von der Richtlinieneinstellung nie in Suchergebnissen und Vorschlägen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="999b4-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="999b4-148">Wenn Sie beispielsweise die Ermittlungs Einstellung für ein privates Team deaktivieren, können Benutzer das Team nicht ermitteln, obwohl der **AllowPrivateTeamDiscovery** -Parameter in der Richtlinieneinstellung für diese Benutzer auf **true** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="999b4-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="999b4-149">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="999b4-149">Related topics</span></span>
- [<span data-ttu-id="999b4-150">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="999b4-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)