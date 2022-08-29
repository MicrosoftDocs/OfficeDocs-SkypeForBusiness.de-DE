---
title: Erste Schritte mit Teamvorlagen mittels Microsoft Graph
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
- m365-frontline
description: Erfahren Sie mehr über die Teamvorlagen, die nur in Microsoft Graph verfügbar sind.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4251aa0293665b6fd41c66e352ca9c595378259
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2022
ms.locfileid: "67397236"
---
# <a name="get-started-with-team-templates-using-microsoft-graph"></a>Erste Schritte mit Teamvorlagen mittels Microsoft Graph

> [!NOTE]
> Teamvorlagen unterstützen derzeit nicht das Erstellen privater Kanäle. Die Erstellung privater Kanäle ist in Vorlagendefinitionen nicht enthalten.

Eine Teamvorlage in Microsoft Teams ist eine Definition der Struktur eines Teams, die auf einen Geschäftlichen Bedarf oder ein Projekt ausgerichtet ist. Mit Teamvorlagen können Sie schnell und einfach umfangreiche Räume für die Zusammenarbeit mit vordefinierten Einstellungen, Kanälen und Apps erstellen. Teamvorlagen können Ihnen helfen, konsistente Teams in Ihrer Organisation bereitzustellen.

Mit Microsoft Graph können Sie [eigene Vorlagen erstellen](/graph/api/resources/teamtemplate?view=graph-rest-beta) oder die vordefinierten Teamvorlagen verwenden, die in Teams enthalten sind, um Teams zu erstellen. In diesem Artikel erfahren Sie mehr über die Eigenschaften, die in Vorlagen definiert werden können, und die vordefinierten Vorlagen, die nur mit Microsoft Graph verfügbar sind.

Dieser Artikel richtet sich an Folgendes:

- Verantwortlich für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Organisation<br>
- Ein Entwickler, der programmgesteuert ein Team mit vordefinierten Kanälen und Apps erstellen möchte

## <a name="team-template-capabilities"></a>Teamvorlagenfunktionen

Die meisten Eigenschaften in einem Team werden von Vorlagen eingeschlossen und unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Hier ist eine kurze Zusammenfassung dessen, was enthalten ist und was nicht in Teamvorlagen enthalten ist.

| **Teameigenschaften, die von Teamvorlagen unterstützt werden** | **Teameigenschaften, die noch nicht von Teamvorlagen unterstützt werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Vorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Teambeschreibung | Kanaleinstellungen |
| Sichtbarkeit des Teams (öffentlich oder privat) | Connectors |
| Teameinstellungen (z. B. Mitglied, Gast, @Erwähnungen) | Dateien und Inhalte |
| Kanal mit automatischer Favoritenliste | |
| App installiert | |
| Angeheftete Registerkarten | |

> [!NOTE]
> Wir werden in zukünftigen Versionen von Microsoft Teams weitere Vorlagenfunktionen hinzufügen. Schauen Sie sich daher die aktuellsten Informationen zu unterstützten Eigenschaften an.

## <a name="pre-built-templates"></a>Vordefinierte Vorlagen

Vordefinierte Teamvorlagen sind Vorlagen, die wir für bestimmte Branchen erstellt haben. Dies sind die vordefinierten Vorlagen, die nur in Microsoft Graph verfügbar sind.

| Vorlagentyp | TemplateId | Eigenschaften, die mit dieser Vorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('standard')` | Keine zusätzlichen Apps und Eigenschaften |
| Bildung -<br>Kursteam | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationClass')` | Apps:<ul><li>OneNote-Kursnotizbuch (angeheftet an die Registerkarte " **Allgemein** ") </li><li>Aufgaben-App (angeheftet an die Registerkarte " **Allgemein** ")</li></ul> Teameigenschaften:<ul><li>Teamsichtbarkeit auf **"HiddenMembership** " festgelegt (kann nicht überschrieben werden)</li></ul> |
| Bildung -<br>Mitarbeiterteam | `https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationStaff')` | Apps:<ul><li>OneNote-Mitarbeiternotizbuch (angeheftet an die Registerkarte " **Allgemein** ")</li></ul> |
|Bildung -<br>PLG-Team |`https://graph.microsoft.com/v1.0/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<ul><li>OneNote PLC-Notizbuch (angeheftet an die Registerkarte " **Allgemein** ")</ul></li>|

> [!NOTE]
> Eine Liste der vordefinierten Vorlagen, die Sie im Teams-Client und mit Microsoft Graph verwenden können, finden Sie [unter "Erste Schritte mit Teamvorlagen im Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md)".

## <a name="related-articles"></a>Verwandte Artikel

- [Erste Schritte mit Teamvorlagen im Microsoft Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md)
- [Erstellen eines Teams](/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
