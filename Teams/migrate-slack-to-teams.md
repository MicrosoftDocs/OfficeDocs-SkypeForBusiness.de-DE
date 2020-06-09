---
title: Migrieren von Slack auf Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- NOCSH
description: Umfassender Leitfaden für das Migrieren von Slack auf Microsoft Teams.
ms.openlocfilehash: ca104baf5baebaa0e44c2202794c1b8ed6862633
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638644"
---
# <a name="migrate-from-slack-to-microsoft-teams"></a><span data-ttu-id="95f38-103">Migrieren von Slack auf Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95f38-103">Migrate from Slack to Microsoft Teams</span></span>

<span data-ttu-id="95f38-104">Dieser Artikel führt Sie durch den Weg der Umstellung von Slack auf Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="95f38-104">This article walks you through the journey of moving to Microsoft Teams from Slack.</span></span>

<span data-ttu-id="95f38-105">Bei der Planung der Umstellung Ihrer Organisation von Slack auf Teams ist es wichtig zu entscheiden, was Sie beibehalten möchten (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="95f38-105">When planning your organization’s move to Teams from Slack, it's important to decide what you need to keep (if anything).</span></span> <span data-ttu-id="95f38-106">Wir beginnen mit einer Beschreibung, welche Arten von Daten migriert werden können, und führen Sie dann durch, wie Sie Ihre Bedürfnisse einschätzen, Ihre Umstellung planen und dann den Schritt machen können.</span><span class="sxs-lookup"><span data-stu-id="95f38-106">We'll start off by describing what types of data can be migrated and then walk you through how to assess your needs, plan your move, and then make the move.</span></span>

<span data-ttu-id="95f38-107">Das nachstehende Diagramm zeigt die Architektur von Slack auf hoher Ebene.</span><span class="sxs-lookup"><span data-stu-id="95f38-107">The diagram below shows the Slack architecture at a high level.</span></span>

![Abbildung, welche die Architektur von Slack auf hoher Ebene verlangsamt](media/migrate-slack-to-teams-image1.png)

## <a name="plan-your-migration-from-slack"></a><span data-ttu-id="95f38-109">Planen Sie Ihre Migration von Slack</span><span class="sxs-lookup"><span data-stu-id="95f38-109">Plan your migration from Slack</span></span>
### <a name="what-you-can-and-cant-migrate"></a><span data-ttu-id="95f38-110">Was Sie migrieren können und was nicht</span><span class="sxs-lookup"><span data-stu-id="95f38-110">What you can and can’t migrate</span></span>
<span data-ttu-id="95f38-111">Ihr Slack-Serviceplan bestimmt, was Sie migrieren können und was nicht.</span><span class="sxs-lookup"><span data-stu-id="95f38-111">Your Slack service plan will determine what you can and can’t migrate.</span></span> <span data-ttu-id="95f38-112">Beispielsweise lassen einige Slack-Servicepläne nur das Exportieren von Verlauf und Dateien öffentlicher Kanäle zu, andere erfordern eine DocuSign-Anfrage, um private Kanäle und Direktnachrichten einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="95f38-112">For example, some Slack service plans only let you export public channels history and files, other require a DocuSign request to include Private Channels and Direct Messages.</span></span> 

<span data-ttu-id="95f38-113">Um den Servicegrad Ihres Slack-Arbeitsbereichs zu bestimmen, melden Sie sich bei Slack an und notieren Sie sich Ihren Plantyp auf der Seite **Über diesen Arbeitsbereich**.</span><span class="sxs-lookup"><span data-stu-id="95f38-113">To determine your Slack Workspace service level, log into Slack and note your plan type on the **About this Workspace** page.</span></span>

<span data-ttu-id="95f38-114">Um mehr über die Exportmöglichkeiten von Slack zu erfahren, besuchen Sie die Slack-Website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="95f38-114">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

<span data-ttu-id="95f38-115">Das folgende Diagramm gibt Ihnen einen Überblick über die Slack-Migrationslandschaft, die wir in diesem Artikel behandeln werden.</span><span class="sxs-lookup"><span data-stu-id="95f38-115">The diagram below gives you a high-level look at the Slack migration landscape that we’ll cover in this article.</span></span> 

![Diagramm, das die Slack-Migrationslandschaft anzeigt.](media/migrate-slack-to-teams-image2.png)

<span data-ttu-id="95f38-117">Folgende Begriffe sollten Sie nach Abschluss dieses Abschnitts kennen:</span><span class="sxs-lookup"><span data-stu-id="95f38-117">When you're done with this section, you should understand:</span></span>
- <span data-ttu-id="95f38-118">Der Servicegrad Ihrer Slack-Arbeitsbereiche</span><span class="sxs-lookup"><span data-stu-id="95f38-118">The service level of your Slack Workspaces</span></span>
- <span data-ttu-id="95f38-119">Was kann exportiert werden und was nicht</span><span class="sxs-lookup"><span data-stu-id="95f38-119">What can and can't be exported</span></span>
- <span data-ttu-id="95f38-120">Allgemeine Vorgehensweisen beim Exportieren</span><span class="sxs-lookup"><span data-stu-id="95f38-120">Common approaches to exporting</span></span>

### <a name="assess-your-slack-workspaces"></a><span data-ttu-id="95f38-121">Bewerten Sie Ihre Slack-Arbeitsbereiche</span><span class="sxs-lookup"><span data-stu-id="95f38-121">Assess your Slack workspaces</span></span>
<span data-ttu-id="95f38-122">Bevor Sie den Migrationsplan Ihrer Organisation planen können, müssen Sie einige Informationen über Ihre Slack-Arbeitsbereiche zusammenstellen.</span><span class="sxs-lookup"><span data-stu-id="95f38-122">Before you can plan your organization’s migration plan, you need to pull together some information about your Slack workspaces.</span></span> <span data-ttu-id="95f38-123">Wenn Sie verstehen, wie Ihre Slack-Arbeitsbereiche genutzt werden, können Sie den Umfang Ihrer Migration bestimmen.</span><span class="sxs-lookup"><span data-stu-id="95f38-123">Understanding how your Slack workspaces are being used helps you determine the scope of your migration.</span></span> <span data-ttu-id="95f38-124">Zum Beispiel, wie viele Arbeitsbereiche werden verschoben?</span><span class="sxs-lookup"><span data-stu-id="95f38-124">For example, how many workspaces are being moved?</span></span> <span data-ttu-id="95f38-125">Werden sie von einer bestimmten Abteilung, von vielen oder von einer ganzen Organisation verwendet?</span><span class="sxs-lookup"><span data-stu-id="95f38-125">Are they used by a specific department, many, or in use by an entire organization?</span></span>

<span data-ttu-id="95f38-126">Wenn Sie Mitglied der Slack-Arbeitsbereiche sind, die Sie migrieren möchten, können Sie die Nutzung selbst analysieren, indem Sie zu *<your Slack workspace>.slack.com/stats* gehen. Überprüfen Sie die Registerkarten „Kanäle“ und „Mitglieder“, um nach Nutzungsmustern zu suchen.</span><span class="sxs-lookup"><span data-stu-id="95f38-126">If you’re a member of the Slack Workspaces you want to migrate, you can analyze the usage yourself by going to *<your Slack workspace>.slack.com/stats*. Review the Channels and Members tabs to look for usage patterns.</span></span> <span data-ttu-id="95f38-127">Entscheiden Sie, welche Arbeitsbereiche Sie migrieren möchten (und welche Sie zurücklassen möchten).</span><span class="sxs-lookup"><span data-stu-id="95f38-127">Decide which workspaces you want to migrate (and which ones you want to leave behind).</span></span> 

> [!NOTE]
> <span data-ttu-id="95f38-128">Wenn Sie keinen Zugriff auf die Seite „Statistiken“ haben, sind Sie kein Administrator oder Besitzer.</span><span class="sxs-lookup"><span data-stu-id="95f38-128">If you don’t have access to the stats page, you’re not an admin or owner.</span></span> 

### <a name="export-channels"></a><span data-ttu-id="95f38-129">Exportieren von Kanälen</span><span class="sxs-lookup"><span data-stu-id="95f38-129">Export Channels</span></span>

<span data-ttu-id="95f38-130">In Slack treten Benutzer einem Kanal bei, der Teil eines Slack-Arbeitsbereichs ist, während in Teams Benutzer einem Team beitreten, das eine Sammlung von Kanälen ist.</span><span class="sxs-lookup"><span data-stu-id="95f38-130">In Slack, users join a channel which is part of a Slack Workspace, whereas in Teams users join a team which is a collection of channels.</span></span> <span data-ttu-id="95f38-131">Wir empfehlen, dass Sie die Slack-Analyse verwenden, um zu sehen, wie viel Aktivität in jedem Kanal stattfindet, damit Sie entscheiden können, welche Kanäle Sie verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="95f38-131">We recommend that you use Slack analytics to see how much activity happens in each channel to help you decide which channels to move.</span></span> <span data-ttu-id="95f38-132">Anhand der Ergebnisliste können Sie herausfinden, wie Sie Ihre Slack-Kanäle zu Teams in Teams gruppieren und wer Mitglied in jedem Team sein sollte.</span><span class="sxs-lookup"><span data-stu-id="95f38-132">You’ll use the resulting list to figure out how to group your Slack channels into teams in Teams as well as who should be members of each team.</span></span>

<span data-ttu-id="95f38-133">Wenn Sie einen kostenpflichtigen Slack-Serviceplan haben (alles andere als kostenlos), können Sie die Analysefunktionen von Slack (<your Slack workspace>.slack.com/admin/stats#channels) verwenden, um zu sehen, wie aktiv ein Kanal ist, wann er zuletzt genutzt wurde und wie viele Personen Mitglieder sind.</span><span class="sxs-lookup"><span data-stu-id="95f38-133">If you have a paid Slack service plan (anything other than Free), you can use Slack’s analytics (<your Slack workspace>.slack.com/admin/stats#channels) to see how active a channel is, when it was last used, and how many people are members.</span></span> <span data-ttu-id="95f38-134">Dies kann Ihnen bei der Entscheidung helfen, ob Sie den Kanal migrieren möchten oder nicht.</span><span class="sxs-lookup"><span data-stu-id="95f38-134">This can help you decide whether to migrate the channel.</span></span> <span data-ttu-id="95f38-135">Standardmäßig können Inhalte öffentlicher Kanäle (Nachrichten und Dateien) exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="95f38-135">By default, public channels content (messages and files) can be exported.</span></span> <span data-ttu-id="95f38-136">Abhängig von Ihrem Slack-Serviceplan und ob Sie private Kanäle und Direktnachrichten von Slack angefordert haben, können diese exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="95f38-136">Depending on your Slack service plan and whether you’ve requested Private Channels and Direct Messages from Slack, those can be exported.</span></span>

<span data-ttu-id="95f38-137">Um mehr über die Exportmöglichkeiten von Slack zu erfahren, besuchen Sie die Slack-Website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span><span class="sxs-lookup"><span data-stu-id="95f38-137">To learn more about Slack export options, go to the Slack website: https://get.slack.help/hc/articles/204897248-Guide-to-Slack-import-and-export-tools</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="95f38-138">Überprüfen Sie die Datenschutz- und Compliance-Anforderungen Ihrer Organisation um Kanaldaten.</span><span class="sxs-lookup"><span data-stu-id="95f38-138">Check your organization’s privacy and compliance requirements around channel data.</span></span> <span data-ttu-id="95f38-139">Ihre Organisation hat möglicherweise Compliance-Anforderungen in Bezug auf die Handhabung, Speicherung und Verarbeitung dieser Daten sowie die Einhaltung des Lebenszyklus von Endbenutzer identifizierbaren Inhalten (EUII).</span><span class="sxs-lookup"><span data-stu-id="95f38-139">Your organization may have compliance requirements around the handling, storage, and processing of this data, in addition to complying with the lifecycle of end-user identifiable content (EUII).</span></span>

### <a name="export-direct-messages"></a><span data-ttu-id="95f38-140">Exportieren von Direktnachrichten</span><span class="sxs-lookup"><span data-stu-id="95f38-140">Export Direct Messages</span></span>
<span data-ttu-id="95f38-141">Direktnachrichten sind die gleichen wie Chats in Teams, die Nicht-Kanalunterhaltungen sind, entweder 1:1 oder 1-zu-viele.</span><span class="sxs-lookup"><span data-stu-id="95f38-141">Direct Messages are the same as chats in Teams, which are 1:1 or 1-to-many non-channel conversations.</span></span> <span data-ttu-id="95f38-142">Die Exportfähigkeit hängt von Ihrem Slack-Serviceplan ab und davon, ob Sie die Aufnahme von Direktnachrichten in Ihren Slack-Export angefordert haben.</span><span class="sxs-lookup"><span data-stu-id="95f38-142">Export-ability depends on your Slack service plan and if you’ve requested Direct Messages to be included in your Slack Export.</span></span> <span data-ttu-id="95f38-143">Teams unterstützt das Importieren von Direktnachrichten zurzeit nicht.</span><span class="sxs-lookup"><span data-stu-id="95f38-143">Teams doesn’t support importing Direct messages currently.</span></span> <span data-ttu-id="95f38-144">Wenden Sie sich an einen Microsoft-Partner, um mehr über Lösungen von Drittanbietern zu erfahren, die Sie ausprobieren können, die Inhalte von Direktnachrichten in Teams integrieren.</span><span class="sxs-lookup"><span data-stu-id="95f38-144">Consult a Microsoft partner to learn about third-party solutions you can explore that bring Direct Messages content into Teams.</span></span>

<span data-ttu-id="95f38-145">Für das Exportieren von Direktnachrichten können Sie im Slack App Store Tools, wie z. B. Export, ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="95f38-145">For exporting Direct Messages, check out tools, such as Export, in the Slack App Store.</span></span>

### <a name="apps-and-custom-integrations"></a><span data-ttu-id="95f38-146">Apps und benutzerdefinierte Integrationen</span><span class="sxs-lookup"><span data-stu-id="95f38-146">Apps and custom integrations</span></span>

<span data-ttu-id="95f38-147">Apps in Slack sind wie Apps in Teams.</span><span class="sxs-lookup"><span data-stu-id="95f38-147">Apps in Slack are like apps in Teams.</span></span> <span data-ttu-id="95f38-148">Sobald Sie eine Liste von Apps und deren Konfigurationen im Arbeitsbereich haben, können Sie im Team App Store nachsehen, ob sie für Teams\* verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="95f38-148">Once you have a list of apps and their configurations in the Workspace, you can search in the Teams App store to see if they’re available for Teams\*.</span></span> 

<span data-ttu-id="95f38-149">Besuchen Sie <your Slack workspace>.slack.com/apps/manage, um eine Liste der Apps und benutzerdefinierten Integrationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="95f38-149">Go to <your Slack workspace>.slack.com/apps/manage to get a list of Apps and Custom Integrations.</span></span> <span data-ttu-id="95f38-150">Diese Seite zeigt Ihnen auch die Anzahl der Konfigurationen, in denen jede App verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95f38-150">This page also shows you the number of configurations where each app is in use.</span></span> <span data-ttu-id="95f38-151">Benutzerdefinierte Integrationen unterscheiden sich in ihrer „Migrationsfähigkeit“.</span><span class="sxs-lookup"><span data-stu-id="95f38-151">Custom Integrations vary in their “migrate-ability.”</span></span> <span data-ttu-id="95f38-152">Wenn es sich um einen Webhook handelt, können Sie ihn normalerweise an einen Microsoft 365- oder Office 365-Connector senden, um den Workflow in Teams zu überführen.</span><span class="sxs-lookup"><span data-stu-id="95f38-152">If it’s a Web Hook, you can usually send it to a Microsoft 365 or Office 365 Connector to shift the workflow into Teams.</span></span> <span data-ttu-id="95f38-153">Bewerten Sie Bots und andere Apps von Fall zu Fall, um sie in Teams zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="95f38-153">Assess bots and other apps on a case-by-case basis to plan for moving them to Teams.</span></span>

<span data-ttu-id="95f38-154">\* Wenn Ihr Administrator die Nutzung von Apps eingeschränkt hat, werden Sie möglicherweise nicht die vollständige Liste der verfügbaren Apps sehen.</span><span class="sxs-lookup"><span data-stu-id="95f38-154">\* If your administrator has restricted apps usage, you may not be looking at the full list of available apps.</span></span>

### <a name="users"></a><span data-ttu-id="95f38-155">Benutzer</span><span class="sxs-lookup"><span data-stu-id="95f38-155">Users</span></span>
<span data-ttu-id="95f38-156">Die Identitätsschemas, die Sie in Slack verwendet haben, werden möglicherweise nicht direkt zu Microsoft 365 oder Office 365 zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="95f38-156">The identity schemes you used in Slack might not map directly to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="95f38-157">So können beispielsweise die E-Mail-Adressen Ihrer Slack-Benutzer nicht zu den Geschäfts-, Schul oder Unikonten von Microsoft 365 oder Office 365 zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="95f38-157">For example, the email addresses of your Slack users may not map to Microsoft 365 or Office 365 work or school accounts.</span></span> <span data-ttu-id="95f38-158">Sie sollten eine Benutzer-ID-Zuordnung erstellen, bevor Sie mit der Planung des Rollouts Ihres Teams beginnen.</span><span class="sxs-lookup"><span data-stu-id="95f38-158">You should create a user-ID map before you start planning your Teams rollout.</span></span>

<span data-ttu-id="95f38-159">Wenn Sie einen kostenpflichtigen Slack-Serviceplan haben, besuchen Sie *<your Slack workspace>.slack.com/admin/stats#members*, um Mitgliederdaten wie E-Mail-Adresse und Kontotyp für jeden Benutzer (z. B. Einzel- oder Mehrkanalgast) zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="95f38-159">If you’re on a paid Slack service plan, you can go to *<your Slack workspace>.slack.com/admin/stats#members* to get member details such as email address and account type for each user (for example, single vs. multi-channel guest).</span></span>

<span data-ttu-id="95f38-160">Hier ist ein Skript, mit dem Sie E-Mail-Adressen aus einem Slack-Export mit Azure AD vergleichen können, um die Mehrdeutigkeit von Namen zu lösen.</span><span class="sxs-lookup"><span data-stu-id="95f38-160">Here’s a script you can use to compare email addresses from a Slack export against Azure AD to help solve for name ambiguity.</span></span> <span data-ttu-id="95f38-161">Es wird auch angezeigt, ob der Benutzer für Teams aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="95f38-161">It’ll also report if the user is enabled for Teams.</span></span> <span data-ttu-id="95f38-162">Wenn Sie Hilfe zu PowerShell benötigen, lesen Sie [Erste Schritte mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="95f38-162">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>

```azurepowershell
Connect-AzureAD
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class User {
    [ValidateNotNullOrEmpty()] $ID
    [ValidateNotNullOrEmpty()] $FullName
    [string] $Email
    [string] $UPN
    [ValidateNotNullOrEmpty()][bool] $ExistsAzureAD
    [ValidateNotNullOrEmpty()][bool] $TeamsEnabled
}

$output = New-Object -type System.Collections.ObjectModel.Collection["User"]

$users = Get-Content -Raw -Path .\slackHistory\users.json | ConvertFrom-Json

Write-Host -ForegroundColor Green "$(Get-Timestamp) User Count: " $users.Count

$i=1
Write-Host "$(Get-Timestamp) Attempting direct email match.. `n"
foreach ($slackUser in $users) {
    $user = New-Object User
    $user.id = $slackUser.id
    $user.FullName = $slackUser.name
    try {
        if ($null -ne $slackUser.profile.email) {
            $user.email = $slackUser.profile.email
            $emailSplit = $slackUser.profile.email.Split('@')
            $mailNickName = $emailSplit[0]
            $result = Get-AzureADUser -Filter "MailNickName eq '$($mailNickName)' or UserPrincipalName eq '$($slackUser.profile.email)' or proxyAddresses/any(c:c eq 'smtp:$($slackUser.profile.email)')"
            if ($null -ne $result) {
                $user.ExistsAzureAD = $true
                $user.UPN = $result.UserPrincipalName
                $assignedPlans = $result.assignedPlans
                foreach ($plan in $assignedPlans) {
                    if ($plan.ServicePlanId -eq "57ff2da0-773e-42df-b2af-ffb7a2317929") {
                        if ($plan.CapabilityStatus -eq "Enabled") {
                            $user.TeamsEnabled = $true
                        }
                        else {
                            $user.TeamsEnabled = $false
                        }
                    }
                }
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - AzureAD object found:" $result.MailNickName
                Write-Host -ForegroundColor Green "$(Get-Timestamp) Current User $($i) - Teams Enabled:" $user.TeamsEnabled
            }
            else {
                $user.ExistsAzureAD = $false
                Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: " $slackUser.profile.email
            }
        }
        $i++
    }   
    catch
    {
        $user.ExistsAzureAD = $false
        Write-Host -ForegroundColor Yellow "$(Get-Timestamp) Current User $($i) - AzureAD object not found: $($i)" $user.profile.email
        $i++
    }
    $output.Add($user)
}

$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
$output | Export-Csv -Path .\SlackToAzureADIdentityMapping.csv -NoTypeInformation
Write-Host "`n $(Get-Timestamp) Generated SlackToAzureADIdentityMapping.csv. Exiting..."
```

<span data-ttu-id="95f38-163">Folgendes sollten Sie nach Abschluss dieses Abschnitts haben:</span><span class="sxs-lookup"><span data-stu-id="95f38-163">When you’re done with this section, you should have:</span></span>
- <span data-ttu-id="95f38-164">Eine Liste der Kanäle pro Arbeitsbereich mit Nutzungsstatistiken.</span><span class="sxs-lookup"><span data-stu-id="95f38-164">A list of Channels per Workspace with usage statistics.</span></span>
- <span data-ttu-id="95f38-165">Eine Liste der Slack-Apps mit Konfigurationen pro Kanal.</span><span class="sxs-lookup"><span data-stu-id="95f38-165">A list of Slack Apps with configurations per channel.</span></span>
- <span data-ttu-id="95f38-166">Bestimmt, welche Art von Slack-Nachrichtenverlauf Sie exportieren möchten (sofern vorhanden).</span><span class="sxs-lookup"><span data-stu-id="95f38-166">Determined what type of Slack message history you want to export (if any).</span></span>
- <span data-ttu-id="95f38-167">Eine Liste von Benutzern, deren Slack-Konten den Arbeits- oder Schulkonten von Microsoft zugeordnet sind und welche Teams-Lizenz sie haben.</span><span class="sxs-lookup"><span data-stu-id="95f38-167">A list of users whose Slack accounts map to Microsoft work or school accounts and which Teams license they have.</span></span>

## <a name="plan-your-teams-deployment"></a><span data-ttu-id="95f38-168">Planen Ihrer Teams-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="95f38-168">Plan your Teams deployment</span></span>
<span data-ttu-id="95f38-169">Sie haben das, was Sie benötigen, aus Slack exportiert (und alles zurückgelassen, was Sie nicht benötigen).</span><span class="sxs-lookup"><span data-stu-id="95f38-169">You’ve exported what you need from Slack (and left behind anything you don’t need).</span></span> <span data-ttu-id="95f38-170">Jetzt ist es an der Zeit das Rollout von Teams zu planen und Ihre Slack-Daten zu importieren.</span><span class="sxs-lookup"><span data-stu-id="95f38-170">Now it’s time to plan how you’ll roll out Teams and import your Slack data.</span></span> <span data-ttu-id="95f38-171">Dies ist eine großartige Gelegenheit, um zu beurteilen, was für das Team auf der Grundlage der Nutzung gut funktioniert hat, und diese Elemente in Ihrer Teams-Bereitstellungsplanung aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="95f38-171">This is a great opportunity to assess what's worked well for the team based on usage and include those elements in your Teams deployment plan.</span></span> <span data-ttu-id="95f38-172">Am Ende dieses Abschnitts finden Sie eine Blaupause für die Benutzer, Kanäle und Apps Ihres Teams.</span><span class="sxs-lookup"><span data-stu-id="95f38-172">At the end of this section, you’ll have a blueprint for your Teams users, channels, and apps.</span></span> 

<span data-ttu-id="95f38-173">Das folgende Diagramm gibt Ihnen einen Überblick über die Elemente, die Sie in Ihrer Teams-Bereitstellung ansprechen werden.</span><span class="sxs-lookup"><span data-stu-id="95f38-173">The diagram below gives you a high-level outline of the things you’ll address in your Teams deployment.</span></span>

:::image type="content" source="media/migrate-slack-to-teams-image3.png" alt-text="Allgemeine Übersicht über die Planung der Bereitstellung von Teams aus Slack.":::

### <a name="team-and-channel-structure"></a><span data-ttu-id="95f38-175">Team- und Kanalstruktur</span><span class="sxs-lookup"><span data-stu-id="95f38-175">Team and channel structure</span></span>

<span data-ttu-id="95f38-176">Ein Slack-Arbeitsbereich kann ein einzelnes Team, mehrere Teams oder eine ganze Organisation sein.</span><span class="sxs-lookup"><span data-stu-id="95f38-176">A Slack Workspace may represent a single team, multiple teams or an entire organization.</span></span> <span data-ttu-id="95f38-177">Es ist wichtig, den Umfang der Arbeitsbereiche zu kennen, wenn Sie die Struktur bestimmen.</span><span class="sxs-lookup"><span data-stu-id="95f38-177">It’s important to understand the scope of the Workspaces as you determine the structure.</span></span> <span data-ttu-id="95f38-178">Die engste Beziehung zu einem Teams-Team in Slack ist der Arbeitsbereich, der eine Sammlung von Kanälen enthält.</span><span class="sxs-lookup"><span data-stu-id="95f38-178">The closest relationship to a Teams team in Slack is the Workspace, which contains a collection of channels.</span></span> <span data-ttu-id="95f38-179">Das folgende Diagramm zeigt 3 verschiedene Slack-to-Teams-Zuordnungen und eine Anleitung zur Auswahl der richtigen für jeden Arbeitsbereich.</span><span class="sxs-lookup"><span data-stu-id="95f38-179">The diagram below demonstrates 3 different Slack-to-Teams mappings, and guidance for picking the right one for each Workspace.</span></span>


|<span data-ttu-id="95f38-180">Slack-to-Teams-Zuordnung</span><span class="sxs-lookup"><span data-stu-id="95f38-180">Slack-to-Teams mapping</span></span> |  |
|---------|---------|
|<span data-ttu-id="95f38-181">1 Slack-Arbeitsbereich: arrow_right: 1 Team</span><span class="sxs-lookup"><span data-stu-id="95f38-181">1 Slack Workspace :arrow_right: 1 team</span></span>   | <span data-ttu-id="95f38-182">Für kleinere Slack-Arbeitsbereiche, die weniger als 200 Kanäle benötigen</span><span class="sxs-lookup"><span data-stu-id="95f38-182">For smaller Slack workspaces that need fewer than 200 channels</span></span><br><span data-ttu-id="95f38-183">Binden Sie einen Puffer für Wachstum und private Kanalplanung ein</span><span class="sxs-lookup"><span data-stu-id="95f38-183">Include a buffer for growth and private channel planning</span></span>  |
|<span data-ttu-id="95f38-184">1 Slack-Arbeitsbereich: arrow_right: mehrere Teams</span><span class="sxs-lookup"><span data-stu-id="95f38-184">1 Slack Workspace :arrow_right: multiple teams</span></span>     | <span data-ttu-id="95f38-185">Verwenden Sie die Analysedaten Ihres Slack-Arbeitsbereichs, um logische Kanalgruppierungen zu erstellen, welche die Grundlage für Ihre Teams bilden.</span><span class="sxs-lookup"><span data-stu-id="95f38-185">Use your Slack Workspace analytics data to create logical channel groupings, which become the basis of your teams</span></span>        |
|<span data-ttu-id="95f38-186">Mehr als 2 Slack-Arbeitsbereiche: arrow_right: mehrere Teams</span><span class="sxs-lookup"><span data-stu-id="95f38-186">2+ Slack Workspaces :arrow_right: multiple teams</span></span>     | <span data-ttu-id="95f38-187">Verwenden Sie die Analysedaten Ihres Slack-Arbeitsbereichs, um logische Team- und Kanalgruppierungen zu erstellen, welche die Grundlage für Ihre Teams bilden.</span><span class="sxs-lookup"><span data-stu-id="95f38-187">Use your Slack Workspace analytics data to create logical team and channel groupings, which become the basis of your teams</span></span>        |

<span data-ttu-id="95f38-188">Lösungen von Drittanbietern verfügen über Nutzungsstatistiken, die Ihnen helfen zu beurteilen, wie aktiv der Kanal ist und wie viele Beiträge es gibt.</span><span class="sxs-lookup"><span data-stu-id="95f38-188">Third-party solutions have usage statistics to help you assess how active the channel is and how many posts there are.</span></span> <span data-ttu-id="95f38-189">Typischerweise sind häufig genutzte Kanäle die geeigneten Kandidaten, um sie in Ihre Teamplanung einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="95f38-189">Typically, channels that are frequently used would be candidates to include in your team planning.</span></span>

> [!TIP]
> <span data-ttu-id="95f38-190">Behalten Sie nur das, was in Ihrem Ansatz erforderlich ist, um zu bestimmen, welche Kanäle in Teams wiederhergestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="95f38-190">Retain only what is required in your approach to determine which channels to recreate in Teams.</span></span> <span data-ttu-id="95f38-191">Weitere Informationen finden Sie unter [Übersicht über Teams und Kanäle](teams-channels-overview.md).</span><span class="sxs-lookup"><span data-stu-id="95f38-191">To learn more, read [Overview of teams and channels](teams-channels-overview.md).</span></span> 

#### <a name="team-planning"></a><span data-ttu-id="95f38-192">Teamplanung</span><span class="sxs-lookup"><span data-stu-id="95f38-192">Team Planning</span></span>
<span data-ttu-id="95f38-193">Verwenden Sie das Kanalinventar, das Sie im Abschnitt „Planung“ oben zusammengestellt haben, und arbeiten Sie mit Ihren Slack-Besitzern und Administratoren zusammen, um herauszufinden, welche Kanäle zu Teams werden sollen und welche zu Kanälen in einem Team werden sollen.</span><span class="sxs-lookup"><span data-stu-id="95f38-193">Using the Channel inventory you compiled in the Planning section above, work with your Slack owners and admins to figure out which channels should become teams and which ones should become channels in a team.</span></span> <span data-ttu-id="95f38-194">Verwenden Sie entweder Excel oder PowerBI, um bei dieser Analyse zu helfen – beide können zusätzliche Erkenntnisse liefern, um diese Diskussionen darüber anzuregen, welche Kanäle beibehalten werden sollen.</span><span class="sxs-lookup"><span data-stu-id="95f38-194">Use either Excel or PowerBI to help with this analysis - both can provide additional insights to help drive these discussions on which channels to retain.</span></span>

> [!TIP]
> <span data-ttu-id="95f38-195">Teams hat derzeit ein 200-Kanal-Limit pro Team.</span><span class="sxs-lookup"><span data-stu-id="95f38-195">Teams currently has a 200-channel limit per team.</span></span> <span data-ttu-id="95f38-196">Wenn Ihre Liste der Kanäle sich diesem Limit nähert, sollten Sie einen Weg finden, sie in zwei getrennte Teams aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="95f38-196">If your list of channels is getting close to that limit, you should figure out a way to split them into two separate teams.</span></span>

### <a name="channel-history"></a><span data-ttu-id="95f38-197">Kanalhistorie</span><span class="sxs-lookup"><span data-stu-id="95f38-197">Channel History</span></span>

<span data-ttu-id="95f38-198">Es gibt sowohl kostenlose Lösungen auf GitHub als auch kostenpflichtige Lösungen, die Sie verwenden können, je nach den Anforderungen Ihrer Organisation, um die Kanalhistorie der öffentlichen und privaten Kanäle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="95f38-198">There are both free solutions on GitHub and paid solutions you can use, depending on your organization’s requirements to retain Channel History of Public and Private channels.</span></span> <span data-ttu-id="95f38-199">Außerdem könnte dies in Teams geskriptet werden.</span><span class="sxs-lookup"><span data-stu-id="95f38-199">Additionally, this could be scripted into Teams.</span></span>

<span data-ttu-id="95f38-200">Nachdem Sie Ihre neue Team- und Kanalstruktur in Teams eingerichtet haben, können Sie die exportierten Dateien in die entsprechenden Dokumentenbibliotheken in Ihren Teams-Kanälen kopieren.</span><span class="sxs-lookup"><span data-stu-id="95f38-200">Once you’ve set up your new team and channel structure in Teams, you can copy the exported files into the appropriate document libraries in your Teams channels.</span></span>

<span data-ttu-id="95f38-201">Um das Importieren Ihrer Inhalte zu automatisieren, gibt es mehrere Ansätze, die Sie in Betracht ziehen können.</span><span class="sxs-lookup"><span data-stu-id="95f38-201">To automate the importing of your content, there are several approaches you can consider.</span></span> <span data-ttu-id="95f38-202">Es gibt ﻿kostenlose Lösungen auf GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) oder [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) und Partnerlösungen.</span><span class="sxs-lookup"><span data-stu-id="95f38-202">There are  free solutions on GitHub ([ChannelSurf](https://github.com/tamhinsf/ChannelSurf) or [Slack Export Viewer](https://github.com/hfaran/slack-export-viewer)) and partner solutions.</span></span> <span data-ttu-id="95f38-203">Wählen Sie eine Lösung, die auf den Anforderungen Ihrer Organisation basiert.</span><span class="sxs-lookup"><span data-stu-id="95f38-203">Choose a solution based on your organization’s needs.</span></span> 

### <a name="channel-files"></a><span data-ttu-id="95f38-204">Kanaldateien</span><span class="sxs-lookup"><span data-stu-id="95f38-204">Channel Files</span></span>

<span data-ttu-id="95f38-205">Die meisten Lösungen exportieren Dateien.</span><span class="sxs-lookup"><span data-stu-id="95f38-205">Most solutions will export files.</span></span> <span data-ttu-id="95f38-206">Sie werden jedoch in der Regel als Links in der Kanalhistorie bereitgestellt, die einen API-Schlüssel zum programmgesteuerten Abrufen erfordern.</span><span class="sxs-lookup"><span data-stu-id="95f38-206">However, they’re typically provided as links in the Channel History that require an API key to programmatically retrieve.</span></span>

<span data-ttu-id="95f38-207">Für Dateien, die in Slack gespeichert sind, können Sie, nachdem Sie Ihre Teams und Kanäle in Teams eingerichtet haben, diese programmgesteuert aus Slack in den Zielkanal von Teams kopieren.</span><span class="sxs-lookup"><span data-stu-id="95f38-207">For files stored in Slack, once you’ve set up your teams and channels in Teams, you can programmatically copy them from Slack into the target Teams channel.</span></span>

<span data-ttu-id="95f38-208">Das folgende Skript ruft Dateien aus Slack ab.</span><span class="sxs-lookup"><span data-stu-id="95f38-208">The following script retrieves files from Slack.</span></span> <span data-ttu-id="95f38-209">Es durchsucht den angegebenen Slack-Export auf Ihrem Computer, erstellt einen Ordner in jedem Zielkanal und lädt alle Dateien an diesen Ort herunter.</span><span class="sxs-lookup"><span data-stu-id="95f38-209">It searches the specified Slack export on your computer, creates a folder in each target channel, and downloads all of the files to that location.</span></span> <span data-ttu-id="95f38-210">Es gibt Lösungen von Drittanbietern, die Daten extrahieren können.</span><span class="sxs-lookup"><span data-stu-id="95f38-210">Third-party solutions exist that can extract data.</span></span> <span data-ttu-id="95f38-211">Wenn Sie Hilfe zu PowerShell benötigen, lesen Sie [Erste Schritte mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span><span class="sxs-lookup"><span data-stu-id="95f38-211">If you need help with PowerShell, read [Get started with Azure PowerShell](https://docs.microsoft.com/powershell/azure/get-started-azureps).</span></span>



```azurepowershell
$ExportPath = ".\slackHistory"
$ExportContents = Get-ChildItem -path $ExportPath -Recurse
Function Get-TimeStamp {
    return "[{0:MM/dd/yy} {0:HH:mm:ss}]" -f (Get-Date)
}

class File {
    [string] $Name
    [string] $Title
    [string] $Channel
    [string] $DownloadURL
    [string] $MimeType
    [double] $Size
    [string] $ParentPath
    [string] $Time
}

$channelList = Get-Content -Raw -Path .\slackHistory\channels.json | ConvertFrom-Json
$Files = New-Object -TypeName System.Collections.ObjectModel.Collection["File"]

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting Step 1 (processing channel export for files) of 2. Total Channel Count: $($channelList.Count)"
#Iterate through each Channel listed in the Archive
foreach ($channel in $channelList) {
    #Iterate through Channel folders from the Export
    foreach ($folder in $ExportContents)
    {
        #If Channel Name matches..
        if ($channel.name -eq $folder){
            $channelJsons = Get-ChildItem -Path $folder.FullName -File
            Write-Host -ForegroundColor White "$(Get-TimeStamp) Info: Starting to process $($channelJsons.Count) days of content for #$($channel.name)."
            #Start processing the daily JSON for files
            foreach ($json in $channelJsons){
                $currentJson = Get-Content -Raw -Path $json.FullName | ConvertFrom-Json
                #Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Info: Processing $($json.Name) in #$($channel.name).."
                #Iterate through every action
                foreach ($entry in $currentJson){
                    #If the action contained file(s)..
                    if($null -ne $entry.files){
                        #Iterate through each file and add it to the List of Files to download
                        foreach ($item in $entry.Files) {
                        $file = New-Object -TypeName File
                            if ($null -ne $item.url_private_download){
                                $file.Name = $item.name
                                $file.Title = $item.Title
                                $file.Channel = $channel.name
                                $file.DownloadURL = $item.url_private_download
                                $file.MimeType = $item.mimetype
                                $file.Size = $item.size
                                $file.ParentPath = $folder.FullName
                                $file.Time = $item.created
                                $files.Add($file)
                            }
                        }
                    }
                }
            }
        }
    }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 1 of 2 complete. `n"

Write-Host -ForegroundColor Green "$(Get-TimeStamp) Starting step 2 (creating folders and downloading files) of 2."
#Determine which Files folders need to be created
$FoldersToMake = New-Object System.Collections.ObjectModel.Collection["string"]
foreach ($file in $files){
    if ($FoldersToMake -notcontains $file.Channel){
        $FoldersToMake.Add($file.Channel)
    }
}

#Create Folders
foreach ($folder in $FoldersToMake){
    #$fullFolderPath = $file.ParentPath + "\Files"
    $fullFolderPath = $ExportPath +"\$($folder)"
    $fullFilesPath = $ExportPath +"\$($folder)\Files"
    if (-not (Test-Path $fullFilesPath)){
        New-Item -Path $fullFolderPath  -Name "Files" -ItemType "directory"
    }
}

#Downloading Files
foreach ($file in $files)
{
    Write-Host -ForegroundColor Yellow "$(Get-TimeStamp) Downloading $($file.Name)."
    $fullFilePath = $file.ParentPath + "\Files\" + $file.Name
        if (-not (Test-Path $fullFilePath)){
            try{
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
        else {
            try{
                $extensionPosition = $file.name.LastIndexOf('.')
                $splitFileName = $file.name.Substring(0,$extensionPosition)
                $splitFileExtention = $file.name.Substring($extensionPosition)
                $newFileName = $splitFileName + $file.Time + $splitFileExtention
                $fullFilePath = $file.ParentPath + "\Files\" + $newFileName
                $request = (New-Object System.Net.WebClient).DownloadFile($file.DownloadURL, $fullFilePath)
            }
            catch [System.Net.WebException]{
                Write-Host -ForegroundColor Red "$(Get-TimeStamp) Error: Unable to download $($file.Name) to $($fullFilePath)"
            }   
        }
}
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Step 2 of 2 complete. `n"
Write-Host -ForegroundColor Green "$(Get-TimeStamp) Exiting.."
```


### <a name="apps-and-custom-integrations"></a><span data-ttu-id="95f38-212">Apps und benutzerdefinierte Integrationen</span><span class="sxs-lookup"><span data-stu-id="95f38-212">Apps and Custom Integrations</span></span>
<span data-ttu-id="95f38-213">Überprüfen Sie Ihre Liste der Slack-Apps und benutzerdefinierten Integrationen (mit Konfigurationen) und entscheiden Sie, welche Sie in Teams verschieben möchten.</span><span class="sxs-lookup"><span data-stu-id="95f38-213">Review your list of Slack apps and custom integrations (with configurations) and decide which ones you want to move to Teams.</span></span> <span data-ttu-id="95f38-214">Schauen Sie auf den Teams Marketplace, um zu sehen, ob eine App verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="95f38-214">Check the Teams Marketplace to see if an app is available.</span></span> <span data-ttu-id="95f38-215">Ist das nicht der Fall, gibt es wahrscheinlich Alternativen.</span><span class="sxs-lookup"><span data-stu-id="95f38-215">If not, there are likely alternatives.</span></span> 

<span data-ttu-id="95f38-216">Um herauszufinden, welche Apps zu Teams hinzugefügt werden sollen, ist es wichtig zu verstehen, wie die App verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="95f38-216">To figure out which apps to add to Teams, it’s important to understand how the app is being used.</span></span> <span data-ttu-id="95f38-217">Wenn Sie die Frage stellen: „Welche Funktionalität bietet die App für diesen Kanal?“, erfahren Sie mehr über das Ergebnis, das die App liefert.</span><span class="sxs-lookup"><span data-stu-id="95f38-217">By asking the question "what functionality is the app providing to this channel?", you'll learn about the outcome the app is delivering.</span></span> 

<span data-ttu-id="95f38-218">In vielen Fällen empfangen Apps in erster Linie ereignisgesteuerte Daten von einem externen Dienst (z. B. Überwachungssystem) und schieben eine Nachricht in den Slack.</span><span class="sxs-lookup"><span data-stu-id="95f38-218">In many cases, apps primarily receive event-driven data from an external service (for example, monitoring system) and push a message into Slack.</span></span> <span data-ttu-id="95f38-219">Sie können das gleiche Ergebnis erzielen, indem Sie einen Microsoft 365-Connector verwenden, der Nachrichten basierend auf Ereignissen in Teams verschieben kann.</span><span class="sxs-lookup"><span data-stu-id="95f38-219">You can achieve the same outcome by using a Microsoft 365 Connector that can push messages into Teams based on events.</span></span>

<span data-ttu-id="95f38-220">Nachfolgend finden Sie Beispiele für Slack-Lösungen, bei denen in Teams ein Microsoft 365-Connector zur Integration verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="95f38-220">Below are examples of Slack solutions where a Microsoft 365 Connector was used in Teams for integration.</span></span>
- <span data-ttu-id="95f38-221">Ansible</span><span class="sxs-lookup"><span data-stu-id="95f38-221">Ansible</span></span>
  - <span data-ttu-id="95f38-222">Benachrichtigungen können über [Ansible-Webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook) an Teams gesendet werden</span><span class="sxs-lookup"><span data-stu-id="95f38-222">Alerts can be sent to Teams via [Ansible webhook](https://docs.ansible.com/ansible-tower/latest/html/userguide/notifications.html#webhook)</span></span>
- <span data-ttu-id="95f38-223">New Relic</span><span class="sxs-lookup"><span data-stu-id="95f38-223">New Relic</span></span>
  - <span data-ttu-id="95f38-224">Sehen Sie sich diese Benutzerlösung an, um [New Relic-Benachrichtigungen an Teams zu senden](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span><span class="sxs-lookup"><span data-stu-id="95f38-224">Check out this user solution for [sending New Relic alerts to Teams](https://discuss.newrelic.com/t/new-relic-alerts-not-working-with-microsoft-teams/48609/3)</span></span>
- <span data-ttu-id="95f38-225">Nagios</span><span class="sxs-lookup"><span data-stu-id="95f38-225">Nagios</span></span>
  - <span data-ttu-id="95f38-226">Benachrichtigungen können heute über Connectors integriert werden.</span><span class="sxs-lookup"><span data-stu-id="95f38-226">Alerts can be integrated today via Connectors.</span></span> <span data-ttu-id="95f38-227">https://github.com/isaac-galvan/nagios-teams-notify</span><span class="sxs-lookup"><span data-stu-id="95f38-227">https://github.com/isaac-galvan/nagios-teams-notify</span></span>
- <span data-ttu-id="95f38-228">ZenDesk</span><span class="sxs-lookup"><span data-stu-id="95f38-228">ZenDesk</span></span>
  - <span data-ttu-id="95f38-229">Die App ist im Teams Store vorhanden</span><span class="sxs-lookup"><span data-stu-id="95f38-229">App exists in Teams Store</span></span>
- <span data-ttu-id="95f38-230">Jenkins</span><span class="sxs-lookup"><span data-stu-id="95f38-230">Jenkins</span></span>
  - <span data-ttu-id="95f38-231">Benachrichtigungen können über [Office 365-Connector von Jenkins](https://plugins.jenkins.io/Office-365-Connector) an Teams gesendet werden</span><span class="sxs-lookup"><span data-stu-id="95f38-231">Alerts can be sent to Teams using [Jenkins’s Office 365 Connector](https://plugins.jenkins.io/Office-365-Connector)</span></span>


### <a name="user-readiness-and-adoption-plan"></a><span data-ttu-id="95f38-232">Benutzerbereitschaft und Übernahmeplan</span><span class="sxs-lookup"><span data-stu-id="95f38-232">User readiness and adoption plan</span></span>
<span data-ttu-id="95f38-233">Der Grundstein für eine erfolgreiche Softwarebereitstellung hängt davon ab, wie gut die Benutzer auf den Wechsel vorbereitet sind.</span><span class="sxs-lookup"><span data-stu-id="95f38-233">The cornerstone of any successful software deployment hinges on how prepared users are for the change.</span></span> <span data-ttu-id="95f38-234">Benutzer in Ihrer Organisation, die Slack verwenden, werden die Konzepte des Teams leicht verstehen, aber es ist immer noch eine Schulung erforderlich, um ihnen einen reibungslosen Übergang zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="95f38-234">Users in your organization using Slack will easily understand Teams concepts, but training is still needed to help them make a smooth transition.</span></span> <span data-ttu-id="95f38-235">Um eine umfassende Auswahl an Ressourcen für die Teams-Übernahme zu erhalten, besuchen Sie bitte den [Teams-Übernahmehub](adopt-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="95f38-235">For a comprehensive set of Teams adoption resources, go to the [Teams adoption hub](adopt-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="95f38-236">Beispielsweise verfügen beide Produkte über Kanäle, aber sie werden in jedem Produkt unterschiedlich verwendet.</span><span class="sxs-lookup"><span data-stu-id="95f38-236">For example, both products feature channels, but they’re used differently in each product.</span></span> <span data-ttu-id="95f38-237">Beispielsweise wird oft ein Kanal in Slack wie ein Chat in Teams für kurzfristige, transaktionale Unterhaltungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="95f38-237">For example, often a Channel in Slack is used like a chat in Teams for short-term, transactional conversations.</span></span> <span data-ttu-id="95f38-238">Weitere bemerkenswerte Unterschiede gibt es bei Thread-Unterhaltung und Nicht-Thread-Unterhaltung sowie bei der Einstellung von Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="95f38-238">Other notable differences are around threaded/non-threaded conversations and tuning notification settings.</span></span>

<span data-ttu-id="95f38-239">Schauen Sie sich unsere umfangreiche Bibliothek von [Teams-Videoschulung für Endbenutzer](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) an.</span><span class="sxs-lookup"><span data-stu-id="95f38-239">Check out our rich library of [End-user Teams video training](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7).</span></span> 

## <a name="move-to-teams"></a><span data-ttu-id="95f38-240">Umstieg auf Teams</span><span class="sxs-lookup"><span data-stu-id="95f38-240">Move to Teams</span></span> 
<span data-ttu-id="95f38-241">Nachdem Ihr Übergangsplan definiert ist, können Sie mit der Erstellung Ihrer Teams und Kanäle in Teams beginnen.</span><span class="sxs-lookup"><span data-stu-id="95f38-241">Now that your transition plan is defined, you can begin creating your teams and channels in Teams.</span></span> 

<span data-ttu-id="95f38-242">Sobald Sie Ihre Teams und Kanäle erstellt haben, fangen Sie an, Dateien aus Slack-Kanälen in Teams zu kopieren und Ihre Apps zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="95f38-242">Once you’ve created your teams & channels, begin copying files from Slack channels into Teams and configuring your apps.</span></span> <span data-ttu-id="95f38-243">Wenn Sie eine Lösung zum Speichern der Historie verwenden, kann diese jetzt auch konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="95f38-243">If you’re using a solution to retain history, that can be configured now as well.</span></span> <span data-ttu-id="95f38-244">Dann können Sie mit der Lizenzierung von Benutzern beginnen (wenn sie noch nicht lizenziert sind) und sie zu den entsprechenden Teams hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="95f38-244">Then you’re ready to start licensing users (if they aren’t licensed already) and adding them to the appropriate teams.</span></span> <span data-ttu-id="95f38-245">Um den Bedarf an zusätzlichen Exporten und Dateikopien zu reduzieren, sollten Sie den Slack-Zugriff zu einem vereinbarten Datum entfernen, das mit dem Hinzufügen jedes Benutzers zum Team übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="95f38-245">To reduce the need for additional exports and file copies, consider removing Slack access at an agreed-upon date that coincides with each user’s addition to the team.</span></span> <span data-ttu-id="95f38-246">Dadurch entfällt das erneute Exportieren und Importieren von Deltaänderungen an Dateien und Historie.</span><span class="sxs-lookup"><span data-stu-id="95f38-246">This avoids needing to re-export and import delta changes on files and history.</span></span>

<span data-ttu-id="95f38-247">Befolgen Sie die Schritte in der folgenden Abbildung, um Teams in Ihrer Organisation einzuführen.</span><span class="sxs-lookup"><span data-stu-id="95f38-247">Follow the steps in the diagram below to roll out Teams in your organization.</span></span> <span data-ttu-id="95f38-248">Weitere Informationen finden Sie unter [Rollout von Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="95f38-248">For more information, check out [How to roll out Teams](How-to-roll-out-teams.md).</span></span>


:::image type="content" source="media/migrate-slack-to-teams-image4.png" alt-text="Das Diagramm listet die Schritte des Wechsels von Slack zu Teams auf.":::
