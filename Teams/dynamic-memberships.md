---
title: Übersicht über dynamische Mitgliedschaft für Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zu dynamischen Teammitgliedschaft basierend auf AAD.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45e9da5b5bc9c1bb5800634d727bd6c9218812ab
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569830"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="b6313-103">Übersicht über dynamische Mitgliedschaft für Teams</span><span class="sxs-lookup"><span data-stu-id="b6313-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="b6313-104">Microsoft-Teams unterstützt Teams dynamischen Mitgliedschaft mit Office 365-Gruppen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="b6313-104">Microsoft Teams supports teams associated with Office 365 groups using dynamic membership.</span></span> <span data-ttu-id="b6313-105">Dynamische Mitgliedschaft kann die Mitgliedschaft der ein Team durch eine oder mehrere Regeln definiert werden, die für bestimmte Benutzerattribute in Azure Active Directory (AAD) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b6313-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (AAD).</span></span> <span data-ttu-id="b6313-106">Benutzer werden automatisch hinzugefügt oder entfernt den richtigen Teams, wie Benutzerattribute ändern oder Benutzer teilnehmen, und lassen Sie den Mandanten.</span><span class="sxs-lookup"><span data-stu-id="b6313-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="b6313-107">Mit der dynamischen Mitgliedschaft können teams Setup für bestimmte Kohorten von Benutzern in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b6313-107">With dynamic membership you can setup teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="b6313-108">Gibt die folgenden mögliche Szenarien:</span><span class="sxs-lookup"><span data-stu-id="b6313-108">Possible scenarios include:</span></span>
- <span data-ttu-id="b6313-109">Ein Krankenhaus kann unterschiedliche Teams für Pflegepersonal, Ärzten und Chirurgen Communications Übertragung erstellen.</span><span class="sxs-lookup"><span data-stu-id="b6313-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="b6313-110">Dies ist besonders wichtig, wenn das Krankenhaus temp Mitarbeiter erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b6313-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="b6313-111">Eine Universität kann erstellen Sie ein Team für alle Fakultät innerhalb einer bestimmten Universität, einschließlich einer angeschlossenen Fakultäts, die häufig ändert.</span><span class="sxs-lookup"><span data-stu-id="b6313-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="b6313-112">Flugzeug möchte ein Team für jeden Flug (wie ein Tag Dienstag ununterbrochenen aus Chicago zu Atlanta) erstellen und eine oft geändertem Flug Crew automatisch zugewiesen oder bei Bedarf entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="b6313-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="b6313-113">Verwenden dieses Feature, ein bestimmtes Team Mitglieder Update automatisch basierend auf einem bestimmten Satz von Kriterien manuell verwalten der Mitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="b6313-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="b6313-114">Dies erfordert Azure AD Premium P1 Lizenzen und Teammitgliedschaft kann jeder Benutzer AAD Eigenschaften [von einem mandantenadministrator zugewiesen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) , vorausgesetzt, Sie haben einen Mandanten und ein Administratorkonto sein.</span><span class="sxs-lookup"><span data-stu-id="b6313-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's AAD properties provided you have a tenant and an admin account.</span></span> 

<span data-ttu-id="b6313-115">Microsoft-Teams, kann an einer beliebigen Stelle von ein paar Minuten, bis zu 2 Stunden dauern dynamischen mitgliedschaftsänderungen aktualisiert, sobald sie in der Office 365-Gruppe für ein Team wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="b6313-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span> 

> [!NOTE]
> - <span data-ttu-id="b6313-116">Regeln können definieren, die ein Teammitglied ist, jedoch nicht, die ein Team Besitzer ist.</span><span class="sxs-lookup"><span data-stu-id="b6313-116">Rules can define who is a team member, but not who is a team Owner.</span></span>
> - <span data-ttu-id="b6313-117">Aktuelle Einschränkungen für Teams und der Kanal Größen finden Sie unter [Limits und Spezifikationen für Microsoft-Teams](limits-specifications-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="b6313-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on Team and channel sizes.</span></span>
> - <span data-ttu-id="b6313-118">Besitzer werden nicht hinzufügen oder Entfernen von Benutzern als Mitglieder des Teams, da durch Regeln für die dynamische Gruppe Mitglieder definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b6313-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="b6313-119">Elemente werden nicht verlassen können Teams, die auf dynamische Gruppen.</span><span class="sxs-lookup"><span data-stu-id="b6313-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="b6313-120">Erstellen und Verwalten von einer Office 365-Gruppe mit dynamischen Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="b6313-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="b6313-121">Beim Anmelden als den Mandanten Admin, befolgen Sie die Anweisungen in [einer dynamischen Gruppe erstellen und überprüfen Sie Status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="b6313-121">While logged in as the tenant Admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="b6313-122">Bei Bedarf finden Sie unter [Regeln für die dynamische Mitgliedschaft für Azure Active Directory-Gruppen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="b6313-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="b6313-123">Erstellen Sie ein neues Team mit Ihrer O365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="b6313-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="b6313-124">Jetzt warten Sie die Änderungen wirksam werden, und erstellen Sie ein neues Team, wie in [Gruppen mit Microsoft-Teams verbessern vorhandenen Office 365](enhance-office-365-groups.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b6313-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="b6313-125">Anwenden von dynamischen Mitgliedschaft an vorhandenen team</span><span class="sxs-lookup"><span data-stu-id="b6313-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="b6313-126">Sie können auch nehmen ein vorhandenes Team und ändern, um eine dynamische Mitgliedschaft, wie beschrieben in [statische Gruppenmitgliedschaft in einen dynamischen in Azure Active Directory ändern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="b6313-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="b6313-127">Änderungen in Clientverhaltens</span><span class="sxs-lookup"><span data-stu-id="b6313-127">Changes in client behavior</span></span>

<span data-ttu-id="b6313-128">Sobald dynamischen Mitgliedschaft für ein Team aktiviert ist, können Teams Clients nicht mehr Member Management für das Team, nämlich.</span><span class="sxs-lookup"><span data-stu-id="b6313-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="b6313-129">Optionen zum Hinzufügen von Mitgliedern, Rollen bearbeiten, senden und Genehmigen von Anfragen Join und das Team verlassen werden alle ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="b6313-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
