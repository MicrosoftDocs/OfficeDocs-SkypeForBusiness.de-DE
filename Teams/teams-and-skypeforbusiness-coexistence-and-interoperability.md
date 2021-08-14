---
title: Verständnis Microsoft Teams und Skype for Business Koexistenz und Interoperabilität
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Details zu Skype for Business und Microsoft Teams Koexistenzoptionen und zur resultierenden Interoperabilität zwischen Skype for Business und Teams.
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
ms.openlocfilehash: 9f28ff0d0cffd3cd370d1454c84e6645fea1a2603fa61f9a21f519e84cef5d92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54342770"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Verständnis Microsoft Teams und Skype for Business Koexistenz und Interoperabilität

![Upgrade journey diagram, emphasizing the Project Definition stage](media/upgrade-banner-project-definition.png "Phasen des Upgradeschritts, mit Betonung auf der Stufe Project Definition")

Dieser Artikel ist Teil der Project Stufe "Definition" Ihres Upgrades. Schließen Sie den Vorgang ab, nachdem Sie ein Sponsoringteam und ein Projektteam erstellt und den Umfang, die Ziele und die Planung für Ihr Projekt definiert haben. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)

Wenn Ihre Organisation heute Skype for Business verwendet und Sie Teams zusammen mit Skype for Business verwenden – oder Sie mit dem Upgrade auf Teams beginnen –, ist es wichtig zu verstehen, wie die beiden Anwendungen koexistieren, wann und wie sie interoperativ sind und wie sie die Migration Ihrer Benutzer bis zu ihrem letzten Upgrade von Skype for Business auf Teams verwalten.

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr [über Koexistenz und Interoperabilität zu erfahren.](https://aka.ms/teams-upgrade-coexistence-interop)
>
> Darüber hinaus können Sie an Live-, interaktiven Workshops teilnehmen, in denen wir Anleitungen, bewährte Methoden und Ressourcen teilen, die als Starthilfe für die Planung und Implementierung von Upgrades entwickelt wurden.
>
> Nehmen Sie zuerst [an der Upgradesitzung](./upgrade-workshops-landing-page.yml) planen teil, um zu beginnen.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Koexistenz von Teams und Skype for Business Übersicht

In den folgenden Abschnitten werden die Koexistenzmodi beschrieben, die verfügbar sind, wenn Sie upgrades Teams und die Funktionen, die jeder Modus bietet. Darüber hinaus beschreiben wir die Interoperabilität (Interoperabilität), die zwischen Benutzern auf Skype-for-Business-Clients und Benutzern auf Teams-Clients stattfindet, und wie sich der ausgewählte Koexistenzmodus auf die Interoperabilität ausdient.

 Teams bietet Funktionen für die Zusammenarbeit, Chats, Anrufe und Besprechungen. Je nachdem, wie Sie ihre Teams, überschneiden sich diese Funktionen möglicherweise mit den Funktionen, die von Skype for Business bestimmten Benutzer bereitgestellt werden. Der Standardmodus besteht im Ausführen von Teams mit Skype for Business sich überschneidenden Funktionen. Einem Benutzer kann jedoch einer von mehreren Koexistenzmodi (auch als Upgrademodi bekannt) zugewiesen werden, mit denen sichergestellt werden soll, dass sich diese Funktionen für diesen Benutzer nicht überlappen (in diesem Fall ist die Interoperabilität zwischen Teams und Skype for Business verfügbar). Wenn Sie z. B. über erhebliche Skype for Business Server lokale Ressourcen mit einer komplexen Enterprise-VoIP-Bereitstellung verfügen, ihre Benutzer aber so [](meetings-first.md) schnell wie möglich an modernen Besprechungen teilnehmen lassen möchten, können Sie Besprechungen zuerst als alternativen Pfad auswerten.

Es wird empfohlen, die folgenden Koexistenzmodi zu überprüfen, um zu ermitteln, welcher Pfad für Ihre Organisation am besten ist.

> [!Important]
> Die Koexistenzmodi sind auch nach dem Ende von Skype for Business Online am 31. Juli 2021 weiterhin vorhanden, sind aber nur für Organisationen mit lokalen Bereitstellungen von Skype for Business Server. Kurz vor der Rente kann Benutzern, die in der lokalen Bereitstellung heimisch sind, ein beliebiger anderer Modus als TeamsOnly zugewiesen werden. Nach dem Ende von Skype for Business Online können benutzer, die in der Cloud heimisch sind, jedoch nur TeamsOnly sein.

### <a name="islands-mode"></a>Islands-Modus

Standardmäßig können Benutzer eine Teams als Skype for Business ausführen, die ähnliche und sich überlappende Funktionen bieten. Die Funktionen umfassen Anwesenheit, Chat, Anrufe und Besprechungen. Teams Benutzer können auch die neuen Funktionen für die Zusammenarbeit nutzen, z. B. Teams und Kanäle, den Zugriff auf Dateien in Microsoft 365 oder Office 365 und Anwendungen.

In diesem Koexistenzmodus, der **als Inseln** bezeichnet wird, wird jede Clientanwendung als separate Insel ausgeführt. Skype for Business mit Skype for Business, Teams mit Teams. Benutzer werden davon erwartet, dass sie beide Clients immer ausführen, und sie können systemeigene in dem Client kommunizieren, von dem aus die Kommunikation gestartet wurde. Es ist also keine Interoperabilität im **Islands-Modus** erforderlich.

Um verwirrende oder regressierte Skype for Business zu vermeiden, behandelt die Skype for Business die folgenden Integrationen, die im Modus **"Teams" nicht** behandelt werden:

- Externe Kommunikation (Verbundkommunikation).
- PSTN-Sprachdienste und -Sprachanwendungen, Office Integration.
- HID-Steuerelemente für USB-Geräte.
- Einige weitere Integrationen.  

Telefonsystem wird im Islands-Teams **nicht** unterstützt. **Der** Islands-Modus unterstützt nicht Enterprise-VoIP Client ist Skype for Business.

> [!Important]
> Im **Islands-Modus** werden alle Nachrichten und Anrufe von Partnerbenutzern (Personen außerhalb Ihrer Organisation) an die Skype for Business. Nach dem Upgrade Teams auf den **Only-Modus** werden alle Nachrichten und Anrufe von außerhalb Ihrer Organisation an den Teams.

> [!Tip]
> Skype for Business Für Onlinekunden wird empfohlen,  mit dem Standardmodus Islands zu beginnen, die Sättigung Teams Organisation zu erhöhen und dann in den Teams **Nur** Modus zu wechseln. Lokale und Hybridkunden, insbesondere komplexe Kunden, können davon profitieren, wenn sie das Skype for Business Skype for Business  mit dem **Teams-Zusammenarbeitsmodus** als Ausgangspunkt und nicht im Modus Islands bereitstellen und von dort  aus im **Teams-Modus** für Zusammenarbeit und Besprechungen (gegebenenfalls besprechungs zuerst) zum Teams Nur-Modus wechseln, wenn die Organisation bereit für die Einführung von Teams ist.

### <a name="teams-only"></a>Teams Nur

Ein **Teams (auch** als aktualisierter  Benutzer bezeichnet) hat Zugriff auf alle Funktionen in Teams. Er behält den Kunden Skype for Business, an Besprechungen Skype for Business, die von Benutzern ohne Upgrade oder externen Parteien organisiert wurden, teilzunehmen. Ein aktualisierter Benutzer kann weiterhin mit anderen Benutzern in der Organisation kommunizieren, die weiterhin Skype for Business verwenden, indem die Interoperabilitätsfunktionen zwischen Teams  und Skype for Business verwendet werden (vorausgesetzt, die Skype for Business-Benutzer befinden sich nicht im Islands-Modus). Ein Aktualisierter Benutzer kann jedoch keine Chat-, Skype for Business- oder Besprechungssitzung starten.

Sobald Ihre Organisation für einige oder alle Benutzer bereit ist, Teams als einziges Kommunikations- und Zusammenarbeitstool zu verwenden, führen Sie ein Upgrade dieser Benutzer auf den Teams **Aus.** Wenn Sie das  Upgrade vom Islands-Modus durchführen, empfiehlt es sich, vor dem Beginn des Upgradeprozesses Teams Sättigung der Übernahme in Ihrer Organisation zu erhalten. Durch diese Einführung werden unterbrochene Kommunikationsszenarien vermieden, da **der Islands-Modus** keine Interoperabilität bietet.

Im Teams **ist** Teams die Standard-App für das SIP/Tel-Protokoll. Links auf der Visitenkarte eines Benutzers in Outlook für Anrufe oder Chats werden von der Teams.

Weitere Überlegungen zum Wechseln in den **Teams-Modus** finden Sie unter Teams [Nur Modusaspekte.](teams-only-mode-considerations.md)

![Screenshot der Teams Bestätigungsmeldung](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business client, der in einem speziellen Modus ausgeführt wird, nachdem der Benutzer als Teams-Only-Benutzer aktualisiert wurde")

### <a name="skype-for-business-only"></a>Nur Skype for Business

In diesem Koexistenzmodus verbleiben Benutzer Skype for Business (nicht Teams) für Chat-, Besprechungs- und Anruffunktionen, und sie verwenden Teams für Teams und Kanäle nicht. Dieser Modus ist heute verfügbar. in der aktuellen Implementierung werden Teams und Kanäle jedoch nicht automatisch für den Benutzer deaktiviert. Dies erreichen Sie, indem Sie die App-Setup-Richtlinie verwenden, um Teams und Dateien auszublenden.

Dieser Modus kann vor dem Starten einer verwalteten Bereitstellung von Teams verwendet werden, um zu verhindern, dass Benutzer mit der Nutzung von Teams, bevor sie die Bereitschaft aufgebaut haben. Dieser Modus ist auch eine Möglichkeit, authentifizierte Teilnahme an Teams-Besprechungen für Skype for Business-Benutzer zu aktivieren, sofern die Benutzer für die Teilnahme Teams.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business mit Teams Zusammenarbeit

Verwenden Sie diesen Modus, um Teams in Ihrer Umgebung zu vorstellen, während Sie Ihre bestehenden Investitionen weiterhin in Skype for Business. Lassen Skype for Business Chat-, Anruf- und Besprechungsfunktionen unverändert. Hinzufügen Teams Funktionen für die Zusammenarbeit:

- Teams und Kanäle.
- Zugriff auf Dateien in Microsoft 365 Oder Office 365.
- Anwendungen. Teams Kommunikationsfunktionen – privater Chat, Anrufe und Planen von Besprechungen.

Teams privaten Chat, Anrufe und Planen von Besprechungen sind in diesem Modus standardmäßig deaktiviert.

Organisationen mit einem Ausgangspunkt von Skype for Business Server lokal oder hybrid sollten diesen  Modus als Alternative zum Islands-Modus betrachten, wenn sie ihren Benutzern Interoperabilität und Vorhersagbarkeit für ihre Kommunikation bieten möchten, sowie  über einen vorhersehbaren Zeitplan für das Upgrade auf Teams (im Gegensatz zur Annahmesättigung im Islands-Modus).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business mit Teams Zusammenarbeit und Besprechungen, auch bekannt als "Besprechungen First"

Verwenden Sie diesen Koexistenzmodus, um die Teams von Besprechungs- und Zusammenarbeitsfunktionen in Ihrer Organisation zu beschleunigen. Im Koexistenzmodus können Benutzer die Vorteile der überlegenen Teams Besprechungen nutzen:

- Großartige Qualität.
- Transkription und Übersetzung.
- Weichbild des Hintergrunds
- Überlegen Sie sich die Benutzerfreundlichkeit auf allen Plattformen, einschließlich mobiler Geräte und Browser.

Neben der Verwendung Teams für Teams und kanalbasierte Unterhaltungen in diesem Modus verwenden Benutzer Teams zum Planen und Durchführen ihrer Besprechungen. Private Chats und Anrufe bleiben auf Skype for Business. Teams und Skype for Business von einer Reihe von "besser gemeinsam"-Funktionen profitieren, z. B. Anwesenheitsabgleich, automatisches Halten/Nichtbehalten und Unterstützung von HID-Geräten in beiden Anwendungen. Sie können Teams und Kanäle bei Bedarf mithilfe der Richtlinie für die App-Einrichtung ausblenden.

Dieser Koexistenzmodus ist besonders hilfreich für Organisationen mit Skype for Business lokalen Bereitstellungen mit Enterprise-VoIP. Diese Organisationen nehmen sich wahrscheinlich etwas Zeit für das Upgrade auf Teams und möchten so schnell wie möglich von den besprechungsbesprechungen Teams profitieren.

> [!TIP]
> Um den empfohlenen Upgrademodus basierend auf den Funktionen zu identifizieren, die Sie in Teams aktivieren möchten, während Skype for Business noch verwendet wird, verwenden Sie den Assistenten Skype, um Teams [zu starten.](https://aka.ms/SkypeToTeamsWizard)

Weitere Informationen zu Modi, Voraussetzungen und Verwaltung der Koexistenz finden Sie unter Migrations- und Interoperabilitätsleitfaden für Organisationen, die Teams zusammen mit Skype for Business verwenden, und Festlegen der Einstellungen [für](./migration-interop-guidance-for-teams-with-skype.md) Koexistenz und [Upgrade.](./setting-your-coexistence-and-upgrade-settings.md)

|Symbol 'Entscheidungspunkt' |Symboldefinition |Beschreibung |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Entscheidungspunkt|<ul><li>Welche Koexistenzmodus(en) passen am besten zu den Anforderungen Ihrer Organisation und der Benutzer?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Nächster Schritt|<ul><li>Wählen Sie den besten Ansatz für Ihre Upgradereise aus.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilität von Teams und Skype for Business

Interoperabilität ist die Möglichkeit, Teams und Skype for Business Benutzern in derselben Organisation zu ermöglichen, über Teams und Skype for Business.

Die Interoperabilität unterliegt dem Koexistenzmodus (auch als Upgrademodus bezeichnet) des Empfängers. Es gibt keine Interoperabilität, wenn sich der Empfänger im **Islands-Modus** befindet.

> [!Note]
> Wenn die Bereitstellung in einem beliebigen Koexistenzmodus mit [](#interoperability-of-teams-and-skype-for-business)Ausnahme von **Inseln,** Teams und Skype for Business ausgeführt wird, können die Benutzer miteinander chatten und sie anrufen. Außerdem wird sichergestellt, dass während des Upgradeverlaufs zu Teams eine flüssige Kommunikation in der gesamten Organisation bleibt. Die Interoperabilität wird durch die Koexistenzmodi bestimmt. Der Koexistenzmodus des Empfängers bestimmt, ob die Interoperabilität verfügbar ist. Wenn sich der Empfänger beispielsweise in einem Modus befindet, in dem chatten nur in einem Client (z. B. Teams) verfügbar ist, ist die Chatinteroperabilität im Allgemeinen für den Fall verfügbar, dass der Kunde den anderen Client (in diesem Fall Skype for Business) zum Starten des Chats verwendet. Wenn sich der Empfänger jedoch in dem Modus befindet, in dem chatten in beiden Clients (Islands-Modus) verfügbar ist, steht die Interoperabilität für den Chat nicht zur Verfügung. Die Nachricht wird vom Empfänger in demselben Client empfangen, in dem auch das Video den Chat gestartet hat. Daher ist für die ordnungsgemäße Kommunikation im **Islands-Modus** eine Teams Sättigung der Verbreitung erforderlich; das heißt, dass alle Benutzer beide Clients aktiv verwenden und überwachen.

> [!Note]
> **Um die neueste Koexistenzerfahrung zu haben, muss es sich bei der Clientversion um den neuesten verfügbaren Client im Kanal Office des Benutzers.**

#### <a name="native-interop-and-interop-escalation"></a>Systemeigene Inaktivität und Inopeskalation

Es gibt zwei Arten von Inop-Erfahrungen: systemeigene und Inopeskalation.

- Eine _systemeigene In interop-Benutzeroberfläche_ tritt auf dem Client auf, den der Benutzer gerade verwendet. Ein Benutzer wird im Client Skype for Business, der andere in der Teams. Eine systemeigene In interop-Erfahrung verwendet sie nicht zu einem anderen Client, um zu kommunizieren. Die Benutzer können ihre Unterhaltung in dem Client führen, den sie gerade verwenden. Die systemeigenen In interop-Erfahrungen sind 1:1-Chats und -Anrufe.
- Eine _Inopeskalationserfahrung_ bedeutet, dass der Client im Rahmen der Unterstützung der Benutzer bei der Durchführung einer erweiterten Aktion (wie dem Freigeben ihres Desktops) die Erstellung einer Besprechung erleichtert, an der die Benutzer teilnehmen können, um die Erfahrung in dieser Besprechung weiter zu erleben. Die Besprechung wird auf der Plattform der "Aktion" erstellt. Die Benutzer, die nicht auf dieser Plattform sind, erhalten einen Teilnahmelink für die Besprechung. Wenn die eingeladenen Benutzer auf diesen Link klicken, werden sie an der Besprechung in einem kompatiblen Client (Browser, Web-App oder vollständiger Client, je nach Konfiguration) teil. Die Inopeskalation von Skype for Business erfordert einen kürzlich verwendeten Client. Die Inopeskalation Teams ist jetzt verfügbar. Beide werden in Interoperabilitätserfahrungen in Mandanten und mandantenübergreifende Partnerkommunikation unterstützt.

#### <a name="native-interop-experiences"></a>Systemeigene In interop-Be erleben

Je nach den Benutzern zugewiesenen Koexistenzmodi (wie zuvor beschrieben) stehen die folgenden systemeigenen Inaktivitätserfahrungen zur Verfügung:

Skype for Business Benutzer können mit anderen Benutzern Teams chatten und umgekehrt. Ein Inop-Chat muss über ein Inop-Gateway gehen, das zu Teams Clouddiensten gehört (und daher nur online verfügbar ist). Inop-Chats sind nur Text: Rich-Text und Emoticons werden nicht unterstützt. Benutzer in Teams und in Skype for Business werden benachrichtigt, dass es sich bei der Unterhaltung um eine Inop-Unterhaltung handelt.

<!--![Screen shot of Interop chat experience from Teams](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business-Benutzer können Sprach- und Videoanrufe mit Teams 1:1-Benutzern und Teams Benutzer können dasselbe tun.

<!--![Screen shot of Interop calling experience from Teams](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Interop-Erfahrungen mit einer lokalen Bereitstellung von Skype for Business erfordern, dass sich die lokale Umgebung im Hybridmodus mit Microsoft 365 oder Office 365 Skype for Business. Details finden Sie unter [Migrations- und Interoperabilitätsleitfade.](./migration-interop-guidance-for-teams-with-skype.md)

Diese Inaktivität ist für Benutzer verfügbar und zwischen diesen, denen einer der folgenden Koexistenzmodi zugewiesen ist: Skype for Business mit **Teams** Zusammenarbeit, **Skype for Business** mit Teams Zusammenarbeit und Besprechungen, **Skype for Business Nur** oder **nur** Teams . Es gibt keine Interoperabilität für Benutzer im **Islands-Modus.**

#### <a name="native-interop-experience-limitations"></a>Einschränkungen bei der Systemeigenen In interop experience

Aufgrund des Unterschieds bei Protokollen und Technologien ist es nicht möglich, alle Funktionen systemeigene zu unterstützen. Insbesondere sind die folgenden Funktionen nicht verfügbar:

- Markdown, Rich-Text und der vollständige Emoticon-Satz werden weder auf der Teams noch Skype for Business. Andere systemeigene Features des Felds zum Verfassen in Teams Chats werden nicht unterstützt.
- Bildschirmfreigaben (Desktop- oder App-Freigabe) zwischen Teams und Skype for Business werden systemeigene nicht unterstützt. Es wird jedoch durch eine Inopeskalation unterstützt.
- Gruppenchats (Unterhaltungen mit mehreren Teilnehmern) in Teams können nur Teilnehmer enthalten, die ihre Teams.
- Chatunterhaltungen mit mehreren Teilnehmern (Gruppenchats) in Skype for Business können nur Teilnehmer enthalten, die die Chatunterhaltungen Skype for Business. Die Inopeskalation für mehrere Parteien ist jedoch über die Skype for Business.
- Eskalieren eines laufenden Peer-to-Peer-Sprach- oder Videoanrufs zu einem Mehrteilnehmeranruf, an dem sowohl Teams als auch Skype for Business-Benutzer beteiligt sind, wird nicht unterstützt.
- Die Dateiübertragung für Zwei-Party-Chats oder Dateianlage in Gruppenchats, von Teams zu Skype for Business und umgekehrt, wird nicht unterstützt.
- Es gibt keine Interoperabilität mit dem Skype for Business Beständiger Chat.

Für alle diese Einschränkungen (mit Ausnahme des beständigen Chats) besteht eine mögliche Problemumgehung dafür, dass ein Benutzer eine Besprechung startet und den anderen Benutzer zur Teilnahme einlädt.

Diese Problemumgehung ist die Grundlage für die Inopeskalation. Insbesondere bildschirmfreigabe und -eskalation für Mehrteiler sind systemeigene nicht erreichbar, werden aber über die Inopeskalation unterstützt.

#### <a name="interop-escalation-experiences"></a>Interop-Eskalationserfahrungen

Die Inopeskalation besteht in der Ergänzung der systemeigenen Inopfunktionen durch verwaltete Eskalationen zu Besprechungen. Besprechungen bieten für jeden ein umfassendes Erlebnis, unabhängig davon, welchen Kunden er hat.

Wenn die Inopeskalation durch den Teams ausgelöst wird, wird Teams Besprechung erstellt. Wenn sie vom Benutzer ausgelöst Skype for Business, wird Skype for Business Besprechung erstellt. In beiden Fällen handelt es sich bei der erstellten Besprechung um **eine** "Jetzt treffen"-Besprechung, die nicht im Kalender des Benutzers angezeigt wird.

Die andere Partei empfängt den Teilnahmelink für die Besprechung über den Inop-Chat und nimmt an der Besprechung teil, indem sie auf diesen Link klickt. Wenn der Skype for Business über ein Teams-Konto verfügt und vom Teams-Benutzer eingeladen wird, wird er authentifiziert an der Besprechung teilnehmen. Andernfalls treten sie als anonymer Teilnehmer bei. Im Gegensatz dazu Teams Benutzer fast immer über ein Skype for Business-Konto und einen Skype for Business-Client verfügen, können sie als authentifizierter Teilnehmer an einer Skype for Business-Besprechung teilnehmen, aber sie können auch als anonymer Teilnehmer teilnehmen, z. B. über die Skype-Besprechung-App.

Sobald die Parteien der Besprechung beigetreten sind, können sie alle unterstützten Aktivitäten in Besprechungen durchführen, z. B. Desktop- oder Inhaltsfreigabe, Dateifreigabe oder -übertragung, Hinzufügen anderer Teilnehmer und so weiter.

#### <a name="interop-escalation-from-skype-for-business"></a>Inopeskalation von Skype for Business

Die Inop- und Inopeskalation des Skype for Business wurde im Juli 2019-Build des monatlichen C2R aktualisiert. In früheren Skype for Business die Remoteparty nicht informiert, dass die Remoteparty das Teams. Es wurde nur angenommen, dass die Signalisierung, die empfangen wurde, nachdem eine Sitzung eingerichtet wurde.

Wenn als Signal signalisiert wurde, dass die Antwort von dem Inop-Gateway stammt (oder über das Inop-Gateway), zeigte es die gelbe Leiste (das Banner) an, die angibt, dass die andere Partei nicht die Skype for Business. Mit der Weiterentwicklung unseres Diensts hat dies zu falsch positiven Meldungen geführt, bei denen Skype for Business-Benutzer die Geschäftsleiste sehen, wenn sie mit dem Cloud-Voicemail-Dienst oder anderen Cloud-Sprachdiensten verbunden waren, statt mit einem tatsächlichen **Teams Only-Benutzer.**

Um diese falsch positiven Ergebnisse zu verhindern, informiert der Anwesenheitsdienst jetzt den Skype for Business-Client, wenn die andere Partei ein **Teams Nur tatsächlicher** Benutzer ist. Auf diese Weise Skype for Business bewusst sein, dass vor der Erstellung eine Inop-Unterhaltung erstellt werden muss und dass das Unterhaltungsfenster für die Inaktivität spezifisch ist.

![Screenshot der Nachricht Teams, um eine Inop-Unterhaltung mit einem Benutzer Skype for Business erstellen](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Wenn der Skype for Business beispielsweise seinen Desktop freigeben möchte, wird er informiert, dass wir eine Besprechung starten und durch die Schritte geführt werden.

![Screenshot einer Teams, um die Besprechung mit einem Benutzer Teams starten](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

Währenddessen erhält der Teams eine eingehende Chatnachricht mit dem Link zur Besprechung und wird zur Teilnahme geführt.

Diese Eskalierung zu Skype for Business Besprechung ist sowohl für In-Tenant-Inop als auch mandantenübergreifende Partneranrufe und Chats verfügbar. Sie ist standardmäßig aktiviert, und es gibt keine Einstellung, die der Administrator bereitstellen muss.

#### <a name="interop-escalation-from-teams"></a>Inopeskalation von Teams

Die Inopeskalation von Teams zu einer Teams-Besprechung ist jetzt verfügbar, wenn der Teams-Benutzer die Desktopfreigabeschaltfläche in einem In-Tenant-Inop-Thread mit einem Skype for Business-Benutzer oder in einem Verbundthread für In-Tenant Interop auswählt. Die Inopeskalation wird bei einer 1:1-Chatunterhaltung oder einem 1:1-Anruf unterstützt.

Die -Funktion wird im Teams-Desktopclient für Windows, im Teams-Desktopclient für Mac und im Teams-Webclient in Browsern unterstützt, in denen Die Inhaltsfreigabe unterstützt wird, während die Kommunikation mit einer beliebigen Skype for Business-Clientversion ausgeführt wird.

In Interoperabilitätsthreads und in Interoperabilitätsthreads des Verbunds verfügt der Benutzer Teams jetzt über die Steuerelemente (Schaltfläche), über die die Inhaltsfreigabe gestartet werden kann. Wenn der Teams die Schaltfläche auswählt, wird ihm ein zusätzliches Menü angezeigt, in dem er darüber informiert wird, dass er zum Freigeben von Inhalten eine Besprechung Teams muss.

Wenn die Benutzer in einem Anruf waren, werden sie auch über das Menü darauf gewarnt, dass ihr aktueller Anruf zwischen Teams und Skype for Business beendet wird, wenn sie in eine Besprechung Teams werden. Sie können den Benutzer vor der Annahme Skype for Business warnen.

![Screenshot der Teams, um eine Besprechung für einen Benutzer Skype for Business freigeben](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Nach der Annahme werden sie in die Besprechung Teams eingeladen. sie die Freigabe über den Freigabeschacht in der Besprechung starten müssen.

Währenddessen erhält Skype for Business Benutzer eine eingehende Chatnachricht mit dem Link zur Besprechung und wird durch die Teilnahme geführt.

Diese Eskalierung zu Teams Besprechung ist sowohl für In-Mandant-Inop als auch mandantenübergreifende Partneranrufe und Chats verfügbar. Sie ist standardmäßig aktiviert, und es gibt keine Einstellung, die der Administrator bereitstellen muss. Sie ist jedoch für den Benutzer deaktiviert, wenn der Administrator ``-AllowPrivateMeetNow`` auf ``CsTeamsMeetingPolicy`` ein ``$false`` setzt.

Nachdem Sie diesen Artikel [](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)überprüft haben, lesen Sie Auswählen Ihres Upgradewegs, Anleitungen für Migration und Interoperabilität, [](./migration-interop-guidance-for-teams-with-skype.md) [Koexistenz](coexistence-chat-calls-presence.md)mit Skype for Business und Festlegen der [Koexistenz-](./setting-your-coexistence-and-upgrade-settings.md) und Upgradeeinstellungen für Implementierungsdetails. Außerdem wird das folgende Video empfohlen: [Video: Verwalten der Koexistenz und Interoperabilität zwischen SfB und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Technische Details der Teams und Skype for Business Koexistenz

In den folgenden Abschnitten wird das Verhalten zusammengefasst, das bei der Ausführung von Teams- und Skype for Business-Clients in derselben Organisation auftreten kann, unabhängig davon, welcher Modus und welche Upgrademethode verwendet wird:

- [Besprechungen](#meetings)
- [Interoperabilität](#interoperability)
- [Inaktivität im Vergleich zu systemeigenen Unterhaltungsthreads](#interop-versus-native-conversation-threads)
- [Anwesenheit](#presence)
- [Partnerverbund](#federation)
- [Kontakte](#contacts)

### <a name="meetings"></a>Besprechungen

Unabhängig vom Modus können Benutzer immer an jeder Art von Besprechung teilnehmen, zu der sie eingeladen werden, ganz gleich, ob es sich um Skype for Business oder Teams.  Benutzer müssen jedoch mit einem entsprechenden Client, der dem Besprechungstyp entspricht, an der Besprechung teilnehmen:

- Wenn es sich bei der Besprechung um eine Teams-Besprechung handelt, verwenden alle Teilnehmer (ganz gleich, ob es sich um TeamsOnly-, Islands- oder Skype for Business-Benutzer handelt) den Teams-Client, um an der Besprechung teilnehmen. Wenn Teams installiert ist, wird der Benutzer nach dem Versuch, an einer Besprechung teilnehmen, an das Web geleitet.

- Wenn es sich bei der Besprechung um eine Skype for Business-Besprechung handelt, verwenden alle Teilnehmer (ganz gleich, ob es sich um TeamsOnly-, Islands- oder Skype for Business-Benutzer handelt) den Skype for Business-Client, um an der Besprechung teilnehmen. Wenn der Skype for Business nicht installiert ist, wird der Benutzer zum Teilnehmen über die Skype-Besprechung-App an das Web geleitet.

Beim Organisieren von Besprechungen basiert der besprechungstyp, der geplant wird, auf dem Modus des Organisators, wie in der folgenden Tabelle dargestellt:

| Organisatormodus    |      Verhalten |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Alle in einer Besprechung geplanten Teams. Skype for Business-Add-In ist in der Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Alle in einer Besprechung geplanten Skype for Business. Teams-Add-In ist in der Outlook. | 
| Inselmodus | Besprechungen können standardmäßig entweder in einer Besprechungssitzung Skype for Business oder Teams. Beide Add-Ins sind in Outlook. Sie können jedoch optional verlangen, dass Benutzer auf den Inseln Besprechungen immer in Teams planen, indem Sie ihnen eine Instanz von TeamsMeetingPolicy mit dem PreferredMeetingProviderForIslandsMode=Teams.| 


### <a name="interoperability"></a>Interoperabilität

Wie oben unter [Interoperabilität](#interoperability-of-teams-and-skype-for-business)von Teams und Skype for Business Teams unterstützt Skype for Business in bestimmten Szenarien Die Interoperabilität mit Skype for Business unterstützt. Interop communication refers to a chat or call between a Skype for Business user and a Teams user.  Interop communication is only possible between two users; Chats/Anrufe mit mehreren Parteien oder das Hinzufügen zusätzlicher Benutzer werden nicht unterstützt.

Ein Inop-Chat oder -Anruf zwischen zwei Benutzern wird erstellt, wenn die folgenden Bedingungen zutreffen:

- Ein Benutzer verwendet Teams und der andere Skype for Business.

- Der Modus des Empfängers der ersten Kommunikation ist NOT Islands (andernfalls würde die Kommunikation auf demselben Client landen), wenn sich beide Benutzer in derselben Organisation befinden. In Partnerszenarien verwendet der sendende Benutzer Teams und der Empfänger befindet sich nicht im TeamsOnly-Modus. 

- Der Teams verfügt NICHT auch über ein Skype for Business lokal benutzerdefiniertes Konto.

Innerhalb der Inopkommunikation ist Chat nur Nur-Text. Darüber hinaus sind Dateifreigaben und Bildschirmfreigaben *im Inopchat selbst nicht möglich.* Benutzer in einer Inop-Unterhaltung können jedoch ganz einfach Dateien und/oder Bildschirmfreigaben erreichen, indem sie eine on-demand-Besprechung aus dem Inop-Chat erstellen, wie unten beschrieben:

- Wenn der Teams-Benutzer versucht, seinen Bildschirm zu teilen, wird automatisch eine auf Abruf ausgeführte Teams-Besprechung erstellt und ein Einladungslink zu dieser Besprechung an den Client des Skype for Business-Benutzers gesendet. Wenn der Benutzer auf den Link Skype for Business, öffnet er Teams und tritt der Besprechung bei. Beide Benutzer befinden sich nun in Teams Besprechung und können nach Bedarf freigeben.

- Wenn der Skype for Business-Benutzer einen Client ab 2018 verwendet und versucht, Inhalte zu teilen, wird automatisch eine auf Abruf ausgeführte Skype for Business-Besprechung erstellt, und ein Einladungslink zu dieser Besprechung wird an den Client des Teams-Benutzers gesendet. Durch Klicken auf den Link versucht Teams Benutzer, an der Besprechung Skype for Business teilnehmen. Wenn der Teams-Benutzer den Skype for Business-Client installiert hat, wird er geöffnet, und der Benutzer wird aufgefordert, sich anmelden (sofern nicht bereits angemeldet).  Wenn der Teams nicht über den installierten Skype for Business-Client verfügt, wird der Benutzer aufgefordert, die Webversion zu verwenden. Sobald sich beide Benutzer angemeldet haben, befinden sie sich in Skype for Business Besprechung und können nach Bedarf freigeben.

### <a name="interop-versus-native-conversation-threads"></a>Inaktivität im Vergleich zu systemeigenen Unterhaltungsthreads

Da die In interop communications nicht alle Features der systemeigenen Teams-Unterhaltung unterstützt, verwaltet der Teams-Client separate Unterhaltungsthreads für Teams-to-Teams- und Teams-to-Skype for Business-Kommunikation. Diese Unterhaltungen werden auf der Benutzeroberfläche anders gerendert: Interop-Threads können von einem normalen systemeigenen Thread unterschieden Teams durch:

- Fehlende Steuerelemente für Rich-Text, Datei-/Bildschirmfreigabe, Unfähigkeit, Benutzer hinzuzufügen.
- Eine Änderung am Symbol des Zielbenutzers mit einem "S" für Skype for Business.

Die folgenden Screenshots zeigen folgende Unterschiede:

Eine systemeigene Teams-to-Teams-Unterhaltung mit Dem Benutzer G3-Test

![Diagramm mit einer systemeigenen Teams-to-Teams-Unterhaltung](media/teams-upgrade-native-thread.png)

Eine Inop-Unterhaltung mit demselben Benutzer-G3-Test

![Diagram showing an interop Teams-to-Teams conversation](media/teams-upgrade-interop-thread.png)

Sobald ein Unterhaltungsthread erstellt wurde, ändert sich dessen Typ nie. Nachdem ein Inopthread in Teams erstellt wurde, wird er immer an den Client des Skype for Business des Zielbenutzers geroutet. Ein systemeigener Thread wird immer zum Client des Zielbenutzers Teams routen.  Wenn sich der Modus eines Empfängers ändert, funktionieren vorhandene Teams-Threads an diesen Benutzer nicht mehr, und in diesem Chat wird eine Notiz mit einem Link zum Starten einer neuen systemeigenen Unterhaltung angezeigt, wie im folgenden Screenshot gezeigt.

![Diagramm eines Chats mit aktualisierten Skype for Business Benutzer](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Anwesenheit

Die Anwesenheit eines bestimmten Benutzers basiert auf der Aktivität des Benutzers im Dienst über den Client. Die Anwesenheit wird dann veröffentlicht, damit andere Benutzer sie sehen können.  Skype for Business und Teams sind separate Dienste mit separaten Clients, sodass jeder Dienst über einen eigenen Anwesenheitsstatus für einen Benutzer verfügt.   Darüber hinaus besteht eine Synchronisierung zwischen den Anwesenheitsdiensten in Teams und in Skype for Business Online.  Dadurch kann ein Dienst bei Bedarf das Vorhandensein des Benutzers aus dem anderen Dienst veröffentlichen. 

Das Verhalten bei der Veröffentlichung von Anwesenheitsinformationen basiert auf dem Modus des Benutzers. Es gibt drei grundlegende Fälle:

- Wenn sich ein Benutzer im TeamsOnly-Modus befindet, sehen alle Teams Anwesenheitsinformationen für diesen Benutzer, unabhängig davon, welchen Client er verwendet.

- Wenn sich ein Benutzer in einem der Skype for Business-Modi befindet, sehen alle anderen Benutzer Skype for Business Anwesenheitsinformationen für diesen Benutzer, unabhängig davon, welchen Client sie verwenden.

- Wenn sich ein Benutzer im Islands-Modus befindet, sind die in Skype for Business und Teams veröffentlichten Anwesenheitsinformationen unabhängig, sodass die Anwesenheitsinformationen, die Benutzern in derselben Organisation angezeigt werden, vom Client des anderen Benutzers abhängen. Benutzer in Partnerorganisationen sehen das Vorhandensein dieses Benutzers basierend auf seiner Skype for Business-Aktivität, da Der Verbundverkehr zu einem Benutzer im Modus Islands in Skype for Business.

Angenommen, Benutzer A befindet sich im Islands-Modus. Wenn Benutzer A in Teams aktiv ist, aber nicht bei Skype for Business angemeldet ist, würden andere Benutzer Benutzer A in ihrem Teams-Client als aktiv sehen, aber in ihrem Skype for Business-Client würde Benutzer A als offline angezeigt. Dies ist von Grund auf möglich, da Benutzer A nicht erreicht werden kann, wenn der Client nicht ausgeführt wird. 


### <a name="federation"></a>Partnerverbund

Für einen Verbund von Teams zu einem anderen Benutzer, der Skype for Business verwendet, muss der Teams online in einem Skype for Business. TeamsUpgradePolicy regelt das Routing für eingehende Partnerchats und Anrufe. Das Verhalten des Partnerroutings ist mit dem für Szenarien mit demselben Mandanten identisch, außer im Islands-Modus. Wenn sich die Empfänger im Islands-Modus befinden:

- Chats und Anrufe, die von einem Teams initiiert werden, werden Skype for Business, wenn sich der Empfänger in einem Partner-Mandanten befindet.
- Chats und Anrufe, die von einem Teams initiiert werden, werden Teams, wenn sich der Empfänger im gleichen Mandanten befindet.
- Chats und Anrufe, die von einer anderen Skype for Business, landen immer auf Skype for Business.

Ein Partnerchat kann entweder ein systemeigener Thread oder ein Inopthread sein. Weitere Informationen [finden Sie unter Inaktivität im Vergleich zu systemeigenen Unterhaltungsthreads.](#interop-versus-native-conversation-threads)

- Wenn Empfänger und Absender beide im TeamsOnly-Upgrademodus sind, handelt es sich bei der Unterhaltung um eine systemeigene Chaterfahrung mit sämtlichen Funktionen für Nachrichten und Anrufe. Weitere Informationen finden Sie unter Native Chaterfahrung für [externe Benutzer (Partnerbenutzer) in Teams.](native-chat-for-external-users.md) 

- Wenn sich einer der Unterhaltungsteilnehmer NICHT im TeamsOnly-Upgrademodus befindet, bleibt die Unterhaltung eine Inkonsistenzerfahrung mit Nur-Text-Nachrichten. Die Benutzeroberfläche macht Partnerchats auf ähnliche Weise wie Inopthreads mit demselben Mandanten verfügbar, es sei denn, es gibt eine Notiz, die angibt, dass sich der Benutzer extern befindet.

Weitere Informationen finden Sie unter Verwalten des externen [Zugriffs in Microsoft Teams](manage-external-access.md) und Systemeigene Chaterfahrung für externe Benutzer [(Verbundbenutzer) in Teams.](native-chat-for-external-users.md)

### <a name="contacts"></a>Kontakte

Teams und Skype for Business über separate Kontaktlisten verfügen. Dies bedeutet, dass Ergänzungen, Entfernungen und Änderungen von Kontakten, die in einem System vorgenommen werden, nicht mit dem anderen System synchronisiert werden. Kontakte aus einem Skype for Business werden jedoch automatisch in das Teams, wenn eines von zwei bestimmten Ereignissen auftritt: 

- Bei jedem Skype for Business Online-Benutzer werden Bei der ersten Anmeldung bei Teams Kontakte aus Skype for Business in die Teams.  Dieses Verhalten ist für Benutzer mit einem lokalen Konto in der lokalen Skype for Business Server.  

- Nachdem ein Benutzer auf TeamsOnly aktualisiert wurde (entweder durch Zuweisen von TeamsUpgradePolicy oder über Move-CsUser -MoveToTeams), werden vorhandene Kontakte in Skype for Business, wenn sich ein Benutzer das nächste Mal bei Teams anmeldet, mit vorhandenen Kontakten in Teams zusammengeführt. Dieses Verhalten tritt auf, wenn der Benutzer in TeamsOnly von der lokalen oder online verschoben wurde. 

In beiden Fällen ist die Übertragung von Kontakten von Skype for Business zu Teams asynchron, daher kann es ein paar Minuten dauern, bis die Kontakte in einer Teams. Die beiden oben aufgeführten Ereignisse lösen die Kopie aus.  

### <a name="related-links"></a>Links zu verwandten Themen

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md) 

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
