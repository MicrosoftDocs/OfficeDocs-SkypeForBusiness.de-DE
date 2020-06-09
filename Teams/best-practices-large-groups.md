---
title: Verwalten von umfangreichen Teams in Microsoft Teams – bewährte Methoden
ms.reviewer: abgupta
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: Informieren Sie sich über bewährte Methoden zum Verwalten großer Teams in Microsoft Teams, um die Anforderungen Ihrer Organisation zu erfüllen.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d939b4be4fcd5f3a1045f2f9adde750197b92f29
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638905"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a>Verwalten von umfangreichen Teams in Microsoft Teams – bewährte Methoden
======================================================

Microsoft Teams bietet gleichermaßen effektive Unterstützung für die Kommunikation zwischen kleinen Gruppen mit Dutzenden Mitgliedern und größeren Gruppen mit Tausenden von Mitgliedern. Überprüfen Sie die [Grenzwerte und Spezifikationen für Teams](limits-specifications-teams.md) auf Updates für Teamgrößen. Die Erhöhung der Teamgröße führt zu eindeutigen Management-und operativen Herausforderungen. In diesem Artikel werden bewährte Methoden zum Erstellen und Verwalten von umfangreichen Teams, die aus Tausenden Mitgliedern bestehen, beschrieben.

## <a name="value-of-large-teams"></a>Wert großer Teams

Große Teams sind sehr hilfreich bei der Aktivierung der folgenden Zusammenarbeitsszenarien:

- **Abteilungsübergreifende Zusammenarbeit**: Wenn Ihre Organisation über mehrere Abteilungen wie Finanzen, Vorgänge, R&D usw. verfügt, können Sie ein einzelnes Team erstellen, das alle Mitglieder in einer bestimmten Abteilung umfasst. Jetzt können alle für eine Abteilung relevanten Kommunikationen in diesem Team freigegeben werden, was die sofortige Erreichbarkeit und das Engagement von Mitgliedern ermöglicht.

- **Zusammenarbeit in Mitarbeiterressourcengruppen**: Organisationen verfügen häufig über große Gruppen von Personen mit gemeinsamem Interesse, die einer anderen Abteilung oder Arbeitsgruppe angehören. Als Beispiel kann es eine Gruppe von Personen geben, die eine Leidenschaft für persönliche Finanzen und Investitionen teilen. In einer größeren Organisation ist es oft schwierig, eine Verbindung herzustellen. Um Communities für solche Gruppen zu entwickeln, können mandantenadministratoren ein großes Team erstellen, das als öffentliche unternehmensweite Ressourcengruppe fungiert, die jeder teilnehmen und nutzen kann. Schließlich sammeln diese Communities Informationen, die von neuen und vorhandenen Mitgliedern genossen werden können.

- **Zusammenarbeit zwischen internen und externen Mitgliedern**: Beliebte Produkte entwickeln oft eine Community von Early Adopters, die eifrig daran interessiert sind, neue Produktversionen zu testen und Feedback zu geben. Frühe Anwender entwickeln eine Beziehung zu Produktgruppen, um die Gestaltung des Produkts zu unterstützen. In solchen Szenarien können mandantenadministratoren ein großes Team einrichten, das sowohl interne Produktgruppen als auch externe Produkt Auswerter umfasst, um einen umfassenden Produktentwicklungsprozess zu ermöglichen. Diese Teams können auch Kundensupport für eine ausgewählte Gruppe von Kunden bereitstellen.

## <a name="create-teams-from-existing-groups"></a>Erstellen von Teams aus vorhandenen Gruppen

Verwenden Sie Kontaktgruppen, Sicherheitsgruppen oder Office-Gruppen, um direkt in Ihr Team zu starten. Sie können eine Gruppe importieren, um ein Team zu bilden oder ein Team aus einer Office-Gruppe zu erstellen.

**Importieren einer Gruppe zum Erstellen eines Teams**: Wenn Sie eine Gruppe mit bis zu 3.500-Mitgliedern in Teams importieren, berechnet Teams automatisch die Gesamtanzahl der Mitglieder in der Gruppe. Hierbei handelt es sich um einen einmaligen Import, und zukünftige Änderungen in der Gruppe werden in den Teams nicht automatisch aktualisiert.

**Erstellen eines Teams aus einer umfangreichen Microsoft 365-Gruppe**: Wenn Sie ein Team aus einer umfangreichen Microsoft 365-Gruppe erstellen, sind Mitglieder automatisch Teil der Microsoft 365 **-Gruppe und** des Teams. In Zukunft werden die Teammitglieder automatisch hinzugefügt oder aus dem Team entfernt, wenn Sie der Microsoft 365-Gruppe beitreten oder diese verlässt.

## <a name="create-channels-to-focus-discussions"></a>Erstellen Sie Kanäle für fokussierte Unterhaltungen

Sie können die Gruppendiskussionen einschränken, indem Sie gezielte Kanäle erstellen. Informationen finden Sie unter [bewährte Methoden für die Organisation von Teams](best-practices-organizing.md).

## <a name="restrict-channel-creation"></a>Kanalerstellung einschränken

Wenn einem Teammitglied die Möglichkeit zum Erstellen von Kanälen gewährt wird, kann das Team Kanal Ausbreitung aufweisen. Team Besitzer sollten die Kanalerstellung,-Aktualisierung,-Löschung und-Wiederherstellung für Mitglieder in **Einstellungen > Mitglieder Berechtigungen**deaktivieren. Sehen Sie sich die [Übersicht über Teams und Kanäle an](teams-channels-overview.md).

![Bildschirmabbildung, in der der Abschnitt "Mitglieder Berechtigungen" auf der Registerkarte "Administratorkonsolen Einstellungen" angezeigt wird.](media/no-channel-creation.png "Bildschirmabbildung des Abschnitts "Mitglieder Berechtigungen" auf der Registerkarte "Administratorkonsolen Einstellungen". Die Optionen zum Erstellen oder Löschen von Kanälen für Mitglieder dürfen nicht aktiviert sein.")

## <a name="add-favorite-channels"></a>Hinzufügen von bevorzugten Kanälen

Um das neue Benutzer Engagement und die Inhaltserkennung zu beschleunigen, können Sie die bevorzugten Kanäle auswählen, die standardmäßig für den Benutzer verfügbar sind. Überprüfen Sie im Bereich **Kanäle** des Admin Centers die Kanäle unter der Spalte **für Mitglieder anzeigen** .

![Bildschirmabbildung, in der der Bereich "Kanäle" der Admin-Konsole angezeigt wird.](media/favorite-channels.png "Bildschirmabbildung mit Kanalbereich der Admin-Konsole Einige Kanäle werden auf "anzeigen" für Mitglieder überprüft.")

 Weitere Informationen finden Sie unter [Erstellen Ihrer ersten Teams und Kanäle](get-started-with-teams-create-your-first-teams-and-channels.md) .

## <a name="regulate-applications-and-bots-in-large-teams"></a>Regulieren von Anwendungen und Bots in umfangreichen Teams

Um das Hinzufügen von störenden Anwendungen oder Bots zu verhindern, können Teambesitzer apps und Connectors für Teammitglieder deaktivieren, hinzufügen, entfernen und hochladen. Deaktivieren Sie im Admin Center unter **Einstellungen > Mitglieder Berechtigungen**die drei Optionen, mit denen Mitglieder Apps oder Connectors hinzufügen können.

![Bildschirmabbildung, in der der Abschnitt "Mitglieder Berechtigungen" des Bereichs "Einstellungen" angezeigt wird.](media/disable-bots-connectors.png "Bildschirmabbildung, in der der Abschnitt "Mitglieder Berechtigung" des Bereichs "Einstellungen" angezeigt wird. Die Optionen für das Hinzufügen von apps oder Connectors für Mitglieder zulassen sind deaktiviert.")

Weitere Informationen finden Sie unter [apps, Bots, &-Connectors](deploy-apps-microsoft-teams-landing-page.md).

## <a name="regulate-team-and-channel-mentions"></a>Regulieren von Team-und Kanal Erwähnungen

Mithilfe von Team-und Kanal Erwähnungen können Sie das gesamte Team auf bestimmte Kanal Beiträge aufmerksam machen. Sobald eine Erwähnung in einem Beitrag verwendet wird, wird eine Benachrichtigung an Tausende von Teammitgliedern gesendet. Wenn die Benachrichtigungen zu häufig sind, können Teammitglieder überladen werden und sich möglicherweise an Teambesitzer beschweren. Um zu verhindern, dass Team-oder Kanal Erwähnungen angezeigt werden, deaktivieren Sie Team-und Kanal Erwähnungen für Mitglieder, indem Sie die Kontrollkästchen in den Gruppen **Einstellungen > @Mentions** Bereich deaktivieren.

![Bildschirmabbildung, in der der Abschnitt "bei Erwähnungen" im Bereich "Einstellungen" angezeigt wird.](media/no-at-mentions.png "Bildschirmabbildung, in der der Abschnitt "bei Erwähnungen" im Bereich "Einstellungen" angezeigt wird. Die Optionen für das Anzeigen und gewähren des Zugriffs auf die Mitglieder auf unter Erwähnungen sind deaktiviert.")

## <a name="consider-setting-up-moderation-in-your-channels"></a>Erwägen Sie, in Ihren Kanälen eine Moderation einzurichten.

Teambesitzer können die Moderation für einen Kanal aktivieren, um zu steuern, wer neue Beiträge starten und auf Beiträge in diesem Kanal antworten kann. Beim Einrichten der Moderation können Sie eines oder mehrere Teammitglieder als Moderatoren auswählen. Team Besitzer sind standardmäßig Moderatoren. Weitere Informationen finden Sie unter [Einrichten und Verwalten der Kanal Moderation](manage-channel-moderation-in-teams.md).

## <a name="related-topics"></a>Verwandte Themen

- [Bewährte Methoden zum Organisieren von Teams](best-practices-organizing.md)
- [Erstellen eines organisationsweiten Teams](create-an-org-wide-team.md)
