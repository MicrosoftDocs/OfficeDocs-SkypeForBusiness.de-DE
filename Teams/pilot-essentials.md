---
title: Pilot Microsoft Teams mit Skype for Business | Bereitstellen, Implementierung durchführen
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Leitfaden zum Starten eines Microsoft Teams-Pilotprojekts zur Untersuchung aller Teams, die Ihre Organisation anbieten können, während Sie Skype for Business weiterhin verwenden
localization_priority: Normal
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 824b14ba49391720305778e676bb47850d836196
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433183"
---
![Diagramm zur Aktualisierung der Reise, Highlighting Bereitstellung und Implementierung] (media/upgrade-banner-deployment.png "Phasen der Upgrade-Reise, wobei der Schwerpunkt auf der Bereitstellungs-und Implementierungsphase liegt")

Dieser Artikel ist Teil der Bereitstellungs-und Implementierungsphase Ihrer Upgrade-Reise und teilt Einblicke für die Ausführung eines effektiven Pilotprojekts. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ihre Projekt Beteiligten wurden eingetragen](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)
- [Verständliche Koexistenz und Interoperabilität von Skype for Business und Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Ihre Upgrade-Reise gewählt](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Ihre Umgebung vorbereitet](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Vorbereiten Ihrer Organisation](https://aka.ms/SkypeToTeams-UserReadiness)

# <a name="conduct-a-user-pilot"></a>Durchführen eines Benutzerpilotprojekts

Durch die Bereitstellungneuer Technologien kann Ihre Organisation geschäftlichen Nutzen wie Kosteneinsparungen, Sicherheitskonformität, Mitarbeiterzufriedenheit und operative Effizienz verwirklichen, kann sich aber auch auf die Produktivität und die organisatorische Infrastruktur Ihrer Benutzer auswirken ( Ihrem Netzwerk). Bevor Sie neue Technologien in Ihrer Organisation aktivieren, führen Sie einen formellen Benutzer Pilot aus. Genau wie Sie einen kleinen Fleck Farbe auf eine Wand malen würden, bevor Sie den ganzen Raum malen, würden Sie einen breiten Rollout auf einem kleineren Maßstab testen, indem Sie ein Pilotprojekt durchführen, um die technische und Benutzer Bereitschaft zu überprüfen, Probleme zu erkennen und zu verringern und um sicherzustellen, dass eine erfolgreiche organisationsweite Implementierung.

Um die realistischsten Ergebnisse zu erzielen, sollte der Pilot die tatsächlichen Benutzer einbeziehen, deren Kommunikation und Zusammenarbeit nachahmen und sowohl die technischen als auch die Benutzererfahrung überprüfen. Unabhängig davon, ob Ihre Organisation Skype for Business und Teams nebeneinander ausführt, ein Upgrade auf Teams in der Zukunft durchführen oder neue Funktionen wie ein Anruf oder eine Konferenz bereitstellen, kann ein Pilotprojekt den richtigen Weg für Ihre Organisation ermitteln. Manchmal als Phase 1 eines Rollouts betrachtet, nutzt der ideale Pilot die bereits begonnene Vorbereitung und implementiert ihren definierten Plan mit einer Zielgruppe von Benutzern.

| | |
|---|---|
| ![Ein Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Wie werden Sie ein Pilotprojekt verwenden, um die Projekt Richtung zu unterrichten?</li></ul> |
| ![Ein Symbol, das den nächsten Schritt darstellt](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Führen Sie die folgenden Anleitungen aus, um Ihr formales Pilotprojekt zu entwerfen und auszuführen.</li></ul>|

> [!Tip]
> Verwenden Sie die Beispiel [Ressourcen für Pilotprojekte](https://aka.ms/UpgradeSuccessKit) , um Ihre Kommunikation, Ihren Testplan und ihre Feedback Umfrage zu entwerfen.

## <a name="1-outline-pilot-logistics"></a>1. Skizzieren der Pilot Logistik

Bei einem erfolgreichen Pilotprojekt wurden Anfangs-und Endtermine sowie [klar definierte Ziele](upgrade-define-project-scope.md#project-goals) für die Erfolgsmessung definiert. Diese Ziele sollten mit dem Umfang Ihres breiteren Projekts übereinstimmen, wie Sie beim [Definieren des Projektumfangs](upgrade-define-project-scope.md)dokumentiert haben, und Sie werden verwendet, um den Pfad nach dem Ende des Pilotprojekts weiterzuleiten. Sie sollten auch sicherstellen, dass Sie die richtigen Projekt beteiligten für die Dauer des Projekts einbezogen haben. Sie möchten sicherstellen, dass genügend Zeit für das Ausführen des Pilotprojekts und die Beurteilung seiner Auswirkungen zulässt: Wir empfehlen eine Mindestanzahl von 30 Tagen.

Starten Sie klein, und fügen Sie Ihrem Pilotprojekt je nach Bedarf – entweder durch Hinzufügen von Arbeitslasten oder Features oder durch zusätzliche Benutzer – Zeit zum Bewerten von Ergebnissen und zum Anpassen des Pilotprojekts während der Iteration hinzu. Möglicherweise können Sie auch nachfolgende Piloten ausführen, da neue Teams-Features pro Roadmap freigegeben werden.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Wählen Sie Ihre Pilot Teilnehmer und Testszenarien aus.

Eine der wichtigsten Aufgaben bei der Planung von Pilotprojekten ist die sorgfältige Auswahl der Teilnehmer. Beachten Sie, dass Teams für Teamarbeit optimiert sind, stellen Sie daher sicher, dass Sie Pilot Teilnehmer auswählen, die nicht nur auf Rollen oder Personas basieren, sondern auch auf der Grundlage ihrer Projekt-und Teamarbeit. Eine hervorragende Anlaufstelle ist es, ihre Stakeholder und Abteilungsleiter nach echten Projekten zu Fragen, die Sie in Teams überprüfen können. Ein Beispiel für ein rollenbasiertes Projekt kann die Verwendung von Teams in ihrer Vertriebsorganisation sein, um sicherzustellen, dass die Feld Mitarbeiter problemlos auf die benötigten Ressourcen zugreifen und Einblicke mit anderen Feld Mitgliedern austauschen können. Ein Beispiel für projektbasierte Arbeit ist möglicherweise die Koordination einer Produkt Einführungsveranstaltung mit den Teams Marketing, Schulung, Public Relations und Event Planning. Je nachdem, welche Szenarien Sie auswählen, sollte sich das Pilotprojekt auf wichtige Personen in IT, Schulung und Helpdesk erstrecken, sodass Sie die Lösung gründlich überprüfen können, während Sie die Projektmanagement Ressourcen vollständig optimieren.

> [!Tip]
> Achten Sie bei der Auswahl der Teilnehmer Ihrer Team-Pilotgruppe darauf, die besten Nutzer von Skype for Business einzubeziehen. Erkundigen Sie sich bei diesen Benutzern, wie Sie Skype for Business heute nutzen, und erstellen Sie dann einen Testplan, um zu überprüfen, ob Teams die aktuellen Anforderungen erfüllen können.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Entwerfen des Testplans und der Feedback Umfrage

Für eine erfolgreiche Pilot Erfahrung geben Sie den Teilnehmern klar definierte Aufgaben zusammen mit einer Möglichkeit, Ihr Feedback zu teilen. Gruppieren Sie Aufgaben zusammen, um Ihren Benutzern realistische Szenarien anzubieten, die Relevanz für Ihre täglichen Aktivitäten demonstrieren. Lassen Sie die Anwendungsfälle, die Sie in [bewerten der Bereitschaft zur organisatorischen Änderung](https://aka.ms/OrgReadiness) definiert haben, Ihren Testplan durchführen.

Möglicherweise wird in Ihrer Organisation alle Funktionen gleichzeitig gesteuert, oder es wird ein gradueller Ansatz verwendet, beispielsweise die Pilot Zusammenarbeit zuerst, dann Besprechungen, dann Chat und Anrufe. Stellen Sie sicher, dass Sie über einen offenen Feedback Kanal verfügen, um den Fortschritt nachverfolgen und Ergebnisse messen zu können. Verwenden Sie eine vordefinierte Umfrage als einfache Möglichkeit, um Pilotergebnisse zu erfassen und zu bewerten. Das Umfrage Design sollte auf den Szenarien und Features in Ihrem Testplan basieren.

## <a name="4-create-your-communications-plan"></a>4. Erstellen Ihres Kommunikationsplans

Für den Erfolg Ihres Pilotprojekts ist es entscheidend, dass Sie Pilot Teilnehmer darüber informieren, was passiert, wann und warum und was von Ihnen erwartet wird. Um die Spannung und die maximale Teilnahme zu steigern, sollten Sie neben Links zu Schulungen und Support auch Benutzerwert Nachrichten einbeziehen, in denen Benutzer zusätzliche Informationen erhalten können, während Sie den Pilot Vorgang fortsetzen. Nachfolgend finden Sie einige Beispiel Ressourcen, die Ihnen den Einstieg in Ihren Pilot Kommunikationsplan verschaffen:

- [Pilot Ressourcen](https://aka.ms/UpgradeSuccessKit), einschließlich e-Mail-Vorlagen und Fragen zur Feedback Umfrage
- [Wechseln Sie zu Teams von Skype for Business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), einem Schnellstarthandbuch, das dazu dient, Skype for Business-Benutzern beim Einstieg in Teams zu helfen.

## <a name="5-conduct-your-pilot"></a>5. durchführen Ihres Pilotprojekts

Nachdem Sie die gesamte Logistik eingerichtet haben, können Sie jetzt mit Ihrem Pilotprojekt beginnen. Die Durchführung Ihres Pilotprojekts umfasst die Kommunikation mit ihren Benutzern, das Überwachen Ihres Netzwerks und die Nutzung, um sicherzustellen, dass Ihre Netzwerkleistung und die Anrufqualität weiterhin fehlerfrei sind, Feedback von Teilnehmern sammelt und Helpdesk-Tickets für Fragen im Zusammenhang mit Teams.

### <a name="tips-for-pilot-success"></a>Tipps für den Erfolg von Pilotprojekten

Die folgenden Tipps können Ihnen helfen, den Erfolg Ihres Pilotprojekts zu gewährleisten:

- Bevor Sie mit dem Pilotprojekt beginnen, vergewissern Sie sich, dass alle Pilot Teilnehmer für den entsprechenden [Koexistenzmodus] aktiviert sind.
- (https://aka.ms/SkypeToTeams-SetCoexistence) Sie möchten überprüfen.
- Wöchentlich, während des gesamten Pilotprojekts, treffen Sie sich mit Ihren Projekt Beteiligten, um Benutzer Feedback, Nutzungsdaten, Netzwerkdaten und Helpdesk-Tickets zu überprüfen, um sicherzustellen, dass ihr Pilotprojekt reibungslos läuft. Nehmen Sie die gewünschten Anpassungen vor.

### <a name="suggested-timeline"></a>Vorgeschlagene Zeitachse

Hier sehen Sie eine vorgeschlagene Zeitachse für einen 30-Tage-Pilot:

- Eine Woche vor dem Start des Pilotprojekts: erste Kommunikation an Pilotbenutzer senden.
- Tag 1: senden Sie eine Kickoff-Kommunikation an Pilotbenutzer.
- Tag 7: halten Sie die erste wöchentliche Projektteam-Checkpoint-Besprechung.
- Tag 14: senden Sie eine Mid-Point-Kommunikation an Ihre Pilotbenutzer, und führen Sie eine wöchentliche Projektteam-Checkpoint-Besprechung.
- Tag 21: halten Sie eine wöchentliche Projektteam-Checkpoint-Besprechung.
- Tag 30: senden Sie die endgültige Kommunikation an Ihre Pilotbenutzer.
- Tage 31 – 45: Bewerten Sie die Pilotergebnisse, und planen Sie die nächsten Schritte.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Bewerten von Lernenden und bewerten Ihres Go-Forward-Plans

Nachdem ihr Pilotprojekt abgeschlossen ist, ist es an der Zeit, alle Feedback Umfragen, endgültige Netzwerkstatistiken und Support Tickets für die Analyse ihrer Ziele zu sammeln und festzustellen, ob Sie Ihren Go-Forward-Plan implementieren. Möglicherweise stellen Sie fest, dass Ihre Organisation für eine breite Bereitstellung bereit ist, oder Sie möchten Ihr Pilotprojekt auf weitere Benutzer erweitern, oder Sie möchten das Pilotprojekt zu einem späteren Zeitpunkt erneut besuchen, nachdem die von Ihnen identifizierten Bedenken verringert wurden. Denken Sie daran, dass ihr Pilotprojekt eine hervorragende Möglichkeit ist, technische und __ Benutzer Ergebnisse in einer kontrollierten Umgebung vorherzusagen. seien Sie nachdenklich, wenn Sie zu schnell vorwärts springen.

Wenn Ihre Ergebnisse Folgendes angeben:

- **Ihre Pilot Ziele (beispielsweise die Benutzerzufriedenheit und die Netzwerkqualität) erreicht**wurden, sollten Sie bereit sein, mit der nächsten Phase des Rollouts fortzufahren. Je nach den Zielen Ihres Projekts kann dies eine der folgenden Folgen haben:
  - Erweitern des Pilotprojekts auf weitere Teilnehmer
  - [Aktivieren von Teams neben Skype for Business (**Inseln** -Modus) für einige oder alle Ihrer Organisation](https://aka.ms/SkypeToTeams-SetCoexistence)
  - [Aktualisieren von Benutzern von Skype for Business auf Teams (nur im Modus "**nur für Teams** ") für einige oder alle Ihrer Organisation](https://aka.ms/SkypeToTeams-SetCoexistence)
- **Ihr Pilotprojekt die gewünschten Ergebnisse nicht erreicht hat (beispielsweise die Benutzerzufriedenheit und die Netzwerkqualität)**, nehmen Sie sich Zeit, um die entsprechenden Anpassungen an Ihrem Plan vorzunehmen, und überprüfen Sie Ihr Pilotprojekt erneut.

> [!Tip]
> Tragen Sie Ihre Pilot Teilnehmer als Peer-Champions ein, um neue Benutzer in Teams zu evangelisieren und an Bord zu bringen. Peer-Champions können sich auf einfache Weise mit anderen Nutzern in Verbindung setzen, ihre eigenen Erfahrungen und Erkenntnisse austauschen und ihren Kollegen Unterstützung und Anleitung bieten. Erfahren Sie mehr über [Champions](https://go.microsoft.com/fwlink/?linkid=859068) und wie Sie Sie in Ihrem eigenen Rollout verwenden können.
