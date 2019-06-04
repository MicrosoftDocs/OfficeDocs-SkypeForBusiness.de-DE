---
title: Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
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
description: Erfahren Sie mehr über APP-Berechtigungsrichtlinien in Microsoft Teams und wie Sie Sie verwenden können, um zu steuern, welche apps für Benutzer in Ihrer Organisation verfügbar sind.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: fac559fb492155af9953beb74c2fac1526f01432
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681921"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="86229-103">Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86229-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> <span data-ttu-id="86229-104">Die aktuelle Methode zum Verwalten von apps in Microsoft Teams finden Sie unter [Verwalten von Microsoft Teams-Einstellungen für Ihre Organisation](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).</span><span class="sxs-lookup"><span data-stu-id="86229-104">For the current method of managing apps in Microsoft Teams, see [Manage Microsoft Teams settings for your organization](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).</span></span>

<span data-ttu-id="86229-105">Als Administrator können Sie App-Berechtigungsrichtlinien verwenden, um zu steuern, welche apps Microsoft Teams-Benutzern in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="86229-105">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="86229-106">Sie können alle apps oder bestimmte apps, die von Microsoft, Drittanbietern und Ihrer Organisation veröffentlicht wurden, zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="86229-106">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="86229-107">Wenn Sie eine APP blockieren, können Benutzer Sie nicht aus dem App Store von Teams installieren.</span><span class="sxs-lookup"><span data-stu-id="86229-107">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="86229-108">Sie verwalten App-Berechtigungsrichtlinien im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="86229-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="86229-109">Sie können die Einstellungen organisationsweit anwenden, die globale (org-Wide Standard)-Richtlinie verwenden sowie benutzerdefinierte Richtlinien für einzelne Benutzer oder Benutzer in einer Gruppe erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="86229-109">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![Screenshot der APP-Berechtigungsrichtlinie](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="86229-111">Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, wenn Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="86229-111">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="86229-112">Organisationsweite App-Einstellungen überschreiben die globale Richtlinie und alle benutzerdefinierten Richtlinien, die Sie erstellen und Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="86229-112">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="86229-113">Angenommen, Sie möchten alle Drittanbieter-apps blockieren und bestimmte apps von Microsoft für das HR-Team in Ihrer Organisation zulassen.</span><span class="sxs-lookup"><span data-stu-id="86229-113">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="86229-114">Sie würden eine benutzerdefinierte Richtlinie mit dem Namen HR-App-Berechtigungsrichtlinie erstellen, Sie so festlegen, dass Sie die gewünschten apps blockiert und zulässt, und Sie dann den Benutzern im HR-Team zuweisen.</span><span class="sxs-lookup"><span data-stu-id="86229-114">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="86229-115">Verwalten von organisationsweiten App-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="86229-115">Manage org-wide app settings</span></span>

<span data-ttu-id="86229-116">Verwenden Sie organisationsweite App-Einstellungen, um zu steuern, welche apps in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="86229-116">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="86229-117">Organisationsweite App-Einstellungen Regeln das Verhalten für alle Benutzer und überschreiben alle anderen APP-Berechtigungsrichtlinien, die Benutzern zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="86229-117">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="86229-118">Organisationsweite App-Einstellungen werden sofort wirksam, und Sie können Sie zum Steuern bösartiger oder problematischer Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="86229-118">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="86229-119">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den**Berechtigungsrichtlinien**für **Teams-App** > .</span><span class="sxs-lookup"><span data-stu-id="86229-119">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="86229-120">Wählen Sie **organisationsweite Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="86229-120">Select **Org-wide settings**.</span></span> <span data-ttu-id="86229-121">Anschließend können Sie die gewünschten Einstellungen im Panel konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="86229-121">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="86229-122">![Screenshot der organisationsweiten App-Einstellungen](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="86229-122">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="86229-123">Deaktivieren oder aktivieren Sie unter **apps von Drittanbietern**diese Einstellungen, um den Zugriff auf Drittanbieter-apps zu steuern:</span><span class="sxs-lookup"><span data-stu-id="86229-123">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="86229-124">**Drittanbieter-apps in Teams zulassen**: Hiermit wird gesteuert, ob Benutzer apps von Drittanbietern verwenden können.</span><span class="sxs-lookup"><span data-stu-id="86229-124">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="86229-125">**Alle neuen Drittanbieter-apps zulassen, die standardmäßig im Store veröffentlicht**werden: Hiermit wird gesteuert, ob neue Drittanbieter-apps, die im App Store für Teams veröffentlicht werden, automatisch in Teams verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="86229-125">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="86229-126">Diese Option kann nur festgesetzt werden, wenn Sie Drittanbieter-apps zulassen.</span><span class="sxs-lookup"><span data-stu-id="86229-126">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="86229-127">Deaktivieren oder aktivieren Sie unter **benutzerdefinierte apps**die Option **Interaktion mit benutzerdefinierten apps zulassen**.</span><span class="sxs-lookup"><span data-stu-id="86229-127">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="86229-128">Diese Einstellung steuert, ob Benutzer mit benutzerdefinierten (quer geladene)-apps interagieren können.</span><span class="sxs-lookup"><span data-stu-id="86229-128">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="86229-129">Beachten Sie, dass dies anders ist, als Benutzern das *hochladen* benutzerdefinierter apps zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="86229-129">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="86229-130">Suchen Sie unter **Blockierte apps**nach den apps, die Sie in Ihrer Organisation blockieren möchten, und fügen Sie Sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="86229-130">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="86229-131">Sie können apps im Mandanten-App-Katalog oder im Teams-App-Store auswählen.</span><span class="sxs-lookup"><span data-stu-id="86229-131">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="86229-132">Klicken Sie auf **Speichern** , damit die App-Einstellungen für die gesamte Organisation wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="86229-132">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="86229-133">Erstellen einer benutzerdefinierten App-Berechtigungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="86229-133">Create a custom app permission policy</span></span>

<span data-ttu-id="86229-134">Wenn Sie die apps steuern möchten, die für unterschiedliche Benutzergruppen in Ihrer Organisation verfügbar sind, erstellen Sie eine oder mehrere benutzerdefinierte App-Berechtigungsrichtlinien, und weisen Sie diese zu.</span><span class="sxs-lookup"><span data-stu-id="86229-134">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="86229-135">Sie können separate benutzerdefinierte Richtlinien erstellen und zuweisen, je nachdem, ob apps von Microsoft, Drittanbietern oder Ihrer Organisation veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="86229-135">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="86229-136">Es ist wichtig zu wissen, dass Sie, nachdem Sie eine benutzerdefinierte Richtlinie erstellt haben, Sie nicht ändern können, wenn apps von Drittanbietern in organisationsweiten Einstellungen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="86229-136">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="86229-137">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den**Berechtigungsrichtlinien**für **Teams-App** > .</span><span class="sxs-lookup"><span data-stu-id="86229-137">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="86229-138">Wählen Sie **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="86229-138">Select **New policy**.</span></span>
    <span data-ttu-id="86229-139">![Screenshot der neuen App-Berechtigungsrichtlinie](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="86229-139">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="86229-140">Geben Sie einen aussagekräftigen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="86229-140">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="86229-141">Wählen Sie unter **Microsoft-apps**, **Drittanbieter-apps**und Mandanten- **apps**eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="86229-141">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="86229-142">**Alle apps zulassen**</span><span class="sxs-lookup"><span data-stu-id="86229-142">**Allow all apps**</span></span>
    - <span data-ttu-id="86229-143">**Zulassen bestimmter apps und Blockieren aller anderen Personen**</span><span class="sxs-lookup"><span data-stu-id="86229-143">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="86229-144">**Blockieren bestimmter apps und zulassen aller anderen Personen**</span><span class="sxs-lookup"><span data-stu-id="86229-144">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="86229-145">**Blockieren aller apps**</span><span class="sxs-lookup"><span data-stu-id="86229-145">**Block all apps**</span></span>

5. <span data-ttu-id="86229-146">Wenn Sie **bestimmte apps zulassen und andere blockieren**ausgewählt haben, fügen Sie die apps hinzu, die Sie zulassen möchten:</span><span class="sxs-lookup"><span data-stu-id="86229-146">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="86229-147">Wählen Sie **apps zulassen**aus.</span><span class="sxs-lookup"><span data-stu-id="86229-147">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="86229-148">Suchen Sie nach den apps, die Sie zulassen möchten, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="86229-148">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="86229-149">Die Suchergebnisse werden nach dem App-Publisher (**Microsoft-apps**, **Drittanbieter-apps**oder **Mandanten-apps**) gefiltert.</span><span class="sxs-lookup"><span data-stu-id="86229-149">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="86229-150">Wenn Sie die Liste der apps ausgewählt haben, klicken Sie auf **zulassen**.</span><span class="sxs-lookup"><span data-stu-id="86229-150">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="86229-151">Wenn Sie **bestimmte apps blockieren und alle anderen Personen zulassen**ausgewählt haben, suchen Sie nach den apps, die Sie blockieren möchten, und fügen Sie Sie hinzu.</span><span class="sxs-lookup"><span data-stu-id="86229-151">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="86229-152">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="86229-152">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="86229-153">Bearbeiten einer APP-Berechtigungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="86229-153">Edit an app permission policy</span></span>

<span data-ttu-id="86229-154">Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der Global (org-Wide Standard)-Richtlinie und der von Ihnen erstellten benutzerdefinierten Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="86229-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="86229-155">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den**Berechtigungsrichtlinien**für **Teams-App** > .</span><span class="sxs-lookup"><span data-stu-id="86229-155">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="86229-156">Wählen Sie die Richtlinie aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="86229-156">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="86229-157">Nehmen Sie hier die gewünschten Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="86229-157">From here, make the changes that you want.</span></span> <span data-ttu-id="86229-158">Sie können Einstellungen basierend auf dem App Publisher verwalten und apps basierend auf der Einstellung Zulassen/Blockieren hinzufügen und entfernen.</span><span class="sxs-lookup"><span data-stu-id="86229-158">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="86229-159">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="86229-159">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="86229-160">Zuweisen einer benutzerdefinierten App-Berechtigungsrichtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="86229-160">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="86229-161">Sie können das Microsoft Teams Admin Center verwenden, um einzelnen Benutzern oder dem Skype for Business PowerShell-Modul eine benutzerdefinierte Richtlinie zuzuweisen, um mehreren Benutzern eine benutzerdefinierte Richtlinie zuzuweisen, beispielsweise alle Benutzer in einer Sicherheitsgruppe oder Verteilergruppe.</span><span class="sxs-lookup"><span data-stu-id="86229-161">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="86229-162">Es wird empfohlen, PowerShell nur zum Zuweisen von Richtlinien für Benutzer zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="86229-162">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="86229-163">Verwenden Sie das Microsoft Teams Admin Center, um Richtlinien zu erstellen, zu bearbeiten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="86229-163">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a><span data-ttu-id="86229-164">Zuweisen einer benutzerdefinierten App-Berechtigungsrichtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="86229-164">Assign a custom app permission policy to individual users</span></span>

1. <span data-ttu-id="86229-165">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="86229-165">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="86229-166">Wählen Sie neben **zugewiesene Richtlinien**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="86229-166">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="86229-167">Wählen Sie unter **App-Berechtigungsrichtlinie**die APP-Berechtigungsrichtlinie aus, die Sie zuweisen möchten, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="86229-167">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![App-Setup-Permission-Assign-Policy. png](media/app-permission-policies-assign-policy.png)

<span data-ttu-id="86229-169">Sie können auch eine APP-Berechtigungsrichtlinie für einen oder mehrere Benutzer wie folgt zuweisen:</span><span class="sxs-lookup"><span data-stu-id="86229-169">You can also assign an app permission policy to one or more users as follows:</span></span>

1. <span data-ttu-id="86229-170">Wechseln Sie zu den**Berechtigungsrichtlinien**für **Microsoft Teams Admin Center** > **Teams-apps** > .</span><span class="sxs-lookup"><span data-stu-id="86229-170">Go to **Microsoft Teams admin center** > **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="86229-171">Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken.</span><span class="sxs-lookup"><span data-stu-id="86229-171">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="86229-172">Wählen Sie **Benutzer verwalten**aus.</span><span class="sxs-lookup"><span data-stu-id="86229-172">Select **Manage users**.</span></span>
4. <span data-ttu-id="86229-173">Suchen Sie im Bereich **Benutzer verwalten** anhand des Anzeige namens oder nach dem Benutzernamen nach dem Benutzer, wählen Sie den Namen aus, und wählen Sie dann **Hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="86229-173">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="86229-174">Wiederholen Sie diesen Schritt für jeden Benutzer, den Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="86229-174">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="86229-175">Wenn Sie alle Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="86229-175">When you are finished adding users, select **Save**.</span></span>
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="86229-176">Zuweisen einer benutzerdefinierten App-Berechtigungsrichtlinie zu Benutzern in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="86229-176">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="86229-177">Möglicherweise möchten Sie mehreren Benutzern, die Sie bereits identifiziert haben, eine benutzerdefinierte App-Berechtigungsrichtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="86229-177">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="86229-178">So können Sie beispielsweise allen Benutzern in einer Sicherheitsgruppe eine Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="86229-178">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="86229-179">Sie können dies tun, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="86229-179">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="86229-180">Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86229-180">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="86229-181">In diesem Beispiel weisen wir allen Benutzern in der Projektgruppe "Contoso Pharmaceuticals HR" eine benutzerdefinierte App-Berechtigungsrichtlinie mit dem Namen "HR-App-Berechtigungsrichtlinie" zu.</span><span class="sxs-lookup"><span data-stu-id="86229-181">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="86229-182">Stellen Sie sicher, dass Sie zunächst eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Herstellen einer Verbindung mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="86229-182">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="86229-183">Rufen Sie die GroupObjectId der jeweiligen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="86229-183">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="86229-184">Rufen Sie die Mitglieder der angegebenen Gruppe ab.</span><span class="sxs-lookup"><span data-stu-id="86229-184">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="86229-185">Weisen Sie allen Benutzern in der Gruppe eine bestimmte App-Berechtigungsrichtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="86229-185">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="86229-186">In diesem Beispiel handelt es sich um die Berechtigungsrichtlinie für HR-app.</span><span class="sxs-lookup"><span data-stu-id="86229-186">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="86229-187">Je nach Anzahl der Mitglieder in der Gruppe kann dieser Befehl mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="86229-187">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="86229-188">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="86229-188">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="86229-189">Arbeiten mit App-Berechtigungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="86229-189">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="86229-190">Kann ich Branchen-Apps (Business) steuern?</span><span class="sxs-lookup"><span data-stu-id="86229-190">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="86229-191">Ja, Sie können APP-Berechtigungsrichtlinien zum Steuern des Rollouts und der Verteilung von benutzerdefinierten (LOB-) Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="86229-191">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="86229-192">Wie beziehen sich app-Berechtigungsrichtlinien auf angeheftete apps und App-Setup Richtlinien?</span><span class="sxs-lookup"><span data-stu-id="86229-192">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="86229-193">Sie können APP-Setup Richtlinien zusammen mit App-Berechtigungsrichtlinien verwenden.</span><span class="sxs-lookup"><span data-stu-id="86229-193">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="86229-194">Vor angeheftete apps werden aus der Gruppe aktivierter Apps für einen Benutzer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="86229-194">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="86229-195">Darüber hinaus wird die app in Teams nicht angezeigt, wenn ein Benutzer über eine APP-Berechtigungsrichtlinie verfügt, die eine app in Ihrer APP-Setup Richtlinie blockiert.</span><span class="sxs-lookup"><span data-stu-id="86229-195">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="86229-196">Kann ich App-Berechtigungsrichtlinien verwenden, um das Hochladen benutzerdefinierter Apps (auch bekannt als Sideloading) zu beschränken?</span><span class="sxs-lookup"><span data-stu-id="86229-196">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="86229-197">Weitere Informationen dazu, wie Sie das Hochladen benutzerdefinierter apps einschränken, finden Sie unter [Verwalten von benutzerdefinierten App-Richtlinien und-Einstellungen in Teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="86229-197">To learn more about how to restrict uploading custom apps, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="86229-198">Wie lange dauert es, bis Richtlinienänderungen wirksam werden?</span><span class="sxs-lookup"><span data-stu-id="86229-198">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="86229-199">Nachdem Sie die globale Richtlinie bearbeitet oder Benutzern eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="86229-199">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="86229-200">Organisationsweite App-Einstellungen werden sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="86229-200">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="86229-201">Gilt das Blockieren einer APP für Mobile Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="86229-201">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="86229-202">Ja, wenn Sie eine APP blockieren, wird diese APP für alle Teams-Clients blockiert.</span><span class="sxs-lookup"><span data-stu-id="86229-202">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="86229-203">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="86229-203">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="86229-204">Was kann ein Benutzer erleben, wenn eine APP blockiert wird?</span><span class="sxs-lookup"><span data-stu-id="86229-204">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="86229-205">Benutzer können nicht mit einer blockierten APP oder deren Funktionen, wie Bots, Tabstopps und Messaging Erweiterungen interagieren.</span><span class="sxs-lookup"><span data-stu-id="86229-205">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="86229-206">In einem freigegebenen Kontext wie einem Team-oder Gruppen-Chat können Bots weiterhin Nachrichten an alle Teilnehmer dieses Kontexts senden.</span><span class="sxs-lookup"><span data-stu-id="86229-206">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="86229-207">Teams zeigt dem Benutzer an, wenn eine APP blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="86229-207">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="86229-208">Wenn beispielsweise eine APP blockiert ist, können die Benutzer keine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="86229-208">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="86229-209">Hinzufügen der app persönlich oder eines Chats oder Teams</span><span class="sxs-lookup"><span data-stu-id="86229-209">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="86229-210">Senden von Nachrichten an den App-bot</span><span class="sxs-lookup"><span data-stu-id="86229-210">Send messages to the app’s bot</span></span>
- <span data-ttu-id="86229-211">Durchführen von Schaltflächenaktionen, die Informationen zurück an die APP senden, wie etwa umsetzbare Nachrichten</span><span class="sxs-lookup"><span data-stu-id="86229-211">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="86229-212">Anzeigen der Registerkarte der APP</span><span class="sxs-lookup"><span data-stu-id="86229-212">View the app’s tab</span></span>
- <span data-ttu-id="86229-213">Einrichten von Connectors zum Empfangen von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="86229-213">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="86229-214">Verwenden der Messaging-Erweiterung der APP</span><span class="sxs-lookup"><span data-stu-id="86229-214">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="86229-215">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="86229-215">Related topics</span></span>
- [<span data-ttu-id="86229-216">Administratoreinstellungen für Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86229-216">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="86229-217">Verwalten von Richtlinien für App-Setup in Teams</span><span class="sxs-lookup"><span data-stu-id="86229-217">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="86229-218">Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams</span><span class="sxs-lookup"><span data-stu-id="86229-218">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
