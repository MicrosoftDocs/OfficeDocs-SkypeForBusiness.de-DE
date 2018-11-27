---
title: Übersicht über dynamische Mitgliedschaft für Teams
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zu dynamischen Teammitgliedschaft basierend auf AAD.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7a96205f1971207f81d6191ef46e1be25e063f4c
ms.sourcegitcommit: 160ced7013c1c46595c4362c2f32c5769b082294
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2018
ms.locfileid: "26699772"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="c6c77-103">Übersicht über dynamische Mitgliedschaft für Teams</span><span class="sxs-lookup"><span data-stu-id="c6c77-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="c6c77-104">Microsoft-Teams unterstützt Teams dynamischen Mitgliedschaft mit Office 365-Gruppen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="c6c77-104">Microsoft Teams supports teams associated with Office 365 groups using dynamic membership.</span></span> <span data-ttu-id="c6c77-105">Dynamische Mitgliedschaft kann die Mitgliedschaft der ein Team durch eine oder mehrere Regeln definiert werden, die für bestimmte Benutzerattribute in Azure Active Directory (AAD) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c6c77-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (AAD).</span></span> <span data-ttu-id="c6c77-106">Benutzer werden automatisch hinzugefügt oder entfernt den richtigen Teams, wie Benutzerattribute ändern oder Benutzer teilnehmen, und lassen Sie den Mandanten.</span><span class="sxs-lookup"><span data-stu-id="c6c77-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="c6c77-107">Mit der dynamischen Mitgliedschaft können teams Setup für bestimmte Kohorten von Benutzern in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="c6c77-107">With dynamic membership you can setup teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="c6c77-108">Gibt die folgenden mögliche Szenarien:</span><span class="sxs-lookup"><span data-stu-id="c6c77-108">Possible scenarios include:</span></span>
- <span data-ttu-id="c6c77-109">Ein Krankenhaus kann unterschiedliche Teams für Pflegepersonal, Ärzten und Chirurgen Communications Übertragung erstellen.</span><span class="sxs-lookup"><span data-stu-id="c6c77-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="c6c77-110">Dies ist besonders wichtig, wenn das Krankenhaus temp Mitarbeiter erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c6c77-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="c6c77-111">Eine Universität kann erstellen Sie ein Team für alle Fakultät innerhalb einer bestimmten Universität, einschließlich einer angeschlossenen Fakultäts, die häufig ändert.</span><span class="sxs-lookup"><span data-stu-id="c6c77-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="c6c77-112">Flugzeug möchte ein Team für jeden Flug (wie ein Tag Dienstag ununterbrochenen aus Chicago zu Atlanta) erstellen und eine oft geändertem Flug Crew automatisch zugewiesen oder bei Bedarf entfernt haben.</span><span class="sxs-lookup"><span data-stu-id="c6c77-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="c6c77-113">Verwenden dieses Feature, ein bestimmtes Team Mitglieder Update automatisch basierend auf einem bestimmten Satz von Kriterien manuell verwalten der Mitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="c6c77-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="c6c77-114">Dies erfordert Azure AD Premium P1 Lizenzen und Teammitgliedschaft kann jeder Benutzer AAD Eigenschaften [von einem mandantenadministrator zugewiesen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) , vorausgesetzt, Sie haben einen Mandanten und ein Administratorkonto sein.</span><span class="sxs-lookup"><span data-stu-id="c6c77-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's AAD properties provided you have a tenant and an admin account.</span></span> 

<span data-ttu-id="c6c77-115">Microsoft-Teams, kann an einer beliebigen Stelle von ein paar Minuten, bis zu 2 Stunden dauern dynamischen mitgliedschaftsänderungen aktualisiert, sobald sie in der Office 365-Gruppe für ein Team wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c6c77-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span> 

> [!NOTE]
> - <span data-ttu-id="c6c77-116">Regeln können Teammitglieder, aber nicht Team Besitzer definieren.</span><span class="sxs-lookup"><span data-stu-id="c6c77-116">Rules can define team members, but not team Owners.</span></span>
> - <span data-ttu-id="c6c77-117">Aktuelle Einschränkungen für Teams und der Kanal Größen finden Sie unter [Limits und Spezifikationen für Microsoft-Teams](limits-specifications-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="c6c77-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on Team and channel sizes.</span></span>

## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="c6c77-118">Erstellen und Verwalten von einer Office 365-Gruppe mit dynamischen Mitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="c6c77-118">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="c6c77-119">Beim Anmelden als den Mandanten Admin, befolgen Sie die Anweisungen in [einer dynamischen Gruppe erstellen und überprüfen Sie Status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="c6c77-119">While logged in as the tenant Admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="c6c77-120">Bei Bedarf finden Sie unter [Regeln für die dynamische Mitgliedschaft für Azure Active Directory-Gruppen](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="c6c77-120">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="c6c77-121">Erstellen Sie ein neues Team mit Ihrer O365-Gruppe</span><span class="sxs-lookup"><span data-stu-id="c6c77-121">Create a new team with your O365 group</span></span>

<span data-ttu-id="c6c77-122">Jetzt warten Sie die Änderungen wirksam werden, und erstellen Sie ein neues Team, wie in [Gruppen mit Microsoft-Teams verbessern vorhandenen Office 365](enhance-office-365-groups.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c6c77-122">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="c6c77-123">Anwenden von dynamischen Mitgliedschaft an vorhandenen team</span><span class="sxs-lookup"><span data-stu-id="c6c77-123">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="c6c77-124">Sie können auch nehmen ein vorhandenes Team und ändern, um eine dynamische Mitgliedschaft, wie beschrieben in [statische Gruppenmitgliedschaft in einen dynamischen in Azure Active Directory ändern](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="c6c77-124">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="c6c77-125">Änderungen in Clientverhaltens</span><span class="sxs-lookup"><span data-stu-id="c6c77-125">Changes in client behavior</span></span>

<span data-ttu-id="c6c77-126">Sobald dynamischen Mitgliedschaft für ein Team aktiviert ist, können Teams Clients nicht mehr Member Management für das Team, nämlich.</span><span class="sxs-lookup"><span data-stu-id="c6c77-126">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="c6c77-127">Optionen zum Hinzufügen von Mitgliedern, Rollen bearbeiten, senden und Genehmigen von Anfragen Join und das Team verlassen werden alle ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="c6c77-127">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
