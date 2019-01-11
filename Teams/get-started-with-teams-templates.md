---
title: Erste Schritte mit Teams Vorlagen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Erfahren Sie, wie Teams Vorlagen verwenden, um ein Team mit vordefinierten Kanälen zu erstellen.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801464"
---
# <a name="get-started-with-teams-templates"></a>Erste Schritte mit Teams Vorlagen 

Teams Vorlagen werden vor dem Definitionen von ein Team Struktur entwickelt, um eine geschäftlicher Bedarf oder ein Projekt erstellt. Vorlagen für Teams können schnell und erstellen umfassender Zusammenarbeit Leerzeichen mit Kanäle für verschiedene Themen und Vorinstallieren von apps in unternehmenswichtige Inhalte und Dienste abrufen. Teams Vorlagen bieten eine vordefinierte Teamstruktur, die Sie auf einfache Weise konsistent Teams innerhalb Ihrer Organisation helfen. 

In diesem Artikel wird die Eigenschaften, die in Vorlagen, welche Basisvorlage definiert werden können, sind, erläutert, und wie Sie verwenden können, Beispiel wenige Anforderungen an ein Team aus einer Vorlage zu erstellen.
 
Dieser Artikel ist für Sie, wenn Sie sind:

- Verantwortlich für die Planung, Bereitstellung und Verwaltung mehrerer Teams innerhalb Ihrer Organisation<br>
- Ein Entwickler aus, um ein Team programmgesteuert mit vordefinierten Kanäle und apps erstellen werden soll 

## <a name="teams-template-capabilities"></a>Teams Vorlage Funktionen

Die meisten Eigenschaften in einem Team sind enthalten und von Vorlagen unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Die folgende Tabelle enthält eine kurze Zusammenfassung der Umfang von hat und was nicht in Teams Vorlagen enthalten ist.

| **Eigenschaften von Team von Teams Vorlagen unterstützt** | **Eigenschaften von Team von Teams Vorlagen noch nicht unterstützt.** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Basisvorlage-Typ | Teammitgliedschaft |
| Teamname | Team-Bild |
| Team Beschreibung | Kanal-Einstellungen |
| Team Sichtbarkeit (öffentlich oder privat) | Connectors |
| Team-Einstellungen (beispielsweise Member, Gast @ erwähnungen) | Dateien und Inhalte |
| Automatische Favoriten DDE-Kanal | |
| Installierte app | |
| Angeheftete Registerkarten | | 

> [!NOTE]
> Wir werden werden weitere Funktionen in zukünftigen Versionen des Microsoft-Teams, hinzufügen, für die die aktuellsten Informationen zu unterstützten Eigenschaften überprüfen.

## <a name="what-are-base-template-types"></a>Was sind Basisvorlage Typen?

Basisvorlage Typen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt. Diese Basis Vorlagen enthalten häufig proprietäre apps, die nicht in den Speicher und die Team-Eigenschaften zur Verfügung stehen, die noch nicht einzeln in Teams Formularvorlagen unterstützt werden.

Nachdem ein Basisvorlage Typ definiert ist, können Sie erweitern oder außer Kraft setzen diese speziellen Vorlagen mit zusätzlichen Eigenschaften, die Sie angeben möchten. Jedoch einige Basisvorlage Typen enthalten Eigenschaften, die nicht überschrieben werden können. 

Standardmäßig ist die Basisvorlage auf **Standard** festgelegt, die keine zusätzlichen proprietäre apps oder spezielle Eigenschaften enthält. Unten ist die aktuelle Liste der Typen Basis Vorlagen verfügbar.

| Basisvorlage-Typ | baseTemplateId | Basisvorlage proprietäre apps und spezielle Eigenschaften |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | Keine zusätzliche apps und Eigenschaften |
| Education- <br>Klasse Team<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | Apps:<ul><li>OneNote-Klasse-Notizbuch (angeheftet auf der Registerkarte **Allgemein** ) </li><li>Assignments-app (angeheftet auf der Registerkarte **Allgemein** )</li></ul> Team-Eigenschaften:<ul><li>Legen Sie die Sichtbarkeit Team auf **HiddenMembership** (können nicht überschrieben werden)</li></ul> |
| Education-<br>Mitarbeiter Team<sup>1</sup> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | Apps:<ul><li>OneNote-Personal-Notizbuch (angeheftet auf der Registerkarte **Allgemein** )</li></ul> |
|Education-<br>PLC-team |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | Apps:<ul><li>OneNote PLC-Notizbuch (angeheftet auf der Registerkarte **Allgemein** )</ul></li>|
|||

<sup>1</sup> -Publikation in spät Oktober, 2018

> [!NOTE]
> Wir können Sie Hinzufügen weiterer Basisvorlage Typen in zukünftigen Versionen von Microsoft-Teams, damit die Kontrollkästchen für die aktuellsten Informationen zu Eigenschaften unterstützt.

## <a name="examples"></a>Beispiele 

Sie können die mithilfe einer Vorlage um ein Team erstellen mithilfe der [Microsoft Graph-API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)starten.

### <a name="create-a-team-from-a-template"></a>Erstellen Sie ein Team aus einer Vorlage

#### <a name="requests"></a>Anfragen

**Erstellen Sie ein Team mit standard Basisvorlage anfordern**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

**Erstellen Sie ein Team mit zusätzlichen einen DDE-Kanal und die nicht Mitglieder löschen Kanäle zulassen**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

**Erstellen Sie ein Team mit allen unterstützten Eigenschaften anfordern**

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a>Abrufen des status

#### <a name="request"></a>Anforderung

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a>Reaktion

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a>Verwandte Themen

- [Create-team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)
- [Neues Team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Administrator-Schulung für Microsoft Teams](itadmin-readiness.md)