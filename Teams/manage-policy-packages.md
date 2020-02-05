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
f1.keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Richtlinien Pakete in Microsoft Teams verwenden und verwalten.
ms.openlocfilehash: d73cd22cc0a98cd772ba3823fffa3649602010bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41772747"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="f0433-103">Verwalten von Richtlinien Paketen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0433-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="f0433-104">Ein Richtlinienpaket in Microsoft Teams ist eine Sammlung vordefinierter Richtlinien und Richtlinieneinstellungen, die Sie Benutzern zuweisen können, die ähnliche Rollen in Ihrer Organisation aufweisen.</span><span class="sxs-lookup"><span data-stu-id="f0433-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="f0433-105">Wir haben Richtlinien Pakete entwickelt, um die Konsistenz beim Verwalten von Richtlinien für Gruppen von Benutzern in Ihrer Organisation zu vereinfachen, zu rationalisieren und zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="f0433-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="f0433-106">Wenn Sie Benutzern ein Richtlinienpaket zuweisen, werden die Richtlinien im Paket erstellt, und Sie können dann die Einstellungen der Richtlinien im Paket anpassen, um die Anforderungen Ihrer Organisation zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="f0433-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="f0433-107">Was ist ein Richtlinienpaket?</span><span class="sxs-lookup"><span data-stu-id="f0433-107">What is a policy package?</span></span>

<span data-ttu-id="f0433-108">Mit Richtlinien Paketen können Sie die Teamfunktionen steuern, die Sie für bestimmte Gruppen von Personen in Ihrer Organisation zulassen oder einschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="f0433-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="f0433-109">Jedes Richtlinienpaket in Teams ist auf eine Benutzerrolle zugeschnitten und enthält vordefinierte Richtlinien und Richtlinieneinstellungen, die die für diese Rolle typischen Aktivitäten für Zusammenarbeit und Kommunikation unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f0433-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="f0433-110">Teams umfasst derzeit die folgenden Richtlinien Pakete.</span><span class="sxs-lookup"><span data-stu-id="f0433-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="f0433-111">**Paket Name**</span><span class="sxs-lookup"><span data-stu-id="f0433-111">**Package name**</span></span>  |<span data-ttu-id="f0433-112">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="f0433-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="f0433-113">Bildung (Hochschulstudent)</span><span class="sxs-lookup"><span data-stu-id="f0433-113">Education (Higher education student)</span></span>    |<span data-ttu-id="f0433-114">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Schüler in der Hochschulbildung gelten.</span><span class="sxs-lookup"><span data-stu-id="f0433-114">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="f0433-115">Education (Primary School Student)</span><span class="sxs-lookup"><span data-stu-id="f0433-115">Education (Primary school student)</span></span>   |<span data-ttu-id="f0433-116">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für primäre Kursteilnehmer gelten.</span><span class="sxs-lookup"><span data-stu-id="f0433-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="f0433-117">Bildung (Secondary School Student)</span><span class="sxs-lookup"><span data-stu-id="f0433-117">Education (Secondary school student)</span></span>    |<span data-ttu-id="f0433-118">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für sekundäre Kursteilnehmer gelten.</span><span class="sxs-lookup"><span data-stu-id="f0433-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="f0433-119">Bildung (Lehrer)</span><span class="sxs-lookup"><span data-stu-id="f0433-119">Education (Teacher)</span></span>    |<span data-ttu-id="f0433-120">Erstellt einen Satz von Richtlinien und Richtlinieneinstellungen, die für Lehrer gelten.</span><span class="sxs-lookup"><span data-stu-id="f0433-120">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="f0433-121">Business-VoIP</span><span class="sxs-lookup"><span data-stu-id="f0433-121">Business voice</span></span> |<span data-ttu-id="f0433-122">Erstellt eine APP-Setup-Richtlinie, die die apps für ein Business-VoIP-Erlebnis umfasst.</span><span class="sxs-lookup"><span data-stu-id="f0433-122">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="f0433-123">Beauftragter für öffentliche Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f0433-123">Public safety officer</span></span>   |<span data-ttu-id="f0433-124">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die für öffentliche Sicherheitsbeauftragte in Ihrer Organisation gelten.</span><span class="sxs-lookup"><span data-stu-id="f0433-124">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|
|<span data-ttu-id="f0433-125">Gesundheitswesen (klinischer Mitarbeiter)</span><span class="sxs-lookup"><span data-stu-id="f0433-125">Healthcare (Clinical worker)</span></span>  |<span data-ttu-id="f0433-126">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die klinischen Mitarbeitern wie registrierten Krankenschwestern, Krankenschwestern, Ärzten und Sozialarbeitern vollen Zugriff auf Chats, Anrufe, Schicht Verwaltung und Besprechungen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f0433-126">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="f0433-127">Gesundheitswesen (Information Worker)</span><span class="sxs-lookup"><span data-stu-id="f0433-127">Healthcare (Information worker)</span></span>  |<span data-ttu-id="f0433-128">Erstellt eine Reihe von Richtlinien und Richtlinieneinstellungen, die Information Worker wie IT-Personal, Informatik Personal, Finanz Personal und Compliance Officer, vollständigen Zugriff auf Chats, Anrufe und Besprechungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f0433-128">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|


> [!NOTE]
> <span data-ttu-id="f0433-129">Es werden weitere Richtlinien Pakete in zukünftigen Versionen von Teams hinzugefügt, daher sollten Sie sich über die neuesten Informationen informieren.</span><span class="sxs-lookup"><span data-stu-id="f0433-129">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="f0433-130">Jede einzelne Richtlinie erhält den Namen des Richtlinienpakets, sodass Sie die Richtlinien, die mit einem Richtlinienpaket verknüpft sind, einfach identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="f0433-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="f0433-131">Wenn Sie beispielsweise Lehrern in ihrer Schule das Richtlinienpaket Education (Lehrer) zuweisen, wird eine Richtlinie mit dem Namen Education_Teacher für jede Richtlinie im Paket erstellt.</span><span class="sxs-lookup"><span data-stu-id="f0433-131">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Screenshot des Richtlinienpakets Education (Lehrer)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="f0433-133">Verwenden von Richtlinien Paketen</span><span class="sxs-lookup"><span data-stu-id="f0433-133">How to use policy packages</span></span>

<span data-ttu-id="f0433-134">Im folgenden wird beschrieben, wie Sie Richtlinien Pakete in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0433-134">The following outlines how to use policy packages in your organization.</span></span>

![Übersicht über das Verwenden von Richtlinien Paketen](media/manage-policy-packages-overview.png)

- <span data-ttu-id="f0433-136">**[Ansicht](#view-the-settings-of-a-policy-in-a-policy-package)**: zeigen Sie die Einstellungen der einzelnen Richtlinien in einem Richtlinienpaket an, bevor Sie ein Paket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f0433-136">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="f0433-137">Stellen Sie sicher, dass Sie jede Einstellung verstehen, und entscheiden Sie dann, ob die vordefinierten Werte für Ihre Organisation geeignet sind, oder ob Sie Sie entsprechend den Anforderungen Ihrer Organisation restriktiver oder nachsichtig gestalten müssen.</span><span class="sxs-lookup"><span data-stu-id="f0433-137">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="f0433-138">Wenn eine Richtlinie gelöscht wird, können Sie weiterhin die Einstellungen anzeigen, aber Sie können keine Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="f0433-138">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="f0433-139">Eine gelöschte Richtlinie wird mit den vordefinierten Einstellungen neu erstellt, wenn Sie das Richtlinienpaket zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f0433-139">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="f0433-140">**[Zuweisen](#assign-a-policy-package)**: weisen Sie das Richtlinienpaket Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="f0433-140">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="f0433-141">Beachten Sie, dass Richtlinien in einem Richtlinienpaket erst erstellt werden, nachdem Sie das Paket zugewiesen haben, nach dem Sie die Einstellungen einzelner Richtlinien im Paket ändern können.</span><span class="sxs-lookup"><span data-stu-id="f0433-141">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="f0433-142">**[Anpassen](#customize-policies-in-a-policy-package)**: passen Sie die Einstellungen der Richtlinien im Richtlinienpaket an die Anforderungen Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="f0433-142">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="f0433-143">Alle Änderungen, die Sie an Richtlinieneinstellungen vornehmen, werden automatisch auf Benutzer angewendet, denen das Paket zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="f0433-143">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="f0433-144">Im folgenden finden Sie die Schritte zum Anzeigen, zuweisen und Anpassen von Richtlinien Paketen im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="f0433-144">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="f0433-145">Anzeigen der Einstellungen einer Richtlinie in einem Richtlinienpaket</span><span class="sxs-lookup"><span data-stu-id="f0433-145">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="f0433-146">Klicken Sie in der linken Navigationsleiste des Microsoft Teams admin Centers auf **Richtlinien Pakete**, und wählen Sie dann ein Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="f0433-146">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="f0433-147">Klicken Sie auf die Richtlinie, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="f0433-147">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="f0433-148">Zuweisen eines Richtlinienpakets</span><span class="sxs-lookup"><span data-stu-id="f0433-148">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="f0433-149">Zuweisen eines Richtlinienpakets zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="f0433-149">Assign a policy package to one user</span></span>

1. <span data-ttu-id="f0433-150">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f0433-150">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="f0433-151">Klicken Sie auf der Seite des Benutzers auf **Richtlinien**, und klicken Sie dann neben **Richtlinienpaket**auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f0433-151">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="f0433-152">Wählen Sie im Bereich **Richtlinienpaket zuweisen** das Paket aus, das Sie zuweisen möchten, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f0433-152">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="f0433-153">Zuweisen eines Richtlinienpakets zu mehreren Benutzern</span><span class="sxs-lookup"><span data-stu-id="f0433-153">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="f0433-154">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Richtlinien Paketen**, und wählen Sie dann das Richtlinienpaket aus, das Sie zuweisen möchten, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="f0433-154">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="f0433-155">Klicken Sie auf **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="f0433-155">Click **Manage users**.</span></span>
3. <span data-ttu-id="f0433-156">Suchen Sie im Bereich **Benutzer verwalten** nach dem Benutzer mit Anzeigename oder nach Benutzername, wählen Sie den Namen aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="f0433-156">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="f0433-157">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="f0433-157">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="f0433-158">Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f0433-158">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="f0433-159">Anpassen von Richtlinien in einem Richtlinienpaket</span><span class="sxs-lookup"><span data-stu-id="f0433-159">Customize policies in a policy package</span></span>

<span data-ttu-id="f0433-160">Sie können die Einstellungen einer Richtlinie über die Seite " **Richtlinien Pakete** " Bearbeiten oder direkt zur Seite "Richtlinie" im Microsoft Teams Admin Center wechseln.</span><span class="sxs-lookup"><span data-stu-id="f0433-160">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="f0433-161">Führen Sie in der linken Navigationsleiste des Microsoft Teams Admin Center eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="f0433-161">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="f0433-162">Klicken Sie auf **Richtlinien Pakete**, und wählen Sie dann das Richtlinienpaket aus, indem Sie links neben dem Paketnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="f0433-162">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="f0433-163">Klicken Sie auf den Richtlinientyp.</span><span class="sxs-lookup"><span data-stu-id="f0433-163">Click the policy type.</span></span>  <span data-ttu-id="f0433-164">Klicken Sie beispielsweise auf **Messaging Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="f0433-164">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="f0433-165">Klicken Sie auf die Richtlinie, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="f0433-165">Click the policy you want to edit.</span></span> <span data-ttu-id="f0433-166">Richtlinien, die mit einem Richtlinienpaket verknüpft sind, haben denselben Namen wie das Richtlinienpaket.</span><span class="sxs-lookup"><span data-stu-id="f0433-166">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="f0433-167">Nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f0433-167">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f0433-168">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="f0433-168">Troubleshooting</span></span>

<span data-ttu-id="f0433-169">**Beim Zuweisen eines Richtlinienpakets wird eine Fehlermeldung angezeigt**</span><span class="sxs-lookup"><span data-stu-id="f0433-169">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="f0433-170">Dies kann auftreten, wenn eine oder mehrere Richtlinien im Paket nicht erstellt oder erfolgreich angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="f0433-170">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="f0433-171">Weisen Sie den Benutzern das Richtlinienpaket erneut zu.</span><span class="sxs-lookup"><span data-stu-id="f0433-171">Reassign the policy package to your users.</span></span> <span data-ttu-id="f0433-172">Das erneute Testen des Vorgangs behebt dieses Problem in der Regel.</span><span class="sxs-lookup"><span data-stu-id="f0433-172">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f0433-173">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f0433-173">Related topics</span></span>

[<span data-ttu-id="f0433-174">Microsoft Teams-Richtlinienpakete für EDU-Administratoren</span><span class="sxs-lookup"><span data-stu-id="f0433-174">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
