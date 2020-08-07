---
title: Erste Schritte mit Teams-Vorlagen mit Microsoft Graph
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Hier erfahren Sie, wie Sie mithilfe von Teamvorlagen in Microsoft Graph Zusammenarbeit mit Kanälen für verschiedene Themen erstellen und apps vorinstallieren, um Inhalte und Dienste bereitzustellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d471446d4c0c05d0c13fdee81018c6287c7dda47
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583524"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Erste Schritte mit Teams-Vorlagen mit Microsoft Graph

> [!NOTE]
> In den Teams-Vorlagen wird derzeit keine private Kanalerstellung unterstützt. Die Erstellung privater Kanäle ist in den Vorlagendefinitionen nicht enthalten.

In den Teams-Vorlagen handelt es sich um vorgefertigte Definitionen einer Teamstruktur, die sich um ein geschäftliches Bedürfnis oder Projekt entwickelt hat. Sie können keine eigene Vorlage erstellen. Stattdessen verwenden Sie die vordefinierten Vorlagen mit Microsoft Graph. Mithilfe von Teams-Vorlagen können Sie schnell umfangreiche Räume für die Zusammenarbeit mit Kanälen für verschiedene Themen erstellen und apps vorinstallieren, um unternehmenskritische Inhalte und Dienste abzurufen. Teams-Vorlagen bieten eine vordefinierte Teamstruktur, die Ihnen bei der einfachen Erstellung konsistenter Teams in Ihrer Organisation helfen kann.

In diesem Artikel erläutern wir die Eigenschaften, die in Vorlagen definiert werden können, welche Basisvorlagen Typen sind und wie Sie ein Team anhand einer Vorlage mit einigen Beispiel Anforderungen erstellen können.

Dieser Artikel ist für Sie da:

- Verantwortlich für das Planen, bereitstellen und Verwalten mehrerer Teams in Ihrer Organisation<br>
- Entwickler, die ein Team programmgesteuert mit vordefinierten Kanälen und Apps erstellen möchten

## <a name="teams-template-capabilities"></a>Teams-Vorlagen Funktionen

Die meisten Eigenschaften in einem Team sind im Lieferumfang enthalten und werden von Vorlagen unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. In der folgenden Tabelle finden Sie eine kurze Zusammenfassung der Inhalte und der nicht in den Teamvorlagen enthaltenen Informationen.

| **Team Eigenschaften, die von Teams-Vorlagen unterstützt werden** | **Team Eigenschaften, die von den Teams-Vorlagen noch nicht unterstützt werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Basis Vorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Team Beschreibung | Kanaleinstellungen |
| Team Sichtbarkeit (öffentlich oder privat) | Connectors |
| Team Einstellungen (beispielsweise Member, Gast, @ Erwähnungen) | Dateien und Inhalte |
| Automatisch bevorzugter Kanal | |
| Installierte App | |
| Angeheftete Tabstopps | |

> [!NOTE]
> In zukünftigen Versionen von Microsoft Teams werden weitere Vorlagen Funktionen hinzugefügt, daher sollten Sie sich über die neuesten Informationen zu den unterstützten Eigenschaften informieren.

## <a name="what-are-base-template-types"></a>Was sind Basisvorlagen Typen?

Basisvorlagen Typen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt hat. Diese Basisvorlagen enthalten häufig proprietäre apps, die in den Store-und teameigenschaften nicht verfügbar sind, die in den Teams-Vorlagen noch nicht einzeln unterstützt werden. Hier erfahren Sie, wie Sie die [Teamvorlagen in der Administratorkonsole](get-started-with-teams-templates.md)verwenden.

Nachdem ein Basis Vorlagentyp definiert wurde, können Sie diese speziellen Vorlagen mit zusätzlichen Eigenschaften erweitern oder außer Kraft setzen, die Sie angeben möchten. Einige Basisvorlagen Typen enthalten jedoch Eigenschaften, die nicht überschrieben werden können.

Standardmäßig ist die Basisvorlage auf **Standard** festgesetzt, der keine zusätzlichen proprietären Apps oder speziellen Eigenschaften enthält. Unten ist die aktuelle Liste der verfügbaren Basisvorlagen Typen aufgeführt.

| Basis Vorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Keine weiteren apps und Eigenschaften |
| Bildung<br>Kurs Team | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Apps<ul><li>OneNote-Kurs Notizbuch (auf der Registerkarte " **Allgemein** " angeheftet) </li><li>Aufgaben-app (angeheftet an die Registerkarte " **Allgemein** ")</li></ul> Team Eigenschaften:<ul><li>Team Sichtbarkeit auf **HiddenMembership** (kann nicht außer Kraft gesetzt werden)</li></ul> |
| Bildung<br>Mitarbeiter Team | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Apps<ul><li>OneNote-Mitarbeiter Notizbuch (auf der Registerkarte " **Allgemein** " angeheftet)</li></ul> |
|Bildung<br>SPS-Team |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps<ul><li>OneNote PLC-Notizbuch (auf der Registerkarte " **Allgemein** " angeheftet)</ul></li>|
| Retail<br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Kanäle<ul><li>UMSCHALT Übergabe</li><li>Lerntools</li></ul>Team Eigenschaften<ul><li>Team Sichtbarkeit auf "öffentlich" eingestellt</li></ul>Mitglieder Berechtigungen<ul><li>Verhindern, dass Mitglieder Kanäle erstellen, aktualisieren oder entfernen</li><li>Verhindern, dass Mitglieder apps hinzufügen oder entfernen</li><li>Verhindern, dass Mitglieder Connectors erstellen, aktualisieren oder entfernen</li></ul> |
| Retail<br>Manager-Zusammenarbeit | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Kanäle<ul><li>UMSCHALT Übergabe</li><li>Lerntools</li></ul>Team Eigenschaften:<ul><li>Team Sichtbarkeit auf "Privat" gesetzt</li></ul>Mitglieder Berechtigungen:<ul><li>Verhindern, dass Mitglieder Kanäle erstellen, aktualisieren oder entfernen</li><li>Verhindern, dass Mitglieder apps hinzufügen oder entfernen</li><li>Verhindern, dass Mitglieder Connectors erstellen, aktualisieren oder entfernen</li></ul>|
| Im Gesundheitswesen<br>Ward |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Kanäle <ul><li>Ankündigungen\*</li><li>Kauert\*</li><li>Runden</li><li>Personal\*</li><li>Schulungen\*</li></ul>\*Automatisch bevorzugte Kanäle |
|Im Gesundheitswesen<br>Krankenhaus | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Kanäle<ul><li>Ankündigungen\*</li><li>Compliance\*</li><li>Freiheits</li><li>Personalwesen</li></li><li>Apotheke</li></ul>\*Automatisch bevorzugter Kanal|
|||

## <a name="related-topics"></a>Verwandte Themen

- [Team erstellen](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)
- [Neues Team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Administratorschulung für Microsoft Teams](itadmin-readiness.md)
- [Erste Schritte mit Vorlagen für Teams im Einzelhandel](get-started-with-retail-teams-templates.md)
- [Erste Schritte mit Teams-Vorlagen für Organisationen im Gesundheitswesen](expand-teams-across-your-org/healthcare/healthcare-templates.md)
