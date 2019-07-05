---
title: Verwalten von Richtlinien Paketen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz
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
ROBOTS: NOINDEX, NOFOLLOW
description: Hier erfahren Sie, wie Sie Richtlinien Pakete in Microsoft Teams verwenden und verwalten.
ms.openlocfilehash: 428e3b9d68064beb70b80603df573aa7df9e59c3
ms.sourcegitcommit: d955406a55cdc4c7abb193f1af90ebd4913c47bc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/04/2019
ms.locfileid: "35542365"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="8d4cf-103">Verwalten von Richtlinien Paketen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8d4cf-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="8d4cf-104">Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="8d4cf-105">Wir haben Richtlinien Pakete entwickelt, um die Konsistenz beim Verwalten von Richtlinien für Gruppen von Benutzern in Ihrer Organisation zu vereinfachen, zu rationalisieren und zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="8d4cf-106">Wenn Sie Benutzern ein Richtlinienpaket zuweisen, werden die Richtlinien im Paket erstellt, und Sie können dann die Einstellungen der Richtlinien im Paket anpassen, um die Anforderungen Ihrer Organisation zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="8d4cf-107">Was ist ein Richtlinienpaket?</span><span class="sxs-lookup"><span data-stu-id="8d4cf-107">What is a policy package?</span></span>

<span data-ttu-id="8d4cf-108">Mit Richtlinien Paketen können Sie die Teamfunktionen steuern, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="8d4cf-109">Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Aktivitäten für Zusammenarbeit und Kommunikation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="8d4cf-110">Teams umfasst derzeit die folgenden Richtlinien Pakete.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="8d4cf-111">**Paket Name**</span><span class="sxs-lookup"><span data-stu-id="8d4cf-111">**Package name**</span></span>  |<span data-ttu-id="8d4cf-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8d4cf-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="8d4cf-113">Education_Teacher-Paket</span><span class="sxs-lookup"><span data-stu-id="8d4cf-113">Education_Teacher package</span></span>     |<span data-ttu-id="8d4cf-114">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Lehrer gelten.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-114">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="8d4cf-115">Education_PrimaryStudent-Paket</span><span class="sxs-lookup"><span data-stu-id="8d4cf-115">Education_PrimaryStudent package</span></span>    |<span data-ttu-id="8d4cf-116">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für primäre Kursteilnehmer gelten.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="8d4cf-117">Education_SecondaryStudent-Paket</span><span class="sxs-lookup"><span data-stu-id="8d4cf-117">Education_SecondaryStudent package</span></span>    |<span data-ttu-id="8d4cf-118">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für sekundäre Kursteilnehmer gelten.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="8d4cf-119">Education_HigherEducationStudent-Paket</span><span class="sxs-lookup"><span data-stu-id="8d4cf-119">Education_HigherEducationStudent package</span></span>    |<span data-ttu-id="8d4cf-120">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Schüler in der Hochschulbildung gelten.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-120">Creates a set of policies and policy settings that apply to higher education students.</span></span>|

> [!NOTE]
> <span data-ttu-id="8d4cf-121">Es werden weitere Richtlinien Pakete in zukünftigen Versionen von Teams hinzugefügt, daher sollten Sie sich über die neuesten Informationen informieren.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-121">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="8d4cf-122">Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-122">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="8d4cf-123">Wenn Sie beispielsweise Lehrern in ihrer Schule das Education_Teacher-Richtlinienpaket zuweisen, wird für jede Richtlinie im Paket eine Richtlinie mit dem Namen Education_Teacher erstellt.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-123">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Screenshot des Education_Teacher-Richtlinienpakets](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="8d4cf-125">Verwenden von Richtlinien Paketen</span><span class="sxs-lookup"><span data-stu-id="8d4cf-125">How to use policy packages</span></span>

<span data-ttu-id="8d4cf-126">Im folgenden wird beschrieben, wie Sie Richtlinien Pakete in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-126">The following outlines how to use policy packages in your organization.</span></span>

![Übersicht über das Verwenden von Richtlinien Paketen](media/manage-policy-packages-overview.png)

- <span data-ttu-id="8d4cf-128">**[Ansicht](#view-the-settings-of-a-policy-in-a-policy-package)**: zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-128">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="8d4cf-129">Stellen Sie sicher, dass Sie jede Einstellung verstehen, und entscheiden Sie dann, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-129">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="8d4cf-130">Wenn eine Richtlinie gelöscht wird, können Sie weiterhin die Einstellungen anzeigen, aber Sie können keine Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-130">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="8d4cf-131">Eine gelöschte Richtlinie wird mit den vordefinierten Einstellungen neu erstellt, wenn Sie das Richtlinienpaket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-131">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="8d4cf-132">**[Zuweisen](#assign-a-policy-package)**: weisen Sie das Richtlinienpaket Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-132">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="8d4cf-133">Beachten Sie, dass Richtlinien in einem Richtlinienpaket erst erstellt werden, nachdem Sie das Paket zugewiesen haben, nach dem Sie die Einstellungen einzelner Richtlinien im Paket ändern können.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-133">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="8d4cf-134">**[Anpassen](#customize-policies-in-a-policy-package)**: passen Sie die Einstellungen der Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-134">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="8d4cf-135">Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-135">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="8d4cf-136">Im folgenden finden Sie die Schritte zum Anzeigen, zuweisen und Anpassen von Richtlinien Paketen im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-136">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="8d4cf-137">Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket</span><span class="sxs-lookup"><span data-stu-id="8d4cf-137">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="8d4cf-138">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Richtlinien Pakete**, und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-138">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="8d4cf-139">Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-139">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="8d4cf-140">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="8d4cf-140">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="8d4cf-141">Zuweisen eines Richtlinienpakets zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="8d4cf-141">Assign a policy package to one user</span></span>

1. <span data-ttu-id="8d4cf-142">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-142">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="8d4cf-143">Klicken Sie auf der Seite des Benutzers auf **Richtlinien**, und klicken Sie dann neben **Richtlinienpaket**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-143">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="8d4cf-144">Wählen Sie im Bereich **Richtlinienpaket zuweisen** das Paket aus, das Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-144">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="8d4cf-145">Zuweisen eines Richtlinienpakets zu mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="8d4cf-145">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="8d4cf-146">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Richtlinien Paketen**, und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="8d4cf-147">Klicken Sie auf **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-147">Click **Manage users**.</span></span>
3. <span data-ttu-id="8d4cf-148">Suchen Sie im Bereich **Benutzer verwalten** nach dem Benutzer mit Anzeigename oder nach Benutzername, wählen Sie den Namen aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="8d4cf-149">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-149">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="8d4cf-150">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-150">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="8d4cf-151">Anpassen von Richtlinien in einem Richtlinienpaket</span><span class="sxs-lookup"><span data-stu-id="8d4cf-151">Customize policies in a policy package</span></span>

<span data-ttu-id="8d4cf-152">Sie können die Einstellungen einer Richtlinie über die Seite " **Richtlinien Pakete** " Bearbeiten oder direkt zur Seite "Richtlinie" im Microsoft Teams Admin Center wechseln.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-152">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="8d4cf-153">Führen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="8d4cf-153">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="8d4cf-154">Klicken Sie auf **Richtlinien Pakete**, und wählen Sie dann das Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-154">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="8d4cf-155">Klicken Sie auf den Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-155">Click the policy type.</span></span>  <span data-ttu-id="8d4cf-156">Klicken Sie beispielsweise auf **Messaging Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-156">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="8d4cf-157">Klicken Sie auf die Richtlinie, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-157">Click the policy you want to edit.</span></span> <span data-ttu-id="8d4cf-158">Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-158">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="8d4cf-159">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-159">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8d4cf-160">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="8d4cf-160">Troubleshooting</span></span>

<span data-ttu-id="8d4cf-161">**Beim Zuweisen eines Richtlinienpakets wird eine Fehlermeldung angezeigt**</span><span class="sxs-lookup"><span data-stu-id="8d4cf-161">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="8d4cf-162">Dies kann auftreten, wenn eine oder mehrere Richtlinien im Paket nicht erstellt oder erfolgreich angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-162">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="8d4cf-163">Weisen Sie den Benutzern das Richtlinienpaket erneut zu.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-163">Reassign the policy package to your users.</span></span> <span data-ttu-id="8d4cf-164">Das erneute Testen des Vorgangs behebt dieses Problem in der Regel.</span><span class="sxs-lookup"><span data-stu-id="8d4cf-164">Retrying the operation typically fixes this issue.</span></span>
