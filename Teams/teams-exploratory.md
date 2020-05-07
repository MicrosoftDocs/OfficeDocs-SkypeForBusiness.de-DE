---
title: Verwalten der explorativen Microsoft Teams-Umgebung
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Microsoft 365- oder Office 365-Benutzer, die nicht für Microsoft Teams lizenziert sind, können eine explorative Lizenz von Microsoft Teams starten.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6c40e9f89d56329dc8f4f450b72a76c031315b9a
ms.sourcegitcommit: 09ff11f8e4f6a93cedc34a5d732a133163df79a0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44041752"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="36de8-103">Verwalten der explorativen Lizenz von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36de8-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="36de8-104">Die explorative Microsoft Teams-Umgebung ermöglicht Benutzern in Ihrer Organisation, die über Azure Active Directory (AAD) verfügen und nicht für Teams lizenziert sind, eine explorative Umgebung von Microsoft Teams zu starten.</span><span class="sxs-lookup"><span data-stu-id="36de8-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (AAD) and are not licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="36de8-105">Administratoren können dieses Feature für Benutzer in ihrer Organisation aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="36de8-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="36de8-106">Die frühere [Microsoft Commercial Cloud-Testversion](iw-trial-teams.md) wurde durch die explorative Microsoft Teams-Umgebung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="36de8-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="36de8-107">Was ist in der explorativen Microsoft Teams-Umgebung enthalten?</span><span class="sxs-lookup"><span data-stu-id="36de8-107">What's in the Teams Exploratory experience?</span></span>

<span data-ttu-id="36de8-108">Folgende Dienstpläne werden einem Administrator als Teil der Microsoft Teams Exploratory-Umgebung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="36de8-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>
 - <span data-ttu-id="36de8-109">Exchange Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="36de8-109">Exchange Online (Plan 1)</span></span>
 - <span data-ttu-id="36de8-110">Microsoft Flow für Office 365</span><span class="sxs-lookup"><span data-stu-id="36de8-110">Flow for Office 365</span></span>
 - <span data-ttu-id="36de8-111">MyAnalytics Insights</span><span class="sxs-lookup"><span data-stu-id="36de8-111">Insights by MyAnalytics</span></span>
 - <span data-ttu-id="36de8-112">Microsoft Forms (Plan E1)</span><span class="sxs-lookup"><span data-stu-id="36de8-112">Microsoft Forms (Plan E1)</span></span>
 - <span data-ttu-id="36de8-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="36de8-113">Microsoft Planner</span></span>
 - <span data-ttu-id="36de8-114">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="36de8-114">Microsoft Search</span></span>
 - <span data-ttu-id="36de8-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="36de8-115">Microsoft StaffHub</span></span>
 - <span data-ttu-id="36de8-116">Microsoft Stream für Office 365 E1 SKU</span><span class="sxs-lookup"><span data-stu-id="36de8-116">Microsoft Stream for O365 E1 SKU</span></span>
 - <span data-ttu-id="36de8-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="36de8-117">Microsoft Teams</span></span>
 - <span data-ttu-id="36de8-118">Verwaltung mobiler Geräte für Office 365</span><span class="sxs-lookup"><span data-stu-id="36de8-118">Mobile Device Management for Office 365</span></span>
 - <span data-ttu-id="36de8-119">Office Mobile-Apps für Office 365</span><span class="sxs-lookup"><span data-stu-id="36de8-119">Office Mobile Apps for Office 365</span></span> 
 - <span data-ttu-id="36de8-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="36de8-120">Office Online</span></span>
 - <span data-ttu-id="36de8-121">PowerApps für Office 365</span><span class="sxs-lookup"><span data-stu-id="36de8-121">PowerApps for Office 365</span></span>
 - <span data-ttu-id="36de8-122">SharePoint Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="36de8-122">SharePoint Online (Plan 1)</span></span>
 - <span data-ttu-id="36de8-123">Sway</span><span class="sxs-lookup"><span data-stu-id="36de8-123">Sway</span></span>
 - <span data-ttu-id="36de8-124">To-Do (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="36de8-124">To-Do (Plan 1)</span></span>
 - <span data-ttu-id="36de8-125">Whiteboard (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="36de8-125">Whiteboard (Plan 1)</span></span>
 - <span data-ttu-id="36de8-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="36de8-126">Yammer Enterprise</span></span>


## <a name="whos-eligible"></a><span data-ttu-id="36de8-127">Wer ist berechtigt?</span><span class="sxs-lookup"><span data-stu-id="36de8-127">Who's eligible?</span></span>

<span data-ttu-id="36de8-128">Solange ein Benutzer über eine verwaltete AAD-Domänen-E-Mail-Adresse verfügt und ihm aktuell keine Teams-Lizenz zugewiesen wurde, ist er zur Nutzung dieser Umgebung berechtigt.</span><span class="sxs-lookup"><span data-stu-id="36de8-128">As long as the user has a managed AAD domain email address and currently does not have/haven't been assigned a Teams license, they are eligible for this experience.</span></span> <span data-ttu-id="36de8-129">Wenn ein Benutzer beispielsweise Microsoft 365 Apps for Business verwendet (das Microsoft Teams nicht beinhaltet), ist er berechtigt, die explorative Microsoft Teams-Umgebung in Anspruch zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="36de8-129">For example, if a user has Microsoft 365 Apps for business (which doesn't include Teams), they're eligible for the Teams Exploratory experience.</span></span>

<span data-ttu-id="36de8-130">Benutzern muss (im Microsoft 365 Admin Center) die Möglichkeit bereitgestellt werden, sich für Apps und Testversionen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="36de8-130">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="36de8-131">Weitere Informationen finden Sie weiter unten in diesem Artikel unter [Verwalten der explorativen Microsoft Teams-Umgebung](#manage-the-teams-exploratory-experience).</span><span class="sxs-lookup"><span data-stu-id="36de8-131">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span> 


## <a name="who-isnt-eligible"></a><span data-ttu-id="36de8-132">Wer ist nicht berechtigt?</span><span class="sxs-lookup"><span data-stu-id="36de8-132">Who isn't eligible</span></span>

<span data-ttu-id="36de8-133">Ihre Organisation ist nicht für dieses Angebot berechtigt, wenn Sie ein Syndication-Partnerkunde oder ein GCC-, GCC High-, DoD- oder EDU-Kunde sind.</span><span class="sxs-lookup"><span data-stu-id="36de8-133">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="36de8-134">So können Benutzer sich für die explorative Microsoft Teams-Umgebung registrieren</span><span class="sxs-lookup"><span data-stu-id="36de8-134">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="36de8-135">Berechtigte Benutzer können sich für die explorative Microsoft Teams-Umgebung registrieren, indem sie sich bei Microsoft Teams ([teams.microsoft.com](https://teams.microsoft.com)) anmelden.</span><span class="sxs-lookup"><span data-stu-id="36de8-135">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="36de8-136">Daraufhin wird ihnen automatisch diese Lizenz zugewiesen. Der Mandantenadministrator erhält eine E-Mail-Benachrichtigung, wenn eine Person in seiner Organisation die explorative Microsoft Teams-Umgebung zum ersten Mal startet.</span><span class="sxs-lookup"><span data-stu-id="36de8-136">They will be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="36de8-137">Verwalten der explorativen Microsoft Teams-Umgebung</span><span class="sxs-lookup"><span data-stu-id="36de8-137">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="36de8-138">Die explorative Microsoft Teams-Umgebung ist für die Initialisierung durch einzelne Endbenutzer bestimmt, und Sie sind nicht berechtigt, dieses Angebot im Namen von Endbenutzern oder Angestellten zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="36de8-138">The Teams Exploratory experience is meant to be initiated by individual end users, and you may not initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="36de8-139">Die explorative Microsoft Teams-Umgebung wird mit einer Exchange Online-Lizenz geliefert, die dem Benutzer jedoch erst vom Administrator zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="36de8-139">The Teams Exploratory experience comes with an Exchange Online license but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="36de8-140">Verfügt der Benutzer noch über keine Exchange-Lizenz, kann er keine Besprechungen in Teams planen und andere Teams-Funktionen möglicherweise nicht verwenden, solange der Administrator die Exchange Online-Lizenz noch nicht zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="36de8-140">If the user doesn't have an Exchange license already and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and may be missing other Teams functionality.</span></span>

<span data-ttu-id="36de8-141">Administratoren können die Option zur Ausführung der explorativen Microsoft Teams-Umgebung für Benutzer in ihrer Organisation über den Switch **Test-Apps und -Dienste** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="36de8-141">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>


### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="36de8-142">Verhindern, dass Benutzer Test-Apps und -dienste installieren</span><span class="sxs-lookup"><span data-stu-id="36de8-142">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="36de8-143">Sie können die Möglichkeit des Benutzers deaktivieren, Test-Apps und -Dienste zu installieren, wodurch Sie Benutzer daran hindern, die explorative Microsoft Teams-Umgebung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="36de8-143">You can turn off a user's ability to install trial apps and services, would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="36de8-144">Navigieren Sie im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) zu **Einstellungen** > **Einstellungen**, wählen Sie **Dienste** und dann **Apps und Dienste im Besitz des Benutzers** aus.</span><span class="sxs-lookup"><span data-stu-id="36de8-144">From the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), go to **Settings** > **Settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![Screenshot der Seite "Dienste" im Admin Center](media/iw-trial-services.png)

2. <span data-ttu-id="36de8-146">Deaktivieren Sie das Kontrollkästchen **Benutzer Test-Apps und -dienste installieren lassen**.</span><span class="sxs-lookup"><span data-stu-id="36de8-146">Clear the **Let users install trial apps and services** check box.</span></span>

    ![Screenshot der Seite "Apps und Dienste im Besitz des Benutzers" im Admin Center.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="36de8-148">Wenn Ihre Organisation nicht berechtigt ist, die explorative Microsoft Teams-Umgebung in Anspruch zu nehmen, wird die Option **Benutzer Test-Apps und -dienste installieren lassen** nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="36de8-148">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="36de8-149">Verwalten der Verfügbarkeit für einen Benutzer mit einer Lizenz, die Microsoft Teams umfasst</span><span class="sxs-lookup"><span data-stu-id="36de8-149">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="36de8-150">Ein Benutzer, dem eine Lizenz zugewiesen wurde, die Microsoft Teams bereits umfasst, ist nicht berechtigt, die explorative Microsoft Teams-Umgebung in Anspruch zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="36de8-150">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="36de8-151">Wenn der Microsoft Teams-Serviceplan aktiviert ist, kann sich der Benutzer anmelden und Microsoft Teams verwenden.</span><span class="sxs-lookup"><span data-stu-id="36de8-151">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="36de8-152">Wenn der Dienstplan deaktiviert ist, kann sich der Benutzer nicht anmelden, und die explorative Microsoft Teams-Umgebung ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="36de8-152">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span>

<span data-ttu-id="36de8-153">So deaktivieren Sie den Zugriff auf Teams:</span><span class="sxs-lookup"><span data-stu-id="36de8-153">To turn off access to Teams:</span></span>

1. <span data-ttu-id="36de8-154">Wählen Sie im Microsoft 365 Admin Center, **Benutzer** > **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="36de8-154">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="36de8-155">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="36de8-155">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="36de8-156">Wählen Sie rechts in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="36de8-156">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="36de8-157">Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="36de8-157">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![Screenshot der Seite „Produktlizenzen“ im Admin Center.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="36de8-159">Verwalten der Verfügbarkeit von Microsoft Teams für Benutzer, die bereits die explorative Microsoft Teams-Umgebung verwenden</span><span class="sxs-lookup"><span data-stu-id="36de8-159">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="36de8-160">Wenn ein Benutzer die explorative Microsoft Teams-Umgebung ausführt, können Sie diese deaktivieren, indem Sie die Lizenz oder den Dienstplan entfernen.</span><span class="sxs-lookup"><span data-stu-id="36de8-160">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span>

<span data-ttu-id="36de8-161">So deaktivieren Sie die Lizenz für die explorative Microsoft Teams-Umgebung:</span><span class="sxs-lookup"><span data-stu-id="36de8-161">To turn off the the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="36de8-162">Wählen Sie im Microsoft 365 Admin Center, **Benutzer** > **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="36de8-162">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="36de8-163">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="36de8-163">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="36de8-164">Wählen Sie rechts in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="36de8-164">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="36de8-165">Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche für die explorative Lizenz auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="36de8-165">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>
   
    >[!Note]
    ><span data-ttu-id="36de8-166">Die Umschaltfläche für die explorative Microsoft Teams-Umgebung wird angezeigt, sobald der erste Benutzer in der Organisation die explorative Microsoft Teams-Umgebung startet.</span><span class="sxs-lookup"><span data-stu-id="36de8-166">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="36de8-167">Verwalten von Microsoft Teams für Benutzer, die über die explorative Microsoft Teams-Lizenz verfügen</span><span class="sxs-lookup"><span data-stu-id="36de8-167">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="36de8-168">Sie können Benutzer mit einer explorativen Microsoft Teams-Lizenz genauso verwalten wie Benutzer mit einer regulären kostenpflichtigen Lizenz.</span><span class="sxs-lookup"><span data-stu-id="36de8-168">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="36de8-169">Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="36de8-169">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="36de8-170">Upgraden von Benutzern mit der explorativen Microsoft Teams-Lizenz</span><span class="sxs-lookup"><span data-stu-id="36de8-170">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="36de8-171">Um Benutzer mit der explorative Microsoft Teams-Lizenz zu upgraden, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="36de8-171">To upgrade users from the Teams Exploratory license, do the following:</span></span>

1. <span data-ttu-id="36de8-172">Kaufen Sie ein Abonnement, das Microsoft Teams enthält.</span><span class="sxs-lookup"><span data-stu-id="36de8-172">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="36de8-173">Entfernen Sie das Abonnement der explorativen Microsoft Teams-Umgebung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="36de8-173">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="36de8-174">Weisen Sie die neu erworbene Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="36de8-174">Assign the newly purchased license.</span></span>

<span data-ttu-id="36de8-175">Weitere Informationen finden Sie unter [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="36de8-175">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="36de8-176">Wenn die Microsoft Teams Exploratory-Lizenz abläuft und kein unmittelbares Upgrade auf ein Abonnement, das Microsoft Teams umfasst, für einen Benutzer erfolgt, werden die Benutzerdaten nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="36de8-176">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, the user data is not removed.</span></span> <span data-ttu-id="36de8-177">Der Benutzer bleibt weiterhin in Azure Active Directory und alle Daten innerhalb von Teams werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="36de8-177">The user still exists in Azure Active Directory and all data within Teams still remains.</span></span> <span data-ttu-id="36de8-178">Sobald dem Benutzer eine neue Lizenz zugewiesen ist, die Teams-Funktionen aktiviert, sind die Inhalte weiterhin vorhanden.</span><span class="sxs-lookup"><span data-stu-id="36de8-178">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.</span></span> 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="36de8-179">Was geschieht mit den Legacylizenzen für den Test der kommerziellen Cloud von Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="36de8-179">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses?</span></span>

<span data-ttu-id="36de8-180">Ab Februar 2020 können berechtigte Benutzer mit der Nutzung der neuesten Microsoft Teams Exploratory-Umgebung beginnen.</span><span class="sxs-lookup"><span data-stu-id="36de8-180">As of February, 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="36de8-181">Alle Legacylizenzen für den Test der kommerziellen Cloud von Microsoft Teams werden automatisch in das neue Angebot konvertiert, bevor die Testversion abläuft.</span><span class="sxs-lookup"><span data-stu-id="36de8-181">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="36de8-182">Entfernen einer explorativen Microsoft Teams-Lizenz</span><span class="sxs-lookup"><span data-stu-id="36de8-182">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="36de8-183">Wenn Sie diese Lizenz über PowerShell entfernen möchten, ziehen Sie [Entfernen von Lizenzen von Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell) zurate.</span><span class="sxs-lookup"><span data-stu-id="36de8-183">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="36de8-184">Wenn Sie diese Lizenz über das Verwaltungsportal entfernen möchten, lesen Sie [Entfernen von Lizenzen von Benutzern in Office 365 Business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="36de8-184">If you would like to remove this license through the admin portal, see: [Remove licenses from users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/remove-licenses-from-users?view=o365-worldwide)</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="36de8-185">Wie lange wird die Teams Exploratory-Umgebung verfügbar sein?</span><span class="sxs-lookup"><span data-stu-id="36de8-185">How long does the Teams Exploratory experience last?</span></span>

<span data-ttu-id="36de8-186">Die Microsoft Teams Exploratory-Umgebung wird ohne zusätzliche Kosten bis zum nächsten **Fälligkeitstag Ihres Vertrags** oder nach **Verlängerung** am oder ab Januar 2021 verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="36de8-186">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="36de8-187">Zu diesem Zeitpunkt müssen Endbenutzer mit einer Microsoft Exploratory-Lizenz zu einer kostenpflichtigen Lizenz wechseln, die Microsoft Teams umfasst.</span><span class="sxs-lookup"><span data-stu-id="36de8-187">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="36de8-188">Alle Microsoft Exploratory-Lizenzen, die danach begonnen wurden, werden bis zu Ihrem nächsten **Fälligkeitstag** oder der nächsten **Verlängerung** ohne zusätzliche Kosten verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="36de8-188">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span> 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a><span data-ttu-id="36de8-189">Was geschieht, wenn ein Endbenutzer kurz vor dem Fälligkeits- oder Verlängerungsdatum mit der Nutzung der Microsoft Teams Exploratory-Umgebung beginnt?</span><span class="sxs-lookup"><span data-stu-id="36de8-189">What happens if an end user initiates the Microsoft Teams Exploratory experience just before my anniversary or renewal date?</span></span>

<span data-ttu-id="36de8-190">Microsoft Teams Exploratory-Lizenzen, die innerhalb von 90 Tagen nach dem **Fälligkeitstag** oder der **Verlängerung des Vertrags** begonnen wurden, sind bis zum anschließenden Fälligkeitstag oder Verlängerungszyklus nicht verpflichtet, zu einer kostenpflichtigen Lizenz zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="36de8-190">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** will not be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span> 
