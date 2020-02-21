---
title: Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die app "Schichten" in Teams für First-worker in Ihrer Organisation einrichten und verwalten.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 134ff131307034381b97643a2bf9a3dd7fc87a7d
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161858"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="48334-103">Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="48334-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48334-104">2019, 31. Dezember, wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="48334-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="48334-105">Wir erstellen StaffHub-Funktionen in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="48334-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="48334-106">Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="48334-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="48334-107">StaffHub wird am 31. Dezember 2019 nicht mehr für alle Benutzer funktionieren.</span><span class="sxs-lookup"><span data-stu-id="48334-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="48334-108">Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist.</span><span class="sxs-lookup"><span data-stu-id="48334-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="48334-109">Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="48334-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="48334-110">Übersicht über Schichten</span><span class="sxs-lookup"><span data-stu-id="48334-110">Overview of Shifts</span></span>

<span data-ttu-id="48334-111">Mit der App "Schichten" in Microsoft Teams sind die Mitarbeiter von firstal verbunden und synchron. Es ist ein mobiles Gerät, das für schnelle und effektive Zeitmanagement und Kommunikation für Teams entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="48334-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="48334-112">Mithilfe von Schichten können First-Worker und Ihre Manager Ihre mobilen Geräte verwenden, um Zeitpläne zu verwalten und in Kontakt zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="48334-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="48334-113">Manager erstellen, aktualisieren und verwalten Schichtpläne für Teams.</span><span class="sxs-lookup"><span data-stu-id="48334-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="48334-114">Sie können Nachrichten an eine Person senden ("Es gibt einen Überlauf auf dem Boden") oder das gesamte Team ("der regionale GM wird in 20 Minuten ankommen").</span><span class="sxs-lookup"><span data-stu-id="48334-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="48334-115">Sie können auch Richtliniendokumente, Nachrichtenbulletins und Videos senden.</span><span class="sxs-lookup"><span data-stu-id="48334-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="48334-116">Die Mitarbeiter sehen Ihre bevorstehenden Schichten an, können sehen, wer sonst für den Tag geplant ist, die Anforderung zum tauschen oder zur Verfügung stellen und eine freie Zeit anfordern.</span><span class="sxs-lookup"><span data-stu-id="48334-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="48334-117">Es ist wichtig zu wissen, dass Schichten die Gastbenutzer derzeit nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="48334-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="48334-118">Das bedeutet, dass Gäste in einem Team nicht hinzugefügt oder Schichtpläne verwenden können, wenn der Gastzugriff in Teams aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="48334-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="48334-119">Verfügbarkeit von Schichten</span><span class="sxs-lookup"><span data-stu-id="48334-119">Availability of Shifts</span></span>

<span data-ttu-id="48334-120">Schichten sind in allen Enterprise-SKUs verfügbar, in denen Teams verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="48334-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="48334-121">Speicherort von schichtdaten</span><span class="sxs-lookup"><span data-stu-id="48334-121">Location of Shifts data</span></span>

<span data-ttu-id="48334-122">Schichten Daten werden derzeit in Azure in Rechenzentren in Nordamerika, Westeuropa und Asien-Pazifik gespeichert.</span><span class="sxs-lookup"><span data-stu-id="48334-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="48334-123">Weitere Informationen dazu, wo Daten gespeichert werden, finden Sie unter [wo befinden sich meine Daten](http://o365datacentermap.azurewebsites.net/)?</span><span class="sxs-lookup"><span data-stu-id="48334-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="48334-124">Einrichten von Schichten</span><span class="sxs-lookup"><span data-stu-id="48334-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="48334-125">Aktivieren oder Deaktivieren von Schichten in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="48334-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="48334-126">Schichten sind standardmäßig für alle Teams-Benutzer in Ihrer Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="48334-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="48334-127">Sie können die APP auf der Organisationsebene auf der Seite " [apps verwalten](../../manage-apps.md) " im Microsoft Teams Admin Center deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="48334-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="48334-128">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Teams apps** > **Verwalten von apps** .</span><span class="sxs-lookup"><span data-stu-id="48334-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="48334-129">Führen Sie in der Liste der apps eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="48334-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="48334-130">Wenn Sie die Schichten für Ihre Organisation deaktivieren möchten, suchen Sie nach der APP Schichten, wählen Sie Sie aus, und klicken Sie dann auf **blockieren**.</span><span class="sxs-lookup"><span data-stu-id="48334-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="48334-131">Wenn Sie die Schichten für Ihre Organisation aktivieren möchten, suchen Sie nach der APP Schichten, wählen Sie Sie aus, und klicken Sie dann auf **zulassen**.</span><span class="sxs-lookup"><span data-stu-id="48334-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="48334-132">Aktivieren oder Deaktivieren von Schichten für bestimmte Benutzer in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="48334-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="48334-133">Wenn Sie bestimmten Benutzern in Ihrer Organisation das Verwenden von Schichten erlauben oder blockieren möchten, stellen Sie sicher, dass für Ihre Organisation auf der Seite " [apps verwalten](../../manage-apps.md) " die Option "Schichten" aktiviert ist, und erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie diese Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="48334-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="48334-134">Weitere Informationen finden Sie unter [Verwalten von App-Berechtigungsrichtlinien in Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="48334-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="48334-135">Verwenden der FirstlineWorker-App-Setup Richtlinie zum Anheften von Schichten an Teams</span><span class="sxs-lookup"><span data-stu-id="48334-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="48334-136">Mit den Richtlinien für die APP-Einrichtung können Sie Teams anpassen, um die apps hervorzuheben, die für Benutzer in Ihrer Organisation am wichtigsten sind.</span><span class="sxs-lookup"><span data-stu-id="48334-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="48334-137">Die in einer Richtlinie festgelegten apps werden an&mdash;die APP-Leiste angeheftet, die sich auf der Seite des Teams-Desktop Clients und am unteren&mdash;Rand der mobilen Teams-Clients befindet, auf denen Benutzer schnell und einfach darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="48334-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="48334-138">Teams umfasst eine integrierte Richtlinie für die FirstlineWorker-APP, die Sie den Mitarbeitern in Ihrer Organisation in erster Linie zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="48334-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="48334-139">Standardmäßig umfasst die Richtlinie die Aktivitäten, Schichten, Chats und Anruf-apps.</span><span class="sxs-lookup"><span data-stu-id="48334-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="48334-140">Wenn Sie die FirstlineWorker-Richtlinie anzeigen möchten, wechseln Sie in der linken Navigationsleiste des Microsoft Teams admin Centers zu den**Setup Richtlinien**für **Teams-App** > -app.</span><span class="sxs-lookup"><span data-stu-id="48334-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="48334-141">![Screenshot der FirstlineWorker-App-Setup Richtlinie](../../media/firstline-worker-app-setup-policy.png "Screenshot der FirstlineWorker-App-Setup Richtlinie im Microsoft Teams Admin Center")</span><span class="sxs-lookup"><span data-stu-id="48334-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="48334-142">Zuweisen der FirstlineWorker-Richtlinie zu einzelnen Benutzern</span><span class="sxs-lookup"><span data-stu-id="48334-142">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="48334-143">Navigieren Sie in der linken Navigationsleiste des Microsoft Teams Admin Center zu **Benutzer**, und klicken Sie dann auf den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="48334-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="48334-144">Wählen Sie neben **zugewiesene Richtlinien**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="48334-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="48334-145">Wählen Sie unter **Teams-App-Setup Richtlinie**die Option **FirstlineWorker**aus, und wählen Sie dann **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="48334-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="48334-146">Zuweisen der FirstlineWorker-App-Setup Richtlinie zu Benutzer Mitgliedern einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="48334-146">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="48334-147">Sie können die FirstlineWorker-App-Setup Richtlinie Benutzern einer Gruppe wie einer Sicherheitsgruppe zuweisen, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="48334-147">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="48334-148">Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="48334-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="48334-149">In diesem Beispiel weisen wir die FirstlineWorker-App-Setup Richtlinie allen Benutzer Mitgliedern der Contoso First Team-Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="48334-149">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="48334-150">Stellen Sie sicher, dass Sie zuerst eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="48334-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="48334-151">Abrufen der GroupObject-ID der jeweiligen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="48334-151">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="48334-152">Abrufen der Mitglieder der gewählten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="48334-152">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="48334-153">Weisen Sie die FirstlineWorker-App-Setup Richtlinie allen Benutzer Mitgliedern der Gruppe zu.</span><span class="sxs-lookup"><span data-stu-id="48334-153">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="48334-154">Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="48334-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="48334-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="48334-155">Related topics</span></span>
- [<span data-ttu-id="48334-156">Schicht Hilfe für Mitarbeiter von First-work</span><span class="sxs-lookup"><span data-stu-id="48334-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
