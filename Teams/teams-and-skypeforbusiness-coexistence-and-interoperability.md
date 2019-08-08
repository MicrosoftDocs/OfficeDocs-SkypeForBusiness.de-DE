---
title: Microsoft Teams | Upgrade, Inseln-Modus, Interop-Richtlinie, nur
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Details zu den Koexistenz-Optionen von Skype for Business und Microsoft Teams und zur Interoperabilität zwischen Skype for Business und Teams.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5ba7ae0613bbab87f09a6c290d191d711d583c24
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237528"
---
![Diagramm zum Upgrade von Fahrten mit Hervorhebung der Projekt Definitions Stufe] (media/upgrade-banner-project-definition.png "Phasen der Upgrade-Reise mit dem Schwerpunkt auf der Projekt Definitions Stufe")

Dieser Artikel ist Teil der Projekt Definitionsphase Ihres Upgrade-Vorgangs, einer Aktivität, die Sie nach dem Erstellen einer Sponsoring-Koalition und eines Projektteams abgeschlossen haben, und definieren Sie den Umfang, die Ziele und die Vision für Ihr Projekt. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ihre Projekt Beteiligten wurden eingetragen](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Grundlegendes zu Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität

Wenn Ihre Organisation Skype for Business heute verwendet und Sie mit der Nutzung von Teams zusammen mit Skype for Business beginnen – oder wenn Sie mit dem Upgrade auf Teams beginnen – ist es wichtig zu verstehen, wie die beiden Anwendungen koexistieren, wann und wie Sie zusammenarbeiten und wie Sie verwaltet werden. die Migration der Benutzer bis hin zu ihrem eventuellen Upgrade von Skype for Business zu Teams.

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über [Koexistenz und Interoperabilität](https://aka.ms/teams-upgrade-coexistence-interop)zu erfahren.
>
> Darüber hinaus können Sie an interaktiven Workshops teilnehmen, in denen wir Anleitungen, bewährte Methoden und Ressourcen austauschen, die für die Planung und Implementierung von Upgrades entwickelt wurden.
>
> Nehmen Sie zuerst an der [Planung Ihrer Upgrade](https://aka.ms/SkypeToTeamsPlanning) -Sitzung Teil, bevor Sie beginnen.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Koexistenz von Teams und Skype for Business

Zusätzlich zu den Funktionen für die Zusammenarbeit bietet Teams Chat-, Anruf-und Besprechungsfunktionen. Je nachdem, wie Sie die Bereitstellung von Teams auswählen, überlappen sich diese Funktionen möglicherweise mit den Funktionen, die Skype for Business für einen bestimmten Benutzer bereitgestellt hat. Der Standardmodus besteht darin, Teams zusammen mit Skype for Business mit den überlappenden Funktionen auszuführen. einem Benutzer kann jedoch einer von mehreren Koexistenzmodus zugewiesen werden, um sicherzustellen, dass diese Funktionen für diesen Benutzer nicht überlappen (in diesem Fall ist die Interoperabilität zwischen Teams und Skype for Business verfügbar).

Wir empfehlen, dass Sie die unten besprochenen koexistenzarten überprüfen, um zu ermitteln, welcher Pfad für Ihre Organisation richtig ist.

> [!Important]
> Das Einführen neuer Technologien oder das vornehmen von Änderungen an Ihrer vorhandenen, vertrauten Skype for Business-Umgebung und die Bereitstellung hervorragender neuer geschäftlicher Vorteile können für die Benutzer störend sein. Nehmen Sie sich Zeit, um die Benutzer Bereitschaft zu bewerten und einen Kommunikations-und Schulungsplan zu implementieren, bevor Sie die in diesem Artikel beschriebenen Änderungen implementieren. Darüber hinaus empfehlen wir Ihnen, Ihren Plan mit einer ausgewählten Gruppe von Benutzern zu pilotieren, bevor Sie ihn in Ihrer Organisation implementieren.

### <a name="islands-mode"></a>Modus "Inseln"

Standardmäßig können Benutzer Teams neben Skype for Business als zwei separate Lösungen ausführen, die ähnliche und überlappende Funktionen wie Anwesenheit, Chat, Anrufe und Besprechungen bereitstellen. Benutzer von Teams können auch die neuen Funktionen für die Zusammenarbeit wie Teams und Kanäle, den Zugriff auf Dateien in Office 365 und Anwendungen nutzen.

In diesem Koexistenzmodus mit dem Namen " **Inseln**" fungiert jede Clientanwendung als separate Insel. Skype for Business kommuniziert mit Skype for Business und Teams. Benutzer führen beide Clients zu allen Zeiten aus und können in dem Client, von dem aus die Kommunikation initiiert wurde, nativ kommunizieren. Daher ist die Interoperabilität im **Inseln** -Modus nicht erforderlich.

Um eine verwirrende oder rückläufige Skype for Business-Erfahrung zu vermeiden, werden externe (Verbund-) Kommunikationen, PSTN-Sprachdienste und Sprachanwendungen, Office-Integration und verschiedene andere Integrationen weiterhin von Skype for Business gehandhabt.

> [!Important]
> Im Modus " **Inseln** " werden alle Nachrichten von Verbundbenutzern (Personen außerhalb Ihrer Organisation) an Skype for Business ausgeliefert. Nach dem Wechsel in den Modus **nur für Teams** werden alle Nachrichten von außerhalb Ihrer Organisation an Teams übermittelt.

> [!Tip]
> Der empfohlene Pfad für Skype for Business Online-Kunden ist es, mit dem standardmäßigen **Inseln** -Modus zu beginnen, die Sättigung der Teams in der Organisation zu steuern und dann schnell in den Modus " **nur Teams** " zu wechseln. Lokale und Hybrid Kunden können davon profitieren, wenn Sie den **Skype for Business-Modus für die Zusammenarbeit mit Teams** als Ausgangspunkt und nicht als Inseln bereitstellen und von dort aus zu **Skype for Business mit Teamarbeits-und Besprechungs** Modus wechseln. Falls zutreffend, und nur im Modus " **nur für Teams** ", wenn die Organisation bereit ist, Teams zu übernehmen.

### <a name="skype-for-business-only"></a>Nur Skype for Business

In diesem Koexistenzmodus verbleiben die Benutzer in Skype for Business – nicht in Teams – für Chat-, Besprechungs-und Anruffunktionen, und Sie verwenden keine Teams für Teams und Kanäle. Dieser Modus steht heute zur Verfügung. in der aktuellen Implementierung werden jedoch Teams und Kanäle nicht automatisch für den Benutzer deaktiviert. Dies kann durch Verwenden der APP-Berechtigungsrichtlinie zum Ausblenden von Teams und Kanälen erreicht werden.

### <a name="teams-only"></a>Nur für Teams

Ein **nur Teams** -Benutzer (auch als ** "aktualisierter Benutzer" bezeichnet) hat Zugriff auf alle Funktionen in Microsoft Teams. Sie können den Skype for Business-Client beibehalten, um an Besprechungen in Skype for Business teilzunehmen, die von nicht aktualisierten Benutzern oder externen Personen organisiert wurden. Ein aktualisierter Benutzer kann weiterhin mit anderen Benutzern in der Organisation kommunizieren, die weiterhin Skype for Business verwenden, indem die Interoperabilitätsfunktionen zwischen Teams und Skype for Business verwendet werden (sofern sich diese Skype for Business-Benutzer nicht im Modus "Inseln" befinden) ; ein aktualisierter Benutzer kann jedoch keinen Skype for Business-Chat,-Anruf oder eine Besprechung initiieren.

Sobald Ihre Organisation für einige oder alle Benutzer bereit ist, Teams als einziges Kommunikations-und Zusammenarbeits Tool zu verwenden, können Sie diese Benutzer in den Modus **nur für Teams** aktualisieren. Wenn Sie den Modus "Inseln" aktualisieren, empfehlen wir, dass Sie die Einführung von Teams zunächst in Ihrer Organisation übersättigen, bevor Sie mit dem Upgrade beginnen. Dies vermeidet fehlerhafte Kommunikationsszenarien, da der Inseln-Modus keine Interoperabilität bietet.

Weitere Überlegungen zum Wechseln in den Modus nur für Teams finden Sie unter [Überlegungen zum nur für Teams](teams-only-mode-considerations.md).

Screenshot ![der Bestätigungsmeldung für Teams] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business-Client, der in einem speziellen Modus ausgeführt wird, nachdem der Benutzer als nur-Team-Benutzer aktualisiert wurde")

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business mit Zusammenarbeit in Teams

Verwenden Sie diesen Modus, um Teams in Ihrer Umgebung einzuführen, während Sie weiterhin Ihre vorhandene Investition in Skype for Business nutzen. In diesem Modus verlassen Sie Skype for Business unverändert für Chat-, Anruf-und Besprechungsfunktionen, und Sie fügen Teamzusammenarbeitsfunktionen hinzu – Teams und Kanäle, Zugriff auf Dateien in Office 365 und Anwendungen. Die Kommunikationsfunktionen von Teams – private Chats, Anrufe und Planungs Besprechungen – sind in diesem Modus standardmäßig deaktiviert. Organisationen mit einem Ausgangspunkt von Skype for Business Server lokal oder Hybrid sollten diesen Modus als Alternative zum Modus "Inseln" berücksichtigen, wenn Sie Ihren Benutzern Interoperabilität und Vorhersagbarkeit für Ihre Kommunikation geben möchten.

### <a name="skype-for-business-with-teams-collaboration-and-meetings"></a>Skype for Business mit Zusammenarbeit und Besprechungen in Teams

Verwenden Sie diesen Koexistenzmodus, um die Verfügbarkeit von Teams-Besprechungsfunktionen in Ihrer Organisation zusätzlich zu den Zusammenarbeitsfunktionen zu beschleunigen, die es Ihren Benutzern ermöglichen, die Vorteile der überlegenen Teams für Besprechungen zu nutzen – hervorragende Qualität, innovative Funktionen wie Transkription und Übersetzung oder Hintergrund Unschärfe sowie hervorragende Benutzerfreundlichkeit auf allen Plattformen, einschließlich mobiler Geräte und Browser.

Zusammen mit der Verwendung von Teams für Teams und auf Kanälen basierende Konversationen in diesem Modus verwenden die Benutzer Teams, um Ihre Besprechungen zu planen und durchzuführen. Privater Chat und Anrufe verbleiben in Skype for Business. Teams und Skype for Business profitieren von einer Reihe von "besser kombinierten" Funktionen wie Anwesenheits Abstimmung, automatisches halten/aufhalten und Unterstützung von HID-Geräten in beiden Anwendungen. 

Dieser Koexistenzmodus eignet sich besonders für Benutzer in Skype for Business-Bereitstellungen mit Enterprise-VoIP, die sich wahrscheinlich einige Zeit dauern, bis Sie auf Teams aktualisiert werden und so schnell wie möglich von den überlegenen Teams-Besprechungen profitieren möchten.

> [!Note]
> Wenn Sie in bestimmten Koexistenzmodus bereitgestellt werden, können Teams und Skype for Business zusammen [arbeiten](#interoperability-of-teams-and-skype-for-business)und es Benutzern ermöglichen, mit Ihnen zu chatten und sich gegenseitig anzurufen, und sicherzustellen, dass die Kommunikation während der Upgrade-Reise zu Teams in Ihrer Organisation flüssig bleibt. Koexistenzmodus steuert die Interoperabilität. Der Koexistenzmodus des Empfängers bestimmt, ob die Interoperabilität verfügbar ist. Wenn sich der Empfänger beispielsweise in einem Modus befindet, in dem Chat nur in einem Client verfügbar ist (sagen wir, Teams), ist Chat-Interoperabilität in der Regel verfügbar, falls der Initiator den anderen Client (in diesem Fall Skype for Business) verwendet, um den Chat zu starten. Wenn sich der Receiver hingegen in einem Modus befindet, in dem Chats in beiden Clients verfügbar sind (Inseln-Modus), steht die Interoperabilität für den Chat nicht zur Verfügung. Die Nachricht wird vom Empfänger in dem gleichen Client empfangen, in dem der Initiator den Chat gestartet hat. Daher erfordert die ordnungsgemäße Kommunikation im Modus "Inseln" eine Sättigung der Teams. Das bedeutet, dass alle Benutzer beide Clients aktiv verwenden und überwachen.

> [!TIP]
> Wenn Sie den empfohlenen Aktualisierungsmodus basierend auf den Funktionen ermitteln möchten, die Sie in Microsoft Teams aktivieren möchten, während Skype for Business noch verwendet wird, nutzen Sie den [Upgrade-Assistenten von Skype to Teams](https://aka.ms/SkypeToTeamsWizard).

Weitere Informationen zu den Modi für Koexistenz, Voraussetzungen und Verwaltung finden Sie unter [Leitfaden zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://aka.ms/SkypeToTeams-Interop) , und [die Einstellungen für Koexistenz und Upgrade festlegen](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Entscheidungspunkt|<ul><li>Welche Koexistenzmodus (en) passt am besten zu den Anforderungen Ihrer Organisation und der Benutzer?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Nächster Schritt|<ul><li>Wählen Sie den besten Ansatz für Ihre Upgrade-Reise aus.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilität von Teams und Skype for Business

Interoperabilität ist die Möglichkeit für Teams und Skype for Business-Benutzer in derselben Organisation, über Teams und Skype for Business hinweg zu kommunizieren.

### <a name="native-interop-and-interop-escalation"></a>Systemeigene Interop-und Interop-Eskalation

Es gibt zwei Arten von Interop-Erfahrungen: systemeigene und Interop-Eskalation.

- Eine _systemeigene Interop_ -Oberfläche tritt in dem Client auf, den der Benutzer zurzeit verwendet. Ein Nutzer befindet sich im Skype for Business-Client, der andere in Teams. Eine native Interop-Erfahrung führt Sie nicht zu einem anderen Client, um zu kommunizieren, die Benutzer können Ihre Konversation in dem Client durchführen, den Sie zurzeit verwenden. Die nativen Interop-Erfahrungen sind 1:1-Chats und-Anrufe.
- Eine _Interop_ -Eskalations Erfahrung bedeutet, dass der Client im Rahmen der Unterstützung der Benutzer, die eine erweiterte Aktion durchführen (wie etwa das Freigeben des Desktops), die Erstellung einer Besprechung erleichtert, an der Benutzer teilnehmen können, um die Erfahrung in dieser Besprechung fortzusetzen. Die Besprechung wird auf der Plattform des Initiators der Aktion erstellt. Der Benutzer oder die Benutzer, die nicht auf dieser Plattform sind, erhalten einen Link zur Besprechungsteilnahme. Wenn Sie auf diesen Link klicken, werden Sie je nach Konfiguration in einem kompatiblen Client (Browser, Web App oder vollständiger Client) der Besprechung beigetreten. Die Interop-Eskalation von Skype for Business erfordert einen kürzlichen Client. Die Interop-Eskalation von Teams wird in Kürze folgen.

### <a name="native-interop-experiences"></a>Systemeigene Interop-Erfahrungen

Je nachdem, welche Koexistenzmodus Benutzern zugewiesen ist (wie oben beschrieben), stehen die folgenden systemeigenen Interop-Erfahrungen zur Verfügung:

- Skype for Business-Benutzer können mit Teams-Benutzern einzeln chatten und umgekehrt. Ein Interop-Chat muss ein Interop-Gateway durchlaufen, das Teil der Cloud-Dienste von Teams ist (und daher nur Online vorhanden ist). Interop-Chats sind nur-Text: Rich-Text und Emoticons werden nicht unterstützt. Benutzer in Teams und in Skype for Business werden benachrichtigt, dass es sich um eine Interop-Unterhaltung handelt.

    Screenshot ![des Interop-Chats in Microsoft Teams] (media/Interop_chat_experience_from_Teams.png "Interop-Chat-Erfahrung von Teams")

- Skype for Business-Benutzer können Einzel-sprach-und Videoanrufe an Teams-Nutzer tätigen und umgekehrt.

    Screenshot ![der Benutzeroberfläche für Interop-Anrufe in Teams] (media/Interop_calling_experience_from_Teams.png "Interoperabilitäts-Anruf Erfahrung von Teams")

> [!Important]
> Interoperabilitäts Erfahrungen mit einer lokalen Bereitstellung von Skype for Business setzen voraus, dass sich die lokale Umgebung im Hybrid Modus mit Office 365 Skype for Business befindet. Ausführliche Informationen finden Sie unter [Leitfaden zur Migration und Interoperabilität](https://aka.ms/SkypeToTeams-Interop).

Diese Interoperabilitätsfunktionen stehen für und zwischen Benutzern zur Verfügung, denen einer der folgenden Koexistenzmodus zugewiesen ist: **Skype for Business mit Teamzusammenarbeit**, **Skype for Business mit Teamzusammenarbeit und**-Besprechungen, **Skype für Nur für Unternehmen**oder **nur für Teams**. Im Modus "Inseln" gibt es keine Interoperabilität für Benutzer.

### <a name="native-interop-experience-limitations"></a>Einschränkungen der systemeigenen Interop-Umgebung

Einige Features stehen für den Interop-Chat und die Interop-Anruffunktion zwischen Teams und Skype for Business nicht zur Verfügung:

- Abschriften, Rich-Text und der vollständige Emoticon-Satz werden weder von Teams noch von Skype for Business unterstützt. Andere systemeigene Features des Felds zum Verfassen in Teams-Chats werden nicht unterstützt.
- Die Bildschirmübertragung (Desktop-oder App-Freigabe) zwischen Teams und Skype for Business wird nicht unterstützt.
- Gruppen-Chats (mehr Parteien Unterhaltungen) in Teams können nur Teilnehmer einbeziehen, die Teams verwenden.
- Chat Unterhaltungen mit mehreren Teilnehmern (Gruppen-Chats) in Skype for Business können nur Teilnehmer einbeziehen, die Skype for Business nutzen.
- Die Eskalation eines laufenden Peer-to-Peer-sprach-oder Videoanrufs zu einem mehr Parteien-Anruf mit Teams und Skype for Business-Benutzern wird nicht unterstützt.
- Die Dateiübertragung für zwei-Parteien-Chats oder Dateianlagen in Gruppen-Chats, von Teams zu Skype for Business – und umgekehrt – werden nicht unterstützt.
- Es gibt keine Interoperabilität mit dem beständigen Chat von Skype for Business.

Für alle diese Einschränkungen (mit Ausnahme des beständigen Chats) besteht eine mögliche Problemumgehung darin, dass ein Benutzer eine Besprechung startet und den anderen Benutzer zur Teilnahme einlädt. Diese Problemumgehung ist die Grundlage für die Interop-Eskalation.

Nachdem Sie diesen Artikel überprüft haben, lesen Sie [Auswählen Ihrer Upgrade-Reise](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [Migrations-und Interoperabilitäts Anleitung](https://aka.ms/SkypeToTeams-Interop), [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md)und [Festlegen ihrer Koexistenz-und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) für die Implementierung. Details.

## <a name="related-links"></a>Verwandte Links

[Video: Verwalten der Koexistenz und Interoperabilität zwischen SFB und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
