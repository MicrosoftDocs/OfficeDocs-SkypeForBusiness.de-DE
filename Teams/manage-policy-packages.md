---
title: Verwalten von Richtlinien Paketen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Richtlinien Pakete in Microsoft Teams verwenden und verwalten.
ms.openlocfilehash: ecfc6ae6fb1bb4d9632b8cd04b35dcee6d63359d
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "38679826"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="0ccea-103">Verwalten von Richtlinien Paketen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0ccea-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="0ccea-104">Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0ccea-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="0ccea-105">Wir haben Richtlinien Pakete entwickelt, um die Konsistenz beim Verwalten von Richtlinien für Gruppen von Benutzern in Ihrer Organisation zu vereinfachen, zu rationalisieren und zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="0ccea-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="0ccea-106">Wenn Sie Benutzern ein Richtlinienpaket zuweisen, werden die Richtlinien im Paket erstellt, und Sie können dann die Einstellungen der Richtlinien im Paket anpassen, um die Anforderungen Ihrer Organisation zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="0ccea-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="0ccea-107">Was ist ein Richtlinienpaket?</span><span class="sxs-lookup"><span data-stu-id="0ccea-107">What is a policy package?</span></span>

<span data-ttu-id="0ccea-108">Mit Richtlinien Paketen können Sie die Teamfunktionen steuern, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="0ccea-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="0ccea-109">Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Aktivitäten für Zusammenarbeit und Kommunikation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0ccea-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="0ccea-110">Teams umfasst derzeit die folgenden Richtlinien Pakete.</span><span class="sxs-lookup"><span data-stu-id="0ccea-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="0ccea-111">**Paket Name**</span><span class="sxs-lookup"><span data-stu-id="0ccea-111">**Package name**</span></span>  |<span data-ttu-id="0ccea-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0ccea-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="0ccea-113">Education_Teacher Paket</span><span class="sxs-lookup"><span data-stu-id="0ccea-113">Education_Teacher package</span></span>     |<span data-ttu-id="0ccea-114">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Lehrer gelten.</span><span class="sxs-lookup"><span data-stu-id="0ccea-114">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="0ccea-115">Education_PrimaryStudent Paket</span><span class="sxs-lookup"><span data-stu-id="0ccea-115">Education_PrimaryStudent package</span></span>    |<span data-ttu-id="0ccea-116">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für primäre Kursteilnehmer gelten.</span><span class="sxs-lookup"><span data-stu-id="0ccea-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="0ccea-117">Education_SecondaryStudent Paket</span><span class="sxs-lookup"><span data-stu-id="0ccea-117">Education_SecondaryStudent package</span></span>    |<span data-ttu-id="0ccea-118">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für sekundäre Kursteilnehmer gelten.</span><span class="sxs-lookup"><span data-stu-id="0ccea-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="0ccea-119">Education_HigherEducationStudent Paket</span><span class="sxs-lookup"><span data-stu-id="0ccea-119">Education_HigherEducationStudent package</span></span>    |<span data-ttu-id="0ccea-120">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Schüler in der Hochschulbildung gelten.</span><span class="sxs-lookup"><span data-stu-id="0ccea-120">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="0ccea-121">SmallMediumBusiness_BusinessVoice Paket</span><span class="sxs-lookup"><span data-stu-id="0ccea-121">SmallMediumBusiness_BusinessVoice package</span></span>    |<span data-ttu-id="0ccea-122">Erstellt eine APP-Setup-Richtlinie, die die apps für ein Business-VoIP-Erlebnis umfasst.</span><span class="sxs-lookup"><span data-stu-id="0ccea-122">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|

> [!NOTE]
> <span data-ttu-id="0ccea-123">Es werden weitere Richtlinien Pakete in zukünftigen Versionen von Teams hinzugefügt, daher sollten Sie sich über die neuesten Informationen informieren.</span><span class="sxs-lookup"><span data-stu-id="0ccea-123">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="0ccea-124">Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="0ccea-124">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="0ccea-125">Wenn Sie beispielsweise Lehrern in ihrer Schule das Education_Teacher-Richtlinienpaket zuweisen, wird eine Richtlinie mit dem Namen Education_Teacher für jede Richtlinie im Paket erstellt.</span><span class="sxs-lookup"><span data-stu-id="0ccea-125">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Screenshot des Education_Teacher-Richtlinienpakets](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="0ccea-127">Verwenden von Richtlinien Paketen</span><span class="sxs-lookup"><span data-stu-id="0ccea-127">How to use policy packages</span></span>

<span data-ttu-id="0ccea-128">Im folgenden wird beschrieben, wie Sie Richtlinien Pakete in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="0ccea-128">The following outlines how to use policy packages in your organization.</span></span>

![Übersicht über das Verwenden von Richtlinien Paketen](media/manage-policy-packages-overview.png)

- <span data-ttu-id="0ccea-130">**[Ansicht](#view-the-settings-of-a-policy-in-a-policy-package)**: zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0ccea-130">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="0ccea-131">Stellen Sie sicher, dass Sie jede Einstellung verstehen, und entscheiden Sie dann, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.</span><span class="sxs-lookup"><span data-stu-id="0ccea-131">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="0ccea-132">Wenn eine Richtlinie gelöscht wird, können Sie weiterhin die Einstellungen anzeigen, aber Sie können keine Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="0ccea-132">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="0ccea-133">Eine gelöschte Richtlinie wird mit den vordefinierten Einstellungen neu erstellt, wenn Sie das Richtlinienpaket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0ccea-133">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="0ccea-134">**[Zuweisen](#assign-a-policy-package)**: weisen Sie das Richtlinienpaket Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="0ccea-134">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="0ccea-135">Beachten Sie, dass Richtlinien in einem Richtlinienpaket erst erstellt werden, nachdem Sie das Paket zugewiesen haben, nach dem Sie die Einstellungen einzelner Richtlinien im Paket ändern können.</span><span class="sxs-lookup"><span data-stu-id="0ccea-135">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="0ccea-136">**[Anpassen](#customize-policies-in-a-policy-package)**: passen Sie die Einstellungen der Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="0ccea-136">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="0ccea-137">Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0ccea-137">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="0ccea-138">Im folgenden finden Sie die Schritte zum Anzeigen, zuweisen und Anpassen von Richtlinien Paketen im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="0ccea-138">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="0ccea-139">Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket</span><span class="sxs-lookup"><span data-stu-id="0ccea-139">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="0ccea-140">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Richtlinien Pakete**, und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="0ccea-140">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="0ccea-141">Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="0ccea-141">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="0ccea-142">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="0ccea-142">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="0ccea-143">Zuweisen eines Richtlinienpakets zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="0ccea-143">Assign a policy package to one user</span></span>

1. <span data-ttu-id="0ccea-144">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0ccea-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="0ccea-145">Klicken Sie auf der Seite des Benutzers auf **Richtlinien**, und klicken Sie dann neben **Richtlinienpaket**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="0ccea-145">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="0ccea-146">Wählen Sie im Bereich **Richtlinienpaket zuweisen** das Paket aus, das Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0ccea-146">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="0ccea-147">Zuweisen eines Richtlinienpakets zu mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="0ccea-147">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="0ccea-148">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Richtlinien Paketen**, und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="0ccea-148">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="0ccea-149">Klicken Sie auf **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="0ccea-149">Click **Manage users**.</span></span>
3. <span data-ttu-id="0ccea-150">Suchen Sie im Bereich **Benutzer verwalten** nach dem Benutzer mit Anzeigename oder nach Benutzername, wählen Sie den Namen aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="0ccea-150">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="0ccea-151">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="0ccea-151">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="0ccea-152">Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0ccea-152">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="0ccea-153">Anpassen von Richtlinien in einem Richtlinienpaket</span><span class="sxs-lookup"><span data-stu-id="0ccea-153">Customize policies in a policy package</span></span>

<span data-ttu-id="0ccea-154">Sie können die Einstellungen einer Richtlinie über die Seite " **Richtlinien Pakete** " Bearbeiten oder direkt zur Seite "Richtlinie" im Microsoft Teams Admin Center wechseln.</span><span class="sxs-lookup"><span data-stu-id="0ccea-154">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="0ccea-155">Führen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="0ccea-155">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="0ccea-156">Klicken Sie auf **Richtlinien Pakete**, und wählen Sie dann das Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="0ccea-156">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="0ccea-157">Klicken Sie auf den Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="0ccea-157">Click the policy type.</span></span>  <span data-ttu-id="0ccea-158">Klicken Sie beispielsweise auf **Messaging Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="0ccea-158">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="0ccea-159">Klicken Sie auf die Richtlinie, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="0ccea-159">Click the policy you want to edit.</span></span> <span data-ttu-id="0ccea-160">Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.</span><span class="sxs-lookup"><span data-stu-id="0ccea-160">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="0ccea-161">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="0ccea-161">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0ccea-162">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="0ccea-162">Troubleshooting</span></span>

<span data-ttu-id="0ccea-163">**Beim Zuweisen eines Richtlinienpakets wird eine Fehlermeldung angezeigt**</span><span class="sxs-lookup"><span data-stu-id="0ccea-163">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="0ccea-164">Dies kann auftreten, wenn eine oder mehrere Richtlinien im Paket nicht erstellt oder erfolgreich angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="0ccea-164">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="0ccea-165">Weisen Sie den Benutzern das Richtlinienpaket erneut zu.</span><span class="sxs-lookup"><span data-stu-id="0ccea-165">Reassign the policy package to your users.</span></span> <span data-ttu-id="0ccea-166">Das erneute Testen des Vorgangs behebt dieses Problem in der Regel.</span><span class="sxs-lookup"><span data-stu-id="0ccea-166">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0ccea-167">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0ccea-167">Related topics</span></span>

[<span data-ttu-id="0ccea-168">Microsoft Teams-Richtlinienpakete für EDU-Administratoren</span><span class="sxs-lookup"><span data-stu-id="0ccea-168">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
