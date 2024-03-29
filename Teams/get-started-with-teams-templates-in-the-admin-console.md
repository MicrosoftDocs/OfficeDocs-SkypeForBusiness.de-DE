---
title: Erste Schritte mit Teamvorlagen im Microsoft Teams Admin Center
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
description: Erfahren Sie mehr über Teamvorlagen und deren Verwaltung im Microsoft Teams Admin Center.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 41267db383d39c40ee18a67ee96538f205df52e4
ms.sourcegitcommit: ceba5fd8f098c8d0eafaffe5c5301c845a3ae7ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2022
ms.locfileid: "67837555"
---
# <a name="get-started-with-team-templates-in-the-teams-admin-center"></a>Erste Schritte mit Teamvorlagen im Microsoft Teams Admin Center

**Die Möglichkeit zum Erstellen benutzerdefinierter Vorlagen wird für EDU-Kunden noch nicht unterstützt.**

> [!NOTE]
> - Private und freigegebene Kanäle werden derzeit in Teamvorlagen nicht unterstützt. Die Erstellung privater und freigegebener Kanäle ist in Vorlagendefinitionen nicht enthalten.
>
> - Vertraulichkeitsbezeichnungen werden in Teamvorlagen in GCC-Umgebungen nicht unterstützt. Die Vertraulichkeitsbezeichnungsoption im Vorlagenfluss "Team erstellen" wird nicht auf das Team angewendet.

## <a name="overview"></a>Übersicht

Eine Teamvorlage in Microsoft Teams ist eine Definition der Struktur eines Teams, die auf einen Geschäftlichen Bedarf oder ein Projekt ausgerichtet ist. Als Administrator können Sie Vorlagen verwenden, um konsistente Teams ganz einfach in Ihrer Organisation bereitzustellen. Mit Vorlagen können Ihre Benutzer schnell umfangreiche Räume für die Zusammenarbeit mit vordefinierten Einstellungen, Kanälen und Apps erstellen.

Sie können Teamvorlagen im Microsoft Teams Admin Center oder mithilfe von PowerShell verwalten. Sie können die vordefinierten Vorlagen verwenden, die wir bereitstellen, und Sie können auch [eigene benutzerdefinierte Vorlagen erstellen](#create-your-own-team-templates). Sie können auch [Vorlagenrichtlinien anwenden](#apply-team-template-policies) , um zu steuern, welche Vorlagen ihren Benutzern in Teams zur Verfügung stehen.

In diesem Artikel erhalten Sie einen Überblick über die Arbeit mit Teamvorlagen im Teams Admin Center. Sie erfahren mehr über die Eigenschaften, die in Vorlagen unterstützt werden, die vordefinierten Vorlagen, die wir bereitstellen, Beschränkungen der Vorlagengröße, das Erstellen und Verwalten von Vorlagen und vieles mehr.

> [!NOTE]
> Ihre Benutzer können [Teams aus vordefinierten oder benutzerdefinierten Teamvorlagen in der Teams-App erstellen](https://support.microsoft.com/office/create-a-team-from-a-template-a90c30f3-9940-4897-ab5b-988e69e4cd9c) . Entwickler können teams auch programmgesteuert aus vordefinierten oder benutzerdefinierten Teamvorlagen mitHilfe von Microsoft Graph erstellen. Weitere Informationen finden Sie unter ["Erste Schritte mit Teamvorlagen mit Microsoft Graph](get-started-with-teams-templates.md)".

## <a name="team-template-capabilities"></a>Teamvorlagenfunktionen

Die meisten Eigenschaften in einem Team werden von Teamvorlagen eingeschlossen und unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Hier ist eine Zusammenfassung dessen, was enthalten ist und was nicht in Teamvorlagen enthalten ist.

| **Teameigenschaften, die von Teamvorlagen unterstützt werden** | **Teameigenschaften, die noch nicht von Teamvorlagen unterstützt werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Vorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Teambeschreibung | Kanaleinstellungen |
| Sichtbarkeit des Teams (öffentlich oder privat) | Connectors |
| Teameinstellungen (z. B. Mitglied, Gast, @Erwähnungen) | Dateien und Inhalte |
| AutoFavorite-Kanal | |
| App installiert | |
| Angeheftete Registerkarten | |

> [!NOTE]
> Wir werden in zukünftigen Versionen von Microsoft Teams weitere Vorlagenfunktionen hinzufügen. Schauen Sie sich daher die aktuellsten Informationen zu unterstützten Eigenschaften an.

## <a name="pre-built-team-templates-in-the-teams-admin-center"></a>Vordefinierte Teamvorlagen im Teams Admin Center

Hier sind die vordefinierten Teamvorlagen, die im Teams Admin Center verfügbar sind. Vordefinierte Vorlagen sind Vorlagen, die wir für bestimmte Branchen erstellt haben. Um diese Vorlagen anzuzeigen, wechseln Sie im linken Navigationsbereich des Teams Admin Centers zu **Teams-Teamvorlagen** > .

Sie können vordefinierte Vorlagen duplizieren, aber nicht bearbeiten. Wenn Sie die Eigenschaften in einer vordefinierten Vorlage ändern möchten, können Sie eine neue Vorlage aus einer vorhandenen Vorlage erstellen und dann die gewünschten Eigenschaften hinzufügen oder entfernen. Beachten Sie, dass bestimmte Eigenschaften in einigen Vorlagen nicht geändert werden können.

> [!NOTE]
> Ein Sternchen (*) gibt an, dass es sich bei der Vorlage um eine *mit Microsoft 365 verbundene Vorlage* handelt. Wenn Benutzer ein Team mithilfe der Vorlage erstellen, wird die verbundene SharePoint-Vorlage auf die Website und das Team angewendet. SharePoint-Komponenten wie Seiten, Listen und Power Platform-Integrationen werden automatisch als Registerkarten zum Kanal "Allgemein" im Team hinzugefügt und angeheftet. Benutzer können diese Seiten und Listen direkt in Teams bearbeiten.
>
> Weitere Informationen zu SharePoint-Vorlagen finden Sie [unter Anwenden und Anpassen von SharePoint-Websitevorlagen](https://support.microsoft.com/office/apply-and-customize-sharepoint-site-templates-39382463-0e45-4d1b-be27-0e96aeec8398#ID0EDBJ=Team_site_templates).

>[!div class="mx-tdBreakAll"]
>| Vorlagentyp | TemplateId | Eigenschaften, die mit dieser Vorlage geliefert werden |
>| ------------------ | -------------- | ----------------------------------------------------- |
>| Verwalten eines Projekts* |`com.microsoft.teams.template.ManageAProject`| Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ressourcen</li> <li>Planung</li></ul> Apps:<ul><li>Genehmigungen</li><li>Bulletins</li><li>Listen<ul><li>Projektverfolgung</li><li>Problemverfolgung</li></ul></li><li>Meilensteine</li><li>OneNote</li><li>Power Automate</li><li>SharePoint-Seiten<ul><li>Unsere Website</li></ul></li><li>Aufgaben nach Planner und Aufgaben</li><li>Wiki</li></ul> |
| Verwalten eines Ereignisses*|`com.microsoft.teams.template.ManageAnEvent` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Budget</li> <li>Inhalt</li><li>Logistik</li> <li>Planung</li> <li> Marketing und PR</li></ul> Apps:<ul><li>Genehmigungen</li><li>Bulletins</li> <li>Mitarbeiterideen</li><li>Listen<ul><li>Inhaltsplanung</li></ul></li><li>Meilensteine</li> <li>OneNote</li> <li>Power Automate</li> <li>SharePoint-Seiten<ul><li>Unsere Website</li><li>Über unsere Veranstaltung</li></ul><li>Aufgaben nach Planner und Aufgaben</li><li>Wiki</li> |
|Onboarding von Mitarbeitern*|`com.microsoft.teams.template.OnboardEmployees` | Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Mitarbeiterchat</li> <li>Schulung</li></ul>Apps:<ul><li>Bulletins</li><li>Mitarbeiterideen</li><li>Listen<ul><li>Checkliste für das Onboarding</li></ul></li><li>Meilensteine</li><li>Power Automate</li> <li>SharePoint-Seiten<ul><li>Erste Schritte</li><li>Schulung</li></ul><li>Aufgaben nach Planner und Aufgaben</li><li>Viva Engage</li><li>Wiki</li></ul>|
| Übernehmen Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Kanäle: <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Champions Corner</li> <li>Teamformulare</li><li>Kalender</li></ul> Apps: <ul><li>Wiki</li>  <li>Kanalkalender</li> <li>Meilensteine</li><li>Bulletins</li></ul>
|Organisieren des Helpdesks*| `com.microsoft.teams.template.OrganizeHelpDesk`|Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Häufig gestellte Fragen</li></ul>Apps:<ul><li>Problemberichterstattung</li><li>Listen<ul><li>Geräte</li><li>Tickets</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint-Seiten<ul><li>Unsere Website</li><li>Häufig gestellte Fragen</li></ul></li><li>Aufgaben nach Planner und Aufgaben</li><li>Wiki</li></ul> |
|Reaktion auf Vorfälle| `com.microsoft.teams.template.CoordinateIncidentResponse`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Logistik</li><li>Planung</li><li>Genesung</li><li>Dringende</li></ul> Apps: <ul><li>Wiki</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Aufgaben</li> <li>Genehmigungen</li> <li>Prüfung</li> <li>Power Automate</li><li>Bulletins</li><li>Meilensteine</li></ul>|
| Krisenkommunikation* |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Executive Update</li><li>Planung</li><li>Logistik</li></ul>Apps: <ul><li>Genehmigungen</li><li>Problemberichterstattung</li><li>Listen<ul><li>Inhaltsplanung</li><li>Projektplan</li></ul></li><li>OneNote</li><li>Power Automate</li><li>SharePoint-Seiten<ul><li>Unsere Website</li><li>Neuestes Update</li></ul><li>Aufgaben nach Planner und Aufgaben</li>|
| Verwalten eines Stores*| `com.microsoft.teams.template.retailStore` |Kanäle: <ul><li>Allgemein<li>Übergabe umschalten</li><li>Store-Bereitschaft</li><li>Learning</li></ul> Apps: <ul><li>Genehmigungen</li><li>Prüfung</li><li>Listen<ul><li>Bestandsliste</li></ul></li><li>SharePoint-Seiten<ul><li>Unser Store</li></ul></li><li>Schichten</li><li>Aufgaben nach Planner und Aufgaben</li><li>Wiki</li></ul>|
|Bankfiliale| `com.microsoft.teams.template.CollaborateWithinABankBranch`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Huddles</li><li>Kundenbesprechungen</li><li>Genehmigungsanforderung </li><li>Coaching</li><li>Kompetenzentwicklung</li><li>Kreditverarbeitung</li><li>Kundenbeschwerden</li><li>Kudos</li><li>Lustiges</li><li>Compliance</li></ul>Apps:<ul><li>Lob </li><li>Problemmelder</li><li>Wiki</li><li>Kalender</li><li>Genehmigungen</li><li>Bulletins</li><li>Ideen</li></ul>|
| Patientenversorgung| `com.microsoft.teams.template.healthcareWard`| Kanäle:<ul><li>Allgemein</li><li>Ankündigungen</li><li>Huddles</li><li>Runden</li><li>Personal</li><li>Schulung</li></ul> Apps: <ul><li>Wiki</li><li>Listen  </li><li>Genehmigungen</li><li>Bulletins</li><li>Prüfung</li></ul>|
|Krankenhaus| `com.microsoft.teams.template.healthcareHospital` |Kanäle: <ul><li>Allgemein</li><li>Ankündigungen</li><li>Compliance</li><li>Sorgerecht</li><li>Personalwesen</li><li>Apotheke</li></ul> Apps: <ul><li>Wiki</li><li>Listen</li><li>Aufgaben</li><li>Genehmigungen</li><li>Schichten</li><li>Bulletins</li><li>Prüfung</li><li>Ideen</li></ul>|
|Qualität und Sicherheit |`com.microsoft.teams.template.QualitySafety`|Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Führung</li><li>Wartung</li><li>Produktionslinie 1</li><li>Produktionslinie 2</li><li>Produktionslinie 3</li><li>Gesundheit und Sicherheit</li><li>Schulung</li><li>Lustiges</li></ul> Apps: <ul><li>Wiki</li><li>Aufgaben</li> <li>Problemmelder</li> <li>Prüfung</li> </ul>|
|Einzelhandel für Manager*| `com.microsoft.teams.template.retailManagerCollaboration` |Kanäle: <ul><li>Allgemein<li>Vorgänge</li><li>Lernen</li></ul> Apps: <ul><li>Genehmigungen</li><li>Prüfung</li><li>SharePoint-Seiten<ul><li>Unser Store</li></ul></li><li>Aufgaben nach Planner und Aufgaben</li><li>Wiki</li></ul>|
|Verwalten von Freiwilligen| `com.microsoft.teams.template.ManageVolunteers` |Kanäle: <ul><li>Allgemein<li>Ankündigungen</li><li>Berichterstellung</li><li>Freiwilligenverwaltung</li><li>Engagement-Möglichkeiten</li><li>Onboarding von Freiwilligen</li></ul> Apps: <ul><li>Website</li><li>YouTube</li><li>Power BI</li><li>Power Apps</li><li>Aufgaben</li><li>SharePoint</li><li>OneNote</li></ul>|

### <a name="team-templates-by-category-and-industry"></a>Teamvorlagen nach Kategorie und Branche

Weitere Informationen zur Verwendung der vordefinierten Vorlagen in Ihrer Branche finden Sie unter:

- [Allgemeine Teamvorlagen](general-teams-templates-in-the-admin-console.md)
- [Vorlagen für Finanzteams](financial-teams-templates-in-the-admin-console.md)
- [Vorlagen für Behördenteams](government-teams-templates-in-the-admin-console.md)
- [Teamvorlagen für das Gesundheitswesen](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Teamvorlagen für die Fertigung](manufacturing-teams-templates-in-the-admin-console.md)
- [Vorlagen für gemeinnützige Teams](team-templates-nonprofit.md)
- [Teamvorlagen für den Einzelhandel](get-started-with-retail-teams-templates.md)

## <a name="team-template-size-limits"></a>Größenbeschränkungen für Teamvorlagen

Vorlagen sind auf eine bestimmte Anzahl von Kanälen, Registerkarten und Apps beschränkt.

 > [!Note]
 > Sie können dem Team nach der Erstellung aus einer Vorlage weitere Kanäle, Registerkarten und Apps hinzufügen.

|Feature | Limit|
|-|-|
|Kanäle pro Vorlage | 15 |
|Registerkarten pro Kanal in einer Vorlage | 20 |
|Apps pro Vorlage | 50|

Weitere Informationen finden Sie [unter "Grenzwerte und Spezifikationen von Teams"](limits-specifications-teams.md).

## <a name="manage-team-templates"></a>Verwalten von Teamvorlagen

### <a name="manage-team-templates-in-the-teams-admin-center"></a>Verwalten von Teamvorlagen im Teams Admin Center

#### <a name="view-team-templates"></a>Anzeigen von Teamvorlagen

Um Teamvorlagen anzuzeigen, wechseln Sie in der linken Navigationsleiste des Teams Admin Centers zu **Teams-Teamvorlagen** > . Wählen Sie eine Vorlage aus, um weitere Details anzuzeigen, einschließlich der darin enthaltenen Kanäle und Apps.

#### <a name="create-your-own-team-templates"></a>Erstellen Eigener Teamvorlagen

Sie können eigene benutzerdefinierte Vorlagen von Grund auf neu, aus einem vorhandenen Team und aus einer vorhandenen Vorlage erstellen. Weitere Informationen finden Sie unter:

- [Erstellen einer benutzerdefinierten Teamvorlage](create-a-team-template.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-template-from-existing-team.md)
- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](create-template-from-existing-template.md)

#### <a name="apply-team-template-policies"></a>Anwenden von Richtlinien für Teamvorlagen

Um die Vorlagen zu steuern, die Benutzern in Teams zum [Erstellen von Teams](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b) angezeigt werden, können Sie Vorlagenrichtlinien festlegen und diesen Benutzern und Gruppen in Ihrer Organisation zuweisen. Weitere Informationen finden [Sie unter Verwalten von Teamvorlagen im Teams Admin Center](templates-policies.md).

### <a name="manage-team-templates-using-powershell"></a>Verwalten von Teamvorlagen mithilfe von PowerShell

Verwenden Sie die folgenden Cmdlets, um Ihre Vorlagen in PowerShell zu verwalten.

- [Get-CsTeamTemplate](/powershell/module/teams/get-csteamtemplate)
- [Get-CsTeamTemplateList](/powershell/module/teams/get-csteamtemplatelist)
- [New-CsTeamTemplate](/powershell/module/teams/new-csteamtemplate)
- [Remove-CsTeamTemplate](/powershell/module/teams/remove-csteamtemplate)
- [Update-CsTeamTemplate](/powershell/module/teams/update-csteamtemplate)

## <a name="related-articles"></a>Verwandte Artikel

- [Erstellen eines Teams aus einer Vorlage](https://support.microsoft.com/office/create-a-team-with-team-templates-702a2977-e662-4038-bef5-bdf8ee47b17b)
- [Erste Schritte mit Teamvorlagen mittels Microsoft Graph](get-started-with-teams-templates.md)
- [Klonen eines Teams](/graph/api/team-clone)
- [Übersicht über die Integration von Teams und SharePoint](/sharepoint/teams-connected-sites)
