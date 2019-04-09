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
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informationen Sie zu Richtlinien für die app-Berechtigung in der Microsoft-Teams und deren Verwendung zum Steuern, welche apps für Benutzer in Ihrer Organisation zur Verfügung stehen.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: 49200d597811d87ce27d94d9bb19577def6355c1
ms.sourcegitcommit: a505869a3cc2fe6fe4ee18bcbe99bf980aa91a86
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "31520224"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="83c0a-103">Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83c0a-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon.md)]

<span data-ttu-id="83c0a-104">Ein Administrator können Berechtigungsrichtlinien app Sie steuern, welche apps Microsoft-Teams, Benutzer in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-104">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="83c0a-105">Sie können zulassen oder blockieren alle apps oder bestimmte apps, die von Microsoft veröffentlicht dritten und Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="83c0a-105">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="83c0a-106">Wenn Sie eine app blockieren, können Benutzer nicht aus dem Teams app Store zu installieren.</span><span class="sxs-lookup"><span data-stu-id="83c0a-106">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="83c0a-107">Sie können Richtlinien für die app-Berechtigung in der Verwaltungskonsole von Microsoft-Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="83c0a-107">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="83c0a-108">Sie können Einstellungen Org geltende anwenden, verwenden Sie die globale Richtlinie (Org geltende Standard) und Richtlinien erstellen und zuweisen benutzerdefinierte für einzelne Benutzer oder Benutzer in einer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="83c0a-108">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![Screenshot der app Berechtigungsrichtlinie](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="83c0a-110">Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen, und weisen Sie eine benutzerdefinierte Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="83c0a-110">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="83c0a-111">Org geltende app-Einstellungen außer Kraft setzen die globale Richtlinie und alle benutzerdefinierten Richtlinien, die Sie erstellen und Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-111">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="83c0a-112">Angenommen Sie, Sie möchten alle Drittanbieter-apps blockieren und bestimmte apps von Microsoft für die HR-Abteilung in Ihrer Organisation zulassen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-112">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="83c0a-113">Sie würden erstellen Sie eine benutzerdefinierte Richtlinie mit dem Namen HR App Berechtigungsrichtlinie, setzen Sie sie blockieren und Zulassen von apps, die Sie möchten und weisen Sie es Benutzern in der HR-Abteilung.</span><span class="sxs-lookup"><span data-stu-id="83c0a-113">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="83c0a-114">Org geltende app-Einstellungen verwalten</span><span class="sxs-lookup"><span data-stu-id="83c0a-114">Manage org-wide app settings</span></span>

<span data-ttu-id="83c0a-115">Verwenden Sie Org geltende app-Einstellungen auf Steuerelement, welche apps in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-115">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="83c0a-116">Org geltende app-Einstellungen steuern das Verhalten für alle Benutzer und überschreiben Sie alle anderen app Berechtigungsrichtlinien, die Benutzern zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-116">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="83c0a-117">Org geltende app-Einstellungen werden sofort wirksam und können sie bösartiger oder problematisch apps zu steuern.</span><span class="sxs-lookup"><span data-stu-id="83c0a-117">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="83c0a-118">Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**App > **Berechtigungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-118">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="83c0a-119">Wählen Sie **gesamte Org Einstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="83c0a-119">Select **Org-wide settings**.</span></span> <span data-ttu-id="83c0a-120">Sie können dann die gewünschten Einstellungen konfigurieren, in der Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="83c0a-120">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="83c0a-121">![Screenshot der gesamte Org app-Einstellungen](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="83c0a-121">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="83c0a-122">Deaktivieren Sie unter **Drittanbieter - apps**oder aktivieren Sie diese Einstellungen zur Steuerung des Zugriffs auf Drittanbieter-apps:</span><span class="sxs-lookup"><span data-stu-id="83c0a-122">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="83c0a-123">**Zulassen von Drittanbieter - apps in Teams**: Hiermit legen Sie fest, ob Benutzer Drittanbieter-apps verwenden können.</span><span class="sxs-lookup"><span data-stu-id="83c0a-123">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="83c0a-124">**Neue Drittanbieter - apps, die an den Store standardmäßig veröffentlicht zulassen**: Diese steuert, ob neue Drittanbieter-apps, die an die Teams app veröffentlicht werden gespeichert werden automatisch in Teams verfügbar.</span><span class="sxs-lookup"><span data-stu-id="83c0a-124">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="83c0a-125">Sie können diese Option nur festlegen, wenn Sie zulassen, dass Drittanbieter-apps.</span><span class="sxs-lookup"><span data-stu-id="83c0a-125">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="83c0a-126">Klicken Sie unter **benutzerdefinierte apps**deaktivieren Sie oder aktivieren Sie **Zulassen Interaktion mit benutzerdefinierten apps**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-126">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="83c0a-127">Diese Einstellung steuert, ob Benutzer benutzerdefinierte (Sideloaded) apps interagieren können.</span><span class="sxs-lookup"><span data-stu-id="83c0a-127">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="83c0a-128">Beachten Sie, dass dies ermöglicht Benutzern das *Hochladen* von benutzerdefinierten apps unterscheidet beibehalten.</span><span class="sxs-lookup"><span data-stu-id="83c0a-128">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="83c0a-129">Unter **blockiert apps**suchen und Hinzufügen von apps, die Sie in Ihrer Organisation blockieren möchten.</span><span class="sxs-lookup"><span data-stu-id="83c0a-129">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="83c0a-130">Sie können apps aus dem Mandanten app-Katalog oder Teams app Store auswählen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-130">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="83c0a-131">Klicken Sie auf die für die gesamte Org app-Einstellungen **Speichern** , um wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="83c0a-131">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="83c0a-132">Erstellen Sie eine benutzerdefinierte Anwendung Berechtigungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="83c0a-132">Create a custom app permission policy</span></span>

<span data-ttu-id="83c0a-133">Wenn Sie möchten die apps zu steuern, die für verschiedene Gruppen von Benutzern in Ihrer Organisation zur Verfügung stehen, erstellen Sie, und weisen Sie Berechtigungsrichtlinien für eine oder mehrere benutzerdefinierte Anwendung.</span><span class="sxs-lookup"><span data-stu-id="83c0a-133">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="83c0a-134">Sie erstellen und Zuweisen von separaten basierend auf gibt an, ob apps von Microsoft veröffentlicht werden benutzerdefinierte Richtlinien können Drittanbieter oder Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="83c0a-134">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="83c0a-135">Es ist wichtig, zu wissen, dass nach der Erstellung einer benutzerdefinierten Richtlinie nicht mehr ändern können, wenn Drittanbieter-apps in Org geltende Einstellungen deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="83c0a-135">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="83c0a-136">Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**App > **Berechtigungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-136">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="83c0a-137">Wählen Sie **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="83c0a-137">Select **New policy**.</span></span>
    <span data-ttu-id="83c0a-138">![Screenshot des neuen app-Berechtigungsrichtlinie](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="83c0a-138">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="83c0a-139">Geben Sie einen beschreibenden Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="83c0a-139">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="83c0a-140">Wählen Sie unter **Microsoft-apps**, **Drittanbieter - apps**und **Mandanten apps**eine der folgenden:</span><span class="sxs-lookup"><span data-stu-id="83c0a-140">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="83c0a-141">**Alle apps zulassen**</span><span class="sxs-lookup"><span data-stu-id="83c0a-141">**Allow all apps**</span></span>
    - <span data-ttu-id="83c0a-142">**Zulassen Sie bestimmte apps oder blockieren Sie alle anderen**</span><span class="sxs-lookup"><span data-stu-id="83c0a-142">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="83c0a-143">**Blockieren Sie bestimmte apps, und zulassen alle anderen**</span><span class="sxs-lookup"><span data-stu-id="83c0a-143">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="83c0a-144">**Blockieren Sie alle apps**</span><span class="sxs-lookup"><span data-stu-id="83c0a-144">**Block all apps**</span></span>

5. <span data-ttu-id="83c0a-145">Wenn Sie **bestimmte apps zulassen und verhindern, dass Benutzer**ausgewählt haben, fügen Sie die apps, die Sie zulassen möchten:</span><span class="sxs-lookup"><span data-stu-id="83c0a-145">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="83c0a-146">Wählen Sie **apps zulassen**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-146">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="83c0a-147">Suchen Sie nach der apps, die Sie zulassen, und klicken Sie dann auf **Hinzufügen**möchten.</span><span class="sxs-lookup"><span data-stu-id="83c0a-147">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="83c0a-148">Die Suchergebnisse werden mit dem app-Verleger (**Microsoft-apps**, **Drittanbieter - apps**oder **apps Mandanten**) gefiltert.</span><span class="sxs-lookup"><span data-stu-id="83c0a-148">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="83c0a-149">Wenn Sie die Liste der apps ausgewählt haben, klicken Sie auf **Zulassen**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-149">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="83c0a-150">Wenn Sie **bestimmte apps blockieren und alle anderen Benutzern gestatten**ausgewählt haben, suchen Sie nach und Hinzufügen von apps, die Sie blockieren möchten.</span><span class="sxs-lookup"><span data-stu-id="83c0a-150">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="83c0a-151">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-151">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="83c0a-152">Bearbeiten einer Berechtigungsrichtlinie für eine app</span><span class="sxs-lookup"><span data-stu-id="83c0a-152">Edit an app permission policy</span></span>

<span data-ttu-id="83c0a-153">Das Microsoft-Teams, Administrationscenter können Sie eine Richtlinie, einschließlich der globalen (Org geltende) Standardrichtlinie und benutzerdefinierte Richtlinien, die Sie erstellen, bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="83c0a-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="83c0a-154">Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**App > **Berechtigungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-154">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="83c0a-155">Wählen Sie die Richtlinie, den, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="83c0a-155">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="83c0a-156">Stellen Sie dort die gewünschten Änderungen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-156">From here, make the changes that you want.</span></span> <span data-ttu-id="83c0a-157">Sie können basierte auf den Herausgeber der app-Einstellungen verwalten und hinzufügen und Entfernen von apps basierend auf der Einstellung zulassen/blockieren.</span><span class="sxs-lookup"><span data-stu-id="83c0a-157">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="83c0a-158">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-158">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="83c0a-159">Weisen Sie eine benutzerdefinierte Anwendung Berechtigungsrichtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="83c0a-159">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="83c0a-160">Das Microsoft-Teams, Administrationscenter können Sie weisen Sie eine benutzerdefinierte Richtlinie für einzelne Benutzer oder die Skype für Business PowerShell-Modul mehrere Benutzer, wie alle Benutzer in einer Sicherheitsgruppe oder Verteilergruppe eine benutzerdefinierte Richtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-160">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83c0a-161">Es wird empfohlen, mithilfe von PowerShell nur für Richtlinien Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-161">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="83c0a-162">Verwenden Sie das Microsoft-Teams, Administrationscenter zu erstellen, bearbeiten und Verwalten von Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="83c0a-162">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a><span data-ttu-id="83c0a-163">Weisen Sie eine benutzerdefinierte Anwendung Berechtigungsrichtlinie für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="83c0a-163">Assign a custom app permission policy to individual users</span></span>

1. <span data-ttu-id="83c0a-164">Im linken Navigationsbereich von Microsoft-Teams, Administrationscenter wechseln Sie zu dem **Benutzer**, und klicken Sie dann auf Benutzer.</span><span class="sxs-lookup"><span data-stu-id="83c0a-164">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="83c0a-165">Neben **zugewiesene Richtlinien**wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="83c0a-165">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="83c0a-166">Wählen Sie unter **App Berechtigungsrichtlinie**die app-Berechtigung-Richtlinie, den, die Sie zuweisen möchten, und wählen Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-166">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![App-Setup-Berechtigung-zuweisen-policy.png](media/app-permission-policies-assign-policy.png)

<span data-ttu-id="83c0a-168">Sie können einen oder mehrere Benutzer auch wie folgt eine Berechtigungsrichtlinie app zuweisen:</span><span class="sxs-lookup"><span data-stu-id="83c0a-168">You can also assign an app permission policy to one or more users as follows:</span></span>

1. <span data-ttu-id="83c0a-169">Navigieren Sie zum **Microsoft-Teams, Administrationscenter** > **Teams apps** > **Berechtigungsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-169">Go to **Microsoft Teams admin center** > **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="83c0a-170">Wählen Sie die Richtlinie, indem Sie auf links neben den Namen der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="83c0a-170">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="83c0a-171">Wählen Sie **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-171">Select **Manage users**.</span></span>
4. <span data-ttu-id="83c0a-172">Klicken Sie im Bereich **Benutzer verwalten** Suche für den Benutzer nach Anzeigename oder nach Benutzernamen, wählen Sie den Namen, und wählen Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="83c0a-172">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="83c0a-173">Wiederholen Sie diesen Schritt für jeden Benutzer, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="83c0a-173">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="83c0a-174">Wenn Sie die Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="83c0a-174">When you are finished adding users, select **Save**.</span></span>
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="83c0a-175">Weisen Sie eine benutzerdefinierte Anwendung Berechtigungsrichtlinie für Benutzer in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="83c0a-175">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="83c0a-176">Sie möchten eine benutzerdefinierte Anwendung Berechtigungsrichtlinie zu mehreren Benutzern zuweisen, die Sie bereits ermittelt haben.</span><span class="sxs-lookup"><span data-stu-id="83c0a-176">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="83c0a-177">Beispiel: Sie möchten eine Richtlinie für alle Benutzer in einer Sicherheitsgruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="83c0a-177">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="83c0a-178">Hierzu können Sie eine Verbindung mit Azure Active Directory PowerShell Graph-Modul und die Skype für Business PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="83c0a-178">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="83c0a-179">Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über die PowerShell Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="83c0a-179">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="83c0a-180">In diesem Beispiel weisen wir eine benutzerdefinierte Anwendung Berechtigungsrichtlinie HR App Berechtigungsrichtlinie aufgerufen, um alle Benutzer in der Gruppe Contoso Pharmaceuticals HR-Projekt.</span><span class="sxs-lookup"><span data-stu-id="83c0a-180">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="83c0a-181">Stellen Sie sicher, dass Sie zuerst die Azure Active Directory-PowerShell-Modul Diagramm und Skype für Business PowerShell-Modul anschließen, durch die Schritte in [Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="83c0a-181">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="83c0a-182">Rufen Sie die GroupObjectId bestimmten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="83c0a-182">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="83c0a-183">Rufen Sie die Mitglieder der angegebenen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="83c0a-183">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="83c0a-184">Weisen Sie alle Benutzer in der Gruppe zu einer Berechtigungsrichtlinie für einen bestimmten app.</span><span class="sxs-lookup"><span data-stu-id="83c0a-184">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="83c0a-185">In diesem Beispiel ist es HR App Berechtigungsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="83c0a-185">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="83c0a-186">Abhängig von der Anzahl der Elemente in der Gruppe kann dieser Befehl mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="83c0a-186">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="83c0a-187">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="83c0a-187">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="83c0a-188">Arbeiten mit Richtlinien für die app-Berechtigung</span><span class="sxs-lookup"><span data-stu-id="83c0a-188">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="83c0a-189">Kann ich die Codezeile Business (LOB) apps steuern?</span><span class="sxs-lookup"><span data-stu-id="83c0a-189">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="83c0a-190">Ja, können Sie Berechtigungsrichtlinien app verwenden, um die Einführung und Verteilung von benutzerdefinierten (LOB) apps zu steuern.</span><span class="sxs-lookup"><span data-stu-id="83c0a-190">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="83c0a-191">Wie beziehen sich app Berechtigungsrichtlinien angeheftete apps und Richtlinien für die app Setup?</span><span class="sxs-lookup"><span data-stu-id="83c0a-191">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="83c0a-192">Sie können Richtlinien für die app Setup zusammen mit Berechtigungsrichtlinien app verwenden.</span><span class="sxs-lookup"><span data-stu-id="83c0a-192">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="83c0a-193">Vor dem angeheftete apps sind aus dem Satz von aktivierte apps für einen Benutzer ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="83c0a-193">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="83c0a-194">Verfügt ein Benutzer einer Berechtigungsrichtlinie für eine app, die eine app in ihrer app-Richtlinie Setup blockiert, werden nicht darüber hinaus app in Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="83c0a-194">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="83c0a-195">Kann ich app Berechtigungsrichtlinien einschränken Hochladen von benutzerdefinierten apps (auch bekannt als Sideloading) verwenden?</span><span class="sxs-lookup"><span data-stu-id="83c0a-195">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="83c0a-196">Weitere Informationen zum Einschränken des benutzerdefinierten apps hochladen finden Sie unter [Manage benutzerdefinierte app-Richtlinien und Einstellungen in Teams](teams-custom-app-policies-and-settings.md).</span><span class="sxs-lookup"><span data-stu-id="83c0a-196">To learn more about how to restrict uploading custom apps, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="83c0a-197">Wie lange dauert es Richtlinie, damit Änderungen wirksam werden, bis?</span><span class="sxs-lookup"><span data-stu-id="83c0a-197">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="83c0a-198">Nachdem Sie die globale Richtlinie bearbeiten oder einer Richtlinie für Benutzer zuweisen, kann es bis zu 24 Stunden, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="83c0a-198">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="83c0a-199">Org geltende app-Einstellungen werden sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="83c0a-199">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="83c0a-200">Bezieht blockieren einer app Teams mobilen Clients sich auf?</span><span class="sxs-lookup"><span data-stu-id="83c0a-200">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="83c0a-201">Ja, wenn Sie eine app blockieren, wird diese app über alle Teams Clients blockiert.</span><span class="sxs-lookup"><span data-stu-id="83c0a-201">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="83c0a-202">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="83c0a-202">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="83c0a-203">Was fest ein Benutzer, wenn eine app ausgeschlossen wird?</span><span class="sxs-lookup"><span data-stu-id="83c0a-203">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="83c0a-204">Benutzer können nicht mit einer blockierten app oder seine Funktionen, solche Bots, Registerkarten und messaging Extensions interagieren.</span><span class="sxs-lookup"><span data-stu-id="83c0a-204">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="83c0a-205">In einem freigegebenen Kontext, beispielsweise einen Chat Team- oder Gruppenmitglieder können Bots weiterhin Nachrichten an alle Teilnehmer dieses Kontexts senden.</span><span class="sxs-lookup"><span data-stu-id="83c0a-205">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="83c0a-206">Teams informiert den Benutzer bei eine app ausgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="83c0a-206">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="83c0a-207">Beispielsweise, wenn eine app gesperrt wird, können nicht Benutzer der folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="83c0a-207">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="83c0a-208">Fügen Sie die app persönlich oder einen Chat oder Teams</span><span class="sxs-lookup"><span data-stu-id="83c0a-208">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="83c0a-209">Senden von Nachrichten an die app bot</span><span class="sxs-lookup"><span data-stu-id="83c0a-209">Send messages to the app’s bot</span></span>
- <span data-ttu-id="83c0a-210">Ausführen von Aktionen, die Informationen zurück an die app, beispielsweise bearbeitungsfähige Nachrichten senden</span><span class="sxs-lookup"><span data-stu-id="83c0a-210">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="83c0a-211">Anzeigen der app-Registerkarte</span><span class="sxs-lookup"><span data-stu-id="83c0a-211">View the app’s tab</span></span>
- <span data-ttu-id="83c0a-212">Einrichten von Connectors zum Empfangen von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="83c0a-212">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="83c0a-213">Verwenden Sie die app-messaging-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="83c0a-213">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="83c0a-214">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="83c0a-214">Related topics</span></span>
- [<span data-ttu-id="83c0a-215">Administratoreinstellungen für Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="83c0a-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="83c0a-216">Verwalten von Richtlinien für App-Setup in Teams</span><span class="sxs-lookup"><span data-stu-id="83c0a-216">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="83c0a-217">Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams</span><span class="sxs-lookup"><span data-stu-id="83c0a-217">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
