---
title: Zuweisen von Richtlinien zu umfangreichen Benutzergruppen in ihrer Schule
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: saragava,karsmith
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Sie mithilfe der Batch Richtlinienzuweisung Richtlinien für große Gruppen von Benutzern in Ihrer Bildungseinrichtung in loser Schüttung für Remote Schulen (teleschool, Tele Schule) zuweisen.
f1keywords: ''
ms.openlocfilehash: 5772a260642b09232e4df5eec57751a39ec2a74a
ms.sourcegitcommit: 86b0956680b867b8bedb2e969220b8006829ee53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2020
ms.locfileid: "44410440"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="0bd4c-103">Zuweisen von Richtlinien zu umfangreichen Benutzergruppen in ihrer Schule</span><span class="sxs-lookup"><span data-stu-id="0bd4c-103">Assign policies to large sets of users in your school</span></span>

<span data-ttu-id="0bd4c-104">Müssen Sie Ihren Kursteilnehmern und Lehrkräften Zugriff auf verschiedene Features in Microsoft Teams gewähren?</span><span class="sxs-lookup"><span data-stu-id="0bd4c-104">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="0bd4c-105">Sie können die Benutzer in Ihrer Organisation anhand des Lizenztyps schnell identifizieren und Ihnen dann die entsprechende Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-105">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="0bd4c-106">In diesem Lernprogramm erfahren Sie, wie Sie mithilfe der [Batch Richtlinienzuweisung](assign-policies.md#assign-a-policy-to-a-batch-of-users) eine Besprechungsrichtlinie Benutzern in Massen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-106">This tutorial shows you how to use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy to users in bulk.</span></span>

<span data-ttu-id="0bd4c-107">Beachten Sie, dass Benutzer in Teams automatisch die globale (org-Wide Standard)-Richtlinie für einen Teams-Richtlinientyp abrufen, sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-107">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="0bd4c-108">Da die Kursteilnehmer häufig die größte Gruppe von Benutzern sind und häufig die restriktivsten Einstellungen erhalten, empfehlen wir, dass Sie die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="0bd4c-108">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="0bd4c-109">Bearbeiten und Anwenden der globalen (org-Wide Standard)-Richtlinie, um die Funktionen für Schüler zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-109">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span> 
- <span data-ttu-id="0bd4c-110">Erstellen Sie eine benutzerdefinierte Richtlinie, die Kernfunktionen wie private Chats und Besprechungsplanung zulässt, und weisen Sie die Richtlinie ihren Mitarbeitern und Pädagogen zu.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-110">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>

<span data-ttu-id="0bd4c-111">Beachten Sie, dass die globale Richtlinie für alle Benutzer in ihrer Schule gelten soll, bis Sie eine benutzerdefinierte Richtlinie erstellt und ihren Mitarbeitern und Pädagogen zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-111">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="0bd4c-112">In diesem Lernprogramm erhalten die Kursteilnehmer die globale Besprechungsrichtlinie, und wir verwenden PowerShell zum Zuweisen einer benutzerdefinierten Besprechungsrichtlinie mit dem Namen "EducatorMeetingPolicy" für Mitarbeiter und Pädagogen in Massen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-112">In this tutorial, students will get the Global meeting policy and we use PowerShell to assign a custom meeting policy named EducatorMeetingPolicy to staff and educators in bulk.</span></span> <span data-ttu-id="0bd4c-113">Wir gehen davon aus, dass Sie die globale Richtlinie so geändert haben, dass Sie die Besprechungseinstellungen für Schüler zugeschnitten und eine benutzerdefinierte Richtlinie erstellt, die die Besprechungs Erfahrung für Mitarbeiter und Pädagogen definiert.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-113">We assume that you've edited the Global policy to tailor meeting settings for students and created a custom policy that defines the meeting experience for staff and educators.</span></span>

![Screenshot der Seite "Besprechungsrichtlinien" im Team Admin Center](media/edu-batch-policy-assignment.png)

<span data-ttu-id="0bd4c-115">Führen Sie die folgenden Schritte aus, um Mitarbeitern und Pädagogen massenweise eine benutzerdefinierte Besprechungsrichtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-115">Follow these steps to assign a custom meeting policy to staff and educators in bulk.</span></span>

## <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="0bd4c-116">Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul und dem Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="0bd4c-116">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="0bd4c-117">Bevor Sie die in diesem Artikel beschriebenen Schritte ausführen, müssen Sie das Azure AD PowerShell für Graph-Modul installieren und eine Verbindung herstellen (um die Benutzer anhand der zugewiesenen Lizenzen zu identifizieren) und das Microsoft Teams PowerShell-Modul (um die Richtlinien diesen Benutzern zuzuweisen).</span><span class="sxs-lookup"><span data-stu-id="0bd4c-117">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="0bd4c-118">Installieren und Herstellen einer Verbindung mit dem Azure AD PowerShell für Graph-Modul</span><span class="sxs-lookup"><span data-stu-id="0bd4c-118">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="0bd4c-119">Öffnen Sie eine erweiterte Windows PowerShell-Eingabeaufforderung (Windows PowerShell als Administrator ausführen), und führen Sie dann die folgenden Schritte aus, um das Azure Active Directory PowerShell für Graph-Modul zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-119">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="0bd4c-120">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Azure AD herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-120">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="0bd4c-121">Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-121">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="0bd4c-122">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="0bd4c-122">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="0bd4c-123">Installieren und Herstellen einer Verbindung mit dem Microsoft Teams PowerShell-Modul</span><span class="sxs-lookup"><span data-stu-id="0bd4c-123">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="0bd4c-124">Führen Sie die folgenden Schritte aus, um das [Microsoft Teams PowerShell-Modul](https://www.powershellgallery.com/packages/MicrosoftTeams)zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-124">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="0bd4c-125">Stellen Sie sicher, dass Sie Version 1.0.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-125">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="0bd4c-126">Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen und eine Sitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-126">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="0bd4c-127">Wenn Sie dazu aufgefordert werden, melden Sie sich mit denselben Administratoranmeldeinformationen an, die Sie für die Verbindung mit Azure AD verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-127">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

## <a name="identify-your-users"></a><span data-ttu-id="0bd4c-128">Identifizieren der Benutzer</span><span class="sxs-lookup"><span data-stu-id="0bd4c-128">Identify your users</span></span>

<span data-ttu-id="0bd4c-129">Führen Sie zunächst die folgenden Schritte aus, um Ihre Mitarbeiter und Pädagogen anhand des Lizenztyps zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-129">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="0bd4c-130">Hier erfahren Sie, welche SKUs in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-130">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="0bd4c-131">Sie können dann Mitarbeiter und Pädagogen identifizieren, denen eine Fakultäts-SKU zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-131">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="0bd4c-132">Was zurückgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="0bd4c-132">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="0bd4c-133">In diesem Beispiel zeigt die Ausgabe, dass die Fakultäts Lizenz SkuId "e97c048c-37a4-45fb-ab50-922fbf07a370" ist.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-133">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="0bd4c-134">Eine Liste der Education-SKUs und SKU-IDs finden Sie unter [Education-SKU-Referenz](sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="0bd4c-134">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="0bd4c-135">Als nächstes führen wir die folgenden Schritte aus, um die Benutzer zu identifizieren, die über diese Lizenz verfügen, und Sie alle zusammen zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-135">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

## <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="0bd4c-136">Zuweisen einer Richtlinie in Massen</span><span class="sxs-lookup"><span data-stu-id="0bd4c-136">Assign a policy in bulk</span></span>

<span data-ttu-id="0bd4c-137">Nun weisen wir Benutzern die entsprechenden Richtlinien in loser Schüttung zu.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-137">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="0bd4c-138">Die maximale Anzahl von Benutzern, für die Sie Richtlinien zuweisen oder aktualisieren können, ist 5.000.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-138">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="0bd4c-139">Wenn Sie beispielsweise über mehr als 5.000 Mitarbeiter und Pädagogen verfügen, müssen Sie mehrere Batches übermitteln.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-139">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>


<span data-ttu-id="0bd4c-140">Führen Sie die folgenden Schritte aus, um Ihren Mitarbeitern und Pädagogen die Besprechungsrichtlinie mit dem Namen EducatorMeetingPolicy zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-140">Run the following to assign the meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="0bd4c-141">Wenn Sie einen anderen Richtlinientyp in Massen zuweisen möchten, wie TeamsMessagingPolicy, müssen Sie ```PolicyType``` zu der Richtlinie, die Sie zuweisen, und ```PolicyName``` dem Richtliniennamen wechseln.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-141">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

## <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="0bd4c-142">Abrufen des Status einer Massen Zuordnung</span><span class="sxs-lookup"><span data-stu-id="0bd4c-142">Get the status of a bulk assignment</span></span>

<span data-ttu-id="0bd4c-143">Jede Massenaufgabe gibt eine Vorgangs-ID zurück, die Sie verwenden können, um den Fortschritt der Richtlinienzuweisungen zu verfolgen oder eventuell auftretende Fehler zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-143">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="0bd4c-144">Führen Sie beispielsweise die folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="0bd4c-144">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="0bd4c-145">Führen Sie die folgenden Schritte aus, um den Zuordnungsstatus jedes Benutzers im Batchvorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-145">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="0bd4c-146">Details zu den einzelnen Benutzern sind in der Eigenschaft zu finden ```UserState``` .</span><span class="sxs-lookup"><span data-stu-id="0bd4c-146">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

## <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="0bd4c-147">Zuweisen einer Richtlinie in loser Schüttung, wenn mehr als 5.000-Benutzer vorhanden sind</span><span class="sxs-lookup"><span data-stu-id="0bd4c-147">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="0bd4c-148">Führen Sie zunächst die folgenden Schritte aus, um zu sehen, wie viele Mitarbeiter und Pädagogen Sie haben:</span><span class="sxs-lookup"><span data-stu-id="0bd4c-148">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="0bd4c-149">Anstatt die vollständige Liste der Benutzer-IDs bereitzustellen, führen Sie die folgenden Schritte aus, um die erste 5.000 und dann die nächste 5.000 usw. anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-149">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="0bd4c-150">Sie können den Bereich der Benutzer-IDs ändern, bis Sie die vollständige Liste der Benutzer erreichen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-150">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="0bd4c-151">Geben Sie beispielsweise ```$faculty[0..4999``` für den ersten Batch ein, verwenden Sie ```$faculty[5000..9999``` für den zweiten Batch, geben Sie ```$faculty[10000..14999``` für den dritten Batch ein, und so weiter.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-151">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

## <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="0bd4c-152">Abrufen der Richtlinien, die einem Benutzer zugewiesen sind</span><span class="sxs-lookup"><span data-stu-id="0bd4c-152">Get the policies assigned to a user</span></span>

<span data-ttu-id="0bd4c-153">Führen Sie die folgenden Schritte aus, um alle Richtlinien anzuzeigen, die einem bestimmten Benutzer zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-153">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="0bd4c-154">Im folgenden Beispiel wird gezeigt, wie Sie die Richtlinien abrufen, die Hannah@contoso.com zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-154">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="0bd4c-155">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="0bd4c-155">FAQ</span></span>

<span data-ttu-id="0bd4c-156">**Ich möchte sicherstellen, dass allen Benutzern, die Schüler, Mitarbeiter und Pädagogen sind, automatisch Richtlinien zugewiesen werden. Wie kann ich das tun?**</span><span class="sxs-lookup"><span data-stu-id="0bd4c-156">**I want to make sure that all users that are students, staff, and educators automatically get policies assigned. How can I do that?**</span></span>

<span data-ttu-id="0bd4c-157">Das Teams-Produktteam unterstützt die Zuweisung von Richtlinien zu Sicherheitsgruppen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-157">The Teams product team is doing work to support assigning policies to security groups.</span></span> <span data-ttu-id="0bd4c-158">Zu diesem Zeitpunkt können Sie Gruppen für Ihre Schüler und Lehrer und dann die entsprechenden Richtlinien für diese Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-158">At that time, you'll be able to create groups for your students and teachers, and then the appropriate policies to those groups.</span></span> <span data-ttu-id="0bd4c-159">Beachten Sie, dass explizite Benutzerzuweisungen (wie die Richtlinien, die Sie mithilfe dieses Lernprogramms zugewiesen haben) die von einer Gruppe geerbten Richtlinien außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-159">Note that explicit user assignments (such as the policies that you've assigned using this tutorial) will override policies inherited from a group.</span></span> <span data-ttu-id="0bd4c-160">Wenn dieses Feature unterstützt wird, erhalten Sie weitere Anweisungen dazu, wie Sie die Richtlinienzuweisung für Gruppen verwenden und Ihre Benutzer aktualisieren können, um sicherzustellen, dass Sie die geerbten Gruppenrichtlinien erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bd4c-160">When this feature is supported, we'll provide more instructions on how to use policy assignment to groups and update your users to ensure they get the inherited group policies.</span></span>

<span data-ttu-id="0bd4c-161">**Ich bin mit PowerShell für Teams nicht vertraut. Wo finde ich weitere Informationen?**</span><span class="sxs-lookup"><span data-stu-id="0bd4c-161">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="0bd4c-162">Weitere Informationen finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0bd4c-162">See [Teams Powershell overview](teams-powershell-overview.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="0bd4c-163">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0bd4c-163">Related topics</span></span>

- [<span data-ttu-id="0bd4c-164">Zuweisen von Richtlinien zu Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="0bd4c-164">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="0bd4c-165">Neu – CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="0bd4c-165">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="0bd4c-166">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="0bd4c-166">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="0bd4c-167">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="0bd4c-167">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)
