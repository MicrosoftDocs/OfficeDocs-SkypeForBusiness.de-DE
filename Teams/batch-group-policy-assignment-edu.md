---
title: Zuweisen von Richtlinien zu umfangreichen Benutzergruppen in ihrer Schule
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie in Ihrer Bildungseinrichtung Richtlinien auf der Grundlage einer Gruppenmitgliedschaft oder direkt über eine Batch Zuordnung für Remote School (teleschool, Tele Schule) zuweisen.
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534101"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="bd50f-103">Zuweisen von Richtlinien zu umfangreichen Benutzergruppen in ihrer Schule</span><span class="sxs-lookup"><span data-stu-id="bd50f-103">Assign policies to large sets of users in your school</span></span>

> [!NOTE]
> <span data-ttu-id="bd50f-104">Eine ausführlichere Geschichte zum Zuweisen von Richtlinien in Microsoft Teams finden Sie unter [Zuweisen von Richtlinien zu Ihren Benutzern in Teams](assign-policies.md).</span><span class="sxs-lookup"><span data-stu-id="bd50f-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="bd50f-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bd50f-105">Overview</span></span>

<span data-ttu-id="bd50f-106">Müssen Sie Ihren Kursteilnehmern und Lehrkräften Zugriff auf verschiedene Features in Microsoft Teams gewähren?</span><span class="sxs-lookup"><span data-stu-id="bd50f-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="bd50f-107">Sie können die Benutzer in Ihrer Organisation anhand des Lizenztyps schnell identifizieren und Ihnen dann die entsprechende Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="bd50f-108">In diesem Lernprogramm erfahren Sie, wie Sie einer Besprechungsrichtlinie große Gruppen von Benutzern in ihrer Schule zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="bd50f-109">Sie können Richtlinien mit dem Microsoft Teams Admin Center und PowerShell zuweisen, und wir werden Ihnen beide Möglichkeiten zeigen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="bd50f-110">Sie können eine Besprechungsrichtlinie einer Sicherheitsgruppe zuweisen, in der die Benutzer Mitglied oder direkt für Benutzer sind, und zwar über eine Batch Richtlinienzuordnung.</span><span class="sxs-lookup"><span data-stu-id="bd50f-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="bd50f-111">Folgende Punkte werden behandelt:</span><span class="sxs-lookup"><span data-stu-id="bd50f-111">You'll learn how to:</span></span>

- <span data-ttu-id="bd50f-112">**Verwenden Sie die [Richtlinienzuweisung für Gruppen](#assign-a-policy-to-a-group) , um einer Sicherheitsgruppe eine Besprechungsrichtlinie zuzuweisen (empfohlen)**.</span><span class="sxs-lookup"><span data-stu-id="bd50f-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="bd50f-113">Mit dieser Methode können Sie eine Richtlinie basierend auf der Gruppenmitgliedschaft zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="bd50f-114">Sie können einer Sicherheitsgruppe oder Verteilerliste eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="bd50f-115">Wenn Mitglieder der Gruppe hinzugefügt oder aus ihr entfernt werden, werden Ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="bd50f-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="bd50f-116">Wir empfehlen, diese Methode zu verwenden, da dadurch die Zeit für das Verwalten von Richtlinien für neue Benutzer oder die Änderung der Rollen der Benutzer verringert wird.</span><span class="sxs-lookup"><span data-stu-id="bd50f-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="bd50f-117">Diese Methode eignet sich am besten für Gruppen mit bis zu 50.000 Benutzern, funktioniert aber auch mit größeren Gruppen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="bd50f-118">**Verwenden Sie die [Zuweisung von Stapelverarbeitungs Richtlinien](assign-policies.md#assign-a-policy-to-a-batch-of-users) , um Benutzern eine Besprechungsrichtlinie in einem Massenvorgang direkt zuzuweisen**.</span><span class="sxs-lookup"><span data-stu-id="bd50f-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="bd50f-119">Sie können eine Richtlinie für bis zu 5.000-Benutzer gleichzeitig zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="bd50f-120">Wenn Sie über mehr als 5.000 Benutzer verfügen, können Sie mehrere Batches übermitteln.</span><span class="sxs-lookup"><span data-stu-id="bd50f-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="bd50f-121">Bei dieser Methode müssen Sie bei neuen Benutzern die Batch Zuordnung erneut ausführen, um die Richtlinie diesen neuen Benutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="bd50f-122">Beachten Sie, dass Benutzer in Teams automatisch die globale (org-Wide Standard)-Richtlinie für einen Teams-Richtlinientyp abrufen, sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="bd50f-123">Da die Kursteilnehmer häufig die größte Gruppe von Benutzern sind und häufig die restriktivsten Einstellungen erhalten, empfehlen wir, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="bd50f-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="bd50f-124">Erstellen Sie eine benutzerdefinierte Richtlinie, die Kernfunktionen wie private Chats und Besprechungsplanung zulässt, und weisen Sie die Richtlinie ihren Mitarbeitern und Pädagogen zu.</span><span class="sxs-lookup"><span data-stu-id="bd50f-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="bd50f-125">Weisen Sie die benutzerdefinierte Richtlinie ihren Mitarbeitern und Pädagogen zu.</span><span class="sxs-lookup"><span data-stu-id="bd50f-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="bd50f-126">Bearbeiten und Anwenden der globalen (org-Wide Standard)-Richtlinie, um die Funktionen für Schüler zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="bd50f-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="bd50f-127">Beachten Sie, dass die globale Richtlinie für alle Benutzer in ihrer Schule gelten soll, bis Sie eine benutzerdefinierte Richtlinie erstellt und ihren Mitarbeitern und Pädagogen zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="bd50f-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="bd50f-128">In diesem Lernprogramm erhalten die Kursteilnehmer die globale Besprechungsrichtlinie, und wir weisen Mitarbeitern und Pädagogen eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen "EducatorMeetingPolicy" zu.</span><span class="sxs-lookup"><span data-stu-id="bd50f-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="bd50f-129">Wir gehen davon aus, dass Sie die globale Richtlinie so geändert haben, dass Sie die Besprechungseinstellungen für Schüler zugeschnitten und [eine benutzerdefinierte Richtlinie erstellt](policy-packages-edu.md) , die die Besprechungs Erfahrung für Mitarbeiter und Pädagogen definiert.</span><span class="sxs-lookup"><span data-stu-id="bd50f-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Screenshot der Seite "Besprechungsrichtlinien" im Team Admin Center](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="bd50f-131">Zuweisen einer Richtlinie zu einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="bd50f-131">Assign a policy to a group</span></span>

<span data-ttu-id="bd50f-132">Führen Sie die folgenden Schritte aus, um eine Sicherheitsgruppe für Ihre Mitarbeiter und Pädagogen zu erstellen und dann dieser Sicherheitsgruppe eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="bd50f-133">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="bd50f-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd50f-134">Wenn Sie einer Gruppe eine Richtlinie zuweisen, wird die Richtlinienzuweisung entsprechend den Rangfolgenregeln an Mitglieder der Gruppe weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="bd50f-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="bd50f-135">Wenn einem Benutzer beispielsweise direkt eine Richtlinie zugewiesen wird (entweder einzeln oder über eine Batch Zuordnung), hat diese Richtlinie Vorrang vor einer Richtlinie, die von einer Gruppe geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="bd50f-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="bd50f-136">Das bedeutet auch, dass Sie, wenn ein Benutzer über eine Besprechungsrichtlinie verfügt, die Ihnen direkt zugewiesen wurde, diese Besprechungsrichtlinie vom Benutzer entfernen müssen, bevor Sie eine Besprechungsrichtlinie von einer Sicherheitsgruppe erben können.</span><span class="sxs-lookup"><span data-stu-id="bd50f-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="bd50f-137">Bevor Sie beginnen, ist es wichtig, die [Rangfolge von Prioritätsregeln](assign-policies.md#precedence-rules) und die Rangfolge von [Gruppenaufgaben](assign-policies.md#group-assignment-ranking)zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="bd50f-138">**Stellen Sie sicher, dass Sie die Konzepte lesen und verstehen, die [Sie über die Richtlinienzuweisung zu Gruppen wissen müssen](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span><span class="sxs-lookup"><span data-stu-id="bd50f-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="bd50f-139">Sie müssen alle diese Schritte ausführen, damit Ihre Mitarbeiter und Pädagogen eine Besprechungsrichtlinie von einer Sicherheitsgruppe erben können.</span><span class="sxs-lookup"><span data-stu-id="bd50f-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="bd50f-140">[Erstellen von Sicherheitsgruppen](#create-security-groups)</span><span class="sxs-lookup"><span data-stu-id="bd50f-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="bd50f-141">[Zuweisen einer Richtlinie zu einer Sicherheitsgruppe](#assign-a-policy-to-a-security-group)</span><span class="sxs-lookup"><span data-stu-id="bd50f-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="bd50f-142">[Entfernen Sie eine Richtlinie, die Benutzern direkt zugewiesen wurde](#remove-a-policy-that-was-directly-assigned-to-users).</span><span class="sxs-lookup"><span data-stu-id="bd50f-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="bd50f-143">Erstellen von Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="bd50f-143">Create security groups</span></span>

<span data-ttu-id="bd50f-144">Erstellen Sie zunächst eine Sicherheitsgruppe für Ihre Mitarbeiter und Erzieher.</span><span class="sxs-lookup"><span data-stu-id="bd50f-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="bd50f-145">Mit [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS) können Sie auf [einfache Weise Sicherheitsgruppen Pädagogen und Schüler](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in ihrer Schule erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="bd50f-146">Wir empfehlen, SDS zum Erstellen der Sicherheitsgruppen zu verwenden, die Sie zum Verwalten von Richtlinien für Ihre Schule benötigen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="bd50f-147">Wenn Sie SDS in Ihrer Umgebung nicht bereitstellen können, verwenden Sie [dieses PowerShell-Skript](scripts/powershell-script-security-groups-edu.md) , um zwei Sicherheitsgruppen zu erstellen: eine für alle Mitarbeiter und Pädagogen, denen eine Fakultäts Lizenz zugewiesen ist, und eine andere für alle Schüler, denen eine Schülerlizenz zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd50f-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="bd50f-148">Sie müssen dieses Skript routinemäßig ausführen, um die Gruppen frisch und auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="bd50f-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="bd50f-149">Zuweisen einer Richtlinie zu einer Sicherheitsgruppe</span><span class="sxs-lookup"><span data-stu-id="bd50f-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bd50f-150">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="bd50f-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="bd50f-151">Derzeit steht die Richtlinienzuweisung für Gruppen, die das Microsoft Teams Admin Center verwenden, nur für Teams-Anruf Richtlinien, Teams-Anruf Park Richtlinien, Teams-Richtlinien, Teams-Live-Ereignisrichtlinien, Teams-Besprechungsrichtlinien und Teams-Messagingrichtlinien zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bd50f-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="bd50f-152">Verwenden Sie für andere Richtlinientypen PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bd50f-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="bd50f-153">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Meetings**  >  **Besprechungsrichtlinien**für Besprechungen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="bd50f-154">Wählen Sie die Registerkarte **Gruppenrichtlinien Zuweisung** aus.</span><span class="sxs-lookup"><span data-stu-id="bd50f-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="bd50f-155">Wählen Sie **Gruppe hinzufügen**aus, und führen Sie dann im Bereich **Richtlinie zu Gruppe zuweisen** die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="bd50f-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![Screenshot des Bereichs "Einstellungen bearbeiten" mit den Besprechungsrichtlinien](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="bd50f-157">Suchen Sie im Feld **Gruppe auswählen** nach der Sicherheitsgruppe, die Ihre Mitarbeiter und Pädagogen enthält, und fügen Sie Sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="bd50f-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="bd50f-158">Geben Sie im Feld **Rang auswählen** den Wert **1**ein.</span><span class="sxs-lookup"><span data-stu-id="bd50f-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="bd50f-159">Wählen Sie im Feld **Richtlinie auswählen** die Option **EducatorMeetingPolicy**aus.</span><span class="sxs-lookup"><span data-stu-id="bd50f-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="bd50f-160">Wählen Sie über **nehmen**aus.</span><span class="sxs-lookup"><span data-stu-id="bd50f-160">Select **Apply**.</span></span>

<span data-ttu-id="bd50f-161">Wenn Sie eine Gruppenrichtlinien Zuordnung entfernen möchten, wählen Sie auf der Registerkarte **Gruppenrichtlinien Zuweisung** auf der Seite Richtlinie die Gruppenzuordnung aus, und wählen Sie dann **Entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="bd50f-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="bd50f-162">Wenn Sie die Rangfolge einer Gruppenaufgabe ändern möchten, müssen Sie zuerst die Gruppenrichtlinien Zuweisung entfernen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="bd50f-163">Führen Sie dann die obigen Schritte aus, um die Richtlinie einer Gruppe zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="bd50f-164">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd50f-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="bd50f-165">Derzeit steht die Richtlinienzuweisung zu Gruppen mit PowerShell nicht für alle Teamrichtlinien Typen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bd50f-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="bd50f-166">Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .</span><span class="sxs-lookup"><span data-stu-id="bd50f-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="bd50f-167">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="bd50f-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="bd50f-168">Führen Sie die folgenden Schritte aus, um das [PowerShell-Modul von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern es noch nicht installiert ist).</span><span class="sxs-lookup"><span data-stu-id="bd50f-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="bd50f-169">Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="bd50f-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="bd50f-170">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="bd50f-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="bd50f-171">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="bd50f-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="bd50f-172">Zuweisen einer Richtlinie zu einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="bd50f-172">Assign a policy to a group</span></span>

<span data-ttu-id="bd50f-173">Führen Sie die folgenden Schritte aus, um der Sicherheitsgruppe, die Ihre Mitarbeiter und Pädagogen enthält, die Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuweisen und die Zuordnungs Rangfolge auf 1 festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="bd50f-174">Sie können eine Sicherheitsgruppe mithilfe der Objekt-ID, der SIP-Adresse (Session Initiation Protocol) oder der e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="bd50f-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="bd50f-175">In diesem Beispiel wird eine e-Mail-Adresse (Staff-Faculty@contoso.com) verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd50f-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="bd50f-176">Entfernen einer Richtlinie, die Benutzern direkt zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="bd50f-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="bd50f-177">Beachten Sie, dass die Richtlinie Vorrang hat, wenn einem Benutzer direkt eine Richtlinie zugewiesen wurde (entweder einzeln oder über eine Batch Aufgabe).</span><span class="sxs-lookup"><span data-stu-id="bd50f-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="bd50f-178">Das bedeutet, dass Sie die Besprechungsrichtlinie des Benutzers entfernen müssen, bevor Sie eine Besprechungsrichtlinie von einer Sicherheitsgruppe erben können, wenn ein Benutzer über eine Besprechungsrichtlinie verfügt, die Ihnen direkt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd50f-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="bd50f-179">Weitere Informationen finden Sie unter [was Sie über die Richtlinienzuweisung zu Gruppen wissen müssen](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span><span class="sxs-lookup"><span data-stu-id="bd50f-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="bd50f-180">Führen Sie die folgenden Schritte aus, um die Besprechungsrichtlinie zu entfernen, die ihren Mitarbeitern und Pädagogen direkt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd50f-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="bd50f-181">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="bd50f-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="bd50f-182">Führen Sie die folgenden Schritte aus, um das [PowerShell-Modul von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern es noch nicht installiert ist).</span><span class="sxs-lookup"><span data-stu-id="bd50f-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="bd50f-183">Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="bd50f-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="bd50f-184">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="bd50f-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="bd50f-185">Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung mit Azure AD verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="bd50f-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="bd50f-186">Aufheben der Zuweisung einer Richtlinie, die Benutzern direkt zugewiesen wurde</span><span class="sxs-lookup"><span data-stu-id="bd50f-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="bd50f-187">Führen Sie die folgenden Schritte aus, um eine Besprechungsrichtlinie von Benutzern zu entfernen, denen diese Richtlinie direkt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd50f-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="bd50f-188">Sie können Benutzer nach e-Mail-Adresse oder Objekt-ID angeben.</span><span class="sxs-lookup"><span data-stu-id="bd50f-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="bd50f-189">In diesem Beispiel werden die Besprechungsrichtlinien von Benutzern entfernt, die durch Ihre e-Mail-Adresse angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bd50f-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="bd50f-190">In diesem Beispiel wird die Besprechungsrichtlinie aus der Liste der Benutzer in einer Textdatei mit dem Namen user_ids.txt entfernt.</span><span class="sxs-lookup"><span data-stu-id="bd50f-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span> 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="bd50f-191">Abrufen von Richtlinienzuweisungen für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="bd50f-191">Get policy assignments for a group</span></span>

<span data-ttu-id="bd50f-192">Führen Sie die folgenden Schritte aus, um alle Richtlinien anzuzeigen, die einer bestimmten Sicherheitsgruppe zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="bd50f-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="bd50f-193">Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgeführt werden, auch wenn die SIP-Adresse oder e-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="bd50f-193">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="bd50f-194">Abrufen der Richtlinien, die einem Benutzer zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="bd50f-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="bd50f-195">Führen Sie die folgenden Schritte aus, um alle Richtlinien anzuzeigen, die einem bestimmten Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="bd50f-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="bd50f-196">Im folgenden Beispiel wird gezeigt, wie Sie die Richtlinien abrufen, die Reda@contoso.com zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="bd50f-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="bd50f-197">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="bd50f-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="bd50f-198">Führen Sie die folgenden Schritte aus, um Ihren Mitarbeitern und Pädagogen eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy direkt zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="bd50f-199">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd50f-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="bd50f-200">Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul und dem Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="bd50f-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="bd50f-201">Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, müssen Sie das Azure AD PowerShell für Graph-Modul installieren und eine Verbindung herstellen (um die Benutzer anhand der zugewiesenen Lizenzen zu identifizieren) und das Microsoft Teams PowerShell-Modul (um die Richtlinien diesen Benutzern zuzuweisen).</span><span class="sxs-lookup"><span data-stu-id="bd50f-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="bd50f-202">Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul</span><span class="sxs-lookup"><span data-stu-id="bd50f-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="bd50f-203">Öffnen Sie eine erweiterte Windows PowerShell-Eingabeaufforderung (Windows PowerShell als Administrator ausführen), und führen Sie dann die folgenden Schritte aus, um das Azure Active Directory PowerShell für Graph-Modul zu installieren.</span><span class="sxs-lookup"><span data-stu-id="bd50f-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="bd50f-204">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="bd50f-205">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="bd50f-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="bd50f-206">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="bd50f-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="bd50f-207">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="bd50f-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="bd50f-208">Führen Sie die folgenden Schritte aus, um das [PowerShell-Modul von Teams](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (sofern es noch nicht installiert ist).</span><span class="sxs-lookup"><span data-stu-id="bd50f-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="bd50f-209">Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="bd50f-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="bd50f-210">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="bd50f-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="bd50f-211">Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung mit Azure AD verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="bd50f-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="bd50f-212">Identifizieren der Benutzer</span><span class="sxs-lookup"><span data-stu-id="bd50f-212">Identify your users</span></span>

<span data-ttu-id="bd50f-213">Führen Sie zunächst die folgenden Schritte aus, um Ihre Mitarbeiter und Pädagogen anhand des Lizenztyps zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bd50f-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="bd50f-214">Hier erfahren Sie, welche SKUs in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd50f-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="bd50f-215">Sie können dann Mitarbeiter und Pädagogen identifizieren, denen eine Fakultäts-SKU zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="bd50f-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="bd50f-216">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="bd50f-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="bd50f-217">In diesem Beispiel zeigt die Ausgabe, dass die Fakultäts Lizenz SkuId "e97c048c-37a4-45fb-ab50-922fbf07a370" ist.</span><span class="sxs-lookup"><span data-stu-id="bd50f-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="bd50f-218">Eine Liste der Education-SKUs und SKU-IDs finden Sie unter [Education-SKU-Referenz](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="bd50f-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="bd50f-219">Als nächstes führen wir die folgenden Schritte aus, um die Benutzer zu identifizieren, die über diese Lizenz verfügen, und Sie alle zusammen zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="bd50f-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="bd50f-220">Zuweisen einer Richtlinie in Massen</span><span class="sxs-lookup"><span data-stu-id="bd50f-220">Assign a policy in bulk</span></span>

<span data-ttu-id="bd50f-221">Nun weisen wir Benutzern die entsprechenden Richtlinien in loser Schüttung zu.</span><span class="sxs-lookup"><span data-stu-id="bd50f-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="bd50f-222">Die maximale Anzahl von Benutzern, für die Sie Richtlinien zuweisen oder aktualisieren können, ist 5.000.</span><span class="sxs-lookup"><span data-stu-id="bd50f-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="bd50f-223">Wenn Sie beispielsweise über mehr als 5.000 Mitarbeiter und Pädagogen verfügen, müssen Sie mehrere Batches übermitteln.</span><span class="sxs-lookup"><span data-stu-id="bd50f-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="bd50f-224">Führen Sie die folgenden Schritte aus, um Ihren Mitarbeitern und Pädagogen eine benutzerdefinierte Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="bd50f-225">Wenn Sie einen anderen Richtlinientyp in Massen zuweisen möchten, wie TeamsMessagingPolicy, müssen Sie ```PolicyType``` zu der Richtlinie, die Sie zuweisen, und ```PolicyName``` dem Richtliniennamen wechseln.</span><span class="sxs-lookup"><span data-stu-id="bd50f-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="bd50f-226">Abrufen des Status einer Massen Zuordnung</span><span class="sxs-lookup"><span data-stu-id="bd50f-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="bd50f-227">Jede Massenaufgabe gibt eine Vorgangs-ID zurück, die Sie verwenden können, um den Fortschritt der Richtlinienzuweisungen zu verfolgen oder eventuell auftretende Fehler zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="bd50f-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="bd50f-228">Führen Sie beispielsweise die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="bd50f-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="bd50f-229">Führen Sie die folgenden Schritte aus, um den Zuordnungsstatus jedes Benutzers im Batchvorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="bd50f-230">Details zu den einzelnen Benutzern sind in der Eigenschaft zu finden ```UserState``` .</span><span class="sxs-lookup"><span data-stu-id="bd50f-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="bd50f-231">Zuweisen einer Richtlinie in loser Schüttung, wenn mehr als 5.000-Benutzer vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="bd50f-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="bd50f-232">Führen Sie zunächst die folgenden Schritte aus, um zu sehen, wie viele Mitarbeiter und Pädagogen Sie haben:</span><span class="sxs-lookup"><span data-stu-id="bd50f-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="bd50f-233">Anstatt die vollständige Liste der Benutzer-IDs bereitzustellen, führen Sie die folgenden Schritte aus, um die erste 5.000 und dann die nächste 5.000 usw. anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bd50f-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="bd50f-234">Sie können den Bereich der Benutzer-IDs ändern, bis Sie die vollständige Liste der Benutzer erreichen.</span><span class="sxs-lookup"><span data-stu-id="bd50f-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="bd50f-235">Geben Sie beispielsweise ```$faculty[0..4999``` für den ersten Batch ein, verwenden Sie ```$faculty[5000..9999``` für den zweiten Batch, geben Sie ```$faculty[10000..14999``` für den dritten Batch ein, und so weiter.</span><span class="sxs-lookup"><span data-stu-id="bd50f-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="bd50f-236">Abrufen der Richtlinien, die einem Benutzer zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="bd50f-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="bd50f-237">Führen Sie die folgenden Schritte aus, um alle Richtlinien anzuzeigen, die einem bestimmten Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="bd50f-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="bd50f-238">Im folgenden Beispiel wird gezeigt, wie Sie die Richtlinien abrufen, die Hannah@contoso.com zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="bd50f-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="bd50f-239">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="bd50f-239">FAQ</span></span>

<span data-ttu-id="bd50f-240">**Ich bin mit PowerShell für Teams nicht vertraut. Wo finde ich weitere Informationen?**</span><span class="sxs-lookup"><span data-stu-id="bd50f-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="bd50f-241">Eine Übersicht über die Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bd50f-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="bd50f-242">Weitere Informationen zu den in diesem Artikel verwendeten Cmdlets finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="bd50f-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="bd50f-243">Neu – CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="bd50f-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="bd50f-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="bd50f-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="bd50f-245">Neu – CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="bd50f-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="bd50f-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="bd50f-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="bd50f-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="bd50f-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="bd50f-248">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bd50f-248">Related topics</span></span>

- [<span data-ttu-id="bd50f-249">Zuweisen von Richtlinien zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="bd50f-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="bd50f-250">Teamrichtlinien und Richtlinien Pakete für Bildungseinrichtungen</span><span class="sxs-lookup"><span data-stu-id="bd50f-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="bd50f-251">Verwalten von Besprechungsrichtlinien in Teams</span><span class="sxs-lookup"><span data-stu-id="bd50f-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
