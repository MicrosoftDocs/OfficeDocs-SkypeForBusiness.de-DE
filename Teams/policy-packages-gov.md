---
title: Teams-Richtlinien Pakete für Behörden
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Teamrichtlinien Pakete für Ihre Regierungsorganisation verwenden und verwalten.
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908594"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="cee60-103">Teams-Richtlinien Pakete für Behörden</span><span class="sxs-lookup"><span data-stu-id="cee60-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="cee60-104">Richtlinien Pakete sind derzeit in den Microsoft 365 Government gcc-oder DoD-Bereitstellungen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cee60-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="cee60-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="cee60-105">Overview</span></span>

<span data-ttu-id="cee60-106">Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cee60-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="cee60-107">Richtlinienpakete vereinfachen und rationalisieren Richtlinien und lassen Sie diese konsistent verwalten.</span><span class="sxs-lookup"><span data-stu-id="cee60-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="cee60-108">Sie können die Einstellungen der Richtlinien im Paket entsprechend den Anforderungen Ihrer Benutzer anpassen.</span><span class="sxs-lookup"><span data-stu-id="cee60-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="cee60-109">Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="cee60-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="cee60-110">Sie können Richtlinien Pakete mit dem Microsoft Teams Admin Center oder mit PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="cee60-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="cee60-111">Richtlinien Pakete definieren für die folgenden Richtlinien je nach Paket:</span><span class="sxs-lookup"><span data-stu-id="cee60-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="cee60-112">Messaging</span><span class="sxs-lookup"><span data-stu-id="cee60-112">Messaging</span></span>
- <span data-ttu-id="cee60-113">Besprechungen</span><span class="sxs-lookup"><span data-stu-id="cee60-113">Meetings</span></span>
- <span data-ttu-id="cee60-114">Anrufe</span><span class="sxs-lookup"><span data-stu-id="cee60-114">Calling</span></span>
- <span data-ttu-id="cee60-115">App-Setup</span><span class="sxs-lookup"><span data-stu-id="cee60-115">App setup</span></span>
- <span data-ttu-id="cee60-116">Liveereignisse</span><span class="sxs-lookup"><span data-stu-id="cee60-116">Live events</span></span>

<span data-ttu-id="cee60-117">Teams umfasst derzeit die folgenden Richtlinien Pakete für Behörden.</span><span class="sxs-lookup"><span data-stu-id="cee60-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="cee60-118">Paket Name im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="cee60-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="cee60-119">Am besten geeignet für</span><span class="sxs-lookup"><span data-stu-id="cee60-119">Best used for</span></span>|<span data-ttu-id="cee60-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cee60-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="cee60-121">Beauftragter für öffentliche Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cee60-121">Public safety officer</span></span>  |<span data-ttu-id="cee60-122">Beauftragte für öffentliche Sicherheit in ihrer Regierungsorganisation</span><span class="sxs-lookup"><span data-stu-id="cee60-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="cee60-123">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="cee60-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="cee60-124">First-Manager</span><span class="sxs-lookup"><span data-stu-id="cee60-124">Firstline manager</span></span>  |<span data-ttu-id="cee60-125">First-Manager in ihrer Regierungsorganisation</span><span class="sxs-lookup"><span data-stu-id="cee60-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="cee60-126">Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf First-Manager in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="cee60-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="cee60-127">First-Worker</span><span class="sxs-lookup"><span data-stu-id="cee60-127">Firstline worker</span></span>  |<span data-ttu-id="cee60-128">Erste Arbeitskräfte in ihrer Regierungsorganisation</span><span class="sxs-lookup"><span data-stu-id="cee60-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="cee60-129">Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Mitarbeiter in Ihrer Organisation in erster Linie an.</span><span class="sxs-lookup"><span data-stu-id="cee60-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Screenshot der Gesundheitsrichtlinien Pakete](media/policy-packages-gov.png)

<span data-ttu-id="cee60-131">Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="cee60-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="cee60-132">Wenn Sie beispielsweise Benutzern in Ihrer Organisation das Richtlinienpaket für das öffentliche Sicherheitsbeauftragte zuweisen, wird eine Richtlinie mit dem Namen PublicSafety_Officer für jede Richtlinie im Paket erstellt.</span><span class="sxs-lookup"><span data-stu-id="cee60-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Screenshot der Richtlinien im Healthcare Clinical Worker-Paket](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="cee60-134">Verwalten von Richtlinienpaketen</span><span class="sxs-lookup"><span data-stu-id="cee60-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="cee60-135">Ansicht</span><span class="sxs-lookup"><span data-stu-id="cee60-135">View</span></span>

<span data-ttu-id="cee60-136">Zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cee60-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="cee60-137">Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers **Richtlinien Pakete** aus, wählen Sie den Paketnamen aus, und wählen Sie dann den Richtliniennamen aus.</span><span class="sxs-lookup"><span data-stu-id="cee60-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="cee60-138">Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.</span><span class="sxs-lookup"><span data-stu-id="cee60-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="cee60-139">Anpassen</span><span class="sxs-lookup"><span data-stu-id="cee60-139">Customize</span></span>

<span data-ttu-id="cee60-140">Passen Sie die Einstellungen der Richtlinien im Richtlinienpaket nach Bedarf an die Anforderungen Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="cee60-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="cee60-141">Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cee60-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="cee60-142">Wenn Sie die Einstellungen einer Richtlinie in einem Richtlinienpaket bearbeiten möchten, wählen Sie im Microsoft Teams Admin Center das Richtlinienpaket aus, wählen Sie den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="cee60-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="cee60-143">Beachten Sie, dass Sie auch die Einstellungen von Richtlinien in einem Paket ändern können, nachdem Sie das Richtlinienpaket zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="cee60-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="cee60-144">Weitere Informationen finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="cee60-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="cee60-145">Zuweisen</span><span class="sxs-lookup"><span data-stu-id="cee60-145">Assign</span></span>

<span data-ttu-id="cee60-146">Weisen Sie das Richtlinienpaket Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="cee60-146">Assign the policy package to users.</span></span> <span data-ttu-id="cee60-147">Wenn einem Benutzer eine Richtlinie zugewiesen ist und Sie später eine andere Richtlinie zuweisen, hat die letzte Aufgabe Vorrang.</span><span class="sxs-lookup"><span data-stu-id="cee60-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="cee60-148">Zuweisen eines Richtlinienpakets zu einem oder mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="cee60-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="cee60-149">Wenn Sie einem oder mehreren Benutzern ein Richtlinienpaket zuweisen möchten, wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Richtlinien Paketen** , und wählen Sie dann **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="cee60-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![Screenshot: Zuweisen eines Richtlinienpakets im Admin Center](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="cee60-151">Weitere Informationen finden Sie unter [Zuweisen eines Richtlinienpakets](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="cee60-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="cee60-152">Wenn einem Benutzer eine Richtlinie zugewiesen ist und Sie später eine andere Richtlinie zuweisen, hat die letzte Aufgabe Vorrang.</span><span class="sxs-lookup"><span data-stu-id="cee60-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="cee60-153">Zuweisen eines Richtlinienpakets zu einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="cee60-153">Assign a policy package to a group</span></span>

<span data-ttu-id="cee60-154">**Dieses Feature befindet sich in der privaten Vorschau**</span><span class="sxs-lookup"><span data-stu-id="cee60-154">**This feature is in private preview**</span></span>

<span data-ttu-id="cee60-155">Mit der Richtlinienpaket Zuweisung zu Gruppen können Sie einer Gruppe von Benutzern mehrere Richtlinien zuweisen, beispielsweise eine Sicherheitsgruppe oder eine Verteilerliste.</span><span class="sxs-lookup"><span data-stu-id="cee60-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="cee60-156">Die Richtlinienzuweisung wird nach Rangfolgeregeln an Mitglieder der Gruppe weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="cee60-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="cee60-157">Wenn Mitglieder einer Gruppe hinzugefügt oder daraus entfernt werden, werden Ihre geerbten Richtlinienzuweisungen entsprechend aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="cee60-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="cee60-158">Diese Methode wird für Gruppen von bis zu 50.000 Benutzern empfohlen, funktioniert aber auch mit größeren Gruppen.</span><span class="sxs-lookup"><span data-stu-id="cee60-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="cee60-159">Weitere Informationen finden Sie unter [Zuweisen eines Richtlinienpakets zu einer Gruppe](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="cee60-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="cee60-160">Zuweisen eines Richtlinienpakets zu einem umfangreichen Satz (Batch) von Benutzern</span><span class="sxs-lookup"><span data-stu-id="cee60-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="cee60-161">Verwenden Sie die Batch Richtlinien-Paket Zuweisung, um einem Richtlinienpaket große Gruppen von Benutzern gleichzeitig zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="cee60-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="cee60-162">Sie verwenden das Cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) , um einen Benutzer Batch und das Richtlinienpaket, das Sie zuweisen möchten, zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="cee60-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="cee60-163">Die Aufgaben werden als Hintergrundvorgang verarbeitet, und für jeden Batch wird eine Vorgangs-ID generiert.</span><span class="sxs-lookup"><span data-stu-id="cee60-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="cee60-164">Ein Batch kann bis zu 5.000-Benutzer enthalten.</span><span class="sxs-lookup"><span data-stu-id="cee60-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="cee60-165">Sie können Benutzer anhand ihrer Objekt-ID, Ihres UPN, ihrer SIP-Adresse oder Ihrer e-Mail-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="cee60-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="cee60-166">Weitere Informationen finden Sie unter [Zuweisen eines Richtlinienpakets zu einem Batch von Benutzern](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="cee60-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="cee60-167">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cee60-167">Related topics</span></span>

[<span data-ttu-id="cee60-168">Verwalten von Richtlinienpaketen in Teams</span><span class="sxs-lookup"><span data-stu-id="cee60-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="cee60-169">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cee60-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
