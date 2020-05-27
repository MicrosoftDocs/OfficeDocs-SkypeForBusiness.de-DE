---
title: Interoperabilität zwischen Skype for Business und Microsoft Teams
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
f1.keywords:
- CSH
ms.custom: seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e34bc0b15186afdbbe33edb154f02b4decdc3b12
ms.sourcegitcommit: 47637ed816b471fe689e7bdac27b73e6efced60c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44374303"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Grundlegendes zu Microsoft Teams und Skype for Business-Koexistenz und-Interoperabilität

![Diagramm zum Upgrade von Fahrten mit Hervorhebung der Projekt Definitions Stufe](media/upgrade-banner-project-definition.png "Phasen der Upgrade-Reise mit dem Schwerpunkt auf der Projekt Definitions Stufe")

Dieser Artikel ist Teil der Projekt Definitionsphase Ihres Upgrade-Vorgangs, einer Aktivität, die Sie nach dem Erstellen einer Sponsoring-Koalition und eines Projektteams abgeschlossen haben, und definieren Sie den Umfang, die Ziele und die Vision für Ihr Projekt. Bevor Sie fortfahren, bestätigen Sie, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)

Wenn Ihre Organisation Skype for Business heute verwendet und Sie mit der Nutzung von Teams zusammen mit Skype for Business beginnen – oder wenn Sie mit dem Upgrade auf Teams beginnen – ist es wichtig zu verstehen, wie die beiden Anwendungen koexistieren, wann und wie Sie zusammenarbeiten, und wie Sie die Migration der Benutzer bis zu einem späteren Upgrade von Skype for Business auf Teams verwalten können.

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über [Koexistenz und Interoperabilität](https://aka.ms/teams-upgrade-coexistence-interop)zu erfahren.
>
> Darüber hinaus können Sie an interaktiven Workshops teilnehmen, in denen wir Anleitungen, bewährte Methoden und Ressourcen austauschen, die für die Planung und Implementierung von Upgrades entwickelt wurden.
>
> Nehmen Sie zuerst an der [Planung Ihrer Upgrade](https://aka.ms/SkypeToTeamsPlanning) -Sitzung Teil, bevor Sie beginnen.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Koexistenz von Teams und Skype for Business

Zusätzlich zu den Funktionen für die Zusammenarbeit bietet Teams Chat-, Anruf-und Besprechungsfunktionen. Je nachdem, wie Sie die Bereitstellung von Teams auswählen, überlappen sich diese Funktionen möglicherweise mit den Funktionen, die Skype for Business für einen bestimmten Benutzer bereitgestellt hat. Der Standardmodus besteht darin, Teams zusammen mit Skype for Business mit den überlappenden Funktionen auszuführen. einem Benutzer kann jedoch einer von mehreren Koexistenzmodus (auch als Upgrademodus bezeichnet) zugewiesen werden, um sicherzustellen, dass diese Funktionen für diesen Benutzer nicht überlappen (in diesem Fall ist die Interoperabilität zwischen Teams und Skype for Business verfügbar). Wenn Sie beispielsweise über signifikante Skype for Business Server-Ressourcen mit einer komplexen Enterprise-VoIP-Bereitstellung verfügen, Ihre Benutzer aber so schnell wie möglich an modernen Besprechungen teilhaben lassen möchten, sollten Sie [Besprechungen zuerst](meetings-first.md) als alternativen Pfad bewerten.

Wir empfehlen, die folgenden koexistenzarten zu überprüfen, um zu ermitteln, welcher Pfad für Ihre Organisation richtig ist.

> [!Important]
> Das Einführen neuer Technologien oder das vornehmen von Änderungen an Ihrer vorhandenen, vertrauten Skype for Business-Umgebung und die Bereitstellung hervorragender neuer geschäftlicher Vorteile können für die Benutzer störend sein. Nehmen Sie sich Zeit, um die Benutzer Bereitschaft zu bewerten und einen Kommunikations-und Schulungsplan zu implementieren, bevor Sie die in diesem Artikel beschriebenen Änderungen implementieren. Darüber hinaus empfehlen wir Ihnen, Ihren Plan mit einer ausgewählten Gruppe von Benutzern zu pilotieren, bevor Sie ihn in Ihrer Organisation implementieren.

### <a name="islands-mode"></a>Modus "Inseln"

Standardmäßig können Benutzer Teams neben Skype for Business als zwei separate Lösungen ausführen, die ähnliche und überlappende Funktionen wie Anwesenheit, Chat, Anrufe und Besprechungen bereitstellen. Benutzer von Teams können auch die neuen Funktionen für die Zusammenarbeit wie Teams und Kanäle, den Zugriff auf Dateien in Office 365 und Anwendungen nutzen.

In diesem Koexistenzmodus mit dem Namen " **Inseln**" fungiert jede Clientanwendung als separate Insel. Skype for Business kommuniziert mit Skype for Business und Teams. Es wird davon ausgegangen, dass Benutzer beide Clients zu allen Zeiten ausführen und in dem Client, von dem die Kommunikation initiiert wurde, nativ kommunizieren können. Daher ist die Interoperabilität im **Inseln** -Modus nicht erforderlich.

Um eine verwirrende oder rückläufige Skype for Business-Erfahrung zu vermeiden, werden externe (Verbund-) Kommunikationen, PSTN-Sprachdienste und Sprachanwendungen, Office-Integration, HID-Steuerungen für USB-Geräte und mehrere andere Integrationen weiterhin von Skype for Business gehandhabt und stehen in Teams im **Inseln** -Modus nicht zur Verfügung. Das Telefon System wird in Teams im Modus " **Inseln** " nicht unterstützt. in diesem Modus ist der einzige Enterprise-VoIP-Client Skype for Business.

> [!Important]
> Im Modus " **Inseln** " werden alle Nachrichten und Anrufe von Verbundbenutzern (Personen außerhalb Ihrer Organisation) an Skype for Business ausgeliefert. Nach dem Upgrade auf den Modus **nur für Teams** werden alle Nachrichten und Anrufe von außerhalb Ihrer Organisation an Teams übermittelt.

> [!Tip]
> Der empfohlene Pfad für Skype for Business Online-Kunden ist es, mit dem standardmäßigen **Inseln** -Modus zu beginnen, die Sättigung der Teams in der Organisation zu steuern und dann schnell in den Modus " **nur Teams** " zu wechseln. Lokale und hybride Kunden, besonders komplexe, können davon profitieren, wenn Sie den **Skype for Business-Modus für Teams Zusammenarbeit** als Ausgangspunkt und nicht als **Inseln** -Modus bereitstellen und von dort aus zu **Skype for Business mit Teamarbeits-und Besprechungs** Modus (also Besprechungen zuerst), falls erforderlich, und dem Modus " **nur Teams** " wechseln, wenn die Organisation bereit ist, Teams zu

### <a name="skype-for-business-only"></a>Nur Skype for Business

In diesem Koexistenzmodus verbleiben die Benutzer in Skype for Business – nicht in Teams – für Chat-, Besprechungs-und Anruffunktionen, und Sie verwenden keine Teams für Teams und Kanäle. Dieser Modus steht heute zur Verfügung. in der aktuellen Implementierung werden jedoch Teams und Kanäle nicht automatisch für den Benutzer deaktiviert. Dies kann durch Verwenden der APP-Berechtigungsrichtlinie zum Ausblenden von Teams und Kanälen erreicht werden.

Dieser Modus kann vor dem Starten einer verwalteten Bereitstellung von Teams verwendet werden, um zu verhindern, dass Benutzer Teams vor dem Aufbau der Bereitschaft verwenden, oder als Möglichkeit, die authentifizierte Teilnahme an Teams-Besprechungen für Skype for Business-Benutzer zu aktivieren, vorausgesetzt, die Benutzer sind für Teams lizenziert.

### <a name="teams-only"></a>Nur für Teams


> [!IMPORTANT]
> Wenn Sie den Skype for Business-Client deinstallieren, nachdem Sie einen Benutzer in den **TeamsOnly**-Modus verschoben haben, funktionieren die Anwesenheitsinformationen in Outlook und anderen Office-Apps nicht mehr. In Microsoft Teams funktionieren die Anwesenheitsinformationen einwandfrei. Problemumgehung: Wenn Sie die Anwesenheitsinformationen in Outlook (und anderen Office-Apps) anzeigen möchten, muss Skype for Business installiert sein, auch wenn Sie Microsoft Teams im **Nur-Teams**-Modus ausführen. Das Problem ist Microsoft bekannt, und es wird gerade an einer Lösung gearbeitet.


Ein **nur Teams** -Benutzer (auch als " *aktualisierter* Benutzer" bezeichnet) hat Zugriff auf alle Funktionen in Microsoft Teams. Sie können den Skype for Business-Client beibehalten, um an Besprechungen in Skype for Business teilzunehmen, die von nicht aktualisierten Benutzern oder externen Personen organisiert wurden. Ein aktualisierter Benutzer kann weiterhin mit anderen Benutzern in der Organisation kommunizieren, die weiterhin Skype for Business verwenden, indem die Interoperabilitätsfunktionen zwischen Teams und Skype for Business verwendet werden (sofern sich diese Skype for Business-Benutzer nicht im Modus " **Inseln** " befinden). Ein aktualisierter Benutzer kann jedoch keinen Skype for Business-Chat,-Anruf oder eine Besprechung initiieren.

Sobald Ihre Organisation für einige oder alle Benutzer bereit ist, Teams als einziges Kommunikations-und Zusammenarbeits Tool zu verwenden, können Sie diese Benutzer in den Modus **nur für Teams** aktualisieren. Wenn Sie den Modus " **Inseln** " aktualisieren, empfehlen wir, dass Sie die Einführung von Teams in Ihrer Organisation zunächst übersättigen, bevor Sie mit dem Upgrade beginnen. Dies vermeidet fehlerhafte Kommunikationsszenarien, da der **Inseln** -Modus keine Interoperabilität bietet.

Im Modus " **nur für Teams** " ist "Teams" die Standard-App für das SIP/Tel-Protokoll. Das bedeutet, dass die Links in der Visitenkarte eines Benutzers in Outlook für Anrufe oder Chats von Teams verarbeitet werden.

Weitere Überlegungen zum Wechseln in den Modus **nur für Teams** finden Sie unter [Überlegungen zum nur für Teams](teams-only-mode-considerations.md).

![Screenshot der Bestätigungsmeldung für Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business-Client, der in einem speziellen Modus ausgeführt wird, nachdem der Benutzer als nur-Team-Benutzer aktualisiert wurde")

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business mit Zusammenarbeit in Teams

Verwenden Sie diesen Modus, um Teams in Ihrer Umgebung einzuführen, während Sie weiterhin Ihre vorhandene Investition in Skype for Business nutzen. In diesem Modus verlassen Sie Skype for Business unverändert für Chat-, Anruf-und Besprechungsfunktionen, und Sie fügen Teamzusammenarbeitsfunktionen hinzu – Teams und Kanäle, Zugriff auf Dateien in Office 365 und Anwendungen. Die Kommunikationsfunktionen von Teams – private Chats, Anrufe und Planungs Besprechungen – sind in diesem Modus standardmäßig deaktiviert.

Organisationen mit einem Ausgangspunkt von Skype for Business Server lokal oder Hybrid sollten diesen Modus als Alternative zum Modus " **Inseln** " berücksichtigen, wenn Sie Ihren Benutzern Interoperabilität und Vorhersagbarkeit für Ihre Kommunikation geben möchten sowie über eine vorhersagbare Zeitachse für Ihr Upgrade auf Teams verfügen (im Gegensatz zu einer Annahme Sättigung im **Inseln** -Modus).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business mit Teamzusammenarbeit und Besprechungen, auch als "Besprechungen" bezeichnet

Verwenden Sie diesen Koexistenzmodus, um die Verfügbarkeit von Teams-Besprechungsfunktionen in Ihrer Organisation zusätzlich zu den Zusammenarbeitsfunktionen zu beschleunigen, die es Ihren Benutzern ermöglichen, die überlegenen Teams für Besprechungen zu nutzen – hervorragende Qualität, innovative Funktionen wie Transkription und Übersetzung oder Hintergrund Unschärfe sowie hervorragende Benutzerfreundlichkeit auf allen Plattformen, einschließlich mobiler Geräte und Browser.

Zusammen mit der Verwendung von Teams für Teams und auf Kanälen basierende Konversationen in diesem Modus verwenden die Benutzer Teams, um Ihre Besprechungen zu planen und durchzuführen. Privater Chat und Anrufe verbleiben in Skype for Business. Teams und Skype for Business profitieren von einer Reihe von "besser kombinierten" Funktionen wie Anwesenheits Abstimmung, automatisches halten/aufhalten und Unterstützung von HID-Geräten in beiden Anwendungen. Beachten Sie, dass es möglich ist, Teams und Kanäle bei Bedarf mithilfe der APP-Berechtigungsrichtlinie zu verbergen.

Dieser Koexistenzmodus eignet sich besonders für Organisationen, die lokale Skype for Business-Bereitstellungen mit Enterprise-VoIP nutzen, die sich wahrscheinlich etwas Zeit für ein Upgrade auf Teams nehmen und so schnell wie möglich von den überlegenen Teams-Besprechungen profitieren möchten.

> [!Note]
> Wenn Sie in einem Koexistenzmodus mit Ausnahme von **Inseln**bereitgestellt werden, können Teams und Skype for Business zusammen [arbeiten](#interoperability-of-teams-and-skype-for-business), sodass die Benutzer mit anderen Personen chatten und sich gegenseitig anrufen können, und sicherstellen, dass die Kommunikation während der Upgrade-Reise zu Teams in ihrer gesamten Organisation flüssig bleibt. Koexistenzmodus steuert die Interoperabilität. Der Koexistenzmodus des Empfängers bestimmt, ob die Interoperabilität verfügbar ist. Wenn sich der Empfänger beispielsweise in einem Modus befindet, in dem Chat nur in einem Client verfügbar ist (sagen wir, Teams), ist Chat-Interoperabilität in der Regel verfügbar, falls der Initiator den anderen Client (in diesem Fall Skype for Business) verwendet, um den Chat zu starten. Wenn sich der Receiver hingegen in dem Modus befindet, in dem Chat in beiden Clients verfügbar ist (Inseln-Modus), steht die Interoperabilität für den Chat nicht zur Verfügung. Die Nachricht wird vom Empfänger in dem gleichen Client empfangen, in dem der Initiator den Chat gestartet hat. Daher erfordert die ordnungsgemäße Kommunikation im Modus " **Inseln** " eine Sättigung der Teams. Das bedeutet, dass alle Benutzer beide Clients aktiv verwenden und überwachen.

> [!TIP]
> Wenn Sie den empfohlenen Aktualisierungsmodus basierend auf den Funktionen ermitteln möchten, die Sie in Microsoft Teams aktivieren möchten, während Skype for Business noch verwendet wird, nutzen Sie den [Upgrade-Assistenten von Skype to Teams](https://aka.ms/SkypeToTeamsWizard).

Weitere Informationen zu den Modi für Koexistenz, Voraussetzungen und Verwaltung finden Sie unter [Leitfaden zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](https://aka.ms/SkypeToTeams-Interop) , und [die Einstellungen für Koexistenz und Upgrade festlegen](https://aka.ms/SkypeToTeams-SetCoexistence).

| | | |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Entscheidungspunkt|<ul><li>Welche Koexistenzmodus (en) passt am besten zu den Anforderungen Ihrer Organisation und der Benutzer?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Nächster Schritt|<ul><li>Wählen Sie den besten Ansatz für Ihre Upgrade-Reise aus.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilität von Teams und Skype for Business

Interoperabilität ist die Möglichkeit für Teams und Skype for Business-Benutzer in derselben Organisation, über Teams und Skype for Business hinweg zu kommunizieren.

Die Interoperabilität unterliegt dem Koexistenzmodus (auch bekannt als Aktualisierungsmodus) des Empfängers. Es gibt keine Interoperabilität, wenn sich der Receiver im **Inseln** -Modus befindet.

### <a name="native-interop-and-interop-escalation"></a>Systemeigene Interop-und Interop-Eskalation

Es gibt zwei Arten von Interop-Erfahrungen: systemeigene und Interop-Eskalation.

- Eine _systemeigene Interop_ -Oberfläche tritt in dem Client auf, den der Benutzer zurzeit verwendet. Ein Nutzer befindet sich im Skype for Business-Client, der andere in Teams. Eine native Interop-Erfahrung führt Sie nicht zu einem anderen Client, um zu kommunizieren, die Benutzer können Ihre Konversation in dem Client durchführen, den Sie zurzeit verwenden. Die nativen Interop-Erfahrungen sind 1:1-Chats und-Anrufe.
- Eine _Interop-Eskalations_ Erfahrung bedeutet, dass der Client im Rahmen der Unterstützung der Benutzer, die eine erweiterte Aktion durchführen (wie etwa das Freigeben des Desktops), die Erstellung einer Besprechung erleichtert, an der Benutzer teilnehmen können, um die Erfahrung in dieser Besprechung fortzusetzen. Die Besprechung wird auf der Plattform des Initiators der Aktion erstellt. Der Benutzer oder die Benutzer, die nicht auf dieser Plattform sind, erhalten einen Link zur Besprechungsteilnahme. Wenn Sie auf diesen Link klicken, werden Sie je nach Konfiguration in einem kompatiblen Client (Browser, Web App oder vollständiger Client) der Besprechung beigetreten. Die Interop-Eskalation von Skype for Business erfordert einen kürzlichen Client. Die Interop-Eskalation von Teams ist jetzt verfügbar. Beide werden in den Interoperabilitätsfunktionen im Mandanten und für die Mandantenübergreifende Kommunikation unterstützt.

### <a name="native-interop-experiences"></a>Systemeigene Interop-Erfahrungen

Je nach den den Benutzern zugewiesenen Koexistenz Modi (wie zuvor beschrieben) sind die folgenden systemeigenen Interop-Erfahrungen verfügbar:

Skype for Business-Benutzer können mit Teams-Benutzern einzeln chatten und umgekehrt. Ein Interop-Chat muss ein Interop-Gateway durchlaufen, das Teil der Cloud-Dienste von Teams ist (und daher nur Online vorhanden ist). Interop-Chats sind nur-Text: Rich-Text und Emoticons werden nicht unterstützt. Benutzer in Teams und in Skype for Business werden benachrichtigt, dass es sich um eine Interop-Unterhaltung handelt.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business-Benutzer können Einzel-sprach-und Videoanrufe an Teams-Nutzer tätigen und umgekehrt.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Interoperabilitäts Erfahrungen mit einer lokalen Bereitstellung von Skype for Business setzen voraus, dass sich die lokale Umgebung im Hybrid Modus mit Office 365 Skype for Business befindet. Ausführliche Informationen finden Sie unter [Leitfaden zur Migration und Interoperabilität](https://aka.ms/SkypeToTeams-Interop).

Diese Interoperabilitätsfunktionen stehen für und zwischen Benutzern zur Verfügung, denen einer der folgenden Koexistenzmodus zugewiesen ist: **Skype for Business mit Teamzusammenarbeit**, **Skype for Business mit Teamzusammenarbeit und Besprechungen**, **nur Skype for Business**oder nur **Teams**. Im Modus " **Inseln** " gibt es keine Interoperabilität für Benutzer.

### <a name="native-interop-experience-limitations"></a>Einschränkungen der systemeigenen Interop-Umgebung

Aufgrund der Unterschiede bei Protokollen und Technologien ist es nicht möglich, alle Funktionen nativ zu unterstützen. Insbesondere stehen die folgenden Funktionen nicht zur Verfügung:

- Abschriften, Rich-Text und der vollständige Emoticon-Satz werden weder von Teams noch von Skype for Business unterstützt. Andere systemeigene Features des Felds zum Verfassen in Teams-Chats werden nicht unterstützt.
- Bildschirmübertragung (Desktop-oder App-Freigabe) zwischen Teams und Skype for Business wird nicht nativ unterstützt. Sie wird jedoch durch die Interop-Eskalation unterstützt.
- Gruppen-Chats (mehr Parteien Unterhaltungen) in Teams können nur Teilnehmer einbeziehen, die Teams verwenden.
- Chat Unterhaltungen mit mehreren Teilnehmern (Gruppen-Chats) in Skype for Business können nur Teilnehmer einbeziehen, die Skype for Business nutzen. Die Interop-Eskalation an mehrere Teilnehmer ist jedoch über Skype for Business verfügbar.
- Die Eskalation eines laufenden Peer-to-Peer-sprach-oder Videoanrufs zu einem mehr Parteien-Anruf mit Teams und Skype for Business-Benutzern wird nicht unterstützt.
- Die Dateiübertragung für zwei-Parteien-Chats oder Dateianlagen in Gruppen-Chats, von Teams zu Skype for Business – und umgekehrt – werden nicht unterstützt.
- Es gibt keine Interoperabilität mit dem beständigen Chat von Skype for Business.

Für alle diese Einschränkungen (mit Ausnahme des beständigen Chats) besteht eine mögliche Problemumgehung darin, dass ein Benutzer eine Besprechung startet und den anderen Benutzer zur Teilnahme einlädt.

Diese Problemumgehung ist die Grundlage für die Interop-Eskalation. Insbesondere können die Bildschirmübertragung und die Eskalation an mehrteilige Komponenten nicht nativ durchführbar sein, aber Sie werden über die Interop-Eskalation unterstützt.

### <a name="interop-escalation-experiences"></a>Interop-Eskalations Erfahrungen

Die Interop-Eskalation besteht darin, die systemeigenen Interop-Funktionen durch verwaltete Eskalationen zu Besprechungen zu ergänzen. Besprechungen bieten zahlreiche Erfahrungen, die für jeden verfügbar sind, unabhängig davon, welchen Client Sie haben.

Wenn die Interop-Eskalation vom Team Benutzer ausgelöst wird, wird eine Teambesprechung erstellt. Wenn es vom Skype for Business-Benutzer ausgelöst wird, wird eine Skype for Business-Besprechung erstellt. In beiden Fällen ist die erstellte **Besprechung eine Besprechung** , die sich nicht im Kalender des Benutzers widerspiegelt.
 
Die andere Partei erhält den Link "Besprechungsteilnahme" über Interop-Chat und Verknüpfungen, indem Sie auf diesen Link klickt. Wenn der Skype for Business-Benutzer ein Teams-Konto hat und vom Team Benutzer eingeladen wird, wird er an der Besprechung authentifiziert. Andernfalls werden Sie als anonymer Teilnehmer beitreten. Umgekehrt verfügen die Benutzer von Teams fast immer über ein Skype for Business-Konto und einen Skype for Business-Client, den Sie für die Teilnahme an einer Skype for Business-Besprechung als authentifizierter Teilnehmer verwenden können, aber möglicherweise auch als anonymer Teilnehmer beitreten, beispielsweise über die Skype-Besprechungs-app.

Nachdem die Parteien der Besprechung beigetreten sind, können Sie alle in Besprechungen unterstützten Aktivitäten wie Desktop-oder Inhaltsfreigabe, Dateifreigabe oder-Übertragung, Hinzufügen weiterer Teilnehmer usw. durchführen.

#### <a name="interop-escalation-from-skype-for-business"></a>Interop-Eskalation von Skype for Business

Die Interoperabilitäts-und Interop-Eskalation von Skype for Business wurde im 2019-Build des monatlichen C2R vom Juli aktualisiert. Zuvor hatte Skype for Business keine Bewusstheit darüber, dass die Remote-Partei Teams verwendet hat. Es war nur davon ausgegangen, dass aus der Signalgebung, die nach der Einrichtung einer Sitzung empfangen wurde.

Wenn die Signalgebung angegeben hat, dass die Antwort von (oder über) dem Interop-Gateway kam, würde die Gelbe Business-Leiste (Banner) angezeigt, die besagt, dass die andere Person Skype for Business nicht verwendet hat. Mit der Entwicklung unseres Services führte dies zu falsch positiven Ergebnissen, bei denen Skype for Business-Benutzer die Business-Leiste sehen würden, wenn Sie mit dem Cloud-Voicemaildienst oder anderen Cloud-Sprachdiensten verbunden waren, anstatt mit einem tatsächlichen **nur** -Benutzer.
 
Um diese falsch positiven Meldungen zu verhindern, informiert der Anwesenheitsdienst nun den Skype for Business-Client, wenn die andere Partei nur ein tatsächlicher Benutzer von **Teams** ist. Auf diese Weise kann sich Skype for Business bewusst sein, dass es eine Interop-Unterhaltung erstellen muss, bevor es erstellt wurde, und dass das Unterhaltungsfenster für Interop spezifisch ist.

![Screenshot der Meldung "Teams" zum Erstellen einer Interop-Unterhaltung mit einem Skype for Business-Benutzer](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Wenn der Skype for Business-Benutzer beispielsweise seinen Desktop freigeben möchte, wird ihm mitgeteilt, dass wir eine Besprechung beginnen und durch die einzelnen Schritte geführt werden.

![Screenshot der Meldung "Teams" zum Starten der Besprechung mit einem Team Benutzer](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

In der Zwischenzeit erhält der Benutzer des Teams eine eingehende Chatnachricht mit dem Link zur Besprechung und wird zum teilnehmen geführt.

Diese Eskalation zu einer Skype for Business-Besprechung steht sowohl für Mandantenübergreifende Interop-als auch für Mandantenübergreifende Anrufe und Chats zur Verfügung. Sie ist standardmäßig aktiviert, und es gibt keine Einstellung, die der Administrator bereitstellen muss.

#### <a name="interop-escalation-from-teams"></a>Interop-Eskalation von Teams

Die Interop-Eskalation von Teams zu einer Teams-Besprechung ist jetzt verfügbar, wenn der Benutzer von Teams die Schaltfläche für die Desktopfreigabe in einem in-Tenant-Interop-Thread mit einem Skype for Business-Benutzer oder einem mandantenübergreifenden Interop Federation-Thread auswählt. Die Interop-Eskalation wird von einer 1:1-Chat Unterhaltung oder einem 1:1-Anruf unterstützt.

Die Funktion wird im Team-Desktop Client für Windows, im Team-Desktop Client für Mac und im Team-WebClient in Browsern unterstützt, bei denen die Inhaltsfreigabe unterstützt wird, während die Kommunikation mit einer beliebigen Skype for Business-Client Version erfolgt.

In Interoperabilitäts-Threads und in Verbund Interoperabilitäts-Threads verfügt der Benutzer von Teams nun über die Steuerelemente (Schaltfläche), um die Inhaltsfreigabe zu starten. Wenn der Benutzer der Teams die Schaltfläche auswählt, wird ein zusätzliches Menü angezeigt, in dem Sie darüber informiert werden, dass zum Freigeben von Inhalten eine Teambesprechung gestartet werden muss.

Wenn sich die Benutzer in einem Anruf befanden, warnt das Menü auch, dass Ihr aktueller Anruf zwischen Teams und Skype for Business beendet wird, wenn Sie in eine Teams-Besprechung gestellt werden. Wenn dies der Fall ist, kann er den Skype for Business-Nutzer vor der Annahme warnen.

![Screenshot der Team Nachricht zur Freigabe von Besprechungen mit einem Skype for Business-Benutzer](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Bei der Annahme werden Sie in die Teams-Besprechung gesetzt; Sie müssen die Freigabe über das Freigabe Fach in der Besprechung starten.
 
In der Zwischenzeit erhält der Skype for Business-Nutzer eine eingehende Chat-Nachricht mit dem Link zur Besprechung und wird zum teilnehmen geführt.

Diese Eskalation zu einer Teams-Besprechung steht sowohl für Mandantenübergreifende Interop-als auch für Mandantenübergreifende Anrufe und Chats zur Verfügung. Sie ist standardmäßig aktiviert, und es gibt keine Einstellung, die der Administrator bereitstellen muss. Sie ist jedoch für den Benutzer deaktiviert, wenn sich der Administrator in auf festgelegt hat ``-AllowPrivateMeetNow`` ``CsTeamsMeetingPolicy`` ``$false`` .

Nachdem Sie diesen Artikel überprüft haben, lesen Sie [Wählen Sie Ihre Upgrade-Reise](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [Migrations-und Interoperabilitäts Anleitung](https://aka.ms/SkypeToTeams-Interop), [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md)und [Festlegen ihrer Koexistenz-und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) für Implementierungsdetails.

## <a name="related-links"></a>Verwandte Links

[Video: Verwalten der Koexistenz und Interoperabilität zwischen SFB und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
