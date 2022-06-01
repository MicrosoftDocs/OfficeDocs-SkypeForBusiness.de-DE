---
title: Führen Sie ein Benutzerpiloten durch, um zu bewerten und zu testen, wie Microsoft Teams in Ihrer Organisation funktionieren.
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Anleitung zum Starten eines Microsoft Teams Pilotprojekts, um alles zu erkunden, was Teams Ihrer Organisation bieten können, während Sie weiterhin Skype for Business
ms.localizationpriority: medium
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae69bab918a9c8bd542e5ec70a95df7544677d8d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823224"
---
# <a name="conduct-a-user-pilot"></a>Durchführen eines Benutzerpilotprojekts

![Upgrade journey diagram, highlighting Deployment and Implementation.](media/upgrade-banner-deployment.png "Phasen der Upgradephase mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihrer Upgrade-Reise und gibt Einblicke für die Durchführung eines effektiven Pilotprojekts. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
- [Ihre Organisation vorbereitet](./upgrade-prepare-organization.md)

Durch die Bereitstellung neuer Technologien kann Ihre Organisation geschäftlichen Nutzen wie Kosteneinsparungen, Sicherheitscompliance, Mitarbeiterzufriedenheit und betriebliche Effizienz realisieren, kann sich aber auch auf die Produktivität und Organisationsinfrastruktur Ihrer Benutzer (Ihr Netzwerk) auswirken. Bevor Sie neue Technologien in Ihrer Organisation aktivieren, führen Sie ein formelles Benutzerpiloten durch. Genau wie Sie vor dem Malen des gesamten Raums einen kleinen Farbpatch auf eine Wand malen würden, testen Sie eine breite Einführung in kleinerem Maßstab, indem Sie ein Pilotprojekt durchführen, um die technische und Benutzerbereitschaft zu überprüfen, Probleme zu identifizieren und zu mindern und eine erfolgreiche organisationsweite Implementierung sicherzustellen.

Um die realistischsten Ergebnisse zu erzielen, sollte das Pilotprojekt tatsächliche Benutzer einbeziehen, nachahmen, wie sie kommunizieren und zusammenarbeiten, und sowohl die technische als auch die Benutzererfahrung überprüfen. Unabhängig davon, ob Ihre Organisation Skype for Business und Teams parallel ausführen, in Zukunft ein Upgrade auf Teams durchführen oder neue Funktionen wie Anrufe oder Konferenzen bereitstellen möchte, kann ein Pilotprojekt dabei helfen, den richtigen Weg für Ihre Organisation zu identifizieren. Manchmal als Phase 1 eines Rollouts betrachtet, nutzt das ideale Pilotprojekt die Vorbereitung, die Sie bereits begonnen haben, und implementiert Ihren definierten Plan mit einer gezielten Benutzergruppe.

|&nbsp; | &nbsp;|
|---|---|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt.](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Wie werden Sie ein Pilotprojekt verwenden, um die Projektleitung zu informieren?</li></ul> |
| ![Ein Symbol, das den nächsten Schritt darstellt.](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Verwenden Sie die nachstehenden Anleitungen, um Ihr formales Pilotprojekt zu entwerfen und auszuführen.</li></ul>|

> [!Tip]
> Verwenden Sie die [Beispiel-Pilotressourcen](https://aka.ms/UpgradeSuccessKit) , um Ihre Kommunikations-, Testplan- und Feedbackumfrage zu entwerfen.

## <a name="1-outline-pilot-logistics"></a>1. Gliederung der Pilotlogistik

Ein erfolgreiches Pilotprojekt hat Start- und Endtermine sowie [klar definierte Ziele](upgrade-define-project-scope.md#project-goals) für die Erfolgsmessung definiert. Diese Ziele sollten mit dem Umfang Ihres breiteren Projekts übereinstimmen, wie Sie bei der [Definition des Projektumfangs](upgrade-define-project-scope.md) dokumentiert haben, und werden verwendet, um Den Weg nach vorne zu informieren, nachdem Das Pilotprojekt beendet ist. Sie sollten auch sicherstellen, dass Sie die richtigen Projektbeteiligten für die Dauer des Projekts einbezogen haben. Sie sollten sicher sein, genügend Zeit für die Ausführung des Pilotprojekts zu haben und dessen Auswirkungen zu bewerten: Wir empfehlen ein Minimum von 30 Tagen.

Beginnen Sie klein, und fügen Sie Ihrem Pilotprojekt nach Bedarf hinzu – ganz gleich, ob Sie Workloads, Features oder zusätzliche Benutzer hinzufügen – und sich Zeit für die Bewertung der Ergebnisse und die Anpassung Ihres Pilotprojekts beim Durchlaufen nehmen. Möglicherweise entscheiden Sie sich sogar für nachfolgende Pilotprojekte, da neue Teams Features gemäß der Roadmap veröffentlicht werden.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Wählen Sie Ihre Pilotteilnehmer und Testszenarien aus.

Eine der wichtigsten Aufgaben der Pilotplanung ist die sorgfältige Teilnehmerauswahl. Denken Sie daran, dass Teams für Teamarbeit optimiert ist. Achten Sie daher darauf, Pilotteilnehmer nicht nur basierend auf Rollen oder Personas, sondern auch basierend auf ihrem Projekt und ihrer teamübergreifenden Arbeit auszuwählen. Ein guter Ausgangspunkt ist, Ihre Projektbeteiligten und Abteilungsleiter nach echten Projekten zu fragen, die Sie in Teams überprüfen können. Ein Beispiel für ein rollenbasiertes Projekt könnte darin sein, Teams mit Ihrer Vertriebsorganisation zu verwenden, um sicherzustellen, dass Außendienstmitarbeiter problemlos auf die benötigten Ressourcen zugreifen und Erkenntnisse mit anderen Feldmitgliedern teilen können. Ein Beispiel für projektbasierte Arbeit könnte die Koordination einer Produktstartveranstaltung mit den Teams für Marketing, Schulung, Öffentlichkeitsarbeit und Veranstaltungsplanung sein. Je nachdem, welche Szenarien Sie auswählen, sollte das Pilotprojekt auf wichtige It-Mitarbeiter, Schulungen und Ihren Helpdesk ausgeweitet werden, damit Sie die Lösung gründlich überprüfen und gleichzeitig die Projektmanagementressourcen vollständig optimieren können.

> [!Tip]
> Achten Sie bei der Auswahl Ihrer Teams Pilotgruppenteilnehmer darauf, die wichtigsten Benutzer von Skype for Business einzuschließen. Wenden Sie sich an diese Benutzer, um zu verstehen, wie sie Skype for Business heute verwenden, und erstellen Sie dann einen Testplan, um zu überprüfen, ob Teams ihre aktuellen Anforderungen erfüllen können.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Entwerfen Ihrer Testplan- und Feedbackumfrage

Für eine erfolgreiche Piloterfahrung geben Sie Ihren Teilnehmern klar definierte Aufgaben zusammen mit einer Möglichkeit, ihr Feedback zu teilen. Gruppieren Sie Aufgaben zusammen, um Ihren Benutzern reale Szenarien anzubieten und so die Relevanz ihrer täglichen Aktivitäten zu demonstrieren. Lassen Sie die Anwendungsfälle, die Sie in ["Bewertung der Bereitschaft für organisatorische Änderungen](./upgrade-org-change-readiness.md) " definiert haben, Ihren Testplan leiten.

Ihre Organisation kann sich entscheiden, alle Funktionen gleichzeitig zu pilotieren oder einen graduellen Ansatz zu verwenden, z. B. zuerst die Pilotzusammenarbeit, dann Besprechungen, dann Chats und Anrufe. Stellen Sie sicher, dass Sie über einen offenen Feedbackkanal verfügen, um den Fortschritt nachzuverfolgen und Ergebnisse zu messen. Verwenden Sie eine vordefinierte Umfrage als einfache Möglichkeit zum Erfassen und Bewerten von Pilotergebnissen. der Umfrageentwurf sollte auf den Szenarien und Features in Ihrem Testplan basieren.

## <a name="4-create-your-communications-plan"></a>4. Erstellen Ihres Kommunikationsplans

Für den Erfolg Ihres Pilotprojekts ist es entscheidend, dass Sie die Pilotteilnehmer darüber informieren, was wann und warum geschieht und was von ihnen erwartet wird. Um Die Begeisterung und maximale Teilnahme zu fördern, sollten Sie zusätzlich zu Links zu Schulungen und Support, in denen Benutzer zusätzliche Informationen erhalten können, während sie während des Pilotprojekts fortschritten, Benutzerwertnachrichten einschließen. Im Folgenden finden Sie einige Beispielressourcen für die ersten Schritte mit Ihrem Pilotkommunikationsplan:

- [Pilotressourcen](https://aka.ms/UpgradeSuccessKit), einschließlich E-Mail-Vorlagen und Fragen zur Beispielfeedbackumfrage
- [Wechseln Sie von Skype for Business zu Teams](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), einer Schnellstartanleitung, die Skype for Business Benutzern bei den ersten Teams

## <a name="5-conduct-your-pilot"></a>5. Führen Sie Ihr Pilotprojekt durch

Mit der gesamten Logistik sind Sie jetzt bereit, Mit Ihrem Pilotprojekt zu beginnen. Die Durchführung Ihres Pilotprojekts umfasst die Kommunikation mit Ihren Benutzern, die Überwachung Ihres Netzwerks und Ihrer Nutzung, um sicherzustellen, dass Ihre Netzwerkleistung und Anrufqualität fehlerfrei bleiben, das Sammeln von Feedback von Teilnehmern und das Überprüfen von Helpdesktickets für Fragen im Zusammenhang mit Teams.

### <a name="tips-for-pilot-success"></a>Tipps für Piloterfolg

Die folgenden Tipps können dazu beitragen, den Erfolg Ihres Pilotprojekts sicherzustellen:

- Vergewissern Sie sich vor beginn des Pilotprojekts, dass alle Pilotteilnehmer für den entsprechenden [Koexistenzmodus] aktiviert sind.
- (https://aka.ms/SkypeToTeams-SetCoexistence) sie überprüfen möchten.
- Treffen Sie sich wöchentlich während Des Pilotprojekts mit den Projektbeteiligten, um Benutzerfeedback, Nutzungsdaten, Netzwerkdaten und Helpdesk-Tickets zu überprüfen, um sicherzustellen, dass Ihr Pilotprojekt reibungslos funktioniert. Nehmen Sie nach Bedarf Anpassungen vor.

### <a name="suggested-timeline"></a>Vorgeschlagene Zeitachse

Hier ist eine vorgeschlagene Zeitachse für ein 30-tägiges Pilotprojekt:

- Eine Woche vor dem Pilot-Kickoff: Senden der ersten Kommunikation an Pilotbenutzer.
- Tag 1: Senden der Kickoff-Kommunikation an Pilotbenutzer.
- Tag 7: Halten Sie die erste wöchentliche Projektteam-Prüfpunktbesprechung ab.
- Tag 14: Senden Sie mid-point communication an Ihre Pilotbenutzer, halten Sie eine wöchentliche Projektteam-Prüfpunktbesprechung ab.
- Tag 21: Halten Sie eine wöchentliche Projektteam-Prüfpunktbesprechung ab.
- Tag 30: Senden Sie die endgültige Kommunikation an Ihre Pilotbenutzer.
- Tage 31–45: Bewerten Sie die Pilotergebnisse, und planen Sie die nächsten Schritte.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Bewerten Der Lernprozesse und Bewerten Ihres Zukunftsplans

Nach Abschluss Ihres Pilotprojekts ist es An der Zeit, alle Feedbackumfragen, endgültigen Netzwerkstatistiken und Supporttickets für die Analyse Ihrer Ziele zu sammeln und zu bestimmen, ob Sie Ihren Plan für die Zukunft implementieren. Möglicherweise stellen Sie fest, dass Ihre Organisation für eine umfassende Bereitstellung bereit ist, oder Sie möchten Ihr Pilotprojekt auf weitere Benutzer erweitern, oder Sie möchten das Pilotprojekt zu einem späteren Zeitpunkt erneut aufrufen, nachdem alle von Ihnen identifizierten Bedenken abgemildert wurden. Denken Sie daran, dass Ihr Pilotprojekt eine großartige Möglichkeit ist, technische und Benutzerergebnisse in einer _kontrollierten_ Umgebung vorherzusagen; seien Sie über das Springen zu schnell nachdenklich.

Wenn Ihre Ergebnisse Folgendes angeben:

- **Ihre Pilotziele (z. B. Benutzerzufriedenheit und Netzwerkqualität) wurden erreicht**. Sie sollten bereit sein, mit der nächsten Phase Ihres Rollouts fortzufahren. Abhängig von den Zielen Ihres Projekts kann dies eine der folgenden Sein:
  - Erweitern des Pilotprojekts auf weitere Teilnehmer
  - [Aktivieren von Teams neben Skype for Business (**Inselmodus**) für einige oder die gesamte Organisation](./setting-your-coexistence-and-upgrade-settings.md)
  - [Aktualisieren von Benutzern von Skype for Business auf Teams (**nur Teams** Modus) für einige oder die gesamte Organisation](./setting-your-coexistence-and-upgrade-settings.md)
- **Ihr Pilotprojekt hat nicht die gewünschten Ergebnisse erzielt (z. B. Benutzerzufriedenheit und Netzwerkqualität),** nehmen Sie sich Zeit, um die entsprechenden Anpassungen an Ihrem Plan vorzunehmen, und überprüfen Sie Ihr Pilotprojekt erneut.

> [!Tip]
> Enlist your pilot participants as peer champions to help evangelize and onboard new users to Teams. Peer-Experten können sich problemlos mit anderen Benutzern in Verbindung setzen, ihre eigenen Erfahrungen und Erkenntnisse teilen und ihren Kollegen Unterstützung und Anleitung bieten. Erfahren Sie mehr über [Experten](
https://adoption.microsoft.com/become-a-champion/) und wie Sie sie in Ihrem eigenen Rollout verwenden können.