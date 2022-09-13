---
title: Grundlegendes zu Microsoft Teams und Skype for Business Koexistenz und Interoperabilität
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Details zu Skype for Business- und Microsoft Teams-Koexistenzoptionen und der daraus resultierenden Interoperabilität zwischen Skype for Business und Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: 6d1b5604d5b76d0f642fe26a4ec9777060b9d5ef
ms.sourcegitcommit: 9de6b0b03f433e71fe239d292387eed33c11b531
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2022
ms.locfileid: "67657335"
---
# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Grundlegendes zu Microsoft Teams und Skype for Business Koexistenz und Interoperabilität

![Upgrade-Reisediagramm mit Betonung der Projektdefinitionsphase.](media/upgrade-banner-project-definition.png "Phasen der Upgradephase mit Schwerpunkt auf der Projektdefinitionsphase")

Dieser Artikel ist Teil der Projektdefinitionsphase Ihrer Upgrade-Reise. Abgeschlossen, nachdem Sie eine Sponsoring-Koalition und ein Projektteam erstellt und den Umfang, die Ziele und den Plan für Ihr Projekt definiert haben. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten abgeschlossen haben:

- [Ernennen der Projektbeteiligten](upgrade-enlist-stakeholders.md)
- [Definieren des Projektumfangs](./upgrade-define-project-scope.md)

Wenn Ihre Organisation heute Skype for Business verwendet und Sie mit der Verwendung von Teams zusammen mit Skype for Business beginnen oder mit dem Upgrade auf Teams beginnen, ist es wichtig zu verstehen, wie die beiden Anwendungen vorhanden sind, wann und wie sie zusammenarbeiten und wie Sie die Migration Ihrer Benutzer bis zu ihrem eventuellen Upgrade von Skype for Business zu Teams.

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über [Koexistenz und Interoperabilität](https://aka.ms/teams-upgrade-coexistence-interop) zu erfahren.
>
> Darüber hinaus können Sie an live stattfindenden interaktiven Workshops teilnehmen, in denen wir Anleitungen, bewährte Methoden und Ressourcen für den Einstieg in die Upgradeplanung und -implementierung freigeben.
>
> Nehmen Sie zuerst an der [Upgradesitzung "Planen"](./upgrade-workshops-landing-page.yml) teil, um zu beginnen.

## <a name="coexistence-of-teams-and-skype-for-business-overview"></a>Koexistenz von Teams und Skype for Business Übersicht

In den folgenden Abschnitten werden die Koexistenzmodi beschrieben, die verfügbar sind, wenn Sie sich für Upgrades auf Teams entscheiden, und die Funktionen, die jeder Modus bietet. Darüber hinaus beschreiben wir die Interoperabilität (Interop), die zwischen Benutzern auf Skype-for-Business-Clients und Benutzern auf Teams-Clients auftritt, und wie sich die Interoperabilität auf den ausgewählten Koexistenzmodus auswirkt.

Teams bietet Funktionen für Zusammenarbeit, Chat, Anrufe und Besprechungen. Je nachdem, wie Sie Teams bereitstellen, überschneiden sich diese Funktionen möglicherweise mit den Von Skype for Business für einen bestimmten Benutzer bereitgestellten Funktionen. Der Standardmodus besteht darin, Teams zusammen mit Skype for Business mit überlappenden Funktionen auszuführen. Einem Benutzer kann jedoch einer von mehreren Koexistenzmodi (auch als Upgrademodi bezeichnet) zugewiesen werden, die darauf ausgelegt sind, sicherzustellen, dass sich diese Funktionen für diesen Benutzer nicht überlappen (in diesem Fall ist die Interoperabilität zwischen Teams und Skype for Business verfügbar). Wenn Sie beispielsweise über erhebliche Skype for Business Server lokalen Ressourcen mit einer komplexen Enterprise-VoIP Bereitstellung verfügen, Ihren Benutzern aber so schnell wie möglich moderne Besprechungen ermöglichen möchten, sollten Sie "[Besprechungen zuerst](meetings-first.md)" als alternativen Pfad auswerten.

Es wird empfohlen, die folgenden Koexistenzmodi zu überprüfen, um zu ermitteln, welcher Pfad für Ihre Organisation geeignet ist.

> [!Important]
> Koexistenzmodi sind nach der Einstellung von Skype for Business Online weiterhin vorhanden, benutzer, die online verwaltet werden, können jedoch nur über einen Modus von TeamsOnly verfügen. Es ist nicht mehr möglich, einem Benutzer, der online verwaltet wird, einen anderen Modus als TeamsOnly zuzuweisen.  Wie vor der Einstellung von Skype for Business Online können Benutzern, die lokal verwaltet werden, *andere Modus als TeamsOnly* zugewiesen werden.

### <a name="islands-mode"></a>Inselmodus

Standardmäßig können Benutzer Teams zusammen mit Skype for Business als zwei separate Lösungen ausführen, die ähnliche und überlappende Funktionen bereitstellen. Die Funktionen umfassen Anwesenheit, Chat, Anrufe und Besprechungen. Teams-Benutzer können auch neue Funktionen für die Zusammenarbeit nutzen, z. B. Teams und Kanäle, Zugriff auf Dateien in Microsoft 365 und Anwendungen.

In diesem Koexistenzmodus, genannt **"Inseln**", fungiert jede der Clientanwendungen als separate Insel. Skype for Business spricht mit Skype for Business und Teams mit Teams. Es wird davon ausgegangen, dass Benutzer beide Clients jederzeit ausführen und nativ in dem Client kommunizieren können, von dem aus die Kommunikation gestartet wurde. Daher ist im **Inselmodus** keine Interoperabilität erforderlich.

Um eine verwirrende oder zurückgeschrittene Skype for Business Erfahrung zu vermeiden, behandelt die Skype for Business die folgenden Integrationen, die im Modus "**Teams-Inseln**" nicht behandelt werden:

- Externe Kommunikation (Verbundkommunikation).
- PSTN-VoIP-Dienste und Sprachanwendungen, Office-Integration.
- HID-Steuerelemente für USB-Geräte.
- Mehrere andere Integrationen.

Das Telefonsystem wird in Teams im **Inselmodus** nicht unterstützt. Der **Inselmodus** unterstützt nicht, Enterprise-VoIP Client Skype for Business ist.

> [!Important]
> Im **Inselmodus** werden alle Nachrichten und Anrufe von Verbundbenutzern (Personen außerhalb Ihrer Organisation) an Skype for Business übermittelt. Nach dem Upgrade auf den Modus **"Nur Teams** " werden alle Nachrichten und Anrufe von außerhalb Ihrer Organisation an Teams übermittelt.

### <a name="teams-only"></a>Nur Teams

Ein **Nur-Teams-Benutzer** (auch als *aktualisierter* Benutzer bezeichnet) hat Zugriff auf alle Funktionen in Teams. Sie können den Skype for Business-Client für die Teilnahme an Besprechungen auf Skype for Business behalten, die von nicht aktualisierten Benutzern oder externen Parteien organisiert wurden. Ein aktualisierter Benutzer kann weiterhin mit anderen Benutzern in der Organisation kommunizieren, die weiterhin Skype for Business verwenden, indem er die Interoperabilitätsfunktionen zwischen Teams und Skype for Business verwendet (vorausgesetzt, die Skype for Business Benutzer sich nicht im **Inselmodus** befinden). Ein aktualisierter Benutzer kann jedoch keinen Skype for Business Chat, Anruf oder Besprechung initiieren.

Sobald Ihre Organisation für einige oder alle Benutzer bereit ist, Teams als einziges Kommunikations- und Zusammenarbeitstool zu verwenden, aktualisieren Sie diese Benutzer in den Modus " **Nur Teams** ". Wenn Sie ein Upgrade vom **Inselmodus** durchführen, empfehlen wir Ihnen, die Einführung von Teams in Der gesamten Organisation zu überlasten, bevor Sie mit dem Upgradeprozess beginnen. Durch diese Einführung werden fehlerhafte Kommunikationsszenarien vermieden, da der **Inselmodus** keine Interoperabilität bietet.

Im Modus **"Nur Teams** " ist Teams die Standard-App für das SIP/Tel-Protokoll. Links auf der Visitenkarte eines Benutzers in Outlook für Anrufe oder Chats werden von Teams verarbeitet.

Weitere Überlegungen zum Wechseln in den Modus " **Nur Teams** " finden Sie unter [Überlegungen zum Nur-Teams-Modus](teams-only-mode-considerations.md).

![Screenshot der Teams-Bestätigungsmeldung.](media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype for Business Client, der in einem speziellen Modus ausgeführt wird, nachdem der Benutzer als nur Teams-Benutzer aktualisiert wurde")

### <a name="skype-for-business-only"></a>Nur Skype for Business

In diesem Koexistenzmodus verbleiben Benutzer in Skype for Business – nicht in Teams – für Chat-, Besprechungs- und Anruffunktionen, und sie verwenden Teams nicht für Teams und Kanäle. Dieser Modus ist heute verfügbar. In der aktuellen Implementierung werden Teams und Kanäle jedoch nicht automatisch für den Benutzer deaktiviert. Dies kann mithilfe der App-Setuprichtlinie erreicht werden, um Teams und Dateien auszublenden.

Dieser Modus kann vor dem Starten einer verwalteten Bereitstellung von Teams verwendet werden, um zu verhindern, dass Benutzer Teams verwenden, bevor sie bereitschaftsbereit sind. Dieser Modus ist auch eine Möglichkeit, die authentifizierte Teilnahme an Teams-Besprechungen für Skype for Business Benutzer zu aktivieren, vorausgesetzt, die Benutzer sind für Teams lizenziert.

### <a name="skype-for-business-with-teams-collaboration"></a>Skype for Business mit Teams-Zusammenarbeit

Verwenden Sie diesen Modus, um Teams in Ihrer Umgebung einzuführen, während Sie Weiterhin Ihre vorhandene Investition in Skype for Business verwenden. Lassen Sie Skype for Business für Chat-, Anruf- und Besprechungsfunktionen unverändert. Hinzufügen von Teams-Funktionen für die Zusammenarbeit:

- Teams und Kanäle.
- Zugriff auf Dateien in Microsoft 365 oder Office 365.
- Anwendungen. Teams-Kommunikationsfunktionen – privater Chat, Anrufe und Planen von Besprechungen.

Private Teams-Chats, -Anrufe und -Besprechungen sind in diesem Modus standardmäßig deaktiviert.

Organisationen mit einem Ausgangspunkt für Skype for Business Server lokal oder hybrid sollten diesen Modus als Alternative zum **Inselmodus** in Betracht ziehen, wenn sie ihren Benutzern Interoperabilität und Vorhersagbarkeit für ihre Kommunikation sowie eine vorhersehbare Zeitachse für ihr Upgrade auf Teams bieten möchten (anstatt sich auf die Akzeptanzsättigung im **Inselmodus** zu verlassen).

### <a name="skype-for-business-with-teams-collaboration-and-meetings-also-known-as-meetings-first"></a>Skype for Business mit Teams-Zusammenarbeit und -Besprechungen, auch bekannt als "Besprechungen zuerst"

Verwenden Sie diesen Koexistenzmodus, um die Verfügbarkeit von Teams-Besprechungs- und -Zusammenarbeitsfunktionen in Ihrer Organisation zu beschleunigen. Mit dem Koexistenzmodus können Ihre Benutzer die vorteile der überlegenen Teams-Besprechungserfahrung nutzen:

- Tolle Qualität.
- Transkription und Übersetzung.
- Unscharfer Hintergrund.
- Überlegene Benutzererfahrung auf allen Plattformen, einschließlich mobiler Geräte und Browser.

Neben der Verwendung von Teams für Teams und kanalbasierte Unterhaltungen in diesem Modus verwenden Benutzer Teams, um ihre Besprechungen zu planen und durchzuführen. Privater Chat und Anrufe bleiben auf Skype for Business. Teams und Skype for Business profitieren von einer Reihe von "besseren Gemeinsam"-Funktionen, z. B. anwesenheitsbasierte Abstimmung, automatisches Halten/Zurückhalten und HID-Geräteunterstützung in beiden Anwendungen. Es ist möglich, Teams und Kanäle bei Bedarf mithilfe der App-Setuprichtlinie auszublenden.

Dieser Koexistenzmodus ist besonders nützlich für Organisationen mit Skype for Business lokalen Bereitstellungen mit Enterprise-VoIP. Diese Organisationen nehmen sich wahrscheinlich einige Zeit, um auf Teams zu aktualisieren, und möchten so schnell wie möglich von den überlegenen Teams-Besprechungen profitieren.

> [!TIP]
> Um den empfohlenen Upgrademodus basierend auf den Funktionen zu identifizieren, die Sie in Teams aktivieren möchten, während Skype for Business noch verwendet wird, nutzen Sie den [Upgrade-Assistenten von Skype zu Teams](https://aka.ms/SkypeToTeamsWizard).

Weitere Informationen zu Koexistenzmodi, Voraussetzungen und Verwaltung finden Sie in [den Migrations- und Interoperabilitätsanleitungen für Organisationen, die Teams zusammen mit Skype for Business](./migration-interop-guidance-for-teams-with-skype.md) verwenden, sowie [zum Festlegen Ihrer Koexistenz- und Upgradeeinstellungen](./setting-your-coexistence-and-upgrade-settings.md).

|Symbol für Entscheidungspunkt |Symboldefinition |Beschreibung |
|---|---|---|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|Entscheidungspunkt|<ul><li>Welche Koexistenzmodus(en) passen am besten zu den Anforderungen Ihrer Organisation und Ihrer Benutzer?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt= "An icon depicting the next step"/>|Nächster Schritt|<ul><li>Wählen Sie den besten Ansatz für Ihre Upgrade-Reise aus.</li></ul>|

### <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilität von Teams und Skype for Business

Interoperabilität ist die Möglichkeit für Teams und Skype for Business Benutzern in derselben Organisation, über Teams und Skype for Business hinweg zu kommunizieren.

Die Interoperabilität wird durch den Koexistenzmodus (auch als Upgrademodus bezeichnet) des Empfängers gesteuert. Es gibt keine Interoperabilität, wenn sich der Empfänger im **Inselmodus** befindet.

> [!Note]
> Wenn Teams und Skype for Business in einem beliebigen Koexistenzmodus mit Ausnahme von **Inseln** bereitgestellt werden, können [sie zusammenarbeiten](#interoperability-of-teams-and-skype-for-business), sodass Benutzer miteinander chatten und sich gegenseitig anrufen können, und sicherstellen, dass die Kommunikation während Ihrer Upgrade-Reise zu Teams in Ihrer Organisation flüssig bleibt. Koexistenzmodi steuern die Interoperabilität. Der Koexistenzmodus des Empfängers bestimmt, ob Interoperabilität verfügbar ist. Wenn sich der Empfänger beispielsweise in einem Modus befindet, in dem der Chat nur in einem Client (z. B. Teams) verfügbar ist, ist die Chatinteroperabilität im Allgemeinen verfügbar, falls der Initiator den anderen Client (in diesem Fall Skype for Business) zum Starten des Chats verwendet. Wenn sich der Empfänger hingegen in dem Modus befindet, in dem der Chat in beiden Clients (Inselmodus) verfügbar ist, ist keine Interoperabilität für den Chat verfügbar. Die Nachricht wird vom Empfänger im selben Client empfangen, in dem der Initiator den Chat gestartet hat. Daher erfordert die ordnungsgemäße Kommunikation im **Inselmodus** eine Sättigung der Teams-Einführung. das heißt, alle Benutzer verwenden und überwachen beide Clients aktiv.

> [!Note]
> **Um die neueste Koexistenzerfahrung zu haben, muss die Clientversion der neueste verfügbare Client im Office-Bereitstellungskanal des Benutzers sein.**

#### <a name="native-interop-and-interop-escalation"></a>Systemeigene Interop- und Interopeskalation

Es gibt zwei Arten von Interoperabilitätserfahrungen: native und Interopeskalation.

- In dem Client, den der Benutzer derzeit verwendet, tritt eine _systemeigene Interoperabilitätserfahrung_ auf. Ein Benutzer ist im Skype for Business Client, der andere in Teams. Eine systemeigene Interoperabilitätserfahrung bringt sie nicht zu einem anderen Client, um zu kommunizieren. Die Benutzer können ihre Unterhaltungen in dem Client führen, den sie derzeit verwenden. Die nativen Interop-Erfahrungen sind 1:1-Chats und -Anrufe.
- Eine _Interopeskalationserfahrung_ bedeutet, dass der Client als Teil der Unterstützung von Benutzern beim Ausführen einer erweiterten Aktion (z. B. freigeben des Desktops) die Erstellung einer Besprechung erleichtert, an der Benutzer teilnehmen können, um die Erfahrung in dieser Besprechung fortzusetzen. Die Besprechung wird auf der Plattform des Initiators der Aktion erstellt. Der Oder die Benutzer, die sich nicht auf dieser Plattform befinden, erhalten einen Besprechungsbeitrittslink. Wenn sie auf diesen Link klicken, werden sie in einem kompatiblen Client (Browser, Web-App oder vollständiger Client, je nach Konfiguration) mit der Besprechung verbunden. Interopeskalation von Skype for Business erfordert einen aktuellen Client. Die Interopeskalation von Teams ist jetzt verfügbar. Beide werden in der Interoperabilitätsumgebung im Mandanten und für mandantenübergreifende Verbundkommunikation unterstützt.

#### <a name="native-interop-experiences"></a>Native Interop-Erfahrungen

Je nach den Benutzern zugewiesenen Koexistenzmodi (wie zuvor beschrieben) sind die folgenden nativen Interoperabilitätsfunktionen verfügbar:

Skype for Business Benutzer können einzeln mit Teams-Benutzern chatten und umgekehrt. Ein Interop-Chat muss über ein Interopgateway erfolgen, das Teil von Teams-Clouddiensten ist (und daher nur online vorhanden ist). Interoperabilitätschats sind Nur-Text: Rich-Text und Emoticons werden nicht unterstützt. Benutzer in Teams und in Skype for Business werden benachrichtigt, dass es sich bei der Unterhaltung um eine Interoperabilitätsunterhaltung handelt.

<!--![Screen shot of Interop chat experience from Teams.](media/Interop_chat_experience_from_Teams.png "Interop chat experience from Teams")-->

Skype for Business Benutzer können 1:1-Sprach- und Videoanrufe an Teams-Benutzer tätigen, und Teams-Benutzer können dies auch tun.

<!--![Screen shot of Interop calling experience from Teams.](media/Interop_calling_experience_from_Teams.png "Interop calling experience from Teams")-->

> [!Important]
> Interoperabilitätserfahrungen mit einer lokalen Bereitstellung von Skype for Business erfordern, dass sich die lokale Umgebung im Hybridmodus mit Teams befindet. Ausführliche Informationen finden [Sie unter Konfigurieren der Hybridverbindung zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

Diese Interoperabilitätsfunktionen stehen Benutzern zur Verfügung, denen einer der folgenden Koexistenzmodi zugewiesen ist: **Skype for Business mit Teams-Zusammenarbeit**, **Skype for Business mit Teams-Zusammenarbeit und -Besprechungen**, **Skype for Business Nur** oder **Nur Teams**. Im **Inselmodus** gibt es keine Interoperabilität für Benutzer.

#### <a name="native-interop-experience-limitations"></a>Einschränkungen der nativen Interop-Erfahrung

Aufgrund des Unterschieds bei Protokollen und Technologien ist es nicht möglich, alle Funktionen nativ zu unterstützen. Insbesondere sind die folgenden Funktionen nicht verfügbar:

- Markdown, Rich-Text und der vollständige Emoticon-Satz werden weder von Teams noch von Skype for Business unterstützt. Andere systemeigene Features des Felds zum Verfassen in Teams-Chats werden nicht unterstützt.
- Die Bildschirmfreigabe (Desktop- oder App-Freigabe) zwischen Teams und Skype for Business wird nativ nicht unterstützt. Es wird jedoch durch Interopeskalation unterstützt.
- Gruppenchats (Unterhaltungen mit mehreren Teilnehmern) in Teams können nur Teilnehmer enthalten, die Teams verwenden.
- Chatunterhaltungen mit mehreren Teilnehmern (Gruppenchats) in Skype for Business können nur Teilnehmer umfassen, die Skype for Business verwenden. Die Interopeskalation zu mehreren Parteien steht jedoch über Skype for Business zur Verfügung.
- Das Eskalieren eines laufenden Peer-to-Peer-Sprach- oder Videoanrufs zu einem Anruf mit mehreren Teilnehmern, an dem sowohl Teams als auch Skype for Business Benutzer beteiligt sind, wird nicht unterstützt.
- Die Dateiübertragung für Zwei-Parteien-Chats oder Dateianlagen in Gruppenchats von Teams zu Skype for Business – und umgekehrt – wird nicht unterstützt.
- Es gibt keine Interoperabilität mit Skype for Business beständigen Chat.

Bei all diesen Einschränkungen (mit Ausnahme des beständigen Chats) besteht eine mögliche Problemumgehung darin, dass ein Benutzer eine Besprechung startet und den anderen Benutzer zur Teilnahme an der Besprechung einlädt.

Diese Problemumgehung ist die Grundlage für die Interopeskalation. Insbesondere die Bildschirmfreigabe und -eskalation zu Mehreren Teilnehmern sind nativ nicht erreichbar, werden aber über die Interopeskalation unterstützt.

#### <a name="interop-escalation-experiences"></a>Interopeskalationserfahrungen

Die Interopeskalation besteht darin, die nativen Interopfunktionen durch verwaltete Eskalationen zu Besprechungen zu ergänzen. Besprechungen bieten umfassende Erfahrungen, die jedem zur Verfügung stehen, unabhängig davon, welchen Client er hat.

Wenn die Interopeskalation vom Teams-Benutzer ausgelöst wird, wird eine Teams-Besprechung erstellt. Wenn sie vom Skype for Business Benutzer ausgelöst wird, wird eine Skype for Business Besprechung erstellt. In beiden Fällen handelt es sich bei der erstellten Besprechung um eine Besprechung " **Jetzt besprechen** ", die nicht im Kalender des Benutzers widergespiegelt wird.

Die andere Partei empfängt den Link "Besprechungsbeitritt" über den Interoperabilitätschat und nimmt daran teil, indem sie auf diesen Link klickt. Wenn der Skype for Business Benutzer über ein Teams-Konto verfügt und vom Teams-Benutzer eingeladen wird, wird er authentifiziert an der Besprechung teilnehmen. Andernfalls werden sie als anonymer Teilnehmer beitreten. Umgekehrt verfügen Teams-Benutzer fast immer über ein Skype for Business Konto und einen Skype for Business Client, mit dem sie als authentifizierter Teilnehmer an einer Skype for Business Besprechung teilnehmen können, aber sie können auch als anonymer Teilnehmer teilnehmen, z. B. über die Skype-Besprechung App.

Nachdem die Parteien der Besprechung beigetreten sind, können sie alle aktivitäten durchführen, die in Besprechungen unterstützt werden, z. B. Desktop- oder Inhaltsfreigabe, Dateifreigabe oder -übertragung, Hinzufügen anderer Teilnehmer usw.

#### <a name="interop-escalation-from-skype-for-business"></a>Interopeskalation von Skype for Business

Die Interop- und Interopeskalation von Skype for Business wurde im Build des monatlichen C2R im Juli 2019 aktualisiert. Zuvor war Skype for Business nicht bewusst, dass die Remotepartei Teams verwendet hat. Es wurde nur davon ausgegangen, dass aus der Signalisierung, die nach der Einrichtung einer Sitzung empfangen wurde.

Wenn die Signalisierung anzeigte, dass die Antwort vom Interoperabilitätsgateway (oder durch) kam, wird die gelbe Geschäftsleiste (Banner) angezeigt, die angibt, dass die andere Partei Skype for Business nicht verwendet hat. Mit der Weiterentwicklung unseres Dienstes führte dies zu falsch positiven Ergebnissen, bei denen Skype for Business Benutzern die Business-Leiste angezeigt wurde, wenn sie mit dem Cloud-Voicemail-Dienst oder anderen Cloud-VoIP-Diensten verbunden waren, anstatt mit einem tatsächlichen **Teams Only-Benutzer**.

Um diese falsch positiven Ergebnisse zu verhindern, informiert der Anwesenheitsdienst jetzt den Skype for Business-Client, wenn die andere Partei ein **tatsächlicher** Benutzer ist. Auf diese Weise können Skype for Business wissen, dass sie eine Interopunterhaltung erstellen müssen, bevor sie erstellt wurde, und dass das Unterhaltungsfenster interopspezifisch sein muss.

![Screenshot der Teams-Nachricht zum Erstellen einer Interoperabilitätsunterhaltung mit einem Skype for Business Benutzer.](media/teams-and-skypeforbusiness-coexistence-and-interop-create-conversation-with-skype-user.png)

Wenn der Skype for Business Benutzer z. B. den Desktop freigeben möchte, wird er darüber informiert, dass wir eine Besprechung starten und durch die Schritte geführt werden.

![Screenshot der Teams-Nachricht zum Starten einer Besprechung mit einem Teams-Benutzer.](media/teams-and-skypeforbusiness-coexistence-and-interop-start-meeting-with-teams-user.png)

In der Zwischenzeit erhält der Teams-Benutzer eine eingehende Chatnachricht mit dem Link zur Besprechung und wird zur Teilnahme geführt.

Diese Eskalation zu einer Skype for Business-Besprechung ist sowohl für In-Tenant-Interop- als auch für mandantenübergreifende Verbundanrufe und Chats verfügbar. Sie ist standardmäßig aktiviert, und es gibt keine Einstellung, die der Administrator bereitstellen muss.

#### <a name="interop-escalation-from-teams"></a>Interopeskalation von Teams

Die Interopeskalation von Teams zu einer Teams-Besprechung ist jetzt verfügbar, wenn der Teams-Benutzer die Desktopfreigabeschaltfläche in einem Mandanten-Interopthread mit einem Skype for Business Benutzer oder in einem mandantenübergreifenden Interop-Verbundthread auswählt. Interopeskalation wird von einer 1:1-Chatunterhaltung oder von einem 1:1-Anruf unterstützt.

Die Funktion wird im Teams-Desktopclient für Windows, im Teams-Desktopclient für Mac und im Teams-Webclient in Browsern unterstützt, in denen die Inhaltsfreigabe unterstützt wird, während sie mit jeder Skype for Business Clientversion kommuniziert.

In Interoperabilitätsthreads und in Verbundinteroperabilitätsthreads verfügt der Teams-Benutzer jetzt über die Steuerelemente (Schaltfläche), um die Inhaltsfreigabe zu starten. Wenn der Teams-Benutzer die Schaltfläche auswählt, wird ein zusätzliches Menü angezeigt, in dem er darüber informiert wird, dass er zum Freigeben von Inhalten eine Teams-Besprechung starten muss.

Wenn die Benutzer in einem Anruf waren, warnt das Menü sie auch, dass ihr aktueller Anruf zwischen Teams und Skype for Business beendet wird, sobald sie in eine Teams-Besprechung gestellt werden. Wenn sie dies auswählen, können sie den Skype for Business Benutzer vor der Annahme warnen.

![Screenshot der Teams-Nachricht zum Freigeben einer Besprechung mit einem Skype for Business Benutzer.](media/teams-and-skypeforbusiness-coexistence-and-interop-share-meeting-with-skype-user.png)

Nach der Annahme werden sie in die Teams-Besprechung aufgenommen. Sie müssen die Freigabe über die Freigabeleiste in der Besprechung starten.

In der Zwischenzeit erhält der Skype for Business Benutzer eine eingehende Chatnachricht mit dem Link zur Besprechung und wird zur Teilnahme geführt.

Diese Eskalation zu einer Teams-Besprechung ist sowohl für In-Tenant-Interop- als auch für mandantenübergreifende Verbundanrufe und Chats verfügbar. Sie ist standardmäßig aktiviert, und es gibt keine Einstellung, die der Administrator bereitstellen muss. Es ist jedoch für den Benutzer deaktiviert, wenn sich der Administrator ``-AllowPrivateMeetNow`` auf ``CsTeamsMeetingPolicy`` ``$false``.

Nachdem Sie diesen Artikel durchsehen haben, finden Sie informationen zu Implementierungsdetails unter ["Auswählen der Upgrade-Reise](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)", "[Anleitungen für Migration und Interoperabilität](./migration-interop-guidance-for-teams-with-skype.md)", ["Koexistenz mit Skype for Business](coexistence-chat-calls-presence.md)" [und "Festlegen ihrer Koexistenz- und Upgradeeinstellungen](./setting-your-coexistence-and-upgrade-settings.md)". Wir empfehlen auch das folgende Video: [Video: Verwalten der Koexistenz und Interoperabilität zwischen SfB und Teams](https://www.youtube.com/watch?v=wEc9u4S3GIA&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl&index=11)

## <a name="technical-details-of-teams-and-skype-for-business-coexistence"></a>Technische Details zu Teams und Skype for Business Koexistenz

In den folgenden Abschnitten wird das Verhalten zusammengefasst, das beim Ausführen von Teams und Skype for Business Clients in derselben Organisation auftreten kann, unabhängig davon, welcher Modus und welche Upgrademethode verwendet wird:

- [Besprechungen](#meetings)
- [Interoperabilität](#interoperability)
- [Interop im Vergleich zu nativen Unterhaltungsthreads](#interop-versus-native-conversation-threads)
- [Anwesenheit](#presence)
- [Partnerverbund](#federation)
- [Kontakte](#contacts)

### <a name="meetings"></a>Besprechungen

Unabhängig von ihrem Modus können Benutzer jederzeit an jeder Art von Besprechung teilnehmen, zu der sie eingeladen werden, unabhängig davon, ob es sich um Skype for Business oder Teams handelt.  Benutzer müssen jedoch mit einem entsprechenden Client an der Besprechung teilnehmen, der dem Besprechungstyp entspricht:

- Wenn es sich bei der Besprechung um eine Teams-Besprechung handelt, verwenden alle Teilnehmer (unabhängig davon, ob es sich um TeamsOnly-, Islands- oder Skype for Business-Benutzer handelt) den Teams-Client, um an der Besprechung teilzunehmen. Wenn Teams nicht installiert ist, wird der Benutzer beim Versuch, an einer Besprechung teilzunehmen, ins Web geleitet.

- Wenn es sich bei der Besprechung um eine Skype for Business Besprechung handelt, verwenden alle Teilnehmer (unabhängig davon, ob es sich um TeamsOnly-, Islands- oder Skype for Business-Benutzer handelt) den Skype for Business Client, um an der Besprechung teilzunehmen. Wenn der Skype for Business-Client nicht installiert ist, wird der Benutzer über die Skype-Besprechung App zum Beitritt ins Web weitergeleitet. 

  In einigen Fällen können Teilnehmer im TeamsOnly-Modus nur mit Skype for Business-Web-App oder der Skype-Besprechungs-App als anonymer Benutzer an Skype for Business Besprechungen teilnehmen. Dieser Fall gilt schließlich für alle Benutzer im TeamsOnly-Modus. Weitere Informationen finden Sie [unter Skype for Business Online-Einstellung](skype-for-business-online-retirement.md#what-to-expect-post-retirement).

Beim Organisieren von Besprechungen basiert der Besprechungstyp, der geplant wird, auf dem Modus des Organisators, wie in der folgenden Tabelle gezeigt:

| Modus des Organisators    |      Verhalten |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings | Alle in Teams geplanten Besprechungen. Skype for Business Add-In ist in Outlook nicht verfügbar. |
| SfbWithTeamsCollab, SfbOnly | Alle in Skype for Business geplanten Besprechungen. Das Teams-Add-In ist in Outlook nicht verfügbar. |
| Inselmodus | Standardmäßig können Besprechungen entweder in Skype for Business oder Teams geplant werden. Beide Add-Ins sind in Outlook verfügbar. Sie können jedoch optional festlegen, dass Benutzer auf Inseln immer Besprechungen in Teams planen, indem Sie ihnen eine Instanz von TeamsMeetingPolicy mit dem PreferredMeetingProviderForIslandsMode=Teams zuweisen.|

### <a name="interoperability"></a>Interoperabilität

Wie oben unter [Interoperabilität von Teams und Skype for Business](#interoperability-of-teams-and-skype-for-business) beschrieben, unterstützt Teams in bestimmten Szenarien die Interoperabilität mit Skype for Business. Interopkommunikation bezieht sich auf einen Chat oder Anruf zwischen einem Skype for Business Benutzer und einem Teams-Benutzer.  Interop-Kommunikation ist nur zwischen zwei Benutzern möglich; Chats/Anrufe mit mehreren Teilnehmern oder das Hinzufügen zusätzlicher Benutzer werden nicht unterstützt.

Ein Interoperabilitätschat oder -anruf zwischen zwei Benutzern wird erstellt, wenn jeder der folgenden Bedingungen zutrifft:

- Ein Benutzer verwendet Teams, der andere Skype for Business.

- Der Modus des Empfängers der anfänglichen Kommunikation ist KEINE Inseln (andernfalls würde die Kommunikation im selben Client landen), wenn sich beide Benutzer in derselben Organisation befinden. In Verbundszenarien verwendet der sendende Benutzer Teams, und der Empfänger befindet sich nicht im TeamsOnly-Modus.

- Der Teams-Benutzer verfügt NICHT auch über ein Skype for Business Konto, das lokal verwaltet wird.

Innerhalb der Interop-Kommunikation ist Chat nur Nur-Text. Darüber hinaus ist die Dateifreigabe und Bildschirmfreigabe *im Interoperabilitätschat selbst* nicht möglich. Benutzer in einer Interoperabilitätsunterhaltung können die Datei- und/oder Bildschirmfreigabe jedoch problemlos erreichen, indem sie eine On-Demand-Besprechung innerhalb des Interop-Chats erstellen, wie unten beschrieben:

- Wenn der Teams-Benutzer versucht, seinen Bildschirm freizugeben, wird automatisch eine On-Demand-Teams-Besprechung erstellt, und ein Einladungslink zu dieser Besprechung wird an den Client des Skype for Business Benutzers gesendet. Wenn sie auf den Link klicken, öffnet der Skype for Business Benutzer Teams und nimmt an der Besprechung teil. Beide Benutzer befinden sich jetzt in einer Teams-Besprechung und können nach Bedarf teilen.

- Wenn der Skype for Business Benutzer einen Client ab 2018 oder höher verwendet und versucht, Inhalte freizugeben, wird automatisch eine On-Demand-Skype for Business Besprechung erstellt und ein Einladungslink zu dieser Besprechung an den Client des Teams-Benutzers gesendet. Beim Klicken auf den Link versucht der Teams-Benutzer, an der Skype for Business Besprechung teilzunehmen. Wenn der Teams-Benutzer den Skype for Business-Client installiert hat, wird er geöffnet, und der Benutzer wird aufgefordert, sich anzumelden (falls nicht bereits angemeldet).  Wenn der Teams-Benutzer den Skype for Business Client nicht installiert hat, wird der Benutzer aufgefordert, die Webversion zu verwenden. Sobald beide Benutzer angemeldet sind, befinden sie sich in einer Skype for Business Besprechung und können sie nach Bedarf freigeben.

### <a name="interop-versus-native-conversation-threads"></a>Interop im Vergleich zu nativen Unterhaltungsthreads

Da die Interoperabilitätskommunikation nicht alle Features der nativen Teams-Unterhaltung unterstützt, verwaltet der Teams-Client separate Unterhaltungsthreads für die Kommunikation zwischen Teams und teams-zu-Skype for Business. Diese Unterhaltungen werden auf der Benutzeroberfläche anders gerendert: Interopthreads können von einem normalen nativen Teams-Thread unterschieden werden durch:

- Fehlende Steuerelemente für Rich-Text, Datei-/Bildschirmfreigabe, Unfähigkeit, Benutzer hinzuzufügen.
- Eine Änderung am Symbol des Zielbenutzers mit einem "S" für Skype for Business.

Diese Unterschiede werden in den folgenden Screenshots gezeigt:

Eine native Teams-zu-Teams-Unterhaltung mit Benutzer-G3-Test

![Diagramm, das eine native Teams-zu-Teams-Unterhaltung zeigt.](media/teams-upgrade-native-thread.png)

Eine Interoperabilitätsunterhaltung mit demselben Benutzer-G3-Test

![Diagramm, das eine Interop-Teams-zu-Teams-Unterhaltung zeigt.](media/teams-upgrade-interop-thread.png)

Sobald ein Unterhaltungsthread erstellt wurde, ändert sich dessen Typ nie mehr. Nach der Erstellung wird ein Interoperabilitätsthread in Teams immer zum Skype for Business Client des Zielbenutzers geleitet. Ein systemeigener Thread wird immer zum Teams-Client des Zielbenutzers geleitet.  Wenn sich der Modus eines Empfängerbenutzers ändert, funktionieren vorhandene Teams-Threads für diesen Benutzer nicht mehr, und in diesem Chat wird eine Notiz mit einem Link zum Starten einer neuen nativen Unterhaltung angezeigt, wie im folgenden Screenshot dargestellt.

![Diagramm, das einen Chat mit aktualisiertem Skype for Business Benutzer zeigt.](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Anwesenheit

Die Anwesenheit für einen bestimmten Benutzer basiert auf der Aktivität des Benutzers im Dienst über den Client. Der Anwesenheitsstatus wird dann für andere Benutzer veröffentlicht.  Skype for Business und Teams sind separate Dienste mit separaten Clients, sodass jeder Dienst einen eigenen Anwesenheitsstatus für einen Benutzer hat.   Es gibt auch eine Synchronisierung zwischen den Anwesenheitsdiensten in Teams und in Skype for Business Online.  Auf diese Weise kann ein Dienst bei Bedarf die Anwesenheit des Benutzers aus dem anderen Dienst veröffentlichen.

Das Veröffentlichungsverhalten von Anwesenheitsinformationen basiert auf dem Modus des Benutzers. Es gibt drei grundlegende Fälle:

- Wenn sich ein Benutzer im TeamsOnly-Modus befindet, sehen alle anderen Benutzer die Anwesenheit von Teams für diesen Benutzer, unabhängig davon, welchen Client er verwendet.

- Wenn sich ein Benutzer in einem der Skype for Business Modi befindet, sehen alle anderen Benutzer Skype for Business Anwesenheit für diesen Benutzer, unabhängig davon, welchen Client er verwendet.

- Wenn sich ein Benutzer im Inselmodus befindet, sind die in Skype for Business und Teams veröffentlichten Anwesenheitsinformationen unabhängig, sodass die Für die Benutzer innerhalb derselben Organisation angezeigte Anwesenheit vom Client des anderen Benutzers abhängt. Benutzern in Verbundorganisationen wird das Vorhandensein dieses Benutzers basierend auf seiner Skype for Business Aktivität angezeigt, da der Verbunddatenverkehr zu einem Benutzer im Inselmodus in Skype for Business landet.

Angenommen, Benutzer A befindet sich im Inselmodus. Wenn Benutzer A in Teams aktiv ist, aber nicht bei Skype for Business angemeldet ist, sehen andere Benutzer Benutzer A von ihrem Teams-Client aus als aktiv, aber in ihrem Skype for Business-Client würde Benutzer A als offline angezeigt. Dies ist beabsichtigt, da Benutzer A nicht erreicht werden kann, wenn der Client nicht ausgeführt wird.


### <a name="federation"></a>Partnerverbund

Der Partnerverbund von Teams zu einem anderen Benutzer, der Skype for Business verwendet, setzt voraus, dass der Teams-Benutzer online in Skype for Business verwaltet wird. TeamsUpgradePolicy steuert das Routing für eingehende Verbundchats und -anrufe. Das Partnerweiterleitungsverhalten ist das gleiche wie für Szenarien mit demselben Mandanten, außer im Inselmodus. Wenn sich empfänger im Inselmodus befinden:

- Chats und Anrufe, die von Teams initiiert werden, landen in Skype for Business, wenn sich der Empfänger in einem Verbundmandanten befindet.
- Chats und Anrufe, die von Teams initiiert werden, landen in Teams, wenn sich der Empfänger im selben Mandanten befindet.
- Chats und Anrufe, die von Skype for Business initiiert werden, landen immer in Skype for Business.

Ein Verbundchat kann entweder ein nativer Thread oder ein Interoperabilitätsthread sein. Siehe [Interop im Vergleich zu nativen Unterhaltungsthreads](#interop-versus-native-conversation-threads).

- Wenn sich der Empfänger und der Absender sowohl im TeamsOnly-Upgrademodus befinden, ist die Unterhaltung eine native Chaterfahrung, die alle umfassenden Messaging- und Anruffunktionen umfasst. Weitere Informationen finden Sie [in der nativen Chaterfahrung für externe Benutzer (Verbundbenutzer) in Teams](native-chat-for-external-users.md).

- Wenn sich einer der Unterhaltungsteilnehmer NICHT im TeamsOnly-Upgrademodus befindet, bleibt die Unterhaltung eine Interoperabilitätserfahrung mit Nur-Text-Nachrichten. Die Benutzeroberfläche macht Verbundchats auf ähnliche Weise wie Interoperabilitätsthreads mit demselben Mandanten verfügbar, es sei denn, es gibt eine Notiz, die angibt, dass der Benutzer extern ist.

Weitere Informationen finden Sie unter [Verwalten des externen Zugriffs in Microsoft Teams](manage-external-access.md) und [der nativen Chaterfahrung für externe Benutzer (Verbundbenutzer) in Teams](native-chat-for-external-users.md).

### <a name="contacts"></a>Kontakte

Teams und Skype for Business verfügen über separate Kontaktlisten. Dies bedeutet, dass Kontaktergänzen, Entfernungen und Änderungen, die in einem System vorgenommen wurden, nicht mit dem anderen System synchronisiert werden. Kontakte aus Skype for Business werden jedoch automatisch in Teams kopiert, wenn eines von zwei spezifischen Ereignissen auftritt:

- Bei jedem Skype for Business Online-Benutzer werden bei der ersten Anmeldung bei Teams Kontakte aus Skype for Business in Teams kopiert.  Dieses Verhalten ist für Benutzer mit einem lokalen Konto in Skype for Business Server nicht verfügbar.

- Nachdem ein Benutzer auf TeamsOnly aktualisiert wurde (entweder durch Zuweisen von TeamsUpgradePolicy oder über Move-CsUser -MoveToTeams), werden vorhandene Kontakte in Skype for Business, die sich das nächste Mal bei Teams anmelden, mit vorhandenen Kontakten zusammengeführt, die bereits in Teams vorhanden sind. Dieses Verhalten tritt unabhängig davon auf, ob der Benutzer von lokal oder online nach TeamsOnly verschoben wurde.

In beiden Fällen erfolgt die Übertragung von Kontakten von Skype for Business zu Teams asynchron, sodass es einige Minuten dauern kann, bis Kontakte in Teams angezeigt werden. Die beiden oben genannten Ereignisse lösen die Kopie aus.

### <a name="related-links"></a>Verwandte Links

[Anleitungen zur Migration und Interoperabilität für Organisationen, die Teams zusammen mit Skype for Business verwenden](migration-interop-guidance-for-teams-with-skype.md)

[Konfigurieren der Hybridkonnektivität zwischen Skype for Business Server und Microsoft 365 oder Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Verschieben von Benutzern zwischen lokalen Bereitstellungen und der Cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Festlegen Ihrer Einstellungen für Koexistenz und Upgrades](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Verwenden des Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
