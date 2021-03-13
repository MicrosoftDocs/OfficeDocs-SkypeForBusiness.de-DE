---
title: Verwalten großer Teams in Microsoft Teams – bewährte Methoden
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Erfahren Sie mehr über bewährte Methoden zum Verwalten großer Teams in Microsoft Teams, um die Anforderungen Ihrer Organisation zu erfüllen.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52b1e50cfd29aa6916f7b816f3639953d27d6526
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756241"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Verwalten großer Teams in Microsoft Teams – Bewährte Methoden
======================================================

Microsoft Teams erleichtert ebenso die Kommunikation zwischen kleinen Gruppen mit Dutzenden von Mitgliedern und großen Gruppen mit Tausenden von Mitgliedern. Überprüfen [Sie Grenzwerte und Spezifikationen für Teams,](limits-specifications-teams.md) um Updates für Teamgrößen zu erhalten. Die Zunahme der Teamgröße führt zu eindeutigen Management- und betrieblichen Herausforderungen. In diesem Artikel werden bewährte Methoden zum Erstellen und Verwalten großer Teams beschrieben, die aus Tausenden von Mitgliedern bestehen.

## <a name="value-of-large-teams"></a>Wert großer Teams

Große Teams sind bei der Aktivierung der folgenden Szenarien für die Zusammenarbeit sehr hilfreich:

- **Abteilungsweite** Zusammenarbeit: Wenn Ihre Organisation über mehrere Abteilungen wie Finanzen, Vorgänge, R&D usw. verfügt, können Sie ein einzelnes Team erstellen, das alle Mitglieder einer bestimmten Abteilung umfasst. Jetzt können alle für eine Abteilung relevanten Kommunikationen in diesem Team geteilt werden, was die sofortige Reichweite und das Engagement der Mitglieder erleichtert.

- **Zusammenarbeit in Mitarbeiterressourcengruppen:** Organisationen haben häufig große Gruppen von Personen mit gemeinsamen Interessen, die einer anderen Abteilung oder Arbeitsgruppe angehören. Als Beispiel kann es eine Gruppe von Personen geben, die eine Leidenschaft für private Finanzen und Investitionen teilen. Es ist häufig schwierig, eine Verbindung in einer großen Organisation herzustellen. Um Communitys für solche Gruppen zu entwickeln, können Mandantenadministratoren ein großes Team erstellen, das als öffentliche unternehmensweite Ressourcengruppe dient, der jeder beitreten und nutzen kann. Schließlich sammeln diese Communitys Informationen, die neue und vorhandene Mitglieder nutzen können.

- **Zusammenarbeit zwischen internen und externen** Mitgliedern: Beliebte Produkte entwickeln häufig eine Community von frühen Adoptern, die neue Produktversionen ausprobieren und Feedback geben. Frühe Adoptierer entwickeln eine Beziehung zu Produktgruppen, um das Produkt zu gestalten. In solchen Szenarien können Mandantenadministratoren ein großes Team einrichten, das sowohl interne Produktgruppen als auch externe Produktevaluatoren umfasst, um einen reichhaltigen Produktentwicklungsprozess zu ermöglichen. Diese Teams können auch Kundensupport für eine ausgewählte Gruppe von Kunden bereitstellen.

## <a name="create-teams-from-existing-groups"></a>Erstellen von Teams aus vorhandenen Gruppen

Verwenden Sie Kontaktgruppen, Sicherheitsgruppen oder Office-Gruppen, um ihr Team zu starten. Sie können eine Gruppe importieren, um ein Team zu erstellen oder ein Team aus einer Office-Gruppe zu erstellen.

**Importieren einer** Gruppe zum Erstellen eines Teams: Wenn Sie eine Gruppe mit bis zu 3.500 Mitgliedern in Teams importieren, berechnet Teams automatisch die Gesamtzahl der Mitglieder in der Gruppe. Dies ist nur ein einmaler Import, und zukünftige Änderungen in der Gruppe werden in Teams nicht automatisch aktualisiert.

Erstellen eines Teams aus einer großen **Microsoft 365-Gruppe:** Wenn Sie ein Team aus einer großen Microsoft 365-Gruppe erstellen, sind Mitglieder automatisch Teil der Microsoft 365-Gruppe und des **Teams.** Wenn Teammitglieder der Microsoft 365-Gruppe beitreten oder diese verlassen, werden sie in Zukunft automatisch dem Team hinzugefügt oder entfernt.

## <a name="bulk-importexportremove-members-in-a-team"></a>Massenimport/Export/Entfernen von Mitgliedern in einem Team

Das Azure-Portal ermöglicht Benutzern das Massenimport/Exportieren/Entfernen von Mitgliedern in einer Microsoft 365-Gruppe. Weitere Informationen finden Sie unter [So importieren Sie Gruppenmitglieder im Massenimport.](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)

Da jedes Team von einer Microsoft 365-Gruppe unterstützt wird, können Sie diese Vorgänge über das Azure-Portal in der Gruppe ausführen, die dem Team entspricht. Die Mitgliedsvorgänge werden innerhalb von 24 Stunden im Team widerspiegelt.

## <a name="create-channels-to-focus-discussions"></a>Erstellen Sie Kanäle für fokussierte Unterhaltungen

Sie können die Gruppendiskussionen eindinnen, indem Sie kanäle mit Schwerpunkt erstellen. Weitere Informationen finden Sie unter Bewährte [Methoden zum Organisieren von Teams.](best-practices-organizing.md)

## <a name="restrict-channel-creation"></a>Einschränken der Kanalerstellung

Wenn ein Teammitglied Kanäle erstellen darf, kann dieses Team kanalspraklig sein. Teambesitzer sollten das Erstellen, Aktualisieren, Löschen und Wiederherstellen von Kanälen für Mitglieder unter Einstellungen **> Memberberechtigungen deaktivieren.** Weitere [Informationen finden Sie unter Übersicht über Teams und Kanäle.](teams-channels-overview.md)

![Bildschirmbild mit dem Abschnitt "Mitgliederberechtigungen" auf der Registerkarte "Einstellungen" der Administratorkonsole.](media/no-channel-creation.png "Screenshot des Abschnitts "Mitgliederberechtigungen" auf der Registerkarte "Einstellungen" der Administratorkonsole. Die Optionen zum Erstellen oder Löschen von Kanälen durch Mitglieder sind deaktiviert.")

## <a name="add-favorite-channels"></a>Hinzufügen von bevorzugten Kanälen

Um neue Benutzerbindung und Inhaltsermittlung zu beschleunigen, können Sie bevorzugte Kanäle auswählen, die dem Benutzer standardmäßig zur Verfügung stehen. Überprüfen Sie **im Bereich** Kanäle des Admin Centers die Kanäle unter der Spalte Für **Mitglieder anzeigen.**

![Bildschirmbild, das den Kanalbereich der Administratorkonsole zeigt.](media/favorite-channels.png "Bildschirmbild, das den Kanalbereich der Administratorkonsole zeigt. Einige Kanäle sind auf Anzeigen für Mitglieder überprüft.")

 Details finden Sie unter Erstellen [Ihrer ersten Teams und](get-started-with-teams-create-your-first-teams-and-channels.md) Kanäle.

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regeln von Anwendungen und Bots in großen Teams

Um das Hinzufügen von abgelenkten Anwendungen oder Bots zu verhindern, können Teambesitzer Apps und Connectors für Teammitglieder deaktivieren, hinzufügen, entfernen und hochladen. Deaktivieren Sie im Admin Center unter Einstellungen **> Mitgliederberechtigungen** die drei Optionen, mit denen Mitglieder Apps oder Connectors hinzufügen können.

![Bildschirmbild, das den Abschnitt "Mitgliederberechtigungen" im Bereich "Einstellungen" zeigt.](media/disable-bots-connectors.png "Bildschirmbild mit dem Abschnitt "Mitgliedberechtigung" im Bereich "Einstellungen". Die Optionen für das Hinzufügen von Apps oder Connectors durch Mitglieder sind deaktiviert.")

Siehe [Apps, Bots, & Connectors](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regeln von Team- und Kanal erwähnungen

Team- und Kanal erwähnungen können verwendet werden, um die Aufmerksamkeit des gesamten Teams auf bestimmte Kanalbeiträge zu ziehen. Sobald eine Erwähnung in einem Beitrag verwendet wird, wird eine Benachrichtigung an Tausende von Teammitgliedern gesendet. Wenn die Benachrichtigungen zu häufig sind, können Teammitglieder überlastet werden und sich möglicherweise bei Teambesitzern beschweren. Um Team- oder Kanal erwähnungen zu verhindern, deaktivieren Sie Team- und Kanal erwähnungen für **Mitglieder,** indem Sie die Kontrollkästchen im Bereich "Teameinstellungen" > @mentions deaktivieren.

![Bildschirmbild, das den Abschnitt "Erwähnungen" im Bereich "Einstellungen" zeigt.](media/no-at-mentions.png "Bildschirmbild, das den Abschnitt "Erwähnungen" im Bereich "Einstellungen" zeigt. Die Optionen zum Anzeigen und Geben von Mitgliedern, auf die Sie bei Erwähnungen zugreifen können, sind deaktiviert.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Erwägen Sie, in Ihren Kanälen eine Moderation einzurichten.

Teambesitzer können die Moderation für einen Kanal aktivieren, um zu steuern, wer neue Beiträge starten und auf Beiträge in diesem Kanal antworten kann. Beim Einrichten der Moderation können Sie eines oder mehrere Teammitglieder als Moderatoren auswählen. Teambesitzer sind standardmäßig Moderatoren. Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanalmoderation.](manage-channel-moderation-in-teams.md)

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden zum Organisieren von Teams](best-practices-organizing.md)
- [Erstellen eines organisationsweiten Teams](create-an-org-wide-team.md)
