---
title: Teams-Vorlagen für kleine und mittelständische Unternehmen, die mit Microsoft Graph erstellt wurden
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Verwenden Sie in Microsoft Graph integrierte vordefinierte Microsoft Teams-Vorlagen, um Teams für kleine und mittelständische Unternehmen schnell und einfach zu erstellen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116993"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a>In Microsoft Graph für kleine und mittelständische Unternehmen integrierte Teams

Mit Microsoft Teams-Vorlagen können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten Apps bereitstellen.

Für kleine und mittelständische Unternehmen können Vorlagen besonders leistungsfähig sein, da sie Administratoren dabei helfen, Teams schnell in der gesamten Organisation zu implementieren. Vorlagen helfen außerdem, Benutzer zu orientieren und mit der effektiven Verwendung von Teams zu beginnen. Dieser Artikel ist für Sie da, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Organisation zuständig sind.

Wir bieten derzeit drei SMB-Vorlagen von drittanbietern, die Sie für eine Vielzahl von Situationen nutzen können. Alle Vorlagen erstellen *Private* Teams. Nachdem Sie die Teams erstellt haben und bereit sind, ein Rollout für Ihre Organisation zu erstellen, können Sie den Datenschutz auf *Org-Wide* oder *Public* festlegen. Weitere Informationen zu Teams-Vorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Teams-Vorlagen](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>Company-Wide-Vorlage
Die Company-Wide-Vorlage ist für Kommunikation und Zusammenarbeit gedacht, die für das gesamte Unternehmen relevant sind. Sie können den Kanal Allgemein für unternehmensweite Ankündigungen, Branchennachrichten oder Geschäftsleitungsbeiträge verwenden. Der Kanal "Personalwesen" ist ein hervorragender Ort, um alle personalbezogenen Aktivitäten wie Stellenangebote, onboarding für neue Mitarbeiter, Schulungen und Entwicklung zu konsolidieren. Der Kanal Fun Stuff stellt eine soziale Plattform für alle zufälligen und lustigen Beiträge zur Verfügung.

| Basisorlagentyp  | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB – <br>Unternehmensweit | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Kanäle <ul><li>Allgemein\*</li><li>Personalwesen\*</li><li>Lustiges Material\*</li></ul><br> Apps<ul><li>Unternehmensportal (Website, an den Kanal **"Personalwesen" angeheftet)** </li> </UL><br>Teameigenschaften <ul><li>Teamsichtbarkeit auf Privat gesetzt</li></ul> |

*Automatisch bevorzugte Kanäle 

Wenn Sie das Company-Wide erstellen möchten, indem Sie Standardwerte aus der vordefinierten Vorlage verwenden, stellen Sie die JSON-Darstellung des Teamobjekts im Anforderungstext fest. Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph-Artikel [zum Erstellen eines Teams.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>Anforderung 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a>Vorlage für das Führungsteam

Die Vorlage "Führungsteam" eignet sich ideal zum Erstellen eines Teams für Unternehmensleiter, um unternehmensinitiativen wie jährliche Prioritäten, Budgetbudgets, strategische Initiativen und Topkunden zu kommunizieren und zusammenzuarbeiten. Diese Vorlage enthält einen *privaten Kanal,* über den ausgewählte Benutzer zu bestimmten Themen eingeladen werden können.

| Basisorlagentyp  | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB – <br>Executives Team | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Kanäle <ul><li>Allgemein\*</li><li>Privat \*</li></ul> Apps<ul><li>OneNote (an den privaten **Kanal angeheftet)**</li> <li>Planner (an den privaten **Kanal angeheftet)** </li></ul><br>Teameigenschaften <ul><li>Teamsichtbarkeit auf Privat gesetzt</li></ul> | 

*Automatisch bevorzugte Kanäle<br>

Wenn Sie das Executives-Team erstellen möchten, indem Sie Standardwerte aus der vordefinierten Vorlage verwenden, stellen Sie die JSON-Darstellung des Teamobjekts im Anforderungstext ein. Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph-Artikel [zum Erstellen eines Teams.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>Anforderung 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>Vorlage "Abteilungsteam"

Die Teamvorlage "Abteilung" kann zum Erstellen eines Teams für einzelne Abteilungen oder für Projekte verwendet werden. Die Vorlage "Finanzteam" eignet sich ideal für alle Beiträge, Ankündigungen sowie die tägliche Zusammenarbeit und Kommunikation innerhalb der Mitglieder des Finanzteams und der Mitglieder des Führungsteams. Die Vorlage enthält einen *privaten Kanal,* über den ausgewählte Benutzer zu bestimmten Themen eingeladen werden können. Außerdem stellen wir das folgende Skript für das Finanzteam zur Verfügung, mit dem die Vorlage auf weitere Abteilungen oder bestimmte Projekte erweitert werden kann, indem Sie nach Ihren Wünschen hinzufügen, löschen oder bearbeiten. Wenn Sie beispielsweise über  eine Marketingabteilung verfügen, kann das Skript angepasst werden, indem das Team von *"Finanzen"* in *"Marketing"* umbenennet wird, um ein neues Marketingteam zu erstellen.

| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB – <br>Finanzen  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Kanäle <ul><li>Allgemein\*</li><li>Privat \*</li></ul><br> Apps<ul><li>OneNote (an den privaten **Kanal angeheftet)**</li> <li>Planner (an den privaten **Kanal angeheftet)** </li> </ul><br>Teameigenschaften <ul><li>Teamsichtbarkeit auf Privat gesetzt</li></ul> | 

*Automatisch bevorzugte Kanäle

Wenn Sie das Finanzteam erstellen möchten, indem Sie Standardwerte aus der vordefinierten Vorlage verwenden, stellen Sie die JSON-Darstellung des Teamobjekts im Anforderungstext ein. Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph-Artikel [zum Erstellen eines Teams.](/graph/api/team-post?view=graph-rest-beta)

#### <a name="request"></a>Anforderung 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a>Beispiel: Erweiterungsskript "Finanzteam"

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teams-Vorlagen in der Administratorkonsole](get-started-with-teams-templates-in-the-admin-console.md)
- [Erste Schritte mit Teams-Vorlagen](get-started-with-teams-templates.md)
- [Team erstellen](/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)