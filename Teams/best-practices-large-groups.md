---
title: Verwalten großer Teams in Microsoft Teams – Bewährte Methoden
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Erfahren Sie mehr über bewährte Methoden für die Verwaltung großer Microsoft Teams, um die Anforderungen Ihrer Organisation zu erfüllen.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d856a47fb4d7888dcaa990cde9a3dd151dac79ea
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58619671"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Verwalten großer Teams in Microsoft Teams – Bewährte Methoden

Microsoft Teams ist gleichermaßen effektiv, um die Kommunikation zwischen kleinen Gruppen mit Dutzenden von Mitgliedern und großen Gruppen mit Tausenden von Mitgliedern zu erleichtern. Überprüfen [Sie Grenzwerte und Spezifikationen für Teams](limits-specifications-teams.md) für Updates für Teamgrößen. Eine Zunahme der Teamgröße führt zu einzigartigen Management- und operationalen Herausforderungen. In diesem Artikel werden bewährte Methoden zum Erstellen und Verwalten großer Teams beschrieben, die aus Tausenden von Mitgliedern bestehen.

## <a name="value-of-large-teams"></a>Wert großer Teams

Große Teams sind sehr hilfreich bei der Aktivierung der folgenden Szenarien für die Zusammenarbeit:

- **Abteilungsweite** Zusammenarbeit: Wenn Ihre Organisation über mehrere Abteilungen wie Finanzen, Vorgänge, R&D usw. verfügt, können Sie ein einzelnes Team erstellen, das alle Mitglieder einer bestimmten Abteilung umfasst. Jetzt können alle für eine Abteilung relevanten Kommunikationen in diesem Team geteilt werden, was die sofortige Reichweite und das Engagement der Mitglieder erleichtert.

- **Zusammenarbeit in Mitarbeiterressourcengruppen:** Organisationen haben häufig große Gruppen von Personen mit gemeinsamen Interessen, die einer anderen Abteilung oder Arbeitsgruppe angehören. Beispielsweise kann es eine Gruppe von Personen geben, die sich für die private Finanzen und DasInning m meisten leidenschaftlich sind. Es ist häufig schwierig, in einer großen Organisation eine Verbindung herzustellen. Zum Entwickeln von Communitys für solche Gruppen können Mandantenadministratoren ein großes Team erstellen, das als öffentliche unternehmensweite Ressourcengruppe dient, der jeder beitreten und von diesen nutzen kann. Schließlich sammeln diese Communitys Informationen, die sowohl neue als auch vorhandene Mitglieder nutzen können.

- **Zusammenarbeit zwischen internen und externen** Mitgliedern: Beliebte Produkte entwickeln häufig eine Community von Early Adoptern, die neue Produktversionen ausprobieren und Feedback geben wollen. Early Adopters entwickeln eine Beziehung zu Produktgruppen, um das Produkt zu gestalten. In solchen Szenarien können Mandantenadministratoren ein großes Team einrichten, das sowohl interne Produktgruppen als auch externe Produkt-Evaluierer umfasst, um einen reichhaltigen Produktentwicklungsprozess zu vereinfachen. Diese Teams können auch einen Kundensupport für eine bestimmte Gruppe von Kunden bereitstellen.

## <a name="create-teams-from-existing-groups"></a>Erstellen von Teams aus vorhandenen Gruppen

Verwenden Sie Kontaktgruppen, Sicherheitsgruppen oder Gruppen Office, um ein Team zu starten. Sie können eine Gruppe importieren, um ein Team zu erstellen, oder ein Team aus einer Gruppe Office erstellen.

Importieren einer Gruppe, um ein Team zu **erstellen:** Wenn Sie eine Gruppe mit bis zu 3.500 Mitgliedern in Teams importieren, berechnet Teams automatisch die Gesamtzahl der Mitglieder in der Gruppe. Dies ist nur ein einmal verwendeter Import, und zukünftige Änderungen in der Gruppe werden in diesem Zeitraum Teams.

**Erstellen eines Teams** aus einer großen Microsoft 365-Gruppe: Wenn Sie ein Team aus einer großen Microsoft 365-Gruppe erstellen, gehören die Mitglieder automatisch der Microsoft 365-Gruppe und dem **Team** an. Wenn zukünftig Teammitglieder der Gruppe der Microsoft 365 beitreten oder sie verlassen, werden sie dem Team automatisch hinzugefügt oder aus dem Team entfernt.

## <a name="bulk-importexportremove-members-in-a-team"></a>Massenimport/-export/-entfernen von Mitgliedern in einem Team

Das Azure-Portal ermöglicht benutzern das Massenimport/-export/-entfernen von Mitgliedern in einer Microsoft 365 Gruppe. Weitere Informationen finden Sie unter [Massenimport von Gruppenmitgliedern.](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)

Da jedes Team von einer Microsoft 365-Gruppe unterstützt wird, können Sie diese Vorgänge über das Azure-Portal in der Gruppe ausführen, die dem Team entspricht. Die Vorgänge der Mitglieder werden innerhalb von 24 Stunden im Team widerspiegelt.

## <a name="create-channels-to-focus-discussions"></a>Erstellen Sie Kanäle für fokussierte Unterhaltungen

Sie können die Gruppendiskussionen einkreisen, indem Sie fokussierte Kanäle erstellen. Lesen [Sie bewährte Methoden zum Organisieren von Teams.](best-practices-organizing.md)

## <a name="restrict-channel-creation"></a>Einschränken der Kanalerstellung

Wenn es einem Teammitglied gestattet ist, Kanäle zu erstellen, kann dieses Team Kanalsenkung erstellen. Teambesitzer sollten das Erstellen, Aktualisieren, Löschen und Wiederherstellen von Kanälen für Mitglieder in den Einstellungen > **deaktivieren.** Weitere Informationen [finden Sie unter Übersicht über Teams und Kanäle.](teams-channels-overview.md)

![Screen image that shows the member permissions section of the admin console Einstellungen tab.](media/no-channel-creation.png "Screen image that member permissions section of the admin console Einstellungen tab. Die Optionen zum Erstellen oder Löschen von Kanälen durch Mitglieder sind deaktiviert.")

## <a name="add-favorite-channels"></a>Hinzufügen bevorzugter Kanäle

Um das neue Engagement von Benutzern und die Inhaltsermittlung zu beschleunigen, können Sie bevorzugte Kanäle auswählen, die standardmäßig für den Benutzer verfügbar sind. Überprüfen Sie **im** Bereich Kanäle des Admin Centers die Kanäle unter der **Spalte Für Mitglieder anzeigen.**

![Bildschirmabbild, das den Kanalbereich der Verwaltungskonsole zeigt.](media/favorite-channels.png "Bildschirmabbild, das den Kanalbereich der Verwaltungskonsole zeigt. Einige Kanäle sind auf Für Mitglieder anzeigen aktiviert.")

 Details [finden Sie unter Erstellen Ihrer ersten](get-started-with-teams-create-your-first-teams-and-channels.md) Teams und Kanäle.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regulieren von Anwendungen und Bots in großen Teams

Um das Hinzufügen ablenkenden Anwendungen oder Bots zu verhindern, können Teambesitzer Apps und Connectors für Teammitglieder deaktivieren, hinzufügen, entfernen und hochladen. Deaktivieren Sie im Admin Center **unter Einstellungen > Mitgliedsberechtigungen** die drei Optionen, mit denen Mitglieder Apps oder Connectors hinzufügen können.

![Bildschirmabbild, das den Abschnitt "Mitgliederberechtigungen" im Einstellungen zeigt.](media/disable-bots-connectors.png "Bildschirmabbild, das den Berechtigungsbereich &quot;Mitglied&quot; im Einstellungen zeigt. Die Optionen für zulassen, dass Mitglieder Apps oder Connectors hinzufügen können, sind deaktiviert.")

Siehe [Apps, Bots, & Connectors.](deploy-apps-microsoft-teams-landing-page.md)

## <a name="regulate-team-and-channel-mentions"></a>Regulieren von Team- und Kanal-Erwähnungen

Team- und Kanal-Erwähnungen können verwendet werden, um die Aufmerksamkeit des gesamten Teams auf bestimmte Kanalbeiträge zu ziehen. Sobald eine Erwähnung in einem Beitrag verwendet wird, wird eine Benachrichtigung an Tausende von Teammitgliedern gesendet. Wenn die Benachrichtigungen zu häufig sind, können Teammitglieder überlastet werden und sich an Teambesitzer beschweren. Um Team- oder Kanalergnungen zu verhindern, deaktivieren Sie Team- und Kanalergnungen für Mitglieder, indem Sie die Kontrollkästchen im **Team- Einstellungen > @mentions** deaktivieren.

![Bildschirmabbild, das den Abschnitt "At Erwähnungen" im Einstellungen zeigt.](media/no-at-mentions.png "Bildschirmabbild, das den Abschnitt &quot;At Erwähnungen&quot; im Einstellungen zeigt. Die Optionen zum Anzeigen und Zugreifen auf At-Erwähnungen sind deaktiviert.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Erwägen Sie, in Ihren Kanälen eine Moderation einzurichten.

Teambesitzer können die Moderation für einen Kanal aktivieren, um zu steuern, wer neue Beiträge starten und auf Beiträge in diesem Kanal antworten kann. Beim Einrichten der Moderation können Sie eines oder mehrere Teammitglieder als Moderatoren auswählen. Teambesitzer sind standardmäßig Moderatoren. Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanalmoderation.](manage-channel-moderation-in-teams.md)

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden für das Organisieren Teams](best-practices-organizing.md)
- [Erstellen eines organisationsweiten Teams](create-an-org-wide-team.md)