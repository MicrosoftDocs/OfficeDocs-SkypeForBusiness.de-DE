---
title: Verwenden von Teams-Vorlagen im Admin Center
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: aaglick
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie mithilfe von Teams-Vorlagen Räume für die Zusammenarbeit mit Kanälen für verschiedene Themen mithilfe vorinstallierter Vorlagen erstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ad7b25a645948bae404a890f88ab29a14150f4d5
ms.sourcegitcommit: 29646ef386f693ecb9b740a473fba4365b187210
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51188317"
---
# <a name="get-started-with-teams-templates-in-the-admin-center"></a>Erste Schritte mit Teams-Vorlagen im Admin Center

**Die Möglichkeit zum Erstellen benutzerdefinierter Vorlagen wird für EDU-Kunden noch nicht unterstützt.**

> [!NOTE]
> Private Kanäle und Vertraulichkeitsbeschriftungen werden derzeit in Teams-Vorlagen nicht unterstützt. Die Erstellung privater Kanäle ist in Vorlagendefinitionen nicht enthalten. Die Option "Vertraulichkeitsbeschriftung" in **Team aus** Vorlagenfluss erstellen wird nicht auf das Team angewendet.

Teams-Vorlagen sind vordefinierte Definitionen der Struktur eines Teams, die für einen geschäftlichen Bedarf oder ein Geschäftsprojekt entwickelt wurden. Verwenden Sie vordefinierte Vorlagen, oder erstellen Sie eine eigene Vorlage. Mit Teams-Vorlagen können Sie schnell umfangreiche Zusammenarbeitsräume mit Kanälen für unterschiedliche Themen erstellen und Apps vorab installieren, um unternehmenskritische Inhalte und Dienste zu nutzen. Teams-Vorlagen bieten eine vordefinierte Teamstruktur, mit der Sie problemlos einheitliche Teams in Ihrer Organisation erstellen können. Derzeit können Sie ein Team aus einer Vorlage in Teams oder mithilfe von [Microsoft Graph erstellen.](get-started-with-teams-templates.md)

In diesem Artikel werden die folgenden Features beschrieben:

- Die Eigenschaften, die in Vorlagen definiert werden können.
- Die Basisvorlagentypen.
- So können Sie ein paar Beispielanforderungen verwenden, um ein Team aus einer Vorlage zu erstellen.

Dieser Artikel ist für Sie da, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Organisation zuständig sind.

## <a name="teams-template-capabilities"></a>Vorlagenfunktionen von Teams

Die meisten Eigenschaften in einem Team werden von Vorlagen eingeschlossen und unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Die folgende Tabelle enthält eine schnelle Zusammenfassung der enthaltenen und nicht in Teams-Vorlagen enthaltenen Informationen.

| **Teameigenschaften, die von Teams-Vorlagen unterstützt werden** | **Teameigenschaften, die noch nicht von Teams-Vorlagen unterstützt werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Basisorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Teambeschreibung | Kanaleinstellungen |
| Sichtbarkeit des Teams (öffentlich oder privat) | Connectors |
| Teameinstellungen (z. B. Mitglied, Gast, @Erwähnungen) | Dateien und Inhalte |
| Autofavorite-Kanal | |
| App installiert | |
| Angeheftet Registerkarten | |

> [!NOTE]
> Wir werden in zukünftigen Versionen von Microsoft Teams weitere Vorlagenfunktionen hinzufügen, also schauen Sie sich die neuesten Informationen zu unterstützten Eigenschaften an.

## <a name="what-are-base-template-types"></a>Was sind Basisvorlagentypen?

Basisvorlagentypen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt hat. Diese Basisvorlagen enthalten häufig proprietäre Apps, die im App Store nicht verfügbar sind.

Nachdem ein Basisvorlagentyp definiert wurde, können Sie diese speziellen Vorlagen mit weiteren Eigenschaften erweitern oder überschreiben, die Sie angeben möchten. Einige Basisvorlagentypen enthalten Eigenschaften, die nicht überschrieben werden können.

> [!NOTE]
> Vordefinierte Basisvorlagen, die in Microsoft Teams bereitgestellt werden, können dupliziert, aber nicht bearbeitet werden.

| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Office 365 übernehmen |`com.microsoft.teams.template.AdoptOffice365`|  Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Champions Corner</li> <li>Teamformulare</li></ul> Apps: <ul><li>Wiki</li>  <li>Kalender</li> |
| Verwalten eines Projekts |`com.microsoft.teams.template.ManageAProject`| Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ressourcen</li> <li>Planung</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>Listen</li>  </ul> |
| Verwalten eines Ereignisses|`com.microsoft.teams.template.ManageAnEvent` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Budget</li> <li>Inhalt</li><li>Logistik</li> <li>Planung</li> <li> Marketing und PR</li></ul> Apps:<ul><li>Wiki</li><li>Website</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Mitarbeiter an Bord|`com.microsoft.teams.template.OnboardEmployees` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Mitarbeiterchat</li> <li>Schulung</li></ul>Apps:<ul><li>Wiki</li><li>Communitys</li><li>Planner</li></ul>|
|Organisieren des Helpdesks| `com.microsoft.teams.template.OrganizeHelpDesk`|Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Häufig gestellte Fragen</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>Lob</li></ul> |
| Arbeiten Sie bei der Patientenversorgung zusammen| `healthcareWard`| Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Huddles</li><li>Runden</li><li>Personal</li><li>Schulung</li></ul> Apps: <ul><li>Wiki</li><li>Listen  </li></ul>|
| Zusammenarbeiten an globalen Krisen oder Ereignisse |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>News aus der Welt</li><li>Geschäftskontinuität</li><li>Remotearbeit</li><li>Interne Kommas</li><li>Externe Kommas</li><li>Genehmigungsanfrage</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Executive Update</li></ul>Apps: <ul><li>Lob</li><li>Wiki</li><li>Website</li><li>Planner</li></ul>|
|Zusammenarbeit innerhalb einer Bankfiliale| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Huddles</li><li>Kundenbesprechungen</li><li>Genehmigungsanfrage </li><li>Coachen</li><li>Qualifikationsentwicklung</li><li>Kreditverarbeitung</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Lustige Dinge</li><li>Compliance</li></ul>Apps:<ul><li>Lob </li></ul>|
|Koordinieren der Reaktion auf Vorfälle| `com.microsoft.teams.template.CoordinateIncidentResponse`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Logistik</li><li>Planung</li><li>Wiederherstellung</li><li>Dringend</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Krankenhaus| `healthcareHospital` |Kanäle: <ul><li>Allgemein</li><li>Ankündigungen</li><li>Compliance</li><li>Sorgerecht</li><li>Personalwesen</li><li>Apotheke</li></ul> Apps: <ul><li>Wiki</li><li>Listen  </li></ul>|
|Ein Store organisieren| `retailStore` |Kanäle: <ul><li>Allgemein<li>Schichtübergabe</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li></ul>|
|Qualität und Sicherheit |`com.microsoft.teams.template.QualitySafety`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Zeile 1</li><li>Zeile 2</li><li>Zeile 3</li><li>Sicherheit</li><li>Schulung</li><li>Wartung</li><li>Lustige Dinge</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li></ul>|
|Zusammenarbeit zwischen Einzelhandel und Manager| `retailManagerCollaboration` |Kanäle: <ul><li>Allgemein<li>Vorgänge</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li></ul>|
||||

Weitere Informationen zu den Vorlagenkategorien finden Sie in den folgenden Kategorien:

- [Finanzvorlagen](financial-teams-templates-in-the-admin-console.md)
- [Allgemeine Vorlagen](general-teams-templates-in-the-admin-console.md)
- [Vorlagen für Behörden](government-teams-templates-in-the-admin-console.md)
- [Vorlagen für das Gesundheitswesen](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Fertigungsvorlagen](manufacturing-teams-templates-in-the-admin-console.md)
- [Einzelhandelsvorlagen](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Größenbeschränkungen für Vorlagen

Vorlagen sind auf eine bestimmte Anzahl von Kanälen, Registerkarten und Apps beschränkt.

 > [!Note]
 > Sie können dem Team weitere Kanäle, Registerkarten und Apps hinzufügen, nachdem es aus einer Vorlage erstellt wurde.

|Feature | Limit|
|-|-|
|Kanäle pro Vorlage | 15 |
|Registerkarten pro Kanal in einer Vorlage | 20 |
|Apps pro Vorlage | 50|
|||

Weitere Informationen finden Sie unter Grenzwerte und Spezifikationen von [Teams.](limits-specifications-teams.md)

## <a name="related-topics"></a>Verwandte Themen

- [Erstellen einer benutzerdefinierten Teamvorlage](create-a-team-template.md)
- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](create-template-from-existing-template.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-template-from-existing-team.md)
