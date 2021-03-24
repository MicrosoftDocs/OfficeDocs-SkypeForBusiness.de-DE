---
title: Verständnis der Koexistenz und Interoperabilität von Microsoft Teams und Skype for Business
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Details zu den Optionen für die Koexistenz von Skype for Business und Microsoft Teams sowie zur resultierenden Interoperabilität zwischen Skype for Business und Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3332ec1a5c5bc05bc833511a3b33e0f4dff6cccc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111131"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Verständnis der Koexistenz und Interoperabilität von Microsoft Teams und Skype for Business

![Upgrade des Reisediagramms, Hervorhebung der Projektdefinitionsphase](media/upgrade-banner-project-definition.png "Phasen des Upgradewegs mit Schwerpunkt auf der Projektdefinitionsphase")

Dieser Artikel ist Teil der Projektdefinitionsphase Ihrer Upgradereise. Schließen Sie den Vorgang ab, nachdem Sie eine Sponsoringkoalition und ein Projektteam erstellt und den Umfang, die Ziele und den Plan für Ihr Projekt definiert haben. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)

Wenn Ihre Organisation skype for Business heute verwendet und Sie beginnen, Teams zusammen mit Skype for Business zu verwenden – oder Sie beginnen, ein Upgrade auf Teams zu starten –, ist es wichtig zu verstehen, wie die beiden Anwendungen nebeneinander vorhanden sind, wann und wie sie zusammenarbeiten und wie Sie die Migration Ihrer Benutzer bis zum letztendlichen Upgrade von Skype for Business auf Teams verwalten können.

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr [über Koexistenz und Interoperabilität zu erfahren.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Darüber hinaus können Sie an interaktiven Liveworkshops teilnehmen, in denen wir Ihnen Anleitungen, bewährte Methoden und Ressourcen zum Einstieg in die Upgradeplanung und -implementierung bieten.
>
> Nehmen Sie [zuerst an der Upgradesitzung](./upgrade-workshops-landing-page.yml) planen teil, um zu beginnen.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Übersicht über die Koexistenz von Teams und Skype for Business

In den folgenden Abschnitten werden die Koexistenzmodi beschrieben, die verfügbar sind, wenn Sie sich für Upgrades auf Teams entscheiden, und die Funktionen, die jeder Modus bietet. Darüber hinaus beschreiben wir die Interoperabilität (Interoperabilität), die zwischen Benutzern auf Skype-for-Business-Clients und Benutzern auf Teams-Clients stattfindet, und wie die Interoperabilität vom ausgewählten Koexistenzmodus beeinflusst wird.

 Teams bietet Funktionen für die Zusammenarbeit, Chats, Anrufe und Besprechungen. Je nachdem, wie Sie Teams bereitstellen, überschneiden sich diese Funktionen möglicherweise mit den Funktionen, die von Skype for Business für einen bestimmten Benutzer bereitgestellt werden. Der Standardmodus besteht im Ausführen von Teams zusammen mit Skype for Business mit überlappenden Funktionen. Einem Benutzer kann jedoch einer von mehreren Koexistenzmodi (auch als Upgrademodi bekannt) zugewiesen werden, die darauf ausgelegt sind, sicherzustellen, dass sich diese Funktionen für diesen Benutzer nicht überlappen (in diesem Fall ist die Interoperabilität zwischen Teams und Skype for Business verfügbar). Wenn Sie z. B. über erhebliche lokale Ressourcen von Skype for Business Server mit einer komplexen Enterprise-VoIP-Bereitstellung verfügen, aber [](meetings-first.md) möchten, dass Ihre Benutzer moderne Besprechungen so schnell wie möglich nutzen können, sollten Sie "Besprechungen zuerst" als alternativen Weg auswerten.

Wir empfehlen, die folgenden Koexistenzmodi zu überprüfen, um zu ermitteln, welcher Pfad für Ihre Organisation richtig ist.

> [!Important]
> Die Einführung neuer Technologien oder das Vornehmen von Änderungen an Ihrer vorhandenen, vertrauten Skype for Business-Umgebung kann für Benutzer störend sein, während sie gleichzeitig großartige neue Geschäftliche Vorteile bieten. Nehmen Sie sich Zeit, um die Benutzerbereitschaft zu bewerten und einen Kommunikations- und Schulungsplan zu implementieren, bevor Sie die in diesem Artikel beschriebenen Änderungen implementieren. Darüber hinaus empfehlen wir Ihnen dringend, Ihren Plan mit einer ausgewählten Gruppe von Benutzern zu piloten, bevor Sie ihn in Ihrer gesamten Organisation implementieren.

### <a name="islands-mode"></a>Inselmodus

Standardmäßig können Benutzer Teams zusammen mit Skype for Business als zwei separate Lösungen ausführen, die ähnliche und überlappende Funktionen bereitstellen. Die Funktionen umfassen Anwesenheit, Chat, Anrufe und Besprechungen. Teams-Benutzer können auch neue Zusammenarbeitsfunktionen nutzen, z. B. Teams und Kanäle, Zugriff auf Dateien in Microsoft 365 oder Office 365 und Anwendungen.

In diesem Koexistenzmodus, dem so genannten **Islands,** wird jede der Clientanwendungen als separate Insel ausgeführt. Skype for Business spricht mit Skype for Business, und Teams spricht mit Teams. Es wird erwartet, dass Benutzer beide Clients jederzeit ausführen und systemeigene Kommunikationen in dem Client ausführen können, von dem aus die Kommunikation gestartet wurde. Deshalb ist keine Interoperabilität im **Inselmodus** erforderlich.

Um ein verwirrendes oder regressiertes Skype for Business-Erlebnis zu vermeiden, behandelt Skype for Business die folgenden Integrationen, die nicht im Modus **"Teamsinseln" behandelt** werden:

- Externe Kommunikation (Verbundkommunikation).
- PSTN-Sprachdienste und Sprachanwendungen, Office-Integration.
- HID-Steuerelemente für USB-Geräte.
- Mehrere andere Integrationen.  

Das Telefonsystem wird im Modus "Teams im **Inselmodus" nicht** unterstützt. **Der Inselmodus** unterstützt keine Enterprise-VoIP Skype for Business-Client ist.

> [!Important]
> Im **Inselmodus** werden alle Nachrichten und Anrufe von Verbundbenutzern (Personen außerhalb Ihrer Organisation) an Skype for Business übermittelt. Nach dem Upgrade **auf den Modus "Nur** Teams" werden alle Nachrichten und Anrufe von außerhalb Ihrer Organisation an Teams übermittelt.

> [!Tip]
> Skype for Business Online-Kunden empfehlen,  mit dem Standardmodus "Inseln" zu beginnen, die Akzeptanzsättigung von Teams in der Organisation zu erhöhen und dann schnell in **den Modus "Teams Only"** zu wechseln. Lokale und Hybridkunden, insbesondere komplexe Kunden, können von der Bereitstellung des Skype for  **Business mit Teams-Zusammenarbeitsmodus** als Ausgangspunkt und nicht vom Inselmodus profitieren und von dort aus zum Skype for Business mit Teams-Zusammenarbeits- und -Besprechungsmodus (d. h. Besprechungen zuerst) und in **den Modus Nur Teams** wechseln, wenn die Organisation bereit ist, Teams zu übernehmen. 

### <a name="teams-only"></a>Nur Teams

Ein **Nur-Teams-Benutzer**  (auch als aktualisierter Benutzer bezeichnet) hat Zugriff auf alle Funktionen in Teams. Sie können den Skype for Business-Client behalten, um an Besprechungen in Skype for Business teilzunehmen, die von nicht aktualisierten Benutzern oder externen Parteien organisiert wurden. Ein aktualisierter Benutzer kann weiterhin mit anderen Benutzern in der Organisation kommunizieren, die Skype for Business weiterhin verwenden, indem er  die Interoperabilitätsfunktionen zwischen Teams und Skype for Business verwendet (vorausgesetzt, die Skype for Business-Benutzer befinden sich nicht im Inselmodus). Ein aktualisierter Benutzer kann jedoch keinen Skype for Business-Chat, einen Anruf oder eine Besprechung initiieren.

Sobald Ihre Organisation bereit ist, dass einige oder alle Benutzer Teams als einziges Kommunikations- und Zusammenarbeitstool verwenden können, aktualisieren Sie diese Benutzer auf den **Modus "Nur Teams".** Wenn Sie ein Upgrade vom Islands-Modus **durchführen,** sollten Sie die Einführung von Teams zuerst in der gesamten Organisation sättigten, bevor Sie mit dem Upgradevorgang beginnen. Diese Einführung verhindert defekte Kommunikationsszenarien, da **der Inselmodus** keine Interoperabilität bietet.

Im **Modus Nur Teams** ist Teams die Standard-App für das SIP/Tel-Protokoll. Links auf der Visitenkarte eines Benutzers in Outlook für Anrufe oder Chats werden von Teams behandelt.

Weitere Überlegungen zum Wechseln in **den Modus "Nur Teams"** finden Sie unter [Überlegungen zum Teams Only-Modus.](teams-only-mode-considerations.md)

![Screenshot der Bestätigungsmeldung von Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business-Client, der in einem speziellen Modus ausgeführt wird, nachdem der Benutzer ein Upgrade als Nur-Teams-Benutzer durchgeführt hat")

### <a name="skype-for-business-only"></a>Nur Skype for Business

In diesem Koexistenzmodus verbleiben Benutzer für Chat-, Besprechungs- und Anruffunktionen in Skype for Business und nicht in Teams, und sie verwenden Teams nicht für Teams und Kanäle. Dieser Modus ist heute verfügbar. In der aktuellen Implementierung werden Teams und Kanäle jedoch nicht automatisch für den Benutzer deaktiviert. Dies kann mithilfe der App-Setuprichtlinie erreicht werden, um Teams und Dateien auszublenden.

Dieser Modus kann vor dem Starten einer verwalteten Bereitstellung von Teams verwendet werden, um zu verhindern, dass Benutzer mit der Verwendung von Teams beginnen, bevor sie die Bereitschaft erstellt haben. Dieser Modus ist auch eine Möglichkeit, die authentifizierte Teilnahme an Teams-Besprechungen für Skype for Business-Benutzer zu aktivieren, vorausgesetzt, die Benutzer sind für Teams lizenziert.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business mit Teamzusammenarbeit

Verwenden Sie diesen Modus, um Teams in Ihrer Umgebung einzuführen, während Sie Ihre vorhandenen Investitionen in Skype for Business weiterhin verwenden. Lassen Sie Skype for Business für Chats, Anrufe und Besprechungsfunktionen unverändert. Hinzufügen von Teamzusammenarbeitsfunktionen:

- Teams und Kanäle.
- Zugriff auf Dateien in Microsoft 365 oder Office 365.
- Anwendungen. Kommunikationsfunktionen von Teams – privater Chat, Anrufe und Planen von Besprechungen.

Private Chats, Anrufe und Terminplanungsbesprechungen von Teams sind in diesem Modus standardmäßig deaktiviert.

Organisationen mit einem Lokalen oder Hybridstartpunkt von Skype for Business  Server sollten diesen Modus als Alternative zum Inselmodus betrachten, wenn sie ihren Benutzern Interoperabilität und Vorhersagbarkeit für ihre  Kommunikation bieten möchten, sowie über eine vorhersagbare Zeitachse für das Upgrade auf Teams (im Gegensatz zur Nutzung der Akzeptanzsättigung im Inselmodus).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business mit Zusammenarbeit und Besprechungen von Teams, auch bekannt als "Besprechungen zuerst"

Verwenden Sie diesen Koexistenzmodus, um die Verfügbarkeit von Teams-Besprechungs- und Zusammenarbeitsfunktionen in Ihrer Organisation zu beschleunigen. Im Koexistenzmodus können Ihre Benutzer die vorteile der überlegenen Teams-Besprechungserfahrung nutzen:

- Hervorragende Qualität.
- Transkription und Übersetzung.
- Hintergrund verschwommen.
- Überlegene Benutzererfahrung auf allen Plattformen, einschließlich mobiler Geräte und Browser.

Neben der Verwendung von Teams für Teams und kanälenbasierte Unterhaltungen in diesem Modus verwenden Benutzer Teams zum Planen und Durchführen ihrer Besprechungen. Private Chats und Anrufe bleiben in Skype for Business erhalten. Teams und Skype for Business profitieren von einer Reihe von Funktionen für "bessere Zusammenarbeit", z. B. Anwesenheitsabgleich, automatisches Halten/Zurückhalten und Unterstützung von HID-Geräten in beiden Anwendungen. Es ist möglich, Teams und Kanäle bei Bedarf mithilfe der App-Setuprichtlinie auszublenden.

Dieser Koexistenzmodus ist besonders nützlich für Organisationen mit lokalen Skype for Business-Bereitstellungen mit Enterprise-VoIP. Diese Organisationen nehmen sich wahrscheinlich etwas Zeit für ein Upgrade auf Teams und möchten so schnell wie möglich von den überlegenen Teams-Besprechungen profitieren.

> [!TIP]
> Um den empfohlenen Upgrademodus basierend auf den Funktionen zu identifizieren, die Sie in Teams aktivieren möchten, während Skype for Business noch verwendet wird, verwenden Sie den [Skype-zu-Teams-Upgrade-Assistenten.](https://aka.ms/SkypeToTeamsWizard)

Weitere Informationen zu Koexistenzmodi, Voraussetzungen und Verwaltung finden Sie unter [Migrations-](./migration-interop-guidance-for-teams-with-skype.md) und Interoperabilitätsleitfaden für Organisationen, die Teams zusammen mit Skype for Business verwenden, und Festlegen Ihrer [Koexistenz- und Upgradeeinstellungen.](./setting-your-coexistence-and-upgrade-settings.md)

|Symbol "Entscheidungspunkt" |Symboldefinition |Beschreibung |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Entscheidungspunkt|<ul><li>Welche Koexistenzmodus(en) passen am besten zu den Anforderungen Ihrer Organisation und der Benutzer?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Nächster Schritt|<ul><li>Wählen Sie den besten Ansatz für Ihre Upgradereise aus.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilität von Teams und Skype for Business

Interoperabilität ist die Möglichkeit für Teams- und Skype for Business-Benutzer in derselben Organisation, über Teams und Skype for Business hinweg zu kommunizieren.

Die Interoperabilität wird vom Koexistenzmodus (auch als Upgrademodus bezeichnet) des Empfängers bestimmt. Es gibt keine Interoperabilität, wenn sich der Empfänger im **Inselmodus** befindet.

> [!Note]
> Wenn sie in einem beliebigen Koexistenzmodus mit Ausnahme von **Inseln** bereitgestellt werden, können Teams und Skype for Business zusammenarbeiten, [](#interoperability-of-teams-and-skype-for-business)sodass Benutzer miteinander chatten und sich anrufen können, und sicherstellen, dass die Kommunikation in Ihrer Organisation während des Upgrades zu Teams flüssig bleibt. Koexistenzmodi steuern die Interoperabilität. Der Koexistenzmodus des Empfängers bestimmt, ob Interoperabilität verfügbar sein wird. Wenn sich der Empfänger beispielsweise in einem Modus befindet, in dem Chats nur in einem Client (z. B. Teams) verfügbar sind, ist die Chatinteroperabilität im Allgemeinen verfügbar, wenn der Gründer den anderen Client (in diesem Fall Skype for Business) zum Starten des Chats verwendet. Wenn sich der Empfänger dagegen im Modus befindet, in dem der Chat in beiden Clients (Inselmodus) verfügbar ist, ist die Interoperabilität für den Chat nicht verfügbar. Die Nachricht wird vom Empfänger in dem Client empfangen, in dem der Gründer den Chat gestartet hat. Für die ordnungsgemäße Kommunikation im **Inselmodus ist** daher eine Sättigung der #A0 erforderlich. d. h., alle Benutzer verwenden und überwachen beide Clients aktiv.

> [!Note]
> **Um die neueste Koexistenzerfahrung zu haben, muss die Clientversion der neueste verfügbare Client im Office-Bereitstellungskanal des Benutzers sein.**

#### <a name="native-interop-and-interop-escalation"></a>Native In- und In-Op-Eskalation

Es gibt zwei Arten von Inop-Erfahrungen: systemeigene und In-Op-Eskalation.

- In _dem Client,_ den der Benutzer derzeit verwendet, tritt eine systemeigene Inopoperfahrung auf. Ein Benutzer ist im Skype for Business-Client, der andere in Teams. Eine systemeigene In-Interop-Erfahrung verwendet sie nicht zu einem anderen Client, um zu kommunizieren. Die Benutzer können ihre Unterhaltungen auf dem Client führen, den sie derzeit verwenden. Die nativen In-Op-Erfahrungen sind 1:1-Chats und Anrufe.
- Eine _In-Op-Eskalationserfahrung_ bedeutet, dass der Client im Rahmen der Unterstützung von Benutzern beim Ausführen einer erweiterten Aktion (z. B. das Freigeben ihres Desktops) die Erstellung einer Besprechung erleichtert, an der Benutzer teilnehmen können, um die Erfahrung in dieser Besprechung fortzufahren. Die Besprechung wird auf der Plattform des Initianten der Aktion erstellt. Der Benutzer oder die Benutzer, die sich nicht auf dieser Plattform befinden, erhalten einen Link zum Teilnehmen an einer Besprechung. Wenn sie auf diesen Link klicken, werden sie der Besprechung in einem kompatiblen Client (Browser, Web App oder vollständiger Client, je nach Konfiguration) beigetreten. Für die In-Op-Eskalation von Skype for Business ist ein neuer Client erforderlich. Die In-Op-Eskalation von Teams ist jetzt verfügbar. Beide werden in der Interoperabilitätserfahrung im Mandanten und für Mandantenübergreifende Verbundkommunikation unterstützt.

#### <a name="native-interop-experiences"></a>Native Inop-Erfahrungen

Je nach den den Benutzern zugewiesenen Koexistenzmodi (wie zuvor beschrieben) stehen die folgenden systemeigenen In-Op-Erfahrungen zur Verfügung:

Skype for Business-Benutzer können mit Teams-Benutzern 1:1 chatten und umgekehrt. Ein Inopchat muss über ein Inopgateway gehen, das Teil der Teams-Clouddienste ist (und daher nur online vorhanden ist). Inopchats sind Nur-Text-Chats: Rich-Text- und Emoticons werden nicht unterstützt. Benutzer in Teams und in Skype for Business werden benachrichtigt, dass es sich bei der Unterhaltung um eine In-Interop-Unterhaltung handelt.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business-Benutzer können 1:1-Sprach- und Videoanrufe an Teams-Benutzer führen, und Teams-Benutzer können dies auch tun.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Die Inopoperfahrung bei einer lokalen Bereitstellung von Skype for Business erfordert, dass sich die lokale Umgebung mit Microsoft 365 oder Office 365 Skype for Business im Hybridmodus befindet. Details finden Sie unter [Migrations- und Interoperabilitätsleitfäden](./migration-interop-guidance-for-teams-with-skype.md).

Diese Inopoperfahrungen sind für und zwischen Benutzern verfügbar, denen einer der folgenden Koexistenzmodi zugewiesen ist: **Skype for Business mit Teams Collaboration,** Skype for Business mit Teams **Collaboration** und Besprechungen, Skype for **Business Only** oder Teams **Only**. Es gibt keine Interoperabilität für Benutzer im **Inselmodus.**

#### <a name="native-interop-experience-limitations"></a>Einschränkungen der systemeigenen Inop-Erfahrung

Aufgrund des Unterschieds in Protokollen und Technologien ist es nicht möglich, alle Funktionen systemeigener zu unterstützen. Insbesondere stehen die folgenden Funktionen nicht zur Verfügung:

- Markdown, Rich Text und der vollständige Emoticonsatz werden weder von Teams noch von Skype for Business unterstützt. Andere systemeigene Features des Felds zum Verfassen in Teams-Chats werden nicht unterstützt.
- Die Bildschirmfreigabe (Desktop- oder App-Freigabe) zwischen Teams und Skype for Business wird systemeigener nicht unterstützt. Sie wird jedoch durch die In-Op-Eskalation unterstützt.
- Gruppenchats (Unterhaltungen mit mehreren Teilnehmern) in Teams können nur Teilnehmer enthalten, die Teams verwenden.
- Chatunterhaltungen mit mehreren Teilnehmern (Gruppenchats) in Skype for Business können nur Teilnehmer enthalten, die Skype for Business verwenden. Die In-App-Eskalation für mehrere Parteien ist jedoch über Skype for Business verfügbar.
- Das Eskalieren eines laufenden Peer-to-Peer-Sprach- oder Videoanrufs zu einem Anruf mit mehreren Parteien, an dem sowohl Teams- als auch Skype for Business-Benutzer beteiligt sind, wird nicht unterstützt.
- Die Dateiübertragung für Zwei-Parteien-Chats oder Dateianlage in Gruppenchats, von Teams zu Skype for Business – und umgekehrt – wird nicht unterstützt.
- Es gibt keine Interoperabilität mit beständigem Skype for Business-Chat.

Bei all diesen Einschränkungen (mit Ausnahme des permanenten Chats) besteht eine mögliche Problemumgehung in der Möglichkeit, dass ein Benutzer eine Besprechung startet und den anderen Benutzer zur Teilnahme an der Besprechung einlädt.

Diese Problemumgehung ist die Grundlage für die In-Op-Eskalation. Insbesondere die Bildschirmfreigabe und die Eskalation zu mehrteiligen Teilen sind nicht systemeigener, werden aber über die Inopeskalation unterstützt.

#### <a name="interop-escalation-experiences"></a>Erfahrungen mit der In-Op-Eskalation

Die Inopeskalation besteht darin, die systemeigenen Inopfunktionen durch verwaltete Eskalationen zu Besprechungen zu ergänzen. Besprechungen bieten umfassende, für jeden zugängliche Erfahrungen, unabhängig davon, über welchen Kunden sie verfügen.

Wenn die Inop-Eskalation vom Benutzer von Teams ausgelöst wird, wird eine Teams-Besprechung erstellt. Wenn sie vom Skype for Business-Benutzer ausgelöst wird, wird eine Skype for Business-Besprechung erstellt. In beiden Fällen handelt es  sich bei der erstellten Besprechung um eine Besprechung, die sich nicht im Kalender des Benutzers widerspiegelt.

Die andere Partei empfängt den Link für die Besprechungs-Teilnahme über den In-Op-Chat und tritt bei, indem sie auf diesen Link klickt. Wenn der Skype for Business-Benutzer über ein Teams-Konto verfügt und vom Teams-Benutzer eingeladen wird, wird er authentifiziert an der Besprechung teilnehmen. Andernfalls nehmen sie als anonymer Teilnehmer teil. Umgekehrt verfügen Teams-Benutzer fast immer über ein Skype for Business-Konto und einen Skype for Business-Client, über den sie als authentifizierter Teilnehmer an einer Skype for Business-Besprechung teilnehmen können, aber sie können auch als anonymer Teilnehmer teilnehmen, z. B. mithilfe der Skype-Besprechungs-App.

Sobald die Parteien der Besprechung beigetreten sind, können sie alle aktivitäten durchführen, die in Besprechungen unterstützt werden, z. B. Desktop- oder Inhaltsfreigabe, Dateifreigabe oder -übertragung, Hinzufügen anderer Teilnehmer und so weiter.

#### <a name="interop-escalation-from-skype-for-business"></a>Inopop escalation from Skype for Business

Die In- und Inop-Eskalation von Skype for Business wurde im Juli 2019-Build von monatlicher C2R aktualisiert. Bisher war Skype for Business nicht bekannt, dass die Remoteparty Teams verwendet. Es wurde nur angenommen, dass aus der Signalisierung, die nach dem Start einer Sitzung empfangen wurde.

Wenn die Signalisierung angibt, dass die Antwort vom (oder über) das Inopgateway stammt, wird die gelbe Geschäftsleiste (Banner) angezeigt, die angibt, dass die andere Partei Skype for Business nicht verwendet. Mit der Weiterentwicklung unseres Diensts führte dies zu falsch positiven Meldungen, bei denen Skype for Business-Benutzern die Geschäftsleiste angezeigt wurde, wenn sie mit dem Cloud VoicemailDienst oder anderen Cloud voice services verbunden waren, anstatt mit einem tatsächlichen **Nur-Teams-Benutzer.**

Um diese falsch positiven Ergebnisse zu verhindern, informiert der Anwesenheitsdienst jetzt den Skype for Business-Client, wenn die andere Partei ein **tatsächlicher Benutzer** von Teams ist. Auf diese Weise kann Skype for Business wissen, dass eine Inop-Unterhaltung erstellt werden muss, bevor sie erstellt wurde, und das Unterhaltungsfenster muss speziell für die Inopop-Funktion sein.

![Screenshot der Nachricht "Teams" zum Erstellen einer Inop-Unterhaltung mit einem Skype for Business-Benutzer](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Wenn der Skype for Business-Benutzer beispielsweise seinen Desktop freigeben möchte, wird er darüber informiert, dass wir eine Besprechung starten und durch die Schritte geführt werden.

![Screenshot der Teams-Nachricht zum Starten einer Besprechung mit einem Teams-Benutzer](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Währenddessen erhält der Teams-Benutzer eine eingehende Chatnachricht mit dem Link zur Besprechung und wird zur Teilnahme geführt.

Diese Eskalation zu einer Skype for Business-Besprechung ist sowohl für In-Mandant-In-App- als auch mandantenübergreifende Verbundanrufe und Chats verfügbar. Es ist standardmäßig aktiviert, und es gibt keine Einstellung, die der Administrator bereitstellen muss.

#### <a name="interop-escalation-from-teams"></a>In-Op-Eskalation von Teams

Die Inopeskalation von Teams zu einer Teams-Besprechung ist jetzt verfügbar, wenn der Teams-Benutzer die Schaltfläche für die Desktopfreigabe in einem In-Mandant-In-App-Thread mit einem Skype for Business-Benutzer oder in einem threadübergreifenden Verbundthread für Inopops auswählt. Die Inopeskalation wird von einer 1:1-Chatunterhaltung oder von einem 1:1-Anruf unterstützt.

Die Funktion wird im Teams-Desktopclient für Windows, im Teams-Desktopclient für Mac und im Teams-Webclient in Browsern unterstützt, in denen die Inhaltsfreigabe unterstützt wird, während die Kommunikation mit einer beliebigen Skype for Business-Clientversion besteht.

In Interoperabilitätsthreads und in Verbundinteroperabilitätsthreads verfügt der Teams-Benutzer jetzt über die Steuerelemente (Schaltfläche), um die Inhaltsfreigabe zu starten. Wenn der Teams-Benutzer die Schaltfläche auswählt, wird ihm ein zusätzliches Menü angezeigt, in dem er darüber informiert wird, dass er zum Freigeben von Inhalten eine Teams-Besprechung starten muss.

Wenn sich die Benutzer in einem Anruf befinden, werden sie im Menü darüber hinaus gewarnt, dass ihr aktueller Anruf zwischen Teams und Skype for Business beendet wird, wenn sie in eine Teams-Besprechung eintreffen. Wenn sie sich entscheiden, kann sie den Skype for Business-Benutzer vor der Annahme warnen.

![Screenshot der Teams-Nachricht zum Freigeben einer Besprechung für einen Skype for Business-Benutzer](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Nach der Annahme werden sie in die #A0 eingeladen. sie müssen mit der Freigabe über die Freigabeleiste in der Besprechung beginnen.

Währenddessen empfängt der Skype for Business-Benutzer eine eingehende Chatnachricht mit dem Link zur Besprechung und wird zur Teilnahme geführt.

Diese Eskalation zu einer Teams-Besprechung ist sowohl für in-mandant-in-In- als auch mandantenübergreifende Verbundanrufe und Chats verfügbar. Es ist standardmäßig aktiviert, und es gibt keine Einstellung, die der Administrator bereitstellen muss. Wenn der Administrator auf ein -Konto einstellt, ist es für den Benutzer ``-AllowPrivateMeetNow`` jedoch ``CsTeamsMeetingPolicy`` ``$false`` deaktiviert.

Nachdem Sie diesen Artikel [](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)überprüft haben, lesen Sie Wählen Sie Ihre Upgradereise, [Migrations-](./migration-interop-guidance-for-teams-with-skype.md)und Interoperabilitätsleitfäden , [Koexistenz](coexistence-chat-calls-presence.md)mit Skype for Business und Festlegen Ihrer [Koexistenz-](./setting-your-coexistence-and-upgrade-settings.md) und Upgradeeinstellungen für Implementierungsdetails aus. Wir empfehlen auch das folgende Video: [Video: Verwalten der Koexistenz und Interoperabilität zwischen SfB und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Technische Details zur Koexistenz von Teams und Skype for Business

In den folgenden Abschnitten wird das Verhalten zusammengefasst, das beim Ausführen von Teams- und Skype for Business-Clients in derselben Organisation auftreten kann, unabhängig davon, welcher Modus und welche Upgrademethode verwendet wird:

- [Besprechungen](#meetings)
- [Interoperabilität](#interoperability)
- [Inopop versus native Unterhaltungsthreads](#interop-versus-native-conversation-threads)
- [Anwesenheit](#presence)
- [Partnerverbund](#federation)
- [Kontakte](#contacts)

### <a name="meetings"></a>Besprechungen

Unabhängig vom Modus können Benutzer immer an jeder Art von Besprechung teilnehmen, zu der sie eingeladen werden, ganz gleich, ob es sich um Skype for Business oder Teams handelt.  Benutzer müssen jedoch mit einem entsprechenden Client an der Besprechung teilnehmen, der dem Besprechungstyp entspricht:

- Wenn es sich bei der Besprechung um eine Teams-Besprechung handelt, verwenden alle Teilnehmer (unabhängig davon, ob es sich um TeamsOnly-, Islands- oder Skype for Business-Benutzer handelt) den Teams-Client, um an der Besprechung teil zu nehmen. Wenn Teams nicht installiert ist, wird der Benutzer nach dem Versuch, an einer Besprechung teil zu nehmen, in das Web geleitet.

- Wenn es sich bei der Besprechung um eine Skype for Business-Besprechung handelt, verwenden alle Teilnehmer (unabhängig davon, ob es sich um TeamsOnly-, Insel- oder Skype for Business-Benutzer handelt) den Skype for Business-Client, um an der Besprechung teil zu nehmen. Wenn der Skype for Business-Client nicht installiert ist, wird der Benutzer über die Skype-Besprechungs-App in das Web geleitet, um an der App für Skype-Besprechungen teil zu nehmen.

Beim Organisieren von Besprechungen basiert der geplante Besprechungstyp auf dem Modus des Organisators, wie in der folgenden Tabelle dargestellt:

| Modus des Organisators    |      Verhalten |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Alle in Teams geplanten Besprechungen. Das Skype for Business-Add-In ist in Outlook nicht verfügbar. | 
| SfbWithTeamsCollab, SfbOnly   | Alle in Skype for Business geplanten Besprechungen. Das Teams-Add-In ist in Outlook nicht verfügbar. | 
| Inseln | Standardmäßig können Besprechungen entweder in Skype for Business oder Teams geplant werden. Beide Add-Ins sind in Outlook verfügbar. Sie können jedoch optional verlangen, dass Benutzer auf Inseln besprechungen immer in Teams planen, indem Sie ihnen eine Instanz von TeamsMeetingPolicy mit dem PreferredMeetingProviderForIslandsMode=Teams zuweisen.| 


### <a name="interoperability"></a>Interoperabilität

Wie oben unter Interoperabilität von Teams und [Skype for Business](#interoperability-of-teams-and-skype-for-business)beschrieben, unterstützt Teams die Interoperabilität mit Skype for Business in bestimmten Szenarien. Die Inopkommunikation bezieht sich auf einen Chat oder Anruf zwischen einem Skype for Business-Benutzer und einem Teams-Benutzer.  Die Inopopkommunikation ist nur zwischen zwei Benutzern möglich. Chats/Anrufe mit mehreren Parteien oder das Hinzufügen weiterer Benutzer werden nicht unterstützt.

Ein Inopchat oder Anruf zwischen zwei Benutzern wird erstellt, wenn jeder der folgenden Punkte zutrifft:

- Ein Benutzer verwendet Teams, der andere Skype for Business.

- Der Modus des Empfängers der ursprünglichen Kommunikation ist NOT Islands (andernfalls würde die Kommunikation im gleichen Client landen), wenn sich beide Benutzer in derselben Organisation befinden. In Verbundszenarien verwendet der sendende Benutzer Teams, und der Empfänger befindet sich nicht im TeamsOnly-Modus. 

- Der Benutzer von Teams verfügt NICHT auch über ein lokales Skype for Business-Konto.

In der In-Interop-Kommunikation ist Chat nur Nur-Text. Darüber hinaus sind Dateifreigabe und Bildschirmfreigabe im *In-Interop-Chat selbst nicht möglich.* Benutzer in einer Inopunterhaltung können jedoch problemlos Datei- und/oder Bildschirmfreigaben erzielen, indem sie eine On-Demand-Besprechung innerhalb des Inopchats erstellen, wie unten beschrieben:

- Wenn der Teams-Benutzer versucht, seinen Bildschirm zu teilen, wird automatisch eine on-demand-Teams-Besprechung erstellt und ein Einladungslink zu dieser Besprechung an den Client des Skype for Business-Benutzers gesendet. Wenn der Skype for Business-Benutzer auf den Link klickt, öffnet er Teams und tritt an der Besprechung teil. Beide Benutzer befinden sich jetzt in einer Teams-Besprechung und können nach Bedarf freigeben.

- Wenn der Skype for Business-Benutzer einen Client ab 2018 verwendet und versucht, Inhalte zu teilen, wird automatisch eine Skype for Business-Besprechung auf Abruf erstellt und ein Einladungslink zu dieser Besprechung an den Client des Teams-Benutzers gesendet. Wenn der Benutzer auf den Link klickt, versucht er, an der Skype for Business-Besprechung teil zu nehmen. Wenn der Teams-Benutzer den Skype for Business-Client installiert hat, wird er geöffnet, und der Benutzer wird zur Anmeldung aufgefordert (sofern nicht bereits angemeldet).  Wenn der Benutzer von Teams den Skype for Business-Client nicht installiert hat, wird der Benutzer aufgefordert, die Webversion zu verwenden. Sobald beide Benutzer angemeldet sind, befinden sie sich in einer Skype for Business-Besprechung und können nach Bedarf freigeben.

### <a name="interop-versus-native-conversation-threads"></a>Inopop versus native Unterhaltungsthreads

Da die Inopopkommunikation nicht alle Features der nativen Teams-Unterhaltung unterstützt, verwaltet der Teams-Client separate Unterhaltungsthreads für die Kommunikation zwischen Teams und Teams-zu-Skype for Business. Diese Unterhaltungen werden in der Benutzeroberfläche anders gerendert: Interopthreads können von einem normalen systemeigenen Teams-Thread unterschieden werden, indem Sie:

- Fehlende Steuerelemente für Rich-Text, Datei-/Bildschirmfreigabe, Unfähigkeit zum Hinzufügen von Benutzern.
- Eine Änderung am Symbol des Zielbenutzers mit einem "S" für Skype for Business.

Diese Unterschiede werden in den folgenden Screenshots gezeigt:

Eine native Teams-to-Teams-Unterhaltung mit Benutzer-G3-Test

![Diagramm mit einer nativen Teams-to-Teams-Unterhaltung](media/teams-upgrade-native-thread.png)

Eine Inop-Unterhaltung mit demselben Benutzer-G3-Test

![Diagramm mit einer In-Interop-Unterhaltung zwischen Teams und Teams](media/teams-upgrade-interop-thread.png)

Sobald ein Unterhaltungsthread erstellt wurde, ändert sich dessen Typ nie. Nachdem ein Inopthread in Teams erstellt wurde, wird er immer an den Skype for Business-Client des Zielbenutzers gesendet. Ein systemeigener Thread wird immer an den Teams-Client des Zielbenutzers gesendet.  Wenn sich der Modus eines Empfängerbenutzers ändert, funktionieren vorhandene Teams-Threads für diesen Benutzer nicht mehr, und in diesem Chat wird eine Notiz mit einem Link zum Starten einer neuen nativen Unterhaltung angezeigt, wie im folgenden Screenshot gezeigt.

![Diagramm mit einem Chat mit einem aktualisierten Skype for Business-Benutzer](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Anwesenheit

Die Anwesenheit eines bestimmten Benutzers basiert auf der Aktivität des Benutzers im Dienst über den Client. Die Anwesenheit wird dann veröffentlicht, damit andere Benutzer sie sehen können.  Skype for Business und Teams sind separate Dienste mit separaten Clients, sodass jeder Dienst über einen eigenen Anwesenheitsstatus für einen Benutzer verfügt.   Es gibt auch eine Synchronisierung zwischen den Anwesenheitsdiensten in Teams und in Skype for Business Online.  Dies ermöglicht es einem Dienst, bei Bedarf die Anwesenheit des Benutzers aus dem anderen Dienst zu veröffentlichen. 

Das Verhalten der Anwesenheitsveröffentlichung basiert auf dem Modus des Benutzers. Es gibt drei grundlegende Fälle:

- Wenn sich ein Benutzer im TeamsOnly-Modus befindet, sehen alle anderen Benutzer die Anwesenheit von Teams für diesen Benutzer, unabhängig davon, welchen Client er verwendet.

- Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, sehen alle anderen Benutzer die Skype for Business-Anwesenheit für diesen Benutzer, unabhängig davon, welchen Client er verwendet.

- Wenn sich ein Benutzer im Inselmodus befindet, sind die in Skype for Business und Teams veröffentlichten Anwesenheitsinformationen unabhängig, sodass die Anwesenheit, die Benutzern innerhalb derselben Organisation angezeigt wird, vom Client des anderen Benutzers abhängig ist. Benutzer in Verbundorganisationen sehen die Anwesenheit dieses Benutzers basierend auf seiner Skype for Business-Aktivität, da Der Verbunddatenverkehr zu einem Benutzer im Inselmodus in Skype for Business landet.

Angenommen, Benutzer A befindet sich im Inselmodus. Wenn Benutzer A in Teams aktiv, aber nicht bei Skype for Business angemeldet ist, würden andere Benutzer Benutzer A von ihrem Teams-Client aus als aktiv sehen, aber in ihrem Skype for Business-Client würden Benutzer A als offline angezeigt. Dies ist vom Design aus möglich, da Benutzer A nicht erreicht werden kann, wenn der Client nicht ausgeführt wird. 


### <a name="federation"></a>Partnerverbund

Für den Verbund von Teams zu einem anderen Benutzer, der Skype for Business verwendet, muss der Teams-Benutzer online in Skype for Business zu Hause sein. TeamsUpgradePolicy regelt das Routing für eingehende Verbundchats und Anrufe. Das Verhalten des Verbundroutings ist dasselbe wie für Szenarien mit demselben Mandanten, mit Ausnahme des Islands-Modus. Wenn sich Empfänger im Inselmodus befinden:

- Von Teams initiierte Chats und Anrufe landen in Skype for Business, wenn sich der Empfänger in einem Verbund-Mandanten befindet.
- Von Teams initiierte Chats und Anrufe landen in Teams, wenn sich der Empfänger im gleichen Mandanten befindet.
- Von Skype for Business initiierte Chats und Anrufe landen immer in Skype for Business.

Ein Verbundchat kann entweder ein systemeigener Thread oder ein In-Op-Thread sein. Weitere Informationen [finden Sie unter In-Op- und native Unterhaltungsthreads.](#interop-versus-native-conversation-threads)

- Wenn sich Empfänger und Absender beide im TeamsOnly-Upgrademodus befinden, handelt es sich bei der Unterhaltung um eine systemeigene Chaterfahrung, die alle reichhaltigen Nachrichten- und Anruffunktionen umfasst. Weitere Informationen finden Sie unter [Native Chaterfahrung für externe (Verbundbenutzer) in Teams.](native-chat-for-external-users.md) 

- Wenn sich einer der Unterhaltungsteilnehmer NICHT im TeamsOnly-Upgrademodus befindet, bleibt die Unterhaltung eine Inopoperfahrung mit nur Textnachrichten. Die Benutzeroberfläche stellt Verbundchats auf ähnliche Weise wie In-Mandant-In-Op-Threads zur Verfügung, es sei denn, es gibt eine Notiz, die besagt, dass der Benutzer extern ist.

Weitere Informationen finden Sie unter [Verwalten des externen](manage-external-access.md) Zugriffs in Microsoft Teams und native Chaterfahrung für externe [(Verbundbenutzer) in Teams.](native-chat-for-external-users.md)

### <a name="contacts"></a>Kontakte

Teams und Skype for Business verfügen über separate Kontaktlisten. Dies bedeutet, dass kontaktierte Ergänzungen, Entfernungen und Änderungen, die in einem System vorgenommen wurden, nicht mit dem anderen System synchronisiert werden. Kontakte aus Skype for Business werden jedoch automatisch in Teams kopiert, wenn eines von zwei bestimmten Ereignissen eintritt: 

- Bei jedem Skype for Business Online-Benutzer, der sich zum ersten Mal bei Teams anmeldet, werden Kontakte aus Skype for Business in Teams kopiert.  Dieses Verhalten ist für Benutzer mit einem lokalen Konto in Skype for Business Server nicht verfügbar.  

- Nachdem ein Benutzer ein Upgrade auf TeamsOnly durchgeführt hat (entweder über die Zuweisung von TeamsUpgradePolicy oder über Move-CsUser -MoveToTeams), werden vorhandene Kontakte in Skype for Business mit vorhandenen Kontakten zusammengeführt, die bereits in Teams vorhanden sind. Dieses Verhalten tritt auf, unabhängig davon, ob das Skype for Business-Konto des Benutzers lokal oder online zu Hause ist. 

In beiden Fällen ist die Übertragung von Kontakten von Skype for Business zu Teams asynchron, sodass es einige Minuten dauern kann, bis Kontakte in Teams angezeigt werden. Die beiden oben genannten Ereignisse lösen die Kopie aus.  

### <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Besprechungsmigrationsdiensts (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)