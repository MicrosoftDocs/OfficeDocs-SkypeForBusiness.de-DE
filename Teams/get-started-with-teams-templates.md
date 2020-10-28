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
ms.openlocfilehash: 484b3ac3fd3545ce306dcb6e3d833bb523df5a86
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772196"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Erste Schritte mit Teams-Vorlagen mit Microsoft Graph

> [!NOTE]
> In den Teams-Vorlagen wird derzeit keine private Kanalerstellung unterstützt. Die Erstellung privater Kanäle ist in den Vorlagendefinitionen nicht enthalten.

In den Teams-Vorlagen handelt es sich um vorgefertigte Definitionen einer Teamstruktur, die sich um ein geschäftliches Bedürfnis oder Projekt entwickelt hat. Sie können [in der Admin-Konsole eine eigene Vorlage erstellen](get-started-with-teams-templates-in-the-admin-console.md). Mit Microsoft Graph verwenden Sie die vordefinierten Vorlagen. Mithilfe von Teams-Vorlagen können Sie schnell umfangreiche Räume für die Zusammenarbeit mit Kanälen für verschiedene Themen erstellen und apps vorinstallieren, um unternehmenskritische Inhalte und Dienste abzurufen. Teams-Vorlagen bieten eine vordefinierte Teamstruktur, die Ihnen bei der einfachen Erstellung konsistenter Teams in Ihrer Organisation helfen kann.

In diesem Artikel erläutern wir die Eigenschaften, die in Vorlagen definiert werden können, welche Basisvorlagen Typen sind und wie Sie mit einigen Beispiel Anforderungen ein Team aus einer Vorlage erstellen können.

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

Basisvorlagen Typen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt hat. Diese Basisvorlagen enthalten häufig proprietäre apps, die im Store nicht zur Verfügung stehen. Darüber hinaus enthalten Basisvorlagen häufig teameigenschaften, die in den Teams-Vorlagen noch nicht einzeln unterstützt werden. Hier erfahren Sie, wie Sie die [Teamvorlagen in Microsoft Graph](get-started-with-teams-templates.md)verwenden.

Nachdem ein Basis Vorlagentyp definiert wurde, können Sie diese speziellen Vorlagen mit zusätzlichen Eigenschaften erweitern oder außer Kraft setzen, die Sie angeben möchten. Einige Basisvorlagen Typen enthalten Eigenschaften, die nicht überschrieben werden können.

Standardmäßig ist die Basisvorlage auf **Standard** festzulegen, die keine zusätzlichen proprietären Apps oder speziellen Eigenschaften enthält. Unten ist die aktuelle Liste der verfügbaren Basisvorlagen Typen aufgeführt.

| Basis Vorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Keine weiteren apps und Eigenschaften |
| Bildung<br>Kurs Team | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Apps<ul><li>OneNote-Kurs Notizbuch (auf der Registerkarte " **Allgemein** " angeheftet) </li><li>Aufgaben-app (angeheftet an die Registerkarte " **Allgemein** ")</li></ul> Team Eigenschaften:<ul><li>Team Sichtbarkeit auf **HiddenMembership** (kann nicht außer Kraft gesetzt werden)</li></ul> |
| Bildung<br>Mitarbeiter Team | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Apps<ul><li>OneNote-Mitarbeiter Notizbuch (auf der Registerkarte " **Allgemein** " angeheftet)</li></ul> |
|Bildung<br>SPS-Team |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps<ul><li>OneNote PLC-Notizbuch (auf der Registerkarte " **Allgemein** " angeheftet)</ul></li>|
| Retail<br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Kanäle<ul><li>UMSCHALT Übergabe</li><li>Lerntools</li></ul>Team Eigenschaften<ul><li>Team Sichtbarkeit auf "öffentlich" eingestellt</li></ul>Mitglieder Berechtigungen<ul><li>Verhindern, dass Mitglieder Kanäle erstellen, aktualisieren oder entfernen</li><li>Verhindern, dass Mitglieder apps hinzufügen oder entfernen</li><li>Verhindern, dass Mitglieder Connectors erstellen, aktualisieren oder entfernen</li></ul> |
| Retail<br>Manager-Zusammenarbeit | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Kanäle<ul><li>Lerntools</li><li>Vorgänge</li></ul>Team Eigenschaften:<ul><li>Team Sichtbarkeit auf "Privat" gesetzt</li></ul>Mitglieder Berechtigungen:<ul><li>Verhindern, dass Mitglieder Kanäle erstellen, aktualisieren oder entfernen</li><li>Verhindern, dass Mitglieder apps hinzufügen oder entfernen</li><li>Verhindern, dass Mitglieder Connectors erstellen, aktualisieren oder entfernen</li></ul>|
| Im Gesundheitswesen<br>Ward |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Kanäle <ul><li>Ankündigungen\*</li><li>Kauert\*</li><li>Runden</li><li>Personal\*</li><li>Schulungen\*</li></ul>\*Automatisch bevorzugte Kanäle |
|Im Gesundheitswesen<br>Krankenhaus | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Kanäle<ul><li>Ankündigungen\*</li><li>Compliance\*</li><li>Freiheits</li><li>Personalwesen</li></li><li>Apotheke</li></ul>\*Automatisch bevorzugter Kanal|
|||


Verwenden Sie die folgenden Vorlagen zum Erstellen von Teams sowohl im Team Client als auch in Microsoft Graph.


| Basis Vorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Übernehmen von Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Champions Corner</li> <li>Team Formulare</li></ul> Apps <ul><li>Wiki-</li>  <li>Kalender</li> |
| Verwalten eines Projekts |`com.microsoft.teams.template.`<br>`ManageAProject`| Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ressourcen</li> <li>Planung</li></ul> Apps<ul><li>Wiki-</li><li>OneNote</li></ul> |
| Verwalten eines Ereignisses|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Budget</li> <li>Inhalt</li><li>Logistik</li> <li>Planung</li> <li> Marketing und PR</li></ul> Apps<ul><li>Wiki-</li><li>Website</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Onboard-Mitarbeiter|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Mitarbeiter-Chat</li> <li>Schulungen</li></ul>Apps<ul><li>Wiki-</li><li>Gemeinschaften</li></ul>|
|Organisieren des Helpdesks| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Kanäle<ul><li>Allgemein</li><li>Ankündigungen</li><li>Häufig gestellte Fragen</li></ul>Apps<ul><li>Wiki-</li><li>OneNote</li></ul> |
| Zusammenarbeit bei der Patientenversorgung| `healthcareWard `| Kanäle<ul><li>Allgemein</li><li>Ankündigungen</li><li>Kauert</li><li>Runden</li><li>Personal</li><li>Schulungen</li></ul> Apps <ul><li>Wiki-</li>|
| Zusammenarbeiten an globaler Krise oder Veranstaltung |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Welt Nachrichten</li><li>Business Continuity</li><li>Remote arbeiten</li><li>Interne Comms</li><li>Externe Comms</li><li>Kundenreklamationen</li><li>Kudos</li><li>Executive-Update</li></ul>Apps <ul><li>Lob</li><li>Wiki-</li><li>Website</li></ul>|
|Zusammenarbeiten in einer Bankfiliale| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Kauert</li><li>Kundenbesprechungen</li><li>Coaching</li><li>Qualifikationsentwicklung</li><li>Kreditbearbeitung</li><li>Kundenreklamationen</li><li>Kudos</li><li>Lustige Sachen</li><li>Compliance</li></ul>|
|Koordinieren der Vorfall Antwort| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Logistik</li><li>Planung</li><li>Recovery</li><li>Dringend</li></ul> Apps <ul><li>Wiki-</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Krankenhaus| `healthcareHospita`l |Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Compliance</li><li>Freiheits</li><li>Personalwesen</li><li>Apotheke</li></ul> Apps <ul><li>Wiki-</li></ul>|
|Organisieren eines Shops| `retailStore` |Kanäle <ul><li>Allgemein<li>UMSCHALT Übergabe</li><li>Lerntools</li></ul> Apps <ul><li>Wiki-</li></ul>|
|Qualität und Sicherheit |`com.microsoft.teams.`<br>`template.QualitySafety`|Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Zeile 1</li><li>Zeile 2</li><li>Zeile 3</li><li>Sicherheit</li><li>Schulungen</li><li>Wartung</li><li>Lustige Sachen</li></ul> Apps <ul><li>Wiki-</li></ul>|
|Zusammenarbeit im Einzelhandel – Manager| `retailManagerCollaboration` |Kanäle <ul><li>Allgemein<li>Vorgänge</li><li>Lerntools</li></ul> Apps <ul><li>Wiki-</li></ul>|
||||

Weitere Informationen finden Sie unter [Erste Schritte mit Microsoft Teams-Vorlagen im Admin Center](get-started-with-teams-templates-in-the-admin-console.md) .

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Microsoft Teams-Vorlagen in der Admin-Konsole](get-started-with-teams-templates-in-the-admin-console.md)
- [Team erstellen](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)
- [Neues Team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Administratorschulung für Microsoft Teams](itadmin-readiness.md)