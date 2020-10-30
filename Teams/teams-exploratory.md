---
title: Verwalten der explorativen Microsoft Teams-Umgebung
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: a266d9d3ea8fd572cca171768174d86094a8c945
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766968"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="cc430-103">Verwalten der explorativen Lizenz von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc430-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="cc430-104">Die Microsoft Teams Exploratory-Umgebung ermöglicht Benutzern in Ihrer Organisation, die über Azure Active Directory (Azure AD) verfügen und nicht für Microsoft Teams lizenziert sind, eine explorative Microsoft Teams-Umgebung zu starten.</span><span class="sxs-lookup"><span data-stu-id="cc430-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="cc430-105">Administratoren können dieses Feature für Benutzer in ihrer Organisation aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cc430-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="cc430-106">Die frühere [Microsoft Commercial Cloud-Testversion](iw-trial-teams.md) wurde durch die explorative Microsoft Teams-Umgebung ersetzt.</span><span class="sxs-lookup"><span data-stu-id="cc430-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="cc430-107">Was steckt in der Microsoft Teams Exploratory-Umgebung?</span><span class="sxs-lookup"><span data-stu-id="cc430-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="cc430-108">Folgende Dienstpläne werden einem Administrator als Teil der Microsoft Teams Exploratory-Umgebung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="cc430-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="cc430-109">Exchange Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="cc430-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="cc430-110">Flow für Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="cc430-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="cc430-111">MyAnalytics Insights</span><span class="sxs-lookup"><span data-stu-id="cc430-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="cc430-112">Microsoft Forms (Plan E1)</span><span class="sxs-lookup"><span data-stu-id="cc430-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="cc430-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="cc430-113">Microsoft Planner</span></span>
- <span data-ttu-id="cc430-114">Microsoft Search</span><span class="sxs-lookup"><span data-stu-id="cc430-114">Microsoft Search</span></span>
- <span data-ttu-id="cc430-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="cc430-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="cc430-116">Microsoft Stream für Microsoft 365 und Office 365 E1 SKUs <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="cc430-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="cc430-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc430-117">Microsoft Teams</span></span>
- <span data-ttu-id="cc430-118">Verwaltung mobiler Geräte für Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="cc430-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="cc430-119">Office Mobile-Apps für Office 365</span><span class="sxs-lookup"><span data-stu-id="cc430-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="cc430-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="cc430-120">Office Online</span></span>
- <span data-ttu-id="cc430-121">PowerApps für Microsoft 365 oder Office 365</span><span class="sxs-lookup"><span data-stu-id="cc430-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="cc430-122">SharePoint Online (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="cc430-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="cc430-123">Sway</span><span class="sxs-lookup"><span data-stu-id="cc430-123">Sway</span></span>
- <span data-ttu-id="cc430-124">To-Do (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="cc430-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="cc430-125">Whiteboard (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="cc430-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="cc430-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="cc430-126">Yammer Enterprise</span></span>

  <span data-ttu-id="cc430-127"><sup>1</sup> Der Wechsel von Microsoft Stream zu [OneDrive for Business und SharePoint für Besprechungsaufzeichnungen](tmr-meeting-recording-change.md) erfolgt schrittweise.</span><span class="sxs-lookup"><span data-stu-id="cc430-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="cc430-128">Beim Start können Sie sich für diese Umgebung entscheiden.</span><span class="sxs-lookup"><span data-stu-id="cc430-128">At launch you'll be able to opt in to this experience.</span></span> <span data-ttu-id="cc430-129">Sie müssen sich im November abmelden, wenn Sie Stream weiterhin verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="cc430-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="cc430-130">Anfang 2021 müssen alle Kunden OneDrive for Business und SharePoint für neue Besprechungsaufzeichungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc430-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="cc430-131">Wer ist anspruchsberechtigt?</span><span class="sxs-lookup"><span data-stu-id="cc430-131">Who's eligible</span></span>

<span data-ttu-id="cc430-132">Benutzer erfüllen die Kriterien für eine Microsoft Teams Exploratory-Umgebung wenn sie:</span><span class="sxs-lookup"><span data-stu-id="cc430-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="cc430-133">Über eine verwaltete Azure AD-Domain-E-Mail-Adresse verfügen.</span><span class="sxs-lookup"><span data-stu-id="cc430-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="cc430-134">Zu einem Mandanten mit einem kostenpflichtigen Abonnement gehören.</span><span class="sxs-lookup"><span data-stu-id="cc430-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="cc430-135">Benutzern muss (im Microsoft 365 Admin Center) die Möglichkeit bereitgestellt werden, sich für Apps und Testversionen zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="cc430-135">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="cc430-136">Weitere Informationen finden Sie weiter unten in diesem Artikel unter [Verwalten der explorativen Microsoft Teams-Umgebung](#manage-the-teams-exploratory-experience).</span><span class="sxs-lookup"><span data-stu-id="cc430-136">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="cc430-137">Wer ist nicht berechtigt?</span><span class="sxs-lookup"><span data-stu-id="cc430-137">Who isn't eligible</span></span>

<span data-ttu-id="cc430-138">Benutzer erfüllen nicht die Kriterien, wenn sie:</span><span class="sxs-lookup"><span data-stu-id="cc430-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="cc430-139">Teams gegenwärtig oder früher als bezahlte, unbezahlte oder Probelizenz verwendeten</span><span class="sxs-lookup"><span data-stu-id="cc430-139">Currently or previously had Teams from a paid, unpaid or trial license</span></span> 
- <span data-ttu-id="cc430-140">Zu einem Mandanten gehören, der mindestens ein spezielles COVID-Angebot nutzte/empfing.</span><span class="sxs-lookup"><span data-stu-id="cc430-140">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="cc430-141">Ihre Organisation ist nicht für dieses Angebot berechtigt, wenn Sie ein Syndication-Partnerkunde oder ein GCC-, GCC High-, DoD- oder EDU-Kunde sind.</span><span class="sxs-lookup"><span data-stu-id="cc430-141">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="cc430-142">So können Benutzer sich für die explorative Microsoft Teams-Umgebung registrieren</span><span class="sxs-lookup"><span data-stu-id="cc430-142">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="cc430-143">Berechtigte Benutzer können sich für die explorative Microsoft Teams-Umgebung registrieren, indem sie sich bei Microsoft Teams ([teams.microsoft.com](https://teams.microsoft.com)) anmelden.</span><span class="sxs-lookup"><span data-stu-id="cc430-143">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="cc430-144">Daraufhin wird ihnen automatisch diese Lizenz zugewiesen. Der Mandantenadministrator erhält eine E-Mail-Benachrichtigung, wenn eine Person in Ihrer Organisation die Microsoft Teams Exploratory-Umgebung zum ersten Mal startet.</span><span class="sxs-lookup"><span data-stu-id="cc430-144">They'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="cc430-145">Verwalten der Microsoft Teams Exploratory-Umgebung</span><span class="sxs-lookup"><span data-stu-id="cc430-145">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="cc430-146">Die Microsoft Teams Exploratory-Umgebung ist für die Initialisierung durch einzelne Endbenutzer bestimmt, und Sie sind nicht berechtigt, dieses Angebot im Namen von Endbenutzern oder Angestellten zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="cc430-146">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="cc430-147">Die Microsoft Teams Exploratory-Umgebung wird mit einer Exchange Online-Lizenz geliefert, die dem Benutzer jedoch erst vom Administrator zugewiesen werden muss.</span><span class="sxs-lookup"><span data-stu-id="cc430-147">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="cc430-148">Verfügt der Benutzer noch über keine Exchange-Lizenz, kann er keine Besprechungen in Microsoft Teams planen und andere Microsoft Teams-Funktionen möglicherweise nicht verwenden, solange der Administrator die Exchange Online-Lizenz noch nicht zugewiesen hat.</span><span class="sxs-lookup"><span data-stu-id="cc430-148">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="cc430-149">Administratoren können die Option zur Ausführung der explorativen Microsoft Teams-Umgebung für Benutzer in ihrer Organisation über den Switch **Test-Apps und -Dienste** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="cc430-149">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="cc430-150">Verhindern, dass Benutzer Test-Apps und -dienste installieren</span><span class="sxs-lookup"><span data-stu-id="cc430-150">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="cc430-151">Sie können die Möglichkeit eines Benutzers zum Installieren von Test-Apps und -Diensten deaktivieren. Auf diese Weise hindern Sie ihn daran, die explorative Microsoft Teams-Umgebung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cc430-151">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="cc430-152">Navigieren Sie im Microsoft 365 Admin Center zu **Einstellungen** > **Organisationseinstellungen** , wählen Sie **Dienste** und dann **Apps und Dienste im Besitz des Benutzers** aus.</span><span class="sxs-lookup"><span data-stu-id="cc430-152">From the Microsoft 365 admin center, go to **Settings** > **Org settings** , select **Services** , and then select **User owned apps and services** .</span></span>

    ![die Seite "Dienste" im Admin Center](media/iw-trial-services.png)

2. <span data-ttu-id="cc430-154">Deaktivieren Sie das Kontrollkästchen **Benutzer Test-Apps und -dienste installieren lassen** . </span><span class="sxs-lookup"><span data-stu-id="cc430-154">Clear the **Let users install trial apps and services** check box.</span></span>

    ![die Seite "Apps und Dienste im Besitz des Benutzers" im Admin Center](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="cc430-156">Wenn Ihre Organisation nicht berechtigt ist, die explorative Microsoft Teams-Umgebung in Anspruch zu nehmen, wird die Option **Benutzer Test-Apps und -dienste installieren lassen** nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc430-156">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="cc430-157">Verwalten der Verfügbarkeit für einen Benutzer mit einer Lizenz, die Microsoft Teams umfasst</span><span class="sxs-lookup"><span data-stu-id="cc430-157">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="cc430-158">Ein Benutzer, dem eine Lizenz zugewiesen wurde, die Microsoft Teams bereits umfasst, ist nicht berechtigt, die explorative Microsoft Teams-Umgebung in Anspruch zu nehmen.</span><span class="sxs-lookup"><span data-stu-id="cc430-158">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="cc430-159">Wenn der Microsoft Teams-Serviceplan aktiviert ist, kann sich der Benutzer anmelden und Microsoft Teams verwenden.</span><span class="sxs-lookup"><span data-stu-id="cc430-159">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="cc430-160">Wenn der Dienstplan deaktiviert ist, kann sich der Benutzer nicht anmelden, und die explorative Microsoft Teams-Umgebung ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cc430-160">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="cc430-161">Sie benötigen Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="cc430-161">You must have admin privileges.</span></span>

<span data-ttu-id="cc430-162">So deaktivieren Sie den Zugriff auf Teams:</span><span class="sxs-lookup"><span data-stu-id="cc430-162">To turn off access to Teams:</span></span>

1. <span data-ttu-id="cc430-163">Wählen Sie im Microsoft 365 Admin Center, **Benutzer** > **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="cc430-163">In the Microsoft 365 admin center, select **Users** > **Active users** .</span></span>

2. <span data-ttu-id="cc430-164">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cc430-164">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="cc430-165">Wählen Sie in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="cc430-165">In the **Product licenses** row, choose **Edit** .</span></span>

4. <span data-ttu-id="cc430-166">Setzen Sie im Bereich **Produktlizenzen** die Umschaltfläche auf **Aus** .</span><span class="sxs-lookup"><span data-stu-id="cc430-166">In the **Product licenses** pane, switch the toggle to **Off** .</span></span>

    ![die Seite „Produktlizenzen“ im Admin Center](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="cc430-168">Verwalten der Verfügbarkeit von Microsoft Teams für Benutzer, die bereits die explorative Microsoft Teams-Umgebung verwenden</span><span class="sxs-lookup"><span data-stu-id="cc430-168">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="cc430-169">Wenn ein Benutzer die explorative Microsoft Teams-Umgebung ausführt, können Sie diese deaktivieren, indem Sie die Lizenz oder den Dienstplan entfernen.</span><span class="sxs-lookup"><span data-stu-id="cc430-169">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="cc430-170">Sie benötigen Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="cc430-170">You must have admin privileges.</span></span>

<span data-ttu-id="cc430-171">So deaktivieren Sie die Lizenz für die Microsoft Teams Exploratory-Umgebung:</span><span class="sxs-lookup"><span data-stu-id="cc430-171">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="cc430-172">Wählen Sie im Microsoft 365 Admin Center, **Benutzer** > **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="cc430-172">In the Microsoft 365 admin center, select **Users** > **Active users** .</span></span>

2. <span data-ttu-id="cc430-173">Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cc430-173">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="cc430-174">Wählen Sie in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="cc430-174">In the **Product licenses** row, choose **Edit** .</span></span>

4. <span data-ttu-id="cc430-175">Wechseln Sie im Bereich **Produktlizenzen** die Umschaltfläche für die explorative Lizenz auf **Aus** .</span><span class="sxs-lookup"><span data-stu-id="cc430-175">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off** .</span></span>

    >[!Note]
    ><span data-ttu-id="cc430-176">Die Umschaltfläche für die explorative Microsoft Teams-Umgebung wird angezeigt, sobald der erste Benutzer in der Organisation die explorative Microsoft Teams-Umgebung startet.</span><span class="sxs-lookup"><span data-stu-id="cc430-176">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="cc430-177">Verwalten von Microsoft Teams für Benutzer, die über die explorative Microsoft Teams-Lizenz verfügen</span><span class="sxs-lookup"><span data-stu-id="cc430-177">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="cc430-178">Sie können Benutzer mit einer explorativen Microsoft Teams-Lizenz genauso verwalten wie Benutzer mit einer regulären kostenpflichtigen Lizenz.</span><span class="sxs-lookup"><span data-stu-id="cc430-178">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="cc430-179">Weitere Informationen finden Sie unter [Verwalten von Microsoft Teams-Einstellungen in Ihrer Organisation](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="cc430-179">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="cc430-180">Upgraden von Benutzern mit der explorativen Microsoft Teams-Lizenz</span><span class="sxs-lookup"><span data-stu-id="cc430-180">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="cc430-181">Um Benutzer mit der Microsoft Teams Exploratory-Lizenz zu upgraden (Sie benötigen Administratorberechtigungen), gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="cc430-181">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="cc430-182">Kaufen Sie ein Abonnement, das Microsoft Teams enthält.</span><span class="sxs-lookup"><span data-stu-id="cc430-182">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="cc430-183">Entfernen Sie das Abonnement der explorativen Microsoft Teams-Umgebung des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cc430-183">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="cc430-184">Weisen Sie die neu erworbene Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="cc430-184">Assign the newly purchased license.</span></span>

<span data-ttu-id="cc430-185">Weitere Informationen finden Sie unter [Microsoft Teams-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="cc430-185">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="cc430-186">Wenn die Microsoft Teams Exploratory-Lizenz endet und für einen Benutzer nicht sofort ein Upgrade auf ein Abonnement vorgenommen wird, das Microsoft Teams umfasst, hat er eine Nachfrist von 30 Tagen und dann weitere 30 Tage, nach deren Ablauf die Daten gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="cc430-186">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted.</span></span> <span data-ttu-id="cc430-187">Der Benutzer ist weiterhin in Azure Active Directory vorhanden.</span><span class="sxs-lookup"><span data-stu-id="cc430-187">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="cc430-188">Sobald dem Benutzer eine neue Lizenz zugewiesen wurde, um Microsoft Teams-Funktionen wieder zu aktivieren, sind die Inhalte weiterhin vorhanden, sofern der Benutzer innerhalb der Nachfrist hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="cc430-188">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="cc430-189">Was geschieht mit älteren Lizenzen für Microsoft Teams Commercial Cloud-Testversionen?</span><span class="sxs-lookup"><span data-stu-id="cc430-189">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="cc430-190">Seit Februar 2020 können anspruchsberechtigte Benutzer mit der Nutzung der neuesten Microsoft Teams Exploratory-Umgebung beginnen.</span><span class="sxs-lookup"><span data-stu-id="cc430-190">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="cc430-191">Alle älteren Lizenzen für Microsoft Teams Commercial Cloud-Testversionen werden automatisch in das neue Angebot konvertiert, bevor die entsprechenden Testversionen ablaufen.</span><span class="sxs-lookup"><span data-stu-id="cc430-191">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="cc430-192">Wenn sich ein Benutzer zum ersten Mal bei seiner abgelaufenen Microsoft Teams Commercial Cloud-Testversionen anmeldet, wird ihm automatisch eine Lizenz für die Microsoft Teams Exploratory-Umgebung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cc430-192">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users.</span></span> <span data-ttu-id="cc430-193">Benutzer werden erst konvertiert, wenn sie sich anmelden.</span><span class="sxs-lookup"><span data-stu-id="cc430-193">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="cc430-194">Entfernen einer explorativen Microsoft Teams-Lizenz</span><span class="sxs-lookup"><span data-stu-id="cc430-194">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="cc430-195">Wenn Sie diese Lizenz über PowerShell entfernen möchten, ziehen Sie [Entfernen von Lizenzen von Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell) zurate.</span><span class="sxs-lookup"><span data-stu-id="cc430-195">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="cc430-196">Wenn Sie diese Lizenz über das Verwaltungsportal entfernen möchten, lesen Sie [Löschen eines Benutzers aus Ihrer Organisation](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user).</span><span class="sxs-lookup"><span data-stu-id="cc430-196">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="cc430-197">Was sieht die Datenaufbewahrungsrichtlinie vor</span><span class="sxs-lookup"><span data-stu-id="cc430-197">What is the data retention policy</span></span>

<span data-ttu-id="cc430-198">Informationen hierzu finden Sie unter [Informationen zum Microsoft 365-Abonnement](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="cc430-198">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="cc430-199">Wie lange die Teams Exploratory-Umgebung verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="cc430-199">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="cc430-200">Die Microsoft Teams Exploratory-Umgebung wird ohne zusätzliche Kosten bis zum nächsten **Fälligkeitstag Ihres Vertrags** oder nach **Verlängerung** am oder ab Januar 2021 verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="cc430-200">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="cc430-201">Zu diesem Zeitpunkt müssen Endbenutzer mit einer Microsoft Exploratory-Lizenz zu einer kostenpflichtigen Lizenz wechseln, die Microsoft Teams umfasst.</span><span class="sxs-lookup"><span data-stu-id="cc430-201">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="cc430-202">Alle Microsoft Exploratory-Lizenzen, die danach begonnen wurden, werden bis zu Ihrem nächsten **Fälligkeitstag** oder der nächsten **Verlängerung** ohne zusätzliche Kosten verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="cc430-202">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="cc430-203">Was geschieht, wenn ein Endbenutzer kurz vor dem Fälligkeits- oder Verlängerungsdatum mit der Nutzung der Microsoft Teams Exploratory-Umgebung beginnt?</span><span class="sxs-lookup"><span data-stu-id="cc430-203">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="cc430-204">Lizenzen für die Microsoft Teams Exploratory-Umgebung, die innerhalb von 90 Tagen nach dem **Fälligkeitstag** oder der **Verlängerung des Vertrags** begonnen wurden, sind bis zum anschließenden Fälligkeitstag oder Verlängerungszyklus nicht zum Wechsel zu einer kostenpflichtigen Lizenz verpflichtet.</span><span class="sxs-lookup"><span data-stu-id="cc430-204">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="cc430-205">Was ist zu tun, wenn mein Vertrag keinen Fälligkeits- oder kein jährliches Verlängerungsdatum aufweist (z. B. Monatsverträge)?</span><span class="sxs-lookup"><span data-stu-id="cc430-205">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="cc430-206">Bei Verträgen ohne Fälligkeits- oder jährliches Verlängerungsdatum wird das Folgejahr, nachdem der erste Endbenutzer die Lizenz für die Microsoft Teams Exploratory-Umgebung aktiviert hat, als Fälligkeits- oder Verlängerungsdatum behandelt.</span><span class="sxs-lookup"><span data-stu-id="cc430-206">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end-user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="cc430-207">Benutzer mit der Lizenz für die Microsoft Teams Exploratory-Umgebung müssen bis zu diesem Datum jedes Jahr gemäß den in diesem Artikel genannten Richtlinien zu einer kostenpflichtigen Lizenz wechseln.</span><span class="sxs-lookup"><span data-stu-id="cc430-207">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="cc430-208">Wenn der erste Endbenutzer Microsoft Teams Exploratory zum Beispiel am 19. Juni 2020 aktiviert, müssen er und alle anderen berechtigten Benutzer im Kundenmandanten bis zum 19. Juni 2021 auf eine kostenpflichtige Lizenz mit Teams umsteigen.</span><span class="sxs-lookup"><span data-stu-id="cc430-208">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="cc430-209">Nach Ablauf der vorherigen Exploratory-Testlizenz werden Kunden deaktiviert und drei Monate lang daran gehindert, eine neue Testversion zu starten.</span><span class="sxs-lookup"><span data-stu-id="cc430-209">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
