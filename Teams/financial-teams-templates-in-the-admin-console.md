---
title: Verwenden Sie Vorlagen für Finanzteams
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: yinchang
ms.collection:
- M365-collaboration
ms.localizationpriority: high
search.appverid: MET150
description: Erfahren Sie, wie Sie Finanzteamvorlagen im Teams Admin Center und mit Microsoft Graph verwalten und verwenden, um schnell und einfach Teams für Ihre Finanzdienstleistungsorganisation zu erstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9273f8519fd7aeea90ff35f49ca0d6986afa2d59
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991104"
---
# <a name="use-financial-team-templates"></a>Verwenden Sie Vorlagen für Finanzteams

Mit Teamvorlagen in Microsoft Teams können Sie schnell und einfach Teams erstellen, indem Sie eine vordefinierte Teamstruktur aus Einstellungen, Kanälen und vorinstallierten Apps bereitstellen.

Für Finanzdienstleistungsunternehmen können Teamvorlagen besonders leistungsstark sein, da sie Ihnen helfen, schnell konsistente Teams in Ihrer gesamten Organisation bereitzustellen. Vorlagen helfen den Mitarbeitern auch, sich bei der effektiven Verwendung von Teams zu orientieren.

Teams enthält Vorlagen für Finanzdienstleistungsunternehmen. Verwenden Sie diese vorgefertigten Vorlagen, um schnell Teams zu erstellen, mit denen Mitarbeiter kommunizieren und zusammenarbeiten können. In diesem Artikel stellen wir Ihnen jede dieser Vorlagen vor und empfehlen deren Verwendung.

Wie Sie Teamvorlagen verwalten und damit arbeiten, hängt davon ab, ob Sie Administrator oder Entwickler sind.

|Wenn Sie: | Dann: |
| ---- | --------- |
| Ein Administrator oder IT-Profi |[Verwalten Sie Teamvorlagen im Teams Admin Center](#manage-team-templates-in-the-teams-admin-center). Zeigen Sie Teamvorlagen an und wenden Sie Vorlagenrichtlinien an, um zu steuern, welche Vorlagen Ihre Mitarbeiter in Teams zum Erstellen von Teams verwenden können. |
| Ein Entwickler | [Verwenden Sie Microsoft Graph](#use-team-templates-with-microsoft-graph), um Teams aus Teamvorlagen zu erstellen. |

## <a name="manage-team-templates-in-the-teams-admin-center"></a>Verwalten von Teamvorlagen im Teams Admin Center

Als Administrator können Sie Teamvorlagen im Microsoft Teams Admin Center verwalten. Hier können Sie Details zu jeder Vorlage anzeigen. Sie können Ihren Mitarbeitern auch [Vorlagenrichtlinien erstellen und zuweisen](templates-policies.md), um zu steuern, welche Vorlagen sie in Teams zum [Erstellen von Teams](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) sehen.

Weitere Informationen zu Teamvorlagen im Allgemeinen finden Sie unter [Erste Schritte mit Teamvorlagen im Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md).

Wir bieten derzeit die folgenden vorgefertigten Teamvorlagen für Finanzdienstleistungsunternehmen an. Um sie anzuzeigen, wechseln Sie in der linken Navigation des Teams Admin Center zu **Teams** > **Team-Vorlagen**.

### <a name="collaborate-within-a-bank-branch"></a>Zusammenarbeit in einer Bankfiliale

Zentralisieren Sie die Zusammenarbeit für die Mitarbeiter Ihrer Bank zweigstellenübergreifend über Zusammenkünfte, Kundenbesprechungen und Geschäftsprozesse wie die Zusammenarbeit mit Hypotheken, und halten Sie alle mit Ankündigungen und Kudos auf dem Laufenden.

| Vorlagentyp |TemplateId| Eigenschaften, die mit dieser Vorlage geliefert werden |
| ------------------ |--|----------------------------------------------------- |
|Bankfiliale| `CollaborateWithinABankBranch`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Huddles</li><li>Kundenbesprechungen</li><li>Genehmigungen anfordern </li><li>Coaching</li><li>Kompetenzentwicklung</li><li>Kreditbearbeitung</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Lustiges</li><li>Compliance</li></ul>Apps:<ul><li>Lob </li><li>Problemmelder</li><li>Wiki</li><li>Kalender</li><li>Genehmigungen</li><li>Bulletins</li><li>Ideen</li></ul>|
||||

## <a name="use-team-templates-with-microsoft-graph"></a>Verwenden Sie Teamvorlagen mit Microsoft Graph

Entwickler können Microsoft Graph verwenden, um Teams aus vorgefertigten Teamvorlagen zu erstellen. Weitere Informationen zur Verwendung von Teamvorlagen mit Microsoft Graph finden Sie unter [Erste Schritte mit Teamvorlagen mit Microsoft Graph](get-started-with-teams-templates.md), [Übersicht über die Microsoft Teams-API](/graph/teams-concept-overview?view=graph-rest-1.0), und [teamsTemplate-Ressourcentyp](/graph/api/resources/teamstemplate?view=graph-rest-1.0).

### <a name="bank-branch"></a>Bankfiliale

Zentralisieren Sie die Zusammenarbeit für die Mitarbeiter Ihrer Bank zweigstellenübergreifend über Zusammenkünfte, Kundenbesprechungen und Geschäftsprozesse wie die Zusammenarbeit mit Hypotheken, und halten Sie alle mit Ankündigungen und Kudos auf dem Laufenden.

| Vorlagentyp |TemplateId| Vorlagenkanäle |
| ------------------ |--|----------------------------------------------------- |
|Bankfiliale|`https://graph.microsoft.com/beta/teamsTemplates('CollaborateWithinABankBranch')`|Allgemein<br>Ankündigungen<br>Huddles<br>Kundenbesprechungen<br>Genehmigungen anfordern<br>Coaching<br>Kompetenzentwicklung<br>Kreditbearbeitung<br>Kundenbeschwerden<br>Kudos<br>Lustiges<br>Compliance|
||||

> [!NOTE]
> Weitere Vorlagen, die für die Organisation von Finanzdienstleistungen gelten, finden Sie unter [In Microsoft Graph erstellte Teamvorlagen für kleine und mittlere Unternehmen](smb-templates.md).