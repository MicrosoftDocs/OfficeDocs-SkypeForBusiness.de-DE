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
ms.openlocfilehash: 67b5abef6cdbdab9a127dd2957c2fdfefbaf2927
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691421"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a><span data-ttu-id="311f1-103">Verwalten von Anrufer-ID-Richtlinien in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="311f1-103">Manage caller ID policies in Microsoft Teams</span></span>

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

<span data-ttu-id="311f1-104">Als Administrator können Sie die Anrufer-ID-Richtlinien in Microsoft Teams verwenden, um die Rufnummernanzeige (auch als Anruf Leitungs-ID bezeichnet) zu ändern oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="311f1-104">As an admin, you can use caller ID policies in Microsoft Teams to change or block the caller ID (also known as calling line ID).</span></span> <span data-ttu-id="311f1-105">Standardmäßig kann die Telefonnummer von Teams-Benutzern angezeigt werden, wenn Sie einen Anruf an ein PSTN-Telefon durchführen, und die Telefonnummer der PSTN-Anrufer kann angezeigt werden, wenn Sie einen Teams-Nutzer anrufen.</span><span class="sxs-lookup"><span data-stu-id="311f1-105">By default, the phone number of Teams users can be seen when they make a call to a PSTN phone and the phone number of PSTN callers can be seen when they call a Teams user.</span></span> <span data-ttu-id="311f1-106">Sie können die Richtlinien für die Rufnummernanzeige verwenden, um eine alternative Telefonnummer für Teams-Benutzer in Ihrer Organisation anzuzeigen oder die Anzeige einer eingehenden Nummer zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="311f1-106">You can use caller ID policies to display an alternate phone number for Teams users in your organization or block an incoming number from being displayed.</span></span>

<span data-ttu-id="311f1-107">Wenn Benutzer beispielsweise einen Anruf führen, können Sie die Rufnummernanzeige ändern, um die Haupttelefonnummer Ihrer Organisation anstelle der Telefonnummern der Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="311f1-107">For example, when users make a call, you can change the caller ID to display your organization's main phone number instead of users' phone numbers.</span></span>

<span data-ttu-id="311f1-108">Sie verwalten die Richtlinien für die Rufnummernanzeige, indem Sie **Voice**  >  im Microsoft Teams Admin Center zu den Richtlinien für die VoIP **-Anruferkennung** wechseln.</span><span class="sxs-lookup"><span data-stu-id="311f1-108">You manage caller ID policies by going to **Voice** > **Caller ID policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="311f1-109">Sie können die globale Standardrichtlinie (Org-wide default) verwenden oder benutzerdefinierte Richtlinien erstellen und diese Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="311f1-109">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="311f1-110">Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="311f1-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="311f1-111">Sie können die globale Standardrichtlinie bearbeiten oder eine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="311f1-111">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="311f1-112">Sofern einem Benutzer eine benutzerdefinierte Richtlinie zugewiesen wurde, gilt diese Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="311f1-112">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="311f1-113">Wurde einem Benutzer keine benutzerdefinierte Richtlinie zugewiesen, gilt für diesen Benutzer die globale Standardrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="311f1-113">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-caller-id-policy"></a><span data-ttu-id="311f1-114">Erstellen einer benutzerdefinierten Anrufer-ID-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="311f1-114">Create a custom caller ID policy</span></span>

1. <span data-ttu-id="311f1-115">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**  >  **-Richtlinien für Anrufer**.</span><span class="sxs-lookup"><span data-stu-id="311f1-115">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="311f1-116">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="311f1-116">Click **Add**.</span></span> <br>
<span data-ttu-id="311f1-117">![Screenshot der Seite "neue Rufnummernanzeige" im Admin Center](media/caller-id-policies-add-policy.png)</span><span class="sxs-lookup"><span data-stu-id="311f1-117">![Screenshot of new caller ID policy page in the admin center](media/caller-id-policies-add-policy.png)</span></span>
3. <span data-ttu-id="311f1-118">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="311f1-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="311f1-119">Wählen Sie hier die gewünschten Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="311f1-119">From here, choose the settings that you want:</span></span>

    - <span data-ttu-id="311f1-120">**Eingehende Anrufer-ID blockieren**: Aktivieren Sie diese Einstellung, um die Rufnummernanzeige für eingehende Anrufe zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="311f1-120">**Block incoming caller ID**: Turn on this setting to block the caller ID of incoming calls from being displayed.</span></span>
    - <span data-ttu-id="311f1-121">**Überschreiben Sie die Richtlinie für die Rufnummern**Anzeige: Aktivieren Sie diese Einstellung, damit Benutzer die Einstellungen in der Richtlinie bezüglich der Anzeige der Rufnummer für Anrufer überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="311f1-121">**Override the caller ID policy**: Turn on this setting to let users override the settings in the policy regarding displaying their number to callees or not.</span></span> <span data-ttu-id="311f1-122">Das bedeutet, dass Benutzer auswählen können, ob Sie Ihre Rufnummernanzeige anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="311f1-122">This means that users can choose whether to display their caller ID.</span></span> <span data-ttu-id="311f1-123">Weitere Informationen finden Sie unter [Endbenutzer-Steuerung der ausgehenden Rufnummern](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)Anzeige.</span><span class="sxs-lookup"><span data-stu-id="311f1-123">For more information, see [End user control of outbound caller ID](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id).</span></span>
    - <span data-ttu-id="311f1-124">**Ersetzen Sie die Rufnummern**Anzeige durch: Legen Sie die Rufnummernanzeige für die Benutzer angezeigt, indem Sie eine der folgenden Optionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="311f1-124">**Replace the caller ID with**: Set the caller ID to be displayed for users by selecting one of the following:</span></span>

        - <span data-ttu-id="311f1-125">**Nummer des Benutzers**: zeigt die Nummer des Benutzers an.</span><span class="sxs-lookup"><span data-stu-id="311f1-125">**User's number**: Displays the user's number.</span></span> 
        - <span data-ttu-id="311f1-126">**Dienstnummer**: Hier können Sie eine Dienst Telefonnummer einrichten, die als Rufnummernanzeige angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="311f1-126">**Service number**: Lets you set a service phone number to display as the caller ID.</span></span>
        - <span data-ttu-id="311f1-127">**Anonym**: zeigt die Rufnummernanzeige als "Anonym" an.</span><span class="sxs-lookup"><span data-stu-id="311f1-127">**Anonymous**: Displays the caller ID as Anonymous.</span></span>

    - <span data-ttu-id="311f1-128">**Ersetzen Sie die Rufnummernanzeige durch diese Service-Nummer**: Wählen Sie eine Dienstnummer aus, um die Rufnummernanzeige der Nutzer zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="311f1-128">**Replace the caller ID with this service number**: Choose a service number to replace the caller ID of users.</span></span> <span data-ttu-id="311f1-129">Diese Option steht zur Verfügung, wenn Sie im **Feld Rufnummernanzeige ersetzen die Rufnummern** **Anzeige ausgewählt haben** .</span><span class="sxs-lookup"><span data-stu-id="311f1-129">This option is available if you selected **Service number** in **Replace the caller ID with**.</span></span>

5. <span data-ttu-id="311f1-130">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="311f1-130">Click **Save**.</span></span>

## <a name="edit-a-caller-id-policy"></a><span data-ttu-id="311f1-131">Bearbeiten einer Rufnummernanzeige-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="311f1-131">Edit a caller ID policy</span></span>

<span data-ttu-id="311f1-132">Sie können die globale Standardrichtlinie bearbeiten oder eine von Ihnen erstellte, benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="311f1-132">You can edit the global policy or any custom policies that you create.</span></span> 

1. <span data-ttu-id="311f1-133">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **VoIP**  >  **-Richtlinien für Anrufer**.</span><span class="sxs-lookup"><span data-stu-id="311f1-133">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="311f1-134">Wählen Sie die Richtlinie aus, indem Sie zunächst links neben die Richtlinienbezeichnung und dann auf **Bearbeiten** klicken.</span><span class="sxs-lookup"><span data-stu-id="311f1-134">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="311f1-135">Ändern Sie die gewünschten Einstellungen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="311f1-135">Change the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-caller-id-policy-to-users"></a><span data-ttu-id="311f1-136">Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="311f1-136">Assign a custom caller ID policy to users</span></span>

<span data-ttu-id="311f1-137">Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie einem oder mehreren Benutzern oder dem Skype for Business PowerShell-Modul zuzuweisen, um Benutzern in einer Gruppe, beispielsweise einer Sicherheitsgruppe oder Verteilergruppe, eine benutzerdefinierte Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="311f1-137">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to users in a group, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-caller-line-id-policy-to-users"></a><span data-ttu-id="311f1-138">Zuweisen einer benutzerdefinierten Richtlinie für die Rufnummernanzeige für Benutzer</span><span class="sxs-lookup"><span data-stu-id="311f1-138">Assign a custom caller line ID policy to users</span></span>

<span data-ttu-id="311f1-139">So weisen Sie einem Benutzer eine Richtlinie zu:</span><span class="sxs-lookup"><span data-stu-id="311f1-139">To assign a policy to one user:</span></span>

1. <span data-ttu-id="311f1-140">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Nutzer**, und klicken Sie dann den gewünschten Nutzer an.</span><span class="sxs-lookup"><span data-stu-id="311f1-140">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="311f1-141">Klicken Sie zunächst auf **Richtlinien** und dann neben **Zugewiesene Richtlinien** auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="311f1-141">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="311f1-142">Wählen Sie unter **Anrufer-ID-Richtlinie**die Richtlinie aus, die Sie zuweisen möchten, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="311f1-142">Under **Caller ID policy**, select the policy you want to assign, and then choose **Save**.</span></span>

<span data-ttu-id="311f1-143">So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu</span><span class="sxs-lookup"><span data-stu-id="311f1-143">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="311f1-144">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="311f1-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="311f1-145">Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="311f1-145">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="311f1-146">Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).</span><span class="sxs-lookup"><span data-stu-id="311f1-146">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="311f1-147">Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.</span><span class="sxs-lookup"><span data-stu-id="311f1-147">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="311f1-148">Sie können auch die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="311f1-148">Or, you can also do the following:</span></span>

1. <span data-ttu-id="311f1-149">Wechseln Sie zu **Microsoft Teams Admin Center**  >  **Voice**  >  **-VoIP-Anruf Erkennungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="311f1-149">Go to **Microsoft Teams admin center** > **Voice** > **Caller ID policies**.</span></span>
2. <span data-ttu-id="311f1-150">Wählen Sie die gewünschte Richtlinie aus, indem Sie links neben die Richtlinienbezeichnung klicken.</span><span class="sxs-lookup"><span data-stu-id="311f1-150">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="311f1-151">Wählen Sie **Benutzer verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="311f1-151">Select **Manage users**.</span></span>
4. <span data-ttu-id="311f1-152">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeigenamens oder des Benutzernamens nach dem Benutzer, wählen Sie den Namen aus, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="311f1-152">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="311f1-153">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen wollen.</span><span class="sxs-lookup"><span data-stu-id="311f1-153">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="311f1-154">Wenn Sie mit dem Hinzufügen von Benutzern fertig sind, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="311f1-154">When you're finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-caller-id-policy-to-users-in-a-group"></a><span data-ttu-id="311f1-155">Zuweisen einer benutzerdefinierten Anrufer-ID-Richtlinie zu Benutzern in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="311f1-155">Assign a custom caller ID policy to users in a group</span></span>

<span data-ttu-id="311f1-156">Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="311f1-156">You may want to assign a custom  policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="311f1-157">So möchten Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="311f1-157">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="311f1-158">Dies ist möglich, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="311f1-158">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="311f1-159">Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="311f1-159">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="311f1-160">In diesem Beispiel weisen wir eine benutzerdefinierte Richtlinie für die Rufnummernanzeige mit der Bezeichnung Support Caller ID-Richtlinie allen Benutzern in der Contoso-Support Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="311f1-160">In this example, we assign a custom caller lID policy called Support Caller ID Policy to all users in the Contoso Support group.</span></span>  

> [!NOTE]
> <span data-ttu-id="311f1-161">Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Microsoft 365-oder Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="311f1-161">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="311f1-162">Abrufen der GroupObject-ID der jeweiligen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="311f1-162">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Support"
```
<span data-ttu-id="311f1-163">Abrufen der Mitglieder der gewählten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="311f1-163">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="311f1-164">Weisen Sie alle Benutzer in der Gruppe einer bestimmten Rufnummernanzeige-Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="311f1-164">Assign all users in the group to a particular caller ID policy.</span></span> <span data-ttu-id="311f1-165">In diesem Beispiel wird die Richtlinie für die Rufnummernanzeige unterstützt.</span><span class="sxs-lookup"><span data-stu-id="311f1-165">In this example, it's Support Caller ID Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsCallingLineIdentity -PolicyName "Support Caller ID Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="311f1-166">Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="311f1-166">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="311f1-167">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="311f1-167">Related topics</span></span>

- [<span data-ttu-id="311f1-168">Neu – CsCallingLineIdentity</span><span class="sxs-lookup"><span data-stu-id="311f1-168">New-CsCallingLineIdentity</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)
- [<span data-ttu-id="311f1-169">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="311f1-169">Assign policies to your users in Teams</span></span>](assign-policies.md)
