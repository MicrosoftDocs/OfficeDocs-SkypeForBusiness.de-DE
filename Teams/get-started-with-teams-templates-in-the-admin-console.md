---
title: Verwenden von Teamvorlagen zum Erstellen eines neuen Teams
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
description: Hier erfahren Sie, wie Sie mithilfe von "Teams-Vorlagen" Zusammenarbeits Räume mit Kanälen für verschiedene Themen über vorinstallierte Vorlagen erstellen.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: e3269a49072f9e050a139d9bd6463ab4c85a358d
ms.sourcegitcommit: 340c2f432b78af4e78b21056af56c6421627045d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294611"
---
# <a name="get-started-with-teams-templates-in-the-admin-console"></a>Erste Schritte mit Microsoft Teams-Vorlagen in der Admin-Konsole

**Benutzerdefinierte Vorlagen werden für edu-Kunden noch nicht unterstützt.**

> [!NOTE]
> In den Teams-Vorlagen wird derzeit keine private Kanalerstellung unterstützt. Die Erstellung privater Kanäle ist in den Vorlagendefinitionen nicht enthalten.

In den Teams-Vorlagen handelt es sich um vorgefertigte Definitionen einer Teamstruktur, die sich um ein geschäftliches Bedürfnis oder Projekt entwickelt hat. Verwenden Sie vordefinierte Vorlagen, oder erstellen Sie eine eigene Vorlage. Mithilfe von "Teams-Vorlagen" können Sie schnell umfangreiche Zusammenarbeit mit Kanälen für verschiedene Themen erstellen und apps vorinstallieren, um unternehmenskritische Inhalte und Dienste abzurufen. Teams-Vorlagen bieten eine vordefinierte Teamstruktur, die Ihnen bei der einfachen Erstellung konsistenter Teams in Ihrer Organisation helfen kann. Derzeit können Sie ein Team aus einer Vorlage in Teams oder mit [Microsoft Graph](get-started-with-teams-templates.md)erstellen.

In diesem Artikel werden die Eigenschaften beschrieben, die in Vorlagen definiert werden können, welche Basisvorlagen Typen sind und wie Sie mit einigen Beispiel Anforderungen ein Team aus einer Vorlage erstellen können.

Dieser Artikel ist für Sie zuständig, wenn Sie für die Planung, Bereitstellung und Verwaltung mehrerer Teams in Ihrer Organisation verantwortlich sind.

## <a name="teams-template-capabilities"></a>Teams-Vorlagen Funktionen

Die meisten Eigenschaften in einem Team sind im Lieferumfang enthalten und werden von Vorlagen unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. In der folgenden Tabelle finden Sie eine kurze Zusammenfassung der Inhalte und der nicht in den Teamvorlagen enthaltenen Informationen.

| **Team Eigenschaften, die von Teams-Vorlagen unterstützt werden** | **Team Eigenschaften, die von den Teams-Vorlagen noch nicht unterstützt werden** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Basis Vorlagentyp | Teammitgliedschaft |
| Teamname | Teambild |
| Team Beschreibung | Kanaleinstellungen |
| Team Sichtbarkeit (öffentlich oder privat) | Connectors |
| Team Einstellungen (beispielsweise Member, Gast, @ Erwähnungen) | Dateien und Inhalte |
| Autofavorite-Kanal | |
| Installierte App | |
| Angeheftete Tabstopps | |

> [!NOTE]
> In zukünftigen Versionen von Microsoft Teams werden weitere Vorlagen Funktionen hinzugefügt, daher sollten Sie sich über die neuesten Informationen zu den unterstützten Eigenschaften informieren.

## <a name="what-are-base-template-types"></a>Was sind Basisvorlagen Typen?

Basisvorlagen Typen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt hat. Diese Basisvorlagen enthalten häufig proprietäre apps, die im App Store nicht zur Verfügung stehen.

Nachdem ein Basis Vorlagentyp definiert wurde, können Sie diese speziellen Vorlagen mit zusätzlichen Eigenschaften erweitern oder außer Kraft setzen, die Sie angeben möchten. Einige Basisvorlagen Typen enthalten Eigenschaften, die nicht überschrieben werden können.

> [!NOTE]
> Vordefinierte Basisvorlagen, die in Microsoft Teams bereitgestellt werden, können dupliziert, aber nicht bearbeitet werden.

| Basis Vorlagentyp | baseTemplateId | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ |----|----------------------------------------------------- |
| Übernehmen von Office 365 |`com.microsoft.teams.template.AdoptOffice365`|  Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Champions Corner</li> <li>Team Formulare</li></ul> Apps <ul><li>Wiki-</li>  <li>Kalender</li> |
| Verwalten eines Projekts |`com.microsoft.teams.template.ManageAProject`| Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ressourcen</li> <li>Planung</li></ul> Apps<ul><li>Wiki-</li><li>OneNote</li></ul> |
| Verwalten eines Ereignisses|`com.microsoft.teams.template.ManageAnEvent` | Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Budget</li> <li>Inhalt</li><li>Logistik</li> <li>Planung</li> <li> Marketing und PR</li></ul> Apps<ul><li>Wiki-</li><li>Website</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Onboard-Mitarbeiter|`com.microsoft.teams.template.OnboardEmployees` | Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Mitarbeiter-Chat</li> <li>Schulungen</li></ul>Apps<ul><li>Wiki-</li><li>Gemeinschaften</li></ul>|
|Organisieren des Helpdesks| `com.microsoft.teams.template.OrganizeHelpDesk`|Kanäle<ul><li>Allgemein</li><li>Ankündigungen</li><li>Häufig gestellte Fragen</li></ul>Apps<ul><li>Wiki-</li><li>OneNote</li></ul> |
| Zusammenarbeit bei der Patientenversorgung| `healthcareWard `| Kanäle<ul><li>Allgemein</li><li>Ankündigungen</li><li>Kauert</li><li>Runden</li><li>Personal</li><li>Schulungen</li></ul> Apps <ul><li>Wiki-</li>|
| Zusammenarbeiten an globaler Krise oder Veranstaltung |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent`| Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Welt Nachrichten</li><li>Business Continuity</li><li>Remote arbeiten</li><li>Interne Comms</li><li>Externe Comms</li><li>Kundenreklamationen</li><li>Kudos</li><li>Executive-Update</li></ul>Apps <ul><li>Lob</li><li>Wiki-</li><li>Website</li></ul>|
|Zusammenarbeiten in einer Bankfiliale| `com.microsoft.teams.template.CollaborateWithinABankBranch `|Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Kauert</li><li>Kundenbesprechungen</li><li>Coaching</li><li>Qualifikationsentwicklung</li><li>Kreditbearbeitung</li><li>Kundenreklamationen</li><li>Kudos</li><li>Lustige Sachen</li><li>Compliance</li></ul>|
|Koordinieren der Vorfall Antwort| `com.microsoft.teams.template.CoordinateIncidentResponse`|Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Logistik</li><li>Planung</li><li>Recovery</li><li>Dringend</li></ul> Apps <ul><li>Wiki-</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Krankenhaus| `healthcareHospita`l |Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Compliance</li><li>Freiheits</li><li>Personalwesen</li><li>Apotheke</li></ul> Apps <ul><li>Wiki-</li></ul>|
|Organisieren eines Shops| `retailStore` |Kanäle <ul><li>Allgemein<li>UMSCHALT Übergabe</li><li>Lerntools</li></ul> Apps <ul><li>Wiki-</li></ul>|
|Qualität und Sicherheit |`com.microsoft.teams.template.QualitySafety`|Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Zeile 1</li><li>Zeile 2</li><li>Zeile 3</li><li>Sicherheit</li><li>Schulungen</li><li>Wartung</li><li>Lustige Sachen</li></ul> Apps <ul><li>Wiki-</li></ul>|
|Zusammenarbeit im Einzelhandel – Manager| `retailManagerCollaboration` |Kanäle <ul><li>Allgemein<li>Vorgänge</li><li>Lerntools</li></ul> Apps <ul><li>Wiki-</li></ul>|
||||

Weitere Informationen zu den Vorlagenkategorien finden Sie in den folgenden Kategorien:

- [Finanz Vorlagen](financial-teams-templates-in-the-admin-console.md)
- [Allgemeine Vorlagen](general-teams-templates-in-the-admin-console.md)
- [Government-Vorlagen](government-teams-templates-in-the-admin-console.md)
- [Healthcare-Vorlagen](expand-teams-across-your-org/healthcare/healthcare-templates-admin-console.md)
- [Fertigungs Vorlagen](manufacturing-teams-templates-in-the-admin-console.md)
- [Einzelhandels Vorlagen](retail-teams-templates-in-the-admin-console.md)

## <a name="template-size-limits"></a>Größenbeschränkungen für Vorlagen

Vorlagen sind auf eine bestimmte Anzahl von Kanälen, Registerkarten und apps limitiert.

 > [!Note]
 > Sie können dem Team weitere Kanäle, Registerkarten und apps hinzufügen, nachdem es aus einer Vorlage erstellt wurde.

|Feature | Limit|
|-|-|
|Kanäle pro Vorlage | 15 |
|Tabstopps pro Kanal in einer Vorlage | 20 |
|Apps pro Vorlage | 50|
|||

Weitere Informationen finden Sie unter [Grenzwerte und Spezifikationen von Teams](limits-specifications-teams.md) .

## <a name="related-topics"></a>Verwandte Themen

- [Erstellen einer benutzerdefinierten Teamvorlage](create-a-team-template.md)
- [Erstellen einer Teamvorlage aus einer vorhandenen Teamvorlage](create-template-from-existing-template.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-template-from-existing-team.md)
