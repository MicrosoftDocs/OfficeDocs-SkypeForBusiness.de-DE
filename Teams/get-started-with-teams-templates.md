---
title: Erste Schritte mit Teams Vorlagen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 151a789b6047540071aa5780fb81a895503dd70b
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838891"
---
# <a name="get-started-with-teams-templates"></a>Erste Schritte mit Teams Vorlagen 

Definitionen von entwickelt, um ein geschäftlicher Bedarf oder Projekt ein Team Struktur werden vor dem Teamvorlagen erstellt werden. Teamvorlagen können schnell und erstellen umfassender Zusammenarbeit Leerzeichen mit Kanäle für verschiedene Themen und Vorinstallieren von apps in unternehmenswichtige Inhalte und Dienste abrufen. Teamvorlagen bieten eine vordefinierte Teamstruktur, die Sie auf einfache Weise konsistent Teams innerhalb Ihrer Organisation helfen. 

In diesem Artikel wird die Eigenschaften, die in Vorlagen, welche Basisvorlage definiert werden können, sind, erläutert, und wie Sie verwenden können, Beispiel wenige Anforderungen an ein Team aus einer Vorlage zu erstellen.
 
Dieser Artikel ist für Sie, wenn Sie sind:

• Verantwortlich für die Planung, Bereitstellung und Verwaltung mehrere Teams für Ihre Organisation • ein Entwickler suchen So erstellen Sie ein Team mit vordefinierten Kanäle und apps programmgesteuert

## <a name="team-template-capabilities"></a>Funktionen für Team-Vorlage

Die meisten Eigenschaften in einem Team sind enthalten und von Vorlagen unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Die folgende Tabelle enthält eine kurze Zusammenfassung der Umfang von hat und was nicht in Teams Vorlagen enthalten ist.

| **Eigenschaften von Team von Teams Vorlagen unterstützt** | **Eigenschaften von Team von Teams Vorlagen noch nicht unterstützt.** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Basisvorlage-Typ | Teammitgliedschaft |
| Teamname | Team-Bild |
| Team Beschreibung | Kanal-Einstellungen (beispielsweise automatische Favoriten und Datenschutz) |
| Team Sichtbarkeit (öffentlich oder privat) | Connectors |
| Team-Einstellungen (beispielsweise Member, Gast @ erwähnungen) | Dateien und Inhalte |
| Automatische Favoriten DDE-Kanal | |
| Installierte app | |
| Angeheftete Registerkarten | | 

> [!NOTE]
> Wir werden werden weitere Funktionen in zukünftigen Versionen des Microsoft-Teams, hinzufügen, für die die aktuellsten Informationen zu unterstützten Eigenschaften überprüfen.

## <a name="what-are-base-template-types"></a>Was sind Basisvorlage Typen?

Basisvorlage Typen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt. Diese Basis Vorlagen enthalten häufig proprietäre apps, die nicht in den Speicher und die Team-Eigenschaften, die noch nicht einzeln in Teams Formularvorlagen unterstützt verfügbar sind.

Nachdem ein Basisvorlage Typ definiert ist, können Sie erweitern oder außer Kraft setzen diese speziellen Vorlagen mit zusätzlichen Eigenschaften, die Sie angeben möchten. Einige Basisvorlage Typen enthalten jedoch Eigenschaften, die nicht überschrieben werden können. 

Standardmäßig ist die Basisvorlage auf **Standard** festgelegt, die keine zusätzlichen proprietäre apps oder spezielle Eigenschaften enthält. Unten ist die aktuelle Liste der Typen Basis Vorlagen verfügbar.

| Basisvorlage-Typ | baseTemplateId | Basisvorlage proprietäre apps und spezielle Eigenschaften |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | Keine zusätzliche apps und Eigenschaften |
| Gesundheitswesen - Vorsicht Koordinierung | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | Apps:<br/> -Patienten app (angeheftet auf der Registerkarte **Allgemein** )<br/> <br/>Kanäle: <br/> -Ansagen<br/> -Diabetes<br/> -Herz-Kreislauf-Erkrankungen<br/> -Registered Pflegepersonal |
| Gesundheitswesen - Prozess drängeln | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | Kanäle:<br/> -Vermeidbare Todesfälle<br/> -Mortalität Überprüfung <br/> -Fällt verhindern <br/> -Sepsis Pläne |
| Education - Klasse Team<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | Apps:<br/> -OneNote Klasse Notizbuch (angeheftet auf der Registerkarte **Allgemein** ) <br/> -Assignments app (angeheftet auf der Registerkarte **Allgemein** ) <br/><br/> Team-Eigenschaften <br/> -Legen Sie die Sichtbarkeit Team auf **HiddenMembership** (können nicht überschrieben werden) |
| Education - team-Mitarbeiter<sup>1</sup> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | Apps<br/> -OneNote Personal-Notizbuch (angeheftet auf der Registerkarte **Allgemein** ) |

<sup>1</sup> -Publikation in spät Oktober, 2018

> [!NOTE]
> Wir können Sie Hinzufügen weiterer Basisvorlage Typen in zukünftigen Versionen von Microsoft-Teams, damit die Kontrollkästchen für die aktuellsten Informationen zu Eigenschaften unterstützt.

## <a name="examples"></a>Beispiele 

Sie können mit dem Erstellen eines Teams über Vorlage durch Installieren von [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).

### <a name="create-a-team-from-a-template"></a>Erstellen Sie ein Team aus einer Vorlage

#### <a name="requests"></a>Anfragen

**Erstellen Sie ein Team mit standard Basisvorlage anfordern**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

**Erstellen Sie ein Team mit zusätzlichen einen DDE-Kanal und die nicht Mitglieder löschen Kanäle zulassen**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

**Erstellen Sie ein Team mit allen unterstützten Eigenschaften anfordern**

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a>Reaktion

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
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

- [Create-team](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (in der Vorschau)
- [Neues Team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Administratorschulungen für Microsoft Teams](itadmin-readiness.md)