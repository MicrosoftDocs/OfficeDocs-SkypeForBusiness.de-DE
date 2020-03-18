---
title: Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informieren Sie sich über die verschiedenen Möglichkeiten, wie Sie Ihren Benutzern in Microsoft Teams Richtlinien zuweisen können.
f1keywords: ''
ms.openlocfilehash: 0f0ce566eb395e3bf3722149797908599091bc2a
ms.sourcegitcommit: 891ba3670ccd16bf72adee5a5f82978dc144b9c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2020
ms.locfileid: "42691195"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="15020-103">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15020-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="15020-104">**Eines der in diesem Artikel behandelten Features von Microsoft Teams, [Richtlinienzuweisung zu Gruppen](#assign-a-policy-to-a-group), befindet sich derzeit in der Vorschau.**</span><span class="sxs-lookup"><span data-stu-id="15020-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently in preview.**</span></span>

<span data-ttu-id="15020-105">Als Administrator verwenden Sie Richtlinien, um die Teamfunktionen zu steuern, die Benutzern in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="15020-105">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="15020-106">So gibt es beispielsweise Anruf Richtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen.</span><span class="sxs-lookup"><span data-stu-id="15020-106">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="15020-107">Organisationen verfügen über unterschiedliche Arten von Benutzern mit eindeutigen Anforderungen und benutzerdefinierten Richtlinien, die Sie erstellen und zuweisen, damit Sie die Richtlinieneinstellungen basierend auf den Anforderungen an unterschiedliche Benutzergruppen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="15020-107">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="15020-108">Um das Verwalten von Richtlinien in Ihrer Organisation zu vereinfachen, bietet Teams verschiedene Möglichkeiten, Richtlinien für Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-108">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="15020-109">Sie können Benutzern eine Richtlinie entweder einzeln oder im Maßstab über eine Batch Zuordnung oder einer Gruppe, der der Benutzer angehört, direkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-109">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="15020-110">Sie können auch Richtlinien Pakete verwenden, um Benutzern in Ihrer Organisation, die über ähnliche Rollen verfügen, eine vordefinierte Sammlung von Richtlinien zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="15020-111">Die von Ihnen ausgewählte Option richtet sich nach der Anzahl der Richtlinien, die Sie verwalten, und der Anzahl der Benutzer, denen Sie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-111">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="15020-112">In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie Benutzern Richtlinien zuweisen können, sowie die empfohlenen Szenarien für die Verwendung von was.</span><span class="sxs-lookup"><span data-stu-id="15020-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="15020-113">Welche Richtlinie hat Vorrang?</span><span class="sxs-lookup"><span data-stu-id="15020-113">Which policy takes precedence?</span></span>

<span data-ttu-id="15020-114">Ein Benutzer verfügt über eine gültige Richtlinie für die einzelnen Richtlinientypen.</span><span class="sxs-lookup"><span data-stu-id="15020-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="15020-115">Es ist möglich oder sogar wahrscheinlich, dass einem Benutzer direkt eine Richtlinie zugewiesen wird, und er ist auch ein Mitglied einer oder mehrerer Gruppen, denen eine Richtlinie desselben Typs zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15020-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="15020-116">Welche Richtlinie hat in diesen Szenarien Vorrang?</span><span class="sxs-lookup"><span data-stu-id="15020-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="15020-117">Die effektive Richtlinie eines Benutzers wird wie folgt gemäß den Regeln für die Rangfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="15020-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="15020-118">Wenn einem Benutzer direkt eine Richtlinie zugewiesen wird (entweder einzeln oder über eine Batch Zuordnung), hat diese Richtlinie Vorrang.</span><span class="sxs-lookup"><span data-stu-id="15020-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="15020-119">Im folgenden Beispiel ist die effektive Richtlinie des Benutzers die Lincoln Square-Besprechungsrichtlinie, die dem Benutzer direkt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15020-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagramm, das zeigt, wie eine direkt zugewiesene Richtlinie Vorrang hat](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="15020-121">Wenn einem Benutzer keine Richtlinie eines bestimmten Typs direkt zugewiesen wird, hat die der Gruppe zugewiesene Richtlinie Vorrang.</span><span class="sxs-lookup"><span data-stu-id="15020-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="15020-122">Wenn ein Benutzer ein Mitglied mehrerer Gruppen ist, hat die Richtlinie, die die höchste [Gruppen Zuordnungs Rangfolge](#group-assignment-ranking) für den angegebenen Richtlinientyp aufweist, Vorrang.</span><span class="sxs-lookup"><span data-stu-id="15020-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="15020-123">In diesem Beispiel ist die effektive Richtlinie des Benutzers die Exec Teams-und HD-Richtlinie, die die höchste Zuordnungs Rangfolge relativ zu anderen Gruppen aufweist, in der der Benutzer Mitglied ist und dem auch eine Richtlinie desselben Richtlinientyps zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15020-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagramm, das zeigt, wie eine von Group geerbte Richtlinie Vorrang hat](media/assign-policies-example-group.png)

<span data-ttu-id="15020-125">Wenn einem Benutzer keine Richtlinie direkt zugewiesen wurde oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, erhält der Benutzer die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="15020-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="15020-126">Hier ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="15020-126">Here's an example.</span></span>

![Diagramm, das zeigt, wie eine globale Richtlinie Vorrang hat](media/assign-policies-example-global.png)

<span data-ttu-id="15020-128">Weitere Informationen finden Sie unter [Prioritätsregeln](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="15020-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="15020-129">Methoden zum Zuweisen von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="15020-129">Ways to assign policies</span></span>

<span data-ttu-id="15020-130">Im folgenden finden Sie eine Übersicht über die Methoden zum Zuweisen von Richtlinien zu Benutzern sowie zu den empfohlenen Szenarien für die einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="15020-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="15020-131">Klicken Sie auf die Links, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="15020-131">Click the links to learn more.</span></span>

|<span data-ttu-id="15020-132">Tun Sie dies</span><span class="sxs-lookup"><span data-stu-id="15020-132">Do this</span></span>  |<span data-ttu-id="15020-133">Wenn...</span><span class="sxs-lookup"><span data-stu-id="15020-133">If...</span></span>  | <span data-ttu-id="15020-134">Verwenden von...</span><span class="sxs-lookup"><span data-stu-id="15020-134">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="15020-135">Zuweisen einer Richtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="15020-135">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="15020-136">Sie sind neu bei Microsoft Teams und haben gerade erst begonnen, oder Sie müssen nur einer kleinen Anzahl von Benutzern eine oder mehrere Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-136">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="15020-137">Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im Skype for Business Online PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="15020-137">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="15020-138">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="15020-138">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="15020-139">Sie müssen bestimmten Gruppen von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-139">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="15020-140">Weisen Sie beispielsweise Lehrern in Ihrer Bildungseinrichtung das Richtlinienpaket Education (Teacher) zu, um Ihnen den vollständigen Zugriff auf Chats, Anrufe und Besprechungen sowie das Richtlinienpaket Education (Secondary School Student) für sekundäre Schüler zu gewähren, um bestimmte Funktionen wie private Anrufe.</span><span class="sxs-lookup"><span data-stu-id="15020-140">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="15020-141">Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="15020-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="15020-142">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="15020-142">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="15020-143">Sie müssen einem umfangreichen Satz von Benutzern Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-143">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="15020-144">So möchten Sie beispielsweise Hunderten oder tausenden Benutzern in Ihrer Organisation gleichzeitig eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-144">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="15020-145">PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="15020-145">PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="15020-146">[Zuweisen einer Richtlinie zu einer Gruppe](#assign-a-policy-to-a-group) (in der Vorschau)</span><span class="sxs-lookup"><span data-stu-id="15020-146">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="15020-147">Sie müssen Richtlinien basierend auf der Gruppenmitgliedschaft eines Benutzers zuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-147">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="15020-148">So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Organisationseinheit eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-148">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="15020-149">PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="15020-149">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="15020-150">Zuweisen eines Richtlinienpakets zu einem Batch von Benutzern (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="15020-150">Assign a policy package to a batch of users (coming soon)</span></span> |||
| <span data-ttu-id="15020-151">Zuweisen eines Richtlinienpakets zu einer Gruppe (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="15020-151">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="15020-152">Zuweisen einer Richtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="15020-152">Assign a policy to individual users</span></span>

<span data-ttu-id="15020-153">Führen Sie die folgenden Schritte aus, um einem einzelnen Benutzer oder einer kleinen Anzahl von Benutzern gleichzeitig eine Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-153">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="15020-154">Verwenden des Microsoft Teams admin Centers</span><span class="sxs-lookup"><span data-stu-id="15020-154">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="15020-155">So weisen Sie einem Benutzer eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="15020-155">To assign a policy to a user:</span></span>

1. <span data-ttu-id="15020-156">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="15020-156">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="15020-157">Wählen Sie den Benutzer aus, indem Sie links neben dem Benutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="15020-157">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="15020-158">Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="15020-158">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="15020-159">Wenn Sie bis zu 20 Benutzern gleichzeitig eine Richtlinie zuweisen möchten, lesen Sie [Bearbeiten der Benutzereinstellungen für Teams in Massen](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="15020-159">To assign a policy to up to 20 users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="15020-160">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="15020-160">Or, you can also do the following:</span></span>

1. <span data-ttu-id="15020-161">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zur Seite Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="15020-161">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="15020-162">Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, indem Sie links neben dem Richtliniennamen klicken.</span><span class="sxs-lookup"><span data-stu-id="15020-162">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="15020-163">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="15020-163">Select **Manage users**.</span></span>
4. <span data-ttu-id="15020-164">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="15020-164">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="15020-165">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="15020-165">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="15020-166">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="15020-166">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="15020-167">Verwenden von PowerShell</span><span class="sxs-lookup"><span data-stu-id="15020-167">Using PowerShell</span></span>

<span data-ttu-id="15020-168">Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Verwalten.</span><span class="sxs-lookup"><span data-stu-id="15020-168">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="15020-169">Verwenden Sie ```Grant-``` das Cmdlet für einen bestimmten Richtlinientyp, um die Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-169">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="15020-170">Verwenden Sie beispielsweise das ```Grant-CsTeamsMeetingPolicy``` Cmdlet, um Benutzern eine Teams-Besprechungsrichtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-170">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="15020-171">Diese Cmdlets sind Bestandteil des Skype for Business Online PowerShell-Moduls und werden im [Skype for Business-Cmdlet Reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="15020-171">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="15020-172">Laden Sie das [Skype for Business Online PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366) herunter, und installieren Sie es (falls noch nicht geschehen), und führen Sie dann die folgenden Schritte aus, um eine Verbindung mit Skype for Business Online herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="15020-172">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="15020-173">In diesem Beispiel weisen wir eine Teams-Besprechungsrichtlinie mit dem Namen "Student-Besprechungsrichtlinie" einem Benutzer mit dem Namen "Sie" zu.</span><span class="sxs-lookup"><span data-stu-id="15020-173">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="15020-174">Weitere Informationen finden Sie unter [Verwalten von Richtlinien über PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="15020-174">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="15020-175">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="15020-175">Assign a policy package</span></span>

<span data-ttu-id="15020-176">Ein Richtlinienpaket in Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die über die gleichen oder ähnlichen Rollen in Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="15020-176">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="15020-177">Jedes Richtlinienpaket ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die für diese Rolle typische Aktivitäten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="15020-177">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="15020-178">Einige Beispiele für Richtlinien Pakete sind das Paket "Education (Teacher)" und "Healthcare (Clinical Worker)".</span><span class="sxs-lookup"><span data-stu-id="15020-178">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="15020-179">Wenn Sie Benutzern ein Richtlinienpaket zuweisen, werden die Richtlinien im Paket erstellt, und Sie können dann die Einstellungen jeder Richtlinie im Paket anpassen, um die Anforderungen der Benutzer zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="15020-179">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="15020-180">Weitere Informationen zu Richtlinien Paketen, einschließlich Schritt-für-Schritt-Anleitungen zum Zuweisen und Verwalten dieser Pakete, finden Sie unter [Verwalten von Richtlinien Paketen in Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="15020-180">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="15020-181">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="15020-181">Assign a policy to a batch of users</span></span>
 
<span data-ttu-id="15020-182">Mit der Batch Richtlinienzuweisung können Sie eine Richtlinie für große Benutzergruppen gleichzeitig zuweisen, ohne ein Skript verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="15020-182">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="15020-183">Sie verwenden das ```New-CsBatchPolicyAssignmentOperationd``` Cmdlet, um einen Benutzer Batch und die Richtlinie, die Sie zuweisen möchten, zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="15020-183">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="15020-184">Die Aufgaben werden als Hintergrundvorgang verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.</span><span class="sxs-lookup"><span data-stu-id="15020-184">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="15020-185">Anschließend können Sie das ```Get-CsBatchPolicyAssignmentOperation``` Cmdlet verwenden, um den Fortschritt und den Status der Aufgaben in einem Batch zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="15020-185">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="15020-186">Ein Batch kann bis zu 20.000-Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="15020-186">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="15020-187">Sie können Benutzer nach ihrer Objekt-ID, dem Benutzerprinzipalnamen (User Principal Name, UPN), der SIP-Adresse (Session Initiation Protocol) oder der e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="15020-187">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="15020-188">Wir empfehlen derzeit, Richtlinien in Batches von 5.000-Benutzern gleichzeitig zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-188">We're currently recommending that you assign policies in batches of 5,000 users at a time.</span></span> <span data-ttu-id="15020-189">In Zeiten höherer Nachfrage können Verzögerungen bei der Verarbeitung auftreten.</span><span class="sxs-lookup"><span data-stu-id="15020-189">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="15020-190">Um die Auswirkungen dieser erhöhten Verarbeitungszeiten zu minimieren, empfehlen wir, kleinere Batchgrößen von bis zu 5.000-Benutzern zu übermitteln und jeden Batch erst nach Abschluss des vorherigen zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="15020-190">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="15020-191">Das Übermitteln von Batches außerhalb ihrer regulären Geschäftszeiten kann ebenfalls hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="15020-191">Submitting batches outside your regular business hours can also help.</span></span>

> [!NOTE]
> <span data-ttu-id="15020-192">Derzeit steht die Zuweisung von Batch Richtlinien für alle Teams-Richtlinientypen nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="15020-192">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="15020-193">Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) .</span><span class="sxs-lookup"><span data-stu-id="15020-193">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="15020-194">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="15020-194">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="15020-195">Führen Sie die folgenden Schritte aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams)zu installieren.</span><span class="sxs-lookup"><span data-stu-id="15020-195">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="15020-196">Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="15020-196">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="15020-197">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="15020-197">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="15020-198">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="15020-198">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="15020-199">Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul (optional)</span><span class="sxs-lookup"><span data-stu-id="15020-199">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="15020-200">Möglicherweise möchten Sie auch [das Azure AD PowerShell für Graph-Modul](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (falls noch nicht geschehen) herunterladen und installieren und eine Verbindung mit Azure AD herstellen, damit Sie eine Liste der Benutzer in Ihrer Organisation abrufen können.</span><span class="sxs-lookup"><span data-stu-id="15020-200">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="15020-201">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.</span><span class="sxs-lookup"><span data-stu-id="15020-201">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="15020-202">Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung zu Teams verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="15020-202">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="15020-203">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="15020-203">Assign a policy to a batch of users</span></span>

<span data-ttu-id="15020-204">In diesem Beispiel verwenden wir das ```New-CsBatchPolicyAssignmentOperation``` Cmdlet, um eine APP-Setup Richtlinie mit dem Namen "HR-App-Setup Richtlinie" einem Batch von Benutzern zuzuweisen, die in der Datei "Users_ids. Text" aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="15020-204">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="15020-205">In diesem Beispiel stellen wir eine Verbindung mit Azure AD her, um eine Sammlung von Benutzern abzurufen, und weisen dann eine Messagingrichtlinie mit dem Namen "New Hire Messaging Policy" einem Batch von Benutzern zu, die mithilfe Ihres UPNs angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="15020-205">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="15020-206">Weitere Informationen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="15020-206">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="15020-207">Abrufen des Status einer Stapelverarbeitungs Zuordnung</span><span class="sxs-lookup"><span data-stu-id="15020-207">Get the status of a batch assignment</span></span>

<span data-ttu-id="15020-208">Führen Sie die folgenden Schritte aus, um den Status einer Stapelverarbeitungs Zuweisung abzurufen, wobei Vorgangskennung die Vorgangs-ID ist ```New-CsBatchPolicyAssignmentOperation``` , die vom Cmdlet für einen bestimmten Batch zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="15020-208">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="15020-209">Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie die folgenden Schritte aus, um weitere Informationen zu ```UserState``` Fehlern zu erhalten, die in der Eigenschaft enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="15020-209">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="15020-210">Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="15020-210">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="15020-211">Zuweisen einer Richtlinie zu einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="15020-211">Assign a policy to a group</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="15020-212">Mit der Richtlinienzuweisung zu Gruppen können Sie einer Gruppe von Benutzern eine Richtlinie zuweisen, beispielsweise eine Sicherheitsgruppe oder eine Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="15020-212">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="15020-213">Die Richtlinienzuweisung wird nach Rangfolgeregeln an Mitglieder der Gruppe weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="15020-213">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="15020-214">Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden Ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="15020-214">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="15020-215">Sie verwenden das ```New-CsGroupPolicyAssignment``` Cmdlet, um einer Gruppe eine Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-215">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="15020-216">Sie können eine Gruppe mithilfe der Objekt-ID, der SIP-Adresse oder der e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="15020-216">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="15020-217">Wenn Sie die Richtlinie zuweisen, wird Sie sofort der Gruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="15020-217">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="15020-218">Beachten Sie jedoch, dass die Verteilung der Richtlinienzuweisung an Mitglieder der Gruppe als Hintergrundvorgang ausgeführt wird und je nach Größe der Gruppe einige Zeit in Anspruch nehmen kann.</span><span class="sxs-lookup"><span data-stu-id="15020-218">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="15020-219">Das gleiche gilt, wenn eine Richtlinie aus einer Gruppe nicht zugewiesen wird oder wenn Mitglieder einer Gruppe hinzugefügt oder aus ihr entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="15020-219">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="15020-220">Derzeit steht die Richtlinienzuweisung zu Gruppen nicht für alle Teams-Richtlinientypen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="15020-220">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="15020-221">Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .</span><span class="sxs-lookup"><span data-stu-id="15020-221">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="15020-222">Was Sie über die Richtlinienzuweisung zu Gruppen wissen müssen</span><span class="sxs-lookup"><span data-stu-id="15020-222">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="15020-223">Bevor Sie beginnen, ist es wichtig, die Rangfolge von Prioritätsregeln und die Rangfolge von Gruppenaufgaben zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="15020-223">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="15020-224">Rangfolgeregeln</span><span class="sxs-lookup"><span data-stu-id="15020-224">Precedence rules</span></span>

<span data-ttu-id="15020-225">Für einen bestimmten Richtlinientyp wird die effektive Richtlinie eines Benutzers entsprechend den folgenden Bedingungen bestimmt:</span><span class="sxs-lookup"><span data-stu-id="15020-225">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="15020-226">Eine Richtlinie, die einem Benutzer direkt zugewiesen ist, hat Vorrang vor jeder anderen Richtlinie desselben Typs, die einer Gruppe zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15020-226">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="15020-227">Anders ausgedrückt: Wenn einem Benutzer eine Richtlinie eines bestimmten Typs direkt zugewiesen wird, erbt dieser Benutzer keine Richtlinie desselben Typs aus einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="15020-227">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="15020-228">Dies bedeutet auch, dass Sie diese Richtlinie vom Benutzer entfernen müssen, bevor Sie eine Richtlinie desselben Typs aus einer Gruppe erben können, wenn ein Benutzer über eine Richtlinie eines bestimmten Typs verfügt, der Ihnen direkt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="15020-228">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="15020-229">Wenn einem Benutzer nicht direkt eine Richtlinie zugewiesen wurde und es sich um ein Mitglied von zwei oder mehr Gruppen handelt und für jede Gruppe eine Richtlinie desselben Typs zugewiesen ist, erbt der Benutzer die Richtlinie der Gruppenaufgabe, die die höchste Rangfolge aufweist.</span><span class="sxs-lookup"><span data-stu-id="15020-229">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="15020-230">Wenn ein Benutzer nicht Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, gilt die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="15020-230">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="15020-231">Die effektive Richtlinie eines Benutzers wird entsprechend diesen Regeln aktualisiert, wenn ein Benutzer zu einer Gruppe hinzugefügt oder daraus entfernt wird, der eine Richtlinie zugewiesen ist, eine Richtlinie von einer Gruppe nicht zugewiesen wird oder eine Richtlinie entfernt wird, die dem Benutzer direkt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15020-231">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="15020-232">Gruppen Zuordnungs Rangfolge</span><span class="sxs-lookup"><span data-stu-id="15020-232">Group assignment ranking</span></span>
 
<span data-ttu-id="15020-233">Wenn Sie einer Gruppe eine Richtlinie zuweisen, geben Sie eine Rangfolge für die Gruppenzuordnung an.</span><span class="sxs-lookup"><span data-stu-id="15020-233">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="15020-234">Damit wird ermittelt, welche Richtlinie ein Benutzer als effektive Richtlinie erben soll, wenn der Benutzer ein Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15020-234">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="15020-235">Die Rangfolge der Gruppenzuweisungen ist relativ zu anderen Gruppenzuordnungen desselben Typs.</span><span class="sxs-lookup"><span data-stu-id="15020-235">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="15020-236">Wenn Sie beispielsweise zwei Gruppen eine Anrufrichtlinie zuweisen, legen Sie die Rangfolge einer Zuordnung auf 1 und die andere auf 2, wobei 1 die höchste Rangliste ist.</span><span class="sxs-lookup"><span data-stu-id="15020-236">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="15020-237">Die Gruppen Zuordnungs Rangfolge gibt an, welche Gruppenmitgliedschaft wichtiger oder relevanter als andere Gruppenmitgliedschaften im Hinblick auf die Vererbung ist.</span><span class="sxs-lookup"><span data-stu-id="15020-237">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="15020-238">Angenommen, Sie verfügen über zwei Gruppen, Store-Mitarbeiter und Store-Manager.</span><span class="sxs-lookup"><span data-stu-id="15020-238">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="15020-239">Beiden Gruppen wird eine Anrufrichtlinie für Teams zugewiesen, und Sie können die Anruf Richtlinien für die Mitarbeiter und die Geschäftsmanager anrufen.</span><span class="sxs-lookup"><span data-stu-id="15020-239">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="15020-240">Bei einem Store Manager, der sich in beiden Gruppen befindet, ist ihre Rolle als Manager relevanter als ihre Rolle als Mitarbeiter, sodass die Anrufrichtlinie, die der Gruppe Store Managers zugewiesen ist, eine höhere Rangfolge aufweisen sollte.</span><span class="sxs-lookup"><span data-stu-id="15020-240">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="15020-241">Gruppe</span><span class="sxs-lookup"><span data-stu-id="15020-241">Group</span></span> |<span data-ttu-id="15020-242">Anruf Richtlinienname für Teams</span><span class="sxs-lookup"><span data-stu-id="15020-242">Teams calling policy name</span></span>  |<span data-ttu-id="15020-243">Rang</span><span class="sxs-lookup"><span data-stu-id="15020-243">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="15020-244">Store-Manager</span><span class="sxs-lookup"><span data-stu-id="15020-244">Store Managers</span></span>   |<span data-ttu-id="15020-245">Anruf Richtlinien für Store-Manager</span><span class="sxs-lookup"><span data-stu-id="15020-245">Store Managers Calling Policy</span></span>         |<span data-ttu-id="15020-246">1</span><span class="sxs-lookup"><span data-stu-id="15020-246">1</span></span>|
|<span data-ttu-id="15020-247">Speichern von Mitarbeitern</span><span class="sxs-lookup"><span data-stu-id="15020-247">Store Employees</span></span>    |<span data-ttu-id="15020-248">Speichern von Mitarbeiter Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="15020-248">Store Employees Calling Policy</span></span>      |<span data-ttu-id="15020-249">2</span><span class="sxs-lookup"><span data-stu-id="15020-249">2</span></span>|

<span data-ttu-id="15020-250">Wenn Sie kein Ranking angeben, erhält die Richtlinienzuweisung die niedrigste Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="15020-250">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="15020-251">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="15020-251">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="15020-252">Die Cmdlets befinden sich in der Pre-Release-Version des Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="15020-252">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="15020-253">Führen Sie die folgenden Schritte aus, um zunächst die allgemein verfügbare Version des Teams PowerShell-Moduls (sofern installiert) zu deinstallieren, und installieren Sie dann die neueste Vorabversion des Moduls aus dem PowerShell-Test Katalog.</span><span class="sxs-lookup"><span data-stu-id="15020-253">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="15020-254">Wenn Sie dies noch nicht getan haben, führen Sie die folgenden Schritte aus, um den PowerShell-Test Katalog als vertrauenswürdige Quelle zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="15020-254">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="15020-255">Wenn Sie die allgemein verfügbare Version des Teams PowerShell-Moduls installiert haben, führen Sie die folgenden Schritte aus, um Sie zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="15020-255">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="15020-256">Führen Sie die folgenden Schritte aus, um das aktuelle Microsoft Teams PowerShell-Modul aus dem PowerShell-Test Katalog zu installieren.</span><span class="sxs-lookup"><span data-stu-id="15020-256">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="15020-257">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="15020-257">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="15020-258">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="15020-258">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="15020-259">Zuweisen einer Richtlinie zu einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="15020-259">Assign a policy to a group</span></span>

<span data-ttu-id="15020-260">In diesem Beispiel verwenden wir das ```New-CsGroupPolicyAssignment``` Cmdlet, um einer Gruppe mit einer Zuordnungs Rangfolge von 1 eine Teams-Besprechungsrichtlinie mit dem Namen "Einzelhandels Manager-Besprechungsrichtlinie" zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="15020-260">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="15020-261">Weitere Informationen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="15020-261">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="15020-262">Abrufen von Richtlinienzuweisungen für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="15020-262">Get policy assignments for a group</span></span>

<span data-ttu-id="15020-263">Verwenden Sie ```Get-CsGroupPolicyAssignment``` das Cmdlet, um alle Richtlinien abzurufen, die einer Gruppe zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="15020-263">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="15020-264">Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgeführt werden, auch wenn die SIP-Adresse oder e-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="15020-264">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="15020-265">In diesem Beispiel rufen wir alle Richtlinien ab, die einer bestimmten Gruppe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="15020-265">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="15020-266">In diesem Beispiel geben wir alle Gruppen zurück, denen eine Teams-Besprechungsrichtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15020-266">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="15020-267">Weitere Informationen finden Sie unter [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="15020-267">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="15020-268">Entfernen einer Richtlinie aus einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="15020-268">Remove a policy from a group</span></span>

<span data-ttu-id="15020-269">Verwenden Sie ```Remove-CsGroupPolicyAssignment``` das Cmdlet, um eine Richtlinie aus einer Gruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="15020-269">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="15020-270">Wenn Sie eine Richtlinie aus einer Gruppe entfernen, werden die Prioritäten anderer Richtlinien desselben Typs, die dieser Gruppe zugewiesen sind und die eine niedrigere Rangfolge aufweisen, aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="15020-270">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="15020-271">Wenn Sie beispielsweise eine Richtlinie entfernen, die eine Rangfolge von 2 aufweist, werden Richtlinien mit einer Rangfolge von 3 und 4 aktualisiert, um Ihre neue Rangfolge wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="15020-271">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="15020-272">In den beiden folgenden Tabellen wird dieses Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="15020-272">The following two tables show this example.</span></span>

<span data-ttu-id="15020-273">Nachfolgend finden Sie eine Liste der Richtlinienzuweisungen und Prioritäten für eine Team-Besprechungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="15020-273">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="15020-274">Gruppenname</span><span class="sxs-lookup"><span data-stu-id="15020-274">Group name</span></span>  |<span data-ttu-id="15020-275">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="15020-275">Policy name</span></span>  |<span data-ttu-id="15020-276">Rang</span><span class="sxs-lookup"><span data-stu-id="15020-276">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="15020-277">Vertrieb</span><span class="sxs-lookup"><span data-stu-id="15020-277">Sales</span></span>    |<span data-ttu-id="15020-278">Vertriebsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="15020-278">Sales policy</span></span>       | <span data-ttu-id="15020-279">1</span><span class="sxs-lookup"><span data-stu-id="15020-279">1</span></span>        |
|<span data-ttu-id="15020-280">Region West</span><span class="sxs-lookup"><span data-stu-id="15020-280">West Region</span></span>     |<span data-ttu-id="15020-281">West Regions-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="15020-281">West Region policy</span></span>         |<span data-ttu-id="15020-282">2</span><span class="sxs-lookup"><span data-stu-id="15020-282">2</span></span>         |
|<span data-ttu-id="15020-283">Division</span><span class="sxs-lookup"><span data-stu-id="15020-283">Division</span></span>    |<span data-ttu-id="15020-284">Abteilungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="15020-284">Division policy</span></span>         |<span data-ttu-id="15020-285">3</span><span class="sxs-lookup"><span data-stu-id="15020-285">3</span></span>         |
|<span data-ttu-id="15020-286">Tochter</span><span class="sxs-lookup"><span data-stu-id="15020-286">Subsidiary</span></span>   |<span data-ttu-id="15020-287">Subsidiäre Richtlinie</span><span class="sxs-lookup"><span data-stu-id="15020-287">Subsidiary policy</span></span>        |<span data-ttu-id="15020-288">4</span><span class="sxs-lookup"><span data-stu-id="15020-288">4</span></span>         |

<span data-ttu-id="15020-289">Wenn die West Region-Richtlinie aus der Gruppe "West Region" entfernt wird, werden die Richtlinienzuweisungen und-Prioritäten wie folgt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="15020-289">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="15020-290">Gruppenname</span><span class="sxs-lookup"><span data-stu-id="15020-290">Group name</span></span>  |<span data-ttu-id="15020-291">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="15020-291">Policy name</span></span>  |<span data-ttu-id="15020-292">Rang</span><span class="sxs-lookup"><span data-stu-id="15020-292">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="15020-293">Vertrieb</span><span class="sxs-lookup"><span data-stu-id="15020-293">Sales</span></span>    |<span data-ttu-id="15020-294">Vertriebsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="15020-294">Sales policy</span></span>       | <span data-ttu-id="15020-295">1</span><span class="sxs-lookup"><span data-stu-id="15020-295">1</span></span>        |
|<span data-ttu-id="15020-296">Division</span><span class="sxs-lookup"><span data-stu-id="15020-296">Division</span></span>    |<span data-ttu-id="15020-297">Abteilungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="15020-297">Division policy</span></span>         |<span data-ttu-id="15020-298">2</span><span class="sxs-lookup"><span data-stu-id="15020-298">2</span></span>         |
|<span data-ttu-id="15020-299">Tochter</span><span class="sxs-lookup"><span data-stu-id="15020-299">Subsidiary</span></span>   |<span data-ttu-id="15020-300">Subsidiäre Richtlinie</span><span class="sxs-lookup"><span data-stu-id="15020-300">Subsidiary policy</span></span>        |<span data-ttu-id="15020-301">3</span><span class="sxs-lookup"><span data-stu-id="15020-301">3</span></span>        |

<span data-ttu-id="15020-302">In diesem Beispiel entfernen wir die Besprechungsrichtlinie für Teams aus einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="15020-302">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="15020-303">Weitere Informationen finden Sie unter [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="15020-303">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="15020-304">Ändern einer Richtlinien Aufgabe für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="15020-304">Change a policy assignment for a group</span></span>

<span data-ttu-id="15020-305">Nachdem Sie einer Gruppe eine Richtlinie zugewiesen haben, können Sie das ```Set-CsGroupPolicyAssignmentd``` Cmdlet verwenden, um die Richtlinienzuweisung dieser Gruppe wie folgt zu ändern:</span><span class="sxs-lookup"><span data-stu-id="15020-305">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="15020-306">Ändern der Rangfolge</span><span class="sxs-lookup"><span data-stu-id="15020-306">Change the ranking</span></span>
- <span data-ttu-id="15020-307">Ändern der Richtlinie eines bestimmten Richtlinientyps</span><span class="sxs-lookup"><span data-stu-id="15020-307">Change the policy of a given policy type</span></span>
- <span data-ttu-id="15020-308">Ändern der Richtlinie eines bestimmten Richtlinientyps und der Rangfolge</span><span class="sxs-lookup"><span data-stu-id="15020-308">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="15020-309">In diesem Beispiel ändern wir die Richtlinie für die Anruf Park Richtlinie einer Gruppe in eine Richtlinie mit dem Namen SupportCallPark und die Zuordnungs Rangfolge auf 3.</span><span class="sxs-lookup"><span data-stu-id="15020-309">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="15020-310">Weitere Informationen finden Sie unter [Satz-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="15020-310">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="15020-311">Ändern der effektiven Richtlinie für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="15020-311">Change the effective policy for a user</span></span>

<span data-ttu-id="15020-312">Im folgenden finden Sie ein Beispiel für das Ändern der effektiven Richtlinie für einen Benutzer, dem eine Richtlinie direkt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="15020-312">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="15020-313">Zunächst verwenden wir das ```Get-CsUserPolicyAssignment``` Cmdlet zusammen mit dem ```PolicySource``` Parameter, um Details zu den Broadcast Richtlinien für Teams zu erhalten, die dem Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="15020-313">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="15020-314">Weitere Informationen finden Sie unter [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="15020-314">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="15020-315">Die Ausgabe zeigt, dass dem Benutzer direkt eine Team-Broadcast Richtlinie mit dem Namen "Employee Events" zugewiesen wurde, die Vorrang vor der Richtlinie namens "Vendor Live Events" hat, die einer Gruppe zugeordnet ist, der der Benutzer angehört.</span><span class="sxs-lookup"><span data-stu-id="15020-315">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="15020-316">Jetzt entfernen wir die Mitarbeiter-Ereignis Richtlinie des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="15020-316">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="15020-317">Das bedeutet, dass der Benutzer nicht mehr über eine Broadcast Richtlinie für Teams verfügt, die Ihnen direkt zugewiesen wurde, und erbt die Richtlinie für Anbieter-Live Ereignisse, die der Gruppe zugewiesen ist, der der Benutzer angehört.</span><span class="sxs-lookup"><span data-stu-id="15020-317">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="15020-318">Verwenden Sie dazu das folgende Cmdlet im Skype for Business PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="15020-318">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="15020-319">Sie können das folgende Cmdlet im Teams PowerShell-Modul verwenden, um dies bei einer Batch Richtlinienzuweisung zu tun, wobei $users eine Liste der von Ihnen angegebenen Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="15020-319">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a><span data-ttu-id="15020-320">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="15020-320">Related topics</span></span>

- [<span data-ttu-id="15020-321">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="15020-321">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)