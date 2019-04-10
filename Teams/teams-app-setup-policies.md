---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
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
description: Informationen Sie zu Richtlinien für die app Setup in Microsoft-Teams und Nutzung zum Anpassen von Teams für Benutzer in Ihrer Organisation Pin apps.
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: 7e4eaf604c075f8ab95cd40ec7588515c428360c
ms.sourcegitcommit: 9bb2bfd09ca279752dbedf17911ea46568649c4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "31749749"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="63b4f-103">Verwalten von Richtlinien für das App-Setup in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63b4f-103">Manage app setup policies in Microsoft Teams</span></span>

> [!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="63b4f-104">Als Administrator können Sie Richtlinien für die app-Setup zum Anpassen von Microsoft-Teams, um apps zu markieren, die am besten für Ihre Benutzer wichtig sind.</span><span class="sxs-lookup"><span data-stu-id="63b4f-104">As an admin, you can use app setup policies to customize Microsoft Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="63b4f-105">Sie wählen den apps zum Anheften und Festlegen der Reihenfolge, die sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="63b4f-105">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="63b4f-106">Richtlinien für die App Setup können Sie apps, die Benutzer in Ihrer Organisation auch von Drittanbietern oder von Entwicklern in Ihrer Organisation erstellt müssen, präsentieren.</span><span class="sxs-lookup"><span data-stu-id="63b4f-106">App setup policies let you showcase apps that users in your organization need, including ones built by third parties or by developers in your organization.</span></span> <span data-ttu-id="63b4f-107">Sie können auch Richtlinien für die app-Setup zum Verwalten von Features wie integrierter angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="63b4f-107">You can also use app setup policies to manage how built-in features appear.</span></span>

<span data-ttu-id="63b4f-108">Apps sind an die app-Leiste angeheftet.</span><span class="sxs-lookup"><span data-stu-id="63b4f-108">Apps are pinned to the app bar.</span></span> <span data-ttu-id="63b4f-109">Dies ist die Leiste rechts auf dem Desktopclient Teams und am unteren Rand der Teams mobilen Clients (iOS und Android).</span><span class="sxs-lookup"><span data-stu-id="63b4f-109">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span> 

|<span data-ttu-id="63b4f-110">Desktopclient Teams</span><span class="sxs-lookup"><span data-stu-id="63b4f-110">Teams desktop client</span></span>  |<span data-ttu-id="63b4f-111">Teams mobiler Clients</span><span class="sxs-lookup"><span data-stu-id="63b4f-111">Teams mobile client</span></span> |
|---------|---------|
|![App-Setup-Policies-Desktop-App-bar.PNG](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![App-Setup-Policies-Mobile-App-bar.PNG](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="63b4f-114">Sie können Richtlinien für die app Setup in der Verwaltungskonsole von Microsoft-Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="63b4f-114">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="63b4f-115">Verwenden Sie die globale Richtlinie (Org geltende Standard) oder benutzerdefinierte Richtlinien erstellen, und Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-115">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="63b4f-116">Benutzer in Ihrer Organisation erhalten automatisch die globale Richtlinie, es sei denn, Sie erstellen, und weisen Sie eine benutzerdefinierte Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="63b4f-116">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="63b4f-117">Sie können die Einstellungen zum Einschließen von apps, die Sie möchten in der globalen Richtlinie bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="63b4f-117">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="63b4f-118">Wenn Sie Teams für verschiedene Gruppen von Benutzern in Ihrer Organisation anpassen möchten, erstellen und eine oder mehrere benutzerdefinierte Richtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-118">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![App-Setup-policies.png](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="63b4f-120">Wenn ein Benutzer eine benutzerdefinierte Richtlinie zugewiesen ist, gilt diese Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="63b4f-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="63b4f-121">Wenn ein Benutzer eine benutzerdefinierte Richtlinie zugewiesen wird nicht, gilt die globale Richtlinie für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="63b4f-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="63b4f-122">Erstellen Sie eine benutzerdefinierte Anwendung Setup-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="63b4f-122">Create a custom app setup policy</span></span>

<span data-ttu-id="63b4f-123">Das Microsoft-Teams, Administrationscenter können Sie eine benutzerdefinierte Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-123">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="63b4f-124">Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**Apps > **Richtlinien einrichten**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-124">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="63b4f-125">Wählen Sie **neue Richtlinie**aus.</span><span class="sxs-lookup"><span data-stu-id="63b4f-125">Select **New policy**.</span></span>
3. <span data-ttu-id="63b4f-126">Geben Sie einen beschreibenden Namen für die Richtlinie ein, und klicken Sie dann auf **apps hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-126">Enter a descriptive name for the policy, and then click **Add apps**.</span></span>
4. <span data-ttu-id="63b4f-127">Aktivieren oder Deaktivieren von **benutzerdefinierten apps Hochladen zulassen**, je nachdem, ob Sie benutzerdefinierte apps in Teams hoch Benutzern ermöglichen möchten.</span><span class="sxs-lookup"><span data-stu-id="63b4f-127">Turn on or turn off **Allow uploading custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span>
5. <span data-ttu-id="63b4f-128">Suchen Sie im Bereich **Hinzufügen fixiert apps** für die apps, den, die Sie hinzufügen, und klicken Sie dann auf **Hinzufügen**möchten.</span><span class="sxs-lookup"><span data-stu-id="63b4f-128">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="63b4f-129">Sie können auch apps durch app Berechtigungsrichtlinie filtern.</span><span class="sxs-lookup"><span data-stu-id="63b4f-129">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="63b4f-130">Wenn Sie die Liste der apps ausgewählt haben, klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-130">When you've chosen your list of apps, click **Add**.</span></span>

     ![App-Setup-Richtlinien-add-apps.png](media/app-setup-policies-add-apps.png)

6. <span data-ttu-id="63b4f-132">Ordnen Sie die apps in der Reihenfolge, in der Sie sollen in Teams angezeigt, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-132">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

    ![App-Setup-Policies-New-Policy-Setup.PNG](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="63b4f-134">Bearbeiten einer Richtlinie für den app-setup</span><span class="sxs-lookup"><span data-stu-id="63b4f-134">Edit an app setup policy</span></span>

<span data-ttu-id="63b4f-135">Das Microsoft-Teams, Administrationscenter können Sie eine Richtlinie, einschließlich der globalen (Org geltende) Standardrichtlinie und benutzerdefinierte Richtlinien, die Sie erstellen, bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="63b4f-135">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="63b4f-136">Wechseln Sie im linken Navigationsbereich von Microsoft-Teams, Administrationscenter, **Teams**Apps > **Richtlinien einrichten**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-136">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="63b4f-137">Wählen Sie die Richtlinie, den, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="63b4f-137">Select the policy you want to edit.</span></span> 
3. <span data-ttu-id="63b4f-138">Stellen Sie dort die gewünschten Änderungen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-138">From here, make the changes that you want.</span></span> <span data-ttu-id="63b4f-139">Sie können hinzufügen oder entfernen und Ändern der Reihenfolge von apps.</span><span class="sxs-lookup"><span data-stu-id="63b4f-139">You can add, remove, and change the order of apps.</span></span>
4. <span data-ttu-id="63b4f-140">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-140">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="63b4f-141">Zuweisen einer Richtlinie auf benutzerdefinierte Anwendung Setup für Benutzer</span><span class="sxs-lookup"><span data-stu-id="63b4f-141">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="63b4f-142">Das Microsoft-Teams, Administrationscenter können Sie weisen Sie eine benutzerdefinierte Richtlinie für einzelne Benutzer oder die Skype für Business PowerShell-Modul für Gruppen von Benutzern, beispielsweise eine Sicherheitsgruppe oder Verteilergruppe eine benutzerdefinierte Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-142">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63b4f-143">Es wird empfohlen, mithilfe von PowerShell nur für Richtlinien Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-143">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="63b4f-144">Verwenden Sie das Microsoft-Teams, Administrationscenter zu erstellen, bearbeiten und Verwalten von Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="63b4f-144">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="63b4f-145">Zuweisen einer Richtlinie auf benutzerdefinierte Anwendung Setup für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="63b4f-145">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="63b4f-146">Im linken Navigationsbereich von Microsoft-Teams, Administrationscenter wechseln Sie zu dem **Benutzer**, und klicken Sie dann auf Benutzer.</span><span class="sxs-lookup"><span data-stu-id="63b4f-146">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="63b4f-147">Neben **zugewiesene Richtlinien**wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="63b4f-147">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="63b4f-148">Wählen Sie unter **Teams App Setup Richtlinie**die app-Setup-Richtlinie, die Sie zuweisen möchten, und wählen Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-148">Under **Teams App Setup policy**, select the app setup policy you want to assign, and then choose **Save**.</span></span>

    ![App-Setup-Richtlinien-zuweisen-policy.png](media/app-setup-policies-assign-policy.png)

<span data-ttu-id="63b4f-150">Sie können einen oder mehrere Benutzer auch wie folgt eine app-Setup-Richtlinie zuweisen:</span><span class="sxs-lookup"><span data-stu-id="63b4f-150">You can also assign an app setup policy to one or more users as follows:</span></span>

1. <span data-ttu-id="63b4f-151">Navigieren Sie zum **Microsoft-Teams, Administrationscenter** > **Teams apps** > **Richtlinien einrichten**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-151">Go to **Microsoft Teams admin center** > **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="63b4f-152">Wählen Sie die Richtlinie, indem Sie auf links neben den Namen der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="63b4f-152">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="63b4f-153">Wählen Sie **Benutzer verwalten**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-153">Select **Manage users**.</span></span>
4. <span data-ttu-id="63b4f-154">Klicken Sie im Bereich **Benutzer verwalten** Suche für den Benutzer nach Anzeigename oder nach Benutzernamen, wählen Sie den Namen, und wählen Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-154">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="63b4f-155">Wiederholen Sie diesen Schritt für jeden Benutzer, die Sie hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="63b4f-155">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="63b4f-156">Wenn Sie die Benutzer hinzugefügt haben, wählen Sie **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="63b4f-156">When you are finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="63b4f-157">Zuweisen einer Richtlinie auf benutzerdefinierte Anwendung Setup für Benutzer in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="63b4f-157">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="63b4f-158">Sie möchten eine benutzerdefinierte Anwendung Setup-Richtlinie zu mehreren Benutzern zuweisen, die Sie bereits ermittelt haben.</span><span class="sxs-lookup"><span data-stu-id="63b4f-158">You may want to assign a custom app setup policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="63b4f-159">Beispiel: Sie möchten eine Richtlinie für alle Benutzer in einer Sicherheitsgruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-159">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="63b4f-160">Hierzu können Sie eine Verbindung mit Azure Active Directory PowerShell Graph-Modul und die Skype für Business PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="63b4f-160">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="63b4f-161">Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über die PowerShell Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="63b4f-161">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="63b4f-162">In diesem Beispiel weisen wir eine benutzerdefinierte Anwendung Setup Richtlinie HR App Setup Policy aufgerufen, um alle Benutzer in der Gruppe Contoso Pharmaceuticals HR-Projekt.</span><span class="sxs-lookup"><span data-stu-id="63b4f-162">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="63b4f-163">Stellen Sie sicher, dass Sie zuerst die Azure Active Directory-PowerShell-Modul Diagramm und Skype für Business PowerShell-Modul anschließen, durch die Schritte in [Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="63b4f-163">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="63b4f-164">Rufen Sie die GroupObjectId bestimmten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="63b4f-164">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="63b4f-165">Rufen Sie die Mitglieder der angegebenen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="63b4f-165">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="63b4f-166">Weisen Sie alle Benutzer in der Gruppe zu einer bestimmten app-Setup-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="63b4f-166">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="63b4f-167">In diesem Beispiel ist es HR App Setup Policy.</span><span class="sxs-lookup"><span data-stu-id="63b4f-167">In this example, it's HR App Setup Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="63b4f-168">Abhängig von der Anzahl der Elemente in der Gruppe kann dieser Befehl mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="63b4f-168">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="63b4f-169">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="63b4f-169">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="63b4f-170">Arbeiten mit Richtlinien für die app-setup</span><span class="sxs-lookup"><span data-stu-id="63b4f-170">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="63b4f-171">Welche integrierten app-Setup-Richtlinien sind in der Microsoft-Teams-Verwaltungskonsole enthalten?</span><span class="sxs-lookup"><span data-stu-id="63b4f-171">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="63b4f-172">**Global (Org geltende Standard)**: Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie eine andere Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-172">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="63b4f-173">Bearbeiten Sie die globale Richtlinie für die Pin-apps, die für Ihre Benutzer am wichtigsten sind.</span><span class="sxs-lookup"><span data-stu-id="63b4f-173">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="63b4f-174">**FirstLineWorker**: Diese Richtlinie für Firstline Mitarbeiter ist.</span><span class="sxs-lookup"><span data-stu-id="63b4f-174">**FirstLineWorker**: This policy is for firstline workers.</span></span> <span data-ttu-id="63b4f-175">Sie können es Firstline Mitarbeiter in Ihrer Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-175">You can assign it to firstline workers in your organization.</span></span> <span data-ttu-id="63b4f-176">Es ist wichtig, zu wissen, dass Sie wie benutzerdefinierte Richtlinien, die Sie erstellen, weisen Sie die Richtlinie, die Benutzern für die Einstellungen aktiv sein müssen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-176">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="63b4f-177">Weitere Informationen finden Sie in den Abschnitt [weisen Sie eine benutzerdefinierte Anwendung Setup-Richtlinie für Benutzer](#assign-a-custom-app-setup-policy-to-users) dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="63b4f-177">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="63b4f-178">Warum kann ich eine app nicht im Bereich angeheftete apps hinzufügen finden?</span><span class="sxs-lookup"><span data-stu-id="63b4f-178">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="63b4f-179">Nicht alle apps können Teams über eine app Setup zu fixiert werden.</span><span class="sxs-lookup"><span data-stu-id="63b4f-179">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="63b4f-180">Einige apps können diese Funktion nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="63b4f-180">Some apps may not support this functionality.</span></span> <span data-ttu-id="63b4f-181">Um apps zu suchen, die fixiert werden können, suchen Sie für die app im Bereich **Hinzufügen fixiert apps** .</span><span class="sxs-lookup"><span data-stu-id="63b4f-181">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="63b4f-182">Registerkarten, die einem persönlichen Bereich (statische Registerkarten) und von Programmen haben auf dem Desktopclient Teams fixiert werden können, und diese apps im Bereich **Hinzufügen fixiert apps** verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="63b4f-182">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="63b4f-183">Behalten Sie im Hinterkopf Teams app Store alle Teams apps aufgeführt, während der **Hinzufügen fixiert apps** Bereich nur apps umfasst die Teams über eine Richtlinie fixiert werden können.</span><span class="sxs-lookup"><span data-stu-id="63b4f-183">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="63b4f-184">Ich bin ein Teams für Bildungseinrichtungen Admin. Was muss ich über Richtlinien für die app Setup in Teams für Bildungseinrichtungen wissen?</span><span class="sxs-lookup"><span data-stu-id="63b4f-184">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="63b4f-185">Die Aufruf von app nicht in Teams für Bildungseinrichtungen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="63b4f-185">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="63b4f-186">Wenn Sie eine neue benutzerdefinierte Anwendung Setup Richtlinie erstellen, wird die Aufruf von app in der Liste der apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63b4f-186">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="63b4f-187">Jedoch die app wird nicht fixiert Teams Clients und Teams für Bildungseinrichtungen Benutzer werden die Anrufe-app in Teams nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63b4f-187">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span> 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a><span data-ttu-id="63b4f-188">Wie viele apps können auf eine Richtlinie hinzugefügt werden?</span><span class="sxs-lookup"><span data-stu-id="63b4f-188">How many apps can be added to a policy?</span></span>

<span data-ttu-id="63b4f-189">Zu den Teams mobilen Clients (iOS und Android) muss mindestens zwei apps fixiert werden.</span><span class="sxs-lookup"><span data-stu-id="63b4f-189">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="63b4f-190">Weist eine Richtlinie auf weniger als zwei apps, die mobilen Clients die Benutzerrichtlinien werden nicht aktualisiert und stattdessen werden weiterhin die vorhandene Konfiguration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="63b4f-190">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="63b4f-191">Wie lange dauert es Richtlinie, damit Änderungen wirksam werden, bis?</span><span class="sxs-lookup"><span data-stu-id="63b4f-191">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="63b4f-192">Nachdem Sie die globale Richtlinie bearbeiten oder einer Richtlinie zuweisen, dauert es bis zu 24 Stunden, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="63b4f-192">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="63b4f-193">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="63b4f-193">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="63b4f-194">Wie können die Benutzer ihre angeheftete apps in Teams anzeigen?</span><span class="sxs-lookup"><span data-stu-id="63b4f-194">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="63b4f-195">Um alle apps anzuzeigen, die für einen Benutzer fixiert sind, möglicherweise Benutzer je nach der Anzahl der installierten apps und die Größe der ihrer Client-Fenster Teams folgende Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-195">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="63b4f-196">Desktopclient Teams</span><span class="sxs-lookup"><span data-stu-id="63b4f-196">Teams desktop client</span></span> |<span data-ttu-id="63b4f-197">Teams mobiler Clients</span><span class="sxs-lookup"><span data-stu-id="63b4f-197">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="63b4f-198">Klicken Sie in der app-Leiste an der Seite Teams auf **... Weitere apps**.</span><span class="sxs-lookup"><span data-stu-id="63b4f-198">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="63b4f-199">In der app-Leiste am unteren Rand Teams zu führen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-199">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![App-Setup-Policies-Desktop-More-Apps.PNG](media/app-setup-policies-desktop-more-apps.png)<br>   |![App-Setup-Policies-Mobile-More-Apps.PNG](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="63b4f-202">Was muss ich über des mobilen Zugriffs Teams wissen?</span><span class="sxs-lookup"><span data-stu-id="63b4f-202">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="63b4f-203">Die Teams mobilen Clients (iOS und Android) derzeit nicht persönliche apps mit statischen Registerkarten unterstützen.</span><span class="sxs-lookup"><span data-stu-id="63b4f-203">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="63b4f-204">Je nach der apps in der Richtlinie festgelegt sind apps, die auf dem Desktopclient Teams fixiert in Teams mobilen Clients möglicherweise nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63b4f-204">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="63b4f-205">Persönliche Bots werden weiterhin im Chat auf mobilen Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63b4f-205">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="63b4f-206">Mit den mobilen Clients Teams die Benutzer sehen Core Teams apps wie Aktivität, Chat und Teams und können Sie einige apps erste Teilnehmern von Microsoft, wie etwa Schichten anheften.</span><span class="sxs-lookup"><span data-stu-id="63b4f-206">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="63b4f-207">Können Benutzer die Reihenfolge von apps, die über eine Richtlinie fixiert ändern?</span><span class="sxs-lookup"><span data-stu-id="63b4f-207">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="63b4f-208">Derzeit können Benutzer die Reihenfolge der ihre angeheftete apps auf mobilen Clients Teams jedoch nicht auf die Teams Desktop oder Web Clients ändern.</span><span class="sxs-lookup"><span data-stu-id="63b4f-208">Currently, users can change the order of their pinned apps on Teams mobile clients but not on the Teams desktop or web clients.</span></span> 

### <a name="custom-teams-apps"></a><span data-ttu-id="63b4f-209">Benutzerdefinierte Teams apps</span><span class="sxs-lookup"><span data-stu-id="63b4f-209">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="63b4f-210">Meine Organisation eine benutzerdefinierte Teams-Anwendung erstellt und veröffentlicht, auf Elemente verwenden oder den Mandanten app-Katalog, aber das app-Symbol wird nicht angezeigt, wie erwartet, wenn die app auf der app-Leiste in Teams fixiert ist.</span><span class="sxs-lookup"><span data-stu-id="63b4f-210">My organization built a custom Teams app and published it, either to AppSource or the Tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="63b4f-211">Wie behebe ich es?</span><span class="sxs-lookup"><span data-stu-id="63b4f-211">How do I fix it?</span></span> 

<span data-ttu-id="63b4f-212">Stellen Sie sicher, dass die Logorichtlinien befolgen, bevor Sie die app zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="63b4f-212">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="63b4f-213">Finden Sie weitere Informationen finden Sie unter [Prüfliste für die Übermittlung Seller Dashboard](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span><span class="sxs-lookup"><span data-stu-id="63b4f-213">To learn more, see [Checklist for Seller Dashboard submission](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="63b4f-214">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="63b4f-214">Related topics</span></span>
- [<span data-ttu-id="63b4f-215">Administratoreinstellungen für Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="63b4f-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="63b4f-216">Verwalten von Richtlinien für App-Berechtigungen in Teams</span><span class="sxs-lookup"><span data-stu-id="63b4f-216">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="63b4f-217">Verwalten von benutzerdefinierten App-Richtlinien und Einstellungen in Teams</span><span class="sxs-lookup"><span data-stu-id="63b4f-217">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="63b4f-218">Veröffentlichen einer app mit dem Mandanten Apps Katalog vom Client Teams</span><span class="sxs-lookup"><span data-stu-id="63b4f-218">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>](tenant-apps-catalog-teams.md)
