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
description: Hier erfahren Sie, wie Sie die Schichten-App in Microsoft Teams für Mitarbeiter in Service und Produktion in Ihrer Organisation einrichten und verwalten können.
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
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161858"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="9d5e7-103">Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d5e7-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d5e7-104">Am 31. Dezember 2019 wird Microsoft StaffHub eingestellt.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="9d5e7-105">Einige StaffHub-Funktionen werden in Microsoft Teams integriert.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="9d5e7-106">Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="9d5e7-107">StaffHub wird am 31. Dezember 2019 für alle Benutzer eingestellt.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="9d5e7-108">Jedem Benutzer, der StaffHub zu öffnen versucht, wird eine Meldung angezeigt, die ihn zum Microsoft Teams-Download leitet.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="9d5e7-109">Weitere Informationen finden Sie unter [Microsoft StaffHub wird eingestellt](microsoft-staffhub-to-be-retired.md).</span><span class="sxs-lookup"><span data-stu-id="9d5e7-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="9d5e7-110">Übersicht über "Schichten"</span><span class="sxs-lookup"><span data-stu-id="9d5e7-110">Overview of Shifts</span></span>

<span data-ttu-id="9d5e7-111">Die Schichten-App in Microsoft Teams sorgt dafür, dass Mitarbeiter in Service und Produktion vernetzt und ihre Zeitpläne synchronisiert sind. Sie stellt eine mobile Lösung für eine schnelle und effektive Zeitverwaltung und Kommunikation für Teams dar.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-111">The Shifts app in Microsoft Teams keeps Firstline Workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="9d5e7-112">Mithilfe der Schichten-App können Mitarbeiter in Service und Produktion sowie deren Vorgesetzte ihre mobilen Geräte verwenden, um Arbeitszeitpläne zu verwalten und in Kontakt zu bleiben.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-112">Shifts lets Firstline Workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="9d5e7-113">Vorgesetzte erstellen, aktualisieren und verwalten Schichtzeitpläne für Teams.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-113">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="9d5e7-114">Sie können Nachrichten an eine Person ("Der Boden ist schmutzig") oder an das gesamte Team ("Der regionale Geschäftsführer kommt in 20 Minuten") senden.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-114">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="9d5e7-115">Sie können auch Richtliniendokumente, Bekanntmachungen und Videos senden.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-115">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="9d5e7-116">Mitarbeiter können anstehende Schichten anzeigen, sie können sehen, wer für diesen Tag sonst noch eingeteilt ist, einen Schichtwechsel oder arbeitsfreie Zeit beantragen.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-116">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="9d5e7-117">Es ist wichtig zu wissen, dass "Schichten" zurzeit keine Gastbenutzer unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-117">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="9d5e7-118">Dies bedeutet, dass Gäste eines Teams keinen Schichtplänen hinzugefügt werden können und diese auch nicht verwenden können, wenn der Gastzugriff in Microsoft Teams aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-118">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="9d5e7-119">Verfügbarkeit der Schichten-App</span><span class="sxs-lookup"><span data-stu-id="9d5e7-119">Availability of Shifts</span></span>

<span data-ttu-id="9d5e7-120">"Schichten" ist in allen Enterprise-SKUs verfügbar, die Microsoft Teams umfassen.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-120">Shifts is available in all Enterprise SKUs where Teams is available.</span></span>

## <a name="location-of-shifts-data"></a><span data-ttu-id="9d5e7-121">Speicherort von Daten der Schichten-App</span><span class="sxs-lookup"><span data-stu-id="9d5e7-121">Location of Shifts data</span></span>

<span data-ttu-id="9d5e7-122">Daten der Schichten-App werden aktuell in Azure in Rechenzentren in Nordamerika, Westeuropa und im asiatisch-pazifischen Raum gespeichert.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-122">Shifts data is currently stored in Azure in data centers in North America, Western Europe, and Asia Pacific.</span></span> <span data-ttu-id="9d5e7-123">Weitere Informationen zum Speicherort von Daten finden Sie unter [Wo befinden sich meine Daten?](http://o365datacentermap.azurewebsites.net/).</span><span class="sxs-lookup"><span data-stu-id="9d5e7-123">For more information about where data is stored, see [Where is my data](http://o365datacentermap.azurewebsites.net/)?</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="9d5e7-124">Einrichten von "Schichten"</span><span class="sxs-lookup"><span data-stu-id="9d5e7-124">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="9d5e7-125">Aktivieren oder Deaktivieren von "Schichten" in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="9d5e7-125">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="9d5e7-126">"Schichten" ist standardmäßig für alle Microsoft Teams-Benutzer in Ihrer Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-126">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="9d5e7-127">Sie können die App auf Organisationsebene im Microsoft Teams Admin Center auf der Seite [Apps verwalten](../../manage-apps.md) deaktivieren oder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-127">You can turn off or turn on the app at the org level on the [Manage apps](../../manage-apps.md) page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="9d5e7-128">Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **Teams-Apps** > **Apps verwalten**.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-128">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps** .</span></span>
2. <span data-ttu-id="9d5e7-129">Führen Sie in der Liste der Apps einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="9d5e7-129">In the list of apps, do one of the following:</span></span>

    - <span data-ttu-id="9d5e7-130">Wenn Sie "Schichten" für Ihre Organisation deaktivieren möchten, suchen Sie nach der App "Schichten", wählen Sie sie aus, und klicken Sie dann auf **Blockieren**.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-130">To turn off Shifts for your organization, search for the Shifts app, select it, and then click **Block**.</span></span>
    - <span data-ttu-id="9d5e7-131">Wenn Sie "Schichten" für Ihre Organisation aktivieren möchten, suchen Sie nach der App "Schichten", wählen Sie sie aus, und klicken Sie dann auf **Zulassen**.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-131">To turn on Shifts for your organization, search for the Shifts app, select it, and then click **Allow**.</span></span>

### <a name="enable-or-disable-shifts-for-specific-users-in-your-organization"></a><span data-ttu-id="9d5e7-132">Aktivieren oder Deaktivieren von "Schichten" für bestimmte Benutzer in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="9d5e7-132">Enable or disable Shifts for specific users in your organization</span></span>

<span data-ttu-id="9d5e7-133">Wenn Sie die Nutzung von "Schichten" für bestimmte Benutzer in Ihrer Organisation zulassen oder blockieren möchten, stellen Sie sicher, dass die App für Ihre Organisation auf der Seite [Apps verwalten](../../manage-apps.md) aktiviert ist, und erstellen Sie dann eine benutzerdefinierte App-Berechtigungsrichtlinie, und weisen Sie diese den betreffenden Benutzern zu.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-133">To allow or block specific users in your organization from using Shifts, make sure Shifts is turned on for your organization on the [Manage apps](../../manage-apps.md) page, and then create a custom app permission policy and assign it to those users.</span></span> <span data-ttu-id="9d5e7-134">Weitere Informationen finden Sie unter [Verwalten von Richtlinien für App-Berechtigungen in Microsoft Teams](../../teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="9d5e7-134">To learn more, see [Manage app permission policies in Teams](../../teams-app-permission-policies.md).</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="9d5e7-135">Verwenden der FirstlineWorker App-Setup-Richtlinie, um "Schichten" in Microsoft Teams anzuheften</span><span class="sxs-lookup"><span data-stu-id="9d5e7-135">Use the FirstlineWorker app setup policy to pin Shifts to Teams</span></span>

<span data-ttu-id="9d5e7-136">Mithilfe von App-Setup Richtlinien können Sie Microsoft Teams so anpassen, dass die Apps, die für die Benutzer in Ihrer Organisation am wichtigsten sind, hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-136">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="9d5e7-137">Die in einer Richtlinie festgelegten Apps werden an die App-Leiste geheftet &mdash;das ist die seitliche Leiste bei Microsoft Teams-Desktop-Clients und am unteren Rand bei Microsoft Teams Mobile-Clients&mdash;, von wo die Benutzer schnell und einfach darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-137">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="9d5e7-138">Microsoft Teams umfasst eine integrierte FirstlineWorker-App-Setup-Richtlinie, die Sie Mitarbeitern in Service und Produktion in Ihrem Unternehmen zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-138">Teams includes a built-in FirstlineWorker app setup policy that you can assign to Firstline Workers in your organization.</span></span> <span data-ttu-id="9d5e7-139">Standardmäßig beinhaltet diese Richtlinie die Apps für Aktivität, Schichten, Chat und Anrufe.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-139">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="9d5e7-140">Wenn Sie die FirstlineWorker-Richtlinie anzeigen möchten, wechseln Sie im linken Navigationsbereich des Microsoft Teams Admin Centers zu **Teams-App** > **-App-Setup-Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-140">To view the FirstlineWorker policy, in the left navigation of the Microsoft Teams admin center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="9d5e7-141">![Screenshot der FirstlineWorker-App-Setup-Richtlinie](../../media/firstline-worker-app-setup-policy.png "Screenshot der FirstlineWorker-App-Setup-Richtlinie im Microsoft Teams Admin Center")</span><span class="sxs-lookup"><span data-stu-id="9d5e7-141">![Screenshot of the FirstlineWorker app setup policy](../../media/firstline-worker-app-setup-policy.png "Screenshot of the FirstlineWorker app setup policy in the Microsoft Teams admin center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="9d5e7-142">Einzelnen Benutzern die FirstlineWorker-Richtlinie zuweisen</span><span class="sxs-lookup"><span data-stu-id="9d5e7-142">Assign the FirstlineWorker policy to individual users</span></span>

1. <span data-ttu-id="9d5e7-143">Wechseln Sie in der linken Navigation des Microsoft Teams Admin Centers zu **Benutzer**, und klicken Sie dann den gewünschten Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="9d5e7-144">Wählen Sie neben **Zugewiesene Richtlinien\*\*\*\*Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-144">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="9d5e7-145">Wählen Sie unter **Teams-App-Setup-Richtlinie\*\*\*\*FirstlineWorker** und dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-145">Under **Teams App Setup policy**, select **FirstlineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-user-members-of-a-group"></a><span data-ttu-id="9d5e7-146">Die FirstlineWorker App-Setup-Richtlinie Mitgliedern einer Gruppe zuweisen</span><span class="sxs-lookup"><span data-stu-id="9d5e7-146">Assign the FirstlineWorker app setup policy to user members of a group</span></span>

<span data-ttu-id="9d5e7-147">Sie können die FirstlineWorker-App-Setup-Richtlinie Mitgliedern einer Gruppe wie z. B. einer Sicherheitsgruppe zuweisen, indem Sie eine Verbindung mit dem Azure Active Directory PowerShell für Graph-Modul und dem Skype for Business PowerShell-Modul herstellen.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-147">You can assign the FirstlineWorker app setup policy to user members of a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="9d5e7-148">Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Teams finden Sie unter [Überblick über PowerShell für Microsoft Teams](../../teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9d5e7-148">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](../../teams-powershell-overview.md).</span></span>

<span data-ttu-id="9d5e7-149">In diesem Beispiel wird die FirstlineWorker-App-Setup-Richtlinie allen Mitgliedern der Gruppe "Contoso Firstline-Team" zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-149">In this example, we assign the FirstlineWorker app setup policy to all user members of the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="9d5e7-150">Stellen Sie sicher, dass Sie zuerst eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul und dem Skype for Business PowerShell-Modul herstellen, indem Sie die Schritte unter [Verbinden mit allen Office 365-Diensten in einem einzigen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)ausführen.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-150">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="9d5e7-151">Abrufen der GroupObject-ID der jeweiligen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-151">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="9d5e7-152">Abrufen der Mitglieder der gewählten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-152">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="9d5e7-153">Die FirstlineWorker App-Setup-Richtlinie allen Mitgliedern der Gruppe zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-153">Assign the FirstlineWorker app setup policy to all user members of the group.</span></span>
```PowerShell
$members | ForEach-Object {Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="9d5e7-154">Je nach Anzahl der Mitglieder einer Gruppe kann das Ausführen dieses Befehls mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="9d5e7-154">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9d5e7-155">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9d5e7-155">Related topics</span></span>
- [<span data-ttu-id="9d5e7-156">Hilfe zur Schichten-App für Mitarbeiter in Service und Produktion</span><span class="sxs-lookup"><span data-stu-id="9d5e7-156">Shifts Help for Firstline Workers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
