---
title: Azure Sentinel und Microsoft Teams
author: MicrosoftHeidi
ms.author: tracyp
manager: dansimp
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Sicherheitsratschläge und -Erkenntnisse für IT-Administratoren zur Verwendung von Sentinel zum Überwachen von und Suchen nach Bedrohungen, die in Teams auftreten können.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f13cdd1d62a31178f7aed922b3bc55b87cd59db
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701233"
---
# <a name="azure-sentinel-and-microsoft-teams"></a><span data-ttu-id="79dd1-103">Azure Sentinel und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79dd1-103">Azure Sentinel and Microsoft Teams</span></span>

<span data-ttu-id="79dd1-104">Teams spielt eine zentrale Rolle sowohl bei der Kommunikation als auch bei der Datenfreigabe in der Microsoft 365 Cloud.</span><span class="sxs-lookup"><span data-stu-id="79dd1-104">Teams serves a central role in both communication and data sharing in the Microsoft 365 Cloud.</span></span> <span data-ttu-id="79dd1-105">Da der Teams-Dienst Berührungspunkte mit so vielen zugrunde liegenden Technologien in der Cloud hat, kann er sowohl von menschlicher als auch automatisierter Analyse profitieren, nicht nur wenn es um das *Suchen in Protokollen* geht, sondern auch bei der *Überwachung von Besprechungen in Echtzeit*.</span><span class="sxs-lookup"><span data-stu-id="79dd1-105">Because the Teams service touches on so many underlying technologies in the Cloud, it can benefit from human and automated analysis not only when it comes to *hunting in logs*, but also in *real-time monitoring of meetings*.</span></span> <span data-ttu-id="79dd1-106">Azure Sentinel bietet Administratoren diese Lösungen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-106">Azure Sentinel offers admins these solutions.</span></span>

> [!NOTE]
> <span data-ttu-id="79dd1-107">Benötigen Sie eine Auffrischung zu Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="79dd1-107">Need a refresher on Azure Sentinel?</span></span> <span data-ttu-id="79dd1-108">Genau so etwas finden Sie in [diesem Artikel](https://docs.microsoft.com/azure/sentinel/overview).</span><span class="sxs-lookup"><span data-stu-id="79dd1-108">[This article](https://docs.microsoft.com/azure/sentinel/overview) is just the thing.</span></span>

## <a name="sentinel-and-microsoft-teams-activity-logs"></a><span data-ttu-id="79dd1-109">Sentinel und Microsoft Teams-Aktivitätsprotokolle</span><span class="sxs-lookup"><span data-stu-id="79dd1-109">Sentinel and Microsoft Teams Activity Logs</span></span>

<span data-ttu-id="79dd1-110">Dieser Artikel befasst sich hauptsächlich mit dem Sammeln von Team-Aktivitätsprotokollen in Azure Sentinel.</span><span class="sxs-lookup"><span data-stu-id="79dd1-110">This article focuses on collecting Teams activity logs in Azure Sentinel.</span></span> <span data-ttu-id="79dd1-111">Abgesehen davon, dass Administratoren mithilfe von Sentinel-Arbeitsmappen und Runbooks die Sicherheitsverwaltung an einer zentralen Stelle durchführen können (einschließlich aller ausgewählten Geräte von Drittanbietern, Microsoft Threat Protection und anderen Microsoft 365-Workloads), können sie damit auch die Sicherheitsüberwachung systematisieren.</span><span class="sxs-lookup"><span data-stu-id="79dd1-111">Aside from allowing administrators to put security management under one pane of glass (including any selected 3rd party devices, Microsoft Threat Protection, and other Microsoft 365 Workloads), Sentinel workbooks, and runbooks can make security monitoring systematic.</span></span> <span data-ttu-id="79dd1-112">Ein guter erster Schritt bei dieser Vorgehensweise ist das Sammeln der erforderlichen Protokolle für die Analyse.</span><span class="sxs-lookup"><span data-stu-id="79dd1-112">A good first step in this process is collecting the needed logs for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="79dd1-113">Es kann mehr als ein Microsoft 365-Abonnement in derselben Instanz von Azure Sentinel vorkommen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-113">More than one Microsoft 365 subscription can be surfaced in the same instance of Azure Sentinel.</span></span> <span data-ttu-id="79dd1-114">Dies gestattet [Echtzeitüberwachung](https://docs.microsoft.com/azure/sentinel/livestream) und die Suche nach Bedrohungen in historischen Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="79dd1-114">This will allow for [realtime monitoring](https://docs.microsoft.com/azure/sentinel/livestream) and hunting for threats in historical log file s.</span></span> <span data-ttu-id="79dd1-115">Administratoren können mithilfe von [ressourcenübergreifenden Abfragen](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query) suchen, d.h. innerhalb einer einzelnen Ressourcengruppe, über Ressourcengruppen hinweg oder in einem anderen Abonnement.</span><span class="sxs-lookup"><span data-stu-id="79dd1-115">Administrators will be able to hunt using [cross-resource queries](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query), that is within a single resource group, across resource groups, or in another subscription.</span></span>

## <a name="step-1-collect-teams-logs"></a><span data-ttu-id="79dd1-116">Schritt 1: Sammeln von Teams-Protokollen</span><span class="sxs-lookup"><span data-stu-id="79dd1-116">Step 1: Collect Teams logs</span></span>

<span data-ttu-id="79dd1-117">Dieser Abschnitt besteht aus drei Teilen:</span><span class="sxs-lookup"><span data-stu-id="79dd1-117">This section has three parts:</span></span>

1. <span data-ttu-id="79dd1-118">Aktivieren von Überwachungsprotokollen in **Microsoft 365** (M365).</span><span class="sxs-lookup"><span data-stu-id="79dd1-118">Enabling Audit Logs in **Microsoft 365** (M365).</span></span>
2. <span data-ttu-id="79dd1-119">Registrieren einer App bei **Microsoft Azure**, um die Authentifizierung und Autorisierung für die Protokollsammlung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-119">Registering an App in **Microsoft Azure** to permit authentication and authorization for log collection.</span></span>
3. <span data-ttu-id="79dd1-120">Registrieren des API-Abonnements, das die Protokollsammlung über die M365-API mittels **PowerShell** zulassen soll.</span><span class="sxs-lookup"><span data-stu-id="79dd1-120">Registering the API subscription that will allow log collection via M365 API via **PowerShell**.</span></span>

### <a name="enable-audit-logs-in-m365"></a><span data-ttu-id="79dd1-121">Aktivieren von Überwachungsprotokollen in M365</span><span class="sxs-lookup"><span data-stu-id="79dd1-121">Enable Audit logs in M365</span></span>

<span data-ttu-id="79dd1-122">Da Teams Aktivitäten über M365 protokolliert, werden Überwachungsprotokolle nicht standardmäßig gesammelt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-122">Because Teams logs activity through M365, audit logs aren't collected by default.</span></span> <span data-ttu-id="79dd1-123">Aktivieren Sie diese Funktion mithilfe [dieser Schritte](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0).</span><span class="sxs-lookup"><span data-stu-id="79dd1-123">Turn on this feature via [these steps](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0).</span></span> <span data-ttu-id="79dd1-124">Teams-Daten werden in der M365-Überwachung unter *Audit.General* gesammelt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-124">Teams data is collected in the M365 audit under *Audit.General*.</span></span>

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a><span data-ttu-id="79dd1-125">Registrieren einer App bei Microsoft Azure für die Protokollsammlung</span><span class="sxs-lookup"><span data-stu-id="79dd1-125">Register an App in Microsoft Azure for log collection</span></span>

> [!TIP]
> <span data-ttu-id="79dd1-126">Bevor Sie beginnen, müssen Sie Ihre **Anwendungs-ID/Client-ID** und ihre **Mandanten-ID** für die spätere Verwendung aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-126">Before you begin, you will need to record you **Application ID / Client ID**, and your **Tenant ID** for later use.</span></span> <span data-ttu-id="79dd1-127">Stellen Sie sicher, dass Sie sie erfassen, während Sie die unten beschriebenen Schritte zur App-Registrierung absolvieren.</span><span class="sxs-lookup"><span data-stu-id="79dd1-127">Be sure to capture them as you walk through app registration steps below.</span></span> <span data-ttu-id="79dd1-128">Beide IDs werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-128">You will see both IDs.</span></span>
>- <span data-ttu-id="79dd1-129">Nachdem Ihre App erstellt wurde, klicken Sie auf der Schnellstart-Randleiste auf „App-Registrierung“, suchen Sie den Anzeigenamen Ihrer neuen App, und kopieren Sie die Anwendungs (Client)-ID.</span><span class="sxs-lookup"><span data-stu-id="79dd1-129">After your app is created, click App Registration on the quick launch side-bar > Find your new app's display name > copy the Application (client) ID.</span></span>
>- <span data-ttu-id="79dd1-130">Klicken Sie auf der Schnellstart-Randleiste auf „Übersicht“, und kopieren Sie die Verzeichnis (Mandanten)-ID.</span><span class="sxs-lookup"><span data-stu-id="79dd1-130">Click Overview on the quick launch side-bar > copy the Directory (tenant) ID.</span></span>

<span data-ttu-id="79dd1-131">Authentifizieren und autorisieren Sie eine Azure Active Directory-App (Azure AD) für das Sammeln von Protokolldaten aus der API.</span><span class="sxs-lookup"><span data-stu-id="79dd1-131">Authenticate and authorize an Azure Active Directory (Azure AD) app to collect log data from the API.</span></span>

1. <span data-ttu-id="79dd1-132">Navigieren Sie im Azure-Portal zum Blatt *Azure AD*.</span><span class="sxs-lookup"><span data-stu-id="79dd1-132">Navigate to your *Azure AD* blade in the Azure portal.</span></span>
2. <span data-ttu-id="79dd1-133">Klicken Sie auf der Schnellstart-Randleiste auf *App-Registrierungen*.</span><span class="sxs-lookup"><span data-stu-id="79dd1-133">Click on *App registrations* in the quick launch side-bar.</span></span>
3. <span data-ttu-id="79dd1-134">Wählen Sie *Neue Registrierung* aus.</span><span class="sxs-lookup"><span data-stu-id="79dd1-134">Select *New registration*.</span></span>
4. <span data-ttu-id="79dd1-135">Benennen Sie Ihre App zum Sammeln von Teams-Protokollen, und klicken Sie auf *Registrieren*.</span><span class="sxs-lookup"><span data-stu-id="79dd1-135">Name your Teams log collecting app and click *Register*.</span></span>
5. <span data-ttu-id="79dd1-136">Klicken Sie entlang dieses Pfads auf: *API-Berechtigungen* > *Berechtigung hinzufügen* > *Office 365-Verwaltungs-APIs* > *Anwendungsberechtigungen*.</span><span class="sxs-lookup"><span data-stu-id="79dd1-136">Click along this path: *API Permissions* > *Add a permission* > *Office 365 Management APIs* > *Application permissions*.</span></span>
6. <span data-ttu-id="79dd1-137">Erweitern Sie den Aktivitätsfeed, und aktivieren Sie *ActivityFeed.Read*.</span><span class="sxs-lookup"><span data-stu-id="79dd1-137">Expand Activity Feed and check *ActivityFeed.Read*.</span></span>
7. <span data-ttu-id="79dd1-138">Wählen Sie hier *Administratoreinwilligung erteilen* aus.</span><span class="sxs-lookup"><span data-stu-id="79dd1-138">Choose *Grand admin consent* here.</span></span> <span data-ttu-id="79dd1-139">Klicken Sie auf „Ja“, wenn Sie gefragt werden, ob Sie das möchten.</span><span class="sxs-lookup"><span data-stu-id="79dd1-139">Click Yes when prompted asking if you mean it.</span></span>
8. <span data-ttu-id="79dd1-140">Klicken Sie auf der Randleiste auf *Zertifikate und Geheimnisse* und dann auf die Schaltfläche *Neuer geheimer Clientschlüssel*.</span><span class="sxs-lookup"><span data-stu-id="79dd1-140">Click *Certificates and Secrets* in the side-bar> *New client secret* button.</span></span>
9. <span data-ttu-id="79dd1-141">Geben Sie im Fenster „Neuer geheimer Clientschlüssel“ eine Beschreibung für den neuen geheimen Clientschlüssel ein, stellen Sie sicher, dass Sie als „Ablauf“ den Wert „Nie“ auswählen, und klicken Sie auf *Hinzufügen*.</span><span class="sxs-lookup"><span data-stu-id="79dd1-141">On the New client secret window, enter a description for the new Client Secret, make sure you choose 'Never' for Expiration, and click *Add*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="79dd1-142">Es ist von **kritischer** Bedeutung, den neuen geheimen Clientschlüssel in einen Kennwort-Manager-Eintrag zu kopieren, der den Namen der neu erstellten App trägt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-142">It's **critical** to copy the new client secret into a password manager entry that goes under the name of the newly created app.</span></span> <span data-ttu-id="79dd1-143">Sie können nicht mehr dorthin zurückkehren, um sich dieses Geheimnis anzusehen, nachdem das Azure-Blatt geschlossen wurde (*Blatt* (blade) ist in Azure die Bezeichnung für „Fenster“).</span><span class="sxs-lookup"><span data-stu-id="79dd1-143">You won't be able to get back to look at this secret after the closing out of the Azure blade (*blade* being the Azure term for window).</span></span>

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a><span data-ttu-id="79dd1-144">Registrieren der API bei PowerShell zum Sammeln von Team-Protokollen</span><span class="sxs-lookup"><span data-stu-id="79dd1-144">Register the API with PowerShell to collect Teams logs</span></span>

<span data-ttu-id="79dd1-145">Der letzte Schritt bei der Einrichtung besteht darin, das API-Abonnement zu sammeln und zu registrieren, damit Sie Ihre Protokolldaten sammeln können.</span><span class="sxs-lookup"><span data-stu-id="79dd1-145">The final step in setup is to collect and register the API subscription so that you can collect your log data.</span></span> <span data-ttu-id="79dd1-146">Dies geschieht über PowerShell-REST-Aufrufe der M365-Verwaltungsaktivitäts-API.</span><span class="sxs-lookup"><span data-stu-id="79dd1-146">This is done via PowerShell REST calls to the M365 Management Activity API.</span></span>

<span data-ttu-id="79dd1-147">Halten Sie die Werte für die **Anwendungs (Client)-ID**, den neuen **geheimen Clientschlüssel**, Ihre **URL-Domäne für M365** und die **Verzeichnis (Mandanten)-ID** bereit, um sie unten in dem PowerShell-Cmdlet bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-147">Be ready to supply **Application (client) ID**, the new **Client Secret**, your **URL domain for M365**, and **Directory (tenant) ID** values in the PowerShell cmdlet below.</span></span>

```PowerShell
$ClientID = "<Application (client) ID>"  
$ClientSecret = "<Client secret>"  
$loginURL = "https://login.microsoftonline.com/"  
$tenantdomain = "<domain>.onmicrosoft.com"  

$TenantGUID = "<Directory (tenant) ID>"  
$resource = "https://manage.office.com"  
$body = @{grant_type="client_credentials";resource=$resource;client_id=$ClientID;client_secret=$ClientSecret}
$oauth = Invoke-RestMethod -Method Post -Uri $loginURL/$tenantdomain/oauth2/token?api-version=1.0 -Body $body  
$headerParams = @{'Authorization'="$($oauth.token_type) $($oauth.access_token)"}
$publisher = New-Guid
Invoke-WebRequest -Method Post -Headers $headerParams -Uri "https://manage.office.com/api/v1.0/$tenantGuid/activity/feed/subscriptions/start?contentType=Audit.General&PublisherIdentifier=$Publisher"
```

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a><span data-ttu-id="79dd1-148">Schritt 2: Bereitstellen eines Sentinel-Playbooks zum Erfassen der Teams-Protokolle</span><span class="sxs-lookup"><span data-stu-id="79dd1-148">Step 2: Deploy a Sentinel Playbook to ingest the Teams logs</span></span>

<span data-ttu-id="79dd1-149">Azure Sentinel-Playbooks (auch als Logik-Apps bezeichnet) gestatten Azure das Erfassen Ihrer gesammelten Teams-Daten.</span><span class="sxs-lookup"><span data-stu-id="79dd1-149">Azure Sentinel Playbooks (also called Logic Apps) will allow Azure to ingest your collected Teams data.</span></span> <span data-ttu-id="79dd1-150">Die Logik-App fragt Office 365 ab, um die Überwachungsdaten zu finden, die es in den Azure Sentinel-Arbeitsbereich schreibt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-150">The Logic App queries Office 365 to find the audit data it writes into the Azure Sentinel workspace.</span></span>

<span data-ttu-id="79dd1-151">Verwenden Sie [diese](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM-Vorlage, um Ihr Sentinel-Playbook bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-151">Use [this](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM template to deploy your Sentinel Playbook.</span></span>

<span data-ttu-id="79dd1-152">Aspekte, die Beachtung verdienen:</span><span class="sxs-lookup"><span data-stu-id="79dd1-152">Things to remember:</span></span>

1. <span data-ttu-id="79dd1-153">Sie müssen die ARM-Vorlage durchgehen und bestimmte Werte durch Werte ersetzen, die für Ihre eigene Umgebung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="79dd1-153">You will need to walk through the ARM template and replace certain of the values with values appropriate for your own environment.</span></span>
2. <span data-ttu-id="79dd1-154">Sie müssen zwischen der Erfassung von Protokollen und dem Anzeigen von Ergebnissen in Azure Sentinel Zeit vergehen lassen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-154">You will need to allow time between the ingestion of logs and looking at the results in Azure Sentinel.</span></span>

   <span data-ttu-id="79dd1-155">Warten Sie 5 bis 10 Minuten, weil sonst, wenn es innerhalb der letzten 5 Minuten keine Daten vorhanden waren, eine Fehlermeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="79dd1-155">Wait for 5 to 10 minutes, understanding that if there is no data within the past 5 minutes you will see an error message.</span></span> <span data-ttu-id="79dd1-156">Überprüfen Sie die Überwachungsprotokolle, und denken Sie daran, dass, weil sich die Teams-Informationen in den „Audit.General“-Ereignissen befinden, in denen mehr als die Teams-Protokolle gesammelt wird, die Ergebnisse innerhalb von 5 bis 10 Minuten auf Systemen angezeigt werden sollten, die gerade verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79dd1-156">Check Audit logs and keep in mind that because Teams information is in the Audit.General events, which collects more than Teams logs, results should appear within 5 to 10 minutes on systems that are in use.</span></span> <span data-ttu-id="79dd1-157">Wenn Sie eine Textumgebung verwenden, stellen Sie sicher, dass Sie Teams verwenden, um die Protokollierung zu generieren.</span><span class="sxs-lookup"><span data-stu-id="79dd1-157">If using a text environment, be certain to use Teams in order to generate logging.</span></span>

![Eine Grafik, die die Logik-App-Klassen zeigt.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> <span data-ttu-id="79dd1-159">Erläuterung der Aktionen in der Grafik:</span><span class="sxs-lookup"><span data-stu-id="79dd1-159">Explanation of actions in the graphic:</span></span> 
  </summary>

  <span data-ttu-id="79dd1-160">• „Wiederholung“ ist der Logik-App-Trigger, der den Workflow veranlasst, dass er stündlich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="79dd1-160">• Recurrence is the Logic App Trigger that tells the workflow to run every hour.</span></span>
  <p>
<span data-ttu-id="79dd1-161">• Die Aktion „Aktuelle Zeit“ ist sehr einfach und ruft lediglich die aktuelle Uhrzeit ab.</span><span class="sxs-lookup"><span data-stu-id="79dd1-161">• The Current Time action is very basic and just gets the current time.</span></span>
  <p>
<span data-ttu-id="79dd1-162">• „Variable initialisieren“ erstellt eine Variable namens „NextPage“ und legt diese auf „1“ fest.</span><span class="sxs-lookup"><span data-stu-id="79dd1-162">• Initialize Variable creates a variable called NextPage and sets it to 1.</span></span> <span data-ttu-id="79dd1-163">Diese wird später verwendet, um die Paginierung aus der O365-API zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="79dd1-163">This will be used later in order to handle pagination from the O365 API.</span></span>
  <p>
<span data-ttu-id="79dd1-164">• „Variable 2 initialisieren“ erstellt eine leere Variable namens „Start Time“ (Startzeit).</span><span class="sxs-lookup"><span data-stu-id="79dd1-164">• Initialize Variable 2 creates an empty variable called Start Time.</span></span>
  <p>
<span data-ttu-id="79dd1-165">• „Abfrage ausführen und Ergebnisse auflisten“ ist eine Azure Monitor-Aktion, die im Arbeitsbereich das letzte O365-Protokoll abfragt, das von der Logik-App eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="79dd1-165">• Run Query and list results is an Azure Monitor action that will query the workspace for the last O365 log that was entered from the Logic App.</span></span>
  <p>
<span data-ttu-id="79dd1-166">• „Bedingung 4“ wird verwendet, um zu überprüfen, ob die Abfrage „Abfrage ausführen und Ergebnisse auflisten“ Daten zurückgegeben hat.</span><span class="sxs-lookup"><span data-stu-id="79dd1-166">• Condition 4 is used to check whether the Run Query and list results query returned any data.</span></span> <span data-ttu-id="79dd1-167">Dies geschieht, um zu überprüfen, ob dies das erste Mal ist, dass die Logik-App verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="79dd1-167">This is done to check if this is the very first time the Logic App has been used.</span></span> <span data-ttu-id="79dd1-168">Wenn keine Daten zurückgegeben werden, wird die Variable „StartTime“ auf „Now – 24 Hours“ (Jetzt – 24 Stunden) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-168">If no data is returned, StartTime variable is set to Now – 24 hours.</span></span> <span data-ttu-id="79dd1-169">Wenn Daten zurückgegeben werden, wird „StartTime“ auf die „TimeGenerated“ des letzten Datensatzes festgelegt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-169">If data is returned, StartTime is set to the last record TimeGenerated.</span></span> <span data-ttu-id="79dd1-170">Dies geschieht, damit die Abfrage mit der Abfrage der O365-API Daten ab dem letzten Eintrag bis jetzt abrufen kann, oder innerhalb der letzten 24 Stunden, wenn dies die erste Ausführung ist.</span><span class="sxs-lookup"><span data-stu-id="79dd1-170">This is done so that the query can get data from the last entry till now in the poll against the O365 API, or in the last 24 hours if this is the first run.</span></span>
  <p>
<span data-ttu-id="79dd1-171">• „Variable 3 initialisieren“ erstellt eine Variable namens „AvailableUri“ (Verfügbarer URI).</span><span class="sxs-lookup"><span data-stu-id="79dd1-171">• Initialize Variable 3 creates a variable called AvailableUri.</span></span> <span data-ttu-id="79dd1-172">Hierbei handelt es sich um eine Zeichenfolge mit der URL, die mit „StartTime“ und „CurrentTime“ als Start- bzw. Endzeit erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="79dd1-172">This is a string with the URL built using the StartTime and CurrentTime as start and end times, respectively.</span></span>
  <p>
<span data-ttu-id="79dd1-173">• Die Bedingung „Until“ (Bis) ist eine Schleife, durch die die Logik-App weiterhin die API abrufen kann, um festzustellen, ob weitere Daten vorhanden sind (Paginierung).</span><span class="sxs-lookup"><span data-stu-id="79dd1-173">• The Until condition is a loop that allows the logic app to keep polling the API to see if there is more data (pagination).</span></span> <span data-ttu-id="79dd1-174">Solange die Variable „NextPage“ (Nächste Seite) den Wert „1“ hat, wird die Schleife fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-174">As long as NextPage variable is 1 the loop will continue.</span></span> <span data-ttu-id="79dd1-175">Später wird diese Variable aktualisiert, wenn keine weiteren Seiten mehr zum Abrufen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="79dd1-175">Later this variable will be updated if there are no more pages left to retrieve.</span></span>
  <p>
<span data-ttu-id="79dd1-176">• Innerhalb der „Until“-Schleife stellt der erste HTTP-Schritt eine Verbindung mit dem „AvailableURI“ her.</span><span class="sxs-lookup"><span data-stu-id="79dd1-176">• Inside the Until loop, the first HTTP step Connects to the AvailableURI.</span></span> <span data-ttu-id="79dd1-177">Dieser URI gibt eine Liste verfügbarer Inhalte und der einzelnen Inhalts-URIs zurück.</span><span class="sxs-lookup"><span data-stu-id="79dd1-177">This URI returns a list of available content and each contents URI.</span></span> <span data-ttu-id="79dd1-178">Weitere Informationen zu dieser Funktionsweise finden Sie unter dieser URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="79dd1-178">There's more on how this works at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="79dd1-179">• Als Nächstes wird ein Test ausgeführt, um sicherzustellen, dass Daten zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="79dd1-179">• Next a check is run to make sure data is returned.</span></span> <span data-ttu-id="79dd1-180">Mit der „Condition“ (Bedingung) wird überprüft, ob die Länge des Texts „0“ beträgt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-180">The Condition checks if the length of the body is 0.</span></span> <span data-ttu-id="79dd1-181">Ist dies der Fall, gibt es keine Daten, die in Log Analytics geschrieben werden könnten.</span><span class="sxs-lookup"><span data-stu-id="79dd1-181">If so there is no data to write to Log Analytics.</span></span> <span data-ttu-id="79dd1-182">Ist der Wert größer als 0, sind zu verarbeitende Daten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="79dd1-182">If the value is greater than 0, there is data to process.</span></span>
  <p>
<span data-ttu-id="79dd1-183">• Wenn Daten erkannt werden, müssen diese als Nächstes verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="79dd1-183">• If data is detected, it must next be processed.</span></span> <span data-ttu-id="79dd1-184">„JSON analysieren“ definiert ein Schema der zurückgegebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="79dd1-184">Parse JSON defines a schema of the returned data.</span></span> <span data-ttu-id="79dd1-185">Damit können Logik-Apps die analysierten Daten in späteren Schritten als dynamische Inhalte verwenden.</span><span class="sxs-lookup"><span data-stu-id="79dd1-185">This allows logic apps to use the parsed data as Dynamic content in later steps.</span></span>
  <p>
<span data-ttu-id="79dd1-186">• Da es sich bei der zurückgegebenen Liste verfügbarer Daten um ein Array handelt, wird eine „For Each“-Aktion verwendet, um die Liste der verfügbaren Inhalte als Schleife zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-186">• Since the returned list of available data is an Array, a For Each action is used to loop through the list of available content.</span></span>
  <p>
<span data-ttu-id="79dd1-187">• Als Nächstes wird der Inhalt extrahiert.</span><span class="sxs-lookup"><span data-stu-id="79dd1-187">• Next is grabbing the content.</span></span>  <span data-ttu-id="79dd1-188">HTTP wird erneut verwendet, um den „contentUri“ (eine dynamische Eigenschaft, die mittels „JSON analysieren“ erstellt wurde) abzurufen, der die URL der abzurufenden Daten ist.</span><span class="sxs-lookup"><span data-stu-id="79dd1-188">HTTP is used again to get the contentUri (a dynamic property created from Parse JSON), which is the URL of the data to retrieve.</span></span>
  <p>
<span data-ttu-id="79dd1-189">• „JSON analysieren“ auch verwendet, um die zurückgegebenen Daten zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="79dd1-189">• Parse JSON is also used to parse the returned data.</span></span> <span data-ttu-id="79dd1-190">Einige Beispielinhalte können Sie unter dieser URL finden: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span><span class="sxs-lookup"><span data-stu-id="79dd1-190">You can find some sample content at this URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.</span></span>
  <p>
<span data-ttu-id="79dd1-191">• Die zurückgegebenen Daten sind ebenfalls ein Array.</span><span class="sxs-lookup"><span data-stu-id="79dd1-191">• The data returned is also an array.</span></span> <span data-ttu-id="79dd1-192">Hier kann auch eine „For Each“-Schleife verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79dd1-192">A For Each loop can be used here as well.</span></span> <span data-ttu-id="79dd1-193">In dieser Schleife nimmt der Workflow das aktuelle Datenelement und verwendet die Aktion „Daten senden“, um die Daten in Log Analytics zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="79dd1-193">In this loop, the workflow takes the current item of data and uses the Send Data action to write the data to Log Analytics.</span></span>
  <p>
<span data-ttu-id="79dd1-194">• Da es mehrere Seiten verfügbarer Inhalte geben kann, wird mit einer Bedingung überprüft, ob der „NextPageUri“ nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="79dd1-194">• Since there may be multiple pages of available content, a condition checks if the NextPageUri is not NULL.</span></span> <span data-ttu-id="79dd1-195">Wenn er NULL oder leer ist, wird „NextPage“ auf „0“ festgelegt, wodurch die „Until“-Schleife beendet wird.</span><span class="sxs-lookup"><span data-stu-id="79dd1-195">If it is NULL, or empty, NextPage is set to 0, which ends the Until loop.</span></span> <span data-ttu-id="79dd1-196">Enthält er eine URL, wird die Variable „AvaibleUri“ auf diese URL aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="79dd1-196">If it contains a URL, the AvaibleUri variable is updated to that URL.</span></span> <span data-ttu-id="79dd1-197">Auf diese Weise wird bei der nächsten Ausführung der „Until“-Schleife die nächste verfügbare URL verwendet, nicht die Anfangs-URL.</span><span class="sxs-lookup"><span data-stu-id="79dd1-197">This way, the next run of the Until loop uses a next available URL, and not the starting URL.</span></span>

  </details>

> [!TIP]
> <span data-ttu-id="79dd1-198">Sie können stattdessen eine *Azure-Funktion* verwenden, um diese Protokolle zu erfassen, und wenn Sie dies tun, finden Sie die Informationen zum Bereitstellen [hier](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) oder [hier](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), je nach Ihren Wünschen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-198">You may choose to use an *Azure Function* to ingest those logs, instead, and if you do, the information on how to deploy is [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data), or [here](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), depending on your preference.</span></span>

<span data-ttu-id="79dd1-199">Während der Connector ausgeführt wird (egal welche der obigen Optionen Sie ausgewählt haben), sollte im Azure Sentinel-Arbeitsbereich eine benutzerdefinierte Tabelle namens „O365API_CL“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="79dd1-199">With the connector (whichever of the options above you chose) running, you should see a custom table called O365API_CL in the Azure Sentinel workspace.</span></span> <span data-ttu-id="79dd1-200">Diese nimmt Ihre Teams-Protokolle auf.</span><span class="sxs-lookup"><span data-stu-id="79dd1-200">This will house your Teams logs.</span></span>

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a><span data-ttu-id="79dd1-201">Schritt 3: Verwenden von Sentinel zum Überwachen von Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="79dd1-201">Step 3: Use Sentinel to monitor Microsoft Teams</span></span>

<span data-ttu-id="79dd1-202">Die Identität ist ein wichtiger zu überwachender Angriffsvektor, wenn es um Microsoft Teams geht.</span><span class="sxs-lookup"><span data-stu-id="79dd1-202">Identity is an important attack vector to monitor when it comes to Microsoft Teams.</span></span> <span data-ttu-id="79dd1-203">Da Azure Active Directory (Azure AD) die Unterstützung des Microsoft 365-Verzeichnisses, einschließlich Teams, ist, ist das Sammeln von und Suchen nach Bedrohungen in Azure AD-Protokollen im Zusammenhang mit Authentifizierung hilfreich, um verdächtiges Verhalten in Bezug auf Identitäten zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-203">Because Azure Active Directory (Azure AD) is the underpinning of Microsoft 365's directory, including Teams, collecting and hunting for threats in Azure AD logs around authentication will be useful in capturing suspicious behavior around identity.</span></span> <span data-ttu-id="79dd1-204">Sie können den integrierten Connector verwenden, um Azure AD-Daten in Azure Sentinel zu pullen, und diese [Erkennungs](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs)- und [Such](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs)-Abfragen, um nach Problemen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-204">You can use the built-in connector to pull Azure AD data into Azure Sentinel, and use these [detection](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs) and [hunting](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs) queries to look for problems.</span></span>

<span data-ttu-id="79dd1-205">In Bezug auf für Microsoft Teams spezifische Angriffe, z. B. die Bedrohung von Daten, verfügt Azure Sentinel auch über Mittel, um diese zu überwachen und sie aufzuspüren.</span><span class="sxs-lookup"><span data-stu-id="79dd1-205">Regarding attacks specific to Microsoft Teams, threats to data, for example, Azure Sentinel also has means to monitor for them and hunt them down.</span></span>

### <a name="create-a-parser-for-your-data"></a><span data-ttu-id="79dd1-206">Erstellen eines Parsers für Ihre Daten</span><span class="sxs-lookup"><span data-stu-id="79dd1-206">Create a parser for your data</span></span>

<span data-ttu-id="79dd1-207">Der erste Schritt, um die große Menge gesammelter Daten sinnvoll zu interpretieren, besteht darin, ihm durch Analyse Bedeutung zu verleihen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-207">The first thing to do in order to make sense of the large set of collected data is to give it meaning by parsing it.</span></span> <span data-ttu-id="79dd1-208">Dies erfolgt mittels einer KQL-Funktion (Kusto Query Language), wodurch sich die Daten einfacher verwenden lassen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-208">This is done with a Kusto Query Language (KQL) Function that makes the data easier to use.</span></span>

> [!NOTE]
> <span data-ttu-id="79dd1-209">KQL-Funktionen sind KQL-Abfragen, die als Datentyp „Funktion“ gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="79dd1-209">KQL functions are KQL queries saved as a data-type called 'function'.</span></span> <span data-ttu-id="79dd1-210">KQL-Funktionen besitzen einen Alias, der in Sentinel in das Abfragefeld eingegeben werden kann, um die Abfrage schnell erneut auszuführen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-210">KQL functions have an alias that can be entered into the query box in Sentinel to quickly run the query again.</span></span> <span data-ttu-id="79dd1-211">Weitere Informationen zu KQL-Funktionen und zum Erstellen einer Parser-Funktion finden Sie in [diesem Tech-Community-Artikel](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="79dd1-211">For more about KQL functions and how to build a parser function, read [this Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>
 
 <span data-ttu-id="79dd1-212">Der folgende Parser ist ein anpassbares Beispiel, das auf die Auswahl einer Teilmenge der Office 365-Verwaltungs-API-Felder abzielt, die für *Teams* relevant sind.</span><span class="sxs-lookup"><span data-stu-id="79dd1-212">The parser below is a customizable example aimed at selecting a subset of the Office 365 Management API fields relevant to *Teams*.</span></span> <span data-ttu-id="79dd1-213">Außerdem gibt es ein empfohlenes [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) für Parser, aber der nachstehende Parser kann geändert werden, um unterschiedliche Anforderungen und Vorlieben zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-213">There is also a suggested parser [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt), but the parser below can be modified to fit different needs and preferences.</span></span>

```kusto
O365API_CL
| where Workload_s =~ "MicrosoftTeams"
| project TimeGenerated,
          Workload=Workload_s,
          Operation=Operation_s,
          TeamName=columnifexists('TeamName_s', ""),
          UserId=columnifexists('UserId_s', ""),
          AddOnName=columnifexists('AddOnName_s', AddOnGuid_g),
          Members=columnifexists('Members_s', ""),
          Settings=iif(Operation_s contains "Setting", pack("Name", columnifexists('Name_s', ""), "Old Value", columnifexists('OldValue_s', ""), "New Value", columnifexists('NewValue_s', "")),""),
          Details=pack("Id", columnifexists('Id_g', ""),  "OrganizationId", columnifexists('OrganizationId_g', ""), "UserType", columnifexists('UserType_d', ""), "UserKey", columnifexists('UserKey_g', ""), "TeamGuid", columnifexists('TeamGuid_s', "")) 
```
 <span data-ttu-id="79dd1-214">Speichern Sie den Parser als KQL-Funktion mit dem Alias „TeamsData“.</span><span class="sxs-lookup"><span data-stu-id="79dd1-214">Save the parser as a KQL function, with an alias of TeamsData.</span></span> <span data-ttu-id="79dd1-215">Er wird in den folgenden Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="79dd1-215">It will be used for the queries to follow.</span></span> <span data-ttu-id="79dd1-216">Details zum Konfigurieren und Verwenden einer KQL-Funktion als Parser finden Sie in diesem [Tech-Community-Artikel](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span><span class="sxs-lookup"><span data-stu-id="79dd1-216">Details on configuring and using a KQL function as a parser can be found in this [Tech Community article](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).</span></span>

## <a name="helpful-hunting-kql-queries"></a><span data-ttu-id="79dd1-217">Hilfreiche KQL-Suchabfragen</span><span class="sxs-lookup"><span data-stu-id="79dd1-217">Helpful hunting KQL queries</span></span>

<span data-ttu-id="79dd1-218">Verwenden Sie diese Abfragen, um sich mit Ihren Teams-Daten und der Teams-Umgebung vertraut zu machen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-218">Use these queries to familiarize yourself with your Teams data and Teams environment.</span></span> <span data-ttu-id="79dd1-219">Die Kenntnis, wie die Umgebung aussehen und sich verhalten sollte, ist ein guter erster Schritt, um verdächtige Aktivitäten zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-219">Knowing how the environment should look and behave is a good first step in recognizing suspicious activity.</span></span> <span data-ttu-id="79dd1-220">Von hier aus können Sie weiter zur Bedrohungssuche verzweigen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-220">From there, you can branch out into threat hunting.</span></span>

#### <a name="federated-external-users-query"></a><span data-ttu-id="79dd1-221">Abfrage für externe Verbundbenutzer</span><span class="sxs-lookup"><span data-stu-id="79dd1-221">Federated external users query</span></span>

<span data-ttu-id="79dd1-222">Rufen Sie die Liste der Teams-Sites ab, auf denen es externe Verbundbenutzer gibt.</span><span class="sxs-lookup"><span data-stu-id="79dd1-222">Get the list of Teams sites that have federated external users.</span></span> <span data-ttu-id="79dd1-223">Diese Benutzer verfügen über einen Domänennamen bzw. ein UPN-Suffix, der/das *nicht* im Besitz Ihrer Organisation ist.</span><span class="sxs-lookup"><span data-stu-id="79dd1-223">These users will have a domain name / UPN suffix that *isn't* owned by your organization.</span></span> <span data-ttu-id="79dd1-224">In dieser Beispielabfrage besitzt die Organisation „contoso.com“.</span><span class="sxs-lookup"><span data-stu-id="79dd1-224">In this example query, the organization owns contoso.com.</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| extend UPN = tostring(parse_json(Members)[0].Upn)
| where UPN !endswith "contoso.com"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members, UPN
```

> [!TIP]
> <span data-ttu-id="79dd1-225">Informationen zu den Zugriffstypen „Extern“ und „Gast“ in Teams finden Sie in [diesem Artikel](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations) oder im Abschnitt *Teilnehmertypen* des [Sicherheitshandbuchs für Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide).</span><span class="sxs-lookup"><span data-stu-id="79dd1-225">To learn more about External and Guest access types in Teams see [this article](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations), or the *Participant Types* section in the [Teams Security Guide](https://docs.microsoft.com/microsoftteams/teams-security-guide).</span></span>

#### <a name="who-recently-joined--whose-role-changed"></a><span data-ttu-id="79dd1-226">Jüngste Beitritte/Jüngste Rollenänderungen</span><span class="sxs-lookup"><span data-stu-id="79dd1-226">Who recently joined / Whose role changed</span></span>

<span data-ttu-id="79dd1-227">Fragen Sie einen bestimmten Benutzer ab, um zu überprüfen, ob er einem Teams-Kanal in den letzten 7 Tagen oder innerhalb einer Woche hinzugefügt wurde:</span><span class="sxs-lookup"><span data-stu-id="79dd1-227">Query a specific user to check if they were added to a Teams channel in the last 7 days, or within a week:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

<span data-ttu-id="79dd1-228">Wurde die Rolle eines Benutzers in den letzten 7 Tagen für ein Team geändert:</span><span class="sxs-lookup"><span data-stu-id="79dd1-228">Was a user's role changed for a Team in the last 7 days:</span></span>

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a><span data-ttu-id="79dd1-229">Externe Benutzer aus unbekannten oder neuen Organisationen</span><span class="sxs-lookup"><span data-stu-id="79dd1-229">External users from unknown or new organizations</span></span>

<span data-ttu-id="79dd1-230">In Teams können Sie Ihrer Umgebung oder Ihren Kanälen externe Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-230">In Teams, you can add external users to your environment or channels.</span></span> <span data-ttu-id="79dd1-231">Organisationen verfügen häufig über eine begrenzte Anzahl wichtiger Partnerschaften und fügen Benutzer aus dem Kreis dieser Partner hinzu.</span><span class="sxs-lookup"><span data-stu-id="79dd1-231">Organizations often have a limited number of key partnerships and add users from among these partners.</span></span> <span data-ttu-id="79dd1-232">Diese KQL-Abfrage sucht nach externen Benutzern, die Teams hinzugefügt wurden, die aus Organisationen stammen, die zuvor noch nicht gesehen oder hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="79dd1-232">This KQL looks at external users added to teams who come from organizations that haven't been seen or added before.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
// If you want to look at users further back than the last day change this value 
let lookback_data = 1d; 
let known_orgs = ( 
TeamsData  
| where TimeGenerated > ago(data_date) 
| where Operation =~ "MemberAdded" or Operation =~ "TeamsSessionStarted" 
// Extract the correct UPN and parse our external organization domain 
| extend UPN = iif(Operation == "MemberAdded", tostring(parse_json(Members)[0].UPN), UserId) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| summarize by Organization); 
TeamsData  
| where TimeGenerated > ago(lookback_data) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| extend Organization = tostring(split(split(UPN, "_")[1], "#")[0]) 
| where isnotempty(Organization) 
| where Organization !in (known_orgs) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UPN 
```

#### <a name="external-users-who-were-added-and-then-removed"></a><span data-ttu-id="79dd1-233">Externe Benutzer, die hinzugefügt und dann entfernt wurden</span><span class="sxs-lookup"><span data-stu-id="79dd1-233">External users who were added and then removed</span></span>

<span data-ttu-id="79dd1-234">Angreifer, die bereits über den Zugriff auf einer bestimmten Ebene verfügen, können in Teams ein neues externes Konto hinzufügen, um auf Daten zuzugreifen und diese zu exfiltrieren.</span><span class="sxs-lookup"><span data-stu-id="79dd1-234">Attackers with some level of existing access may add a new external account to Teams to access and exfiltrate data.</span></span> <span data-ttu-id="79dd1-235">Sie können diesen Benutzer auch schnell wieder entfernen, um zu verbergen, dass dieser Zugriff stattgefunden hat.</span><span class="sxs-lookup"><span data-stu-id="79dd1-235">They may also quickly remove that user to hide that they made access.</span></span> <span data-ttu-id="79dd1-236">Diese Abfrage sucht nach externen Konten, die Teams hinzugefügt und schnell wieder entfernt wurden, um bei der Identifizierung verdächtigen Verhaltens zu helfen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-236">This query hunts for external accounts that are added to Teams and swiftly removed to help identify suspicious behavior.</span></span>

```kusto
// If you want to look at user added further than 7 days ago adjust this value 
let time_ago = 7d; 
// If you want to change the timeframe of how quickly accounts need to be added and removed change this value 
let time_delta = 1h; 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberAdded" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeAdded=TimeGenerated, Operation, UPN, UserWhoAdded = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid) 
| join ( 
TeamsData  
| where TimeGenerated > ago(time_ago) 
| where Operation =~ "MemberRemoved" 
| extend UPN = tostring(parse_json(Members)[0].UPN) 
| project TimeDeleted=TimeGenerated, Operation, UPN, UserWhoDeleted = UserId, TeamName, TeamGuid = tostring(Details.TeamGuid)) on UPN, TeamGuid 
| where TimeDeleted < (TimeAdded + time_delta) 
| project TimeAdded, TimeDeleted, UPN, UserWhoAdded, UserWhoDeleted, TeamName, TeamGuid 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeAdded, AccountCustomEntity = UPN 
```

#### <a name="new-bot-or-application-added"></a><span data-ttu-id="79dd1-237">Neuer Bot oder neue Anwendung hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="79dd1-237">New bot or application added</span></span>

<span data-ttu-id="79dd1-238">In Teams gibt es die Möglichkeit, Apps oder Bots in ein Team aufzunehmen, um den Funktionsumfang zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="79dd1-238">Teams has the ability to include apps or bots in a Team to extend the feature set.</span></span> <span data-ttu-id="79dd1-239">Dies umfasst auch benutzerdefinierte Apps und Bots.</span><span class="sxs-lookup"><span data-stu-id="79dd1-239">This includes custom apps and bots.</span></span> <span data-ttu-id="79dd1-240">In manchen Fällen könnte eine App oder ein Bot dazu verwendet werden, Persistenz in Teams herzustellen, ohne ein Benutzerkonto zu benötigen, sowie um auf Dateien und andere Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-240">In some cases, an app or bot could be used to establish persistence in Teams without needing a user account, as well as access files and other data.</span></span> <span data-ttu-id="79dd1-241">Diese Abfrage sucht nach Apps oder Bots, die neu in Teams sind.</span><span class="sxs-lookup"><span data-stu-id="79dd1-241">This query hunts for apps or bots that are new to Teams.</span></span>

```kusto
// If you have more than 14 days worth of Teams data change this value 
let data_date = 14d; 
let historical_bots = ( 
TeamsData 
| where TimeGenerated > ago(data_date) 
| where isnotempty(AddOnName) 
| project AddOnName); 
TeamsData 
| where TimeGenerated > ago(1d) 
// Look for add-ins we have never seen before 
| where AddOnName in (historical_bots) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = UserId 
```

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a><span data-ttu-id="79dd1-242">Benutzerkonten, die Besitzer einer großen Anzahl von Teams sind</span><span class="sxs-lookup"><span data-stu-id="79dd1-242">User accounts who are Owners of large numbers of Teams</span></span>

<span data-ttu-id="79dd1-243">Angreifer, die ihre Rechte erhöhen möchten, können sich selbst Besitzerrechte für eine große Anzahl verschiedener Teams zuweisen, während Benutzer in der Regel nur eine kleine Anzahl von Teams zu bestimmten Themen erstellen und besitzen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-243">Attackers looking to elevate their privileges may assign themselves Owner privileges of a large number of diverse teams, when, usually, users create and own a small number of teams around specific topics.</span></span> <span data-ttu-id="79dd1-244">Diese KQL-Abfrage sucht nach verdächtigem Verhalten.</span><span class="sxs-lookup"><span data-stu-id="79dd1-244">This KQL query looks for suspicious behavior.</span></span>

```kusto
// Adjust this value to change how many teams a user is made owner of before detecting 
let max_owner_count = 3; 
// Change this value to adjust how larger timeframe the query is run over. 
let time_window = 1d; 
let high_owner_count = (TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| summarize dcount(TeamName) by Member 
| where dcount_TeamName > max_owner_count 
| project Member); 
TeamsData 
| where TimeGenerated > ago(time_window) 
| where Operation =~ "MemberRoleChanged" 
| extend Member = tostring(parse_json(Members)[0].UPN)  
| extend NewRole = toint(parse_json(Members)[0].Role)  
| where NewRole == 2 
| where Member in (high_owner_count) 
| extend TeamGuid = tostring(Details.TeamGuid) 
// Uncomment the following line to map query entities is you plan to use this as a detection query 
//| extend timestamp = TimeGenerated, AccountCustomEntity = Member 
```

#### <a name="many-team-deletions-by-a-single-user"></a><span data-ttu-id="79dd1-245">Viele Löschungen von Teams durch einen einzelnen Benutzer</span><span class="sxs-lookup"><span data-stu-id="79dd1-245">Many Team deletions by a single user</span></span>

<span data-ttu-id="79dd1-246">Angreifer können Unterbrechungen auslösen und Projekte und Daten gefährden, indem sie mehrere Teams löschen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-246">Attackers can cause disruptions and jeopardize projects and data by deleting multiple teams.</span></span> <span data-ttu-id="79dd1-247">Da Teams in der Regel von einzelnen Besitzern gelöscht werden, kann das zentrale Löschen vieler Teams ein Anzeichen für Schwierigkeiten sein.</span><span class="sxs-lookup"><span data-stu-id="79dd1-247">Because teams are generally deleted by individual Owners, a central deletion of many teams can be a sign of trouble.</span></span> <span data-ttu-id="79dd1-248">Diese KQL-Abfrage sucht nach einzelnen Benutzern, die mehrere Teams löschen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-248">This KQL looks for single users who delete multiple teams.</span></span>

```kusto
 // Adjust this value to change how many Teams should be deleted before including
 let max_delete = 3;
 // Adjust this value to change the timewindow the query runs over
 let time_window = 1d;
 let deleting_users = (
 TeamsData 
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | summarize count() by UserId
 | where count_ > max_delete
 | project UserId);
 TeamsData
 | where TimeGenerated > ago(time_window)
 | where Operation =~ "TeamDeleted"
 | where UserId in (deleting_users)
 | extend TeamGuid = tostring(Details.TeamGuid)
 | project-away AddOnName, Members, Settings
 // Uncomment the following line to map query entities is you plan to use this as a detection query
 //| extend timestamp = TimeGenerated, AccountCustomEntity = UserId
```

#### <a name="expanding-your-thread-hunting-opportunities"></a><span data-ttu-id="79dd1-249">Erweitern Ihrer Möglichkeiten für die Bedrohungssuche</span><span class="sxs-lookup"><span data-stu-id="79dd1-249">Expanding your thread hunting opportunities</span></span>

<span data-ttu-id="79dd1-250">Sie können Ihre Suche erweitern, indem Sie Abfragen aus Ressourcen wie Azure Active Directory (Azure AD) oder anderen Office 365-Workloads mit ihren Teams-Abfragen kombinieren.</span><span class="sxs-lookup"><span data-stu-id="79dd1-250">You can expand your hunting by combining queries from resources like Azure Active Directory (Azure AD), or other Office 365 workloads with your Teams queries.</span></span> <span data-ttu-id="79dd1-251">Ein Beispiel hierfür ist die Kombination der Erkennung verdächtiger Muster in Azure AD-Anmeldeprotokollen (SigninLogs) mit der Verwendung dieser Informationen bei der Suche nach Teams-Besitzern.</span><span class="sxs-lookup"><span data-stu-id="79dd1-251">One example is combining detection of suspicious patterns in Azure AD SigninLogs, and using that information while hunting for Team Owners.</span></span>

```kusto
let timeRange = 1d;
let lookBack = 7d;
let threshold_Failed = 5;
let threshold_FailedwithSingleIP = 20;
let threshold_IPAddressCount = 2;
let isGUID = "[0-9a-z]{8}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{4}-[0-9a-z]{12}";
let azPortalSignins = SigninLogs
| where TimeGenerated >= ago(timeRange)
// Azure Portal only and exclude non-failure Result Types
| where AppDisplayName has "Azure Portal" and ResultType !in ("0", "50125", "50140")
// Tagging identities not resolved to friendly names
| extend Unresolved = iff(Identity matches regex isGUID, true, false);
// Lookup up resolved identities from last 7 days
let identityLookup = SigninLogs
| where TimeGenerated >= ago(lookBack)
| where not(Identity matches regex isGUID)
| summarize by UserId, lu_UserDisplayName = UserDisplayName, lu_UserPrincipalName = UserPrincipalName;
// Join resolved names to unresolved list from portal signins
let unresolvedNames = azPortalSignins | where Unresolved == true | join kind= inner (
   identityLookup ) on UserId
| extend UserDisplayName = lu_UserDisplayName, UserPrincipalName = lu_UserPrincipalName
| project-away lu_UserDisplayName, lu_UserPrincipalName;
// Join Signins that had resolved names with list of unresolved that now have a resolved name
let u_azPortalSignins = azPortalSignins | where Unresolved == false | union unresolvedNames;
let failed_signins = (u_azPortalSignins
| extend Status = strcat(ResultType, ": ", ResultDescription), OS = tostring(DeviceDetail.operatingSystem), Browser = tostring(DeviceDetail.browser)
| extend FullLocation = strcat(Location,'|', LocationDetails.state, '|', LocationDetails.city)
| summarize TimeGenerated = makelist(TimeGenerated), Status = makelist(Status), IPAddresses = makelist(IPAddress), IPAddressCount = dcount(IPAddress), FailedLogonCount = count()
by UserPrincipalName, UserId, UserDisplayName, AppDisplayName, Browser, OS, FullLocation
| mvexpand TimeGenerated, IPAddresses, Status
| extend TimeGenerated = todatetime(tostring(TimeGenerated)), IPAddress = tostring(IPAddresses), Status = tostring(Status)
| project-away IPAddresses
| summarize StartTime = min(TimeGenerated), EndTime = max(TimeGenerated) by UserPrincipalName, UserId, UserDisplayName, Status, FailedLogonCount, IPAddress, IPAddressCount, AppDisplayName, Browser, OS, FullLocation
| where (IPAddressCount >= threshold_IPAddressCount and FailedLogonCount >= threshold_Failed) or FailedLogonCount >= threshold_FailedwithSingleIP
| project UserPrincipalName);
TeamsData
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| extend Member = tostring(parse_json(Members)[0].UPN) 
| extend NewRole = toint(parse_json(Members)[0].Role) 
| where NewRole == 2
| where Member in (failed_signins)
| extend TeamGuid = tostring(Details.TeamGuid)
```

<span data-ttu-id="79dd1-252">Sie können die SigninLogs-Erkennungen auch für Teams spezifisch vornehmen, indem Sie einen Filter für nur Teams-basierte Anmeldungen hinzufügen, indem Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="79dd1-252">Also, you can make the SigninLogs detections specific to Teams by adding a filter for only Teams-based sign-ins by using:</span></span>

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

<span data-ttu-id="79dd1-253">Um die Verwendung von `where AppDisplayName starts with "Microsoft Teams"` noch besser zu erläutern, veranschaulicht die unten stehende KQL-Abfrage eine erfolgreiche Anmeldung von einer IP-Adresse und eine mit einem Fehler von einer anderen IP-Adresse, wobei der Gültigkeitsbereich aber nur Teams ist:</span><span class="sxs-lookup"><span data-stu-id="79dd1-253">To help explain using `where AppDisplayName starts with "Microsoft Teams"` further, the KQL below demonstrates a successful logon from one IP address with failure from a different IP address, but scoped only to Teams sign-ins:</span></span>

```kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName startswith "Microsoft Teams"
  | project SuccessLogonTime = TimeGenerated, UserPrincipalName, SuccessIPAddress = IPAddress, AppDisplayName, SuccessIPBlock = strcat(split(IPAddress, ".")[0], ".", split(IPAddress, ".")[1])
  | join kind= inner (
      SigninLogs 
      | where TimeGenerated >= ago(timeFrame) 
      | where ResultType !in ("0", "50140") 
      | where ResultDescription !~ "Other"  
      | where AppDisplayName startswith "Microsoft Teams"
      | project FailedLogonTime = TimeGenerated, UserPrincipalName, FailedIPAddress = IPAddress, AppDisplayName, ResultType, ResultDescription
  ) on UserPrincipalName, AppDisplayName 
  | where SuccessLogonTime < FailedLogonTime and FailedLogonTime - SuccessLogonTime <= logonDiff and FailedIPAddress !startswith SuccessIPBlock
  | summarize FailedLogonTime = max(FailedLogonTime), SuccessLogonTime = max(SuccessLogonTime) by UserPrincipalName, SuccessIPAddress, AppDisplayName, FailedIPAddress, ResultType, ResultDescription 
  | extend timestamp = SuccessLogonTime, AccountCustomEntity = UserPrincipalName, IPCustomEntity = SuccessIPAddress
```

## <a name="important-information-and-updates"></a><span data-ttu-id="79dd1-254">Wichtige Informationen und Updates</span><span class="sxs-lookup"><span data-stu-id="79dd1-254">Important information and updates</span></span>

<span data-ttu-id="79dd1-255">**Vielen Dank für die inhaltliche Zusammenarbeit an Pete Bryan, Nicholas DiCola und Matthew Lowe.**</span><span class="sxs-lookup"><span data-stu-id="79dd1-255">**Thank you for content collaboration, Pete Bryan, Nicholas DiCola, and Matthew Lowe.**</span></span> <span data-ttu-id="79dd1-256">Pete Bryan und die Personen, mit denen er zusammenarbeitet, werden weiterhin Erkennungs- und Suchabfragen für Teams entwickeln. Bleiben Sie also für Updates in Verbindung mit diesem [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs)-Repository.</span><span class="sxs-lookup"><span data-stu-id="79dd1-256">Pete Bryan and the people he collaborates with will continue to develop detection and hunting queries for Teams, so keep in touch with this [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs) repository for updates.</span></span>  <span data-ttu-id="79dd1-257">Überprüfen Sie regelmäßig auf Updates für den in diesem Artikel verwendeten [Parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) bzw. für die verwendete [Logik-App](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data).</span><span class="sxs-lookup"><span data-stu-id="79dd1-257">Monitor for updates to the [parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) and [logic app](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) used in this article.</span></span> <span data-ttu-id="79dd1-258">Sie können auch der [Azure Sentinel-Community](https://github.com/Azure/Azure-Sentinel/wiki) beitreten und daran mitwirken.</span><span class="sxs-lookup"><span data-stu-id="79dd1-258">You can also join and contribute to the [Azure Sentinel community](https://github.com/Azure/Azure-Sentinel/wiki).</span></span> <span data-ttu-id="79dd1-259">Vielen Dank!</span><span class="sxs-lookup"><span data-stu-id="79dd1-259">Thank you!</span></span> <span data-ttu-id="79dd1-260">Fröhliches Suchen.</span><span class="sxs-lookup"><span data-stu-id="79dd1-260">Happy hunting.</span></span>

[<span data-ttu-id="79dd1-261">Registrieren Ihrer Anwendung in Azure AD</span><span class="sxs-lookup"><span data-stu-id="79dd1-261">Registering your application in Azure AD</span></span>](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[<span data-ttu-id="79dd1-262">Aktivieren oder Deaktivieren der Überwachungsprotokollsuche</span><span class="sxs-lookup"><span data-stu-id="79dd1-262">Turn audit log search on or off</span></span>](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[<span data-ttu-id="79dd1-263">Was ist Azure Sentinel?</span><span class="sxs-lookup"><span data-stu-id="79dd1-263">What is Azure Sentinel</span></span>](https://docs.microsoft.com/azure/sentinel/overview)
