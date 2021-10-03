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
ms.openlocfilehash: 78269b393c384af82e48284e3ffefe8785013975
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046001"
---
# <a name="use-healthcare-team-templates"></a>Verwenden der Teamvorlagen für das Gesundheitswesen

Mit Teamvorlagen in Microsoft Teams können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Teamstruktur aus Einstellungen, Kanälen und vorinstallierten Apps bereitstellen.

Für Organisationen im Gesundheitswesen können Teamvorlagen besonders nützlich sein, da sie Ihnen dabei helfen, innerhalb der gesamten Organisation schnell einheitliche Teams bereitzustellen. Vorlagen helfen den Mitarbeitern auch, sich bei der effektiven Verwendung von Microsoft Teams zu orientieren.

Microsoft Teams bietet Vorlagen, die speziell für Organisationen im Gesundheitswesen konzipiert wurden. Verwenden Sie diese vorgefertigten Vorlagen, um für Mitarbeiter schnell Teams für die Kommunikation und Zusammenarbeit bei der Patientenversorgung oder für betrieblichen Anforderungen zu erstellen. In diesem Artikel stellen wir Ihnen jede dieser Vorlagen vor und empfehlen deren Verwendung.

Wie Sie Teamvorlagen verwalten und damit arbeiten, hängt davon ab, ob Sie Administrator oder Entwickler sind.

|Wenn Sie: | Dann: |
| ---- | --------- |
| Ein Administrator oder IT-Profi |[Verwalten Sie Teamvorlagen im Teams Admin Center](#manage-team-templates-in-the-teams-admin-center). Zeigen Sie Teamvorlagen an und wenden Sie Vorlagenrichtlinien an, um zu steuern, welche Vorlagen Ihre Mitarbeiter in Teams zum Erstellen von Teams verwenden können. |
| Ein Entwickler | [Verwenden Sie Microsoft Graph](#use-team-templates-with-microsoft-graph), um Teams aus Teamvorlagen zu erstellen. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Verwalten von Teamvorlagen im Teams Admin Center

Als Administrator können Sie Teamvorlagen im Microsoft Teams Admin Center verwalten. Hier können Sie Details zu jeder Vorlage anzeigen. Sie können Ihren Mitarbeitern auch [Vorlagenrichtlinien erstellen und zuweisen](../../templates-policies.md), um zu steuern, welche Vorlagen sie in Teams zum [Erstellen von Teams](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b) sehen.

Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Teamvorlagen im Teams Admin Center](../../get-started-with-teams-templates-in-the-admin-console.md).

Derzeit sind die folgenden vordefinierten Teamvorlagen für das Gesundheitswesen verfügbar. Um sie anzuzeigen, wechseln Sie in der linken Navigation im Microsoft Teams Admin Center zu **Teams** > **Teamvorlagen**.
### <a name="patient-care"></a>Patientenversorgung

 Diese Vorlage ist für die Kommunikation und Zusammenarbeit innerhalb einer Station, eines Bereiches oder einer Abteilung gedacht. Sie können diese Vorlage zur Vereinfachung des Patientenmanagements und für operative Anforderungen einer Station verwenden. Posten Sie beispielsweise Ankündigungen im Kanal *Ankündigungen* und verwalten Sie Schichten im Kanal *Personal*.

| Vorlagentyp |TemplateId| Eigenschaften, die mit dieser Vorlage geliefert werden |
| ------------------ |---|----------------------------------------------------- |
| Patientenversorgung |`healthcareWard` | Kanäle:<ul><li>Allgemein</li><li>Ankündigungen<ul><li>Bulletins&sup1;</li></ul></li><li>Brainstormings<ul><li>Listen (Patientenliste)&sup1;</li></ul></li><li>Visiten<ul><li>Prüfung&sup1;</li></ul></li><li>Personal</li><li>Schulung</li></ul> Apps: <ul><li>Wiki</li><li>Listen</li><li>Aufgaben</li><li>Genehmigungen</li><li>Schichten</li><li>Bulletins</li><li>Prüfung</li></ul>|
||||

&sup1;App wurde dem Kanal als Registerkarte hinzugefügt
### <a name="hospital"></a>Krankenhaus

Diese Vorlage ist für die Kommunikation und Zusammenarbeit zwischen mehreren Stationen, Bereichen und Abteilungen innerhalb eines Krankenhauses vorgesehen. Diese Vorlage enthält eine Reihe von Kanälen für den Krankenhausbetrieb und kann zur weiteren Anpassung erweitert werden.

| Vorlagentyp |TemplateId | Eigenschaften, die mit dieser Vorlage geliefert werden |
| ------------------|-- |----------------------------------------------------- |
|Krankenhaus|`healthcareHospital`|Kanäle: <ul><li>Allgemein<ul><li>Listen&sup1;</li></ul></li><li>Ankündigungen<ul><li>Bulletins&sup1;</li></ul></li><li>Compliance</li><ul><li>Prüfung&sup1;</li></ul></li><li>Sorgerecht</li><li>Personalwesen<ul><li>Ideen&sup1;</li></ul></li><li>Apotheke</li></ul> Apps: <ul><li>Wiki</li><li>Aufgaben</li><li>Listen</li><li>Genehmigungen</li><li>Schichten</li><li>Bulletins</li><li>Prüfung</li><li>Ideen</li></ul>|
||||

&sup1;App wurde dem Kanal als Registerkarte hinzugefügt
## <a name="use-team-templates-with-microsoft-graph"></a>Verwenden Sie Teamvorlagen mit Microsoft Graph

Entwickler können Microsoft Graph verwenden, um Teams aus vorgefertigten Teamvorlagen zu erstellen. Weitere Informationen zur Verwendung von Teamvorlagen mit Microsoft Graph finden Sie unter [Erste Schritte mit Teamvorlagen mit Microsoft Graph](../../get-started-with-teams-templates.md), [Übersicht über die Microsoft Teams-API](/graph/teams-concept-overview?view=graph-rest-1.0) und [teamsTemplate-Ressourcentyp](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

Hier finden Sie die vorgefertigten Teamvorlagen für das Gesundheitswesen.
### <a name="ward"></a>Station

Die Stationsvorlage ist für die Kommunikation und Zusammenarbeit innerhalb einer Station, eines Bereiches oder einer Abteilung gedacht. Die Vorlage kann zur Vereinfachung des Patientenmanagements und für operative Anforderungen einer Station verwendet werden. Beispielsweise können Stationsankündigungen im *Ankündigungs* kanal veröffentlicht und Schichten in *Personal* verwaltet werden. Wenn Sie Ihren Stationsbetrieb optimieren möchten, ist diese Vorlage genau das Richtige für Sie.

|Vorlagentyp |TemplateId |Vorlagenkanäle|
|:--- |:---|:---|
|Gesundheitswesen – Station | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Allgemein<br>Ankündigungen&sup2; <br> Brainstormings&sup2; <br> Visiten&sup2; <br> Personal&sup2; <br> Schulung&sup2; |
|     | |         |

&sup2;Automatisch als Favoriten festgelegte Kanäle

### <a name="hospital"></a>Krankenhaus

Die Krankenhausvorlage ist für die Kommunikation und Zusammenarbeit zwischen mehreren Stationen, Bereichen und Abteilungen innerhalb eines Krankenhauses vorgesehen. Diese Vorlage enthält mehrere operative Kanäle wie z. B. *Ankündigungen*, *Pflege* und *Apotheke*. Außerdem stellen wir ein Skript bereit, mit dem Sie die Vorlage um zusätzliche Abteilungen oder spezialisierte Kanäle erweitern können. Sie können das Skript an Ihre Anforderungen anpassen.

Wenn Sie beispielsweise eine Abteilung für *Endokrinologie* haben, aber keinen Kanal für die *Augenheilkunde* benötigen, kann das Skript so angepasst werden, dass es einen *Endokrinologie*-Kanal enthält und der Kanal für die *Augenheilkunde* entfernt wird. Wir empfehlen, diese speziellen oder für Stationen modellierten Kanäle nicht automatisch zu bevorzugen, um eine Benachrichtigungssättigung zu vermeiden. Benutzer bevorzugen im Allgemeinen alle Kanäle, die sie für relevant halten.

|Vorlagentyp |TemplateId |Vorlagenkanäle|
|:--- |:---|:---|
|Gesundheitswesen – Krankenhaus | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Allgemein<br>Ankündigungen&sup2; <br> Compliance&sup2; <br> Sorgerecht <br> Personalwesen <br> Apotheke |
| | |  |

&sup2;Automatisch als Favoriten festgelegte Kanäle

### <a name="how-to-use-team-templates-with-microsoft-graph"></a>So verwenden Sie Teamvorlagen mit Microsoft Graph

Um diese Vorlagen zu verwenden, ändern Sie die Eigenschaft „template@odata.bind“ im Anforderungstext von „standard“' in die obigen Vorlagen-IDs. Weitere Informationen zur Bereitstellung von Teamvorlagen finden Sie im Microsoft Graph-Artikel zum [Erstellen eines Teams](/graph/api/team-post?view=graph-rest-beta).

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

- [Erstellen eines Teams aus einer Vorlage](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Erste Schritte mit Teamvorlagen im Microsoft Teams Admin Center](../../get-started-with-teams-templates-in-the-admin-console.md)
- [Erste Schritte mit Teamvorlagen mittels Microsoft Graph](../../get-started-with-teams-templates.md)
- [Erste Schritte mit Teams für Organisationen im Gesundheitswesen](teams-in-hc.md)