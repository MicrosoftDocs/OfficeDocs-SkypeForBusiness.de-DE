---
title: Verwalten der app Schichten für Ihre Organisation im Microsoft-Teams
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 1/10/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zum Einrichten und Verwalten der app Schichten in Teams für Mitarbeiter in Ihrer Organisation Firstline.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fdd9c47e54c9ce51e736363eb47227614824a4c
ms.sourcegitcommit: 768c7b5f0aaa4b38a0b98c7c9ff904ffedd2e9b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "27893357"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a><span data-ttu-id="8f9a5-103">Verwalten der app Schichten für Ihre Organisation im Microsoft-Teams</span><span class="sxs-lookup"><span data-stu-id="8f9a5-103">Manage the Shifts app for your organization in Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8f9a5-104">Die Übermittlung wirksamer wird 1 Oktober 2019, Microsoft StaffHub zurückgezogen werden.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="8f9a5-105">Wir sind StaffHub Funktionen, einschließlich Zeitplan und Task Management in Microsoft-Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-105">We're building StaffHub capabilities, including schedule and task management, into Microsoft Teams.</span></span> <span data-ttu-id="8f9a5-106">Zusätzliche Funktionen für Firstline Mitarbeiter werden über einen Zeitraum Teams einführen.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-106">Additional capabilities for firstline workers will roll out to Teams over time.</span></span> <span data-ttu-id="8f9a5-107">Weitere Informationen finden Sie unter [Microsoft StaffHub zurückgezogen werden](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0).</span><span class="sxs-lookup"><span data-stu-id="8f9a5-107">To learn more, see [Microsoft StaffHub to be retired](https://support.office.com/article/microsoft-staffhub-to-be-retired-30ca17f3-5502-4bc9-bb0a-bed04bb362f0).</span></span>  

## <a name="overview-of-shifts"></a><span data-ttu-id="8f9a5-108">Übersicht über die Schichten</span><span class="sxs-lookup"><span data-stu-id="8f9a5-108">Overview of Shifts</span></span>
<span data-ttu-id="8f9a5-109">Die Schichten-app in Microsoft-Teams, hält Firstline Mitarbeiter verbundenen und synchronisiert. Mobile zunächst für eine schnelle und effektive zeitverwaltung und Kommunikation für Teams basiert.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-109">The Shifts app in Microsoft Teams keeps firstline workers connected and in sync. It's built mobile first for fast and effective time management and communication for teams.</span></span> <span data-ttu-id="8f9a5-110">Schichten können Firstline Mitarbeiter und deren Manager ihren mobilen Geräten verwenden, um Zeitpläne verwalten und in Verbindung bleiben.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-110">Shifts lets firstline workers and their managers use their mobile devices to manage schedules and keep in touch.</span></span> 

- <span data-ttu-id="8f9a5-111">Manager erstellen, aktualisieren und UMSCHALT Zeitpläne für Teams verwalten.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-111">Managers create, update, and manage shift schedules for teams.</span></span> <span data-ttu-id="8f9a5-112">Sie können Nachrichten an eine Person senden ("Es ist einem Spill auf der Bodenfläche") oder das gesamte team ("der regionalen konzipiert ist in 20 Minuten eintreffen").</span><span class="sxs-lookup"><span data-stu-id="8f9a5-112">They can send messages to one person ("there's a spill on the floor") or the entire team ("the regional GM is arriving in 20 minutes").</span></span> <span data-ttu-id="8f9a5-113">Sie können auch Dokumente zu Richtlinien, amtliche nachrichtenverlautbarungen und Videos senden.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-113">They can also send policy documents, news bulletins, and videos.</span></span> 
- <span data-ttu-id="8f9a5-114">Mitarbeiter können ihre bevorstehenden Schichten anzeigen, finden Sie unter, wer außer für den Tag geplant ist, zu vertauschen und bieten eine Schicht Anforderungszeit deaktiviert anfordern.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-114">Employees view their upcoming shifts, can see who else is scheduled for the day, request to swap or offer a shift, and request time off.</span></span> 

<span data-ttu-id="8f9a5-115">Es ist wichtig, zu wissen, dass Schichten unterstützt derzeit keine Gastbenutzer.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-115">It's important to know that Shifts currently doesn't support guest users.</span></span> <span data-ttu-id="8f9a5-116">Dies bedeutet, dass Gäste auf ein Team können nicht hinzugefügt werden, oder UMSCHALT Zeitpläne verwenden, wenn Access Gast in Teams aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-116">This means that guests on a team can't be added to or use shift schedules when Guest access is turned on in Teams.</span></span> 

## <a name="availability-of-shifts"></a><span data-ttu-id="8f9a5-117">Verfügbarkeit von Schichten</span><span class="sxs-lookup"><span data-stu-id="8f9a5-117">Availability of Shifts</span></span>

<span data-ttu-id="8f9a5-118">Schichten ist in allen Office 365-Abonnements, die Teams, mit ein paar Ausnahmen enthalten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-118">Shifts is available in all Office 365 subscriptions that include Teams, with a couple of exceptions.</span></span> <span data-ttu-id="8f9a5-119">Ausnahmen sind US-Regierung Cloud-Community (GCC) und Teams frei.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-119">The exceptions are US Government Cloud Community (GCC) and Teams free.</span></span> <span data-ttu-id="8f9a5-120">Schichten nicht in Office-365 US-Regierung oder Teams frei angeboten.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-120">Shifts isn't available in Office 365 US Government or Teams free offerings.</span></span>

<span data-ttu-id="8f9a5-121">Weitere Informationen zu Lizenzierung für Teams finden Sie unter [Office 365-Lizenzierung für Teams](Office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="8f9a5-121">To learn more about licensing for Teams, see [Office 365 licensing for Teams](Office-365-licensing.md).</span></span>

## <a name="set-up-shifts"></a><span data-ttu-id="8f9a5-122">Einrichten von Schichten</span><span class="sxs-lookup"><span data-stu-id="8f9a5-122">Set up Shifts</span></span>

### <a name="enable-or-disable-shifts-in-your-organization"></a><span data-ttu-id="8f9a5-123">Aktivieren oder Deaktivieren von Schichten in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="8f9a5-123">Enable or disable Shifts in your organization</span></span>

<span data-ttu-id="8f9a5-124">Schichten ist standardmäßig für alle Teams Benutzer in Ihrer Organisation aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-124">Shifts is enabled by default for all Teams users in your organization.</span></span> <span data-ttu-id="8f9a5-125">Sie können deaktivieren oder Aktivieren der app für Ihre Organisation in der Microsoft-365-Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-125">You can turn off or turn on the app for your organization in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="8f9a5-126">Melden Sie sich bei Microsoft 365 Administrationscenter mit Ihrem Office 365-Admin-Konto.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-126">Sign in to the Microsoft 365 admin center with your Office 365 admin account.</span></span>
2. <span data-ttu-id="8f9a5-127">Wechseln Sie zu **Einstellungen** > **Services & -add-ins** > **Microsoft-Teams**.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-127">Go to **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> 
3. <span data-ttu-id="8f9a5-128">Klicken Sie unter **Einstellungen für die gesamte Mandanten** **Apps**, und deaktivieren Sie unter **Default Apps**, ein, oder aktivieren Sie das Kontrollkästchen **Schichten** deaktivieren oder aktivieren Sie die app.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-128">Under **Tenant-wide settings**, select **Apps**, and then under **Default Apps**, clear or select the **Shifts** check box to turn off or turn on the app.</span></span> 

    <span data-ttu-id="8f9a5-129">![Screenshot des Abschnitts Standard-Apps] (media/firstline-worker-enable-disable-shifts.png "Screenshot des Abschnitts Standard-Apps in der Microsoft-365-Verwaltungskonsole mit der Liste der apps, einschließlich app-Schichten")</span><span class="sxs-lookup"><span data-stu-id="8f9a5-129">![Screen shot of the Default Apps section](media/firstline-worker-enable-disable-shifts.png "Screen shot of the Default Apps section in the Microsoft 365 admin center, showing the list of apps, including the Shifts app")</span></span>

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a><span data-ttu-id="8f9a5-130">Verwenden Sie die Richtlinie FirstLineWorker app Setup Pin Schichten Teams</span><span class="sxs-lookup"><span data-stu-id="8f9a5-130">Use the FirstLineWorker app setup policy to pin Shifts to Teams</span></span>

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

<span data-ttu-id="8f9a5-131">Richtlinien für die App Setup können Sie Teams zum Hervorheben von apps, die für Benutzer in Ihrer Organisation am wichtigsten sind anpassen.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-131">App setup policies let you customize Teams to highlight the apps that are most important for users in your organization.</span></span> <span data-ttu-id="8f9a5-132">Die apps in einer Richtlinie festgelegt werden auf der app-Leiste angeheftete&mdash;der Leiste rechts auf dem Desktopclient Teams und am unteren Rand der mobilen Clients Teams&mdash;, in dem Benutzer können schnell und einfach darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-132">The apps set in a policy are pinned to the app bar&mdash;the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients&mdash;where users can quickly and easily access them.</span></span> 
 
<span data-ttu-id="8f9a5-133">Teams umfasst eine integrierte FirstLineWorker app Setup-Richtlinie, die Sie in Ihrer Organisation Mitarbeiter Firstline zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-133">Teams includes a built-in FirstLineWorker app setup policy that you can assign to firstline workers in your organization.</span></span> <span data-ttu-id="8f9a5-134">Standardmäßig enthält die Richtlinie die Aktivität, Schichten, Chat und Aufrufen von apps.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-134">By default, the policy includes the Activity, Shifts, Chat, and Calling apps.</span></span> 

<span data-ttu-id="8f9a5-135">Die Richtlinie FirstLineWorker im linken Navigationsbereich von Microsoft-Teams & Skype für Business Admin Center wechseln Sie zum Anzeigen **Teams**App > **Setup Richtlinien für die App**.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-135">To view the FirstLineWorker policy, in the left navigation of the Microsoft Teams & Skype for Business Admin Center, go to **Teams app** > **App setup policies**.</span></span>

<span data-ttu-id="8f9a5-136">![Screenshot der FirstLineWorker app Setup Richtlinie in der Microsoft-Teams & Skype für Business Admin Center] (media/firstline-worker-app-setup-policy.png "Screenshot der FirstLineWorker app Setup Richtlinie in der Microsoft-Teams & Skype für Business Admin Center")</span><span class="sxs-lookup"><span data-stu-id="8f9a5-136">![Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams & Skype for Business Admin Center](media/firstline-worker-app-setup-policy.png "Screen shot of the FirstLineWorker app setup policy in the Microsoft Teams & Skype for Business Admin Center")</span></span>

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a><span data-ttu-id="8f9a5-137">Zuweisen der Richtlinie FirstLineWorker für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="8f9a5-137">Assign the FirstLineWorker policy to individual users</span></span>

1. <span data-ttu-id="8f9a5-138">Im linken Navigationsbereich von Microsoft-Teams & Skype für Business Admin Center wechseln Sie zu dem **Benutzer**, und klicken Sie dann auf Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-138">In the left navigation of the Microsoft Teams & Skype for Business Admin Center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="8f9a5-139">Neben **zugewiesene Richtlinien**wählen Sie **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-139">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="8f9a5-140">Wählen Sie unter **Teams App Setup Richtlinie** **FirstLineWorker**aus, und wählen Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-140">Under **Teams App Setup policy**, select **FirstLineWorker**, and then choose **Save**.</span></span>

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="8f9a5-141">Weisen Sie die FirstLineWorker app Setup-Richtlinie für Benutzer in einer Gruppe</span><span class="sxs-lookup"><span data-stu-id="8f9a5-141">Assign the FirstLineWorker app setup policy to users in a group</span></span>

<span data-ttu-id="8f9a5-142">Sie können die FirstLineWorker app Setup-Richtlinie für Benutzer in einer Gruppe, wie etwa einer Sicherheitsgruppe zuweisen, indem eine Verbindung mit Azure Active Directory PowerShell Graph-Modul und die Skype für Business PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-142">You can assign the FirstLineWorker app setup policy to users in a group, such as a security group, by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="8f9a5-143">Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über die PowerShell Teams](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8f9a5-143">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="8f9a5-144">In diesem Beispiel weisen wir die FirstLineWorker app Setup-Richtlinie für alle Benutzer in der Gruppe "Contoso" Firstline Team.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-144">In this example, we assign the FirstLineWorker app setup policy to all users in the Contoso Firstline Team group.</span></span>

> [!NOTE]
> <span data-ttu-id="8f9a5-145">Stellen Sie sicher, dass Sie zuerst die Azure Active Directory-PowerShell-Modul Diagramm und Skype für Business PowerShell-Modul anschließen, durch die Schritte in [Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="8f9a5-145">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="8f9a5-146">Rufen Sie die GroupObjectId bestimmten Gruppe.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-146">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
<span data-ttu-id="8f9a5-147">Rufen Sie die Mitglieder der angegebenen Gruppe.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-147">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="8f9a5-148">Weisen Sie alle Benutzer in der Gruppe der FirstLineWorker app Setup-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-148">Assign all users in the group to the FirstLineWorker app setup policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="8f9a5-149">Abhängig von der Anzahl der Elemente in der Gruppe kann dieser Befehl mehrere Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="8f9a5-149">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8f9a5-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8f9a5-150">Related topics</span></span>
- [<span data-ttu-id="8f9a5-151">Hilfe für Firstline Mitarbeiter und Manager Schichten</span><span class="sxs-lookup"><span data-stu-id="8f9a5-151">Shifts Help for firstline workers and managers</span></span>](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)