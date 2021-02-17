---
title: Interoperabilität zwischen Skype for Business und Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Details zu den Koexistenzoptionen für Skype for Business und Microsoft Teams sowie zur resultierenden Interoperabilität zwischen Skype for Business und Teams.
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
ms.openlocfilehash: 7ffc673ade43e8acdb258c9364b3023ba21da2a7
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260347"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Verstehen der Koexistenz und Interoperabilität von Microsoft Teams und Skype for Business

![Upgradewegdiagramm mit Hervorhebung der Projektdefinitionsphase](media/upgrade-banner-project-definition.png "Phasen des Upgradewegs, mit Betonung auf der Projektdefinitionsphase")

Dieser Artikel ist Teil der Projektdefinitionsphase Ihres Upgradewegs. Schließen Sie den Vorgang ab, nachdem Sie ein Sponsoren- und Projektteam erstellt und den Umfang, die Ziele und den Plan für Ihr Projekt definiert haben. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](https://aka.ms/SkypetoTeams-Scope)

Wenn Ihre Organisation Skype for Business heute verwendet und Sie Teams zusammen mit Skype for Business verwenden – oder wenn Sie mit dem Upgrade auf Teams beginnen – ist es wichtig, die folgenden Punkte zu verstehen:

- Die Koexistenz der beiden Anwendungen.
- Wann und wie sie interoperiert werden.
- Verwalten der Benutzermigration bis zu einem eventuellen Upgrade von Skype for Business auf Teams

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr [über Koexistenz und Interoperabilität zu erfahren.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Darüber hinaus können Sie an interaktiven Liveworkshops teilnehmen, in denen wir Ihnen Anleitungen, bewährte Methoden und Ressourcen bieten, die mit der Planung und Implementierung von Upgrades beginnen sollen.
>
> Nehmen Sie [zuerst an der Planung Ihrer Upgradesitzung](https://aka.ms/SkypeToTeamsPlanning) teil.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Koexistenz von Teams und Skype for Business

 Teams bietet Funktionen für die Zusammenarbeit, Chats, Anrufe und Besprechungen. Je nachdem, wie Sie Sich für die Bereitstellung von Teams entscheiden, können sich diese Funktionen mit den Funktionen überschneiden, die von Skype for Business für einen bestimmten Benutzer bereitgestellt werden. Der Standardmodus besteht im Ausführen von Teams zusammen mit Skype for Business mit überlappenden Funktionen. Einem Benutzer kann jedoch einer von mehreren Koexistenzmodi (auch als Upgrademodi bekannt) zugewiesen werden, mit denen sichergestellt werden soll, dass sich diese Funktionen für diesen Benutzer nicht überlappen (in diesem Fall ist die Interoperabilität zwischen Teams und Skype for Business verfügbar). Wenn Sie z. B. über wichtige lokale Ressourcen für Skype for Business Server mit einer komplexen Enterprise-VoIP-Bereitstellung verfügen, Ihre [](meetings-first.md) Benutzer aber möglichst schnell in den Genuss moderner Besprechungen kommen möchten, können Sie Besprechungen zuerst als alternativen Weg auswerten.

Es wird empfohlen, die folgenden Koexistenzmodi zu überprüfen, um zu ermitteln, welcher Pfad für Ihre Organisation am besten ist.

> [!Important]
> Die Einführung neuer Technologien oder das Vornehmen von Änderungen an Ihrer vorhandenen, vertrauten Skype for Business-Umgebung, während gleichzeitig großartige neue Unternehmensvorteile zur Verfügung stellen, kann für die Benutzer störend sein. Nehmen Sie sich Zeit, um die Benutzerbereitschaft zu bewerten und einen Kommunikations- und Schulungsplan zu implementieren, bevor Sie die in diesem Artikel beschriebenen Änderungen implementieren. Darüber hinaus empfehlen wir Ihnen dringend, einen Pilotplan mit einer ausgewählten Gruppe von Benutzern zu erstellen, bevor Sie ihn in der gesamten Organisation implementieren.

### <a name="islands-mode"></a>Islands mode

Standardmäßig können Benutzer Teams zusammen mit Skype for Business als zwei separate Lösungen ausführen, die ähnliche und sich überlappende Funktionen bieten. Die Funktionen umfassen Anwesenheit, Chat, Anrufe und Besprechungen. Die Benutzer von Microsoft Teams können auch die neuen Funktionen für die Zusammenarbeit nutzen, z. B. Teams und Kanäle, den Zugriff auf Dateien in Microsoft 365 oder Office 365 und Anwendungen.

In diesem Koexistenzmodus, der **als "Inseln"** bezeichnet wird, wird jede Clientanwendung als separate Insel bezeichnet. Skype for Business spricht mit Skype for Business, und Teams spricht mit Teams. Es wird erwartet, dass Benutzer beide Clients jederzeit ausführen und systemeigene in dem Client kommunizieren können, von dem aus die Kommunikation gestartet wurde. Deshalb ist keine Interoperabilität im **Islands-Modus** erforderlich.

Um eine verwirrende oder regressierte Skype for Business-Erfahrung zu vermeiden, behandelt Skype for Business die folgenden Integrationen, die im Modus "Teams-Inseln" **nicht behandelt** werden:

- Externe Kommunikation (Verbundkommunikation).
- PSTN-Sprachdienste und -Sprachanwendungen, Office-Integration.
- HiD-Steuerelemente für USB-Geräte.
- Mehrere andere Integrationen.  

Telefonsystem wird im Modus "Teams im Islands"-Modus **nicht** unterstützt. **Der** Islands-Modus unterstützt nicht den Enterprise-VoIP Skype for Business ist.

> [!Important]
> Im **Modus** "Inseln" werden alle Nachrichten und Anrufe von Partnerbenutzern (Personen außerhalb Ihrer Organisation) an Skype for Business übermittelt. Nach dem Upgrade **auf den Nur-Teams-Modus** werden alle Nachrichten und Anrufe von außerhalb Ihrer Organisation an Teams übermittelt.

> [!Tip]
> Für Skype for Business Online-Kunden wird  empfohlen, mit dem Standardmodus "Islands" zu beginnen, die Akzeptanzsättigung von Teams in der Organisation zu erhöhen und dann schnell in den **Modus "Teams Only"** zu wechseln. Lokale und Hybridkunden, insbesondere komplexe, können davon profitieren, wenn der Skype for Business  mit Teams-Zusammenarbeitsmodus als Ausgangspunkt und nicht als Islands-Modus bereitgestellt wird, und von dort zum Skype for Business mit Dem **Team-Zusammenarbeits-** und -Besprechungsmodus (d. h. gegebenenfalls Besprechungen zuerst) und zum  **Nur-Teams-Modus,** wenn die Organisation bereit ist, Teams zu übernehmen.

### <a name="teams-only"></a>Nur Teams

Ein **Nur-Teams-Benutzer** (auch als *aktualisierter* Benutzer bezeichnet) hat Zugriff auf alle Funktionen in Teams. Sie behalten den Skype for Business-Client, um an Besprechungen in Skype for Business teilzunehmen, die von Benutzern ohne Upgrade oder externen Parteien organisiert wurden. Ein aktualisierter Benutzer kann weiterhin mit anderen Benutzern in der Organisation kommunizieren, die skype for Business weiterhin verwenden, indem er  die Interoperabilitätsfunktionen zwischen Teams und Skype for Business verwendet (vorausgesetzt, die Skype for Business-Benutzer befinden sich nicht im Islands-Modus). Ein aktualisierter Benutzer kann jedoch keinen Skype for Business-Chat, -Anruf oder -Besprechung starten.

Sobald Ihre Organisation bereit für einige oder alle Benutzer ist, Teams als einziges Kommunikations- und Zusammenarbeitstool zu verwenden, führen Sie ein Upgrade dieser Benutzer in den Modus **"Nur für Teams"** durch. Wenn Sie ein Upgrade vom **Modus** "Islands" durchführen, sollten Sie zunächst die Einführung von Teams in der gesamten Organisation sättigt haben, bevor Sie mit dem Upgrade beginnen. Durch diese Einführung wird verhindert, dass Kommunikationsszenarien unterbrochen werden, weil der **Islands-Modus** keine Interoperabilität bietet.

Im **Nur-Teams-Modus** ist Teams die Standard-App für das SIP/Tel-Protokoll. Links auf der Visitenkarte eines Benutzers in Outlook für Anrufe oder Chats werden von Teams behandelt.

Zusätzliche Überlegungen zum Wechsel in den **Modus "Nur für Teams"** finden Sie unter Überlegungen [zum Modus "Nur für Teams".](teams-only-mode-considerations.md)

![Screenshot der Bestätigungsmeldung für Teams](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business-Client, der in einem speziellen Modus ausgeführt wird, nachdem der Benutzer als Nur-Teams-Benutzer aktualisiert wurde")

### <a name="skype-for-business-only"></a>Nur Skype for Business

In diesem Koexistenzmodus verbleiben Benutzer für Chat-, Besprechungs- und Anruffunktionen in Skype for Business ( nicht in Teams), und sie verwenden Teams nicht für Teams und Kanäle. Dieser Modus ist heute verfügbar. In der aktuellen Implementierung werden Teams und Kanäle für den Benutzer jedoch nicht automatisch deaktiviert. Dies kann mithilfe der App-Setup-Richtlinie erreicht werden, um Teams und Dateien auszublenden.

Dieser Modus kann vor dem Starten einer verwalteten Bereitstellung von Teams verwendet werden, um zu verhindern, dass Benutzer mit der Nutzung von Teams beginnen, bevor sie die Bereitschaft aufgebaut haben. Dieser Modus ist auch eine Möglichkeit, authentifizierte Teilnahme an Teambesprechungen für Skype for Business-Benutzer zu ermöglichen, vorausgesetzt, die Benutzer sind für Teams lizenziert.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business mit Teamzusammenarbeit

Verwenden Sie diesen Modus, um Teams in Ihrer Umgebung einzuführen, während Sie Weiterhin Ihre bestehenden Investitionen in Skype for Business nutzen. Lassen Sie Skype for Business für Chat-, Anruf- und Besprechungsfunktionen unverändert. Hinzufügen von Teamzusammenarbeitsfunktionen:

- Teams und Kanäle.
- Zugriff auf Dateien in Microsoft 365 oder Office 365.
- Anwendungen. Kommunikationsfunktionen von Teams – privater Chat, Anrufe und Planen von Besprechungen.

In diesem Modus sind private Chats, Anrufe und Besprechungen in Teams standardmäßig deaktiviert.

Organisationen mit einem ausgangspunkt von Skype for Business Server lokal oder  hybrid sollten diesen Modus als Alternative zum Islands-Modus betrachten, wenn sie ihren Benutzern Interoperabilität und Vorhersagbarkeit für ihre  Kommunikation bieten möchten, sowie über einen vorhersehbaren Zeitplan für das Upgrade auf Teams (im Gegensatz zur Nutzung der Übernahmesättigung im Islands-Modus).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business mit Teamzusammenarbeit und -besprechungen, auch als "Besprechungen zuerst" bekannt

Verwenden Sie diesen Koexistenzmodus, um die Verfügbarkeit von Teams-Besprechungs- und -Zusammenarbeitsfunktionen in Ihrer Organisation zu beschleunigen. Der Koexistenzmodus ermöglicht es Ihren Benutzern, die überlegene Teambesprechungserfahrung zu nutzen:

- Hervorragende Qualität.
- Transkription und Übersetzung.
- Verschwommener Hintergrund
- Überlegene Benutzererfahrung auf allen Plattformen, einschließlich mobiler Geräte und Browser.

Neben der Verwendung von Teams für teams- und kanalbasierte Unterhaltungen in diesem Modus verwenden Benutzer Teams zum Planen und Durchführen ihrer Besprechungen. Private Chats und Anrufe bleiben in Skype for Business erhalten. Teams und Skype for Business profitieren von einer Reihe von "besseren Zusammen"-Funktionen, z. B. Anwesenheitsabgleich, automatischer Haltebereich/Enthaltung und Unterstützung von HID-Geräten in beiden Anwendungen. Es ist möglich, Teams und Kanäle mithilfe der App-Setup-Richtlinie bei Bedarf auszublenden.

Dieser Koexistenzmodus ist besonders hilfreich für Organisationen mit lokalen Skype for Business-Bereitstellungen mit Enterprise-VoIP. Diese Organisationen nehmen sich wahrscheinlich Zeit für ein Upgrade auf Teams und möchten so schnell wie möglich von den überlegenen Besprechungen in Teams profitieren.

> [!TIP]
> Um den empfohlenen Upgrademodus basierend auf den Funktionen, die Sie in Teams aktivieren möchten, während Skype for Business noch verwendet wird, zu identifizieren, nutzen Sie den [Skype-zu-Teams-Upgrade-Assistenten.](https://aka.ms/SkypeToTeamsWizard)

Weitere Informationen zu Koexistenzmodi, -voraussetzungen und -verwaltung finden Sie unter Migrations- und Interoperabilitätsleitfaden für Organisationen, die Teams zusammen mit [Skype for Business](https://aka.ms/SkypeToTeams-Interop) verwenden, sowie zum Festlegen Ihrer Koexistenz- und [Upgradeeinstellungen.](https://aka.ms/SkypeToTeams-SetCoexistence)

|Symbol "Entscheidungspunkt" |Symboldefinition |Beschreibung |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Entscheidungspunkt|<ul><li>Welche Koexistenzmodus(en) passen am besten an die Anforderungen Ihrer Organisation und Benutzer?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Nächster Schritt|<ul><li>Wählen Sie den besten Ansatz für Ihren Upgradeweg.</li></ul>|

## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilität von Teams und Skype for Business

Interoperabilität ist die Möglichkeit für Teams- und Skype for Business-Benutzer in derselben Organisation, über Teams und Skype for Business hinweg zu kommunizieren.

Die Interoperabilität unterliegt dem Koexistenzmodus (auch als Upgrademodus bezeichnet) des Empfängers. Es gibt keine Interoperabilität, wenn sich der Empfänger im **Islands-Modus** befindet.

> [!Note]
> Wenn Teams und Skype for Business in einem beliebigen Koexistenzmodus mit Ausnahme von Inseln bereitgestellt **werden,** können Teams und Skype for Business zusammenarbeiten, [](#interoperability-of-teams-and-skype-for-business)sodass Benutzer miteinander chatten und sich anrufen können und sicherstellen, dass die Kommunikation in Ihrer Organisation während des Upgradeverlaufs zu Teams flüssig bleibt. Koexistenzmodi steuern die Interoperabilität. Der Koexistenzmodus des Empfängers bestimmt, ob die Interoperabilität verfügbar ist. Wenn sich der Empfänger beispielsweise in einem Modus befindet, in dem chatten nur in einem Client (z. B. Teams) verfügbar ist, ist die Chatinteroperabilität im Allgemeinen für den Fall verfügbar, dass der andere Client (in diesem Fall Skype for Business) zum Starten des Chats verwendet wird. Wenn sich der Empfänger hingegen in dem Modus befindet, in dem der Chat auf beiden Clients (Islands-Modus) verfügbar ist, steht die Interoperabilität für den Chat nicht zur Verfügung. Die Nachricht wird vom Empfänger in demselben Client empfangen, in dem auch der Chat vom Empfänger gestartet wurde. Daher ist für die ordnungsgemäße Kommunikation im **#A0** eine Sättigung der #A1 erforderlich. d. h., alle Benutzer verwenden und überwachen beide Clients aktiv.

> [!Note]
> **Um die neueste Koexistenzerfahrung zu haben, muss die Clientversion der neueste verfügbare Client im Office-Bereitstellungskanal des Benutzers sein.**

### <a name="native-interop-and-interop-escalation"></a>Systemeigene Inop- und Inopeskalation

Es gibt zwei Arten von Inop-Erfahrungen: systemeigene und Inopeskalation.

- Eine _systemeigene Inoperfahrung_ erfolgt in dem Client, den der Benutzer gerade verwendet. Ein Benutzer ist im Skype for Business-Client, der andere in Teams. Bei einer systemeigenen Inaktivität werden sie nicht zu einem anderen Client für die Kommunikation verwendet. Die Benutzer können ihre Unterhaltung auf dem Zurzeit verwendeten Client führen. Die systemeigenen Inoperfahrungen sind 1:1-Chats und -Anrufe.
- Eine  Inopskalationserfahrung bedeutet, dass der Client als Teil der Unterstützung der Benutzer beim Ausführen einer erweiterten Aktion (z. B. freigeben ihres Desktops) die Erstellung einer Besprechung erleichtert, an der die Benutzer teilnehmen können, um die Erfahrung in dieser Besprechung weiter zu erleben. Die Besprechung wird auf der Plattform der Aktion erstellt. Der oder die Benutzer, die nicht auf dieser Plattform sind, erhalten einen Teilnahmelink für eine Besprechung. Wenn der Benutzer auf diesen Link klickt, wird er der Besprechung in einem kompatiblen Client (Browser, Web App oder vollständiger Client, je nach Konfiguration) beigetreten. Die Inopeskalation von Skype for Business erfordert einen aktuellen Client. Die Inopeskalation von Teams ist jetzt verfügbar. Beide werden in den Interoperabilitätserfahrungen in Mandanten und für mandantenübergreifende Partnerkommunikation unterstützt.

### <a name="native-interop-experiences"></a>Native Inoperfahrungen

Je nach den Benutzern zugewiesenen Koexistenzmodi (wie zuvor beschrieben) stehen die folgenden systemeigenen Inoperfahrungen zur Verfügung:

Skype for Business-Benutzer können 1:1-Chats mit Teams-Benutzern führen und umgekehrt. Ein Inopchat muss über ein Inopgateway gehen, das zu den Teams-Clouddiensten gehört (und daher nur online vorhanden ist). Inopchats sind unformatiert: Rich-Text- und Emoticons werden nicht unterstützt. Benutzer in Teams und in Skype for Business werden benachrichtigt, dass es sich bei der Unterhaltung um eine Inop-Unterhaltung handelt.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business-Benutzer können Sprach- und Videoanrufe mit 1:1 bei Den Benutzern von Teams führen, und Teams-Benutzer können dasselbe tun.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Für die Inopumgebung mit einer lokalen Bereitstellung von Skype for Business muss sich die lokale Umgebung mit Microsoft 365 oder Office 365 Skype for Business im Hybridmodus befinden. Details finden Sie im [Leitfaden zu Migration und Interoperabilität.](https://aka.ms/SkypeToTeams-Interop)

Diese Inoperfahrungen sind für und zwischen Benutzern verfügbar, denen einer der folgenden Koexistenzmodi zugewiesen wurde: **Skype for Business** mit Teams-Zusammenarbeit, Skype for Business mit Zusammenarbeit und Besprechungen in **Teams,** **Skype for Business Only** oder Nur **Teams.** Es gibt keine Interoperabilität für Benutzer im **Islands-Modus.**

### <a name="native-interop-experience-limitations"></a>Einschränkungen der systemeigenen Inoperfahrung

Aufgrund des Unterschieds bei Protokollen und Technologie ist es nicht möglich, alle Funktionen systemeigene zu unterstützen. Insbesondere sind die folgenden Funktionen nicht verfügbar:

- Markdown, Rich-Text und der vollständige Emoticonsatz werden weder in Teams noch in Skype for Business unterstützt. Andere systemeigene Features des Felds zum Verfassen in Teams-Chats werden nicht unterstützt.
- Die Bildschirmfreigabe (Desktop- oder App-Freigabe) zwischen Teams und Skype for Business wird systemintern nicht unterstützt. Es wird jedoch durch eine Inopeskalation unterstützt.
- Gruppenchats (Unterhaltungen mit mehreren Teilnehmern) in Teams können nur Teilnehmer enthalten, die Teams verwenden.
- Chatunterhaltungen mit mehreren Teilnehmern (Gruppenchats) in Skype for Business können nur Teilnehmer umfassen, die Skype for Business verwenden. Die Inopskalation für Mehrere ist jedoch über Skype for Business verfügbar.
- Das Eskalieren eines laufenden Peer-to-Peer-Sprach- oder Videoanrufs zu einem Anruf mit mehreren Personen, an dem sowohl Teams- als auch Skype for Business-Benutzer beteiligt sind, wird nicht unterstützt.
- Die Dateiübertragung für Chats von zwei Personen oder die Dateianlage in Gruppenchats, von Teams zu Skype for Business (und umgekehrt) wird nicht unterstützt.
- Es gibt keine Interoperabilität mit dem beständigen Skype for Business-Chat.

Für alle diese Einschränkungen (mit Ausnahme des beständigen Chats) besteht eine mögliche Problemumgehung dafür, dass ein Benutzer eine Besprechung startet und den anderen Benutzer dazu einlä lädt.

Diese Problemumgehung ist die Grundlage für die Inopeskalation. Insbesondere sind Bildschirmfreigaben und die Ausskalierung für Mehrteiler systemisch nicht erreichbar, werden aber über die Inopeskalation unterstützt.

### <a name="interop-escalation-experiences"></a>Erfahrungen mit der Inopeskalationserfahrung

Die Inopeskalation besteht in der Ergänzung der systemeigenen Inopfunktionen durch verwalteteKalenskalation zu Besprechungen. Besprechungen bieten umfassende Erfahrungen, die jedem zur Verfügung stehen, unabhängig davon, welchen Kunden er hat.

Wenn die Inopskalation durch den Benutzer von Teams ausgelöst wird, wird eine Team-Besprechung erstellt. Wenn sie vom Skype for Business-Benutzer ausgelöst wird, wird eine Skype for Business-Besprechung erstellt. In beiden Fällen handelt es sich bei der erstellten Besprechung um **eine** "Jetzt treffen"-Besprechung, die nicht im Kalender des Benutzers angezeigt wird.

Die andere Partei empfängt den Teilnahmelink für die Besprechung über den Inopchat und nimmt an der Besprechung teil, indem sie auf diesen Link klickt. Wenn der Skype for Business-Benutzer über ein Teams-Konto verfügt und vom Teambenutzer eingeladen wird, wird er authentifiziert an der Besprechung teilnehmen. Andernfalls treten sie als anonymer Teilnehmer bei. Umgekehrt verfügen Benutzer von Teams fast immer über ein Skype for Business-Konto und einen Skype for Business-Client, über den sie als authentifizierter Teilnehmer an einer Skype for Business-Besprechung teilnehmen können. Sie können aber auch als anonymer Teilnehmer teilnehmen, z. B. über die Skype-Besprechungs-App.

Sobald die Teilnehmer der Besprechung beigetreten sind, können sie alle in Besprechungen unterstützten Aktivitäten durchführen, z. B. Desktop- oder Inhaltsfreigabe, Dateifreigabe oder Dateiübertragung, Hinzufügen anderer Teilnehmer und so weiter.

#### <a name="interop-escalation-from-skype-for-business"></a>Inopeskalation von Skype for Business

Die Inop- und Inopskalation von Skype for Business wurde im Juli 2019 im monatlichen C2R aktualisiert. Bisher war Skype for Business nicht bekannt, dass die Remoteparty Teams verwendet hat. Es wurde nur als aus den Signalen, die nach dem Start einer Sitzung empfangen wurden, angenommen.

Wenn durch die Signalisierung angegeben wurde, dass die Antwort von (oder über) das Inopgateway stammte, wurde die gelbe Geschäftsleiste (Banner) angezeigt, die angibt, dass die andere Partei Skype for Business nicht verwendet hat. Mit der Weiterentwicklung unseres Diensts hat dies zu falsch positiven Ergebnisse geführt, bei denen Skype for Business-Benutzern die Geschäftsleiste angezeigt wurde, wenn sie mit dem Cloud Voicemaildienst oder anderen Cloud Voice Services verbunden waren, anstatt mit einem tatsächlichen **Benutzer von Teams Only.**

Um diese falsch positiven Ergebnisse zu verhindern, informiert der Anwesenheitsdienst jetzt den Skype for Business-Client, wenn die andere Partei nur ein tatsächlicher Benutzer von **Teams** ist. Auf diese Weise kann Skype for Business bewusst sein, dass eine Inop-Unterhaltung erstellt werden muss, bevor sie erstellt wurde, und dass das Unterhaltungsfenster für die Inaktivität spezifisch ist.

![Screenshot der Nachricht in Teams zum Erstellen einer Inop-Unterhaltung mit einem Skype for Business-Benutzer](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Wenn der Skype for Business-Benutzer beispielsweise seinen Desktop freigeben möchte, wird er informiert, dass wir eine Besprechung starten und durch die Schritte geführt werden.

![Screenshot der Nachricht "Teams", um eine Besprechung mit einem Teambenutzer zu starten](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Währenddessen erhält der Teams-Benutzer eine eingehende Chatnachricht mit dem Link zur Besprechung und wird zur Teilnahme geführt.

Diese Erkalierung einer Skype for Business-Besprechung ist sowohl für In-Tenant-Inop als auch mandantenübergreifende Partneranrufe und Chats verfügbar. Sie ist standardmäßig aktiviert, und der Administrator muss keine Einstellung bereitstellen.

#### <a name="interop-escalation-from-teams"></a>Inopeskalation von Teams

Die Inopeskalation von Teams zu einer Team-Besprechung ist jetzt verfügbar, wenn der Benutzer der Teams die Desktopfreigabeschaltfläche in einem In-Mandant-Inopthread mit einem Skype for Business-Benutzer oder in einem Mandantenübergreifenden Verbundthread für Inop auswählt. Die Inopeskalation wird von einer 1:1-Chatunterhaltung oder von einem 1:1-Anruf unterstützt.

Die Funktion wird im Teams-Desktopclient für Windows, im Teams-Desktopclient für Mac und im Teams-Webclient in Browsern unterstützt, in denen die Inhaltsfreigabe unterstützt wird, während Sie mit einer beliebigen Skype for Business-Clientversion kommunizieren.

In Interoperabilitätsthreads und in Interoperabilitätsthreads für Verbundbenutzer verfügt der Benutzer von Teams jetzt über die Steuerelemente (Schaltfläche), über die er die Inhaltsfreigabe starten kann. Wenn der Benutzer von Teams die Schaltfläche auswählt, wird ein zusätzliches Menü angezeigt, in dem er darüber informiert wird, dass er zum Teilen von Inhalten eine Team-Besprechung starten muss.

Wenn die Benutzer an einem Anruf teilnen, werden sie über das Menü darüber hinaus gewarnt, dass ihr aktueller Anruf zwischen Teams und Skype for Business beendet wird, wenn sie in eine Teams-Besprechung eintreffen. Wenn sie dies auswählen, können sie den Skype for Business-Benutzer vor der Annahme warnen.

![Screenshot der Nachricht in Teams zum Freigeben einer Besprechung für einen Skype for Business-Benutzer](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Nach der Annahme werden sie in die #A0 eingeladen. sie die Freigabe über den Freigabeschacht in der Besprechung starten müssen.

Währenddessen erhält der Skype for Business-Benutzer eine eingehende Chatnachricht mit dem Link zur Besprechung und wird zur Teilnahme geführt.

Diese Skalierung einer Team-Besprechung ist sowohl für In-Mandant-Inop als auch mandantenübergreifende Partneranrufe und Chats verfügbar. Sie ist standardmäßig aktiviert, und der Administrator muss keine Einstellung bereitstellen. Wenn sich der Administrator auf " einstellt, ist sie für den ``-AllowPrivateMeetNow`` Benutzer jedoch ``CsTeamsMeetingPolicy`` ``$false`` deaktiviert.

Lesen Sie nach dem Lesen dieses Artikels die folgenden verwandten Artikel:

- [Auswählen der Upgrade-Strategie](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Richtlinien für Migration und Interoperabilität](https://aka.ms/SkypeToTeams-Interop)
- [Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md)
-  [Festlegen der Koexistenz- und Upgradeeinstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) für Implementierungsdetails.

## <a name="related-links"></a>Verwandte Links

[Video: Verwalten der Koexistenz und Interoperabilität zwischen SfB und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)
