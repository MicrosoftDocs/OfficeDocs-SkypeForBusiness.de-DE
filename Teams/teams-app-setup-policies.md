---
title: Verwalten von Richtlinien für das App-Setup in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie App-Setup Richtlinien in Microsoft Teams für Benutzer in Ihrer Organisation verwenden und verwalten.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: a23d9f5196f2d537e00c6e049377f9a7d7488654
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611599"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="d3c8c-103">Verwalten von Richtlinien für das App-Setup in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3c8c-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="d3c8c-104">Wenn Sie die organisationsweite app-Einstellung aktiviert haben, die **Interaktion mit benutzerdefinierten apps zulassen**, werden die APP-Setup Richtlinien möglicherweise noch nicht im Microsoft Teams Admin Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you may not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d3c8c-105">Sie wird zurzeit bereitgestellt und wird in Kürze in Ihrer Organisation zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="d3c8c-106">Als Administrator können Sie die APP-Setup Richtlinien verwenden, um die folgenden Aufgaben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d3c8c-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="d3c8c-107">Passen Sie Teams so an, dass jene Apps hervorgehoben werden, die für Ihre Benutzer am wichtigsten sind.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="d3c8c-108">Sie wählen die Apps aus, die Sie anheften möchten, und legen die Reihenfolge fest, in der Sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="d3c8c-109">Mit Anheften von Apps können Sie apps präsentieren, die von Benutzern in Ihrer Organisation benötigt werden, einschließlich von apps, die von Drittanbietern oder von Entwicklern in Ihrer Organisation erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="d3c8c-110">Legen Sie fest, ob Benutzer Apps in Microsoft Teams anheften können.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="d3c8c-111">Installieren von apps im Auftrag von Benutzern **(in der Vorschau)**</span><span class="sxs-lookup"><span data-stu-id="d3c8c-111">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="d3c8c-112">Sie wählen die Apps aus, die standardmäßig für Benutzer installiert werden, wenn Sie Teams starten.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="d3c8c-113">Beachten Sie, dass Benutzer weiterhin Apps selbst installieren können, wenn die Ihnen zugewiesene [App-Berechtigungsrichtlinie](teams-app-permission-policies.md) dies zulässt.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="d3c8c-114">Apps werden an die APP-Leiste angeheftet, die die Leiste auf der Seite des Teams-Desktop Clients und am unteren Rand des Teams Mobile Clients (IOS und Android) ist.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-114">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="d3c8c-115">Desktop Client für Teams</span><span class="sxs-lookup"><span data-stu-id="d3c8c-115">Teams desktop client</span></span>  |<span data-ttu-id="d3c8c-116">Mobiler Client für Teams</span><span class="sxs-lookup"><span data-stu-id="d3c8c-116">Teams mobile client</span></span> |
|---------|---------|
|![Der Desktop Client von Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![Der Mobile Client für Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="d3c8c-119">Um die vorinstallierten apps anzuzeigen, wählen Sie in der APP-Leiste Benutzer aus **... Weitere apps** in den Teams-Desktop-und-Webclients und wischen Sie in den mobilen Clients nach oben.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-119">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="d3c8c-120">Sie verwalten App-Setup Richtlinien im Microsoft Teams Admin Center.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-120">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d3c8c-121">Verwenden Sie die globale (organisationsweite Standardrichtlinie), oder erstellen Sie benutzerdefinierte Richtlinien, und weisen Sie diese zu.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-121">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="d3c8c-122">Sofern Sie keine benutzerdefinierte Richtlinie erstellen und zuweisen, wird Benutzern in Ihrer Organisation automatisch die globale Standardrichtlinie zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-122">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="d3c8c-123">Sie müssen ein globaler Administrator oder Teams-Dienstadministrator sein, um diese Richtlinien verwalten zu können.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-123">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="d3c8c-124">Sie bearbeiten die Einstellungen in der globalen Richtlinie, um die gewünschten apps einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-124">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="d3c8c-125">Um Teams für verschiedene Benutzergruppen in Ihrer Organisation anzupassen, erstellen Sie eine oder mehrere benutzerdefinierte Richtlinien, und weisen Sie diese zu.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-125">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![Seite "Richtlinien für die APP-Installation"](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="d3c8c-127">Wenn Sie über Teams für Bildung verfügen, ist es wichtig zu wissen, dass die Aufgaben-App standardmäßig in der globalen Richtlinie angeheftet ist, obwohl Sie in der globalen Richtlinie zurzeit nicht aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-127">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="d3c8c-128">Es handelt sich um die vierte app in der Liste der angehefteten apps auf Teams-Clients.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-128">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="d3c8c-129">Erstellen einer benutzerdefinierten App-Setup Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d3c8c-129">Create a custom app setup policy</span></span>

<span data-ttu-id="d3c8c-130">Sie können das Microsoft Teams Admin Center verwenden, um eine benutzerdefinierte Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-130">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="d3c8c-131">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den  >  **Setup Richtlinien** für Teams-apps.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-131">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="d3c8c-132">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-132">Select **Add**.</span></span>

   ![Seite "Richtlinien zum Hinzufügen von Apps"](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="d3c8c-134">Geben Sie eine Bezeichnung und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-134">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="d3c8c-135">Aktivieren oder deaktivieren Sie Benutzer **definierte apps hochladen**, je nachdem, ob Sie Benutzer benutzerdefinierte apps in Teams hochladen lassen möchten.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-135">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="d3c8c-136">Sie können diese Einstellung nicht ändern, wenn das **Zulassen von Drittanbieter-apps** in den [organisationsweiten App-Einstellungen](manage-apps.md#manage-org-wide-app-settings)deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-136">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="d3c8c-137">Aktivieren oder deaktivieren Sie das **Zulassen von Benutzer anheften**, je nachdem, ob Benutzer Ihre APP-Leiste personalisieren lassen möchten, indem Sie apps an Sie anheften.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-137">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d3c8c-138">Die Einstellung **Benutzer anheften zulassen** steht im Team Admin Center in Microsoft 365 Government Community Cloud (gcc)-Umgebungen (gcc, gcc-höchst-und DoD) zur Verfügung, hat aber derzeit keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-138">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="d3c8c-139">Führen Sie die folgenden Aufgaben aus, um Apps für Benutzer **(in der Vorschau)** zu installieren:</span><span class="sxs-lookup"><span data-stu-id="d3c8c-139">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="d3c8c-140">Wählen Sie unter **installierte apps** die Option **apps hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-140">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="d3c8c-141">Suchen Sie im Bereich **installierte apps hinzufügen** nach den apps, die Sie beim Starten von Teams automatisch für Benutzer installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-141">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="d3c8c-142">Sie können apps auch nach App-Berechtigungsrichtlinien filtern.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-142">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="d3c8c-143">Wenn Sie die Liste der apps ausgewählt haben, wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-143">When you've chosen your list of apps, select **Add**.</span></span>

       ![der Bereich "installierte apps hinzufügen"](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="d3c8c-145">Gehen Sie wie folgt vor, um apps zu anheften:</span><span class="sxs-lookup"><span data-stu-id="d3c8c-145">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="d3c8c-146">Wählen Sie unter **angeheftete apps** die Option **apps hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-146">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="d3c8c-147">Suchen Sie im Bereich **angeheftete apps hinzu** fügen nach den apps, die Sie hinzufügen möchten, und wählen Sie dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-147">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="d3c8c-148">Sie können apps auch nach App-Berechtigungsrichtlinien filtern.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-148">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="d3c8c-149">Wenn Sie die Liste der zu anheftenden apps ausgewählt haben, wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-149">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![der Bereich "angeheftete apps hinzufügen"](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="d3c8c-151">Ordnen Sie die apps in der Reihenfolge an, in der Sie in Teams angezeigt werden sollen, und wählen Sie dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-151">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![der Abschnitt angeheftete apps](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="d3c8c-153">Bearbeiten einer APP-Setup Richtlinie</span><span class="sxs-lookup"><span data-stu-id="d3c8c-153">Edit an app setup policy</span></span>

<span data-ttu-id="d3c8c-154">Sie können das Microsoft Teams Admin Center verwenden, um eine Richtlinie zu bearbeiten, einschließlich der Global (org-Wide Standard)-Richtlinie und der von Ihnen erstellten benutzerdefinierten Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="d3c8c-155">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu den  >  **Setup Richtlinien** für Teams-apps.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-155">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="d3c8c-156">Wählen Sie die Richtlinie aus, indem Sie links neben dem Richtliniennamen klicken, und wählen Sie dann **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-156">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="d3c8c-157">Nehmen Sie hier die gewünschten Änderungen vor.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-157">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="d3c8c-158">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-158">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="d3c8c-159">Zuweisen einer benutzerdefinierten App-Setup Richtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="d3c8c-159">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="d3c8c-160">Häufig gestellte Fragen</span><span class="sxs-lookup"><span data-stu-id="d3c8c-160">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="d3c8c-161">Arbeiten mit App-Setup Richtlinien</span><span class="sxs-lookup"><span data-stu-id="d3c8c-161">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="d3c8c-162">Welche integrierten App-Setup Richtlinien sind im Microsoft Teams Admin Center enthalten</span><span class="sxs-lookup"><span data-stu-id="d3c8c-162">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="d3c8c-163">**Global (org-Wide Standard)**: Diese Standardrichtlinie gilt für alle Benutzer in Ihrer Organisation, es sei denn, Sie weisen eine andere Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-163">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="d3c8c-164">Bearbeiten Sie die globale Richtlinie, um apps zu anheften, die für Ihre Benutzer am wichtigsten sind.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-164">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="d3c8c-165">**FirstLineWorker**: Diese Richtlinie gilt für First-work-Mitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-165">**FirstLineWorker**: This policy is for Firstline Workers.</span></span> <span data-ttu-id="d3c8c-166">Sie können es den Mitarbeitern in Ihrer Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-166">You can assign it to Firstline Workers in your organization.</span></span> <span data-ttu-id="d3c8c-167">Es ist wichtig zu wissen, dass Sie wie von Ihnen erstellte benutzerdefinierte Richtlinien die Richtlinie Benutzern zuweisen müssen, damit die Einstellungen aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-167">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="d3c8c-168">Weitere Informationen finden Sie im Abschnitt [Zuweisen einer benutzerdefinierten App-Setup Richtlinie zu Benutzern](#assign-a-custom-app-setup-policy-to-users) dieses Artikels.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-168">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="d3c8c-169">Warum kann ich keine app im Bereich "angeheftete apps hinzufügen" finden?</span><span class="sxs-lookup"><span data-stu-id="d3c8c-169">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="d3c8c-170">Nicht alle apps können über eine APP-Setup Richtlinie an Teams angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-170">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="d3c8c-171">Einige apps unterstützen diese Funktion möglicherweise nicht.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-171">Some apps may not support this functionality.</span></span> <span data-ttu-id="d3c8c-172">Um apps zu finden, die angeheftet werden können, suchen Sie im Bereich **angeheftete apps hinzufügen** nach der app.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-172">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="d3c8c-173">Registerkarten mit einem persönlichen Bereich (statische Registerkarten) und Bots können an den Desktop Client von Teams angeheftet werden, und diese apps sind im Bereich **angeheftete apps hinzufügen** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-173">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="d3c8c-174">Beachten Sie, dass im App Store für Teams alle Teams-apps aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-174">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="d3c8c-175">Der Bereich **angeheftete apps hinzufügen** enthält nur apps, die über eine Richtlinie an Teams angeheftet werden können.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-175">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="d3c8c-176">Ich bin ein Team für Bildungs Administrator. Was muss ich über die Richtlinien für die APP-Einrichtung in Teams für Bildung wissen?</span><span class="sxs-lookup"><span data-stu-id="d3c8c-176">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="d3c8c-177">Die Anruf-App steht in Teams für Education nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-177">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="d3c8c-178">Wenn Sie eine neue benutzerdefinierte App-Setup Richtlinie erstellen, wird die aufrufende app in der Liste der apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-178">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="d3c8c-179">Die APP wird jedoch nicht an Teams-Clients und Teams für Education angeheftet. Benutzer sehen die Anruf-APP nicht in Teams.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-179">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="d3c8c-180">Wie viele angeheftete apps einer Richtlinie hinzugefügt werden können</span><span class="sxs-lookup"><span data-stu-id="d3c8c-180">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="d3c8c-181">Mindestens zwei apps müssen an die mobilen Teams (IOS und Android) angeheftet sein.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-181">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="d3c8c-182">Wenn eine Richtlinie weniger als zwei apps aufweist, geben die mobilen Clients die Richtlinieneinstellungen nicht wieder und verwenden stattdessen weiterhin die vorhandene Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-182">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="d3c8c-183">Die Anzahl der angehefteten apps, die Sie einer Richtlinie hinzufügen können, ist unbegrenzt.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-183">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="d3c8c-184">Wie lange dauert es, bis Richtlinienänderungen wirksam werden?</span><span class="sxs-lookup"><span data-stu-id="d3c8c-184">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="d3c8c-185">Nachdem Sie eine Richtlinie bearbeitet oder zugewiesen haben, kann es einige Stunden dauern, bis die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-185">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="d3c8c-186">Benutzererfahrung</span><span class="sxs-lookup"><span data-stu-id="d3c8c-186">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="d3c8c-187">Wie können Benutzer alle Ihre angehefteten apps in Microsoft Teams anzeigen?</span><span class="sxs-lookup"><span data-stu-id="d3c8c-187">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="d3c8c-188">Um alle apps anzuzeigen, die für einen Benutzer angeheftet sind, müssen die Benutzer möglicherweise die folgenden Schritte ausführen, abhängig von der Anzahl der installierten apps und der Größe des Teams-Clientfensters.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-188">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="d3c8c-189">Desktop Client für Teams</span><span class="sxs-lookup"><span data-stu-id="d3c8c-189">Teams desktop client</span></span> |<span data-ttu-id="d3c8c-190">Mobiler Client für Teams</span><span class="sxs-lookup"><span data-stu-id="d3c8c-190">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="d3c8c-191">Wählen Sie in der APP-Leiste auf der Seite von Teams die Option **... Weitere apps**.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-191">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="d3c8c-192">Wischen Sie in der APP-Leiste am unteren Rand von Teams nach oben.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-192">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Weitere apps im Desktop Client von Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![Weitere apps im mobilen Microsoft Teams-Client](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="d3c8c-195">Was muss ich über die Mobile Teams-Umgebung wissen?</span><span class="sxs-lookup"><span data-stu-id="d3c8c-195">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="d3c8c-196">Die Mobile-Clients von Teams (IOS und Android) unterstützen derzeit keine persönlichen apps mit statischen Registerkarten.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-196">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="d3c8c-197">Je nach den in der Richtlinie festgelegten apps werden apps, die an den Desktop Client von Teams angeheftet wurden, möglicherweise nicht in den mobilen Teams angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-197">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="d3c8c-198">Persönliche Bots werden weiterhin im Chat auf mobilen Clients angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-198">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="d3c8c-199">Mit den mobilen Teams von Teams werden Benutzern Kern Teams-apps wie Aktivitäten, Chats und Teams angezeigt, und Sie können einige Erstanbieter-apps von Microsoft anheften, beispielsweise Schichten.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-199">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="d3c8c-200">Können Benutzer die Reihenfolge der apps ändern, die über eine Richtlinie angeheftet sind</span><span class="sxs-lookup"><span data-stu-id="d3c8c-200">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="d3c8c-201">Benutzer können die Reihenfolge ihrer angehefteten apps auf den Desktop-und mobilen Clients von Teams ändern, wenn die Option **Benutzer anheften zulassen** aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-201">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="d3c8c-202">Benutzer können die Reihenfolge ihrer angehefteten apps auf den Microsoft Teams-Webclients nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-202">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="d3c8c-203">Hat das Anheften von Benutzern Vorrang</span><span class="sxs-lookup"><span data-stu-id="d3c8c-203">Does user pinning take precedence</span></span>

<span data-ttu-id="d3c8c-204">Wenn die dem Benutzer zugewiesene App-Setup Richtlinie geändert wird, um das Anheften der Benutzer-APP zu blockieren, entfernt Teams alle apps, die an die APP-Leiste angeheftet sind.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-204">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="d3c8c-205">Wenn die Richtlinie dann geändert wird, um Benutzer-App-anheften zuzulassen, müssen Benutzer ihre zuvor angehefteten apps erneut anheften.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-205">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="d3c8c-206">Benutzerdefinierte Teams-apps</span><span class="sxs-lookup"><span data-stu-id="d3c8c-206">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="d3c8c-207">Meine Organisation hat eine benutzerdefinierte Teams-App erstellt und Sie entweder in AppSource oder im Mandanten-App-Katalog veröffentlicht, doch das App-Symbol wird nicht wie erwartet angezeigt, wenn die app in Teams an die APP-Leiste angeheftet wird.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-207">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="d3c8c-208">Wie behebe ich es</span><span class="sxs-lookup"><span data-stu-id="d3c8c-208">How do I fix it</span></span>

<span data-ttu-id="d3c8c-209">Achten Sie darauf, dass Sie die Richtlinien für das Logo befolgen, bevor Sie die APP übermitteln.</span><span class="sxs-lookup"><span data-stu-id="d3c8c-209">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="d3c8c-210">Weitere Informationen finden Sie unter [Checkliste für die Übermittlung von Verkäufer Dashboards](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span><span class="sxs-lookup"><span data-stu-id="d3c8c-210">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="d3c8c-211">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d3c8c-211">Related topics</span></span>

[<span data-ttu-id="d3c8c-212">Administratoreinstellungen für Apps in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3c8c-212">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="d3c8c-213">Zuweisen von Richtlinien zu Ihren Benutzern in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d3c8c-213">Assign policies to your users in Teams</span></span>](assign-policies.md)
