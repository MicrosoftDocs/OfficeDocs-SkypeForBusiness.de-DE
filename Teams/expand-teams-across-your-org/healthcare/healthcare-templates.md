---
title: Vorlagen für Organisationen im Gesundheitswesen
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Verwenden Sie Microsoft Teams-Vorlagen, um schnell und einfach Teams zu erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und apps bereitstellen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f2ef6bd4bf358a90654e7fda643effbfcc34b3c2
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294436"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations-using-microsoft-graph"></a>Erste Schritte mit Teamvorlagen für Organisationen im Gesundheitswesen mit Microsoft Graph

Mit Microsoft Teams-Vorlagen können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Vorlage mit Einstellungen, Kanälen und vorinstallierten apps bereitstellen.

Für Organisationen im Gesundheitswesen können Vorlagen besonders leistungsstark sein, da Sie die Struktur für Benutzer bereitstellen, um sich mit der effektiven Verwendung von Teams zu orientieren. Mit Vorlagen können Administratoren auch konsistente Teams in ihren Organisationen bereitstellen. Dieser Artikel ist für Sie zuständig, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in ihrer gesamten Gesundheitsorganisation verantwortlich sind.

Wir bieten derzeit zwei First-Party Healthcare-Vorlagen an, die Sie für unterschiedliche Situationen verwenden können. Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen](../../get-started-with-teams-templates.md).

## <a name="ward-template"></a>Ward-Vorlage

Die Ward-Vorlage ist für die Kommunikation und Zusammenarbeit innerhalb einer Station, eines Pod oder einer Abteilung vorgesehen. Die Vorlage kann verwendet werden, um die Patientenverwaltung sowie die betrieblichen Anforderungen einer Station zu vereinfachen. So können beispielsweise Ward-Ankündigungen im *Ankündigungen* -Kanal veröffentlicht werden, und Schichten können in der *Besetzung*verwaltet werden. Wenn Sie Ihre Abteilungen optimieren möchten, ist diese Vorlage für Sie.

|Basis Vorlagentyp |baseTemplateId |Baseline-Vorlagen Kanäle|
|:--- |:---|:---|
|Healthcare – Ward | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Ankündigungen\* <br> Kauert\* <br> Runden\* <br> Personal\* <br> Schulungen\* |
|     | |         |

\* Automatisch Favoriten

## <a name="hospital-template"></a>Vorlage für Krankenhaus

Die Vorlage für das Krankenhaus ist für die Kommunikation und Zusammenarbeit zwischen mehreren Stationen, Hülsen und Abteilungen innerhalb eines Krankenhauses vorgesehen. In dieser Vorlage sind mehrere operationelle Kanäle enthalten, einschließlich *Ankündigungen*, *Freiheitsentzug*und *Pharmazie*, aber wir bieten auch ein Skript, das die Vorlage mit einer Reihe weiterer Abteilungs-oder Spezial orientierter Kanäle erweitert, die Sie Ihren Wünschen hinzufügen, löschen oder bearbeiten können. Wenn Sie beispielsweise über eine *Endokrinologie* -Abteilung verfügen, aber keinen Kanal für die *Augenheilkunde*benötigen, kann das Skript so angepasst werden, dass es einen *Endokrinologie* -Kanal enthält, und den *Ophthalmologie* -Kanal entfernen. Wir empfehlen, dass diese Spezial-oder Stations modellierten Kanäle nicht automatisch als Favorit festgelegt werden, um eine Benachrichtigungs Sättigung zu vermeiden. Benutzer können in der Regel alle Kanäle, die für Sie relevant sind, als Favoriten festlegen.

|Basis Vorlagentyp |baseTemplateId |Baseline-Vorlagen Kanäle|
|:--- |:---|:---|
|Gesundheitswesen – Krankenhaus | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Ankündigungen\* <br> Compliance\* <br> Freiheits <br> Personalwesen <br> Apotheke |
| | |  |

\* Automatisch Favoriten 

## <a name="how-to-use-first-party-templates"></a>Verwenden von Vorlagen für Erstanbieter

Wenn Sie diese Vorlagen verwenden möchten, ändern Sie einfach die Eigenschaft "Template@odata. Bind" im Anforderungstext von "Standard" in das obige TemplateIDs.  Weitere Informationen zum Bereitstellen von Teams-Vorlagen finden Sie im Microsoft Graph-Artikel zum [Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

> [!NOTE]
> Die Kanäle in der Vorlage werden auf der RegisterkarteAllgemein automatisch erstellt.

### <a name="example-hospital-template-extension-script"></a>Beispiel: Erweiterungs Skript für Krankenhaus Vorlagen

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

## <a name="related-topics"></a>Verwandte Themen

[Erste Schritte mit Teams-Vorlagen](../../get-started-with-teams-templates.md)

[Erste Schritte mit Teams für Organisationen im Gesundheitswesen](teams-in-hc.md)

[Erste Schritte mit Microsoft Teams-Vorlagen in der Admin-Konsole](../../get-started-with-teams-templates-in-the-admin-console.md)
