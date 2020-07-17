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
ms.openlocfilehash: 99017e63ae784c7c4271454829198c7c06ecfe8e
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868462"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="46417-103">Verwalten der explorativen Lizenz von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46417-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="46417-104">Die explorative Microsoft Teams-Umgebung ermöglicht Benutzern in Ihrer Organisation, die über Azure Active Directory (AAD) verfügen und nicht für Teams lizenziert sind, eine explorative Umgebung von Microsoft Teams zu starten.</span><span class="sxs-lookup"><span data-stu-id="46417-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (AAD) and are not licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="46417-105">Administratoren können dieses Feature für Benutzer in ihrer Organisation aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="46417-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="46417-106">Die frühere [Microsoft Commercial Cloud-Testversion](iw-trial-teams.md) wurde durch die explorative Microsoft Teams-Umgebung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="46417-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="46417-107">Was ist in der explorativen Microsoft Teams-Umgebung enthalten?</span><span class="sxs-lookup"><span data-stu-id="46417-107">What's in the Teams Exploratory experience?</span></span>

<span data-ttu-id="46417-108">Folgende Dienstpläne werden einem Administrator als Teil der Microsoft Teams Exploratory-Umgebung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="46417-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>
 - <span data-ttu-id="46417-109">Exchange Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="46417-109">Exchange Online (Plan 1)</span></span>
 - <span data-ttu-id="46417-110">Flow für Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="46417-110">Flow for Microsoft 365 or Office 365</span></span>
 - <span data-ttu-id="46417-111">MyAnalytics Insights</span><span class="sxs-lookup"><span data-stu-id="46417-111">Insights by MyAnalytics</span></span>
 - <span data-ttu-id="46417-112">Microsoft Forms (Plan E1)</span><span class="sxs-lookup"><span data-stu-id="46417-112">Microsoft Forms (Plan E1)</span></span>
 - <span data-ttu-id="46417-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="46417-113">Microsoft Planner</span></span>
 - <span data-ttu-id="46417-114">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="46417-114">Microsoft Search</span></span>
 - <span data-ttu-id="46417-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="46417-115">Microsoft StaffHub</span></span>
 - <span data-ttu-id="46417-116">Microsoft Stream für Microsoft 365 und Office 365 E1-SKUs</span><span class="sxs-lookup"><span data-stu-id="46417-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs</span></span>
 - <span data-ttu-id="46417-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="46417-117">Microsoft Teams</span></span>
 - <span data-ttu-id="46417-118">Verwaltung mobiler Geräte für Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="46417-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
 - <span data-ttu-id="46417-119">Office Mobile-Apps für Office 365</span><span class="sxs-lookup"><span data-stu-id="46417-119">Office Mobile Apps for Office 365</span></span> 
 - <span data-ttu-id="46417-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="46417-120">Office Online</span></span>
 - <span data-ttu-id="46417-121">PowerApps für Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="46417-121">PowerApps for Microsoft 365 or Office 365</span></span>
 - <span data-ttu-id="46417-122">SharePoint Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="46417-122">SharePoint Online (Plan 1)</span></span>
 - <span data-ttu-id="46417-123">Sway</span><span class="sxs-lookup"><span data-stu-id="46417-123">Sway</span></span>
 - <span data-ttu-id="46417-124">To-Do (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="46417-124">To-Do (Plan 1)</span></span>
 - <span data-ttu-id="46417-125">Whiteboard (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="46417-125">Whiteboard (Plan 1)</span></span>
 - <span data-ttu-id="46417-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="46417-126">Yammer Enterprise</span></span>


## <a name="whos-eligible"></a><span data-ttu-id="46417-127">Wer ist berechtigt?</span><span class="sxs-lookup"><span data-stu-id="46417-127">Who's eligible?</span></span>

<span data-ttu-id="46417-128">Solange ein Benutzer über eine verwaltete AAD-Domänen-E-Mail-Adresse verfügt und ihm aktuell keine Teams-Lizenz zugewiesen wurde, ist er zur Nutzung dieser Umgebung berechtigt.</span><span class="sxs-lookup"><span data-stu-id="46417-128">As long as the user has a managed AAD domain email address and currently does not have/haven't been assigned a Teams license, they are eligible for this experience.</span></span> <span data-ttu-id="46417-129">Wenn ein Benutzer beispielsweise Microsoft 365 Apps for Business verwendet (das Microsoft Teams nicht beinhaltet), ist er berechtigt, die explorative Microsoft Teams-Umgebung in Anspruch zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="46417-129">For example, if a user has Microsoft 365 Apps for business (which doesn't include Teams), they're eligible for the Teams Exploratory experience.</span></span>

<span data-ttu-id="46417-130">Benutzern muss (im Microsoft 365 Admin Center) die Möglichkeit bereitgestellt werden, sich für Apps und Testversionen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="46417-130">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="46417-131">Weitere Informationen finden Sie weiter unten in diesem Artikel unter [Verwalten der explorativen Microsoft Teams-Umgebung](#manage-the-teams-exploratory-experience).</span><span class="sxs-lookup"><span data-stu-id="46417-131">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span> 


## <a name="who-isnt-eligible"></a><span data-ttu-id="46417-132">Wer ist nicht berechtigt?</span><span class="sxs-lookup"><span data-stu-id="46417-132">Who isn't eligible</span></span>

<span data-ttu-id="46417-133">Ihre Organisation ist nicht für dieses Angebot berechtigt, wenn Sie ein Syndication-Partnerkunde oder ein GCC-, GCC High-, DoD- oder EDU-Kunde sind.</span><span class="sxs-lookup"><span data-stu-id="46417-133">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>


## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="46417-134">So können Benutzer sich für die explorative Microsoft Teams-Umgebung registrieren</span><span class="sxs-lookup"><span data-stu-id="46417-134">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="46417-135">Berechtigte Benutzer können sich für die explorative Microsoft Teams-Umgebung registrieren, indem sie sich bei Microsoft Teams ([teams.microsoft.com](https://teams.microsoft.com)) anmelden.</span><span class="sxs-lookup"><span data-stu-id="46417-135">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="46417-136">Daraufhin wird ihnen automatisch diese Lizenz zugewiesen. Der Mandantenadministrator erhält eine E-Mail-Benachrichtigung, wenn eine Person in seiner Organisation die explorative Microsoft Teams-Umgebung zum ersten Mal startet.</span><span class="sxs-lookup"><span data-stu-id="46417-136">They will be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="46417-137">Verwalten der explorativen Microsoft Teams-Umgebung</span><span class="sxs-lookup"><span data-stu-id="46417-137">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="46417-138">Die explorative Microsoft Teams-Umgebung ist für die Initialisierung durch einzelne Endbenutzer bestimmt, und Sie sind nicht berechtigt, dieses Angebot im Namen von Endbenutzern oder Angestellten zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="46417-138">The Teams Exploratory experience is meant to be initiated by individual end users, and you may not initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="46417-139">Die explorative Microsoft Teams-Umgebung wird mit einer Exchange Online-Lizenz geliefert, die dem Benutzer jedoch erst vom Administrator zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="46417-139">The Teams Exploratory experience comes with an Exchange Online license but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="46417-140">Verfügt der Benutzer noch über keine Exchange-Lizenz, kann er keine Besprechungen in Teams planen und andere Teams-Funktionen möglicherweise nicht verwenden, solange der Administrator die Exchange Online-Lizenz noch nicht zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="46417-140">If the user doesn't have an Exchange license already and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and may be missing other Teams functionality.</span></span>

<span data-ttu-id="46417-141">Administratoren können die Option zur Ausführung der explorativen Microsoft Teams-Umgebung für Benutzer in ihrer Organisation über den Switch **Test-Apps und -Dienste** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="46417-141">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>


### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="46417-142">Verhindern, dass Benutzer Test-Apps und -dienste installieren</span><span class="sxs-lookup"><span data-stu-id="46417-142">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="46417-143">Sie können die Möglichkeit des Benutzers deaktivieren, Test-Apps und -Dienste zu installieren, wodurch Sie Benutzer daran hindern, die explorative Microsoft Teams-Umgebung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="46417-143">You can turn off a user's ability to install trial apps and services, would prevent the user from running the Teams Exploratory experience.</span></span> <span data-ttu-id="46417-144">Sie benötigen Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="46417-144">You must have admin privileges.</span></span> <span data-ttu-id="46417-145">Weitere Informationen zu Administratorrollen finden Sie unter [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](teams-exploratory.md).</span><span class="sxs-lookup"><span data-stu-id="46417-145">To learn more about admin roles, see [Use Microsoft Teams administrator roles to manage Teams](teams-exploratory.md)</span></span>

1. <span data-ttu-id="46417-146">Navigieren Sie im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) zu **Einstellungen** > **Einstellungen**, wählen Sie **Dienste** und dann **Apps und Dienste im Besitz des Benutzers** aus.</span><span class="sxs-lookup"><span data-stu-id="46417-146">From the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), go to **Settings** > **Settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![Screenshot der Seite "Dienste" im Admin Center](media/iw-trial-services.png)

2. <span data-ttu-id="46417-148">Deaktivieren Sie das Kontrollkästchen **Benutzer Test-Apps und -dienste installieren lassen**.</span><span class="sxs-lookup"><span data-stu-id="46417-148">Clear the **Let users install trial apps and services** check box.</span></span>

    ![Screenshot der Seite "Apps und Dienste im Besitz des Benutzers" im Admin Center.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="46417-150">Wenn Ihre Organisation nicht berechtigt ist, die explorative Microsoft Teams-Umgebung in Anspruch zu nehmen, wird die Option **Benutzer Test-Apps und -dienste installieren lassen** nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46417-150">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="46417-151">Verwalten der Verfügbarkeit für einen Benutzer mit einer Lizenz, die Microsoft Teams umfasst</span><span class="sxs-lookup"><span data-stu-id="46417-151">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="46417-152">Ein Benutzer, dem eine Lizenz zugewiesen wurde, die Microsoft Teams bereits umfasst, ist nicht berechtigt, die explorative Microsoft Teams-Umgebung in Anspruch zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="46417-152">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="46417-153">Wenn der Microsoft Teams-Serviceplan aktiviert ist, kann sich der Benutzer anmelden und Microsoft Teams verwenden.</span><span class="sxs-lookup"><span data-stu-id="46417-153">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="46417-154">Wenn der Dienstplan deaktiviert ist, kann sich der Benutzer nicht anmelden, und die explorative Microsoft Teams-Umgebung ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="46417-154">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="46417-155">Sie benötigen Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="46417-155">You must have admin privileges.</span></span> 

<span data-ttu-id="46417-156">So deaktivieren Sie den Zugriff auf Teams:</span><span class="sxs-lookup"><span data-stu-id="46417-156">To turn off access to Teams:</span></span>

1. <span data-ttu-id="46417-157">Wählen Sie im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home) **Benutzer** > **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="46417-157">In the [Microsoft 365 admin center](https://portal.office.com/adminportal/home), select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="46417-158">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="46417-158">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="46417-159">Wählen Sie rechts in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="46417-159">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="46417-160">Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="46417-160">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![Screenshot der Seite „Produktlizenzen“ im Admin Center.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="46417-162">Verwalten der Verfügbarkeit von Microsoft Teams für Benutzer, die bereits die explorative Microsoft Teams-Umgebung verwenden</span><span class="sxs-lookup"><span data-stu-id="46417-162">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="46417-163">Wenn ein Benutzer die explorative Microsoft Teams-Umgebung ausführt, können Sie diese deaktivieren, indem Sie die Lizenz oder den Dienstplan entfernen.</span><span class="sxs-lookup"><span data-stu-id="46417-163">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="46417-164">Sie benötigen Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="46417-164">You must have admin privileges.</span></span> 

<span data-ttu-id="46417-165">So deaktivieren Sie die Lizenz für die explorative Microsoft Teams-Umgebung:</span><span class="sxs-lookup"><span data-stu-id="46417-165">To turn off the the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="46417-166">Wählen Sie im Microsoft 365 Admin Center, **Benutzer** > **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="46417-166">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="46417-167">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="46417-167">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="46417-168">Wählen Sie rechts in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="46417-168">On the right, in the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="46417-169">Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche für die explorative Lizenz auf **Aus**.</span><span class="sxs-lookup"><span data-stu-id="46417-169">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>
   
    >[!Note]
    ><span data-ttu-id="46417-170">Die Umschaltfläche für die explorative Microsoft Teams-Umgebung wird angezeigt, sobald der erste Benutzer in der Organisation die explorative Microsoft Teams-Umgebung startet.</span><span class="sxs-lookup"><span data-stu-id="46417-170">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="46417-171">Verwalten von Microsoft Teams für Benutzer, die über die explorative Microsoft Teams-Lizenz verfügen</span><span class="sxs-lookup"><span data-stu-id="46417-171">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="46417-172">Sie können Benutzer mit einer explorativen Microsoft Teams-Lizenz genauso verwalten wie Benutzer mit einer regulären kostenpflichtigen Lizenz.</span><span class="sxs-lookup"><span data-stu-id="46417-172">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="46417-173">Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="46417-173">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="46417-174">Upgraden von Benutzern mit der explorativen Microsoft Teams-Lizenz</span><span class="sxs-lookup"><span data-stu-id="46417-174">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="46417-175">Um Benutzer mit der explorative Microsoft Teams-Lizenz zu upgraden (Sie benötigen Administratorberechtigungen), gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="46417-175">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following:</span></span>

1. <span data-ttu-id="46417-176">Kaufen Sie ein Abonnement, das Microsoft Teams enthält.</span><span class="sxs-lookup"><span data-stu-id="46417-176">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="46417-177">Entfernen Sie das Abonnement der explorativen Microsoft Teams-Umgebung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="46417-177">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="46417-178">Weisen Sie die neu erworbene Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="46417-178">Assign the newly purchased license.</span></span>

<span data-ttu-id="46417-179">Weitere Informationen finden Sie unter [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="46417-179">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="46417-180">Wenn die Microsoft Teams Exploratory-Lizenz abläuft und kein unmittelbares Upgrade auf ein Abonnement, das Microsoft Teams umfasst, für einen Benutzer erfolgt, werden die Benutzerdaten nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="46417-180">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, the user data is not removed.</span></span> <span data-ttu-id="46417-181">Der Benutzer bleibt weiterhin in Azure Active Directory und alle Daten innerhalb von Teams werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="46417-181">The user still exists in Azure Active Directory and all data within Teams still remains.</span></span> <span data-ttu-id="46417-182">Sobald dem Benutzer eine neue Lizenz zugewiesen ist, die Teams-Funktionen aktiviert, sind die Inhalte weiterhin vorhanden.</span><span class="sxs-lookup"><span data-stu-id="46417-182">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist.</span></span> 

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="46417-183">Was geschieht mit den Legacylizenzen für den Test der kommerziellen Cloud von Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="46417-183">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses?</span></span>

<span data-ttu-id="46417-184">Ab Februar 2020 können berechtigte Benutzer mit der Nutzung der neuesten Microsoft Teams Exploratory-Umgebung beginnen.</span><span class="sxs-lookup"><span data-stu-id="46417-184">As of February, 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="46417-185">Alle Legacylizenzen für den Test der kommerziellen Cloud von Microsoft Teams werden automatisch in das neue Angebot konvertiert, bevor die Testversion abläuft.</span><span class="sxs-lookup"><span data-stu-id="46417-185">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="46417-186">Wenn sich ein Benutzer zum ersten Mal bei seiner abgelaufenen Testversion von Microsoft Teams in der kommerziellen Cloud anmeldet, weisen wir dem Benutzer automatisch eine Teams Exploratory Experience-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="46417-186">When a user signs in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to that user.</span></span> <span data-ttu-id="46417-187">Benutzer werden erst konvertiert, wenn sie sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="46417-187">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="46417-188">Entfernen einer explorativen Microsoft Teams-Lizenz</span><span class="sxs-lookup"><span data-stu-id="46417-188">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="46417-189">Wenn Sie diese Lizenz über PowerShell entfernen möchten, ziehen Sie [Entfernen von Lizenzen von Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell) zurate.</span><span class="sxs-lookup"><span data-stu-id="46417-189">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="46417-190">Wenn Sie diese Lizenz über das Verwaltungsportal entfernen möchten, lesen Sie [Löschen eines Benutzers aus Ihrer Organisation](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span><span class="sxs-lookup"><span data-stu-id="46417-190">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="46417-191">Wie lange wird die Teams Exploratory-Umgebung verfügbar sein?</span><span class="sxs-lookup"><span data-stu-id="46417-191">How long does the Teams Exploratory experience last?</span></span>

<span data-ttu-id="46417-192">Die Microsoft Teams Exploratory-Umgebung wird ohne zusätzliche Kosten bis zum nächsten **Fälligkeitstag Ihres Vertrags** oder nach **Verlängerung** am oder ab Januar 2021 verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="46417-192">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="46417-193">Zu diesem Zeitpunkt müssen Endbenutzer mit einer Microsoft Exploratory-Lizenz zu einer kostenpflichtigen Lizenz wechseln, die Microsoft Teams umfasst.</span><span class="sxs-lookup"><span data-stu-id="46417-193">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="46417-194">Alle Microsoft Exploratory-Lizenzen, die danach begonnen wurden, werden bis zu Ihrem nächsten **Fälligkeitstag** oder der nächsten **Verlängerung** ohne zusätzliche Kosten verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="46417-194">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span> 

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-my-anniversary-or-renewal-date"></a><span data-ttu-id="46417-195">Was geschieht, wenn ein Endbenutzer kurz vor dem Fälligkeits- oder Verlängerungsdatum mit der Nutzung der Microsoft Teams Exploratory-Umgebung beginnt?</span><span class="sxs-lookup"><span data-stu-id="46417-195">What happens if an end user initiates the Microsoft Teams Exploratory experience just before my anniversary or renewal date?</span></span>

<span data-ttu-id="46417-196">Microsoft Teams Exploratory-Lizenzen, die innerhalb von 90 Tagen nach dem **Fälligkeitstag** oder der **Verlängerung des Vertrags** begonnen wurden, sind bis zum anschließenden Fälligkeitstag oder Verlängerungszyklus nicht verpflichtet, zu einer kostenpflichtigen Lizenz zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="46417-196">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** will not be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span> 

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="46417-197">Was ist zu tun, wenn mein Vertrag keinen Fälligkeits- oder jährliches Verlängerungsdatum aufweist (z. B. Monatsverträge)?</span><span class="sxs-lookup"><span data-stu-id="46417-197">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)?</span></span>

<span data-ttu-id="46417-198">Bei Verträgen ohne Fälligkeits- oder jährliches Verlängerungsdatum wird das Folgejahr, nachdem der erste Endbenutzer die Microsoft Teams Exploratory-Lizenz aktiviert hat, als Fälligkeits- oder Verlängerungsdatum behandelt.</span><span class="sxs-lookup"><span data-stu-id="46417-198">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="46417-199">Benutzer mit der Microsoft Teams Exploratory-Lizenz müssen bis zu diesem Datum jedes Jahr gemäß den oben genannten Richtlinien in eine kostenpflichtige Lizenz umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="46417-199">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined above.</span></span>

<span data-ttu-id="46417-200">Wenn der erste Endbenutzer Microsoft Teams Exploratory zum Beispiel am 19. Juni 2020 aktiviert, müssen er und alle anderen berechtigten Benutzer im Kundenmandanten bis zum 19. Juni 2021 auf eine kostenpflichtige Lizenz mit Teams umsteigen.</span><span class="sxs-lookup"><span data-stu-id="46417-200">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span> 

