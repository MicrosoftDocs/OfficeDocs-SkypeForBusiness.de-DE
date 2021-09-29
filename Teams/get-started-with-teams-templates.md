---
title: Erste Schritte mit Teamvorlagen mithilfe von Microsoft Graph
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: yinchang
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über die Teamvorlagen, die nur in Microsoft-Produkten Graph.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e570faff4ec7138457f7cd52e101a0a3632d64d2
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991114"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Erste Schritte mit Teamvorlagen mithilfe von Microsoft Graph

> [!NOTE]
> Teamvorlagen unterstützen derzeit nicht das Erstellen privater Kanäle. Die Erstellung privater Kanäle ist nicht in Vorlagendefinitionen enthalten.

Eine Teamvorlage in Microsoft Teams ist eine Definition der Teamstruktur, die auf einen geschäftlichen Bedarf oder ein geschäftliches Projekt ausgelegt ist. Mit Teamvorlagen können Sie mit vordefinierten Einstellungen, Kanälen und Apps schnell und einfach umfangreiche Bereiche für die Zusammenarbeit erstellen. Teamvorlagen können Ihnen dabei helfen, konsistente Teams in der gesamten Organisation zu implementieren.

Bei Microsoft Graph können Sie die im Lieferumfang enthaltenen vordefinierten Teamvorlagen Teams Teams erstellen. In diesem Artikel erfahren Sie mehr über die Eigenschaften, die in Vorlagen definiert werden können, und zu den Vorlagen, die nur in Microsoft-Produkten Graph.

Dieser Artikel ist für Sie da:

- Verantwortlich für die Planung, Bereitstellung und Verwaltung mehrerer Teams in der gesamten Organisation<br>
- Ein Entwickler, der programmgesteuert ein Team mit vordefinierten Kanälen und Apps erstellen möchte

## <a name="team-template-capabilities"></a>Funktionen für Teamvorlagen

Die meisten Eigenschaften in einem Team werden eingeschlossen und von Vorlagen unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Hier ist eine kurze Zusammenfassung des Inhalts und der nicht in Teamvorlagen enthaltenen Informationen.

| **Von Teamvorlagen unterstützte Teameigenschaften** | **Teameigenschaften, die von Teamvorlagen noch nicht unterstützt werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Vorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Teambeschreibung | Kanaleinstellungen |
| Teamsichtbarkeit (öffentlich oder privat) | Verbinder |
| Teameinstellungen (z. B. Mitglied, Gast, @Erwähnungen) | Dateien und Inhalte |
| Automatischer Kanalfavorit | |
| App installiert | |
| Angeheftete Registerkarten | |

> [!NOTE]
> In zukünftigen Versionen von Microsoft Teams werden weitere Vorlagenfunktionen hinzugefügt. Überprüfen Sie daher die neuesten Informationen zu unterstützten Eigenschaften.

## <a name="pre-built-templates"></a>Vordefinierte Vorlagen

Vordefinierte Teamvorlagen sind Vorlagen, die wir für bestimmte Branchen erstellt haben. Hier sehen Sie die vordefinierten Vorlagen, die nur in Microsoft-Produkten Graph.

| Vorlagentyp | TemplateId | Eigenschaften, die in dieser Vorlage enthalten sind |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Keine weiteren Apps und Eigenschaften |
| Bildung –<br>Kursteam | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Apps:<ul><li>OneNote Kursnotizbuch (an die Registerkarte **"Allgemein" angeheftet)** </li><li>Aufgaben-App (an die Registerkarte **"Allgemein" angeheftet)**</li></ul> Teameigenschaften:<ul><li>Auf **HiddenMembership festgelegte Teamsichtbarkeit** (kann nicht außer Kraft gesetzt werden)</li></ul> |
| Bildung –<br>Mitarbeiterteam | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Apps:<ul><li>OneNote Mitarbeiternotizbuch (an die Registerkarte **"Allgemein" angeheftet)**</li></ul> |
|Bildung –<br>PLG-Team |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<ul><li>OneNote PLG-Notizbuch (an die Registerkarte **"Allgemein" angeheftet)**</ul></li>|

> [!NOTE]
> Eine Liste der vordefinierten Vorlagen, die Sie im Teams-Client und mit Microsoft Graph verwenden können, finden Sie unter Erste Schritte mit Teamvorlagen im [Teams Admin Center.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="related-articles"></a>Verwandte Artikel

- [Erste Schritte mit Teamvorlagen im Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
- [Erstellen eines Teams](/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)
- [Neues Team](/powershell/module/teams/New-Team?view=teams-ps)
