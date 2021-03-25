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
description: Erfahren Sie, wie Sie Teams-Vorlagen in Microsoft Graph verwenden, um Räume für die Zusammenarbeit mit Kanälen für verschiedene Themen zu erstellen und Apps zum Bereitstellen von Inhalten und Diensten vorab zu installieren.
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
# <a name="get-started-with-teams-templates-using-microsoft-graph"></a>Erste Schritte mit Teams-Vorlagen mit Microsoft Graph

> [!NOTE]
> Teams-Vorlagen unterstützen derzeit nicht das Erstellen privater Kanäle. Die Erstellung privater Kanäle ist in Vorlagendefinitionen nicht enthalten.

Teams-Vorlagen sind vordefinierte Definitionen der Struktur eines Teams, die für einen geschäftlichen Bedarf oder ein Geschäftsprojekt entwickelt wurden. Sie können [eine eigene Vorlage in der Administratorkonsole erstellen.](get-started-with-teams-templates-in-the-admin-console.md) In Microsoft Graph verwenden Sie die vordefinierten Vorlagen. Mithilfe von Teams-Vorlagen können Sie schnell umfangreiche Zusammenarbeitsräume mit Kanälen für unterschiedliche Themen erstellen und Apps vorab installieren, um unternehmenskritische Inhalte und Dienste zu nutzen. Teams-Vorlagen bieten eine vordefinierte Teamstruktur, mit der Sie problemlos einheitliche Teams in Ihrer Organisation erstellen können.

In diesem Artikel erläutern wir die Eigenschaften, die in Vorlagen definiert werden können, welche Basisvorlagentypen es sich handelt und wie Sie ein paar Beispielanforderungen verwenden können, um ein Team aus einer Vorlage zu erstellen.

Dieser Artikel ist für Sie da, wenn Sie:

- Verantwortlich für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Organisation<br>
- Ein Entwickler, der programmgesteuert ein Team mit vordefinierten Kanälen und Apps erstellen möchte

## <a name="teams-template-capabilities"></a>Vorlagenfunktionen von Teams

Die meisten Eigenschaften in einem Team werden von Vorlagen eingeschlossen und unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Die folgende Tabelle enthält eine schnelle Zusammenfassung der enthaltenen und nicht in Teams-Vorlagen enthaltenen Informationen.

| **Teameigenschaften, die von Teams-Vorlagen unterstützt werden** | **Teameigenschaften, die noch nicht von Teams-Vorlagen unterstützt werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Basisorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Teambeschreibung | Kanaleinstellungen |
| Sichtbarkeit des Teams (öffentlich oder privat) | Connectors |
| Teameinstellungen (z. B. Mitglied, Gast, @Erwähnungen) | Dateien und Inhalte |
| Autofavoritenkanal | |
| App installiert | |
| Angeheftet Registerkarten | |

> [!NOTE]
> Wir werden in zukünftigen Versionen von Microsoft Teams weitere Vorlagenfunktionen hinzufügen, also schauen Sie sich die neuesten Informationen zu unterstützten Eigenschaften an.

## <a name="what-are-base-template-types"></a>Was sind Basisvorlagentypen?

Basisvorlagentypen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt hat. Diese Basisvorlagen enthalten häufig proprietäre Apps, die im Store nicht verfügbar sind. Darüber hinaus enthalten Basisvorlagen häufig Teameigenschaften, die in Teams-Vorlagen noch nicht einzeln unterstützt werden. Erfahren Sie, wie Sie die [Teamvorlagen in Microsoft Graph verwenden.](get-started-with-teams-templates.md)

Nachdem ein Basisvorlagentyp definiert wurde, können Sie diese speziellen Vorlagen mit zusätzlichen Eigenschaften erweitern oder überschreiben, die Sie angeben möchten. Einige Basisvorlagentypen enthalten Eigenschaften, die nicht überschrieben werden können.

Standardmäßig ist die Basisvorlage auf **Standard festgelegt,** der keine zusätzlichen proprietären Apps oder speziellen Eigenschaften enthält. Nachfolgend finden Sie die aktuelle Liste der verfügbaren Basisvorlagentypen.

| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('standard')` | Keine zusätzlichen Apps und Eigenschaften |
| Ausbildung –<br>Kursteam | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationClass')` | Apps:<ul><li>OneNote-Kursnotizbuch (an die Registerkarte **Allgemein angeheftet)** </li><li>Aufgaben-App (an die Registerkarte **Allgemein angeheftet)**</li></ul> Teameigenschaften:<ul><li>Auf **HiddenMembership** festgelegte Teamsichtbarkeit (kann nicht außer Kraft gesetzt werden)</li></ul> |
| Ausbildung –<br>Mitarbeiterteam | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationStaff')` | Apps:<ul><li>OneNote-Mitarbeiternotizbuch (an die Registerkarte **Allgemein angeheftet)**</li></ul> |
|Ausbildung –<br>PLC-Team |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('educationProfessionalLearningCommunity')` | Apps:<ul><li>OneNote PLC-Notizbuch (an die Registerkarte **Allgemein angeheftet)**</ul></li>|
| Einzelhandel - <br>Store | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailStore')` | Kanäle:<ul><li>Schichtübergabe</li><li>Lernen</li></ul>Teameigenschaften<ul><li>Teamsichtbarkeit auf Öffentlich gesetzt</li></ul>Mitgliedsberechtigungen<ul><li>Verhindern, dass Mitglieder Kanäle erstellen, aktualisieren oder entfernen</li><li>Verhindern, dass Mitglieder Apps hinzufügen oder entfernen</li><li>Verhindern, dass Mitglieder Verbinder erstellen, aktualisieren oder entfernen</li></ul> |
| Einzelhandel - <br>Zusammenarbeit mit Managern | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('retailManagerCollaboration')` | Kanäle:<ul><li>Lernen</li><li>Vorgänge</li></ul>Teameigenschaften:<ul><li>Teamsichtbarkeit auf Privat gesetzt</li></ul>Mitgliedsberechtigungen:<ul><li>Verhindern, dass Mitglieder Kanäle erstellen, aktualisieren oder entfernen</li><li>Verhindern, dass Mitglieder Apps hinzufügen oder entfernen</li><li>Verhindern, dass Mitglieder Verbinder erstellen, aktualisieren oder entfernen</li></ul>|
| Gesundheitswesen –<br>Ward |`https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')` |Kanäle: <ul><li>Ankündigungen\*</li><li>Huddles\*</li><li>Runden</li><li>Personal\*</li><li>Schulung\*</li></ul>\*Automatisch favorisierte Kanäle |
|Gesundheitswesen –<br>Krankenhaus | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')` |Kanäle:<ul><li>Ankündigungen\*</li><li>Compliance\*</li><li>Sorgerecht</li><li>Personalwesen</li></li><li>Apotheke</li></ul>\*Kanal mit automatischer Favoritenliste|
|||


Verwenden Sie die folgenden Vorlagen, um Teams sowohl im Teams-Client als auch in Microsoft Graph zu erstellen.


| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Office 365 übernehmen |`com.microsoft.teams.template.`<br>`AdoptOffice365`|  Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Champions Corner</li> <li>Teamformulare</li></ul> Apps: <ul><li>Wiki</li>  <li>Kalender</li> |
| Verwalten eines Projekts |`com.microsoft.teams.template.`<br>`ManageAProject`| Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ressourcen</li> <li>Planung</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Verwalten eines Ereignisses|`com.microsoft.teams.template.`<br>`ManageAnEvent` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Budget</li> <li>Inhalt</li><li>Logistik</li> <li>Planung</li> <li> Marketing und PR</li></ul> Apps:<ul><li>Wiki</li><li>Website</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Mitarbeiter an Bord|`com.microsoft.teams.template.`<br>`OnboardEmployees` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Mitarbeiterchat</li> <li>Schulung</li></ul>Apps:<ul><li>Wiki</li><li>Communitys</li></ul>|
|Organisieren des Helpdesks| `com.microsoft.teams.template.`<br>`OrganizeHelpDesk`|Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Häufig gestellte Fragen</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li></ul> |
| Arbeiten Sie bei der Patientenversorgung zusammen| `healthcareWard `| Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Huddles</li><li>Runden</li><li>Personal</li><li>Schulung</li></ul> Apps: <ul><li>Wiki</li>|
| Zusammenarbeiten an globalen Krisen oder Ereignisse |`com.microsoft.teams.template.`<br>`CollaborateOnAGlobalCrisisOrEvent`| Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>News aus der Welt</li><li>Geschäftskontinuität</li><li>Remotearbeit</li><li>Interne Kommas</li><li>Externe Kommas</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Executive Update</li></ul>Apps: <ul><li>Lob</li><li>Wiki</li><li>Website</li></ul>|
|Zusammenarbeit innerhalb einer Bankfiliale| `com.microsoft.teams.template.`<br>`CollaborateWithinABankBranch `|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Huddles</li><li>Kundenbesprechungen</li><li>Coachen</li><li>Qualifikationsentwicklung</li><li>Kreditverarbeitung</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Lustige Dinge</li><li>Compliance</li></ul>|
|Koordinieren der Reaktion auf Vorfälle| `com.microsoft.teams.template.`<br>`CoordinateIncidentResponse`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Logistik</li><li>Planung</li><li>Wiederherstellung</li><li>Dringend</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Krankenhaus| `healthcareHospita`l |Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Compliance</li><li>Sorgerecht</li><li>Personalwesen</li><li>Apotheke</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Ein Store organisieren| `retailStore` |Kanäle: <ul><li>Allgemein<li>Schichtübergabe</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Qualität und Sicherheit |`com.microsoft.teams.`<br>`template.QualitySafety`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Zeile 1</li><li>Zeile 2</li><li>Zeile 3</li><li>Sicherheit</li><li>Schulung</li><li>Wartung</li><li>Lustige Dinge</li></ul> Apps: <ul><li>Wiki</li></ul>|
|Zusammenarbeit zwischen Einzelhandel und Manager| `retailManagerCollaboration` |Kanäle: <ul><li>Allgemein<li>Vorgänge</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li></ul>|
||||

Weitere Informationen finden Sie unter Erste Schritte mit Teams-Vorlagen im [Admin Center.](get-started-with-teams-templates-in-the-admin-console.md)

## <a name="related-topics"></a>Verwandte Themen

- [Erste Schritte mit Teams-Vorlagen in der Administratorkonsole](get-started-with-teams-templates-in-the-admin-console.md)
- [Team erstellen](/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)
- [New-Team](/powershell/module/teams/New-Team?view=teams-ps)
- [Administratorschulung für Microsoft Teams](itadmin-readiness.md)