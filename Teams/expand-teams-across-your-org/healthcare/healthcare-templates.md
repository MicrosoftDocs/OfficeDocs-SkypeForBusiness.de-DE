---
title: Vorlagen für Organisationen im Gesundheitswesen
author: serdarsoysal
ms.author: serdars
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
description: Verwenden Sie Microsoft Teams-Vorlagen mit Microsoft Graph, um Teams schnell und einfach zu erstellen, indem Sie eine vordefinierte Vorlage für Einstellungen, Kanäle und Apps bereitstellen.
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX
ms.openlocfilehash: e288bc68c8160fb80d4e56a6477437e0a79fea0a
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260337"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a>Erste Schritte mit Vorlagen für Teams für Organisationen im Gesundheitswesen

Mit Microsoft Teams-Vorlagen können Sie Teams schnell und einfach erstellen, indem Sie eine vordefinierte Vorlage für Einstellungen, Kanäle und vorinstallierte Apps bereitstellen.

Für Organisationen im Gesundheitswesen können Vorlagen besonders leistungsfähig sein, da sie den Benutzern eine Struktur bieten, um sich mit der effektiven Nutzung von Teams zu orientieren. Vorlagen ermöglichen Administratoren außerdem die Bereitstellung einheitlicher Teams in der gesamten Organisation. Dieser Artikel ist für Sie da, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams im gesamten Gesundheitswesen zuständig sind.

Wir bieten derzeit zwei Vorlagen für das Gesundheitswesen von Erstpartei an, die Sie für eine Vielzahl von Situationen verwenden können. Weitere allgemeine Informationen zu Teamvorlagen finden Sie unter ["Erste Schritte mit Teams-Vorlagen".](../../get-started-with-teams-templates.md)

## <a name="ward-template"></a>Vorlage "Vorlage Vorlage"

Die Vorlage "Vorlage" ist für Kommunikation und Zusammenarbeit innerhalb eines Orts, einer Abteilung oder einer Abteilung gedacht. Die Vorlage kann verwendet werden, um die Patientenverwaltung sowie die operationalen Anforderungen eines Patienten zu erleichtern. So können beispielsweise Sprechankündigungen  im Kanal "Ankündigungen" veröffentlicht werden, und Schichten können in *"Mitarbeiter" verwaltet werden.* Wenn Sie Ihre Operationsvorgänge für Ihre Gänge optimieren möchten, ist diese Vorlage für Sie da.

|Basisvorlagentyp |baseTemplateId |Basisplanvorlagenkanäle|
|:--- |:---|:---|
|Gesundheitswesen – Gesundheitswesen | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | Ankündigungen\* <br> Huddles\* <br> Rundet\* <br> Personal\* <br> Schulungen\* |
|     | |         |

\* Automatische Favoriten

## <a name="hospital-template"></a>Vorlage "Hospital"

Die Vorlage "Hospital" ist für die Kommunikation und Zusammenarbeit zwischen mehreren Kliniken, Pods und Abteilungen innerhalb eines Krankenhauses gedacht. Diese Vorlage enthält mehrere Betriebskanäle, darunter "Ankündigungen", "Gewahrsam" und "Einsatz" *.* Wir stellen jedoch auch ein Skript darunter zur Verfügung, das die Vorlage um eine Vielzahl zusätzlicher, auf Abteilungs- oder spezialorientierter Kanäle erweitert, die Sie Ihren Wünschen hinzufügen, löschen oder bearbeiten können. Wenn Sie z.  B. über eine Abteilung für Gesichtsuntersuchungen verfügen, aber keinen Kanal für  *Sichteny* benötigen, kann das Skript so angepasst werden, dass es einen Kanal für DieOlogie enthält und den Kanal *"Weiter" entfernt.* Wir empfehlen, diese speziellen Kanäle oder im Modell modellierten Kanäle nicht automatisch als Favoriten zu verwenden, um eine Benachrichtigungssättigung zu vermeiden. Benutzer favorisierten im Allgemeinen Kanäle, die sie für relevant finden.

|Basisvorlagentyp |baseTemplateId |Basisplanvorlagenkanäle|
|:--- |:---|:---|
|Gesundheitswesen – Hospital | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | Ankündigungen\* <br> Compliance\* <br> Custodial <br> Personalwesen <br> 1-1 |
| | |  |

\* Automatische Favoriten 

## <a name="how-to-use-first-party-templates"></a>Verwenden von Vorlagen von Erstpartei

Wenn Sie diese Vorlagen verwenden möchten, ändern Sie einfach die template@odata.bind-Eigenschaft im Anforderungstext von "standard" in die vorstehenden TemplateIDs.  Weitere Informationen zum Bereitstellen von Vorlagen für Teams finden Sie im Microsoft Graph-Artikel zum Erstellen [eines Teams.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)

> [!NOTE]
> Die Kanäle in der Vorlage werden automatisch auf der Registerkarte "Allgemein" erstellt.

### <a name="example-hospital-template-extension-script"></a>Beispiel: Erweiterungsskript für die Vorlage "Hospital"

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

[Erste Schritte mit Vorlagen für Teams in der Verwaltungskonsole](../../get-started-with-teams-templates-in-the-admin-console.md)
