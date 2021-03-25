---
title: Führen Sie einen Benutzerpilot durch, um auszuwerten und zu testen, wie Microsoft Teams in Ihrer Organisation funktioniert
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Anleitungen zum Starten eines Microsoft Teams-Pilotprojekts, um alles zu erkunden, was Teams Ihrer Organisation bieten kann, während Sie Skype for Business weiterhin verwenden
localization_priority: Normal
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e2d909722674f23e253d0ae937efddb14d96d7a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108371"
---
# <a name="conduct-a-user-pilot"></a>Durchführen eines Benutzerpilotprojekts

![Upgrade-Reisediagramm mit Hervorhebung von Bereitstellung und Implementierung](media/upgrade-banner-deployment.png "Phasen des Upgradewegs mit Schwerpunkt auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihres Upgradewegs und gibt Einblicke für die Durchführung eines effektiven Pilotprojekts. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereiten Ihrer Umgebung](./upgrade-prepare-environment.md)
- [Vorbereiten Ihrer Organisation](./upgrade-prepare-organization.md)

Durch die Bereitstellung neuer Technologien kann Ihre Organisation geschäftliche Vorteile wie Kosteneinsparungen, Sicherheitskonformität, Mitarbeiterzufriedenheit und betriebliche Effizienz erzielen, aber sie kann sich auch auf die Produktivität und Organisationsinfrastruktur Ihrer Benutzer (Ihr Netzwerk) auswirken. Führen Sie vor der Aktivierung neuer Technologien in Ihrer Organisation einen formellen Benutzerpilot durch. Genau wie Sie einen kleinen Farbfleck an eine Wand malen würden, bevor Sie den gesamten Raum bemalen, würden Sie ein breites Rollout in kleinerem Maßstab testen, indem Sie einen Pilot durchführen, um die technische Bereitschaft und Benutzerbereitschaft zu überprüfen, Probleme zu identifizieren und zu verringern und eine erfolgreiche organisationsweite Implementierung zu gewährleisten.

Um die realistischsten Ergebnisse zu erzielen, sollte der Pilot die tatsächlichen Benutzer beteiligen, die Kommunikation und Zusammenarbeit nachahmen und sowohl die technischen als auch die Benutzererfahrungen überprüfen. Ganz gleich, ob Ihre Organisation skype for Business und Teams nebeneinander führen, in Zukunft ein Upgrade auf Teams durchführen oder neue Funktionen wie Anrufe oder Konferenzen bereitstellen möchten, ein Pilotprojekt kann dabei helfen, den richtigen Weg für Ihre Organisation zu finden. Manchmal als Phase 1 eines Rollouts betrachtet, nutzt der ideale Pilot die Vorbereitung, die Sie bereits begonnen haben, und implementiert Ihren definierten Plan mit einer gezielten Gruppe von Benutzern.

| | |
|---|---|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Wie wird ein Pilotprojekt verwendet, um die Projektrichtung zu informieren?</li></ul> |
| ![Ein Symbol, das den nächsten Schritt darstellt](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Verwenden Sie die nachstehenden Anleitungen zum Entwerfen und Ausführen Ihres formellen Pilotprojekts.</li></ul>|

> [!Tip]
> Verwenden Sie die [Beispielpilotressourcen,](https://aka.ms/UpgradeSuccessKit) um Ihre Kommunikation, Ihren Testplan und Ihre Feedbackumfrage zu entwerfen.

## <a name="1-outline-pilot-logistics"></a>1. Gliederung der Pilotlogistik

Ein erfolgreicher Pilot hat Start- und Endtermine und klar [definierte](upgrade-define-project-scope.md#project-goals) Ziele für die Erfolgsmessung definiert. Diese Ziele sollten dem Umfang Ihres breiteren Projekts entsprechen, wie Sie beim Definieren des Projektumfangs dokumentiert haben, und werden verwendet, um Ihren Weg nach dem Ende des Pilotprojekts zu informieren. [](upgrade-define-project-scope.md) Sie sollten auch sicherstellen, dass Sie die richtigen Projektbeteiligten für die Dauer des Projekts einbezogen haben. Sie sollten sicher sein, dass Sie genügend Zeit für die Ausführung des Pilotprojekts haben und deren Auswirkungen bewerten: Wir empfehlen mindestens 30 Tage.

Beginnen Sie klein, und fügen Sie dem Piloten nach Bedenkzeit – sei es durch Hinzufügen von Arbeitslasten oder Features oder zusätzlichen Benutzern – Zeit zum Bewerten der Ergebnisse und zum Anpassen des Pilotprojekts während des Iterierens hinzu. Sie können sich sogar für die Ausführung nachfolgender Piloten entscheiden, da neue Teams-Features nach der Roadmap veröffentlicht werden.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Auswählen ihrer Pilotteilnehmer und Testszenarien

Eine der wichtigsten Aufgaben der Pilotplanung ist eine durchdachte Teilnehmerauswahl. Denken Sie daran, dass Teams für Teamarbeit optimiert ist. Achten Sie daher darauf, pilotierte Teilnehmer nicht nur anhand von Rollen oder Personen, sondern auch basierend auf ihrer Projekt- und teamübergreifenden Arbeit auszuwählen. Ein guter Einstieg ist es, Ihre Projektbeteiligten und Abteilungsleiter nach echten Projekten zu fragen, die Sie in Teams überprüfen können. Ein Beispiel für ein rollenbasiertes Projekt könnte die Verwendung von Teams mit Ihrer Vertriebsorganisation sein, um sicherzustellen, dass Außendienstmitarbeiter problemlos auf die benötigten Ressourcen zugreifen und Erkenntnisse für andere Feldmitglieder freigeben können. Ein Beispiel für projektbasierte Arbeit könnte die Koordination einer Produkteinführungsveranstaltung mit den Teams für Marketing, Schulung, Öffentlichkeitsarbeit und Veranstaltungsplanung sein. Ganz gleich, welche Szenarien Sie auswählen, das Pilotprojekt sollte sich auf wichtige Personen in IT, Schulungen und Ihrem Helpdesk erstrecken, damit Sie die Lösung gründlich überprüfen und gleichzeitig die Projektmanagementressourcen vollständig optimieren können.

> [!Tip]
> Achten Sie bei der Auswahl Ihrer Teams-Pilotgruppenteilnehmer darauf, die Topbenutzer von Skype for Business mit zu verwenden. Überprüfen Sie mit diesen Benutzern, wie sie Skype for Business heute verwenden, und erstellen Sie dann einen Testplan, um zu überprüfen, ob Teams ihre aktuellen Anforderungen erfüllen kann.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Entwerfen Ihres Testplans und einer Feedbackumfrage

Für eine erfolgreiche Piloterfahrung geben Sie Ihren Teilnehmern klar definierte Aufgaben, die sie ausführen müssen, zusammen mit einer Möglichkeit, ihr Feedback zu teilen. Gruppieren Sie Aufgaben zusammen, um Ihren Benutzern reale Szenarien zu bieten, um die Relevanz ihrer täglichen Aktivitäten zu demonstrieren. Lassen Sie den Testplan von den in Bewerten der Bereitschaft zur [Organisationsänderung](./upgrade-org-change-readiness.md) definierten Verwendungsfällen leiten.

Ihre Organisation kann sich entscheiden, alle Funktionen gleichzeitig zu pilotieren oder einen schrittweisen Ansatz zu verwenden, z. B. die Pilotzusammenarbeit zuerst, dann Besprechungen, dann Chats und Anrufe. Stellen Sie sicher, dass Sie über einen offenen Feedbackkanal verfügen, um den Fortschritt zu verfolgen und ergebnisse zu messen. Verwenden Sie eine vordefinierte Umfrage als einfache Möglichkeit zum Erfassen und Bewerten von Pilotergebnissen. Das Umfragedesign sollte auf den Szenarien und Features in Ihrem Testplan basieren.

## <a name="4-create-your-communications-plan"></a>4. Erstellen Ihres Kommunikationsplans

Für den Erfolg Ihres Pilotprojekts ist es entscheidend, dass Sie die Pilotteilnehmer darüber informieren, was wann und warum geschieht und was von ihnen erwartet wird. Um Die Spannung und maximale Teilnahme zu fördern, sollten Sie zusätzlich zu Links zu Schulungen und Support, in denen Benutzer während des Pilotfortschritts zusätzliche Informationen erhalten können, auch Benutzerwertmeldungen enthalten. Hier finden Sie einige Beispielressourcen für die ersten Schritte mit Ihrem Pilotkommunikationsplan:

- [Pilotressourcen,](https://aka.ms/UpgradeSuccessKit)einschließlich E-Mail-Vorlagen und Fragen zur Beispielfeedbackumfrage
- [Wechseln von Skype for Business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)zu Teams , ein Schnellstarthandbuch, das Skype for Business-Benutzern den Einstieg in Teams ermöglichen soll

## <a name="5-conduct-your-pilot"></a>5. Führen Sie Ihren Pilot durch

Wenn die ganze Logistik an Ort und Stelle ist, können Sie jetzt mit dem Piloten beginnen. Die Durchführung Ihres Pilotprojekts umfasst die Kommunikation mit Ihren Benutzern, die Überwachung Ihres Netzwerks und die Nutzung, um sicherzustellen, dass Ihre Netzwerkleistung und Anrufqualität fehlerfrei bleibt, Feedback von Teilnehmern einsammeln und Helpdesktickets für Fragen im Zusammenhang mit Teams überprüfen.

### <a name="tips-for-pilot-success"></a>Tipps für den Piloterfolg

Die folgenden Tipps können Ihnen helfen, den Erfolg Ihres Pilotprojekts sicherzustellen:

- Vergewissern Sie sich vor Beginn des Pilotprojekts, dass alle Pilotteilnehmer für den geeigneten [Koexistenzmodus] aktiviert sind.
- ( https://aka.ms/SkypeToTeams-SetCoexistence) überprüfen möchten.
- Treffen Sie sich wöchentlich während des gesamten Pilotprojekts mit Projektbeteiligten, um Benutzerfeedback, Nutzungsdaten, Netzwerkdaten und Helpdesktickets zu überprüfen, um sicherzustellen, dass Ihr Pilotprojekt reibungslos ausgeführt wird. Nehmen Sie bei Bedarf alle Anpassungen vor.

### <a name="suggested-timeline"></a>Vorgeschlagene Zeitachse

Hier ist eine vorgeschlagene Zeitachse für einen 30-tägigen Pilot:

- Eine Woche vor dem Start des Pilotprojekts: Senden einer ersten Kommunikation an Pilotbenutzer.
- Tag 1: Senden einer Anstoßkommunikation an Pilotbenutzer.
- Tag 7: Halten Sie die erste wöchentliche Projektteampunkt-Besprechung ab.
- Tag 14: Senden Sie Die Kommunikation zwischen den Piloten an Ihre Pilotbenutzer, halten Sie eine wöchentliche Projektteam-Prüfpunkt-Besprechung ab.
- Tag 21: Halten Sie eine wöchentliche Projektteam-Prüfpunkt-Besprechung ab.
- Tag 30: Senden der endgültigen Kommunikation an Die Pilotbenutzer.
- Tage 31 bis 45: Bewerten Sie die Pilotergebnisse, und planen Sie die nächsten Schritte.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Bewerten von Lernergebnissen und Auswerten Ihres Go-Forward-Plans

Nach Abschluss des Pilotprojekts ist es an der Zeit, alle Feedbackumfragen, endgültigen Netzwerkstatistiken und Supporttickets für die Analyse für Ihre Ziele zu sammeln und zu bestimmen, ob Sie Ihren Go-Forward-Plan implementieren. Möglicherweise stellen Sie fest, dass Ihre Organisation für eine umfassende Bereitstellung bereit ist, oder Sie möchten den Pilot auf mehr Benutzer erweitern, oder Sie möchten den Pilot zu einem späteren Zeitpunkt erneut aufarbeiten, nachdem alle von Ihnen erkannten Bedenken abgemildert wurden. Denken Sie daran, dass Ihr Pilotprojekt eine hervorragende Möglichkeit ist, technische Ergebnisse und Benutzerergebnisse in einer kontrollierten _Umgebung vorherzusagen._ denken Sie daran, zu schnell voran zu springen.

Wenn Ihre Ergebnisse angeben:

- **Ihre Pilotziele (z.** B. Benutzerzufriedenheit und Netzwerkqualität) wurden erreicht. Sie sollten bereit sein, mit der nächsten Phase des Rollouts fortzufahren. Abhängig von den Zielen Ihres Projekts kann dies eine der folgenden Sein:
  - Erweitern des Pilotprojekts auf weitere Teilnehmer
  - [Aktivieren von Teams neben Skype for Business **(Inselmodus)** für einige oder die ganze Organisation](./setting-your-coexistence-and-upgrade-settings.md)
  - [Upgrade von Benutzern von Skype for Business auf Teams **(Nur** Teams-Modus) für einige oder die ganze Organisation](./setting-your-coexistence-and-upgrade-settings.md)
- **Ihr Pilot hat** nicht die von Ihnen gewünschten Ergebnisse (z. B. Benutzerzufriedenheit und Netzwerkqualität) erzielt, nimmt sich Zeit, um die entsprechenden Anpassungen an Ihrem Plan zu treffen und den Pilot erneut zu sehen.

> [!Tip]
> Enlist your pilot participants as peer champions to help evangelize and onboard new users to Teams. Peer Champions können ganz einfach mit anderen Benutzern in Verbindung stehen, ihre eigenen Erfahrungen und Erfahrungen teilen und ihren Kollegen Unterstützung und Anleitung anbieten. Erfahren Sie mehr über [Champions](https://go.microsoft.com/fwlink/?linkid=859068) und deren Verwendung innerhalb Ihres eigenen Rollouts.