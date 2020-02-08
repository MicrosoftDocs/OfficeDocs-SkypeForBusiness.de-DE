---
title: Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die Rufnummernanzeige Richtlinien in Microsoft Teams verwenden und verwalten, um die Rufnummernanzeige von Teams-Benutzern in Ihrer Organisation zu ändern oder zu blockieren.
ms.openlocfilehash: ff2f9a02bdf91eb6296dce03e426be673f83495a
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824543"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="16d7e-103">Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16d7e-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="16d7e-104">Als Administrator können Sie die Anrufer-ID-Richtlinien in Microsoft Teams verwenden, um die Rufnummernanzeige (auch als Anruf Leitungs-ID bezeichnet) zu ändern oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="16d7e-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="16d7e-105">Standardmäßig kann die Telefonnummer von Teams-Benutzern angezeigt werden, wenn Sie einen Anruf an ein PSTN-Telefon durchführen, und die Telefonnummer der PSTN-Anrufer kann angezeigt werden, wenn Sie einen Teams-Nutzer anrufen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="16d7e-106">Sie können die Richtlinien für die Rufnummernanzeige verwenden, um eine alternative Telefonnummer für Teams-Benutzer in Ihrer Organisation anzuzeigen oder die Anzeige einer eingehenden Nummer zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="16d7e-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="16d7e-107">Wenn Benutzer beispielsweise einen Anruf führen, können Sie die Rufnummernanzeige ändern, um die Haupttelefonnummer Ihrer Organisation anstelle der Telefonnummern der Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="16d7e-108">Sie verwalten die Richtlinien für die Rufnummernanzeige, indem Sie im Microsoft Teams Admin Center zu den Richtlinien für die **VoIP** > **-Anruferkennung** wechseln.</span><span class="sxs-lookup"><span data-stu-id="16d7e-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="16d7e-109">Sie können die globale Standardrichtlinie (Org-wide default) verwenden oder benutzerdefinierte Richtlinien erstellen und diese Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="16d7e-110">Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="16d7e-111">Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="16d7e-112">Sofern einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen wurde, gilt diese Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="16d7e-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="16d7e-113">Wurde einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen, gilt für diesen Benutzer die globale Standardrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="16d7e-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="16d7e-114">Erstellen einer benutzerdefinierten Anrufer-ID-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="16d7e-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="16d7e-115">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > **-Richtlinien für Anrufer**.</span><span class="sxs-lookup"><span data-stu-id="16d7e-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="16d7e-116">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="16d7e-116">Click **Add**.</span></span>
<span data-ttu-id="16d7e-117">![Screenshot der Seite "neue Rufnummernanzeige" im Admin Center](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="16d7e-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="16d7e-118">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="16d7e-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="16d7e-119">Wählen Sie hier die gewünschten Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="16d7e-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="16d7e-120">**Eingehende Anrufer-ID blockieren**: Aktivieren Sie diese Einstellung, um die Rufnummernanzeige für eingehende Anrufe zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="16d7e-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="16d7e-121">**Benutzer können die Richtlinien für die Rufnummernanzeige außer Kraft setzen**: Aktivieren Sie diese Einstellung, damit Benutzer die Einstellungen in der Richtlinie bezüglich der Anzeige der Rufnummer für Anrufer überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="16d7e-121">**Users can override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="16d7e-122">Das bedeutet, dass Benutzer auswählen können, ob Sie Ihre Rufnummernanzeige anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="16d7e-122">This means that users can choose whether to display their caller ID.</span></span>
    - <span data-ttu-id="16d7e-123">**Rufnummernanzeige ersetzen**: Legen Sie die Anrufer-ID für die Benutzer angezeigt, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="16d7e-123">**Replace caller ID**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="16d7e-124">**Nummer des Benutzers**: zeigt die Nummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="16d7e-124">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="16d7e-125">**Dienstnummer**: Hier können Sie eine Dienst Telefonnummer einrichten, die als Rufnummernanzeige angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="16d7e-125">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="16d7e-126">**Anonym**: zeigt die Rufnummernanzeige als "Anonym" an.</span><span class="sxs-lookup"><span data-stu-id="16d7e-126">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="16d7e-127">**Dienstnummer, die zum Ersetzen der Rufnummernanzeige verwendet**werden soll: Wählen Sie eine Dienstnummer aus, um die Rufnummernanzeige der Benutzer zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-127">**Service number to use to replace the caller ID**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="16d7e-128">Diese Option steht zur Verfügung, wenn Sie unter **Rufnummernanzeige ersetzen**die Option **Dienstnummer** ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="16d7e-128">This option is available if you selected **Service number** in **Replace caller ID**.</span></span>

5. <span data-ttu-id="16d7e-129">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16d7e-129">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="16d7e-130">Bearbeiten einer Rufnummernanzeige-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="16d7e-130">Edit a caller ID policy</span></span>

<span data-ttu-id="16d7e-131">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-131">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="16d7e-132">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP** > **-Richtlinien für Anrufer**.</span><span class="sxs-lookup"><span data-stu-id="16d7e-132">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="16d7e-133">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="16d7e-133">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="16d7e-134">Ändern Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="16d7e-134">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="16d7e-135">Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="16d7e-135">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="16d7e-136">Um einem oder mehreren Benutzern eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Microsoft Teams Admin Center verwenden. Um Benutzergruppen, z. B. einer Sicherheitsgruppe oder einer Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen, können Sie das Skype for Business PowerShell-Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="16d7e-136">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-a-user"></a><span data-ttu-id="16d7e-137">Zuweisen einer benutzerdefinierten Richtlinie für die Rufnummernanzeige zu einem Benutzer</span><span class="sxs-lookup"><span data-stu-id="16d7e-137">Assign a custom caller line ID policy to a user</span></span>

1. <span data-ttu-id="16d7e-138">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="16d7e-138">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="16d7e-139">Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="16d7e-139">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="16d7e-140">Wählen Sie unter **Anrufer-ID-Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="16d7e-140">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

### <a name="assign-a-custom-calling-line-id-policy-to-multiple-users-at-a-time"></a><span data-ttu-id="16d7e-141">Zuweisen einer benutzerdefinierten Anruf Linien-ID-Richtlinie zu mehreren Benutzern gleichzeitig</span><span class="sxs-lookup"><span data-stu-id="16d7e-141">Assign a custom calling line ID policy to multiple users at a time</span></span>

<span data-ttu-id="16d7e-142">Wenn Sie eine benutzerdefinierte Anruf Linien-ID-Richtlinie mehreren Benutzern gleichzeitig zuweisen möchten, lesen Sie [Bearbeiten der Benutzereinstellungen für Teams in Massen](edit-user-settings-in-bulk.md).</span><span class="sxs-lookup"><span data-stu-id="16d7e-142">To assign a custom calling line Id policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="16d7e-143">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="16d7e-143">Or, you can also do the following:</span></span>

1. <span data-ttu-id="16d7e-144">Wechseln Sie zu **Microsoft Teams Admin Center** > -**VoIP** > **-Anruf Erkennungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="16d7e-144">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="16d7e-145">Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.</span><span class="sxs-lookup"><span data-stu-id="16d7e-145">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="16d7e-146">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="16d7e-146">Select **Manage users**.</span></span>
4. <span data-ttu-id="16d7e-147">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="16d7e-147">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="16d7e-148">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="16d7e-148">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="16d7e-149">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="16d7e-149">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="16d7e-150">Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="16d7e-150">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="16d7e-151">Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-151">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="16d7e-152">So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-152">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="16d7e-153">Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-153">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="16d7e-154">Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="16d7e-154">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="16d7e-155">In diesem Beispiel weisen wir eine benutzerdefinierte Richtlinie für die Rufnummernanzeige mit der Bezeichnung Support Caller ID-Richtlinie allen Benutzern in der Contoso-Support Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="16d7e-155">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="16d7e-156">Stellen Sie sicher, dass Sie zuerst eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="16d7e-156">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="16d7e-157">Abrufen der GroupObject-ID der jeweiligen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="16d7e-157">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="16d7e-158">Abrufen der Mitglieder der gewählten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="16d7e-158">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="16d7e-159">Weisen Sie alle Benutzer in der Gruppe einer bestimmten Rufnummernanzeige-Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="16d7e-159">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="16d7e-160">In diesem Beispiel wird die Richtlinie für die Rufnummernanzeige unterstützt.</span><span class="sxs-lookup"><span data-stu-id="16d7e-160">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="16d7e-161">Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="16d7e-161">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="16d7e-162">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="16d7e-162">Related topics</span></span>

- [<span data-ttu-id="16d7e-163">Neu – CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="16d7e-163">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

