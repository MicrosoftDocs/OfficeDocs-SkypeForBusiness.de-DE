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
ms.openlocfilehash: c3b2c37f7f3731b34abb5337bf954250e0c3564d
ms.sourcegitcommit: 046b020cee8af00a1d0e5f5866f847d42e8ad9a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51712767"
---
# <a name="azure-sentinel-and-microsoft-teams"></a>Azure Sentinel und Microsoft Teams

> [!IMPORTANT]
> Azure Sentinel hat jetzt einen integrierten Connector. Weitere Informationen finden Sie unter [Office 365-Protokolle mit Azure Sentinel verbinden](/azure/sentinel/connect-office-365). Dies ist der empfohlene Weg zur Sammlung dieser Protokolle und ersetzt die nachfolgend beschriebenen Sammlungsmethoden.

Microsoft Teams spielt eine zentrale Rolle bei der Kommunikation und der Datenfreigabe in der Microsoft 365 Cloud. Da der Microsoft Teams-Dienst Berührungspunkte mit so vielen Technologien in der Cloud hat, kann er sowohl von menschlicher als auch automatisierter Analyse profitieren. Dies gilt sowohl für *die Suche in Protokollen* als auch für die *Echtzeit-Überwachung von Besprechungen*. Azure Sentinel bietet Administratoren diese Lösungen.

> [!NOTE]
> Benötigen Sie eine Auffrischung zu Azure Sentinel? Genau so etwas finden Sie in [diesem Artikel](/azure/sentinel/overview).

## <a name="sentinel-and-microsoft-teams-activity-logs"></a>Sentinel und Microsoft Teams-Aktivitätsprotokolle

Dieser Artikel befasst sich hauptsächlich mit dem Sammeln von Team-Aktivitätsprotokollen in Azure Sentinel.

Sentinel ermöglicht Administratoren die Sicherheitsverwaltung an einem zentralen Ort. Dies schließt die Verwaltung von Folgendem ein:

- Geräte von Drittanbietern
- Microsoft Threat Protection
- Microsoft 365-Workloads

Sentinel-Arbeitsmappen und Runbooks ermöglichen eine *systematische* Sicherheitsüberwachung. Ein guter erster Schritt in diesem Prozess ist das Sammeln der zu analysierenden Protokolle.

> [!NOTE]
> Es kann mehr als ein Microsoft 365-Abonnement in derselben Instanz von Azure Sentinel vorkommen. Dies gestattet [Echtzeitüberwachung](/azure/sentinel/livestream) und die Suche nach Bedrohungen in historischen Protokolldateien. Administratoren können mithilfe von [ressourcenübergreifenden Abfragen](/azure/azure-monitor/log-query/cross-workspace-query) Suchen durchführen, d.h. innerhalb einer einzelnen Ressourcengruppe, über Ressourcengruppen hinweg oder in einem anderen Abonnement.

## <a name="step-1-collect-teams-logs-enable-audit-logs-in-microsoft-365"></a>Schritt 1: Sammeln von Microsoft Teams-Protokollen: Aktivieren von Überwachungsprotokollen in Microsoft 365

Da Microsoft Teams Aktivitäten über Microsoft 365 protokolliert, werden Überwachungsprotokolle nicht standardmäßig gesammelt. Aktivieren Sie diese Funktion mithilfe [dieser Schritte](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off). Microsoft Teams-Daten werden in der Microsoft 365-Überwachung unter *Audit.General* erfasst.

## <a name="step-2-connect-office-365-logs-to-azure-sentinel"></a>Schritt 2: Verbinden von Office 365-Protokollen mit Azure Sentinel

Azure Sentinel bietet einen integrierten Connector für Office 365-Protokolle, der es Ihnen ermöglicht, Microsoft Teams-Daten zusammen mit anderen Office 365-Daten über Azure Sentinel zu erfassen.
 
Aktivieren Sie in Azure Sentinel den Office 365-Datenconnector. Weitere Informationen finden Sie in der [Dokumentation zu Azure Sentinel](/azure/sentinel/connect-office-365).

## <a name="helpful-hunting-kql-queries"></a>Hilfreiche KQL-Suchabfragen

Verwenden Sie diese Abfragen, um sich mit Ihren Teams-Daten und der Teams-Umgebung vertraut zu machen. Die Kenntnis, wie die Umgebung aussehen und sich verhalten sollte, ist ein guter erster Schritt, um verdächtige Aktivitäten zu erkennen. Von hier aus können Sie weiter zur Bedrohungssuche verzweigen.

### <a name="federated-external-users-query"></a>Abfrage für externe Verbundbenutzer

Rufen Sie die Liste der Teams-Sites ab, auf denen es externe Verbundbenutzer gibt. Diese Benutzer weisen einen Domänennamen und/oder ein UPN-Suffix auf, der/das nicht im Besitz Ihrer Organisation ist.

In dieser Beispielabfrage besitzt die Organisation „contoso.com“.

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where parse_json(Members)[0].Role == 3
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
```

> [!TIP]
> Informationen zu den Zugriffstypen „Extern“ und „Gast“ in Microsoft Teams finden Sie unter [Kommunizieren mit Benutzern aus anderen Organisationen](communicate-with-users-from-other-organizations.md) oder im Abschnitt [Teilnehmertypen](teams-security-guide.md#participant-types) des Sicherheitshandbuchs für Microsoft Teams.

### <a name="who-recently-joined--whose-role-changed"></a>Jüngste Beitritte/Jüngste Rollenänderungen

Führen Sie eine Abfrage zu einem bestimmten Benutzer durch, um zu überprüfen, ob er einem Microsoft Teams-Kanal in den letzten sieben Tagen oder innerhalb einer Woche hinzugefügt wurde:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberAdded"
| where Members has "<DisplayName>" or Members has "<UserPrincipalName>"
| project TeamName, Operation, UserId, Members
```

Führen Sie eine Abfrage dazu durch, ob die Rolle eines Benutzers in den letzten sieben Tagen für ein Team geändert wurde:

```Kusto
OfficeActivity
| where TimeGenerated > ago(7d)
| where Operation =~ "MemberRoleChanged"
| project TeamName, Operation, UserId, Members
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '1'
``` 

### <a name="external-users-from-unknown-or-new-organizations"></a>Externe Benutzer aus unbekannten oder neuen Organisationen

In Teams können Sie Ihrer Umgebung oder Ihren Kanälen externe Benutzer hinzufügen. Organisationen verfügen häufig über eine begrenzte Anzahl wichtiger Partnerschaften und fügen Benutzer aus dem Kreis dieser Partner hinzu. Diese KQL-Abfrage sucht nach externen Benutzern, die Teams hinzugefügt wurden, die aus Organisationen stammen, die zuvor noch nicht gesehen oder hinzugefügt wurden.

Sehen Sie sich für weitere Informationen die Abfrage im [Azure Sentinel-Community-Github](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/ExternalUserFromNewOrgAddedToTeams.yaml) an.

### <a name="external-users-who-were-added-and-then-removed"></a>Externe Benutzer, die hinzugefügt und dann entfernt wurden

Angreifer, die bereits über den Zugriff auf einer bestimmten Ebene verfügen, können in Teams ein neues externes Konto hinzufügen, um auf Daten zuzugreifen und diese zu exfiltrieren. Sie können diesen Benutzer auch schnell wieder entfernen, um zu verbergen, dass dieser Zugriff stattgefunden hat. Diese Abfrage sucht nach externen Konten, die Teams hinzugefügt und schnell wieder entfernt wurden, um bei der Identifizierung verdächtigen Verhaltens zu helfen.

Sehen Sie sich für weitere Informationen die Abfrage im [Azure Sentinel-Community-Github](https://github.com/Azure/Azure-Sentinel/blob/master/Detections/OfficeActivity/ExternalUserAddedRemovedInTeams.yaml) an.

### <a name="new-bot-or-application-added"></a>Neuer Bot oder neue Anwendung hinzugefügt

Microsoft Teams kann Apps oder Bots in einem Team enthalten, um die Featuresammlung zu erweitern (einschließlich benutzerdefinierter Apps und Bots). In manchen Fällen kann eine App oder ein Bot dazu verwendet werden, *Persistenz* in Microsoft Teams herzustellen, ohne ein Benutzerkonto zu benötigen, und sie können auf Dateien und andere Daten zugreifen. Diese Abfrage sucht nach Apps oder Bots, die neu in Microsoft Teams sind.

Sehen Sie sich für weitere Informationen die Abfrage im [Azure Sentinel-Community-Github](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/NewBotAddedToTeams.yaml) an.

### <a name="user-accounts-who-are-owners-of-large-numbers-of-teams"></a>Benutzerkonten, die Besitzer einer großen Anzahl von Teams sind

Angreifer, die ihre Zugriffsrechte erweitern möchten, könnten sich selbst Besitzerrechte für eine große Anzahl verschiedener Teams zuweisen. *Normalerweise* erstellen und besitzen Benutzer ein paar Teams zu bestimmten Themen. Diese KQL-Abfrage sucht nach verdächtigem Verhalten.

Sehen Sie sich für weitere Informationen die Abfrage im [Azure Sentinel-Community-Github](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultiTeamOwner.yaml) an.

### <a name="many-team-deletions-by-a-single-user"></a>Viele Löschungen von Teams durch einen einzelnen Benutzer

Angreifer können Unterbrechungen auslösen und Projekte und Daten gefährden, indem sie mehrere Teams löschen. Da Teams in der Regel von einzelnen Besitzern gelöscht werden, kann das zentrale Löschen vieler Teams ein Anzeichen für Schwierigkeiten sein. Diese KQL-Abfrage sucht nach einzelnen Benutzern, die mehrere Teams löschen.

Sehen Sie sich für weitere Informationen die Abfrage im [Azure Sentinel-Community-Github](https://github.com/Azure/Azure-Sentinel/blob/master/Hunting%20Queries/OfficeActivity/MultipleTeamsDeletes.yaml) an.

### <a name="expanding-your-threat-hunting-opportunities"></a>Erweitern Ihrer Möglichkeiten für die Bedrohungssuche

Sie können Abfragen aus Ressourcen wie Azure Active Directory (Azure AD) oder anderen Office 365-Workloads mit Microsoft Teams-Abfragen kombinieren. Ein Beispiel hierfür ist die Verwendung der Informationen aus einer Suche nach verdächtigen Mustern in Azure AD-Anmeldeprotokollen (SigninLogs) bei der Suche nach Teams-Besitzern.

```Kusto
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
OfficeActivity
| where TimeGenerated > ago(time_window)
| where Operation =~ "MemberRoleChanged"
| mv-expand bagexpansion=array Members
| evaluate bag_unpack(Members)
| where Role == '2'
| where Members in (failed_signins)
```

Sie können die SigninLogs-Erkennungen auch auf Microsoft Teams zuschneiden, indem Sie einen Filter für nur Microsoft Teams-basierte Anmeldungen hinzufügen. Verwenden Sie hierfür Folgendes:

```Kusto
| where AppDisplayName has 'Teams'
```

Um die Verwendung von *wo besitzt AppDisplayName Teams* noch besser zu erläutern, veranschaulicht die KQL-Abfrage hier unten eine erfolgreiche Anmeldung von einer IP-Adresse und eine mit einem Fehler von einer anderen IP-Adresse, jedoch *nur* auf Microsoft Teams-Anmeldungen eingegrenzt:

```Kusto
let timeFrame = 1d;
let logonDiff = 10m;
SigninLogs 
  | where TimeGenerated >= ago(timeFrame) 
  | where ResultType == "0" 
  | where AppDisplayName has "Teams"
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

**Vielen Dank für die inhaltliche Zusammenarbeit an Pete Bryan, Nicholas DiCola und Matthew Lowe.** Pete Bryan und die Personen, mit denen er zusammenarbeitet, werden weiterhin Erkennungs- und Suchabfragen für Microsoft Teams entwickeln.

Halten Sie sich über Updates über dieses [Git Hub](https://github.com/Azure/Azure-Sentinel/tree/master/Hunting%20Queries/TeamsLogs)-Repository auf dem Laufenden.

Halten Sie regelmäßig Ausschau nach Updates für den in diesem Artikel verwendeten [Parser](https://github.com/Azure/Azure-Sentinel/blob/master/Parsers/Teams_parser.txt) bzw. für die verwendete [Logik-App](https://github.com/Azure/Azure-Sentinel/tree/master/Playbooks/Get-O365Data).

Sie sollten auch der [Azure Sentinel-Community](https://github.com/Azure/Azure-Sentinel/wiki) beitreten (und daran mitwirken). Wir sind sehr an Feedback zu diesem Artikel interessiert. Nutzen Sie also bitte die Feedbackoption weiter unten. Vielen Dank und erfolgreiche Suche!

[Registrieren Ihrer Anwendung in Azure AD](/skype-sdk/ucwa/registeringyourapplicationinazuread%C2%A0%20%20%C2%A0)

[Aktivieren oder Deaktivieren der Überwachungsprotokollsuche](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)

[Was ist Azure Sentinel?](/azure/sentinel/overview)
