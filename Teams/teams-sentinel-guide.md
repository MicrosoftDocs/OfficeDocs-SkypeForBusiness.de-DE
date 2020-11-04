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
ms.openlocfilehash: 6aa8e733aeb3828bb1815001ba0299a9ee1aaf78
ms.sourcegitcommit: 3f465eb6eb46db008f2b69fc4c6bb425d432dfcc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48852146"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel und Microsoft Teams

Teams spielt eine zentrale Rolle sowohl bei der Kommunikation als auch bei der Datenfreigabe in der Microsoft 365 Cloud. Da der Teams-Dienst Berührungspunkte mit so vielen zugrunde liegenden Technologien in der Cloud hat, kann er sowohl von menschlicher als auch automatisierter Analyse profitieren, nicht nur wenn es um das *Suchen in Protokollen* geht, sondern auch bei der *Überwachung von Besprechungen in Echtzeit*. Azure Sentinel bietet Administratoren diese Lösungen.

> [!NOTE]
> Benötigen Sie eine Auffrischung zu Azure Sentinel? Genau so etwas finden Sie in [diesem Artikel](https://docs.microsoft.com/azure/sentinel/overview).

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel und Microsoft Teams-Aktivitätsprotokolle

Dieser Artikel befasst sich hauptsächlich mit dem Sammeln von Team-Aktivitätsprotokollen in Azure Sentinel. Abgesehen davon, dass Administratoren mithilfe von Sentinel-Arbeitsmappen und Runbooks die Sicherheitsverwaltung an einer zentralen Stelle durchführen können (einschließlich aller ausgewählten Geräte von Drittanbietern, Microsoft Threat Protection und anderen Microsoft 365-Workloads), können sie damit auch die Sicherheitsüberwachung systematisieren. Ein guter erster Schritt bei dieser Vorgehensweise ist das Sammeln der erforderlichen Protokolle für die Analyse.

> [!NOTE]
> Es kann mehr als ein Microsoft 365-Abonnement in derselben Instanz von Azure Sentinel vorkommen. Dies gestattet [Echtzeitüberwachung](https://docs.microsoft.com/azure/sentinel/livestream) und die Suche nach Bedrohungen in historischen Protokolldateien. Administratoren können mithilfe von [ressourcenübergreifenden Abfragen](https://docs.microsoft.com/azure/azure-monitor/log-query/cross-workspace-query) suchen, d.h. innerhalb einer einzelnen Ressourcengruppe, über Ressourcengruppen hinweg oder in einem anderen Abonnement.

## <a name="step-1-collect-teams-logs"></a>Schritt 1: Sammeln von Teams-Protokollen

Dieser Abschnitt besteht aus drei Teilen:

1. Aktivieren von Überwachungsprotokollen in **Microsoft 365** (M365).
2. Registrieren einer App bei **Microsoft Azure** , um die Authentifizierung und Autorisierung für die Protokollsammlung zuzulassen.
3. Registrieren des API-Abonnements, das die Protokollsammlung über die M365-API mittels **PowerShell** zulassen soll.

### <a name="enable-audit-logs-in-m365"></a>Aktivieren von Überwachungsprotokollen in M365

Da Teams Aktivitäten über M365 protokolliert, werden Überwachungsprotokolle nicht standardmäßig gesammelt. Aktivieren Sie diese Funktion mithilfe [dieser Schritte](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0). Teams-Daten werden in der M365-Überwachung unter *Audit.General* gesammelt.

### <a name="register-an-app-in-microsoft-azure-for-log-collection"></a>Registrieren einer App bei Microsoft Azure für die Protokollsammlung

> [!TIP]
> Bevor Sie beginnen, müssen Sie Ihre **Anwendungs-ID/Client-ID** und ihre **Mandanten-ID** für die spätere Verwendung aufzeichnen. Stellen Sie sicher, dass Sie sie erfassen, während Sie die unten beschriebenen Schritte zur App-Registrierung absolvieren. Beide IDs werden angezeigt.
>- Nachdem Ihre App erstellt wurde, klicken Sie auf der Schnellstart-Randleiste auf „App-Registrierung“, suchen Sie den Anzeigenamen Ihrer neuen App, und kopieren Sie die Anwendungs (Client)-ID.
>- Klicken Sie auf der Schnellstart-Randleiste auf „Übersicht“, und kopieren Sie die Verzeichnis (Mandanten)-ID.

Authentifizieren und autorisieren Sie eine Azure Active Directory-App (Azure AD) für das Sammeln von Protokolldaten aus der API.

1. Navigieren Sie im Azure-Portal zum Blatt *Azure AD*.
2. Klicken Sie auf der Schnellstart-Randleiste auf *App-Registrierungen*.
3. Wählen Sie *Neue Registrierung* aus.
4. Benennen Sie Ihre App zum Sammeln von Teams-Protokollen, und klicken Sie auf *Registrieren*.
5. Klicken Sie entlang dieses Pfads auf: *API-Berechtigungen* > *Berechtigung hinzufügen* > *Office 365-Verwaltungs-APIs* > *Anwendungsberechtigungen*.
6. Erweitern Sie den Aktivitätsfeed, und aktivieren Sie *ActivityFeed.Read*.
7. Wählen Sie hier *Administratoreinwilligung erteilen* aus. Klicken Sie auf „Ja“, wenn Sie gefragt werden, ob Sie das möchten.
8. Klicken Sie auf der Randleiste auf *Zertifikate und Geheimnisse* und dann auf die Schaltfläche *Neuer geheimer Clientschlüssel*.
9. Geben Sie im Fenster „Neuer geheimer Clientschlüssel“ eine Beschreibung für den neuen geheimen Clientschlüssel ein, stellen Sie sicher, dass Sie als „Ablauf“ den Wert „Nie“ auswählen, und klicken Sie auf *Hinzufügen*.

> [!IMPORTANT]
> Es ist von **kritischer** Bedeutung, den neuen geheimen Clientschlüssel in einen Kennwort-Manager-Eintrag zu kopieren, der den Namen der neu erstellten App trägt. Sie können nicht mehr dorthin zurückkehren, um sich dieses Geheimnis anzusehen, nachdem das Azure-Blatt geschlossen wurde ( *Blatt* (blade) ist in Azure die Bezeichnung für „Fenster“).

### <a name="register-the-api-with-powershell-to-collect-teams-logs"></a>Registrieren der API bei PowerShell zum Sammeln von Team-Protokollen

Der letzte Schritt bei der Einrichtung besteht darin, das API-Abonnement zu sammeln und zu registrieren, damit Sie Ihre Protokolldaten sammeln können. Dies geschieht über PowerShell-REST-Aufrufe der M365-Verwaltungsaktivitäts-API.

Halten Sie die Werte für die **Anwendungs (Client)-ID** , den neuen **geheimen Clientschlüssel** , Ihre **URL-Domäne für M365** und die **Verzeichnis (Mandanten)-ID** bereit, um sie unten in dem PowerShell-Cmdlet bereitzustellen.

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

## <a name="step-2-deploy-a-sentinel-playbook-to-ingest-the-teams-logs"></a>Schritt 2: Bereitstellen eines Sentinel-Playbooks zum Erfassen der Teams-Protokolle

Azure Sentinel-Playbooks (auch als Logik-Apps bezeichnet) gestatten Azure das Erfassen Ihrer gesammelten Teams-Daten. Die Logik-App fragt Office 365 ab, um die Überwachungsdaten zu finden, die es in den Azure Sentinel-Arbeitsbereich schreibt.

Verwenden Sie [diese](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data) ARM-Vorlage, um Ihr Sentinel-Playbook bereitzustellen.

Aspekte, die Beachtung verdienen:

1. Sie müssen die ARM-Vorlage durchgehen und bestimmte Werte durch Werte ersetzen, die für Ihre eigene Umgebung geeignet sind.
2. Sie müssen zwischen der Erfassung von Protokollen und dem Anzeigen von Ergebnissen in Azure Sentinel Zeit vergehen lassen.

   Warten Sie 5 bis 10 Minuten, weil sonst, wenn es innerhalb der letzten 5 Minuten keine Daten vorhanden waren, eine Fehlermeldung angezeigt wird. Überprüfen Sie die Überwachungsprotokolle, und denken Sie daran, dass, weil sich die Teams-Informationen in den „Audit.General“-Ereignissen befinden, in denen mehr als die Teams-Protokolle gesammelt wird, die Ergebnisse innerhalb von 5 bis 10 Minuten auf Systemen angezeigt werden sollten, die gerade verwendet werden. Wenn Sie eine Textumgebung verwenden, stellen Sie sicher, dass Sie Teams verwenden, um die Protokollierung zu generieren.

![Eine Grafik, die die Logik-App-Klassen zeigt.](media/tracyp-teams-sentinel-logic-app.png#thumbnail)

 <p><details><summary> Erläuterung der Aktionen in der Grafik: 
  </summary>

  • „Wiederholung“ ist der Logik-App-Trigger, der den Workflow veranlasst, dass er stündlich ausgeführt wird.
  <p>
• Die Aktion „Aktuelle Zeit“ ist sehr einfach und ruft lediglich die aktuelle Uhrzeit ab.
  <p>
• „Variable initialisieren“ erstellt eine Variable namens „NextPage“ und legt diese auf „1“ fest. Diese wird später verwendet, um die Paginierung aus der O365-API zu verarbeiten.
  <p>
• „Variable 2 initialisieren“ erstellt eine leere Variable namens „Start Time“ (Startzeit).
  <p>
• „Abfrage ausführen und Ergebnisse auflisten“ ist eine Azure Monitor-Aktion, die im Arbeitsbereich das letzte O365-Protokoll abfragt, das von der Logik-App eingegeben wurde.
  <p>
• „Bedingung 4“ wird verwendet, um zu überprüfen, ob die Abfrage „Abfrage ausführen und Ergebnisse auflisten“ Daten zurückgegeben hat. Dies geschieht, um zu überprüfen, ob dies das erste Mal ist, dass die Logik-App verwendet wurde. Wenn keine Daten zurückgegeben werden, wird die Variable „StartTime“ auf „Now – 24 Hours“ (Jetzt – 24 Stunden) festgelegt. Wenn Daten zurückgegeben werden, wird „StartTime“ auf die „TimeGenerated“ des letzten Datensatzes festgelegt. Dies geschieht, damit die Abfrage mit der Abfrage der O365-API Daten ab dem letzten Eintrag bis jetzt abrufen kann, oder innerhalb der letzten 24 Stunden, wenn dies die erste Ausführung ist.
  <p>
• „Variable 3 initialisieren“ erstellt eine Variable namens „AvailableUri“ (Verfügbarer URI). Hierbei handelt es sich um eine Zeichenfolge mit der URL, die mit „StartTime“ und „CurrentTime“ als Start- bzw. Endzeit erstellt wurde.
  <p>
• Die Bedingung „Until“ (Bis) ist eine Schleife, durch die die Logik-App weiterhin die API abrufen kann, um festzustellen, ob weitere Daten vorhanden sind (Paginierung). Solange die Variable „NextPage“ (Nächste Seite) den Wert „1“ hat, wird die Schleife fortgesetzt. Später wird diese Variable aktualisiert, wenn keine weiteren Seiten mehr zum Abrufen vorhanden sind.
  <p>
• Innerhalb der „Until“-Schleife stellt der erste HTTP-Schritt eine Verbindung mit dem „AvailableURI“ her. Dieser URI gibt eine Liste verfügbarer Inhalte und der einzelnen Inhalts-URIs zurück. Weitere Informationen zu dieser Funktionsweise finden Sie unter dieser URL: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Als Nächstes wird ein Test ausgeführt, um sicherzustellen, dass Daten zurückgegeben werden. Mit der „Condition“ (Bedingung) wird überprüft, ob die Länge des Texts „0“ beträgt. Ist dies der Fall, gibt es keine Daten, die in Log Analytics geschrieben werden könnten. Ist der Wert größer als 0, sind zu verarbeitende Daten vorhanden.
  <p>
• Wenn Daten erkannt werden, müssen diese als Nächstes verarbeitet werden. „JSON analysieren“ definiert ein Schema der zurückgegebenen Daten. Damit können Logik-Apps die analysierten Daten in späteren Schritten als dynamische Inhalte verwenden.
  <p>
• Da es sich bei der zurückgegebenen Liste verfügbarer Daten um ein Array handelt, wird eine „For Each“-Aktion verwendet, um die Liste der verfügbaren Inhalte als Schleife zu durchlaufen.
  <p>
• Als Nächstes wird der Inhalt extrahiert.  HTTP wird erneut verwendet, um den „contentUri“ (eine dynamische Eigenschaft, die mittels „JSON analysieren“ erstellt wurde) abzurufen, der die URL der abzurufenden Daten ist.
  <p>
• „JSON analysieren“ auch verwendet, um die zurückgegebenen Daten zu analysieren. Einige Beispielinhalte können Sie unter dieser URL finden: https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#list-available-content.
  <p>
• Die zurückgegebenen Daten sind ebenfalls ein Array. Hier kann auch eine „For Each“-Schleife verwendet werden. In dieser Schleife nimmt der Workflow das aktuelle Datenelement und verwendet die Aktion „Daten senden“, um die Daten in Log Analytics zu schreiben.
  <p>
• Da es mehrere Seiten verfügbarer Inhalte geben kann, wird mit einer Bedingung überprüft, ob der „NextPageUri“ nicht NULL ist. Wenn er NULL oder leer ist, wird „NextPage“ auf „0“ festgelegt, wodurch die „Until“-Schleife beendet wird. Enthält er eine URL, wird die Variable „AvaibleUri“ auf diese URL aktualisiert. Auf diese Weise wird bei der nächsten Ausführung der „Until“-Schleife die nächste verfügbare URL verwendet, nicht die Anfangs-URL.

  </details>

> [!TIP]
> Sie können stattdessen eine *Azure-Funktion* verwenden, um diese Protokolle zu erfassen, und wenn Sie dies tun, finden Sie die Informationen zum Bereitstellen [hier](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20Data) oder [hier](https://github.com/Azure/Azure-Sentinel/tree/master/DataConnectors/O365%20DataCSharp), je nach Ihren Wünschen.

Während der Connector ausgeführt wird (egal welche der obigen Optionen Sie ausgewählt haben), sollte im Azure Sentinel-Arbeitsbereich eine benutzerdefinierte Tabelle namens „O365API_CL“ angezeigt werden. Diese nimmt Ihre Teams-Protokolle auf.

## <a name="step-3-use-sentinel-to-monitor-microsoft-teams"></a>Schritt 3: Verwenden von Sentinel zum Überwachen von Microsoft Teams

Die Identität ist ein wichtiger zu überwachender Angriffsvektor, wenn es um Microsoft Teams geht. Da Azure Active Directory (Azure AD) die Unterstützung des Microsoft 365-Verzeichnisses, einschließlich Teams, ist, ist das Sammeln von und Suchen nach Bedrohungen in Azure AD-Protokollen im Zusammenhang mit Authentifizierung hilfreich, um verdächtiges Verhalten in Bezug auf Identitäten zu erfassen. Sie können den integrierten Connector verwenden, um Azure AD-Daten in Azure Sentinel zu pullen, und diese [Erkennungs](https://github.com/Azure/Azure-Sentinel/tree/master/Detections/SigninLogs)- und [Such](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/SigninLogs)-Abfragen, um nach Problemen zu suchen.

In Bezug auf für Microsoft Teams spezifische Angriffe, z. B. die Bedrohung von Daten, verfügt Azure Sentinel auch über Mittel, um diese zu überwachen und sie aufzuspüren.

### <a name="create-a-parser-for-your-data"></a>Erstellen eines Parsers für Ihre Daten

Der erste Schritt, um die große Menge gesammelter Daten sinnvoll zu interpretieren, besteht darin, ihm durch Analyse Bedeutung zu verleihen. Dies erfolgt mittels einer KQL-Funktion (Kusto Query Language), wodurch sich die Daten einfacher verwenden lassen.

> [!NOTE]
> KQL-Funktionen sind KQL-Abfragen, die als Datentyp „Funktion“ gespeichert werden. KQL-Funktionen besitzen einen Alias, der in Sentinel in das Abfragefeld eingegeben werden kann, um die Abfrage schnell erneut auszuführen. Weitere Informationen zu KQL-Funktionen und zum Erstellen einer Parser-Funktion finden Sie in [diesem Tech-Community-Artikel](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).
 
 Der folgende Parser ist ein anpassbares Beispiel, das auf die Auswahl einer Teilmenge der Office 365-Verwaltungs-API-Felder abzielt, die für *Teams* relevant sind. Außerdem gibt es ein empfohlenes [GitHub](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) für Parser, aber der nachstehende Parser kann geändert werden, um unterschiedliche Anforderungen und Vorlieben zu erfüllen.

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
 Speichern Sie den Parser als KQL-Funktion mit dem Alias „TeamsData“. Er wird in den folgenden Abfragen verwendet. Details zum Konfigurieren und Verwenden einer KQL-Funktion als Parser finden Sie in diesem [Tech-Community-Artikel](https://techcommunity.microsoft.com/t5/azure-sentinel/using-kql-functions-to-speed-up-analysis-in-azure-sentinel/ba-p/712381).

## <a name="helpful-hunting-kql-queries"></a>Hilfreiche KQL-Suchabfragen

Verwenden Sie diese Abfragen, um sich mit Ihren Teams-Daten und der Teams-Umgebung vertraut zu machen. Die Kenntnis, wie die Umgebung aussehen und sich verhalten sollte, ist ein guter erster Schritt, um verdächtige Aktivitäten zu erkennen. Von hier aus können Sie weiter zur Bedrohungssuche verzweigen.

#### <a name="federated-external-users-query"></a>Abfrage für externe Verbundbenutzer

Rufen Sie die Liste der Teams-Sites ab, auf denen es externe Verbundbenutzer gibt. Diese Benutzer verfügen über einen Domänennamen bzw. ein UPN-Suffix, der/das *nicht* im Besitz Ihrer Organisation ist. In dieser Beispielabfrage besitzt die Organisation „contoso.com“.

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
> Informationen zu den Zugriffstypen „Extern“ und „Gast“ in Teams finden Sie in [diesem Artikel](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations) oder im Abschnitt *Teilnehmertypen* des [Sicherheitshandbuchs für Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide).

#### <a name="who-recently-joined--whose-role-changed"></a>Jüngste Beitritte/Jüngste Rollenänderungen

Fragen Sie einen bestimmten Benutzer ab, um zu überprüfen, ob er einem Teams-Kanal in den letzten 7 Tagen oder innerhalb einer Woche hinzugefügt wurde:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members contains "UserName"
```

Wurde die Rolle eines Benutzers in den letzten 7 Tagen für ein Team geändert:

```kusto
TeamsData
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| where Members contains "Role" and Members contains "1"
```

#### <a name="external-users-from-unknown-or-new-organizations"></a>Externe Benutzer aus unbekannten oder neuen Organisationen

In Teams können Sie Ihrer Umgebung oder Ihren Kanälen externe Benutzer hinzufügen. Organisationen verfügen häufig über eine begrenzte Anzahl wichtiger Partnerschaften und fügen Benutzer aus dem Kreis dieser Partner hinzu. Diese KQL-Abfrage sucht nach externen Benutzern, die Teams hinzugefügt wurden, die aus Organisationen stammen, die zuvor noch nicht gesehen oder hinzugefügt wurden.

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

#### <a name="external-users-who-were-added-and-then-removed"></a>Externe Benutzer, die hinzugefügt und dann entfernt wurden

Angreifer, die bereits über den Zugriff auf einer bestimmten Ebene verfügen, können in Teams ein neues externes Konto hinzufügen, um auf Daten zuzugreifen und diese zu exfiltrieren. Sie können diesen Benutzer auch schnell wieder entfernen, um zu verbergen, dass dieser Zugriff stattgefunden hat. Diese Abfrage sucht nach externen Konten, die Teams hinzugefügt und schnell wieder entfernt wurden, um bei der Identifizierung verdächtigen Verhaltens zu helfen.

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

#### <a name="new-bot-or-application-added"></a>Neuer Bot oder neue Anwendung hinzugefügt

In Teams gibt es die Möglichkeit, Apps oder Bots in ein Team aufzunehmen, um den Funktionsumfang zu erweitern. Dies umfasst auch benutzerdefinierte Apps und Bots. In manchen Fällen könnte eine App oder ein Bot dazu verwendet werden, Persistenz in Teams herzustellen, ohne ein Benutzerkonto zu benötigen, sowie um auf Dateien und andere Daten zuzugreifen. Diese Abfrage sucht nach Apps oder Bots, die neu in Teams sind.

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

#### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Benutzerkonten, die Besitzer einer großen Anzahl von Teams sind

Angreifer, die ihre Rechte erhöhen möchten, können sich selbst Besitzerrechte für eine große Anzahl verschiedener Teams zuweisen, während Benutzer in der Regel nur eine kleine Anzahl von Teams zu bestimmten Themen erstellen und besitzen. Diese KQL-Abfrage sucht nach verdächtigem Verhalten.

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

#### <a name="many-team-deletions-by-a-single-user"></a>Viele Löschungen von Teams durch einen einzelnen Benutzer

Angreifer können Unterbrechungen auslösen und Projekte und Daten gefährden, indem sie mehrere Teams löschen. Da Teams in der Regel von einzelnen Besitzern gelöscht werden, kann das zentrale Löschen vieler Teams ein Anzeichen für Schwierigkeiten sein. Diese KQL-Abfrage sucht nach einzelnen Benutzern, die mehrere Teams löschen.

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

#### <a name="expanding-your-thread-hunting-opportunities"></a>Erweitern Ihrer Möglichkeiten für die Bedrohungssuche

Sie können Ihre Suche erweitern, indem Sie Abfragen aus Ressourcen wie Azure Active Directory (Azure AD) oder anderen Office 365-Workloads mit ihren Teams-Abfragen kombinieren. Ein Beispiel hierfür ist die Kombination der Erkennung verdächtiger Muster in Azure AD-Anmeldeprotokollen (SigninLogs) mit der Verwendung dieser Informationen bei der Suche nach Teams-Besitzern.

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

Sie können die SigninLogs-Erkennungen auch für Teams spezifisch vornehmen, indem Sie einen Filter für nur Teams-basierte Anmeldungen hinzufügen, indem Sie Folgendes verwenden:

```kusto
| where AppDisplayName startswith "Microsoft Teams"
```

Um die Verwendung von `where AppDisplayName starts with "Microsoft Teams"` noch besser zu erläutern, veranschaulicht die unten stehende KQL-Abfrage eine erfolgreiche Anmeldung von einer IP-Adresse und eine mit einem Fehler von einer anderen IP-Adresse, wobei der Gültigkeitsbereich aber nur Teams ist:

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

## <a name="important-information-and-updates"></a>Wichtige Informationen und Updates

**Vielen Dank für die inhaltliche Zusammenarbeit an Pete Bryan, Nicholas DiCola und Matthew Lowe.** Pete Bryan und die Personen, mit denen er zusammenarbeitet, werden weiterhin Erkennungs- und Suchabfragen für Teams entwickeln. Bleiben Sie also für Updates in Verbindung mit diesem [GitHub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs)-Repository.  Überprüfen Sie regelmäßig auf Updates für den in diesem Artikel verwendeten [Parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) bzw. für die verwendete [Logik-App](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data). Sie können auch der [Azure Sentinel-Community](https://github.com/Azure/Azure-Sentinel/wiki) beitreten und daran mitwirken. Vielen Dank! Fröhliches Suchen.

[Registrieren Ihrer Anwendung in Azure AD](https://docs.microsoft.com/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[Aktivieren oder Deaktivieren der Überwachungsprotokollsuche](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off?view=o365-worldwide&viewFallbackFrom=o365-worldwide%C2%A0)

[Was ist Azure Sentinel?](https://docs.microsoft.com/azure/sentinel/overview)
