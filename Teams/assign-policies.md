---
title: Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
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
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: ae007641734b71a34d9021283704d6b210626a28
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410460"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="eee0d-103">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eee0d-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="eee0d-104">**Eines der in diesem Artikel behandelten Features von Microsoft Teams, [Richtlinienzuweisung zu Gruppen](#assign-a-policy-to-a-group), ist derzeit nur in der privaten Vorschau verfügbar. Die PowerShell-Cmdlets für dieses Feature befinden sich im PowerShell-Modul für Teams vor der Freigabe.**</span><span class="sxs-lookup"><span data-stu-id="eee0d-104">**One of the Microsoft Teams features discussed in this article, [policy assignment to groups](#assign-a-policy-to-a-group), is currently only available in private preview. The Powershell cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span> <span data-ttu-id="eee0d-105">Wenn Sie den Veröffentlichungsstatus dieser Funktion auf dem neuesten Stand halten möchten, lesen Sie die [Roadmap für Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span><span class="sxs-lookup"><span data-stu-id="eee0d-105">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="eee0d-106">Als Administrator verwenden Sie Richtlinien, um die Teamfunktionen zu steuern, die Benutzern in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-106">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="eee0d-107">So gibt es beispielsweise Anruf Richtlinien, Besprechungsrichtlinien und Messagingrichtlinien, um nur einige zu nennen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-107">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="eee0d-108">Organisationen verfügen über unterschiedliche Arten von Benutzern mit eindeutigen Anforderungen und benutzerdefinierten Richtlinien, die Sie erstellen und zuweisen, damit Sie die Richtlinieneinstellungen basierend auf den Anforderungen an unterschiedliche Benutzergruppen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="eee0d-108">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="eee0d-109">Um das Verwalten von Richtlinien in Ihrer Organisation zu vereinfachen, bietet Teams verschiedene Möglichkeiten, Richtlinien für Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-109">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="eee0d-110">Sie können Benutzern eine Richtlinie entweder einzeln oder im Maßstab über eine Batch Zuordnung oder einer Gruppe, der der Benutzer angehört, direkt zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-110">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the user is a member of.</span></span> <span data-ttu-id="eee0d-111">Sie können auch Richtlinien Pakete verwenden, um Benutzern in Ihrer Organisation, die über ähnliche Rollen verfügen, eine vordefinierte Sammlung von Richtlinien zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-111">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="eee0d-112">Die von Ihnen ausgewählte Option richtet sich nach der Anzahl der Richtlinien, die Sie verwalten, und der Anzahl der Benutzer, denen Sie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-112">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span>

<span data-ttu-id="eee0d-113">In diesem Artikel werden die verschiedenen Möglichkeiten beschrieben, wie Sie Benutzern Richtlinien zuweisen können, sowie die empfohlenen Szenarien für die Verwendung von was.</span><span class="sxs-lookup"><span data-stu-id="eee0d-113">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="eee0d-114">Welche Richtlinie hat Vorrang?</span><span class="sxs-lookup"><span data-stu-id="eee0d-114">Which policy takes precedence?</span></span>

<span data-ttu-id="eee0d-115">Ein Benutzer verfügt über eine gültige Richtlinie für die einzelnen Richtlinientypen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-115">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="eee0d-116">Es ist möglich oder sogar wahrscheinlich, dass einem Benutzer direkt eine Richtlinie zugewiesen wird, und er ist auch ein Mitglied einer oder mehrerer Gruppen, denen eine Richtlinie desselben Typs zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-116">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="eee0d-117">Welche Richtlinie hat in diesen Szenarien Vorrang?</span><span class="sxs-lookup"><span data-stu-id="eee0d-117">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="eee0d-118">Die effektive Richtlinie eines Benutzers wird wie folgt gemäß den Regeln für die Rangfolge bestimmt.</span><span class="sxs-lookup"><span data-stu-id="eee0d-118">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="eee0d-119">Wenn einem Benutzer direkt eine Richtlinie zugewiesen wird (entweder einzeln oder über eine Batch Zuordnung), hat diese Richtlinie Vorrang.</span><span class="sxs-lookup"><span data-stu-id="eee0d-119">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="eee0d-120">Im folgenden Beispiel ist die effektive Richtlinie des Benutzers die Lincoln Square-Besprechungsrichtlinie, die dem Benutzer direkt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-120">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![Diagramm, das zeigt, wie eine direkt zugewiesene Richtlinie Vorrang hat](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="eee0d-122">Wenn einem Benutzer keine Richtlinie eines bestimmten Typs direkt zugewiesen wird, hat die der Gruppe zugewiesene Richtlinie Vorrang.</span><span class="sxs-lookup"><span data-stu-id="eee0d-122">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="eee0d-123">Wenn ein Benutzer ein Mitglied mehrerer Gruppen ist, hat die Richtlinie, die die höchste [Gruppen Zuordnungs Rangfolge](#group-assignment-ranking) für den angegebenen Richtlinientyp aufweist, Vorrang.</span><span class="sxs-lookup"><span data-stu-id="eee0d-123">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="eee0d-124">In diesem Beispiel ist die effektive Richtlinie des Benutzers die Exec Teams-und HD-Richtlinie, die die höchste Zuordnungs Rangfolge relativ zu anderen Gruppen aufweist, in der der Benutzer Mitglied ist und dem auch eine Richtlinie desselben Richtlinientyps zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-124">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![Diagramm, das zeigt, wie eine von Group geerbte Richtlinie Vorrang hat](media/assign-policies-example-group.png)

<span data-ttu-id="eee0d-126">Wenn einem Benutzer keine Richtlinie direkt zugewiesen wurde oder kein Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, erhält der Benutzer die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="eee0d-126">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="eee0d-127">Hier ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="eee0d-127">Here's an example.</span></span>

![Diagramm, das zeigt, wie eine globale Richtlinie Vorrang hat](media/assign-policies-example-global.png)

<span data-ttu-id="eee0d-129">Weitere Informationen finden Sie unter [Prioritätsregeln](#precedence-rules).</span><span class="sxs-lookup"><span data-stu-id="eee0d-129">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="eee0d-130">Methoden zum Zuweisen von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="eee0d-130">Ways to assign policies</span></span>

<span data-ttu-id="eee0d-131">Im folgenden finden Sie eine Übersicht über die Methoden zum Zuweisen von Richtlinien zu Benutzern sowie zu den empfohlenen Szenarien für die einzelnen Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eee0d-131">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="eee0d-132">Klicken Sie auf die Links, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eee0d-132">Click the links to learn more.</span></span>

|<span data-ttu-id="eee0d-133">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="eee0d-133">Do this</span></span>  |<span data-ttu-id="eee0d-134">Wenn...</span><span class="sxs-lookup"><span data-stu-id="eee0d-134">If...</span></span>  | <span data-ttu-id="eee0d-135">Verwenden von...</span><span class="sxs-lookup"><span data-stu-id="eee0d-135">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="eee0d-136">Zuweisen einer Richtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="eee0d-136">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="eee0d-137">Sie sind neu bei Microsoft Teams und haben gerade erst begonnen, oder Sie müssen nur einer kleinen Anzahl von Benutzern eine oder mehrere Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-137">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="eee0d-138">Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im Skype for Business Online PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="eee0d-138">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="eee0d-139">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="eee0d-139">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="eee0d-140">Sie müssen bestimmten Gruppen von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-140">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="eee0d-141">Weisen Sie beispielsweise Lehrern in Ihrer Bildungseinrichtung das Richtlinienpaket Education (Teacher) zu, um Ihnen den vollständigen Zugriff auf Chats, Anrufe und Besprechungen sowie das Richtlinienpaket Education (Secondary School Student) für sekundäre Schüler zu gewähren, um bestimmte Funktionen wie private Anrufe zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-141">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="eee0d-142">Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="eee0d-142">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="eee0d-143">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="eee0d-143">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="eee0d-144">Sie müssen einem umfangreichen Satz von Benutzern Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-144">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="eee0d-145">So möchten Sie beispielsweise Hunderten oder tausenden Benutzern in Ihrer Organisation gleichzeitig eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-145">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="eee0d-146">Das Microsoft Teams Admin Center oder PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="eee0d-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|<span data-ttu-id="eee0d-147">[Zuweisen einer Richtlinie zu einer Gruppe](#assign-a-policy-to-a-group) (in der Vorschau)</span><span class="sxs-lookup"><span data-stu-id="eee0d-147">[Assign a policy to a group](#assign-a-policy-to-a-group) (in preview)</span></span>   |<span data-ttu-id="eee0d-148">Sie müssen Richtlinien basierend auf der Gruppenmitgliedschaft eines Benutzers zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-148">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="eee0d-149">So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe oder Organisationseinheit eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-149">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="eee0d-150">PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="eee0d-150">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="eee0d-151">Zuweisen eines Richtlinienpakets zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="eee0d-151">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="eee0d-152">Sie müssen einem Batch von Benutzern in Ihrer Organisation, die über die gleichen oder ähnliche Rollen verfügen, mehrere Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-152">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="eee0d-153">Weisen Sie beispielsweise das Richtlinienpaket Education (Teacher) allen Lehrern in ihrer Schule mithilfe der Batch Zuweisung zu, damit Sie Vollzugriff auf Chats, Anrufe und Besprechungen erhalten und das Richtlinienpaket Education (Secondary School Student) einem Batch von sekundären Kursteilnehmern zuweisen können, um bestimmte Funktionen wie private Anrufe zu begrenzen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-153">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="eee0d-154">PowerShell-Cmdlets im PowerShell-Modul von Teams</span><span class="sxs-lookup"><span data-stu-id="eee0d-154">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="eee0d-155">Zuweisen eines Richtlinienpakets zu einer Gruppe (in Kürze verfügbar)</span><span class="sxs-lookup"><span data-stu-id="eee0d-155">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="eee0d-156">Zuweisen einer Richtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="eee0d-156">Assign a policy to individual users</span></span>

<span data-ttu-id="eee0d-157">Führen Sie die folgenden Schritte aus, um einem einzelnen Benutzer oder einer kleinen Anzahl von Benutzern gleichzeitig eine Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-157">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="eee0d-158">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="eee0d-158">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="eee0d-159">So weisen Sie einem Benutzer eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="eee0d-159">To assign a policy to a user:</span></span>

1. <span data-ttu-id="eee0d-160">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</span><span class="sxs-lookup"><span data-stu-id="eee0d-160">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="eee0d-161">Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="eee0d-161">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="eee0d-162">Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, und klicken Sie dann auf über **nehmen**.</span><span class="sxs-lookup"><span data-stu-id="eee0d-162">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="eee0d-163">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="eee0d-163">Or, you can also do the following:</span></span>

1. <span data-ttu-id="eee0d-164">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zur Seite Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="eee0d-164">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="eee0d-165">Wählen Sie die Richtlinie aus, die Sie zuweisen möchten, indem Sie links neben dem Richtliniennamen klicken.</span><span class="sxs-lookup"><span data-stu-id="eee0d-165">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="eee0d-166">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="eee0d-166">Select **Manage users**.</span></span>
4. <span data-ttu-id="eee0d-167">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="eee0d-167">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="eee0d-168">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-168">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="eee0d-169">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="eee0d-169">When you're finished adding users, select **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="eee0d-170">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="eee0d-170">Using PowerShell</span></span>

<span data-ttu-id="eee0d-171">Jeder Richtlinientyp verfügt über einen eigenen Satz von Cmdlets zum Verwalten.</span><span class="sxs-lookup"><span data-stu-id="eee0d-171">Each policy type has it's own set of cmdlets for managing it.</span></span> <span data-ttu-id="eee0d-172">Verwenden Sie das ```Grant-``` Cmdlet für einen bestimmten Richtlinientyp, um die Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-172">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="eee0d-173">Verwenden Sie beispielsweise das ```Grant-CsTeamsMeetingPolicy``` Cmdlet, um Benutzern eine Teams-Besprechungsrichtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-173">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="eee0d-174">Diese Cmdlets sind Bestandteil des Skype for Business Online PowerShell-Moduls und werden im [Skype for Business-Cmdlet Reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="eee0d-174">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="eee0d-175">Laden Sie das [Skype for Business Online PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366) herunter, und installieren Sie es (falls noch nicht geschehen), und führen Sie dann die folgenden Schritte aus, um eine Verbindung mit Skype for Business Online herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="eee0d-175">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="eee0d-176">In diesem Beispiel weisen wir eine Teams-Besprechungsrichtlinie mit dem Namen "Student-Besprechungsrichtlinie" einem Benutzer mit dem Namen "Sie" zu.</span><span class="sxs-lookup"><span data-stu-id="eee0d-176">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="eee0d-177">Weitere Informationen finden Sie unter [Verwalten von Richtlinien über PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span><span class="sxs-lookup"><span data-stu-id="eee0d-177">To learn more, see [Managing policies via PowerShell](teams-powershell-overview.md#managing-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="eee0d-178">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="eee0d-178">Assign a policy package</span></span>

<span data-ttu-id="eee0d-179">Ein Richtlinienpaket in Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die über die gleichen oder ähnlichen Rollen in Ihrer Organisation verfügen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-179">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="eee0d-180">Jedes Richtlinienpaket ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die für diese Rolle typische Aktivitäten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-180">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="eee0d-181">Einige Beispiele für Richtlinien Pakete sind das Paket "Education (Teacher)" und "Healthcare (Clinical Worker)".</span><span class="sxs-lookup"><span data-stu-id="eee0d-181">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="eee0d-182">Wenn Sie Benutzern ein Richtlinienpaket zuweisen, werden die Richtlinien im Paket erstellt, und Sie können dann die Einstellungen jeder Richtlinie im Paket anpassen, um die Anforderungen der Benutzer zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-182">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="eee0d-183">Weitere Informationen zu Richtlinien Paketen, einschließlich Schritt-für-Schritt-Anleitungen zum Zuweisen und Verwalten dieser Pakete, finden Sie unter [Verwalten von Richtlinien Paketen in Teams](manage-policy-packages.md).</span><span class="sxs-lookup"><span data-stu-id="eee0d-183">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="eee0d-184">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="eee0d-184">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="eee0d-185">Verwenden des Microsoft Teams Admin Centers</span><span class="sxs-lookup"><span data-stu-id="eee0d-185">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="eee0d-186">So weisen Sie Benutzern eine Richtlinie in Massen zu:</span><span class="sxs-lookup"><span data-stu-id="eee0d-186">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="eee0d-187">Wählen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center die Option **Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="eee0d-187">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="eee0d-188">Suchen Sie nach den Benutzern, denen Sie die Richtlinie zuweisen möchten, oder Filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-188">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="eee0d-189">Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="eee0d-189">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="eee0d-190">Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).</span><span class="sxs-lookup"><span data-stu-id="eee0d-190">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="eee0d-191">Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="eee0d-191">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="eee0d-192">Wenn Sie den Status Ihrer Richtlinienzuweisung anzeigen möchten, klicken Sie in dem Banner, das oben auf der Seite " **Benutzer** " angezeigt wird, nachdem Sie auf über **nehmen** klicken, um Ihre Richtlinien Aufgabe zu übermitteln, auf **Aktivitätsprotokoll**.</span><span class="sxs-lookup"><span data-stu-id="eee0d-192">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="eee0d-193">Oder klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Dashboard**, und klicken Sie dann unter **Aktivitätsprotokoll**auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="eee0d-193">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="eee0d-194">Das Aktivitätsprotokoll zeigt Richtlinienzuweisungen für Stapel von mehr als 20 Benutzern über das Microsoft Teams Admin Center der letzten 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="eee0d-194">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="eee0d-195">Weitere Informationen finden Sie unter [Anzeigen der Richtlinienzuweisungen im Aktivitätsprotokoll](activity-log.md).</span><span class="sxs-lookup"><span data-stu-id="eee0d-195">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="eee0d-196">Verwendung von PowerShell</span><span class="sxs-lookup"><span data-stu-id="eee0d-196">Using PowerShell</span></span>
 
<span data-ttu-id="eee0d-197">Mit der Batch Richtlinienzuweisung können Sie eine Richtlinie für große Benutzergruppen gleichzeitig zuweisen, ohne ein Skript verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-197">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="eee0d-198">Sie verwenden das ```New-CsBatchPolicyAssignmentOperationd``` Cmdlet, um einen Benutzer Batch und die Richtlinie, die Sie zuweisen möchten, zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="eee0d-198">You use the ```New-CsBatchPolicyAssignmentOperationd``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="eee0d-199">Die Aufgaben werden als Hintergrundvorgang verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.</span><span class="sxs-lookup"><span data-stu-id="eee0d-199">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="eee0d-200">Anschließend können Sie das ```Get-CsBatchPolicyAssignmentOperation``` Cmdlet verwenden, um den Fortschritt und den Status der Aufgaben in einem Batch zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-200">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span> 

<span data-ttu-id="eee0d-201">Sie können Benutzer nach ihrer Objekt-ID, dem Benutzerprinzipalnamen (User Principal Name, UPN), der SIP-Adresse (Session Initiation Protocol) oder der e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="eee0d-201">You can specify users by their object Id, user principal name (UPN), Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="eee0d-202">Wenn ein Batch doppelte Benutzer enthält, werden die Duplikate aus dem Batch entfernt, bevor die Verarbeitung und der Status nur für die eindeutigen Benutzer bereitgestellt wird, die im Batch verbleiben.</span><span class="sxs-lookup"><span data-stu-id="eee0d-202">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="eee0d-203">Ein Batch kann bis zu 5.000-Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="eee0d-203">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="eee0d-204">Um optimale Ergebnisse zu erzielen, sollten Sie nicht mehr als ein paar Batches gleichzeitig einreichen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-204">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="eee0d-205">Lassen Sie die Verarbeitung von Batches durchführen, bevor Sie weitere Stapel senden.</span><span class="sxs-lookup"><span data-stu-id="eee0d-205">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="eee0d-206">Derzeit steht die Zuweisung von Batch Richtlinien für alle Teams-Richtlinientypen nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eee0d-206">Currently, batch policy assignment isn't available for all Teams policy types.</span></span> <span data-ttu-id="eee0d-207">Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) .</span><span class="sxs-lookup"><span data-stu-id="eee0d-207">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="eee0d-208">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="eee0d-208">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="eee0d-209">Führen Sie die folgenden Schritte aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams)zu installieren.</span><span class="sxs-lookup"><span data-stu-id="eee0d-209">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="eee0d-210">Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="eee0d-210">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="eee0d-211">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="eee0d-211">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="eee0d-212">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="eee0d-212">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="eee0d-213">Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul (optional)</span><span class="sxs-lookup"><span data-stu-id="eee0d-213">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="eee0d-214">Möglicherweise möchten Sie auch [das Azure AD PowerShell für Graph-Modul](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (falls noch nicht geschehen) herunterladen und installieren und eine Verbindung mit Azure AD herstellen, damit Sie eine Liste der Benutzer in Ihrer Organisation abrufen können.</span><span class="sxs-lookup"><span data-stu-id="eee0d-214">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="eee0d-215">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-215">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="eee0d-216">Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung zu Teams verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="eee0d-216">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="eee0d-217">Zuweisen einer Richtlinie zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="eee0d-217">Assign a policy to a batch of users</span></span>

<span data-ttu-id="eee0d-218">In diesem Beispiel verwenden wir das ```New-CsBatchPolicyAssignmentOperation``` Cmdlet, um eine APP-Setup Richtlinie mit dem Namen "HR-App-Setup Richtlinie" einem Batch von Benutzern zuzuweisen, die in der Datei "Users_ids. Text" aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="eee0d-218">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="eee0d-219">In diesem Beispiel stellen wir eine Verbindung mit Azure AD her, um eine Sammlung von Benutzern abzurufen, und weisen dann eine Messagingrichtlinie mit dem Namen "New Hire Messaging Policy" einem Batch von Benutzern zu, die mithilfe Ihres UPNs angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="eee0d-219">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their UPNs.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

<span data-ttu-id="eee0d-220">Weitere Informationen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="eee0d-220">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="eee0d-221">Abrufen des Status einer Stapelverarbeitungs Zuordnung</span><span class="sxs-lookup"><span data-stu-id="eee0d-221">Get the status of a batch assignment</span></span>

<span data-ttu-id="eee0d-222">Führen Sie die folgenden Schritte aus, um den Status einer Stapelverarbeitungs Zuweisung abzurufen, wobei Vorgangskennung die Vorgangs-ID ist, die vom ```New-CsBatchPolicyAssignmentOperation``` Cmdlet für einen bestimmten Batch zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="eee0d-222">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="eee0d-223">Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie die folgenden Schritte aus, um weitere Informationen zu Fehlern zu erhalten, die in der Eigenschaft enthalten sind ```UserState``` .</span><span class="sxs-lookup"><span data-stu-id="eee0d-223">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="eee0d-224">Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="eee0d-224">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="eee0d-225">Zuweisen einer Richtlinie zu einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="eee0d-225">Assign a policy to a group</span></span>

<span data-ttu-id="eee0d-226">**Die Richtlinienzuweisung zu Gruppen steht derzeit nur in der privaten Vorschau zur Verfügung. Die Cmdlets für dieses Feature befinden sich im PowerShell-Modul für Teams vor der Freigabe.**</span><span class="sxs-lookup"><span data-stu-id="eee0d-226">**Policy assignment to groups is currently only available in private preview. The cmdlets for this feature are in the pre-release Teams PowerShell module.**</span></span>

<span data-ttu-id="eee0d-227">Mit der Richtlinienzuweisung zu Gruppen können Sie einer Gruppe von Benutzern eine Richtlinie zuweisen, beispielsweise eine Sicherheitsgruppe oder eine Organisationseinheit.</span><span class="sxs-lookup"><span data-stu-id="eee0d-227">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="eee0d-228">Die Richtlinienzuweisung wird nach Rangfolgeregeln an Mitglieder der Gruppe weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="eee0d-228">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="eee0d-229">Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden Ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="eee0d-229">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="eee0d-230">Sie verwenden das ```New-CsGroupPolicyAssignment``` Cmdlet, um einer Gruppe eine Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-230">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="eee0d-231">Sie können eine Gruppe mithilfe der Objekt-ID, der SIP-Adresse oder der e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="eee0d-231">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="eee0d-232">Wenn Sie die Richtlinie zuweisen, wird Sie sofort der Gruppe zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-232">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="eee0d-233">Beachten Sie jedoch, dass die Verteilung der Richtlinienzuweisung an Mitglieder der Gruppe als Hintergrundvorgang ausgeführt wird und je nach Größe der Gruppe einige Zeit in Anspruch nehmen kann.</span><span class="sxs-lookup"><span data-stu-id="eee0d-233">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="eee0d-234">Das gleiche gilt, wenn eine Richtlinie aus einer Gruppe nicht zugewiesen wird oder wenn Mitglieder einer Gruppe hinzugefügt oder aus ihr entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="eee0d-234">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!NOTE]
> <span data-ttu-id="eee0d-235">Derzeit steht die Richtlinienzuweisung zu Gruppen nicht für alle Teams-Richtlinientypen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eee0d-235">Currently, policy assignment to groups isn't available for all Teams policy types.</span></span> <span data-ttu-id="eee0d-236">Eine Liste der unterstützten Richtlinientypen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) .</span><span class="sxs-lookup"><span data-stu-id="eee0d-236">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="eee0d-237">Was Sie über die Richtlinienzuweisung zu Gruppen wissen müssen</span><span class="sxs-lookup"><span data-stu-id="eee0d-237">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="eee0d-238">Bevor Sie beginnen, ist es wichtig, die Rangfolge von Prioritätsregeln und die Rangfolge von Gruppenaufgaben zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-238">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="eee0d-239">Rangfolgeregeln</span><span class="sxs-lookup"><span data-stu-id="eee0d-239">Precedence rules</span></span>

<span data-ttu-id="eee0d-240">Für einen bestimmten Richtlinientyp wird die effektive Richtlinie eines Benutzers entsprechend den folgenden Bedingungen bestimmt:</span><span class="sxs-lookup"><span data-stu-id="eee0d-240">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="eee0d-241">Eine Richtlinie, die einem Benutzer direkt zugewiesen ist, hat Vorrang vor jeder anderen Richtlinie desselben Typs, die einer Gruppe zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-241">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="eee0d-242">Anders ausgedrückt: Wenn einem Benutzer eine Richtlinie eines bestimmten Typs direkt zugewiesen wird, erbt dieser Benutzer keine Richtlinie desselben Typs aus einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="eee0d-242">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="eee0d-243">Dies bedeutet auch, dass Sie diese Richtlinie vom Benutzer entfernen müssen, bevor Sie eine Richtlinie desselben Typs aus einer Gruppe erben können, wenn ein Benutzer über eine Richtlinie eines bestimmten Typs verfügt, der Ihnen direkt zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="eee0d-243">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="eee0d-244">Wenn einem Benutzer nicht direkt eine Richtlinie zugewiesen wurde und es sich um ein Mitglied von zwei oder mehr Gruppen handelt und für jede Gruppe eine Richtlinie desselben Typs zugewiesen ist, erbt der Benutzer die Richtlinie der Gruppenaufgabe, die die höchste Rangfolge aufweist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-244">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="eee0d-245">Wenn ein Benutzer nicht Mitglied einer Gruppe ist, der eine Richtlinie zugewiesen ist, gilt die globale (organisationsweite Standardrichtlinie) für diesen Richtlinientyp für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="eee0d-245">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="eee0d-246">Die effektive Richtlinie eines Benutzers wird entsprechend diesen Regeln aktualisiert, wenn ein Benutzer zu einer Gruppe hinzugefügt oder daraus entfernt wird, der eine Richtlinie zugewiesen ist, eine Richtlinie von einer Gruppe nicht zugewiesen wird oder eine Richtlinie entfernt wird, die dem Benutzer direkt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-246">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="eee0d-247">Gruppen Zuordnungs Rangfolge</span><span class="sxs-lookup"><span data-stu-id="eee0d-247">Group assignment ranking</span></span>
 
<span data-ttu-id="eee0d-248">Wenn Sie einer Gruppe eine Richtlinie zuweisen, geben Sie eine Rangfolge für die Gruppenzuordnung an.</span><span class="sxs-lookup"><span data-stu-id="eee0d-248">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="eee0d-249">Damit wird ermittelt, welche Richtlinie ein Benutzer als effektive Richtlinie erben soll, wenn der Benutzer ein Mitglied von zwei oder mehr Gruppen ist und jeder Gruppe eine Richtlinie desselben Typs zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-249">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="eee0d-250">Die Rangfolge der Gruppenzuweisungen ist relativ zu anderen Gruppenzuordnungen desselben Typs.</span><span class="sxs-lookup"><span data-stu-id="eee0d-250">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="eee0d-251">Wenn Sie beispielsweise zwei Gruppen eine Anrufrichtlinie zuweisen, legen Sie die Rangfolge einer Zuordnung auf 1 und die andere auf 2, wobei 1 die höchste Rangliste ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-251">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="eee0d-252">Die Gruppen Zuordnungs Rangfolge gibt an, welche Gruppenmitgliedschaft wichtiger oder relevanter als andere Gruppenmitgliedschaften im Hinblick auf die Vererbung ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-252">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="eee0d-253">Angenommen, Sie verfügen über zwei Gruppen, Store-Mitarbeiter und Store-Manager.</span><span class="sxs-lookup"><span data-stu-id="eee0d-253">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="eee0d-254">Beiden Gruppen wird eine Anrufrichtlinie für Teams zugewiesen, und Sie können die Anruf Richtlinien für die Mitarbeiter und die Geschäftsmanager anrufen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-254">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="eee0d-255">Bei einem Store Manager, der sich in beiden Gruppen befindet, ist ihre Rolle als Manager relevanter als ihre Rolle als Mitarbeiter, sodass die Anrufrichtlinie, die der Gruppe Store Managers zugewiesen ist, eine höhere Rangfolge aufweisen sollte.</span><span class="sxs-lookup"><span data-stu-id="eee0d-255">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="eee0d-256">Gruppe</span><span class="sxs-lookup"><span data-stu-id="eee0d-256">Group</span></span> |<span data-ttu-id="eee0d-257">Anruf Richtlinienname für Teams</span><span class="sxs-lookup"><span data-stu-id="eee0d-257">Teams calling policy name</span></span>  |<span data-ttu-id="eee0d-258">Rang</span><span class="sxs-lookup"><span data-stu-id="eee0d-258">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="eee0d-259">Store-Manager</span><span class="sxs-lookup"><span data-stu-id="eee0d-259">Store Managers</span></span>   |<span data-ttu-id="eee0d-260">Anruf Richtlinien für Store-Manager</span><span class="sxs-lookup"><span data-stu-id="eee0d-260">Store Managers Calling Policy</span></span>         |<span data-ttu-id="eee0d-261">1</span><span class="sxs-lookup"><span data-stu-id="eee0d-261">1</span></span>|
|<span data-ttu-id="eee0d-262">Speichern von Mitarbeitern</span><span class="sxs-lookup"><span data-stu-id="eee0d-262">Store Employees</span></span>    |<span data-ttu-id="eee0d-263">Speichern von Mitarbeiter Anruf Richtlinien</span><span class="sxs-lookup"><span data-stu-id="eee0d-263">Store Employees Calling Policy</span></span>      |<span data-ttu-id="eee0d-264">2</span><span class="sxs-lookup"><span data-stu-id="eee0d-264">2</span></span>|

<span data-ttu-id="eee0d-265">Wenn Sie kein Ranking angeben, erhält die Richtlinienzuweisung die niedrigste Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="eee0d-265">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="eee0d-266">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="eee0d-266">Install and connect to the Microsoft Teams PowerShell module</span></span>

> [!NOTE]
> <span data-ttu-id="eee0d-267">Die Cmdlets befinden sich in der Pre-Release-Version des Teams PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="eee0d-267">The cmdlets are in the pre-release version of the Teams PowerShell module.</span></span> <span data-ttu-id="eee0d-268">Führen Sie die folgenden Schritte aus, um zunächst die allgemein verfügbare Version des Teams PowerShell-Moduls (sofern installiert) zu deinstallieren, und installieren Sie dann die neueste Vorabversion des Moduls aus dem PowerShell-Test Katalog.</span><span class="sxs-lookup"><span data-stu-id="eee0d-268">Follow these steps to first uninstall the Generally Available version of the Teams PowerShell module (if it's installed), and then install the latest pre-release version of the module from the PowerShell Test Gallery.</span></span>

<span data-ttu-id="eee0d-269">Wenn Sie dies noch nicht getan haben, führen Sie die folgenden Schritte aus, um den PowerShell-Test Katalog als vertrauenswürdige Quelle zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="eee0d-269">If you haven't already, run the following to register the PowerShell Test Gallery as a trusted source.</span></span>

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

<span data-ttu-id="eee0d-270">Wenn Sie die allgemein verfügbare Version des Teams PowerShell-Moduls installiert haben, führen Sie die folgenden Schritte aus, um Sie zu deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="eee0d-270">If you have the Generally Available version of the Teams PowerShell module installed, run the following to uninstall it.</span></span>

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

<span data-ttu-id="eee0d-271">Führen Sie die folgenden Schritte aus, um das aktuelle Microsoft Teams PowerShell-Modul aus dem PowerShell-Test Katalog zu installieren.</span><span class="sxs-lookup"><span data-stu-id="eee0d-271">Run the following to install the latest Microsoft Teams PowerShell module from the PowerShell Test Gallery.</span></span>

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

<span data-ttu-id="eee0d-272">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="eee0d-272">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="eee0d-273">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="eee0d-273">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="eee0d-274">Zuweisen einer Richtlinie zu einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="eee0d-274">Assign a policy to a group</span></span>

<span data-ttu-id="eee0d-275">In diesem Beispiel verwenden wir das ```New-CsGroupPolicyAssignment``` Cmdlet, um einer Gruppe mit einer Zuordnungs Rangfolge von 1 eine Teams-Besprechungsrichtlinie mit dem Namen "Einzelhandels Manager-Besprechungsrichtlinie" zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-275">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="eee0d-276">Weitere Informationen finden Sie unter [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="eee0d-276">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="eee0d-277">Abrufen von Richtlinienzuweisungen für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="eee0d-277">Get policy assignments for a group</span></span>

<span data-ttu-id="eee0d-278">Verwenden Sie das ```Get-CsGroupPolicyAssignment``` Cmdlet, um alle Richtlinien abzurufen, die einer Gruppe zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="eee0d-278">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="eee0d-279">Beachten Sie, dass Gruppen immer nach ihrer Gruppen-ID aufgeführt werden, auch wenn die SIP-Adresse oder e-Mail-Adresse zum Zuweisen der Richtlinie verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="eee0d-279">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="eee0d-280">In diesem Beispiel rufen wir alle Richtlinien ab, die einer bestimmten Gruppe zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="eee0d-280">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="eee0d-281">In diesem Beispiel geben wir alle Gruppen zurück, denen eine Teams-Besprechungsrichtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-281">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="eee0d-282">Weitere Informationen finden Sie unter [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="eee0d-282">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="eee0d-283">Entfernen einer Richtlinie aus einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="eee0d-283">Remove a policy from a group</span></span>

<span data-ttu-id="eee0d-284">Verwenden Sie das ```Remove-CsGroupPolicyAssignment``` Cmdlet, um eine Richtlinie aus einer Gruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-284">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="eee0d-285">Wenn Sie eine Richtlinie aus einer Gruppe entfernen, werden die Prioritäten anderer Richtlinien desselben Typs, die dieser Gruppe zugewiesen sind und die eine niedrigere Rangfolge aufweisen, aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="eee0d-285">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="eee0d-286">Wenn Sie beispielsweise eine Richtlinie entfernen, die eine Rangfolge von 2 aufweist, werden Richtlinien mit einer Rangfolge von 3 und 4 aktualisiert, um Ihre neue Rangfolge wiederzugeben.</span><span class="sxs-lookup"><span data-stu-id="eee0d-286">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="eee0d-287">In den beiden folgenden Tabellen wird dieses Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="eee0d-287">The following two tables show this example.</span></span>

<span data-ttu-id="eee0d-288">Nachfolgend finden Sie eine Liste der Richtlinienzuweisungen und Prioritäten für eine Team-Besprechungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="eee0d-288">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="eee0d-289">Gruppenname</span><span class="sxs-lookup"><span data-stu-id="eee0d-289">Group name</span></span>  |<span data-ttu-id="eee0d-290">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="eee0d-290">Policy name</span></span>  |<span data-ttu-id="eee0d-291">Rang</span><span class="sxs-lookup"><span data-stu-id="eee0d-291">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="eee0d-292">Vertrieb</span><span class="sxs-lookup"><span data-stu-id="eee0d-292">Sales</span></span>    |<span data-ttu-id="eee0d-293">Vertriebsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="eee0d-293">Sales policy</span></span>       | <span data-ttu-id="eee0d-294">1</span><span class="sxs-lookup"><span data-stu-id="eee0d-294">1</span></span>        |
|<span data-ttu-id="eee0d-295">Region West</span><span class="sxs-lookup"><span data-stu-id="eee0d-295">West Region</span></span>     |<span data-ttu-id="eee0d-296">West Regions-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="eee0d-296">West Region policy</span></span>         |<span data-ttu-id="eee0d-297">2</span><span class="sxs-lookup"><span data-stu-id="eee0d-297">2</span></span>         |
|<span data-ttu-id="eee0d-298">Division</span><span class="sxs-lookup"><span data-stu-id="eee0d-298">Division</span></span>    |<span data-ttu-id="eee0d-299">Abteilungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="eee0d-299">Division policy</span></span>         |<span data-ttu-id="eee0d-300">3</span><span class="sxs-lookup"><span data-stu-id="eee0d-300">3</span></span>         |
|<span data-ttu-id="eee0d-301">Tochter</span><span class="sxs-lookup"><span data-stu-id="eee0d-301">Subsidiary</span></span>   |<span data-ttu-id="eee0d-302">Subsidiäre Richtlinie</span><span class="sxs-lookup"><span data-stu-id="eee0d-302">Subsidiary policy</span></span>        |<span data-ttu-id="eee0d-303">4</span><span class="sxs-lookup"><span data-stu-id="eee0d-303">4</span></span>         |

<span data-ttu-id="eee0d-304">Wenn die West Region-Richtlinie aus der Gruppe "West Region" entfernt wird, werden die Richtlinienzuweisungen und-Prioritäten wie folgt aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="eee0d-304">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="eee0d-305">Gruppenname</span><span class="sxs-lookup"><span data-stu-id="eee0d-305">Group name</span></span>  |<span data-ttu-id="eee0d-306">Richtlinienname</span><span class="sxs-lookup"><span data-stu-id="eee0d-306">Policy name</span></span>  |<span data-ttu-id="eee0d-307">Rang</span><span class="sxs-lookup"><span data-stu-id="eee0d-307">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="eee0d-308">Vertrieb</span><span class="sxs-lookup"><span data-stu-id="eee0d-308">Sales</span></span>    |<span data-ttu-id="eee0d-309">Vertriebsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="eee0d-309">Sales policy</span></span>       | <span data-ttu-id="eee0d-310">1</span><span class="sxs-lookup"><span data-stu-id="eee0d-310">1</span></span>        |
|<span data-ttu-id="eee0d-311">Division</span><span class="sxs-lookup"><span data-stu-id="eee0d-311">Division</span></span>    |<span data-ttu-id="eee0d-312">Abteilungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="eee0d-312">Division policy</span></span>         |<span data-ttu-id="eee0d-313">2</span><span class="sxs-lookup"><span data-stu-id="eee0d-313">2</span></span>         |
|<span data-ttu-id="eee0d-314">Tochter</span><span class="sxs-lookup"><span data-stu-id="eee0d-314">Subsidiary</span></span>   |<span data-ttu-id="eee0d-315">Subsidiäre Richtlinie</span><span class="sxs-lookup"><span data-stu-id="eee0d-315">Subsidiary policy</span></span>        |<span data-ttu-id="eee0d-316">3</span><span class="sxs-lookup"><span data-stu-id="eee0d-316">3</span></span>        |

<span data-ttu-id="eee0d-317">In diesem Beispiel entfernen wir die Besprechungsrichtlinie für Teams aus einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="eee0d-317">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="eee0d-318">Weitere Informationen finden Sie unter [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="eee0d-318">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="eee0d-319">Ändern einer Richtlinien Aufgabe für eine Gruppe</span><span class="sxs-lookup"><span data-stu-id="eee0d-319">Change a policy assignment for a group</span></span>

<span data-ttu-id="eee0d-320">Nachdem Sie einer Gruppe eine Richtlinie zugewiesen haben, können Sie das ```Set-CsGroupPolicyAssignmentd``` Cmdlet verwenden, um die Richtlinienzuweisung dieser Gruppe wie folgt zu ändern:</span><span class="sxs-lookup"><span data-stu-id="eee0d-320">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignmentd``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="eee0d-321">Ändern der Rangfolge</span><span class="sxs-lookup"><span data-stu-id="eee0d-321">Change the ranking</span></span>
- <span data-ttu-id="eee0d-322">Ändern der Richtlinie eines bestimmten Richtlinientyps</span><span class="sxs-lookup"><span data-stu-id="eee0d-322">Change the policy of a given policy type</span></span>
- <span data-ttu-id="eee0d-323">Ändern der Richtlinie eines bestimmten Richtlinientyps und der Rangfolge</span><span class="sxs-lookup"><span data-stu-id="eee0d-323">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="eee0d-324">In diesem Beispiel ändern wir die Richtlinie für die Anruf Park Richtlinie einer Gruppe in eine Richtlinie mit dem Namen SupportCallPark und die Zuordnungs Rangfolge auf 3.</span><span class="sxs-lookup"><span data-stu-id="eee0d-324">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="eee0d-325">Weitere Informationen finden Sie unter [Satz-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="eee0d-325">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>

### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="eee0d-326">Ändern der effektiven Richtlinie für einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="eee0d-326">Change the effective policy for a user</span></span>

<span data-ttu-id="eee0d-327">Im folgenden finden Sie ein Beispiel für das Ändern der effektiven Richtlinie für einen Benutzer, dem eine Richtlinie direkt zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-327">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="eee0d-328">Zunächst verwenden wir das ```Get-CsUserPolicyAssignment``` Cmdlet zusammen mit dem ```PolicySource``` Parameter, um Details zu den Broadcast Richtlinien für Teams zu erhalten, die dem Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="eee0d-328">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="eee0d-329">Weitere Informationen finden Sie unter [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span><span class="sxs-lookup"><span data-stu-id="eee0d-329">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="eee0d-330">Die Ausgabe zeigt, dass dem Benutzer direkt eine Team-Broadcast Richtlinie mit dem Namen "Employee Events" zugewiesen wurde, die Vorrang vor der Richtlinie namens "Vendor Live Events" hat, die einer Gruppe zugeordnet ist, der der Benutzer angehört.</span><span class="sxs-lookup"><span data-stu-id="eee0d-330">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="eee0d-331">Jetzt entfernen wir die Mitarbeiter-Ereignis Richtlinie des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="eee0d-331">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="eee0d-332">Das bedeutet, dass der Benutzer nicht mehr über eine Broadcast Richtlinie für Teams verfügt, die Ihnen direkt zugewiesen wurde, und erbt die Richtlinie für Anbieter-Live Ereignisse, die der Gruppe zugewiesen ist, der der Benutzer angehört.</span><span class="sxs-lookup"><span data-stu-id="eee0d-332">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="eee0d-333">Verwenden Sie dazu das folgende Cmdlet im Skype for Business PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="eee0d-333">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="eee0d-334">Sie können das folgende Cmdlet im Teams PowerShell-Modul verwenden, um dies bei einer Batch Richtlinienzuweisung zu tun, wobei $users eine Liste der von Ihnen angegebenen Benutzer ist.</span><span class="sxs-lookup"><span data-stu-id="eee0d-334">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="eee0d-335">Zuweisen eines Richtlinienpakets zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="eee0d-335">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="eee0d-336">Mit der Zuweisung von Batch Richtlinien Paketen können Sie einem Richtlinienpaket große Gruppen von Benutzern gleichzeitig zuweisen, ohne ein Skript verwenden zu müssen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-336">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="eee0d-337">Sie verwenden das ```New-CsBatchPolicyPackageAssignmentOperation``` Cmdlet, um einen Benutzer Batch und das Richtlinienpaket, das Sie zuweisen möchten, zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="eee0d-337">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="eee0d-338">Die Aufgaben werden als Hintergrundvorgang verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.</span><span class="sxs-lookup"><span data-stu-id="eee0d-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="eee0d-339">Anschließend können Sie das ```Get-CsBatchPolicyAssignmentOperation``` Cmdlet verwenden, um den Fortschritt und den Status der Aufgaben in einem Batch zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-339">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="eee0d-340">Ein Batch kann bis zu 20.000-Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="eee0d-340">A batch can contain up to 20,000 users.</span></span> <span data-ttu-id="eee0d-341">Sie können Benutzer anhand ihrer Objekt-ID, Ihres UPN, ihrer SIP-Adresse oder Ihrer e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="eee0d-341">You can specify users by their object Id, UPN, SIP address, or email address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eee0d-342">Wir empfehlen derzeit, Richtlinien Pakete in Batches von 5.000-Benutzern gleichzeitig zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-342">We're currently recommending that you assign policy packages in batches of 5,000 users at a time.</span></span> <span data-ttu-id="eee0d-343">In Zeiten höherer Nachfrage können Verzögerungen bei der Verarbeitung auftreten.</span><span class="sxs-lookup"><span data-stu-id="eee0d-343">During these times of increased demand, you may experience delays in processing times.</span></span> <span data-ttu-id="eee0d-344">Um die Auswirkungen dieser erhöhten Verarbeitungszeiten zu minimieren, empfehlen wir, kleinere Batchgrößen von bis zu 5.000-Benutzern zu übermitteln und jeden Batch erst nach Abschluss des vorherigen zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="eee0d-344">To minimize the impact of these increased processing times, we suggest that you submit smaller batch sizes of up to 5,000 users, and submit each batch only after the previous one is completed.</span></span> <span data-ttu-id="eee0d-345">Das Übermitteln von Batches außerhalb ihrer regulären Geschäftszeiten kann ebenfalls hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="eee0d-345">Submitting batches outside your regular business hours can also help.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="eee0d-346">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="eee0d-346">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="eee0d-347">Führen Sie die folgenden Schritte aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams) zu installieren (falls noch nicht geschehen).</span><span class="sxs-lookup"><span data-stu-id="eee0d-347">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="eee0d-348">Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="eee0d-348">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="eee0d-349">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="eee0d-349">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="eee0d-350">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="eee0d-350">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="eee0d-351">Zuweisen eines Richtlinienpakets zu einem Benutzer Batch</span><span class="sxs-lookup"><span data-stu-id="eee0d-351">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="eee0d-352">In diesem Beispiel verwenden wir das ```New-CsBatchPolicyPackageAssignmentOperation``` Cmdlet, um einem Batch von Benutzern das Education_PrimaryStudent-Richtlinienpaket zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="eee0d-352">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="eee0d-353">Weitere Informationen finden Sie unter [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="eee0d-353">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="eee0d-354">Abrufen des Status einer Stapelverarbeitungs Zuordnung</span><span class="sxs-lookup"><span data-stu-id="eee0d-354">Get the status of a batch assignment</span></span>

<span data-ttu-id="eee0d-355">Führen Sie die folgenden Schritte aus, um den Status einer Stapelverarbeitungs Zuweisung abzurufen, wobei Vorgangskennung die Vorgangs-ID ist, die vom ```New-CsBatchPolicyAssignmentOperation``` Cmdlet für einen bestimmten Batch zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="eee0d-355">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="eee0d-356">Wenn die Ausgabe zeigt, dass ein Fehler aufgetreten ist, führen Sie die folgenden Schritte aus, um weitere Informationen zu Fehlern zu erhalten, die in der Eigenschaft enthalten sind ```UserState``` .</span><span class="sxs-lookup"><span data-stu-id="eee0d-356">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="eee0d-357">Weitere Informationen finden Sie unter [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="eee0d-357">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="eee0d-358">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="eee0d-358">Related topics</span></span>

- [<span data-ttu-id="eee0d-359">Übersicht über PowerShell für Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eee0d-359">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
