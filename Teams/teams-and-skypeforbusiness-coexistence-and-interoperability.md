---
title: Grundlegendes zu Skype-Interoperabilität und Koexistenz für Unternehmen und die Microsoft-Teams
author: lsomi
ms.author: lsomi
manager: serdars
ms.date: 09/21/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Details der Skype für Geschäfts- und Microsoft-Teams Koexistenz Optionen und Interoperabilität zwischen Skype für Unternehmen und Teams.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: be6cb8b6154c67e75a84bbb2e44add6109b3108c
ms.sourcegitcommit: bb3f235265cddae9578ec1bf605c4edc7f14fb30
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "25851592"
---
![Phasen der Upgrade Reise, mit Schwerpunkt auf der Project-Definition-Phase] (media/upgrade-banner-project-definition.png "Phasen der Upgrade Reise, mit Schwerpunkt auf der Project-Definition-Phase")

Dieser Artikel ist Teil der Project-Definition Phase der Ihrem Upgrade Weg, die Sie nach Abschluss einer Aktivität nach dem Erstellen eines Unterstützung durch Coalition und Project-Teams und der Umfang, die Ziele und die Vision für Ihr Projekt definieren. Bevor Sie fortfahren, vergewissern Sie sich, dass Sie die folgenden Aktivitäten ausgeführt haben:

-   [Ihre Projektbeteiligten eingetragen](upgrade-enlist-stakeholders.md)
-   [Definiert die Projektumfang](https://aka.ms/SkypetoTeams-Scope)

# <a name="understand-microsoft-teams-and-skype-for-business-coexistence-and-interoperability"></a>Grundlegendes zu Microsoft-Teams und Skype für Interoperabilität und Koexistenz Business

Wenn Ihr Unternehmen Skype heute für Unternehmen verwendet und für die Verwendung von Teams zusammen mit Skype für Unternehmen soll – oder Durchführen eines Upgrades auf Teams gestartet werden sollen – es ist wichtig zu verstehen, wie die gegenseitige Koexistenz wann und wie sie interagieren und wie, um Verwalten von Benutzer Migration ganz nach ihren tatsächlichen Upgrades aus Skype für Unternehmen, die Teams.

## <a name="coexistence-of-teams-and-skype-for-business"></a>Koexistenz von Teams und Skype für Unternehmen

Zusätzlich zu den Zusammenarbeitsfunktionen für die bietet Teams Chat, Anrufe und Besprechung Funktionen. Je nachdem, wie Sie die zum Bereitstellen von Teams auswählen werden diese Funktionen mit den Funktionen von Skype für Unternehmen für einen bestimmten Benutzer gelieferten überlappen. Der Standardmodus ist zum Ausführen von Teams zusammen mit Skype für Unternehmen; Allerdings kann ein Benutzer einen von mehreren Koexistenz Modi zugewiesen werden, die entworfen wurden, um sicherzustellen, dass diese Funktionen für diesen Benutzer überlappen nicht.

Es wird empfohlen, dass Sie der Koexistenz Modi erläutert überprüfen, um zu bestimmen, welcher Pfad für Ihr Unternehmen geeignet ist.

> [!Important]
> Einführung in die neue Technologie oder Ändern Ihrer vorhandenen, vertrauten Skype für geschäftsumgebung, während der Bereitstellung von neuen Business Vorteile, kann für Benutzer störende sein. Ermitteln Sie die benutzerbereitschaft und dauert einer Kommunikations- und Schulungsplan implementieren, bevor Sie die Änderungen, die in diesem Artikel beschriebenen implementieren. Darüber hinaus empfehlen wir Ihnen, die mit einer ausgewählten Gruppe von Benutzern des Plans evaluieren, bevor Sie es in Ihrer Organisation implementieren. 

### <a name="islands-mode"></a>Inseln-Modus

Standardmäßig können Benutzer Teams zusammen mit Skype für Unternehmen als zwei separate Lösungen ausführen, die ähnliche oder überlappende Funktionen wie Chat, Anrufe und Besprechungen zu liefern. Teams Benutzer können auch Zusammenarbeitsfunktionen wie Teams und Kanäle, Zugriff auf Dateien in Office 365 und Anwendungen nutzen.

In diesem Koexistenzmodus **Inseln**aufgerufen, wird jeweils der Clientanwendungen als einen separaten Bereich ausgeführt. Skype für Business kommuniziert mit Skype für Unternehmen und Teams kommuniziert mit Teams. Benutzer führen Sie beide Clients und auf dem Client, von dem die Kommunikation initiiert wurde, systemintern kommunizieren können. Daher besteht keine Notwendigkeit für die Interoperabilität im **Inseln** Modus.

> [!Tip]
> Skype für Business Online-Kunden empfohlenen Pfad besteht darin, beginnen Sie mit den Standardmodus **Inseln** , Laufwerk Annahme Sättigung in der Organisation, und wechseln dann schnell zu **Teams** nur Kopfzeilen herunterladen. Auf lokale und hybride werden Kunden aus den kommenden **Skype für Unternehmen mit Zusammenarbeit für Teams** Modus als Ausgangspunkt statt Inseln und Bearbeitung von dort **Nur Teams** Modus bereitstellen, sobald die Organisation einführen kann profitieren. Teams. 

### <a name="skype-for-business-only"></a>Skype für Unternehmen nur

In diesem Koexistenzmodus Benutzer bleiben in Skype für Unternehmen – nicht Teams – für Chat, Meeting aufrufende Funktionen und sie nicht Teams für Teams und Kanäle verwenden. In diesem Modus ist jetzt verfügbar. Allerdings werden in der aktuellen Implementierung Teams Modalitäten nicht für den Benutzer automatisch deaktiviert. Diese Funktion ist in Kürze verfügbare. In der Zwischenzeit können Administratoren die Teams-Lizenz für jeden Benutzer entfernen, die in Skype für Unternehmen als einzige Communications Anwendung bleiben müssen.

### <a name="teams-only-this-mode-started-rolling-out-summer-2018-and-will-be-completed-to-all-tenants-by-fall-2018"></a>Nur Teams (in diesem Modus gestartet parallelen out Sommer 2018 und wird für alle Mandanten fallen 2018 abgeschlossen sein)

Wie Ihre Organisation für einige oder alle Benutzer als einzige Kommunikation und Zusammenarbeit Tool Teams Verwendung bereit ist, können Sie diese Benutzer **Nur Teams** Modus aktualisieren.

Ein Benutzer **nur Teams** können nur die Skype für Business-Client zur Teilnahme an vorhandenen Skype für Business Besprechungen oder Besprechungen auf Skype für Unternehmen, die von Benutzern nicht aktualisiert oder externen Parteien organisiert wurden. Ein aktualisierter Benutzer kann weiterhin mit anderen Benutzern in der Organisation zu kommunizieren, die noch Skype für Unternehmen mithilfe der Funktionen Interoperabilität zwischen Teams und Skype für Unternehmen. Allerdings kann kein aktualisierter Benutzer einen Skype für Chat, Anruf oder eine Besprechung Business initiieren.

![Skype für Business-Client in einem speziellen Modus, nachdem der Benutzer als Teams nur Benutzer aktualisiert wird] (media/teams-and-skypeforbusiness-coexistence-and-interop-image1.png "Skype für Business-Client in einem speziellen Modus, nachdem der Benutzer als Teams nur Benutzer aktualisiert wird")

### <a name="skype-for-business-with-teams-collaboration-this-mode-is-upcoming"></a>Skype für Unternehmen mit Teams für die Zusammenarbeit (in diesem Modus wird in Kürze verfügbare)

Verwenden Sie diesen Modus Teams in Ihrer Umgebung einführen, während Sie weiterhin an Ihre vorhandenen Investitionen in Skype für Unternehmen nutzen. In diesem Modus Sie Skype für Unternehmen mit Chat, Anrufe und Besprechung Funktionen unverändert lassen und Hinzufügen von Teams Zusammenarbeitsfunktionen – Teams und Kanäle, den Zugriff auf Dateien in Office 365 und Anwendungen. Organisationen mit ab Punkt von Skype für Business Server vor Ort oder Hybriden sollte diesen Modus anstelle von Inseln Modus verwenden.

### <a name="skype-for-business-with-teams-collaboration-and-meetings-this-mode-is-upcoming"></a>Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen (in diesem Modus wird in Kürze verfügbare)

Verwenden Sie diesen Koexistenzmodus, die die Verfügbarkeit der Teams meeting-Funktionen in Ihrer Organisation, zusätzlich zu den Zusammenarbeitsfunktionen für die, die es den Benutzern ermöglichen die neuen Funktionen wie etwa Lautschrift hochwertige nutzen beschleunigen und Übersetzung und Unterstützung für Besprechungen in Browsern.

Starten Sie zusammen mit Teams für Teams und Kanäle-basierten Unterhaltungen in diesem Modus verwenden, Benutzer verwenden von Teams zum Planen und Durchführen einer Besprechung. Private Chats und VoIP und video-Anruf, bleiben auf Skype für Unternehmen. In diesem Koexistenzmodus ist besonders hilfreich für Benutzer in Skype für Business lokale Bereitstellungen, die Enterprise-VoIP, die voraussichtlich auf Teams aktualisiert werden einige Zeit in Anspruch nimmt, aber die herausragende Teams Besprechungen nutzen möchten.

> [!Note]
> Wenn in bestimmten Koexistenz Modi bereitgestellt haben, können Teams und Skype für Unternehmen [interagieren](#interoperability-of-teams-and-skype-for-business), Aktivieren von Benutzern mit chat und Aufrufen voneinander, und sicherstellen, dass Communications Unze in Ihrer Organisation während Ihrer Reise Upgrade Teams bleiben. Koexistenz Modi steuern Interoperabilität. Der Koexistenzmodus des Empfängers bestimmt, ob Interoperabilität zur Verfügung stehen. Angenommen, wenn der Empfänger in einen Modus in der Chat nur in einem Client (beispielsweise Teams) verfügbar ist wird, stehen Chat Interoperabilität im Allgemeinen zur Verfügung für den Fall, dass der Initiator der anderen Client (in diesem Fall Skype für Unternehmen) verwendet, um den Chat starten. Andererseits, wenn der Empfänger in einen Modus in der Chat in beiden Clients verfügbar ist ist, Interoperabilität nicht verfügbar für die Chat – und die Nachricht wird vom Empfänger im gleichen Client in der der Initiator den Chat gestartet empfangen werden.

Weitere Informationen zur Koexistenz Modi, erforderliche Komponenten und Verwaltung finden Sie unter [Migration und Interoperabilität Anleitungen für Organisationen mit Teams zusammen mit Skype für Unternehmen](https://aka.ms/SkypeToTeams-Interop) und [Festlegen Ihrer Koexistenz und Einstellungen zu aktualisieren](https://aka.ms/SkypeToTeams-SetCoexistence).


|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|Entscheidungspunkt|<ul><li>Welche Koexistenz mindestens einen bewährte passen Anforderungen Ihrer Organisation und der Benutzer?</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|Nächster Schritt|<ul><li>Wählen Sie am besten für Ihre Upgrade Weg.</li></ul>|


## <a name="interoperability-of-teams-and-skype-for-business"></a>Interoperabilität von Teams und Skype für Unternehmen

Interoperabilität ist die Möglichkeit für Teams und Skype für Unternehmensbenutzer in derselben Organisation Kommunikation über Teams und Skype für Unternehmen.


### <a name="native-interop-and-interop-escalation"></a>Systemeigene interop und Interop-Eskalation

Es gibt zwei Arten von interop Erfahrungen: systemeigene und Interop-Weiterleitung.

-   Eine _systemeigene Interop_ -Erfahrung tritt auf, in dem Client, den der Benutzer derzeit verwendet wird. Ein Benutzer werden in der Skype für Business-Client, der andere in Teams. Eine systemeigene Interop-Erfahrung nehmen keine diese an einen anderen Client kommunizieren, die Benutzer werden ihre Unterhaltung in der aktuell verwendeten Client durchführen können. Die systemeigenen interop Erfahrungen sind 1: 1-Chat und aufrufen.
-   Eine _Interop-Eskalation_ wünschen bedeutet, dass im Rahmen der Unterstützung der Benutzer eine erweiterte Aktion (beispielsweise die Freigabe ihres Desktops) ausführen, der Dienst das Erstellen einer Besprechung erleichtern und die Erfahrung in diese Besprechung fortgesetzt werden kann. Die Besprechung wird auf die der Initiator der Aktion-Plattform erstellt. Der Benutzer oder die Benutzer, die auf dieser Plattform erhalten werden nicht meeting Koordinaten beitreten und an der Besprechung teilnehmen (nach dem Wechsel Clients).

### <a name="native-interop-experiences"></a>Systemeigene Interop guter

Je nach der Koexistenz-Modi, die Benutzern (wie oben beschrieben) zugewiesen stehen die folgenden systemeigenen interop Erfahrungen:

-   Skype für Unternehmensbenutzer kann mit Benutzern von Teams und umgekehrt persönlich chatten. Ein interop Chat muss über ein Interop-Gateway zu wechseln, die Teil des Teams ist Cloud-Dienste (und daher nur online vorhanden). Interop-Chats sind nur-Text: rich-Text und Emoticons werden nicht unterstützt. Benutzer in Teams werden benachrichtigt, die die Unterhaltung eine Interop-Unterhaltung ist; eine ähnliche Benachrichtigung für Skype für Unternehmensbenutzer wird bald bereitgestellt.
![Interop chat Erfahrung von Teams] (media/Interop_chat_experience_from_Teams.png "Interop chat Erfahrung von Teams")
-   Skype für Unternehmensbenutzer kann stellen Angebot Sprach- und Videoanrufe an Benutzer Teams, und umgekehrt.
![Interop Aufrufen Erfahrung von Teams] (media/Interop_calling_experience_from_Teams.png "Interop Aufrufen Erfahrung von Teams")

> [!Important]
> Interop-Erfahrungen mit einer lokalen Bereitstellung von Skype für Unternehmen erfordern, dass die lokale Umgebung im Hybridmodus mit Office 365 Skype für Unternehmen wird. Weitere Informationen hierzu finden Sie unter [Migration und Interoperabilität Anweisungen](https://aka.ms/SkypeToTeams-Interop).

Diese interop Erfahrungen stehen und zwischen Benutzern, die einen der folgenden Koexistenz Modi zugewiesen haben: **Skype für Unternehmen mit Teams für die Zusammenarbeit**, **Skype für Unternehmen mit Teams für die Zusammenarbeit und Besprechungen**, **Skype für Nur Business**, oder **nur Teams**. Es ist keine Interoperabilität für Benutzer in Inseln Modus.


### <a name="native-interop-experience-limitations"></a>Einschränkungen der einheitlichen Interop-Erfahrung

Einige Funktionen sind nicht verfügbar für die interop Chat und interop aufrufende Erfahrung zwischen Teams und Skype für Unternehmen:

-   Abzugsverteilung(en), rich-Text und die vollständige Emoticons werden entweder von Teams oder Skype für Unternehmen nicht unterstützt. Andere systemeigenen Funktionen im zum Verfassen in Teams Chats werden nicht unterstützt.
-   Bildschirmfreigabe (Desktop- oder Anwendungsfreigabe) zwischen Teams und Skype für Unternehmen wird nicht unterstützt.
-   Gruppe Chats (mehreren Teilnehmern Unterhaltungen) in Teams können nur Teilnehmern gehören, die Teams arbeiten.
-   Mehrere geführten Sofortnachrichtenunterhaltung (Gruppe Chats) in Skype für Unternehmen können nur Teilnehmer enthalten, die für die Business Skype verwenden.
-   Ausweiten einer laufende Peer-zu-Peer-VoIP oder Videoanruf mit ein Vielfaches von Drittanbietern Telefonat zwischen Teams und Skype für Unternehmensbenutzer wird nicht unterstützt.
-   Dateiübertragung für zwei Teilnehmern Chats oder Dateianhängen in Gruppe Chats von Teams Skype für Unternehmen – und umgekehrt – werden nicht unterstützt.
-   Es ist keine Interoperabilität mit Skype für Business beständigen Chat.

Für diese Einschränkung (außer für beständigen Chat) ist eine mögliche Abhilfe für einen Benutzer eine Besprechung starten und einladen von den anderen Teilnehmer sie beitreten. Diese problemumgehung bildet die Grundlage für die Interop-Eskalation.

> [!Important]
> Was beginnt, wie ein einfacher Chat (IM) schnell einen Anruf oder eine Ad-hoc-Besprechung ausweiten kann. Wir wissen, dass diese Szenarien für die Verwendbarkeit und benutzerfreundlichkeit von entscheidender Bedeutung sind, und wir ständig interop Erfahrungen zwischen Skype für Unternehmen und Teams weiterentwickelt sind. Kontrollkästchen für die aktuellsten Informationen zurück.

Nach der Lektüre dieses Artikels finden Sie unter [Wählen Sie Ihre Reise Upgrade](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [Migration und Interoperabilität Anleitungen](https://aka.ms/SkypeToTeams-Interop)und [Festlegen der Koexistenz und Durchführen eines Upgrades Einstellungen](https://aka.ms/SkypeToTeams-SetCoexistence) Implementierungsdetails.
