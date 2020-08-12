---
title: Entfernen der RestrictedAnonymousAccess Teams-Besprechungsrichtlinie für Benutzer
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Hier erfahren Sie, wie Sie die RestrictedAnonymousAccess Teams-Besprechungsrichtlinie von Benutzern in Ihrer Organisation entfernen.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640983"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="4a086-103">Entfernen der RestrictedAnonymousAccess Teams-Besprechungsrichtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="4a086-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="4a086-104">[Besprechungsrichtlinien](meeting-policies-in-teams.md) in Microsoft Teams werden verwendet, um die Features zu steuern, die Besprechungsteilnehmern für Besprechungen zur Verfügung stehen, die von Benutzern in Ihrer Organisation geplant werden.</span><span class="sxs-lookup"><span data-stu-id="4a086-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="4a086-105">Teams enthält eine integrierte Richtlinie mit dem Namen "RestrictedAnonymousAccess", die vordefinierte Einstellungen enthält, die das Einschränken von anonymen Benutzern vom Starten einer Besprechung beinhalten.</span><span class="sxs-lookup"><span data-stu-id="4a086-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="4a086-106">(Anonyme Benutzer sind Benutzer, die nicht authentifiziert wurden.) Die vordefinierten Einstellungen in der Besprechungsrichtlinie können von Administratoren nicht bearbeitet oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="4a086-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="4a086-107">In diesem Artikel wird gezeigt, wie Sie die RestrictedAnonymousAccess-Besprechungsrichtlinie mithilfe von PowerShell von Benutzern entfernen, denen diese Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="4a086-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="4a086-108">Weitere Informationen zum Verwalten von Teams mithilfe von PowerShell finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="4a086-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="4a086-109">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="4a086-109">Before you start</span></span>

<span data-ttu-id="4a086-110">Installieren und Herstellen einer Verbindung mit dem [Skype for Business PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="4a086-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="4a086-111">Schritt-für-Schritt-Anleitungen finden Sie unter [Installieren von Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="4a086-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="4a086-112">Abrufen der Besprechungsrichtlinien Zuweisungen für Teams für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="4a086-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="4a086-113">Führen Sie die folgenden Schritte aus, um die Team Besprechungsrichtlinien Zuweisungen für Ihre Organisation abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4a086-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="4a086-114">In diesem Beispiel wird die folgende Ausgabe zurückgegeben, die zeigt, dass zwei Benutzern die RestrictedAnonymousAccess-Besprechungsrichtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="4a086-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="4a086-115">Aufheben der Zuweisung der RestrictedAnonymous-Besprechungsrichtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="4a086-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="4a086-116">Wenn Sie die RestrictedAnonymous-Besprechungsrichtlinie von Benutzern entfernen möchten, können Sie das [Grant-CSTeamsMeetingPolicy-](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) Cmdlet verwenden, wenn Sie eine geringe Anzahl von Benutzern haben (beispielsweise weniger als 100-Benutzer).</span><span class="sxs-lookup"><span data-stu-id="4a086-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="4a086-117">Wenn Sie eine große Anzahl von Benutzern (beispielsweise mehr als 100 Benutzer) haben, ist es effizienter, das Cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) zum Übermitteln eines Batchvorgangs zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a086-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="4a086-118">Verwenden des Cmdlets "Grant-CsTeamsMeeting-Richtlinie"</span><span class="sxs-lookup"><span data-stu-id="4a086-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="4a086-119">Führen Sie die folgenden Schritte aus, um die RestrictedAnonymous-Besprechungsrichtlinie von Benutzern zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4a086-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="4a086-120">Verwenden des Cmdlets "New-CsBatchPolicyAssignmentOperation"</span><span class="sxs-lookup"><span data-stu-id="4a086-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="4a086-121">Bei der [Batch Richtlinienzuweisung](assign-policies.md#assign-a-policy-to-a-batch-of-users)beträgt die maximale Anzahl von Benutzern, für die Sie Richtlinien entfernen oder aktualisieren können, 5.000 gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="4a086-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="4a086-122">Wenn Sie beispielsweise über mehr als 5.000 Benutzer verfügen, müssen Sie mehrere Batches übermitteln.</span><span class="sxs-lookup"><span data-stu-id="4a086-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="4a086-123">Um optimale Ergebnisse zu erzielen, sollten Sie nicht mehrere Batches gleichzeitig übermitteln.</span><span class="sxs-lookup"><span data-stu-id="4a086-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="4a086-124">Lassen Sie die Verarbeitung von Batches durchführen, bevor Sie weitere Stapel senden.</span><span class="sxs-lookup"><span data-stu-id="4a086-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="4a086-125">Das Cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) befindet sich im PowerShell-Modul von Teams.</span><span class="sxs-lookup"><span data-stu-id="4a086-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="4a086-126">Bevor Sie diese Schritte ausführen, installieren und verbinden Sie sich mit dem [PowerShell-Modul von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams).</span><span class="sxs-lookup"><span data-stu-id="4a086-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="4a086-127">Schritt-für-Schritt-Anleitungen finden Sie unter [Installieren von Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="4a086-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="4a086-128">Führen Sie die folgenden Befehle aus, um die RestrictedAnonymousAccess-Besprechungsrichtlinie aus einem Batch von Benutzern zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4a086-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="4a086-129">Abrufen des Status der Batch Zuordnung</span><span class="sxs-lookup"><span data-stu-id="4a086-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="4a086-130">Jede Batch Zuordnung gibt eine Vorgangs-ID zurück, die Sie verwenden können, um den Fortschritt und den Status der Aufgaben zu verfolgen und eventuell auftretende Fehler zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="4a086-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="4a086-131">Führen Sie beispielsweise die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="4a086-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="4a086-132">Stellen Sie sicher, dass **ErrorCount** **0** (null) und **OverallStatus** **abgeschlossen**ist.</span><span class="sxs-lookup"><span data-stu-id="4a086-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4a086-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4a086-133">Related topics</span></span>

- [<span data-ttu-id="4a086-134">Verwalten von Besprechungsrichtlinien in Teams</span><span class="sxs-lookup"><span data-stu-id="4a086-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="4a086-135">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a086-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="4a086-136">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a086-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
