---
title: Verwenden der Teamvorlagen für das Gesundheitswesen
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: high
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: yinchang
description: Erfahren Sie, wie Sie die Teamvorlagen für das Gesundheitswesen im Microsoft Teams Admin Center und mit Microsoft Graph verwalten und verwenden können, um schnell und einfach Teams für Ihre Gesundheitsorganisation zu erstellen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 00da42e4e573306a3737b1d35e89292b04df4fa4
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991124"
---
# <a name="use-healthcare-team-templates"></a>Verwenden der Teamvorlagen für das Gesundheitswesen

Mit Teamvorlagen in Microsoft Teams können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten Apps bereitstellen.

Für Organisationen im Gesundheitswesen können Teamvorlagen besonders nützlich sein, da sie Ihnen dabei helfen, innerhalb der gesamten Organisation schnell einheitliche Teams bereitzustellen. Vorlagen helfen den Mitarbeitern auch, sich bei der effektiven Verwendung von Microsoft Teams zu orientieren.

Microsoft Teams bietet speziell für Organisationen im Gesundheitswesen konzipierte Vorlagen. Verwenden Sie diese vorgefertigten Vorlagen, um für Mitarbeiter schnell Teams zu erstellen für die Kommunikation und Zusammenarbeit bei der Patientenversorgung. In diesem Artikel werden die einzelnen Vorlagen vorgestellt und deren Verwendung erläutert.

Wie Sie Teamvorlagen verwalten und damit arbeiten, hängt davon ab, ob Sie Administrator oder Entwickler sind.

|Sie sind: | Dann können Sie: |
| ---- | --------- |
| Administrator oder IT-Experte |[Teamvorlagen im Microsoft Teams Admin Center verwalten](#manage-team-templates-in-the-teams-admin-center): Zeigen Sie Teamvorlagen an und wenden Sie Vorlagenrichtlinien an, um zu steuern, welche Vorlagen Ihre Mitarbeiter in Microsoft Teams zum Erstellen von Teams verwenden können. |
| Entwickler | [Microsoft Graph verwenden](#use-team-templates-with-microsoft-graph), um mit Teamvorlagen Teams zu erstellen. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Verwalten von Teamvorlagen im Microsoft Teams Admin Center

Als Administrator können Sie Teamvorlagen im Microsoft Teams Admin Center verwalten. Hier können Sie Details zu den einzelnen Vorlagen einsehen. Sie können für Ihre Mitarbeiter auch [Vorlagenrichtlinien erstellen und sie ihnen zuweisen](../../templates-policies.md), um zu steuern, welche Vorlagen ihnen in Microsoft Teams zum [Erstellen von Teams](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) angezeigt werden. 

Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Teamvorlagen im Microsoft Teams Admin Center](../../get-started-with-teams-templates-in-the-admin-console.md).

Derzeit sind die folgenden vordefinierten Teamvorlagen für das Gesundheitswesen verfügbar. Um sie anzuzeigen, wechseln Sie in der linken Navigation im Microsoft Teams Admin Center zu **Teams** > **Teamvorlagen**.
### <a name="patient-care"></a>Patientenversorgung

 Diese Vorlage ist für die Kommunikation und Zusammenarbeit innerhalb einer Station, eines Bereiches oder einer Abteilung gedacht. Sie können diese Vorlage zur Vereinfachung des Patientenmanagements und für operative Anforderungen einer Station verwenden. Posten Sie beispielsweise Ankündigungen im Kanal *Ankündigungen* und verwalten Sie Schichten im Kanal *Mitarbeiter*.

| Vorlagentyp |Vorlagen-ID| Merkmale der Vorlage |
| ------------------ |---|----------------------------------------------------- |
| Patientenversorgung |`healthcareWard` | Kanäle:<ul><li>Allgemein</li><li>Ankündigungen<ul><li>Bulletins&sup1;</li></ul></li><li>Brainstormings<ul><li>Listen (Patientenliste)&Sup1;</li></ul></li><li>Visiten<ul><li>Kontrolle&sup1;</li></ul></li><li>Personal</li><li>Schulung</li></ul> Apps: <ul><li>Wiki</li><li>Listen</li><li>Aufgaben</li><li>Genehmigungen</li><li>Schichten</li><li>Bulletins</li><li>Visite</li></ul>|
||||

&Sup1; App zum Kanal als Registerkarte hinzugefügt
### <a name="hospital"></a>Krankenhaus

Diese Vorlage ist für die Kommunikation und Zusammenarbeit zwischen mehreren Stationen, Bereichen und Abteilungen innerhalb eines Krankenhauses vorgesehen. Sie enthält eine Reihe von Kanälen für den Krankenhausbetrieb und kann zur weiteren Anpassung erweitert werden.

| Vorlagentyp |Vorlagen-ID | Merkmale der Vorlage |
| ------------------|-- |----------------------------------------------------- |
|Krankenhaus|`healthcareHospital`|Kanäle: <ul><li>Allgemein<ul><li>Listen&Sup1;</li></ul></li><li>Ankündigungen<ul><li>Bulletins&sup1;</li></ul></li><li>Compliance</li><ul><li>Kontrolle&sup1;</li></ul></li><li>Sorgerecht</li><li>Personalwesen<ul><li>Ideen&sup1;</li></ul></li><li>Apotheke</li></ul> Apps: <ul><li>Wiki</li><li>Aufgaben</li><li>Listen</li><li>Genehmigungen</li><li>Schichten</li><li>Bulletins</li><li>Visite</li><li>Ideen</li></ul>|
||||

&Sup1; App zum Kanal als Registerkarte hinzugefügt
## <a name="use-team-templates-with-microsoft-graph"></a>Verwenden von Teamvorlagen mit Microsoft Graph

Entwickler können Microsoft Graph verwenden, um Teams aus vorgefertigten Teamvorlagen zu erstellen. Weitere Informationen zur Verwendung von Teamvorlagen mit Microsoft Graph finden Sie unter [Erste Schritte mit Teamvorlagen mit Microsoft Graph](../../get-started-with-teams-templates.md), [Übersicht über Microsoft Teams-APIs](/graph/teams-concept-overview?view=graph-rest-1.0) und [teamsTemplate-Ressourcentyp](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Nachfolgend sind die vorgefertigten Teamvorlagen für das Gesundheitswesen aufgeführt.
### <a name="ward"></a>Sationsvorlage

Die Stationsvorlage ist für die Kommunikation und Zusammenarbeit innerhalb einer Station, eines Bereiches oder einer Abteilung gedacht. Sie kann zur Vereinfachung des Patientenmanagements und für operative Anforderungen einer Station verwendet werden. Beispielsweise können Stationsankündigungen im *Ankündigungs* kanal veröffentlicht und Schichten in *Personal* verwaltet werden. Wenn Sie Ihren Stationsbetrieb optimieren möchten, ist diese Vorlage genau das Richtige für Sie.

|Vorlagentyp |Vorlagen-ID |Vorlagenkanäle|
|:--- |:---|:---|
|Gesundheitswesen – Station | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Allgemein<br>Ankündigungen&sup2; <br> Brainstormings&sup2; <br> Visiten&Sup2; <br> Personal&sup2; <br> Schulung&sup2; |
|     | |         |

&sup2; Automatisch als Favoriten festgelegte Kanäle

### <a name="hospital"></a>Krankenhaus

Die Krankenhausvorlage ist für die Kommunikation und Zusammenarbeit zwischen mehreren Stationen, Bereichen und Abteilungen innerhalb eines Krankenhauses vorgesehen. Diese Vorlage enthält mehrere operative Kanäle wie z. B. *Ankündigungen*, *Pflege* und *Apotheke*. Außerdem stellen wir ein Skript bereit, mit dem Sie die Vorlage um zusätzliche Abteilungen oder spezielle Kanäle erweitern können. Sie können das Skript an Ihre Anforderungen anpassen.

Wenn Sie beispielsweise eine Abteilung für *Endokrinologie* haben, aber keinen Kanal für die *Augenheilkunde* benötigen, kann das Skript so angepasst werden, dass es einen *Endokrinologie*-Kanal enthält und der Kanal für die *Augenheilkunde* entfernt wird. Wir empfehlen, diese speziellen oder für Stationen modellierten Kanäle nicht automatisch zu bevorzugen, um eine Benachrichtigungssättigung zu vermeiden. Benutzer bevorzugen im Allgemeinen alle Kanäle, die sie für relevant halten.

|Vorlagentyp |Vorlagen-ID |Vorlagenkanäle|
|:--- |:---|:---|
|Gesundheitswesen – Krankenhaus | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Allgemein<br>Ankündigungen&sup2; <br> Compliance&sup2; <br> Sorgerecht <br> Personalwesen <br> Apotheke |
| | |  |

&sup2; Automatisch als Favoriten festgelegte Kanäle

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>Informationen zur Verwendung von Teamvorlagen mit Microsoft Graph

Um diese Vorlagen zu verwenden, ändern Sie die Eigenschaft "template@odata.bind" im Anforderungshauptteil von "standard"' in die obigen Vorlagen-IDs. Weitere Informationen zur Nutzung von Teamvorlagen finden Sie im Microsoft Graph-Artikel zum [Erstellen eines Teams](/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Die Kanäle in der Vorlage werden automatisch auf der Registerkarte **Allgemein** erstellt.

#### <a name="example-hospital-template-extension-script"></a>Beispiel: Skript zur Erweiterung der Krankenhausvorlage

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-articles"></a>Verwandte Artikel

[Erste Schritte mit Teamvorlagen im Microsoft Teams Admin Center](../../get-started-with-teams-templates-in-the-admin-console.md)

[Erste Schritte mit Teamvorlagen mit Microsoft Graph](../../get-started-with-teams-templates.md)

[Erste Schritte mit Teams für Organisationen im Gesundheitswesen](teams-in-hc.md)