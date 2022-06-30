---
title: Verwalten großer Teams in Microsoft Teams – bewährte Methoden
ms.reviewer: abgupta
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Erfahren Sie mehr über bewährte Methoden zum Verwalten großer Teams in Microsoft Teams, um die Anforderungen Ihrer Organisation zu erfüllen.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 313c570cfcded3b5a896a773577863f7a8817fa8
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562404"
---
# <a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Verwalten großer Teams in Microsoft Teams – Bewährte Methoden

Microsoft Teams ist gleichermaßen effektiv, um die Kommunikation zwischen kleinen Gruppen mit Dutzenden von Mitgliedern und großen Gruppen mit Tausenden von Mitgliedern zu erleichtern. Überprüfen Sie [Grenzwerte und Spezifikationen für Teams](limits-specifications-teams.md) auf Updates zu Teamgrößen. Die Zunahme der Teamgröße führt zu einzigartigen Management- und operativen Herausforderungen. In diesem Artikel werden bewährte Methoden zum Erstellen und Verwalten großer Teams beschrieben, die aus Tausenden von Mitgliedern bestehen.

## <a name="value-of-large-teams"></a>Wert großer Teams

Große Teams sind sehr nützlich, um die folgenden Szenarien für die Zusammenarbeit zu ermöglichen:

- **Abteilungsweite Zusammenarbeit**: Wenn Ihre Organisation über mehrere Abteilungen wie Finanzen, Operationen, R&D usw. verfügt, können Sie ein einzelnes Team erstellen, das alle Mitglieder in einer bestimmten Abteilung umfasst. Jetzt können alle für eine Abteilung relevanten Kommunikationen in diesem Team geteilt werden, was die sofortige Reichweite und das Engagement der Mitglieder erleichtert.

- **Zusammenarbeit in Mitarbeiterressourcengruppen**: Organisationen haben häufig große Gruppen von Personen mit gegenseitigen Interessen, die zu einer anderen Abteilung oder Arbeitsgruppe gehören. Als Beispiel kann es eine Gruppe von Personen geben, die eine Leidenschaft für persönliche Finanzen und Investitionen teilen. Es ist oft schwierig, eine Verbindung in einer großen Organisation herzustellen. Um Communitys für solche Gruppen zu entwickeln, können Mandantenadministratoren ein großes Team erstellen, das als öffentliche unternehmensweite Ressourcengruppe dient, der jeder beitreten und diese nutzen kann. Schließlich sammeln diese Communitys Informationen, die sowohl neue als auch bestehende Mitglieder genießen können.

- **Zusammenarbeit zwischen internen und externen Mitgliedern**: Beliebte Produkte entwickeln häufig eine Community von Early Adoptern, die neue Produktversionen ausprobieren und Feedback geben möchten. Early Adopters entwickeln eine Beziehung zu Produktgruppen, um das Produkt mitzugestalten. In solchen Szenarien können Mandantenadministratoren ein großes Team einrichten, das sowohl interne Produktgruppen als auch externe Produktauswertungen umfasst, um einen umfassenden Produktentwicklungsprozess zu ermöglichen. Diese Teams können auch Kundensupport für eine ausgewählte Gruppe von Kunden bereitstellen.

## <a name="create-teams-from-existing-groups"></a>Erstellen von Teams aus vorhandenen Gruppen

Verwenden Sie Kontaktgruppen, Sicherheitsgruppen oder Office-Gruppen, um Ihr Team zu starten. Sie können eine Gruppe importieren, um ein Team zu erstellen oder ein Team aus einer Office-Gruppe zu erstellen.

**Importieren einer Gruppe zum Erstellen eines Teams**: Wenn Sie eine Gruppe mit bis zu 3.500 Mitgliedern in Teams importieren, berechnet Teams automatisch die Gesamtzahl der Mitglieder in der Gruppe. Dies ist nur ein einmaliger Import, und zukünftige Änderungen in der Gruppe werden nicht automatisch in Teams aktualisiert.

**Erstellen eines Teams aus einer großen Microsoft 365-Gruppe**: Wenn Sie ein Team aus einer großen Microsoft 365-Gruppe erstellen, werden Mitglieder automatisch Teil der Microsoft 365-Gruppe **und** des Teams. In Zukunft werden Teammitglieder, die der Microsoft 365-Gruppe beitreten oder diese verlassen, automatisch zum Team hinzugefügt oder daraus entfernt.

## <a name="bulk-importexportremove-members-in-a-team"></a>Massenimport,-export/-entfernen von Mitgliedern in einem Team

Die Azure-Portal ermöglicht Benutzern das Massenimport/-export/-entfernen von Mitgliedern in einer Microsoft 365-Gruppe. Weitere Informationen finden Sie unter ["Massenimport von Gruppenmitgliedern](/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)".

Da jedes Team von einer Microsoft 365-Gruppe unterstützt wird, können Sie die Azure-Portal verwenden, um diese Vorgänge in der Gruppe auszuführen, die dem Team entspricht. Die Mitgliedervorgänge werden innerhalb von 24 Stunden im Team angezeigt.

## <a name="create-channels-to-focus-discussions"></a>Erstellen Sie Kanäle für fokussierte Unterhaltungen

Sie können die Gruppendiskussionen einschränken, indem Sie fokussierte Kanäle erstellen. Siehe [bewährte Methoden zum Organisieren von Teams](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Einschränken der Kanalerstellung

Wenn ein Teammitglied Kanäle erstellen darf, kann dieses Team kanalzershallt sein. Teambesitzer sollten die Kanalerstellung, -aktualisierung, -löschung und -wiederherstellung für Mitglieder in **den Einstellungen > Mitgliedsberechtigungen** deaktivieren. Siehe [Übersicht über Teams und Kanäle](teams-channels-overview.md).

![Bildschirmbild mit dem Abschnitt "Mitgliederberechtigungen" auf der Registerkarte "Einstellungen" der Administratorkonsole.](media/no-channel-creation.png "Bildschirmbild des Abschnitts &quot;Mitgliedsberechtigungen&quot; auf der Registerkarte &quot;Einstellungen&quot; der Administratorkonsole. Die Optionen zum Erstellen oder Löschen von Kanälen durch Mitglieder sind deaktiviert.")

## <a name="add-favorite-channels"></a>Hinzufügen von Bevorzugten Kanälen

Um das Engagement neuer Benutzer und die Inhaltsermittlung zu beschleunigen, können Sie bevorzugte Kanäle auswählen, die dem Benutzer standardmäßig zur Verfügung stehen. Überprüfen Sie im Bereich **"Kanäle** " im Admin Center die Kanäle unter der Spalte **"Für Mitglieder anzeigen** ".

![Bildschirmbild, das den Kanalbereich der Administratorkonsole zeigt.](media/favorite-channels.png "Bildschirmbild, das den Kanalbereich der Administratorkonsole zeigt. Einige Kanäle sind auf &quot;Für Mitglieder anzeigen&quot; aktiviert.")

 Details finden [Sie unter "Erstellen Ihrer ersten Teams und Kanäle](get-started-with-teams-create-your-first-teams-and-channels.md) ".

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regeln von Anwendungen und Bots in großen Teams

Um das Hinzufügen störender Anwendungen oder Bots zu verhindern, können Teambesitzer Apps und Connectors für Teammitglieder deaktivieren, hinzufügen, entfernen und hochladen. Deaktivieren Sie im Admin Center unter **"Einstellungen > Mitgliederberechtigungen**" die drei Optionen, mit denen Mitglieder Apps oder Connectors hinzufügen können.

![Bildschirmbild, das den Abschnitt "Mitgliederberechtigungen" im Bereich "Einstellungen" zeigt.](media/disable-bots-connectors.png "Bildschirmbild, das den Abschnitt &quot;Mitgliederberechtigung&quot; im Einstellungsbereich zeigt. Die Optionen, mit denen Mitglieder Apps oder Connectors hinzufügen können, sind deaktiviert.")

Siehe [Apps, Bots, & Connectors](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regeln von Team- und Kanal-Erwähnungen

Team- und Kanal-Erwähnungen können verwendet werden, um die Aufmerksamkeit des gesamten Teams auf bestimmte Kanalbeiträge zu lenken. Sobald eine Erwähnung in einem Beitrag verwendet wird, wird eine Benachrichtigung an Tausende von Teammitgliedern gesendet. Wenn die Benachrichtigungen zu häufig sind, können Teammitglieder überlastet werden und sich möglicherweise bei Teambesitzern beschweren. Um Team- oder Kanal-Erwähnungen zu verhindern, deaktivieren Sie Team- und Kanal-Erwähnungen für Mitglieder, indem Sie die Kontrollkästchen im Bereich " **Teams-Einstellungen" > @mentions** deaktivieren.

![Bildschirmbild, das den Abschnitt "Erwähnungen" im Bereich "Einstellungen" zeigt.](media/no-at-mentions.png "Bildschirmbild, das den Abschnitt &quot;Erwähnungen&quot; im Bereich &quot;Einstellungen&quot; zeigt. Die Optionen zum Anzeigen und Gewähren des Zugriffs auf Mitglieder bei Erwähnungen sind deaktiviert.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Erwägen Sie, in Ihren Kanälen eine Moderation einzurichten.

Teambesitzer können die Moderation für einen Kanal aktivieren, um zu steuern, wer neue Beiträge starten und auf Beiträge in diesem Kanal antworten kann. Beim Einrichten der Moderation können Sie eines oder mehrere Teammitglieder als Moderatoren auswählen. Teambesitzer sind standardmäßig Moderatoren. Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanalmoderation](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden zum Organisieren von Teams](best-practices-organizing.md)
- [Erstellen eines organisationsweiten Teams](create-an-org-wide-team.md)