---
title: Erste Schritte mit Teams vorlagen mithilfe von Microsoft Graph
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
description: Erfahren Sie, wie Teams-Vorlagen in Microsoft Graph verwenden, um Bereiche für die Zusammenarbeit mit Kanälen für verschiedene Themen zu erstellen und Apps vorinstallieren, um Inhalte und Dienste zur Verfügung zu stellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 898adc4b67124fb6244afde2ecc156996e5a38c4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120706"
---
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Erste Schritte mit Teams vorlagen mithilfe von Microsoft Graph

> [!NOTE]
> Teams-Vorlagen unterstützen derzeit nicht das Erstellen privater Kanäle. Die Erstellung privater Kanäle ist nicht in Vorlagendefinitionen enthalten.

Teams-Vorlagen sind vordefinierte Definitionen der Teamstruktur, die auf geschäftlichen Bedarf oder ein geschäftliches Projekt ausgelegt ist. Sie können [in der Verwaltungskonsole eine eigene Vorlage erstellen.](get-started-with-teams-templates-in-the-admin-console.md) Bei Microsoft Graph verwenden Sie die vordefinierten Vorlagen . Mithilfe von Teams können Sie schnell umfangreiche Bereiche für die Zusammenarbeit mit Kanälen für verschiedene Themen erstellen und Apps vorinstallieren, um unternehmenskritische Inhalte und Dienste einziehen zu können. Teams-Vorlagen bieten eine vordefinierte Teamstruktur, die Ihnen hilft, im gesamten Unternehmen problemlos einheitliche Teams zu erstellen.

In diesem Artikel werden die Eigenschaften erläutert, die in Vorlagen definiert werden können, welche Basisvorlagentypen es sich handelt und wie Sie einige Beispielanforderungen verwenden können, um ein Team aus einer Vorlage zu erstellen.

Dieser Artikel ist für Sie da:

- Verantwortlich für die Planung, Bereitstellung und Verwaltung mehrerer Teams in der gesamten Organisation<br>
- Ein Entwickler, der programmgesteuert ein Team mit vordefinierten Kanälen und Apps erstellen möchte

## <a name="teams-template-capabilities"></a>Teams von Vorlagenfunktionen

Die meisten Eigenschaften in einem Team werden eingeschlossen und von Vorlagen unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Die folgende Tabelle enthält eine kurze Zusammenfassung der enthaltenen und nicht in den Vorlagen Teams Vorlagen.

| **Teameigenschaften, die von Teams unterstützt werden** | **Teameigenschaften, die von den Vorlagen noch Teams werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Basisorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Teambeschreibung | Kanaleinstellungen |
| Teamsichtbarkeit (öffentlich oder privat) | Verbinder |
| Teameinstellungen (z. B. Mitglied, Gast, @Erwähnungen) | Dateien und Inhalte |
| Automatischer Kanalfavorit | |
| App installiert | |
| Angeheftete Registerkarten | |

> [!NOTE]
> Wir werden in zukünftigen Versionen von Microsoft Teams weitere Vorlagenfunktionen hinzufügen. Überprüfen Sie daher die neuesten Informationen zu unterstützten Eigenschaften.

## <a name="what-are-base-template-types"></a>Was sind Basisvorlagentypen?

Basisvorlagentypen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt hat. Diese Basisvorlagen enthalten häufig proprietäre Apps, die im Store nicht verfügbar sind. Darüber hinaus enthalten Basisvorlagen häufig Teameigenschaften, die in vorlagen noch nicht Teams werden. Erfahren Sie, wie Sie die [Teamvorlagen in Microsoft Graph.](get-started-with-teams-templates.md)

Nachdem ein Basisvorlagentyp definiert wurde, können Sie diese speziellen Vorlagen mit zusätzlichen Eigenschaften, die Sie angeben möchten, erweitern oder überschreiben. Einige Basisvorlagentypen enthalten Eigenschaften, die nicht überschrieben werden können.

Die Basisvorlage ist standardmäßig auf **Standard** festgelegt, der keine weiteren proprietären Apps oder speziellen Eigenschaften enthält. Unten finden Sie die aktuelle Liste der verfügbaren Basisvorlagentypen.

| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Keine weiteren Apps und Eigenschaften |
| Bildung –<br>Kursteam | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Apps:<ul><li>OneNote Kursnotizbuch (an die Registerkarte **"Allgemein" angeheftet)** </li><li>Aufgaben-App (an die Registerkarte **"Allgemein" angeheftet)**</li></ul> Teameigenschaften:<ul><li>Auf **HiddenMembership festgelegte Teamsichtbarkeit** (kann nicht außer Kraft gesetzt werden)</li></ul> |
| Bildung –<br>Mitarbeiterteam | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Apps:<ul><li>OneNote Mitarbeiternotizbuch (an die Registerkarte **"Allgemein" angeheftet)**</li></ul> |
|Bildung –<br>PLG-Team |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<ul><li>OneNote PLG-Notizbuch (an die Registerkarte **"Allgemein" angeheftet)**</ul></li>|
| Einzelhandel - <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Kanäle:<ul><li>Schichtübergabe</li><li>Lernen</li></ul>Teameigenschaften<ul><li>Teamsichtbarkeit auf Öffentlich gesetzt</li></ul>Mitgliedsberechtigungen<ul><li>Verhindern, dass Mitglieder Kanäle erstellen, aktualisieren oder entfernen</li><li>Verhindern, dass Mitglieder Apps hinzufügen oder entfernen</li><li>Verhindern, dass Mitglieder Verbinder erstellen, aktualisieren oder entfernen</li></ul> |
| Einzelhandel - <br>Zusammenarbeit vorgesetzten | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Kanäle:<ul><li>Lernen</li><li>Vorgänge</li></ul>Teameigenschaften:<ul><li>Teamsichtbarkeit auf Privat gesetzt</li></ul>Mitgliedsberechtigungen:<ul><li>Verhindern, dass Mitglieder Kanäle erstellen, aktualisieren oder entfernen</li><li>Verhindern, dass Mitglieder Apps hinzufügen oder entfernen</li><li>Verhindern, dass Mitglieder Verbinder erstellen, aktualisieren oder entfernen</li></ul>|
| Gesundheitswesen –<br>Durchdingen |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Kanäle: <ul><li>Ankündigungen\*</li><li>Huddles\*</li><li>Runden</li><li>Personal\*</li><li>Schulung\*</li></ul>\*Automatisch favorisierte Kanäle |
|Gesundheitswesen –<br>Krankenhaus | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Kanäle:<ul><li>Ankündigungen\*</li><li>Compliance\*</li><li>Sorgerecht</li><li>Personalwesen</li></li><li>Apotheke</li></ul>\*Kanal mit automatischer Favoritenliste|
|||


Verwenden Sie die folgenden Vorlagen zum Erstellen von Teams sowohl im Teams-Client als auch in Microsoft Graph.


| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Übernehmen Office 365 |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ecke "Champions"</li> <li>Teamformulare</li></ul> Apps: <ul><li>Wiki</li>  <li>Kalender</li> |
| Verwalten eines Projekts |`com.microsoft.teams.template.`<br>`ManageAProject`| Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ressourcen</li> <li>Planung</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Verwalten eines Ereignisses|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Budget</li> <li>Inhalt</li><li>Logistik</li> <li>Planung</li> <li> Marketing und PR</li></ul> Apps:<ul><li>Wiki</li><li>Website</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Mitarbeiter integrieren|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Mitarbeiterchat</li> <li>Schulung</li></ul>Apps:<ul><li>Wiki</li><li>Communitys</li></ul>|
|Helpdesk organisieren| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Häufig gestellte Fragen</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Arbeiten Sie bei der Patientenversorgung zusammen| `healthcareWard `| Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Huddles</li><li>Runden</li><li>Personal</li><li>Schulung</li></ul> Apps: <ul><li>Wiki</li>|
| Zusammenarbeiten an globalen Krisen oder Veranstaltungen |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Nachrichten auf der ganzen Welt</li><li>Geschäftskontinuität</li><li>Remotearbeit</li><li>Interne Kommas</li><li>Externe Kommas</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Update für Geschäftsleitung</li></ul>Apps: <ul><li>Lob</li><li>Wiki</li><li>Website</li></ul>|
|Zusammenarbeiten in einer Bankfiliale| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Huddles</li><li>Kundenbesprechungen</li><li>Durchseringen</li><li>Qualifikationsentwicklung</li><li>Kreditverarbeitung</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Lustiges</li><li>Compliance</li></ul>|
|Koordinieren der Reaktion auf Vorfälle| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Logistik</li><li>Planung</li><li>Wiederherstellung</li><li>Dringend</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Krankenhaus| `healthcareHospita`l |Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Compliance</li><li>Sorgerecht</li><li>Personalwesen</li><li>Apotheke</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Ein Store organisieren| `retailStore` |Kanäle: <ul><li>Allgemein<li>Schichtübergabe</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Qualität und Sicherheit |`com.microsoft.teams.`<br>`template.QualitySafety`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Line 1</li><li>Line 2</li><li>Line 3</li><li>Sicherheit</li><li>Schulung</li><li>Wartung</li><li>Lustiges</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Zusammenarbeit zwischen Einzelhandel und Manager| `retailManagerCollaboration` |Kanäle: <ul><li>Allgemein<li>Vorgänge</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li></ul>|
||||

Weitere [Details finden Sie Teams unter Erste](get-started-with-teams-templates-in-the-admin-console.md) Schritte mit Vorlagen im Admin Center.

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teams-Vorlagen in der Verwaltungskonsole](get-started-with-teams-templates-in-the-admin-console.md)
- [Erstellen eines Teams](/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)
- [Neues Team](/powershell/module/teams/New-Team?view=teams-ps)
- [Administratorschulung für Microsoft Teams](itadmin-readiness.md)