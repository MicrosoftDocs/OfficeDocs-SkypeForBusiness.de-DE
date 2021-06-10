---
title: Verwenden von Teamvorlagen im Admin Center
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
description: Erfahren Sie, wie Sie mithilfe von Teamvorlagen mithilfe vorinstallierter Vorlagen Bereiche für die Zusammenarbeit mit Kanälen für verschiedene Themen erstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: bf5a601cfe373f1afa995b1dcd8b1f9adff05877
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856294"
---
# <a name="get-started-with-team-templates-in-the-admin-center"></a>Erste Schritte mit Teamvorlagen im Admin Center

**Die Möglichkeit zum Erstellen von benutzerdefinierten Vorlagen wird für EDU-Kunden noch nicht unterstützt.**

> [!NOTE]
> Private Kanäle und Vertraulichkeitsbezeichnungen werden in Teamvorlagen derzeit nicht unterstützt. Die Erstellung privater Kanäle ist nicht in den Vorlagendefinitionen enthalten. Die Option für Vertraulichkeitsbeschriftung in **Team aus** Vorlagenfluss erstellen wird nicht auf das Team angewendet.

Teamvorlagen sind vordefinierte Definitionen der Teamstruktur, die für einen geschäftlichen Bedarf oder ein geschäftliches Projekt konzipiert ist. Verwenden Sie vordefinierte Vorlagen, oder erstellen Sie eine eigene Vorlage. Mit Teamvorlagen können Sie schnell umfangreiche Bereiche für die Zusammenarbeit mit Kanälen für verschiedene Themen erstellen und Apps vorinstallieren, um unternehmenskritische Inhalte und Dienste einziehen zu können. Teamvorlagen bieten eine vordefinierte Teamstruktur, die Ihnen hilft, im gesamten Unternehmen problemlos einheitliche Teams zu erstellen. Derzeit können Sie ein Team aus einer Vorlage in Teams oder mithilfe von [Microsoft Graph.](get-started-with-teams-templates.md)

In diesem Artikel werden die folgenden Features beschrieben:

- Die Eigenschaften, die in Vorlagen definiert werden können.
- Die Basisvorlagentypen.
- Hier erfahren Sie, wie Sie mithilfe von einigen Beispielanforderungen ein Team aus einer Vorlage erstellen können.

Dieser Artikel ist für Sie, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in der gesamten Organisation zuständig sind.

## <a name="team-template-capabilities"></a>Funktionen für Teamvorlagen

Die meisten Eigenschaften in einem Team werden eingeschlossen und von Vorlagen unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Die folgende Tabelle enthält eine kurze Zusammenfassung der Informationen, die in Teamvorlagen enthalten sind und was nicht.

| **Von Teamvorlagen unterstützte Teameigenschaften** | **Teameigenschaften, die von Teamvorlagen noch nicht unterstützt werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Basisorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Teambeschreibung | Kanaleinstellungen |
| Teamsichtbarkeit (öffentlich oder privat) | Verbinder |
| Teameinstellungen (z. B. Mitglied, Gast, @Erwähnungen) | Dateien und Inhalte |
| AutoFavorite-Kanal | |
| App installiert | |
| Angeheftete Registerkarten | |

> [!NOTE]
> Wir werden in zukünftigen Versionen von Microsoft Teams weitere Vorlagenfunktionen hinzufügen. Überprüfen Sie daher die neuesten Informationen zu unterstützten Eigenschaften.

## <a name="what-are-base-template-types"></a>Was sind Basisvorlagentypen?

Basisvorlagentypen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt hat. Diese Basisvorlagen enthalten häufig proprietäre Apps, die im App Store nicht verfügbar sind.

Nachdem ein Basisvorlagentyp definiert wurde, können Sie diese speziellen Vorlagen mit weiteren Eigenschaften, die Sie angeben möchten, erweitern oder überschreiben. Einige Basisvorlagentypen enthalten Eigenschaften, die nicht überschrieben werden können.

> [!NOTE]
> Vordefinierte Basisvorlagen, die in Microsoft Teams bereitgestellt werden, können dupliziert, aber nicht bearbeitet werden.

| Basisorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ | -------------- | ----------------------------------------------------- |
| Übernehmen Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ecke "Champions"</li> <li>Teamformulare</li><li>Kalender</li></ul> Apps: <ul><li>Wiki</li>  <li>Kanalkalender</li> |
| Verwalten eines Projekts |`com.microsoft.teams.template.ManageAProject`| Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ressourcen</li> <li>Planung</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li><li>Planner</li><li>Listen</li>  </ul> |
| Verwalten eines Ereignisses|`com.microsoft.teams.template.ManageAnEvent` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Budget</li> <li>Inhalt</li><li>Logistik</li> <li>Planung</li> <li> Marketing und PR</li></ul> Apps:<ul><li>Wiki</li><li>Website</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li> <li>Mitarbeiterideen</li> <li>Problem Reporter</li></ul> |
|Mitarbeiter integrieren|`com.microsoft.teams.template.OnboardEmployees` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Mitarbeiterchat</li> <li>Schulung</li></ul>Apps:<ul><li>Wiki</li><li>Communitys</li><li>Planner</li><li>Mitarbeiterideen</li></ul>|
|Helpdesk organisieren| `com.microsoft.teams.template.OrganizeHelpDesk`|Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Häufig gestellte Fragen</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li><li>Planner </li><li>Lob</li><li>Problem Reporter</li></ul> |
| Patientenpflege| `healthcareWard`| Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Huddles</li><li>Runden</li><li>Personal</li><li>Schulung</li></ul> Apps: <ul><li>Wiki</li><li>Listen  </li><li>Genehmigungen</li></ul>|
| Zusammenarbeiten an globalen Krisen oder Veranstaltungen |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Nachrichten auf der ganzen Welt</li><li>Geschäftskontinuität</li><li>Remotearbeit</li><li>Interne Kommas</li><li>Externe Kommas</li><li>Genehmigungsanforderung</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Update für Geschäftsleitung</li></ul>Apps: <ul><li>Lob</li><li>Wiki</li><li>Website</li><li>Planner</li><li>Problem Reporter</li></ul>|
|Bank zweigstelle| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Huddles</li><li>Kundenbesprechungen</li><li>Genehmigungsanforderung </li><li>Durchseringen</li><li>Qualifikationsentwicklung</li><li>Kreditverarbeitung</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Lustiges</li><li>Compliance</li></ul>Apps:<ul><li>Lob </li><li>Problem Reporter</li></ul>|
|Reaktion auf Vorfälle| `com.microsoft.teams.template.CoordinateIncidentResponse`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Logistik</li><li>Planung</li><li>Wiederherstellung</li><li>Dringend</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li> <li>Genehmigungen</li> <li>Prüfung</li> </ul>|
|Krankenhaus| `healthcareHospital` |Kanäle: <ul><li>Allgemein</li><li>Ankündigungen</li><li>Compliance</li><li>Sorgerecht</li><li>Personalwesen</li><li>Apotheke</li></ul> Apps: <ul><li>Wiki</li><li>Listen  </li></ul>|
|Ein Store organisieren| `retailStore` |Kanäle: <ul><li>Allgemein<li>Schichtübergabe</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li></ul>|
|Qualität und Sicherheit |`com.microsoft.teams.template.QualitySafety`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Line 1</li><li>Line 2</li><li>Line 3</li><li>Sicherheit</li><li>Schulung</li><li>Wartung</li><li>Lustiges</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li> <li>Problem Reporter</li> <li>Prüfung</li> </ul>|
|Einzelhandel für Manager| `retailManagerCollaboration` |Kanäle: <ul><li>Allgemein<li>Vorgänge</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li><li>Planner</li></ul>|
||||

Weitere Informationen zu den Vorlagenkategorien finden Sie in den folgenden Kategorien:

- [Finanzvorlagen](financial-teams-templates-in-the-admin-console.md)
- [Allgemeine Vorlagen](general-teams-templates-in-the-admin-console.md)
- [Vorlagen für Behörden](government-teams-templates-in-the-admin-console.md)
- [Vorlagen für das Gesundheitswesen](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Fertigungsvorlagen](manufacturing-teams-templates-in-the-admin-console.md)
- [Einzelhandelsvorlagen](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Grenzwerte für die Vorlagengröße

Vorlagen sind auf eine bestimmte Anzahl von Kanälen, Registerkarten und Apps beschränkt.

 > [!Note]
 > Sie können dem Team weitere Kanäle, Registerkarten und Apps hinzufügen, nachdem es aus einer Vorlage erstellt wurde.

|Feature | Grenzwert|
|-|-|
|Kanäle pro Vorlage | 15 |
|Registerkarten pro Kanal in einer Vorlage | 20 |
|Apps pro Vorlage | 50|
|||

Weitere [Informationen finden Sie](limits-specifications-teams.md) Teams Beschränkungen und Spezifikationen von Daten.

## <a name="manage-templates-in-powershell"></a>Verwalten von Vorlagen in PowerShell

Verwenden Sie die folgenden Cmdlts, um Ihre Vorlagen in PowerShell zu verwalten.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps) 
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps) 
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-topics"></a>Verwandte Themen

- [Erstellen einer benutzerdefinierten Teamvorlage](create-a-team-template.md)
- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](create-template-from-existing-template.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-template-from-existing-team.md)
