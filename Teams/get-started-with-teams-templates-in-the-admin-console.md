---
title: Erste Schritte mit Teamvorlagen im Teams Admin Center
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
description: Informationen zu Teamvorlagen und deren Verwaltung finden Sie im Microsoft Teams Admin Center.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19333badf3df580129ab7a805cf27c670748d299
ms.sourcegitcommit: 6a65e318d49d8990f2b3409ff7bb2c61ea1f2525
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/29/2021
ms.locfileid: "59991144"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Erste Schritte mit Teamvorlagen im Teams Admin Center

**Die Möglichkeit zum Erstellen von benutzerdefinierten Vorlagen wird für EDU-Kunden noch nicht unterstützt.**

> [!NOTE]
> Private Kanäle und Vertraulichkeitsbezeichnungen werden in Teamvorlagen derzeit nicht unterstützt. Die Erstellung privater Kanäle ist nicht in den Vorlagendefinitionen enthalten. Die Option für Vertraulichkeitsbeschriftung in **Team aus** Vorlagenfluss erstellen wird nicht auf das Team angewendet.

## <a name="overview"></a>Übersicht

Eine Teamvorlage in Microsoft Teams ist eine Definition der Teamstruktur, die auf einen geschäftlichen Bedarf oder ein geschäftliches Projekt ausgelegt ist. Als Administrator können Sie Vorlagen verwenden, um auf einfache Weise konsistente Teams in Der gesamten Organisation zu implementieren. Mit Vorlagen können Benutzer schnell umfangreiche Bereiche für die Zusammenarbeit mit vordefinierten Einstellungen, Kanälen und Apps erstellen.

Sie können Teamvorlagen im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten. Sie können die vordefinierten Vorlagen verwenden, die wir bereitstellen, und Sie können [auch eigene benutzerdefinierte Vorlagen erstellen.](#create-your-own-team-templates) Sie können auch [Vorlagenrichtlinien anwenden,](#apply-team-template-policies) um zu steuern, welche Vorlagen in einem Dokument für Teams.

Dieser Artikel bietet Ihnen einen Überblick über die Arbeit mit Teamvorlagen im Teams Admin Center. Sie erfahren mehr über die eigenschaften, die von Vorlagen unterstützt werden, die von uns erstellten vordefinierten Vorlagen, die Grenzwerte für die Vorlagengröße, das Erstellen und Verwalten von Vorlagen und vieles mehr.

> [!NOTE]
> Ihre Benutzer können Teams aus vordefinierten oder [benutzerdefinierten Teamvorlagen](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) in der App Teams erstellen. Entwickler können Teams auch programmgesteuert aus vordefinierten Teamvorlagen mithilfe von Microsoft Graph. Weitere Informationen finden Sie unter [Erste Schritte mit Teamvorlagen mit Microsoft Graph.](get-started-with-teams-templates.md)

## <a name="team-template-capabilities"></a>Funktionen für Teamvorlagen

Die meisten Eigenschaften in einem Team werden eingeschlossen und von Teamvorlagen unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Hier ist eine Zusammenfassung der enthaltenen und nicht in Teamvorlagen enthaltenen Informationen.

| **Von Teamvorlagen unterstützte Teameigenschaften** | **Teameigenschaften, die von Teamvorlagen noch nicht unterstützt werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Vorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Teambeschreibung | Kanaleinstellungen |
| Teamsichtbarkeit (öffentlich oder privat) | Verbinder |
| Teameinstellungen (z. B. Mitglied, Gast, @Erwähnungen) | Dateien und Inhalte |
| AutoFavorite-Kanal | |
| App installiert | |
| Angeheftete Registerkarten | |

> [!NOTE]
> In zukünftigen Versionen von Microsoft Teams werden weitere Vorlagenfunktionen hinzugefügt. Überprüfen Sie daher die neuesten Informationen zu unterstützten Eigenschaften.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Vordefinierte Teamvorlagen im Teams Admin Center

Dies sind die vordefinierten Teamvorlagen, die im Admin Center Teams sind. Vordefinierte Vorlagen sind Vorlagen, die wir für bestimmte Branchen erstellt haben. Zum Anzeigen dieser Vorlagen wechseln Sie im linken Navigationsbereich Teams Admin Center zu Teams  >  **Teamvorlagen**.

Sie können vordefinierte Vorlagen duplizieren, aber nicht bearbeiten. Wenn Sie die Eigenschaften in einer vordefinierten Vorlage ändern möchten, können Sie eine neue Vorlage aus einer vorhandenen Vorlage erstellen und dann die von Ihnen verwendeten Eigenschaften hinzufügen oder entfernen. Beachten Sie, dass bestimmte Eigenschaften in einigen Vorlagen nicht geändert werden können.

| Vorlagentyp | TemplateId | Eigenschaften, die in dieser Vorlage enthalten sind |
| ------------------ | -------------- | ----------------------------------------------------- |
| Übernehmen Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ecke "Champions"</li> <li>Teamformulare</li><li>Kalender</li></ul> Apps: <ul><li>Wiki</li>  <li>Kanalkalender</li> <li>Meilensteine</li><li>Schwarze Hefter</li></ul>|
| Verwalten eines Projekts |`com.microsoft.teams.template.ManageAProject`| Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ressourcen</li> <li>Planung</li></ul> Apps:<ul><li>Wiki</li><li>OneNote</li><li>Aufgaben</li><li>Listen</li><li>Power Automate</li></ul> |
| Verwalten eines Ereignisses|`com.microsoft.teams.template.ManageAnEvent` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Budget</li> <li>Inhalt</li><li>Logistik</li> <li>Planung</li> <li> Marketing und PR</li></ul> Apps:<ul><li>Wiki</li><li>Website</li> <li>YouTube</li> <li>Aufgaben</li> <li>OneNote</li> <li>Mitarbeiterideen</li> <li>Problem Reporter</li><li>Power Automate</li><li>Schwarze Hefter</li><li>Meilensteine</li></ul> |
|Mitarbeiter integrieren|`com.microsoft.teams.template.OnboardEmployees` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Mitarbeiterchat</li> <li>Schulung</li></ul>Apps:<ul><li>Wiki</li><li>Communitys</li><li>Aufgaben</li><li>Mitarbeiterideen</li><li>Power Automate</li><li>Schwarze Hefter</li><li>Meilensteine</li></ul>|
|Helpdesk organisieren| `com.microsoft.teams.template.OrganizeHelpDesk`|Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Häufig gestellte Fragen</li></ul>Apps:<ul><li>Wiki</li><li>OneNote</li><li>Aufgaben </li><li>Lob</li><li>Problem Reporter</li><li>Power Automate</li><li>Schwarze Hefter</li></ul> |
| Patientenpflege| `com.microsoft.teams.template.healthcareWard`| Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Huddles</li><li>Runden</li><li>Personal</li><li>Schulung</li></ul> Apps: <ul><li>Wiki</li><li>Listen  </li><li>Genehmigungen</li><li>Schwarze Hefter</li><li>Prüfung</li></ul>|
| Kommunikation über Krisen |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Nachrichten auf der ganzen Welt</li><li>Interne Kommas</li><li>Externe Kommas</li><li>Genehmigungen anfordern</li><li>Kundeneskalation</li><li>Update für Geschäftsleitung</li><li>Planung</li><li>Logistik</li></ul>Apps: <ul><li>Website</li><li>Aufgaben</li><li>Problem Reporter</li><li>Genehmigungen</li><li>Schwarze Hefter</li><li>OneNote</li><li>Power Automate</li><li>SharePoint</li></ul>|
|Bank zweigstelle| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Huddles</li><li>Kundenbesprechungen</li><li>Genehmigungen Anforderung </li><li>Durchseringen</li><li>Qualifikationsentwicklung</li><li>Kreditverarbeitung</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Lustiges</li><li>Compliance</li></ul>Apps:<ul><li>Lob </li><li>Problem Reporter</li><li>Wiki</li><li>Kalender</li><li>Genehmigungen</li><li>Schwarze Hefter</li><li>Ideen</li></ul>|
|Reaktion auf Vorfälle| `com.microsoft.teams.template.CoordinateIncidentResponse`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Logistik</li><li>Planung</li><li>Wiederherstellung</li><li>Dringend</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Aufgaben</li> <li>Genehmigungen</li> <li>Prüfung</li> <li>Power Automate</li><li>Schwarze Hefter</li><li>Meilensteine</li></ul>|
|Krankenhaus| `com.microsoft.teams.template.healthcareHospital` |Kanäle: <ul><li>Allgemein</li><li>Ankündigungen</li><li>Compliance</li><li>Sorgerecht</li><li>Personalwesen</li><li>Apotheke</li></ul> Apps: <ul><li>Wiki</li><li>Listen</li><li>Aufgaben</li><li>Genehmigungen</li><li>Schichten</li><li>Schwarze Hefter</li><li>Prüfung</li><li>Ideen</li></ul>|
|Ein Store organisieren| `com.microsoft.teams.template.retailStore` |Kanäle: <ul><li>Allgemein<li>Schichtübergabe</li><li>Store Bereitschaft</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li><li>Aufgaben</li><li>Schichten</li><li>Prüfung</li></ul>|
|Einzelhandel für Manager| `com.microsoft.teams.template.retailManagerCollaboration` |Kanäle: <ul><li>Allgemein<li>Vorgänge</li><li>Lernen</li></ul> Apps: <ul><li>Wiki</li><li>Aufgaben</li><li>Prüfung</li></ul>|
|Qualität und Sicherheit |`com.microsoft.teams.template.QualitySafety`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Leadership</li><li>Wartung</li><li>Production Line 1</li><li>Production Line 2</li><li>Production Line 3</li><li>Gesundheit und Sicherheit</li><li>Schulung</li><li>Lustiges</li></ul> Apps: <ul><li>Wiki</li><li>Aufgaben</li> <li>Problem Reporter</li> <li>Prüfung</li> </ul>|

### <a name="team-templates-by-category-and-industry"></a>Teamvorlagen nach Kategorie und Branche

Weitere Informationen zur Verwendung der vordefinierten Vorlagen in Ihrer Branche finden Sie unter:

- [Vorlage für Finanzteam](financial-teams-templates-in-the-admin-console.md)
- [Allgemeine Teamvorlagen](general-teams-templates-in-the-admin-console.md)
- [Vorlagen für Government-Teams](government-teams-templates-in-the-admin-console.md)
- [Vorlagen für Teams im Gesundheitswesen](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Produktionsteamvorlagen](manufacturing-teams-templates-in-the-admin-console.md)
- [Teamvorlagen für den Einzelhandel](retail-teams-templates-in-the-admin-console.md)

## <a name="team-template-size-limits"></a>Größenbeschränkungen für Teamvorlagen

Vorlagen sind auf eine bestimmte Anzahl von Kanälen, Registerkarten und Apps beschränkt.

 > [!Note]
 > Sie können dem Team weitere Kanäle, Registerkarten und Apps hinzufügen, nachdem es aus einer Vorlage erstellt wurde.

|Feature | Grenzwert|
|-|-|
|Kanäle pro Vorlage | 15 |
|Registerkarten pro Kanal in einer Vorlage | 20 |
|Apps pro Vorlage | 50|
|||

Weitere Informationen finden Sie unter [Beschränkungen und Spezifikationen Teams.](limits-specifications-teams.md)

## <a name="manage-team-templates"></a>Verwalten von Teamvorlagen

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Verwalten von Teamvorlagen im Teams Admin Center

#### <a name="view-team-templates"></a>Anzeigen von Teamvorlagen

Zum Anzeigen von Teamvorlagen wechseln Sie im linken Navigationsbereich Teams Admin Center zu Teams  >  **Teamvorlagen**. Wählen Sie eine Vorlage aus, um weitere Details anzuzeigen, einschließlich der Kanäle und Apps, die sie enthält.

#### <a name="create-your-own-team-templates"></a>Erstellen eigener Teamvorlagen

Sie können eigene benutzerdefinierte Vorlagen von Grund auf neu, aus einem vorhandenen Team und aus einer vorhandenen Vorlage erstellen. Weitere Informationen finden Sie unter:

- [Erstellen einer benutzerdefinierten Teamvorlage](create-a-team-template.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-template-from-existing-team.md)
- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Anwenden von Richtlinien für Teamvorlagen

Um die Vorlagen zu steuern, die Benutzern in Teams zum Erstellen von Teams angezeigt werden, können Sie Vorlagenrichtlinien festlegen und sie Benutzern und Gruppen in Ihrer Organisation zuweisen. Weitere Informationen finden Sie unter [Verwalten von Teamvorlagen im Teams Admin Center.](templates-policies.md)

### <a name="manage-team-templates-using-powershell"></a>Verwalten von Teamvorlagen mit PowerShell

Verwenden Sie die folgenden Cmdlets zum Verwalten Ihrer Vorlagen in PowerShell.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate?view=teams-ps) 
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist?view=teams-ps)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate?view=teams-ps)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate?view=teams-ps) 
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate?view=teams-ps)

## <a name="related-articles"></a>Verwandte Artikel

- [Erstellen eines Teams aus einer Vorlage](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c)
- [Erste Schritte mit Teamvorlagen mithilfe von Microsoft Graph](get-started-with-teams-templates.md) 