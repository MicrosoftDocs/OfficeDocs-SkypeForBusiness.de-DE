---
title: Führen Sie ein Benutzerpiloting durch, um auszuwerten und zu testen, Microsoft Teams Benutzer in Ihrer Organisation funktionieren.
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Anleitungen zum Starten Microsoft Teams Pilotprojekts, um alle Möglichkeiten zu Teams, die Ihr Unternehmen bieten kann, während Sie die Skype for Business
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
ms.openlocfilehash: fe1cf351bb5d3d4a950b818505a8e5d93fa7ab27
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282092"
---
# <a name="conduct-a-user-pilot"></a>Durchführen eines Benutzerpilotprojekts

![Upgrade-Wegdiagramm mit Hervorhebung von Bereitstellung und Implementierung](media/upgrade-banner-deployment.png "Phasen des Upgradewegs, mit Betonung auf der Bereitstellungs- und Implementierungsphase")

Dieser Artikel ist Teil der Bereitstellungs- und Implementierungsphase Ihres Upgradewegs und bietet Einblicke in die Durchführung eines effektiven Pilotprojekts. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)
- [Vertrautmachen mit der Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Vorbereitet auf Ihre Umgebung](./upgrade-prepare-environment.md)
- [Vorbereitung Ihrer Organisation](./upgrade-prepare-organization.md)

Durch die Bereitstellung neuer Technologien kann Ihre Organisation Geschäftswerte wie Kosteneinsparungen, Sicherheitskonformität, Mitarbeiterzufriedenheit und betriebliche Effizienz erreichen, sie kann sich aber auch auf die Produktivität Ihrer Benutzer und die Organisationsinfrastruktur (Ihr Netzwerk) auswirken. Führen Sie ein formelles Benutzerpiloting durch, bevor Sie neue Technologien in Der gesamten Organisation aktivieren. Genau wie Sie einen kleinen Farbpatches auf eine Wand malen, bevor Sie den ganzen Raum zeichnen, würden Sie eine breite Einführung in einem kleineren Maßstab testen, indem Sie ein Pilotprojekt durchführen, um die technische und Benutzerbereitschaft zu überprüfen, Probleme zu identifizieren und zu entschärfen und eine erfolgreiche organisationsweite Implementierung zu gewährleisten.

Um realistischere Ergebnisse zu erzielen, sollte das Pilotprojekt reale Benutzer umfassen, die Kommunikation und Zusammenarbeit imitieren und sowohl die technischen Als auch die Benutzererfahrungen überprüfen. Unabhängig davon, ob Ihre Organisation erwägt, Skype for Business und Teams nebeneinander zu führen, in Zukunft auf Teams zu aktualisieren oder neue Funktionen wie Anrufe oder Konferenzen bereitzustellen, kann ein Pilotprojekt dabei helfen, den richtigen Weg für Ihre Organisation zu finden. Manchmal wird Phase 1 eines Rollouts in Betracht gezogen. Das ideale Pilotprojekt nutzt die bereits begonnene Vorbereitung und implementiert Ihren definierten Plan mit einer gezielten Gruppe von Benutzern.

| | |
|---|---|
| ![Symbol, das einen Entscheidungspunkt darstellt](media/audio_conferencing_image7.png) <br/>Entscheidungspunkt|<ul><li>Wie verwenden Sie ein Pilotprojekt, um die Projektrichtung zu informieren?</li></ul> |
| ![Ein Symbol, das den nächsten Schritt darstellt](media/audio_conferencing_image9.png)<br/>Nächster Schritt|<ul><li>Verwenden Sie die nachstehenden Anleitungen, um Ihr formelles Pilotprojekt zu entwerfen und auszuführen.</li></ul>|

> [!Tip]
> Verwenden Sie die [Beispiel-Pilotressourcen](https://aka.ms/UpgradeSuccessKit) zum Entwerfen Ihrer Kommunikation, Ihres Testplans und Ihrer Feedback-Umfrage.

## <a name="1-outline-pilot-logistics"></a>1. Gliederung der Pilot logistics

Ein erfolgreiches Pilotprojekt hat Start- und Enddaten definiert und klar definierte [Ziele](upgrade-define-project-scope.md#project-goals) zum Messen des Erfolgs definiert. Diese Ziele sollten dem Umfang des breiteren Projekts entsprechen, wie Sie es bei der Definition Ihres Projektumfangs dokumentiert haben, und werden verwendet, um Ihren Weg nach der Pilotphase zu informieren. [](upgrade-define-project-scope.md) Sie sollten auch sicherstellen, dass Sie die richtigen Projektbeteiligten für die Dauer des Projekts einbezogen haben. Sie sollten ausreichend Zeit für die Ausführung des Pilotprojekts haben und die Auswirkungen einschätzen: Wir empfehlen mindestens 30 Tage.

Beginnen Sie klein, und fügen Sie das Pilotprojekt nach Ihren Anforderungen hinzu – ganz gleich, ob Arbeitsauslastungen oder Features oder zusätzliche Benutzer hinzugefügt werden – und erhalten Sie Zeit für die Bewertung der Ergebnisse und die Anpassung des Pilotprojekts, während Sie iterieren. Sie können sogar nachfolgende Pilotprojekte ausführen, Teams neue Features in der Roadmap veröffentlicht werden.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Auswählen der Pilotteilnehmer und Testen von Szenarien

Eine der wichtigsten Aufgaben bei der Pilotplanung ist eine durchdachte Teilnehmerauswahl. Denken Sie daran Teams Projekt für Teamarbeit optimiert ist. Wählen Sie daher die Pilotteilnehmer nicht nur anhand von Rollen oder Personen aus, sondern auch basierend auf ihren Projekt- und teamübergreifenden Arbeiten. Ein guter Anfang ist es, die Projektbeteiligten und Abteilungsleiter nach echten Projekten zu fragen, die Sie in einer Teams. Ein Beispiel für ein rollenbasiertes Projekt könnte sein, Teams zusammen mit Ihrer Vertriebsorganisation zu verwenden, um sicherzustellen, dass Außendienstmitarbeiter problemlos auf die benötigten Ressourcen zugreifen und Erkenntnisse mit anderen Außendienstmitarbeitern teilen können. Ein Beispiel für projektbasierte Arbeit könnte die Koordinierung einer Produkteinführung mit den Teams für Marketing, Schulung, Öffentlichkeitsarbeit und Veranstaltungsplanung sein. Ganz gleich, welche Szenarien Sie auswählen – das Pilotprojekt sollte sich auf wichtige It-, Schulungs- und Helpdeskmitarbeiter erstrecken, damit Sie die Lösung gründlich überprüfen und gleichzeitig Projektmanagementressourcen vollständig optimieren können.

> [!Tip]
> Achten Sie beim Teams Ihrer Pilotgruppenteilnehmer darauf, die besten Benutzer der Pilotgruppe Skype for Business. Informieren Sie sich mit diesen Benutzern, wie sie Skype for Business heute verwenden, und erstellen Sie dann einen Testplan, um zu überprüfen, ob Teams ihre aktuellen Anforderungen erfüllen kann.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Entwerfen Ihres Testplans und ihrer Feedback-Umfrage

Um eine erfolgreiche Piloterfahrung zu ermöglichen, geben Sie den Teilnehmern klar definierte Aufgaben, die sie ausführen müssen, sowie eine Möglichkeit, mit der sie ihr Feedback teilen können. Gruppieren Sie Aufgaben, um ihren Benutzern reale Szenarien zu bieten und so deren tägliche Aktivitäten zu demonstrieren. Lassen Sie die von Ihnen unter Bewerten der Bereitschaft [zur Organisationsänderung](./upgrade-org-change-readiness.md) definierten Verwendungsfälle Ihren Testplan weiterleiten.

Möglicherweise entscheidet sich Ihre Organisation dafür, alle Funktionen auf einmal zu pilotieren oder einen graduellen Ansatz zu wählen – z. B. zuerst Zusammenarbeit in einem Pilotprojekt, dann Besprechungen, anschließend Chats und Anrufe. Stellen Sie sicher, dass Sie über einen offenen Feedbackkanal verfügen, um den Fortschritt nachverfolgt und die Ergebnisse zu messen. Verwenden einer vordefinierten Umfrage als einfache Möglichkeit zum Erfassen und Bewerten von Pilotergebnissen Der Umfrageentwurf sollte auf den Szenarien und Features in Ihrem Testplan basieren.

## <a name="4-create-your-communications-plan"></a>4. Erstellen Ihres Kommunikationsplans

Es ist für den Erfolg Ihres Pilotprojekts von entscheidender Bedeutung, dass Sie die Pilotteilnehmer darüber informieren, was wann und warum geschieht und was von ihnen erwartet wird. Um die Spannung und maximale Teilnahme zu fördern, sollten Sie zusätzlich zu Links zu Schulung und Support, in dem Benutzer beim Fortschritt des Pilotprojekts zusätzliche Informationen erhalten können, auch Benutzer-Value-Messaging verwenden. Im Folgenden finden Sie einige Beispielressourcen für die ersten Schritte mit Ihrem Pilotkommunikationsplan:

- [Pilotressourcen,](https://aka.ms/UpgradeSuccessKit)einschließlich E-Mail-Vorlagen und Fragen zur Feedback-Umfrage
- [Wechseln Sie Teams der Skype for Business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), einem Schnellstarthandbuch, das Benutzern Skype for Business ersten Schritte mit Teams

## <a name="5-conduct-your-pilot"></a>5. Durchführen des Pilotprojekts

Sobald die Logistik bereit ist, können Sie mit dem Pilotprojekt beginnen. Die Durchführung des Pilotprojekts umfasst die Kommunikation mit den Benutzern, die Überwachung Des Netzwerks und die Nutzung, um sicherzustellen, dass Ihre Netzwerkleistung und Anrufqualität fehlerfrei bleiben, das Sammeln von Feedback von den Teilnehmern und das Überprüfen von Helpdesk-Tickets bei Fragen zu Teams.

### <a name="tips-for-pilot-success"></a>Tipps für den Erfolg des Pilotprojekts

Mit den folgenden Tipps können Sie den Erfolg Ihres Pilotprojekts sicherstellen:

- Stellen Sie vor dem Starten des Pilotprojekts sicher, dass alle Pilotteilnehmer für den geeigneten [Koexistenzmodus] aktiviert sind.
- ( https://aka.ms/SkypeToTeams-SetCoexistence) die Sie überprüfen möchten.
- Treffen Sie sich während des gesamten Pilotprojekts wöchentlich mit den Projektbeteiligten, um Das Feedback der Benutzer, Nutzungsdaten, Netzwerkdaten und Helpdesk-Tickets zu überprüfen, um sicherzustellen, dass das Pilotprojekt reibungslos ausgeführt wird. Nehmen Sie nach Bedarf Anpassungen vor.

### <a name="suggested-timeline"></a>Vorgeschlagene Zeitachse

Hier ist eine vorgeschlagene Zeitachse für ein 30-Tage-Pilotprojekt:

- Eine Woche vor dem Pilotstart: Erste Kommunikation an Pilotbenutzer senden.
- Tag 1: Senden von Kick-off-Kommunikation an Pilotbenutzer.
- Tag 7: Halten Sie die erste wöchentliche Besprechung des Projektteams-Prüfpunkts ab.
- Tag 14: Senden Sie Mid-Point Communication an die Pilotbenutzer, und halten Sie eine wöchentliche Besprechung mit dem Projektteam-Prüfpunkt ab.
- Tag 21: Wöchentliche Besprechung des Projektteams-Prüfpunkts.
- Tag 30: Senden der endgültigen Kommunikation an die Pilotbenutzer.
- Tage 31-45: Bewerten der Pilotergebnisse und Planen der nächsten Schritte.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Bewerten von Lernergebnissen und Auswerten Ihres Go-Forward-Plans

Nach Abschluss des Pilotprojekts ist es an der Zeit, alle Feedback-Umfragen, endgültige Netzwerkstatistiken und Supporttickets für die Analyse zu Ihren Zielen zu sammeln und zu bestimmen, ob Sie Ihren Go-Forward-Plan implementieren werden. Möglicherweise stellen Sie fest, dass Ihre Organisation für eine umfassende Bereitstellung bereit ist, oder Sie möchten das Pilotprojekt auf mehr Benutzer ausdämmen, oder Sie möchten das Pilotprojekt zu einem späteren Zeitpunkt erneut aufarbeiten, nachdem alle von Ihnen erkannten Bedenken gemildert wurden. Denken Sie daran, dass das Pilotprojekt eine hervorragende Möglichkeit ist, technische Ergebnisse und Benutzerergebnisse in einer kontrollierten _Umgebung vorherzusagen._ denken Sie daran, zu schnell weiterzukommen.

Die Ergebnisse geben an:

- **Ihre Pilotziele (z.** B. Benutzerzufriedenheit und Netzwerkqualität) wurden erreicht, sollten Sie bereit sein, mit der nächsten Phase Ihrer Einführung fortzufahren. Je nach den Zielen Ihres Projekts kann dies eines der folgenden sein:
  - Erweitern des Pilotprojekts auf weitere Teilnehmer
  - [Aktivieren Teams neben Skype for Business (**Islands-Modus)** für einige oder die ganze Organisation](./setting-your-coexistence-and-upgrade-settings.md)
  - [Aktualisieren von Benutzern von Skype for Business auf Teams **(** nur Teams) für einige oder die ganze Organisation](./setting-your-coexistence-and-upgrade-settings.md)
- **Ihr Pilotprojekt hat nicht** die von Ihnen gewünschten Ergebnisse erzielt (z. B. die Zufriedenheit der Benutzer und die Netzwerkqualität), nehmen Sie sich Zeit, um den Plan entsprechend zu anpassen und das Pilotprojekt erneut zu sehen.

> [!Tip]
> Benennen Sie Ihre Pilotteilnehmer als Peer-Experten ein, um neue Benutzer zu ihrer Unterstützung zu Teams. Peer-Experten können sich problemlos mit anderen Benutzern in Verbindung stellen, ihre eigenen Erfahrungen und Lernergebnisse teilen und ihren Kollegen Support und Anleitung bieten. Erfahren Sie mehr [über Champions](https://go.microsoft.com/fwlink/?linkid=859068) und wie Sie diese in Ihrem eigenen Rollout verwenden können.