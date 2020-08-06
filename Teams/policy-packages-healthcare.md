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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Teams-Richtlinien Pakete für Ihre Gesundheitsorganisation verwenden und verwalten.
ms.openlocfilehash: e7b01935969105abae447ae896480e1faf67fa40
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578199"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="da014-103">Teams-Richtlinien Pakete für Healthcare</span><span class="sxs-lookup"><span data-stu-id="da014-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="da014-104">Übersicht</span><span class="sxs-lookup"><span data-stu-id="da014-104">Overview</span></span>

<span data-ttu-id="da014-105">Ein [Richtlinienpaket](manage-policy-packages.md) in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="da014-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="da014-106">Richtlinienpakete vereinfachen und rationalisieren Richtlinien und lassen Sie diese konsistent verwalten.</span><span class="sxs-lookup"><span data-stu-id="da014-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="da014-107">Sie können die Einstellungen der Richtlinien im Paket entsprechend den Anforderungen Ihrer Benutzer anpassen.</span><span class="sxs-lookup"><span data-stu-id="da014-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="da014-108">Wenn Sie die Einstellungen von Richtlinien in einem Richtlinienpaket ändern, erhalten alle Benutzer, die diesem Paket zugewiesen sind, die aktualisierten Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="da014-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="da014-109">Sie können Richtlinien Pakete mit dem Microsoft Teams Admin Center oder mit PowerShell verwalten.</span><span class="sxs-lookup"><span data-stu-id="da014-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="da014-110">Richtlinien Pakete definieren für die folgenden Richtlinien je nach Paket:</span><span class="sxs-lookup"><span data-stu-id="da014-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="da014-111">Besprechungen</span><span class="sxs-lookup"><span data-stu-id="da014-111">Meetings</span></span>
- <span data-ttu-id="da014-112">Liveereignisse</span><span class="sxs-lookup"><span data-stu-id="da014-112">Live events</span></span>
- <span data-ttu-id="da014-113">Anrufe</span><span class="sxs-lookup"><span data-stu-id="da014-113">Calling</span></span>
- <span data-ttu-id="da014-114">Messaging</span><span class="sxs-lookup"><span data-stu-id="da014-114">Messaging</span></span>
- <span data-ttu-id="da014-115">Teams</span><span class="sxs-lookup"><span data-stu-id="da014-115">Teams</span></span>
- <span data-ttu-id="da014-116">App-Setup</span><span class="sxs-lookup"><span data-stu-id="da014-116">App setup</span></span>

<span data-ttu-id="da014-117">Teams umfasst derzeit die folgenden Gesundheitsrichtlinien Pakete.</span><span class="sxs-lookup"><span data-stu-id="da014-117">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="da014-118">Paket Name im Microsoft Teams Admin Center</span><span class="sxs-lookup"><span data-stu-id="da014-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="da014-119">Am besten geeignet für</span><span class="sxs-lookup"><span data-stu-id="da014-119">Best used for</span></span>|<span data-ttu-id="da014-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da014-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="da014-121">Klinischer Mitarbeiter im Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="da014-121">Healthcare clinical worker</span></span>  |<span data-ttu-id="da014-122">Klinische Mitarbeiter in Ihrer Gesundheitsorganisation</span><span class="sxs-lookup"><span data-stu-id="da014-122">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="da014-123">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die klinischen Mitarbeitern wie registrierten Krankenschwestern, Krankenschwestern, Ärzten und Sozialarbeitern vollen Zugriff auf Chats, Anrufe, Schicht Verwaltung und Besprechungen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="da014-123">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="da014-124">Healthcare Information Worker</span><span class="sxs-lookup"><span data-stu-id="da014-124">Healthcare information worker</span></span>  |<span data-ttu-id="da014-125">Information Worker in Ihrer Gesundheitsorganisation</span><span class="sxs-lookup"><span data-stu-id="da014-125">Information workers in your healthcare organization</span></span> |<span data-ttu-id="da014-126">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Information Worker wie IT-Personal, Informatik Personal, Finanz Personal und Compliance Officer, vollständigen Zugriff auf Chats, Anrufe und Besprechungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="da014-126">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="da014-127">Patientenzimmer im Gesundheitswesen</span><span class="sxs-lookup"><span data-stu-id="da014-127">Healthcare patient room</span></span>  |<span data-ttu-id="da014-128">Patientenraum Geräte</span><span class="sxs-lookup"><span data-stu-id="da014-128">Patient room devices</span></span>|<span data-ttu-id="da014-129">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für Patienten Räume in Ihrer Gesundheitsorganisation gelten.</span><span class="sxs-lookup"><span data-stu-id="da014-129">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Screenshot der Gesundheitsrichtlinien Pakete](media/policy-packages-healthcare.png)

<span data-ttu-id="da014-131">Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="da014-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="da014-132">Wenn Sie beispielsweise dem Klinikpersonal in Ihrer Organisation das Clinical Worker-Richtlinienpaket für medizinische Versorgung zuweisen, wird eine Richtlinie mit dem Namen Healthcare_ClinicalWorker für jede Richtlinie im Paket erstellt.</span><span class="sxs-lookup"><span data-stu-id="da014-132">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Screenshot der Richtlinien im Healthcare Clinical Worker-Paket](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="da014-134">Verwalten von Richtlinienpaketen</span><span class="sxs-lookup"><span data-stu-id="da014-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="da014-135">Ansicht</span><span class="sxs-lookup"><span data-stu-id="da014-135">View</span></span>

<span data-ttu-id="da014-136">Zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="da014-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="da014-137">Wählen Sie in der linken Navigationsleiste des Microsoft Teams admin Centers **Richtlinien Pakete**aus, wählen Sie den Paketnamen aus, und wählen Sie dann den Richtliniennamen aus.</span><span class="sxs-lookup"><span data-stu-id="da014-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="da014-138">Entscheiden Sie, ob die vordefinierten Werte für Ihre Organisation geeignet sind oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.</span><span class="sxs-lookup"><span data-stu-id="da014-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="da014-139">Anpassen</span><span class="sxs-lookup"><span data-stu-id="da014-139">Customize</span></span>

<span data-ttu-id="da014-140">Passen Sie die Einstellungen der Richtlinien im Richtlinienpaket nach Bedarf an die Anforderungen Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="da014-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="da014-141">Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="da014-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="da014-142">Wenn Sie die Einstellungen einer Richtlinie in einem Richtlinienpaket bearbeiten möchten, wählen Sie im Microsoft Teams Admin Center das Richtlinienpaket aus, wählen Sie den Namen der Richtlinie aus, die Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="da014-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="da014-143">Beachten Sie, dass Sie auch die Einstellungen von Richtlinien in einem Paket ändern können, nachdem Sie das Richtlinienpaket zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="da014-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="da014-144">Weitere Informationen finden Sie unter [Anpassen von Richtlinien in einem Richtlinienpaket](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="da014-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="da014-145">Zuweisen</span><span class="sxs-lookup"><span data-stu-id="da014-145">Assign</span></span>

<span data-ttu-id="da014-146">Weisen Sie das Richtlinienpaket Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="da014-146">Assign the policy package to users.</span></span> <span data-ttu-id="da014-147">Wenn Sie einem oder mehreren Benutzern ein Richtlinienpaket zuweisen möchten, klicken Sie auf **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="da014-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="da014-148">Sie können auch PowerShell verwenden, um einem Richtlinienpaket große Batches von Benutzern zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="da014-148">You can also use PowerShell to assign a policy package to large batches of users.</span></span> <span data-ttu-id="da014-149">Eine schrittweise Anleitung zum Zuweisen eines Richtlinienpakets finden Sie unter [Zuweisen eines Richtlinienpakets](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="da014-149">For steps on how to assign a policy package, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Screenshot: Zuweisen eines Richtlinienpakets im Admin Center](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="da014-151">Wenn einem Benutzer eine Richtlinie zugewiesen ist und Sie später eine andere Richtlinie zuweisen, hat die letzte Aufgabe Vorrang.</span><span class="sxs-lookup"><span data-stu-id="da014-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="da014-152">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="da014-152">Related topics</span></span>

[<span data-ttu-id="da014-153">Verwalten von Richtlinienpaketen in Teams</span><span class="sxs-lookup"><span data-stu-id="da014-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="da014-154">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="da014-154">Assign policies to your users in Teams</span></span>](assign-policies.md)
