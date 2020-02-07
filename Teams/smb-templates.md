---
title: Erste Schritte mit Microsoft Teams-Vorlagen für kleine und mittelständische Unternehmen
author: kenwith
ms.author: kenwith
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
description: Erste Schritte mit Microsoft Teams-Vorlagen für kleine und mittelständische Unternehmen
ms.openlocfilehash: be42728387189f2281f892e5cc608f9e6f557b02
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837935"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a>Erste Schritte mit Microsoft Teams-Vorlagen für kleine und mittelständische Unternehmen

Mit Microsoft Teams-Vorlagen können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten apps bereitstellen.

Für kleine und mittelständische Unternehmen können Vorlagen besonders leistungsstark sein, da Sie Administratoren dabei helfen, Teams in ihrer gesamten Organisation schnell bereitzustellen. Mithilfe von Vorlagen können Sie Benutzer auch orientieren und mit der effektiven Verwendung von Teams beginnen. Dieser Artikel ist für Sie zuständig, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Organisation verantwortlich sind.

Wir bieten derzeit drei SMB-Vorlagen von First Party an, die Sie für unterschiedliche Situationen nutzen können. Alle Vorlagen werden *private* Teams erstellen. Nachdem Sie die Teams erstellt haben und bereit für das Rollout in Ihre Organisation sind, können Sie den Datenschutz je nach Bedarf auf *org-Wide* oder *Public*festlegen. Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](get-started-with-teams-templates.md).

## <a name="company-wide-template"></a>Unternehmensweite Vorlage
Die unternehmensweite Vorlage ist für Kommunikation und Zusammenarbeit vorgesehen, die für das gesamte Unternehmen relevant sind. Sie können den allgemeinen Kanal für unternehmensweite Ankündigungen, Branchen-News oder Executive-Beiträge verwenden. Der Personal Kanal ist ein großartiger Ort, um alle HR-bezogenen Aktivitäten wie Stellenangebote, neue Mitarbeiter Onboarding, Schulung und Entwicklung zu konsolidieren. Der Fun-Stuff-Kanal bietet eine soziale Plattform für alle zufällige und lustige Beiträge.

| Basis Vorlagentyp  | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>Unternehmensweit | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| Kanäle <ul><li>Allgemein\*</li><li>Personalwesen\*</li><li>Lustige Sachen\*</li></ul><br> Apps<ul><li>Unternehmens Portal (Website an den **Personal** Kanal angeheftet) </li> </UL><br>Team Eigenschaften <ul><li>Team Sichtbarkeit auf "Privat" gesetzt</li></ul> |

* Automatisch bevorzugte Kanäle 

Um das unternehmensweite Team zu erstellen, indem Sie Standardwerte aus der vordefinierten Vorlage aufnehmen, geben Sie die JSON-Darstellung des Team Objekts im Anforderungstext an. Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph- [Artikel zum Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

## <a name="executive-team-template"></a>Vorlage für das Executive-Team

Die Vorlage für das Executive-Team eignet sich hervorragend zum Erstellen eines Teams für Führungskräfte von Unternehmen, um Unternehmensinitiativen wie jährliche Prioritäten, Finanzbudgets, strategische Initiativen, Top-Kunden usw. zu kommunizieren und zusammenzuarbeiten. Diese Vorlage enthält einen *privaten* Kanal, in dem Sie ausgewählte Benutzer zu bestimmten Themen einladen können.

| Basis Vorlagentyp  | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>Führungskräfte Team | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | Kanäle <ul><li>Allgemein\*</li><li>Private\*</li></ul> Apps<ul><li>OneNote (an den **privaten** Kanal angeheftet)</li> <li>Planner (an den **privaten** Kanal angeheftet) </li></ul><br>Team Eigenschaften <ul><li>Team Sichtbarkeit auf "Privat" gesetzt</li></ul> | 

* Automatisch bevorzugte Kanäle<br>

Um das Executives-Team zu erstellen, indem Sie Standardwerte aus der vordefinierten Vorlage aufnehmen, geben Sie die JSON-Darstellung des Team Objekts im Anforderungstext an. Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph- [Artikel zum Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

#### <a name="request"></a>Anforderung 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company’s leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a>Abteilungs Team Vorlage

Die Vorlage für ein Abteilungs Team kann zum Erstellen eines Teams für einzelne Abteilungen oder für Projekte verwendet werden. Die Vorlage "Finanzteam" eignet sich ideal für alle Beiträge, Ankündigungen und tägliche Zusammenarbeit und Kommunikation innerhalb der Mitglieder des Finance-Teams (und den Mitgliedern des Executive-Teams entsprechend). Die Vorlage enthält einen *privaten* Kanal, in dem Sie ausgewählte Benutzer zu bestimmten Themen einladen können. Darüber hinaus stellen wir das unten aufgeführte Skript für das Finance-Team bereit, mit dem die Vorlage auf weitere Abteilungen oder bestimmte Projekte ausgeweitet werden kann, indem Sie Ihre Wünsche hinzufügen, löschen oder bearbeiten. Wenn Sie beispielsweise über eine *Marketing* Abteilung verfügen, können Sie das Skript anpassen, indem Sie das Team von *Finance* in *Marketing* umbenennen, um ein neues Marketing Team zu erstellen.

| Basis Vorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| SMB <br>Finanzen  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| Kanäle <ul><li>Allgemein\*</li><li>Private\*</li></ul><br> Apps<ul><li>OneNote (an den **privaten** Kanal angeheftet)</li> <li>Planner (an den **privaten** Kanal angeheftet) </li> </ul><br>Team Eigenschaften <ul><li>Team Sichtbarkeit auf "Privat" gesetzt</li></ul> | 

* Automatisch bevorzugte Kanäle

Um das Finance-Team zu erstellen, indem Sie Standardwerte aus der vordefinierten Vorlage aufnehmen, geben Sie die JSON-Darstellung des Team Objekts im Anforderungstext an. Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph- [Artikel zum Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

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

### <a name="example-finance-team-template-extension-script"></a>Beispiel: Skript zur Erweiterung der Finanz Team Vorlage

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

- [Erste Schritte mit Teams-Vorlagen](get-started-with-teams-templates.md)
- [Team erstellen](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)

