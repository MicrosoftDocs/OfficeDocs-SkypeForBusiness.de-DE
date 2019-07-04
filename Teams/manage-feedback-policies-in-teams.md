---
title: Verwalten von Feedback Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: msedliak
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
description: Erfahren Sie, wie Sie mithilfe von Feedback Richtlinien steuern können, ob Teams-Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft übermitteln können.
ms.openlocfilehash: 3c9d05a3003906377447ee119b8cfc9bd137db81
ms.sourcegitcommit: f26bb86d38c3b45a82e6d77c5aa521360a81ee9b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "35540953"
---
# <a name="manage-feedback-policies-in-microsoft-teams"></a><span data-ttu-id="cc94e-103">Verwalten von Feedback Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc94e-103">Manage feedback policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="cc94e-104">Benutzer können Kommentare und Vorschläge zu Microsoft Teams an Microsoft senden, indem \*\*\*\* > Sie Feedback zu den Teams-Clients**geben** .</span><span class="sxs-lookup"><span data-stu-id="cc94e-104">Users can send comments and suggestions about Teams to Microsoft by going to **Help** > **Give feedback** in the Teams clients.</span></span> <span data-ttu-id="cc94e-105">Wir arbeiten ständig an der Verbesserung der Teams, und wir nutzen dieses Feedback, um Teams besser zu machen.</span><span class="sxs-lookup"><span data-stu-id="cc94e-105">We're continually improving the Teams experience and we use this feedback to make Teams better.</span></span>

![Screenshot der Option "Feedback geben" in Teams](media/manage-feedback-policies-in-teams-give-feedback.png)

<span data-ttu-id="cc94e-107">Daten, die durch **Feedback** gesendet werden, werden unter Ihrer Office 365-Vereinbarung als "Support Daten" betrachtet, einschließlich Informationen, die andernfalls als "Kundendaten" oder "personenbezogene Daten" gelten.</span><span class="sxs-lookup"><span data-stu-id="cc94e-107">Data sent through **Give feedback** is considered as "Support Data" under your Office 365 agreement, including information that would otherwise be considered "Customer Data" or "Personal Data".</span></span>

## <a name="set-whether-users-can-send-feedback-about-teams-to-microsoft"></a><span data-ttu-id="cc94e-108">Festlegen, ob Benutzer Feedback zu Teams an Microsoft senden können</span><span class="sxs-lookup"><span data-stu-id="cc94e-108">Set whether users can send feedback about Teams to Microsoft</span></span>

<span data-ttu-id="cc94e-109">Als Administrator können Sie steuern, ob Benutzer in Ihrer Organisation Feedback zu Teams an Microsoft senden können.</span><span class="sxs-lookup"><span data-stu-id="cc94e-109">As an admin, you can control whether users in your organization can send feedback about Teams to Microsoft.</span></span> <span data-ttu-id="cc94e-110">Standardmäßig wird allen Benutzern in Ihrer Organisation automatisch die globale (org-Wide Standard)-Richtlinie zugewiesen, und das Feature ist in der Richtlinie aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cc94e-110">By default, all users in your organization are automatically assigned the global (Org-wide default) policy and the feature is enabled in the policy.</span></span> <span data-ttu-id="cc94e-111">Die Ausnahme bilden Teams für Bildungseinrichtungen, in denen das Feature für Lehrer und Behinderte für Schüler aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="cc94e-111">The exception is Teams for Education, where the feature is enabled for teachers and disabled for students.</span></span>

<span data-ttu-id="cc94e-112">Sie können die globale Richtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cc94e-112">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="cc94e-113">Wenn einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen ist, gilt diese Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cc94e-113">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="cc94e-114">Wenn einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen ist, gilt die globale Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="cc94e-114">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="cc94e-115">Nachdem Sie die globale Richtlinie bearbeitet oder eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="cc94e-115">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

<span data-ttu-id="cc94e-116">Angenommen, Sie möchten allen Benutzern in Ihrer Organisation das Senden von Feedback mit Ausnahme der neuen Mitarbeiter in der Schulung gestatten.</span><span class="sxs-lookup"><span data-stu-id="cc94e-116">Say, for example, you want to allow all users in your organization to send feedback except for new hires in training.</span></span> <span data-ttu-id="cc94e-117">In diesem Szenario erstellen Sie eine benutzerdefinierte Richtlinie, um die Funktion zu deaktivieren und neuen Mitarbeitern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="cc94e-117">In this scenario, you create a custom policy to turn off the feature and assign it to new hires.</span></span> <span data-ttu-id="cc94e-118">Alle anderen Benutzer in Ihrer Organisation erhalten die globale Richtlinie mit aktiviertem Feature.</span><span class="sxs-lookup"><span data-stu-id="cc94e-118">All other users in your organization get the global policy with the feature turned on.</span></span>  

<span data-ttu-id="cc94e-119">Sie verwenden das Cmdlet **New-CsTeamsFeedbackPolicy** zum Erstellen einer benutzerdefinierten Richtlinie und des Cmdlets **Grant-CsTeamsFeedbackPolicy** , um es einem oder mehreren Benutzern oder Gruppen von Benutzern, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="cc94e-119">You use the **New-CsTeamsFeedbackPolicy** cmdlet to create a custom policy and the **Grant-CsTeamsFeedbackPolicy** cmdlet to assign it to one or more users or groups of users, such as a security group or distribution group.</span></span> 

<span data-ttu-id="cc94e-120">Legen Sie den **userInitiatedMode** -Parameter auf **Enabled** , damit Benutzer, denen die Richtlinie zugewiesen ist, Feedback geben können.</span><span class="sxs-lookup"><span data-stu-id="cc94e-120">Set the **userInitiatedMode** parameter to **enabled** to allow users who are assigned the policy to give feedback.</span></span> <span data-ttu-id="cc94e-121">Durch Festlegen des Parameters auf **deaktiviert** wird das Feature deaktiviert, und Benutzer, denen die Richtlinie zugewiesen ist, haben keine Möglichkeit, Feedback zu geben.</span><span class="sxs-lookup"><span data-stu-id="cc94e-121">Setting the parameter to **disabled** turns off the feature and users who are assigned the policy don't have the option to give feedback.</span></span>

## <a name="create-a-custom-feedback-policy"></a><span data-ttu-id="cc94e-122">Erstellen einer benutzerdefinierten Feedback Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cc94e-122">Create a custom feedback policy</span></span>

<span data-ttu-id="cc94e-123">In diesem Beispiel erstellen wir eine Feedback-Richtlinie namens "New Hire Feedback Policy" und deaktivieren die Möglichkeit, Feedback zu geben.</span><span class="sxs-lookup"><span data-stu-id="cc94e-123">In this example, we create a feedback policy called New Hire Feedback Policy and we turn off the ability to give feedback.</span></span>

```
New-CsTeamsFeedbackPolicy -identity "New Hire Feedback Policy" -userInitiatedMode disabled
```

## <a name="assign-a-custom-feedback-policy"></a><span data-ttu-id="cc94e-124">Zuweisen einer benutzerdefinierten Feedback Richtlinie</span><span class="sxs-lookup"><span data-stu-id="cc94e-124">Assign a custom feedback policy</span></span>

### <a name="assign-a-custom-feedback-policy-to-a-user"></a><span data-ttu-id="cc94e-125">Zuweisen einer benutzerdefinierten Feedback Richtlinie zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="cc94e-125">Assign a custom feedback policy to a user</span></span>

<span data-ttu-id="cc94e-126">In diesem Beispiel weisen wir einem Benutzer mit dem Namen Benutzer1 eine benutzerdefinierte Richtlinie mit dem Namen "New Hire Feedback Policy" zu.</span><span class="sxs-lookup"><span data-stu-id="cc94e-126">In this example, we assign a custom policy named New Hire Feedback Policy to a user named user1.</span></span>

```
Grant-CsTeamsFeedbackPolicy -Identity user1@contoso.com -PolicyName "New Hire Feedback Policy"
```
### <a name="assign-a-custom-feedback-policy-to-users-in-a-group"></a><span data-ttu-id="cc94e-127">Zuweisen einer benutzerdefinierten Feedback Richtlinie zu Benutzern in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="cc94e-127">Assign a custom feedback policy to users in a group</span></span>

<span data-ttu-id="cc94e-128">Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Feedback Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cc94e-128">You may want to assign a custom feedback policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="cc94e-129">So können Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cc94e-129">For example, you may want to assign a policy to all users in a security group.</span></span>

<span data-ttu-id="cc94e-130">In diesem Beispiel weisen wir allen Benutzern in der Gruppe Contoso New hires eine benutzerdefinierte Feedback Richtlinie mit dem Namen "New Hire Feedback Policy" zu.</span><span class="sxs-lookup"><span data-stu-id="cc94e-130">In this example, we assign a custom feedback policy called New Hire Feedback Policy to all users in the Contoso New Hires group.</span></span>  

<span data-ttu-id="cc94e-131">Rufen Sie die GroupObjectId der jeweiligen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="cc94e-131">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso New Hires"
```
<span data-ttu-id="cc94e-132">Rufen Sie die Mitglieder der angegebenen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="cc94e-132">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="cc94e-133">Weisen Sie allen Benutzern in der Gruppe eine bestimmte Feedback Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="cc94e-133">Assign all users in the group to a particular feedback policy.</span></span> <span data-ttu-id="cc94e-134">In diesem Beispiel handelt es sich um eine neue Richtlinie für Einstellungs Feedback.</span><span class="sxs-lookup"><span data-stu-id="cc94e-134">In this example, it's New Hire Feedback Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsFeedbackPolicy -PolicyName "New Hire Feedback Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="cc94e-135">Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="cc94e-135">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cc94e-136">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cc94e-136">Related topics</span></span>

- [<span data-ttu-id="cc94e-137">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc94e-137">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)