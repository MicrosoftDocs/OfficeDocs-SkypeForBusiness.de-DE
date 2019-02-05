---
title: Erste Schritte mit Microsoft-Teams Gesundheitswesen Vorlagen
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Erste Schritte mit Microsoft-Teams Gesundheitswesen Vorlagen
ms.openlocfilehash: 7d55d2d6a5f062bc5eb85b6bfc5227f7813c91ca
ms.sourcegitcommit: fddb1d6798e7a716ad87b0613f45a76deff6a043
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2019
ms.locfileid: "29735633"
---
# <a name="get-started-with-microsoft-teams-healthcare-templates"></a>Erste Schritte mit Microsoft-Teams Gesundheitswesen Vorlagen

Microsoft-Teams Vorlagen können Sie schnell und einfach Teams durch die Bereitstellung von Einstellungen, Kanäle und vorinstallierte apps einer vordefinierten Vorlage erstellen.

Für Unternehmen aus dem Gesundheitswesen können Vorlagen besonders leistungsstarke entsprechen, wie Struktur für Benutzer mit der Verwendung Verwaltungsberichte von Teams am besten effektiv zu nutzen ausgerichtet werden. Vorlagen ermöglichen Administratoren das konsistente Teams in ihrer Organisation bereitstellen. Dieser Artikel ist für Sie, wenn Sie die für die Planung, Bereitstellung und Verwaltung mehrere Teams für Ihre Organisation zuständig sind.

Wir derzeit bieten zwei ersten Teilnehmer aus dem Gesundheitswesen Vorlagen, die Sie für eine Vielzahl von Situationen nutzen können. Weitere Informationen zu Team finden finden Sie unter Vorlagen im Allgemeinen bitte [Erste Schritte mit Teams Vorlagen](../get-started-with-teams-templates.md).

## <a name="ward-template"></a>Bezirk-Vorlage

Die Vorlage Bezirk ist für die Kommunikation und Zusammenarbeit innerhalb einer Bezirk, Pod oder Abteilung vorgesehen. Die Vorlage kann verwendet werden, um patientenverwaltungs-als auch Bedarf für den Betrieb von einem Bezirk zu vereinfachen. Beispielsweise Bezirk Ansagen im Kanal *Ankündigungen* gebucht werden und Schichten in *Personal*verwaltet werden können. Wenn Sie zur Optimierung Ihrer Bezirk Vorgänge angezeigt werden, ist dieser Vorlage für Sie.

|Basisvorlage-Typ |baseTemplateId |Geplante Vorlage Kanäle|
|:--- |:---|:---|
|Gesundheitswesen - Bezirk | https://<span></span>Diagramm<span></span>.microsoft.com/beta/teamsTemplates/healthcareWardWide   | Ansagen\* <br> Rufen Sie Lichtquellen\* <br> Hilfreiche Informationen\* <br> Huddles\* <br>Rundet\* <br>Schulung\* |
|     | |         |

\*Automatische favorisierte 

## <a name="hospital-template"></a>Krankenhaus-Vorlage

Die Vorlage Krankenhaus ist für die Kommunikation und Zusammenarbeit zwischen mehreren Patientenbett einsetzen, folgende und Abteilungen innerhalb einer Krankenhaus vorgesehen. In dieser Vorlage sind mehrere operative Kanäle einschließlich, *Ansagen*, *Custodial*und *Apotheke*enthalten, aber wir auch stellen ein Skript Unterschreitung erweitert die Vorlage mit einer Vielzahl von zusätzlichen Abteilung oder spezielle-centric Kanäle, denen Sie hinzufügen können, löschen aus, oder bearbeiten nach Belieben. Beispielsweise wenn Sie über eine Abteilung *Endokrinologie* , jedoch nicht einen Kanal für *Ophthalmology benötigen*, kann dann das Skript angepasst werden, um einen DDE-Kanal *Endokrinologie* enthalten, und entfernen Sie den Kanal *Ophthalmology* . Es wird empfohlen, diese spezielle oder Bezirk modelliert Kanäle nicht automatisch-favorisierte Benachrichtigung Sättigung vermieden werden. Im Allgemeinen bevorzugten Benutzer alle Kanäle, dass sie relevanten finden.

|Basisvorlage-Typ |baseTemplateId |Geplante Vorlage Kanäle|
|:--- |:---|:---|
|Gesundheitswesen - Krankenhaus | https://<span></span>Diagramm<span></span>.microsoft.com/beta/teamsTemplates/healthcareWardWide   | Ansagen\* <br> Compliance\* <br> Hilfreiche Informationen\* <br>Freiheitsentziehenden<br>Finanzen<br>Personalwesen <br>Labor<br> Apotheke |
| | |  |

\*Automatische favorisierte 

## <a name="how-to-use-first-party-templates"></a>So verwenden Sie die erste Partei-Vorlagen

Um diese Vorlagen zu verwenden, ändern Sie einfach die Eigenschaft 'template@odata.bind' im Textkörper Anforderung von'standard' der oben genannten TemplateIDs.  Weitere Informationen zum Bereitstellen von Vorlagen für Teams, finden im Microsoft Graph- [Artikel über das Erstellen eines Teams](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).

### <a name="example-hospital-template-extension-script"></a>Beispiel: Krankenhaus Vorlage Erweiterungsskript

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/healthcareHospitalWide",
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
              "displayName": "Women’s Health",
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
