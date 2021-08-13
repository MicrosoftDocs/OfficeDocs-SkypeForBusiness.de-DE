---
title: Erstellen eines Teams mithilfe von Vorlagen im Gesundheitswesen
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Verwenden Sie Teamvorlagen im Admin Center oder mit Microsoft Graph, um Schnell und einfach Teams zu erstellen, indem Sie eine vordefinierte Vorlage für Einstellungen, Kanäle und Apps bereitstellen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 050ddd4e9efabe3433257f0497081758767e1cfa38c16aa1102ff17554ce3391
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336255"
---
# <a name="use-a-healthcare-team-templates"></a>Verwenden von Vorlagen für ein Gesundheitsteam

Mit Vorlagen können Sie Teams schnell und einfach erstellen, indem Sie eine vordefinierte Vorlage für Einstellungen, Kanäle und vorinstallierte Apps bereitstellen.

Für Organisationen im Gesundheitswesen können Vorlagen besonders leistungsfähig sein, da sie eine Struktur für die Benutzer bieten, die sich mit der effektiven Nutzung ihrer Daten Microsoft Teams. Mithilfe von Vorlagen können Administratoren auch konsistente Teams in ihren Organisationen bereitstellen. Dieser Artikel richtet sich an Sie, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Gesundheitsorganisation verantwortlich sind.

Wählen Sie eine Methode zum Erstellen von Teams mit Den Vorlagen für das Team Gesundheitswesen aus:

| Wer | Zu verwendende Methode: |
| ---- | --------- |
| Administratoren und IT-Spezialisten | [Verwenden Sie Teams Admin Center,](#use-the-team-templates-in-the-admin-center) um Teams basierend auf den Vorlagen im Gesundheitswesen zu erstellen.|
| Entwickler und Systemintegratoren | [Verwenden Sie die Microsoft Graph,](#use-the-team-templates-with-the-microsoft-graph) um ein Team basierend auf den Vorlagen des Gesundheitsteams zu erstellen. |

## <a name="use-the-team-templates-in-the-admin-center"></a>Verwenden der Teamvorlagen im Admin Center

Microsoft Teams Administratoren können das Teams Admin Center verwenden, um Teams mit den Teamvorlagen zu erstellen. Derzeit bieten wir zwei Vorlagen für das Gesundheitswesen von Erstanbietern an, die Sie für eine Vielzahl von Situationen verwenden können. Weitere allgemeine Informationen zu Teamvorlagen finden Sie unter Erste Schritte [mit Teamvorlagen im Admin Center.](../../get-started-with-teams-templates-in-the-admin-console.md)

### <a name="collaborate-on-patient-care"></a>Arbeiten Sie bei der Patientenversorgung zusammen

 Optimieren Sie die Kommunikation und Zusammenarbeit im Gesundheitswesen innerhalb einer Station, eines Bereiches oder einer Abteilung. Die Vorlage kann verwendet werden, um das Patientenmanagement und die operativen Anforderungen einer Station zu erleichtern.

| Basisorlagentyp |baseTemplateId| Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ |---|----------------------------------------------------- |
| Arbeiten Sie bei der Patientenversorgung zusammen |`healthcareWard` | Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Huddles</li><li>Runden</li><li>Personal</li><li>Schulung</li></ul> Apps: <ul><li>Wiki</li><li>Listen</li></ul>|
||||

### <a name="hospital"></a>Krankenhaus

Optimieren Sie die Kommunikation und Zusammenarbeit zwischen mehreren Stationen, Bereichen und Abteilungen innerhalb eines Krankenhauses. Diese Vorlage enthält eine Reihe von Basiskanälen für den Krankenhausbetrieb und kann selbst erweitert werden, um Ad-hoc-Spezialitäten einzuschließen.

| Basisorlagentyp |baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------|-- |----------------------------------------------------- |
|Krankenhaus|`healthcareHospital`|Kanäle: <ul><li>Allgemein</li><li>Ankündigungen</li><li>Compliance</li><li>Sorgerecht</li><li>Personalwesen</li><li>Apotheke</li></ul> Apps: <ul><li>Wiki</li><li>Listen </li></ul>|
||||


## <a name="use-the-team-templates-with-the-microsoft-graph"></a>Verwenden der Teamvorlagen mit dem Microsoft-Graph

Entwickler können die Microsoft-Graph verwenden, um Teams mit den Teamvorlagen zu erstellen. Derzeit bieten wir zwei Vorlagen für das Gesundheitswesen von Erstanbietern an, die Sie für eine Vielzahl von Situationen verwenden können. Weitere allgemeine Informationen zu Teamvorlagen finden Sie unter [Erste Schritte mit Teamvorlagen.](../../get-started-with-teams-templates.md) Informationen zu Teamvorlagen und dem Microsoft-Graph finden Sie unter Übersicht [Microsoft Teams-API](/graph/teams-concept-overview?view=graph-rest-1.0) und [teamsTemplate-Ressourcentyp](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="ward-template"></a>Sationsvorlage

Die Stationsvorlage ist für die Kommunikation und Zusammenarbeit innerhalb einer Station, eines Bereiches oder einer Abteilung gedacht. Die Vorlage kann verwendet werden, um das Patientenmanagement sowie die betrieblichen Anforderungen einer Station zu vereinfachen. Beispielsweise können Stationsankündigungen im *Ankündigungs* kanal veröffentlicht und Schichten in *Personal* verwaltet werden. Wenn Sie Ihren Stationsbetrieb optimieren möchten, ist diese Vorlage genau das Richtige für Sie.

|Basisvorlagentyp |baseTemplateId |Baseline Vorlagenkanäle|
|:--- |:---|:---|
|Gesundheitswesen – Station | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Ankündigungen\* <br> Huddles\* <br> Runden\* <br> Personal\* <br> Schulung\* |
|     | |         |

\*Automatisch favorisiert

### <a name="hospital-template"></a>Krankenhausvorlage

Die Krankenhausvorlage ist für die Kommunikation und Zusammenarbeit zwischen mehreren Stationen, Bereichen und Abteilungen innerhalb eines Krankenhauses vorgesehen. In dieser Vorlage sind mehrere Betriebskanäle enthalten, einschließlich *Ankündigungen*, *Aufsicht* und *Apotheke*. Im Folgenden finden Sie jedoch auch ein Skript, das die Vorlage um eine Reihe zusätzlicher abteilungs- oder spezialitätsorientierter Kanäle erweitert, die Sie nach Ihren Wünschen hinzufügen, löschen oder bearbeiten können. Wenn Sie beispielsweise eine Abteilung für *Endokrinologie* haben, aber keinen Kanal für die *Augenheilkunde* benötigen, kann das Skript so angepasst werden, dass es einen Kanal für die *Endokrinologie* enthält und den Kanal für die *Augenheilkunde* entfernt. Wir empfehlen, diese speziellen oder für Stationen modellierten Kanäle nicht automatisch zu bevorzugen, um eine Benachrichtigungssättigung zu vermeiden. Benutzer bevorzugen im Allgemeinen alle Kanäle, die sie für relevant halten.

|Basisvorlagentyp |baseTemplateId |Baseline Vorlagenkanäle|
|:--- |:---|:---|
|Gesundheitswesen – Krankenhaus | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Ankündigungen\* <br> Compliance\* <br> Sorgerecht <br> Personalwesen <br> Apotheke |
| | |  |

\*Automatisch favorisiert 

### <a name="how-to-use-first-party-templates"></a>So verwenden Sie Vorlagen von Erstanbietern

Um diese Vorlagen zu verwenden, ändern Sie einfach die Eigenschaft 'template@odata.bind' im Anforderungshauptteil von 'standard' in die obigen TemplateIDs.  Weitere Informationen zum Bereitstellen von Teamvorlagen finden Sie im Microsoft Graph zum Erstellen [eines Teams.](/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Die Kanäle in der Vorlage werden automatisch auf der Registerkarte Allgemein erstellt.

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

### <a name="related-topics"></a>Verwandte Themen

[Erste Schritte mit Teamvorlagen](../../get-started-with-teams-templates.md)

[Erste Schritte mit dem Team für Organisationen im Gesundheitswesen](teams-in-hc.md)