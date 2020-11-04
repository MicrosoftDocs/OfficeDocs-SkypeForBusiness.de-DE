---
title: Teams-Richtlinien Pakete für Healthcare
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Hier erfahren Sie, wie Sie Teams-Richtlinien Pakete für Ihre Gesundheitsorganisation verwenden und verwalten.
ms.openlocfilehash: 28db6a594fd8ea579623975c20e96a2ce0189885
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852206"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="10b7e-103">Teams-Richtlinien Pakete für Healthcare</span><span class="sxs-lookup"><span data-stu-id="10b7e-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="10b7e-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="10b7e-104">Overview</span></span>

<span data-ttu-id="10b7e-105">Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="10b7e-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="10b7e-106">Richtlinienpakete vereinfachen und rationalisieren Richtlinien und lassen Sie diese konsistent verwalten.</span><span class="sxs-lookup"><span data-stu-id="10b7e-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="10b7e-107">Sie können die Einstellungen der Richtlinien im Paket entsprechend den Anforderungen Ihrer Benutzer anpassen.</span><span class="sxs-lookup"><span data-stu-id="10b7e-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="10b7e-108">Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="10b7e-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="10b7e-109">Sie können Richtlinien Pakete mit dem Microsoft Teams Admin Center oder mit PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="10b7e-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="10b7e-110">Richtlinien Pakete definieren für die folgenden Richtlinien je nach Paket:</span><span class="sxs-lookup"><span data-stu-id="10b7e-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="10b7e-111">Messaging</span><span class="sxs-lookup"><span data-stu-id="10b7e-111">Messaging</span></span>
- <span data-ttu-id="10b7e-112">Besprechungen</span><span class="sxs-lookup"><span data-stu-id="10b7e-112">Meetings</span></span>
- <span data-ttu-id="10b7e-113">Anrufe</span><span class="sxs-lookup"><span data-stu-id="10b7e-113">Calling</span></span>
- <span data-ttu-id="10b7e-114">App-Setup</span><span class="sxs-lookup"><span data-stu-id="10b7e-114">App setup</span></span>
- <span data-ttu-id="10b7e-115">Liveereignisse</span><span class="sxs-lookup"><span data-stu-id="10b7e-115">Live events</span></span>

<span data-ttu-id="10b7e-116">Teams umfasst derzeit die folgenden Gesundheitsrichtlinien Pakete.</span><span class="sxs-lookup"><span data-stu-id="10b7e-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="10b7e-117">Paket Name im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="10b7e-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="10b7e-118">Am besten geeignet für</span><span class="sxs-lookup"><span data-stu-id="10b7e-118">Best used for</span></span>|<span data-ttu-id="10b7e-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10b7e-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="10b7e-120">Klinischer Mitarbeiter im Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="10b7e-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="10b7e-121">Klinische Mitarbeiter in Ihrer Gesundheitsorganisation</span><span class="sxs-lookup"><span data-stu-id="10b7e-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="10b7e-122">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die klinischen Mitarbeitern wie registrierten Krankenschwestern, Krankenschwestern, Ärzten und Sozialarbeitern vollen Zugriff auf Chats, Anrufe, Schicht Verwaltung und Besprechungen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="10b7e-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="10b7e-123">Healthcare Information Worker</span><span class="sxs-lookup"><span data-stu-id="10b7e-123">Healthcare information worker</span></span>  |<span data-ttu-id="10b7e-124">Information Worker in Ihrer Gesundheitsorganisation</span><span class="sxs-lookup"><span data-stu-id="10b7e-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="10b7e-125">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Information Worker wie IT-Personal, Informatik Personal, Finanz Personal und Compliance Officer, vollständigen Zugriff auf Chats, Anrufe und Besprechungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="10b7e-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="10b7e-126">Patientenzimmer im Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="10b7e-126">Healthcare patient room</span></span>  |<span data-ttu-id="10b7e-127">Patientenraum Geräte</span><span class="sxs-lookup"><span data-stu-id="10b7e-127">Patient room devices</span></span>|<span data-ttu-id="10b7e-128">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patienten Räume in Ihrer Gesundheitsorganisation gelten.</span><span class="sxs-lookup"><span data-stu-id="10b7e-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Screenshot der Gesundheitsrichtlinien Pakete](media/policy-packages-healthcare.png)

<span data-ttu-id="10b7e-130">Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="10b7e-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="10b7e-131">Wenn Sie beispielsweise dem Klinikpersonal in Ihrer Organisation das Clinical Worker-Richtlinienpaket für medizinische Versorgung zuweisen, wird eine Richtlinie mit dem Namen Healthcare_ClinicalWorker für jede Richtlinie im Paket erstellt.</span><span class="sxs-lookup"><span data-stu-id="10b7e-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Screenshot der Richtlinien im Healthcare Clinical Worker-Paket](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="10b7e-133">Erste Schritte mit Richtlinien Paketen</span><span class="sxs-lookup"><span data-stu-id="10b7e-133">Get started with policy packages</span></span>

<span data-ttu-id="10b7e-134">Um Ihnen den Einstieg in die Gesundheitsrichtlinien Pakete zu bereiten, wählen Sie im Microsoft Admin Center-Onboarding-Hub **Healthcare** aus, und wählen Sie dann **Richtlinieneinstellungen nach Rolle zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="10b7e-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare** , and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="10b7e-135">Wenn Sie bereit für die ersten Schritte sind, entscheiden Sie, welchen Richtlinien Paketen Sie Personen in Ihrer Organisation zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="10b7e-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="10b7e-136">Wählen Sie **Richtliniendetails anzeigen** aus, um weitere Informationen zu den spezifischen Richtlinien in einem Paket und den jeweiligen Einstellungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="10b7e-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="10b7e-137">Diese können nach der Zuweisung im Team Admin Center [angepasst werden](manage-policy-packages.md#customize-policies-in-a-policy-package) .</span><span class="sxs-lookup"><span data-stu-id="10b7e-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="10b7e-138">Wählen Sie ein oder mehrere Pakete aus, die Sie zuweisen möchten, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="10b7e-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="10b7e-139">Sie können dem Richtlinienpaket, das sich am besten für ihre Rolle eignet, nach Personen suchen und Sie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="10b7e-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="10b7e-140">Eine Person kann nicht mehr als einem Richtlinienpaket gleichzeitig zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="10b7e-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="10b7e-141">Nachdem Sie dem richtigen Richtlinienpaket Personen hinzugefügt haben, **fertigt Finish** Ihre Auswahl.</span><span class="sxs-lookup"><span data-stu-id="10b7e-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="10b7e-142">Sie können weiterhin Richtlinien Pakete im Microsoft Teams Admin Center anpassen und verwalten.</span><span class="sxs-lookup"><span data-stu-id="10b7e-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="10b7e-143">Verwalten von Richtlinienpaketen</span><span class="sxs-lookup"><span data-stu-id="10b7e-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="10b7e-144">Ansicht</span><span class="sxs-lookup"><span data-stu-id="10b7e-144">View</span></span>

<span data-ttu-id="10b7e-145">Zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="10b7e-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="10b7e-146">Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers **Richtlinien Pakete** aus, wählen Sie den Paketnamen aus, und wählen Sie dann den Richtliniennamen aus.</span><span class="sxs-lookup"><span data-stu-id="10b7e-146">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="10b7e-147">Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.</span><span class="sxs-lookup"><span data-stu-id="10b7e-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="10b7e-148">Anpassen</span><span class="sxs-lookup"><span data-stu-id="10b7e-148">Customize</span></span>

<span data-ttu-id="10b7e-149">Passen Sie die Einstellungen der Richtlinien im Richtlinienpaket nach Bedarf an die Anforderungen Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="10b7e-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="10b7e-150">Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="10b7e-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="10b7e-151">Wenn Sie die Einstellungen einer Richtlinie in einem Richtlinienpaket bearbeiten möchten, wählen Sie im Microsoft Teams Admin Center das Richtlinienpaket aus, wählen Sie den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="10b7e-151">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="10b7e-152">Beachten Sie, dass Sie auch die Einstellungen von Richtlinien in einem Paket ändern können, nachdem Sie das Richtlinienpaket zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="10b7e-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="10b7e-153">Weitere Informationen finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="10b7e-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="10b7e-154">Zuweisen</span><span class="sxs-lookup"><span data-stu-id="10b7e-154">Assign</span></span>

<span data-ttu-id="10b7e-155">Weisen Sie das Richtlinienpaket Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="10b7e-155">Assign the policy package to users.</span></span> <span data-ttu-id="10b7e-156">Wenn Sie einem oder mehreren Benutzern ein Richtlinienpaket zuweisen möchten, klicken Sie auf **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="10b7e-156">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="10b7e-157">Sie können auch [PowerShell verwenden](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) , um einem Richtlinienpaket große Batches von Benutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="10b7e-157">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="10b7e-158">Eine schrittweise Anleitung zum Zuweisen eines Richtlinienpakets mit dem Microsoft Teams Admin Center oder PowerShell finden Sie unter [Zuweisen eines Richtlinienpakets](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="10b7e-158">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Screenshot: Zuweisen eines Richtlinienpakets im Admin Center](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="10b7e-160">Wenn einem Benutzer eine Richtlinie zugewiesen ist und Sie später eine andere Richtlinie zuweisen, hat die letzte Aufgabe Vorrang.</span><span class="sxs-lookup"><span data-stu-id="10b7e-160">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="10b7e-161">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="10b7e-161">Related topics</span></span>

[<span data-ttu-id="10b7e-162">Verwalten von Richtlinienpaketen in Teams</span><span class="sxs-lookup"><span data-stu-id="10b7e-162">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="10b7e-163">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10b7e-163">Assign policies to your users in Teams</span></span>](assign-policies.md)
