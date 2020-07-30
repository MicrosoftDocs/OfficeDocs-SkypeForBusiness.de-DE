---
title: Verwenden von Microsoft Teams-Vorlagen in der Administratorkonsole
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 26f26e869758c06762167731068033acb1707135
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506448"
---
# <a name="get-started-with-teams-templates-in-the-teams-admin-console"></a>Erste Schritte mit Microsoft Teams-Vorlagen in der Team-Verwaltungskonsole

[!INCLUDE [template](includes/preview-feature.md)]

> [!NOTE]
> In den Teams-Vorlagen wird derzeit keine private Kanalerstellung unterstützt. Die Erstellung privater Kanäle ist in den Vorlagendefinitionen nicht enthalten.

In den Teams-Vorlagen handelt es sich um vorgefertigte Definitionen einer Teamstruktur, die sich um ein geschäftliches Bedürfnis oder Projekt entwickelt hat. Verwenden Sie vordefinierte Vorlagen, oder erstellen Sie eine eigene Vorlage. Mithilfe von "Teams-Vorlagen" können Sie schnell umfangreiche Zusammenarbeit mit Kanälen für verschiedene Themen erstellen und apps vorinstallieren, um unternehmenskritische Inhalte und Dienste abzurufen. Teams-Vorlagen bieten eine vordefinierte Teamstruktur, die Ihnen bei der einfachen Erstellung konsistenter Teams in Ihrer Organisation helfen kann. Derzeit können Sie eine Vorlage in der Admin-Konsole oder mit [Microsoft Graph](get-started-with-teams-templates.md)verwenden.

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

Basisvorlagen Typen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt hat. Diese Basisvorlagen enthalten häufig proprietäre apps, die im App Store zur Verfügung stehen.

Nachdem ein Basis Vorlagentyp definiert wurde, können Sie diese speziellen Vorlagen mit zusätzlichen Eigenschaften erweitern oder außer Kraft setzen, die Sie angeben möchten. Einige Basisvorlagen Typen enthalten jedoch Eigenschaften, die nicht überschrieben werden können.

> [!NOTE]
> Vordefinierte Basisvorlagen, die in Microsoft Teams bereitgestellt werden, können dupliziert, aber nicht bearbeitet werden.


| Basis Vorlagentyp | Eigenschaften, die mit dieser Basisvorlage geliefert werden |
| ------------------ |----------------------------------------------------- |
| Übernehmen von Office 365 |  Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Champions Corner</li> <li>Team Formulare</li></ul> Apps <ul><li>Wiki-</li>  <li>Kalender</li> |
| Verwalten eines Projekts | Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Ressourcen</li> <li>Planung</li></ul> Apps<ul><li>Wiki-</li><li>OneNote</li></ul> |
| Verwalten eines Ereignisses | Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Budget</li> <li>Inhalt</li><li>Logistik</li> <li>Planung</li> <li> Marketing und PR</li></ul> Apps<ul><li>Wiki-</li><li>Website</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
|Onboard-Mitarbeiter | Kanäle <ul><li>Allgemein</li> <li>Ankündigungen</li> <li>Mitarbeiter-Chat</li> <li>Schulungen</li></ul>Apps<ul><li>Wiki-</li><li>Gemeinschaften</li>|</ul>
|Organisieren des Helpdesks| Kanäle<ul><li>Allgemein</li><li>Ankündigungen</li><li>Häufig gestellte Fragen</li></ul>Apps<ul><li>Wiki-</li><li>OneNote</li></ul> |
| Zusammenarbeit bei der Patientenversorgung | Kanäle<ul><li>Allgemein</li><li>Ankündigungen</li><li>Kauert</li><li>Runden</li><li>Personal</li><li>Schulungen</li></ul> Apps <ul><li>Wiki-</li>|
| Zusammenarbeiten an globaler Krise oder Veranstaltung |Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Welt Nachrichten</li><li>Business Continuity</li><li>Remote arbeiten</li><li>Interne Comms</li><li>Externe Comms</li><li>Kundenreklamationen</li><li>Kudos</li><li>Executive-Update</li></ul>Apps <ul><li>Lob</li><li>Wiki-</li><li>Website</li></ul>|
|Zusammenarbeiten in einer Bankfiliale |Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Kauert</li><li>Kundenbesprechungen</li><li>Coaching</li><li>Qualifikationsentwicklung</li><li>Kreditbearbeitung</li><li>Kundenreklamationen</li><li>Kudos</li><li>Lustige Sachen</li><li>Compliance</li></ul>|
|Koordinieren der Vorfall Antwort |Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Logistik</li><li>Planung</li><li>Recovery</li><li>Dringend</li></ul> Apps <ul><li>Wiki-</li><li>Excel</li><li>OneNote</li><li>SharePoint</li><li>Planner</li></ul>|
|Krankenhaus |Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Compliance</li><li>Freiheitsentzug/Li><li>Personalwesen</li><li>Apotheke</li></ul> Apps <ul><li>Wiki-</li></ul>|
|Organisieren eines Shops |Kanäle <ul><li>Allgemein<li>UMSCHALT Übergabe</li><li>Lerntools</li></ul> Apps <ul><li>Wiki-</li></ul>|
|Qualität und Sicherheit |Kanäle <ul><li>Allgemein<li>Ankündigungen</li><li>Zeile 1</li><li>Zeile 2</li><li>Zeile 3</li><li>Sicherheit</li><li>Schulungen</li><li>Wartung</li><li>Lustige Sachen</li></ul> Apps <ul><li>Wiki-</li></ul>|
|Zusammenarbeit im Einzelhandel – Manager |Kanäle <ul><li>Allgemein<li>Vorgänge</li><li>Lerntools</li></ul> Apps <ul><li>Wiki-</li></ul>|
|||

## <a name="related-topics"></a>Verwandte Themen

- [Erstellen einer Teamvorlage](create-a-team-template.md)
- [Erstellen eines Teams aus einer vorhandenen Teamvorlage](modify-existing-team-template.md)
- [Erstellen einer Vorlage aus einem vorhandenen Team](create-team-from-existing-team.md)
