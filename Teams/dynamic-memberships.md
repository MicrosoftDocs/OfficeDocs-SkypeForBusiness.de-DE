---
title: Übersicht über dynamische Mitgliedschaft für Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Erfahren Sie, wie Microsoft Teams mithilfe der dynamischen Mitgliedschaft Teams unterstützt, die Microsoft 365-Gruppen zugeordnet sind.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583924"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="e921e-103">Übersicht über dynamische Mitgliedschaft für Teams</span><span class="sxs-lookup"><span data-stu-id="e921e-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="e921e-104">Microsoft Teams unterstützt Teams, die Microsoft 365-Gruppen zugeordnet sind, mithilfe der *dynamischen Mitgliedschaft*.</span><span class="sxs-lookup"><span data-stu-id="e921e-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="e921e-105">Mit der dynamischen Mitgliedschaft kann die Mitgliedschaft in einem Team durch eine oder mehrere Regeln definiert werden, die in Azure Active Directory (Azure AD) nach bestimmten Benutzerattributen suchen.</span><span class="sxs-lookup"><span data-stu-id="e921e-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="e921e-106">Benutzer werden automatisch zu den richtigen Teams hinzugefügt oder entfernt, wenn sich Benutzerattribute ändern oder Benutzer dem Mandanten beitreten und ihn belassen.</span><span class="sxs-lookup"><span data-stu-id="e921e-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="e921e-107">Mit der dynamischen Mitgliedschaft können Sie Teams für bestimmte Kohorten von Benutzern in Ihrer Organisation einrichten.</span><span class="sxs-lookup"><span data-stu-id="e921e-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="e921e-108">Mögliche Szenarien sind:</span><span class="sxs-lookup"><span data-stu-id="e921e-108">Possible scenarios include:</span></span>
- <span data-ttu-id="e921e-109">In einem Krankenhaus können unterschiedliche Teams für Krankenschwestern, Ärzte und Chirurgen zur Übertragung von Kommunikationen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="e921e-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="e921e-110">Dies ist besonders wichtig, wenn das Krankenhaus auf temporäre Mitarbeiter angewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e921e-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="e921e-111">Eine Universität kann ein Team für alle Dozenten innerhalb eines bestimmten Kollegiums erstellen, einschließlich einer Dozenten Gruppe, die sich häufig ändert.</span><span class="sxs-lookup"><span data-stu-id="e921e-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="e921e-112">Eine Fluglinie möchte für jeden Flug ein Team erstellen (wie einen Dienstag Nachmittag nonstop von Chicago nach Atlanta) und eine häufig wechselnde Flight Crew automatisch zugewiesen oder entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="e921e-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="e921e-113">Mithilfe dieser Funktion werden die Mitglieder eines bestimmten Teams automatisch basierend auf einem bestimmten Satz von Kriterien aktualisiert, anstatt die Mitgliedschaft manuell zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e921e-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="e921e-114">Hierfür sind Azure AD Premium P1-Lizenzen erforderlich, und die Teammitgliedschaft kann [von einem mandantenadministrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) für die Azure AD-Eigenschaften jedes Benutzers zugewiesen werden, vorausgesetzt, Sie verfügen über einen Mandanten und ein Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="e921e-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="e921e-115">Microsoft Teams kann zwischen ein paar Minuten und bis zu zwei Stunden dauern, um dynamische Mitgliedschaftsänderungen wiederzugeben, sobald Sie in der Microsoft 365-Gruppe für ein Team wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="e921e-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="e921e-116">Regeln können definieren, wer ein Teammitglied ist, aber nicht, wer ein Teambesitzer ist.</span><span class="sxs-lookup"><span data-stu-id="e921e-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="e921e-117">Aktuelle Grenzwerte für Team-und Kanal Größen finden Sie unter [Grenzwerte und Spezifikationen für Microsoft Teams](limits-specifications-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="e921e-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="e921e-118">Besitzer können Benutzer nicht als Mitglieder des Teams hinzufügen oder entfernen, da Mitglieder durch dynamische Gruppenregeln definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e921e-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="e921e-119">Mitglieder können Teams nicht von dynamischen Gruppen zurücklassen.</span><span class="sxs-lookup"><span data-stu-id="e921e-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="e921e-120">Erstellen und Verwalten einer Microsoft 365-Gruppe mit dynamischer Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="e921e-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="e921e-121">Wenn Sie als mandantenadministrator angemeldet sind, folgen Sie den Anweisungen unter [Erstellen einer dynamischen Gruppe und Überprüfen des Status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="e921e-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="e921e-122">Beziehen Sie sich bei Bedarf auf [Dynamische Mitgliedschaftsregeln für Gruppen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="e921e-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="e921e-123">Erstellen eines neuen Teams mit Ihrer Microsoft 365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="e921e-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="e921e-124">Lassen Sie jetzt Zeit, bis die Mitgliedschaftsänderungen wirksam werden, und erstellen Sie ein neues Team, wie unter [Erstellen eines Teams aus einer vorhandenen Gruppe](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e921e-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="e921e-125">Anwenden einer dynamischen Mitgliedschaft auf ein vorhandenes Team</span><span class="sxs-lookup"><span data-stu-id="e921e-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="e921e-126">Sie können auch ein vorhandenes Team übernehmen und es so ändern, dass es eine dynamische Mitgliedschaft aufweist, wie unter [Ändern der statischen Gruppenmitgliedschaft in Dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e921e-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="e921e-127">Änderungen des Clientverhaltens</span><span class="sxs-lookup"><span data-stu-id="e921e-127">Changes in client behavior</span></span>

<span data-ttu-id="e921e-128">Sobald die dynamische Mitgliedschaft für ein Team aktiviert ist, können die Teams-Clients die Mitgliederverwaltung für das Team nicht mehr zulassen.</span><span class="sxs-lookup"><span data-stu-id="e921e-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="e921e-129">Optionen zum Hinzufügen von Mitgliedern, Bearbeiten von Mitgliederrollen, senden und Genehmigen von Join-Anfragen und belassen des Teams sind alle verborgen.</span><span class="sxs-lookup"><span data-stu-id="e921e-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
