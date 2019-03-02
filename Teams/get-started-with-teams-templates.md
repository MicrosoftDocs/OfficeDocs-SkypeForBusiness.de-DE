---
title: Erste Schritte mit Microsoft Teams-Vorlagen
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phlouie
localization_priority: Normal
search.appverid: MET150
description: Erfahren Sie, wie Teams Vorlagen verwenden, um ein Team mit vordefinierten Kanälen zu erstellen.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97504dcc6fa1cd465eae7bf0ea151cdf36f525d2
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "30352642"
---
# <a name="get-started-with-teams-templates"></a>Erste Schritte mit Microsoft Teams-Vorlagen 

Teams Vorlagen werden vor dem Definitionen von ein Team Struktur entwickelt, um eine geschäftlicher Bedarf oder ein Projekt erstellt. Vorlagen für Teams können schnell und erstellen umfassender Zusammenarbeit Leerzeichen mit Kanäle für verschiedene Themen und Vorinstallieren von apps in unternehmenswichtige Inhalte und Dienste abrufen. Teams Vorlagen bieten eine vordefinierte Teamstruktur, die Sie auf einfache Weise konsistent Teams innerhalb Ihrer Organisation helfen. 

In diesem Artikel wird die Eigenschaften, die in Vorlagen, welche Basisvorlage definiert werden können, sind, erläutert, und wie Sie verwenden können, Beispiel wenige Anforderungen an ein Team aus einer Vorlage zu erstellen.
 
Dieser Artikel ist für Sie, wenn Sie sind:

- Verantwortlich für die Planung, Bereitstellung und Verwaltung mehrerer Teams innerhalb Ihrer Organisation<br>
- Ein Entwickler aus, um ein Team programmgesteuert mit vordefinierten Kanäle und apps erstellen werden soll 

## <a name="teams-template-capabilities"></a>Teams Vorlage Funktionen

Die meisten Eigenschaften in einem Team sind enthalten und von Vorlagen unterstützt. Es gibt jedoch einige Eigenschaften und Features, die derzeit nicht unterstützt werden. Die folgende Tabelle enthält eine kurze Zusammenfassung der Umfang von hat und was nicht in Teams Vorlagen enthalten ist.

| **Eigenschaften von Team von Teams Vorlagen unterstützt** | **Eigenschaften von Team von Teams Vorlagen noch nicht unterstützt.** |
| ------------------------------------------------ | -------------------------------------------------------- |
| Basisvorlage-Typ | Teammitgliedschaft |
| Teamname | Team-Bild |
| Team Beschreibung | Kanal-Einstellungen |
| Team Sichtbarkeit (öffentlich oder privat) | Connectors |
| Team-Einstellungen (beispielsweise Member, Gast @ erwähnungen) | Dateien und Inhalte |
| Automatische Favoriten DDE-Kanal | |
| Installierte app | |
| Angeheftete Registerkarten | | 

> [!NOTE]
> Wir werden werden weitere Funktionen in zukünftigen Versionen des Microsoft-Teams, hinzufügen, für die die aktuellsten Informationen zu unterstützten Eigenschaften überprüfen.

## <a name="what-are-base-template-types"></a>Was sind Basisvorlage Typen?

Basisvorlage Typen sind spezielle Vorlagen, die Microsoft für bestimmte Branchen erstellt. Diese Basis Vorlagen enthalten häufig proprietäre apps, die nicht in den Speicher und die Team-Eigenschaften zur Verfügung stehen, die noch nicht einzeln in Teams Formularvorlagen unterstützt werden.

Nachdem ein Basisvorlage Typ definiert ist, können Sie erweitern oder außer Kraft setzen diese speziellen Vorlagen mit zusätzlichen Eigenschaften, die Sie angeben möchten. Jedoch einige Basisvorlage Typen enthalten Eigenschaften, die nicht überschrieben werden können. 

Standardmäßig ist die Basisvorlage auf **Standard** festgelegt, die keine zusätzlichen proprietäre apps oder spezielle Eigenschaften enthält. Unten ist die aktuelle Liste der Typen Basisvorlage verfügbar.

| Basisvorlage-Typ | baseTemplateId | Eigenschaften, die im Lieferumfang von diese Basisvorlage |
| ------------------ | -------------- | ----------------------------------------------------- |
| Standard | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | Keine zusätzliche apps und Eigenschaften |
| Education-<br>Klasse-Team | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | Apps:<ul><li>OneNote-Klasse-Notizbuch (angeheftet auf der Registerkarte **Allgemein** ) </li><li>Assignments-app (angeheftet auf der Registerkarte **Allgemein** )</li></ul> Team-Eigenschaften:<ul><li>Legen Sie die Sichtbarkeit Team auf **HiddenMembership** (können nicht überschrieben werden)</li></ul> |
| Education-<br>Mitarbeiter-Team | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | Apps:<ul><li>OneNote-Personal-Notizbuch (angeheftet auf der Registerkarte **Allgemein** )</li></ul> |
|Education-<br>PLC-team |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | Apps:<ul><li>OneNote PLC-Notizbuch (angeheftet auf der Registerkarte **Allgemein** )</ul></li>|
| Retail-<br>abspeichern | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailStore` | Kanäle:<ul><li>UMSCHALT Übergabe</li><li>Learning</li></ul>Team-Eigenschaften<ul><li>Team Sichtbarkeit auf Public festgelegt</li></ul>Member-Berechtigungen<ul><li>Verhindern, dass Mitglieder erstellen, aktualisieren oder Entfernen von Kanäle</li><li>Verhindern, dass Mitglieder hinzufügen oder Entfernen von apps</li><li>Verhindern, dass Mitglieder erstellen, aktualisieren oder Entfernen von connectors</li></ul> |
| Retail-<br>Manager für die Zusammenarbeit | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`retailManagerCollaboration` | Kanäle:<ul><li>UMSCHALT Übergabe</li><li>Learning</li></ul>Team-Eigenschaften:<ul><li>Team Visibility auf Private festgelegt</li></ul>Member-Berechtigungen:<ul><li>Verhindern, dass Mitglieder erstellen, aktualisieren oder Entfernen von Kanäle</li><li>Verhindern, dass Mitglieder hinzufügen oder Entfernen von apps</li><li>Verhindern, dass Mitglieder erstellen, aktualisieren oder Entfernen von connectors</li></ul>|
| Gesundheitswesen-<br>Bezirk |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`healthcareWard` |Kanäle: <ul><li>Ansagen\*</li><li>Huddles\*</li><li>Rundet</li><li>Koordiniertes\*</li><li>Schulung\*</li></ul>\*Automatische favorisierte Kanäle |
|Gesundheitswesen-<br>Krankenhaus | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`healthcareHospital` |Kanäle:<ul><li>Ansagen\*</li><li>Beachtung\*</li><li>Freiheitsentziehenden</li><li>Personalwesen</li></li><li>Apotheke</li></ul>\*Automatische favorisierte DDE-Kanal|
|||

> [!NOTE]
> Wir können Sie Hinzufügen weiterer Basisvorlage Typen in zukünftigen Versionen von Microsoft-Teams, damit die Kontrollkästchen für die aktuellsten Informationen zu Eigenschaften unterstützt.


## <a name="related-topics"></a>Verwandte Themen

- [Create-team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in der Vorschau)
- [Neues Team](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [Administratorschulung für Microsoft Teams](itadmin-readiness.md)
- [Erste Schritte mit Vorlagen für Teams im Einzelhandel](get-started-with-retail-teams-templates.md)
- [Erste Schritte mit Gesundheitswesen Teams Vorlagen](healthcare/healthcare-templates.md)
