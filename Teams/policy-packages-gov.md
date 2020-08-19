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
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804023"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="cd42c-103">Teams-Richtlinien Pakete für Behörden</span><span class="sxs-lookup"><span data-stu-id="cd42c-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="cd42c-104">Richtlinien Pakete sind derzeit in den Microsoft 365 Government gcc-oder DoD-Bereitstellungen nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd42c-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="cd42c-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="cd42c-105">Overview</span></span>

<span data-ttu-id="cd42c-106">Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="cd42c-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="cd42c-107">Richtlinienpakete vereinfachen und rationalisieren Richtlinien und lassen Sie diese konsistent verwalten.</span><span class="sxs-lookup"><span data-stu-id="cd42c-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="cd42c-108">Sie können die Einstellungen der Richtlinien im Paket entsprechend den Anforderungen Ihrer Benutzer anpassen.</span><span class="sxs-lookup"><span data-stu-id="cd42c-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="cd42c-109">Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="cd42c-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="cd42c-110">Sie können Richtlinien Pakete mit dem Microsoft Teams Admin Center oder mit PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="cd42c-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="cd42c-111">Richtlinien Pakete definieren für die folgenden Richtlinien je nach Paket:</span><span class="sxs-lookup"><span data-stu-id="cd42c-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="cd42c-112">Messaging</span><span class="sxs-lookup"><span data-stu-id="cd42c-112">Messaging</span></span>
- <span data-ttu-id="cd42c-113">Besprechungen</span><span class="sxs-lookup"><span data-stu-id="cd42c-113">Meetings</span></span>
- <span data-ttu-id="cd42c-114">Anrufe</span><span class="sxs-lookup"><span data-stu-id="cd42c-114">Calling</span></span>
- <span data-ttu-id="cd42c-115">App-Setup</span><span class="sxs-lookup"><span data-stu-id="cd42c-115">App setup</span></span>
- <span data-ttu-id="cd42c-116">Liveereignisse</span><span class="sxs-lookup"><span data-stu-id="cd42c-116">Live events</span></span>

<span data-ttu-id="cd42c-117">Teams umfasst derzeit die folgenden Richtlinien Pakete für Behörden.</span><span class="sxs-lookup"><span data-stu-id="cd42c-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="cd42c-118">Paket Name im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="cd42c-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="cd42c-119">Am besten geeignet für</span><span class="sxs-lookup"><span data-stu-id="cd42c-119">Best used for</span></span>|<span data-ttu-id="cd42c-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd42c-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="cd42c-121">Beauftragter für öffentliche Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cd42c-121">Public safety officer</span></span>  |<span data-ttu-id="cd42c-122">Beauftragte für öffentliche Sicherheit in ihrer Regierungsorganisation</span><span class="sxs-lookup"><span data-stu-id="cd42c-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="cd42c-123">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="cd42c-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="cd42c-124">First-Manager</span><span class="sxs-lookup"><span data-stu-id="cd42c-124">Firstline manager</span></span>  |<span data-ttu-id="cd42c-125">First-Manager in ihrer Regierungsorganisation</span><span class="sxs-lookup"><span data-stu-id="cd42c-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="cd42c-126">Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf First-Manager in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="cd42c-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="cd42c-127">First-Worker</span><span class="sxs-lookup"><span data-stu-id="cd42c-127">Firstline worker</span></span>  |<span data-ttu-id="cd42c-128">Erste Arbeitskräfte in ihrer Regierungsorganisation</span><span class="sxs-lookup"><span data-stu-id="cd42c-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="cd42c-129">Erstellt eine Reihe von Richtlinien und wendet diese Einstellungen auf Mitarbeiter in Ihrer Organisation in erster Linie an.</span><span class="sxs-lookup"><span data-stu-id="cd42c-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Screenshot der Gesundheitsrichtlinien Pakete](media/policy-packages-gov.png)

<span data-ttu-id="cd42c-131">Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="cd42c-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="cd42c-132">Wenn Sie beispielsweise Benutzern in Ihrer Organisation das Richtlinienpaket für das öffentliche Sicherheitsbeauftragte zuweisen, wird eine Richtlinie mit dem Namen PublicSafety_Officer für jede Richtlinie im Paket erstellt.</span><span class="sxs-lookup"><span data-stu-id="cd42c-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Screenshot der Richtlinien im Healthcare Clinical Worker-Paket](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="cd42c-134">Verwalten von Richtlinienpaketen</span><span class="sxs-lookup"><span data-stu-id="cd42c-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="cd42c-135">Ansicht</span><span class="sxs-lookup"><span data-stu-id="cd42c-135">View</span></span>

<span data-ttu-id="cd42c-136">Zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="cd42c-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="cd42c-137">Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers **Richtlinien Pakete**aus, wählen Sie den Paketnamen aus, und wählen Sie dann den Richtliniennamen aus.</span><span class="sxs-lookup"><span data-stu-id="cd42c-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="cd42c-138">Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.</span><span class="sxs-lookup"><span data-stu-id="cd42c-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="cd42c-139">Anpassen</span><span class="sxs-lookup"><span data-stu-id="cd42c-139">Customize</span></span>

<span data-ttu-id="cd42c-140">Passen Sie die Einstellungen der Richtlinien im Richtlinienpaket nach Bedarf an die Anforderungen Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="cd42c-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="cd42c-141">Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cd42c-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="cd42c-142">Wenn Sie die Einstellungen einer Richtlinie in einem Richtlinienpaket bearbeiten möchten, wählen Sie im Microsoft Teams Admin Center das Richtlinienpaket aus, wählen Sie den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="cd42c-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="cd42c-143">Beachten Sie, dass Sie auch die Einstellungen von Richtlinien in einem Paket ändern können, nachdem Sie das Richtlinienpaket zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="cd42c-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="cd42c-144">Weitere Informationen finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="cd42c-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="cd42c-145">Zuweisen</span><span class="sxs-lookup"><span data-stu-id="cd42c-145">Assign</span></span>

<span data-ttu-id="cd42c-146">Weisen Sie das Richtlinienpaket Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="cd42c-146">Assign the policy package to users.</span></span> <span data-ttu-id="cd42c-147">Wenn Sie einem oder mehreren Benutzern ein Richtlinienpaket zuweisen möchten, klicken Sie auf **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="cd42c-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="cd42c-148">Sie können auch [PowerShell verwenden](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) , um einem Richtlinienpaket große Batches von Benutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="cd42c-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="cd42c-149">Eine schrittweise Anleitung zum Zuweisen eines Richtlinienpakets mit dem Microsoft Teams Admin Center oder PowerShell finden Sie unter [Zuweisen eines Richtlinienpakets](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="cd42c-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Screenshot: Zuweisen eines Richtlinienpakets im Admin Center](media/policy-packages-gov-assign.png)

<span data-ttu-id="cd42c-151">Wenn einem Benutzer eine Richtlinie zugewiesen ist und Sie später eine andere Richtlinie zuweisen, hat die letzte Aufgabe Vorrang.</span><span class="sxs-lookup"><span data-stu-id="cd42c-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cd42c-152">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="cd42c-152">Related topics</span></span>

[<span data-ttu-id="cd42c-153">Verwalten von Richtlinienpaketen in Teams</span><span class="sxs-lookup"><span data-stu-id="cd42c-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="cd42c-154">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cd42c-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 
