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
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Richtlinien Pakete in Microsoft Teams verwenden und verwalten.
ms.openlocfilehash: d7c0ded990225b969579f50ea5f87a32efebe388
ms.sourcegitcommit: 54cbcf917d9663e6aa9760d7399b36c00d66478c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "42857985"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="a7d29-103">Verwalten von Richtlinien Paketen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a7d29-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="a7d29-104">Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="a7d29-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="a7d29-105">Wir haben Richtlinien Pakete entwickelt, um die Konsistenz beim Verwalten von Richtlinien für Gruppen von Benutzern in Ihrer Organisation zu vereinfachen, zu rationalisieren und zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="a7d29-106">Wenn Sie Benutzern ein Richtlinienpaket zuweisen, werden die Richtlinien im Paket erstellt, und Sie können dann die Einstellungen der Richtlinien im Paket anpassen, um die Anforderungen Ihrer Organisation zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a7d29-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

<span data-ttu-id="a7d29-107">Richtlinien Pakete sind für Organisationen der US Government Cloud Community (gcc) nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a7d29-107">Policy packages aren't available for US Government Cloud Community (GCC) organizations.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="a7d29-108">Was ist ein Richtlinienpaket?</span><span class="sxs-lookup"><span data-stu-id="a7d29-108">What is a policy package?</span></span>

<span data-ttu-id="a7d29-109">Mit Richtlinien Paketen können Sie die Teamfunktionen steuern, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-109">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="a7d29-110">Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Aktivitäten für Zusammenarbeit und Kommunikation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a7d29-110">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="a7d29-111">Teams umfasst derzeit die folgenden Richtlinien Pakete.</span><span class="sxs-lookup"><span data-stu-id="a7d29-111">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="a7d29-112">**Paket Name**</span><span class="sxs-lookup"><span data-stu-id="a7d29-112">**Package name**</span></span>  |<span data-ttu-id="a7d29-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="a7d29-113">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="a7d29-114">Bildung (Hochschulstudent)</span><span class="sxs-lookup"><span data-stu-id="a7d29-114">Education (Higher education student)</span></span>    |<span data-ttu-id="a7d29-115">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Schüler in der Hochschulbildung gelten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-115">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="a7d29-116">Education (Primary School Student)</span><span class="sxs-lookup"><span data-stu-id="a7d29-116">Education (Primary school student)</span></span>   |<span data-ttu-id="a7d29-117">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für primäre Kursteilnehmer gelten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-117">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="a7d29-118">Bildung (Secondary School Student)</span><span class="sxs-lookup"><span data-stu-id="a7d29-118">Education (Secondary school student)</span></span>    |<span data-ttu-id="a7d29-119">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für sekundäre Kursteilnehmer gelten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-119">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="a7d29-120">Bildung (Lehrer)</span><span class="sxs-lookup"><span data-stu-id="a7d29-120">Education (Teacher)</span></span>    |<span data-ttu-id="a7d29-121">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Lehrer gelten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-121">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="a7d29-122">Business-VoIP</span><span class="sxs-lookup"><span data-stu-id="a7d29-122">Business voice</span></span> |<span data-ttu-id="a7d29-123">Erstellt eine APP-Setup-Richtlinie, die die apps für ein Business-VoIP-Erlebnis umfasst.</span><span class="sxs-lookup"><span data-stu-id="a7d29-123">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="a7d29-124">Beauftragter für öffentliche Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a7d29-124">Public safety officer</span></span>   |<span data-ttu-id="a7d29-125">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-125">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|
|<span data-ttu-id="a7d29-126">Gesundheitswesen (klinischer Mitarbeiter)</span><span class="sxs-lookup"><span data-stu-id="a7d29-126">Healthcare (Clinical worker)</span></span>  |<span data-ttu-id="a7d29-127">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die klinischen Mitarbeitern wie registrierten Krankenschwestern, Krankenschwestern, Ärzten und Sozialarbeitern vollen Zugriff auf Chats, Anrufe, Schicht Verwaltung und Besprechungen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a7d29-127">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="a7d29-128">Gesundheitswesen (Information Worker)</span><span class="sxs-lookup"><span data-stu-id="a7d29-128">Healthcare (Information worker)</span></span>  |<span data-ttu-id="a7d29-129">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Information Worker wie IT-Personal, Informatik Personal, Finanz Personal und Compliance Officer, vollständigen Zugriff auf Chats, Anrufe und Besprechungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="a7d29-129">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|


> [!NOTE]
> <span data-ttu-id="a7d29-130">Es werden weitere Richtlinien Pakete in zukünftigen Versionen von Teams hinzugefügt, daher sollten Sie sich über die neuesten Informationen informieren.</span><span class="sxs-lookup"><span data-stu-id="a7d29-130">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="a7d29-131">Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="a7d29-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="a7d29-132">Wenn Sie beispielsweise Lehrern in ihrer Schule das Richtlinienpaket Education (Lehrer) zuweisen, wird eine Richtlinie mit dem Namen Education_Teacher für jede Richtlinie im Paket erstellt.</span><span class="sxs-lookup"><span data-stu-id="a7d29-132">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Screenshot des Richtlinienpakets Education (Lehrer)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="a7d29-134">Verwenden von Richtlinien Paketen</span><span class="sxs-lookup"><span data-stu-id="a7d29-134">How to use policy packages</span></span>

<span data-ttu-id="a7d29-135">Im folgenden wird beschrieben, wie Sie Richtlinien Pakete in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7d29-135">The following outlines how to use policy packages in your organization.</span></span>

![Übersicht über das Verwenden von Richtlinien Paketen](media/manage-policy-packages-overview.png)

- <span data-ttu-id="a7d29-137">**[Ansicht](#view-the-settings-of-a-policy-in-a-policy-package)**: zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a7d29-137">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="a7d29-138">Stellen Sie sicher, dass Sie jede Einstellung verstehen, und entscheiden Sie dann, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.</span><span class="sxs-lookup"><span data-stu-id="a7d29-138">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="a7d29-139">Wenn eine Richtlinie gelöscht wird, können Sie weiterhin die Einstellungen anzeigen, aber Sie können keine Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="a7d29-139">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="a7d29-140">Eine gelöschte Richtlinie wird mit den vordefinierten Einstellungen neu erstellt, wenn Sie das Richtlinienpaket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a7d29-140">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="a7d29-141">**[Zuweisen](#assign-a-policy-package)**: weisen Sie das Richtlinienpaket Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="a7d29-141">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="a7d29-142">Beachten Sie, dass Richtlinien in einem Richtlinienpaket erst erstellt werden, nachdem Sie das Paket zugewiesen haben, nach dem Sie die Einstellungen einzelner Richtlinien im Paket ändern können.</span><span class="sxs-lookup"><span data-stu-id="a7d29-142">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="a7d29-143">**[Anpassen](#customize-policies-in-a-policy-package)**: passen Sie die Einstellungen der Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="a7d29-143">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="a7d29-144">Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="a7d29-144">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="a7d29-145">Im folgenden finden Sie die Schritte zum Anzeigen, zuweisen und Anpassen von Richtlinien Paketen im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="a7d29-145">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="a7d29-146">Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket</span><span class="sxs-lookup"><span data-stu-id="a7d29-146">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="a7d29-147">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Richtlinien Pakete**, und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="a7d29-147">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="a7d29-148">Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-148">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="a7d29-149">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="a7d29-149">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="a7d29-150">Zuweisen eines Richtlinienpakets zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="a7d29-150">Assign a policy package to one user</span></span>

1. <span data-ttu-id="a7d29-151">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Benutzer**, und klicken Sie dann den gewünschten Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="a7d29-151">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a7d29-152">Klicken Sie auf der Seite des Benutzers auf **Richtlinien**, und klicken Sie dann neben **Richtlinienpaket**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a7d29-152">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="a7d29-153">Wählen Sie im Bereich **Richtlinienpaket zuweisen** das Paket aus, das Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a7d29-153">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="a7d29-154">Zuweisen eines Richtlinienpakets zu mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="a7d29-154">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="a7d29-155">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Richtlinien Paketen**, und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="a7d29-155">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="a7d29-156">Klicken Sie auf **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="a7d29-156">Click **Manage users**.</span></span>
3. <span data-ttu-id="a7d29-157">Suchen Sie im Bereich **Benutzer verwalten** nach dem Benutzer mit Anzeigename oder nach Benutzername, wählen Sie den Namen aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="a7d29-157">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="a7d29-158">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-158">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a7d29-159">Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a7d29-159">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="a7d29-160">Anpassen von Richtlinien in einem Richtlinienpaket</span><span class="sxs-lookup"><span data-stu-id="a7d29-160">Customize policies in a policy package</span></span>

<span data-ttu-id="a7d29-161">Sie können die Einstellungen einer Richtlinie über die Seite " **Richtlinien Pakete** " Bearbeiten oder direkt zur Seite "Richtlinie" im Microsoft Teams Admin Center wechseln.</span><span class="sxs-lookup"><span data-stu-id="a7d29-161">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="a7d29-162">Führen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="a7d29-162">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="a7d29-163">Klicken Sie auf **Richtlinien Pakete**, und wählen Sie dann das Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="a7d29-163">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="a7d29-164">Klicken Sie auf den Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="a7d29-164">Click the policy type.</span></span>  <span data-ttu-id="a7d29-165">Klicken Sie beispielsweise auf **Messaging Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="a7d29-165">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="a7d29-166">Klicken Sie auf die Richtlinie, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="a7d29-166">Click the policy you want to edit.</span></span> <span data-ttu-id="a7d29-167">Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.</span><span class="sxs-lookup"><span data-stu-id="a7d29-167">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="a7d29-168">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a7d29-168">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a7d29-169">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="a7d29-169">Troubleshooting</span></span>

<span data-ttu-id="a7d29-170">**Beim Zuweisen eines Richtlinienpakets wird eine Fehlermeldung angezeigt**</span><span class="sxs-lookup"><span data-stu-id="a7d29-170">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="a7d29-171">Dies kann auftreten, wenn eine oder mehrere Richtlinien im Paket nicht erstellt oder erfolgreich angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a7d29-171">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="a7d29-172">Weisen Sie den Benutzern das Richtlinienpaket erneut zu.</span><span class="sxs-lookup"><span data-stu-id="a7d29-172">Reassign the policy package to your users.</span></span> <span data-ttu-id="a7d29-173">Das erneute Testen des Vorgangs behebt dieses Problem in der Regel.</span><span class="sxs-lookup"><span data-stu-id="a7d29-173">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a7d29-174">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="a7d29-174">Related topics</span></span>

[<span data-ttu-id="a7d29-175">Microsoft Teams-Richtlinienpakete für EDU-Administratoren</span><span class="sxs-lookup"><span data-stu-id="a7d29-175">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
