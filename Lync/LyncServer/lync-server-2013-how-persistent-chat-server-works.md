---
title: 'Lync Server 2013: Funktionsweise des Servers für beständigen Chat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c582ad9e21e111745dc55fd2d43feada761e58d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Funktionsweise von persistent Chat Server in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-21_

Lync Server 2013 können Sie mit dem Server für beständigen Chat an mehrteiligen, themenbasierten Unterhaltungen teilnehmen, die im Laufe der Zeit beibehalten werden. Der Server für beständigen Chat kann Ihrer Organisation dabei helfen, Folgendes zu tun:

  - Verbesserung der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams

  - Förderung von Informationsbewusstsein und aktiver Teilnahme

  - Verbesserung der Kommunikation über alle Unternehmensbereiche hinweg

  - Verringerung der Informationsüberlastung

  - Verbesserung des Informationsbewusstseins

  - Gezielte Weitergabe wichtigen Wissens und wichtiger Informationen

Sie können den Server für beständigen Chat mit lync Server 2013 als optionale Rolle bereitstellen. Die Dienste für beständigen Chat werden in einem dedizierten Pool ausgeführt, und ein Server Pool für beständigen Chat hängt von einem lync Server Pool ab, um Nachrichten an ihn weiterzuleiten. Clients verwenden eXtensible Chat Communication Over SIP (XCCOS). Die lync Server-Front-End-Server sind so konfiguriert, dass der Datenverkehr an einen Server Pool für beständigen Chat weitergeleitet wird.

<div>

## <a name="high-level-architecture"></a>Allgemeine Architektur

Die folgenden Diagramme bieten allgemeine Perspektiven der Architektur und der Dienste für den Server für beständigen Chat.

**Allgemeine Architektur der permanenten Chatserver**

![Server Architektur für beständigen Chat.](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Server Architektur für beständigen Chat.")

**Allgemeine Dienste der permanenten Chatserver**

![Server Komponenten für beständigen Chat.](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Server Komponenten für beständigen Chat.")

Auf den Front-End-Servern für beständigen Chat Server werden zwei Dienste ausgeführt:

  - Beständiger Chat (Kanal)

  - Compliance

<div>

## <a name="persistent-chat-channel-service"></a>Beständiger Chat- (Kanal-) Dienst

Der Dienst für beständigen Chat (Kanal) ist der Hauptdienst, der für den Server für beständigen Chat verantwortlich ist. Dieser Dienst bietet folgende Funktionen:

  - Annahme eingehender Nachrichten

  - Registrieren und Auflisten von Online-Teilnehmern in einem beständigen Chatroom

  - Neuübermittlung von Nachrichten an andere Abonnenten des Kanals

  - Implementierung der Logik zur Kanalverwaltung, Chatroomeinladung, Suche und Benachrichtigungen über neue Inhalte

Der Dienst für beständigen Chat (Kanal) speichert und greift auf Chatroom-Inhalte und andere Systemmetadaten (Autorisierungsregeln usw.) mithilfe des Speichers für beständigen Chat zu. In diesem Dienst werden Dateien gespeichert, die in Chatrooms im Dateispeicher für beständigen Chat hochgeladen werden.

</div>

<div>

## <a name="compliance-service"></a>Kompatibilitätsdienst

Der Kompatibilitätsdienst ist eine optionale Komponente des Servers für beständigen Chat und ist für das Archivieren von Chat Inhalten und Ereignissen im Compliance-Speicher für beständigen Chat verantwortlich. Wenn Ihre Organisation über Regelungen verfügt, bei denen die Aktivität für beständigen Chat archiviert werden muss, können Sie den optionalen Kompatibilitätsdienst für beständigen Chat bereitstellen. Der Kompatibilitätsdienst wird auf jedem Server für beständigen Chat in einem Pool für beständigen Chat installiert. Bei der Konfiguration von beständigen Chat Servern werden Benutzeraktivitäten wie das Hinzufügen und verlassen von Räumen sowie das Veröffentlichen und Lesen von Nachrichten aufgezeichnet. Der Kompatibilitätsdienst speichert Dateien, die im Compliance-Dateispeicher für beständigen Chat archiviert werden müssen.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Webdienste für beständigen Chat

Auf den lync Server-Front-End-Servern werden zwei Dienste ausgeführt, die von Internet Information Services (IIS) abhängen und als Webkomponenten implementiert werden:

  - **Webdienste für beständigen Chat für Datei Upload/-Download** Verantwortlich für das Veröffentlichen und Abrufen von Dateien aus Chatrooms.

  - **Webdienste für beständigen Chat für die Chat Raumverwaltung** Verantwortlich für die Bereitstellung von Benutzern, die ihre Chatrooms verwalten und neue Chatrooms erstellen können.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>Wie fange ich mit dem Server für beständigen Chat an?

Der Server für beständigen Chat ist eine optionale Serverrolle in der lync Server 2013 Infrastruktur. Wenn Sie die Server Rolle "persistent Chat" installieren, können alle Benutzer, die über eine Richtlinie eines Administrators aktiviert wurden, den beständigen Chat mit dem lync 2013-Client verwenden.

Ausführliche Informationen zum Bereitstellen des Servers für beständigen Chat und zur Aktivierung der Funktionen durch Richtlinien finden Sie unter [Deploying persistent Chat Server in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Ausführliche Informationen zum Konfigurieren von Einstellungen für die Bereitstellung von persistent Chat Server finden Sie unter [Deploying persistent Chat Server in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) und [Managing lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Ausführliche Informationen zum Aktivieren von Benutzern durch Richtlinien, sodass Sie Funktionen für beständigen Chat in lync 2013-Client nutzen können, finden Sie unter [Deploying persistent Chat Server in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) und [Managing lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Wenn Sie die Compliance für beständigen Chat bereitgestellt haben, finden Sie weitere Informationen zum Konfigurieren von Einstellungen für die Kompatibilität unter [Managing lync Server 2013, persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) .

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Anruf Flüsse für beständigen Chat

Der Client für beständigen Chat kommuniziert mithilfe von XCCOS mit dem Dienst für beständigen Chat. Die folgenden Sequenzen beschreiben den Anmeldevorgang und ein typisches Szenario beim Abonnieren eines Raums und beim Veröffentlichen einer Nachricht.

<div>

## <a name="sign-in"></a>Anmelden

Das folgende Anruffluss Diagramm und die folgenden Schritte beschreiben den Anmeldevorgang.

**Anruffluss für den Client für beständigen Chat**

![Anruffluss Diagramm für beständigen Chat Server.](images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Anruffluss Diagramm für beständigen Chat Server.")

1.  Der Client für beständigen Chat sendet zunächst einen SIP subscribe, um das in-Band-Dokument vom Server abzurufen. Dieses Dokument gibt an, ob der beständige Chat für den Benutzer und die Liste der SIP-URIs für den Server Pool für beständigen Chat aktiviert oder deaktiviert ist.

2.  Der Client für beständigen Chat sendet eine SIP INVITE-Nachricht an den SIP-URI des Servers für beständigen Chat, den Sie im vorherigen Schritt erhalten hat. Die Invite-Sequenz wird von 200 OK und ACK gefolgt, und der Client für beständigen Chat hat jetzt eine SIP-Sitzung mit einem Server Endpunkt für beständigen Chat geöffnet. Folglich kommuniziert der Client für beständigen Chat mit dem Server für beständigen Chat, indem SIP-Info Nachrichten gesendet werden, die entweder Chat Nachrichten oder Befehle enthalten, die den Server anfordern, eine Aktion durchführen. Alle diese Nachrichten werden mit 200 OK oder 503 Dienst nicht verfügbar (das heißt, im Falle einer schweren Serverlast) bestätigt. Wenn der Client eine 503-Antwort erhält, wird die Nachricht wiederholt. (In diesem Beispiel ist keine 503-Antwort enthalten.) Wenn der Server die Nachricht oder den Befehl akzeptiert und 200 OK sendet, stellt er eine Antwort an den Client in Form einer separaten SIP-INFO-Nachricht bereit. Diese Antwort enthält einen Verweis auf den ursprünglichen Befehl.

3.  Der Client für beständigen Chat sendet eine SIP-INFO-Nachricht, die den Befehl XCCOS **getServerInfo** enthält. Der Server für beständigen Chat antwortet mit einer neuen SIP-INFO-Nachricht, die Informationen zur Konfiguration des beständigen Chat Diensts enthält.

4.  Der Client für beständigen Chat sendet eine SIP-INFO-Nachricht, die den Befehl XCCOS **GetAssociations** enthält. Der Server für beständigen Chat antwortet mit einer neuen SIP-INFO-Nachricht, die die Liste der Räume enthält, in denen der Benutzer Mitglied ist. Der Client für beständigen Chat wiederholt den Befehl, um die Liste der Räume abzurufen, von denen der Benutzer ein Vorgesetzter ist.

5.  Der Client für beständigen Chat Ruft die Liste der befolgten Räume aus dem Dokument "Presence" ab, wobei jeder gefolgte Raum durch eine Kategorie "roomSetting" dargestellt wird. Der Beitritt zu allen Räumen, denen der Benutzer folgt, geschieht durch eine einzige SIP INFO-Nachricht, die den XCCOS-Befehl **bjoin** mit der Liste der Raum-URIs enthält. Da die Liste der Räume, denen der Benutzer folgt, auf dem Server gespeichert ist, verfügt jeder Client auf jedem Computer für die angegebene Benutzer-URI über dieselbe Liste der Räume, denen der Benutzer folgt. Der Client für beständigen Chat behält auch die Liste der geöffneten Räume (falls diese Option vom Benutzer aktiviert ist) in der Registrierung des lokalen Computers bei und verbindet jeden dieser Räume bei der Anmeldung, indem er eine SIP-INFO-Nachricht sendet, die den XCCOS- **Join** -Befehl für jeden geöffneten Raum enthält. Da diese Liste in der Registrierung aufbewahrt wird, kann Sie in zwei auf unterschiedlichen Computern ausgeführten Clients für beständigen Chat unterschiedlich sein.

6.  Für jeden beigefügten Chatroom sendet der Client für beständigen Chat eine SIP-INFO-Nachricht, die den Befehl XCCOS **bccontext** enthält. Der Server für beständigen Chat antwortet mit einer neuen SIP-INFO-Nachricht, die die neueste Chat Nachricht im Chatroom enthält.

7.  Der Client für beständigen Chat sendet eine SIP-INFO-Nachricht, die einen XCCOS- **GetInv** (also, Get-Einladungs Befehl) enthält, um neue Raum Einladungen anzufordern, die der Client noch nicht gesehen hat. In einer separaten SIP-INFO-Nachricht gibt der Server für beständigen Chat eine Liste dieser Räume zurück.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>Abonnieren eines Raums und Veröffentlichen einer Nachricht

Das folgende Anruffluss Diagramm und die folgenden Schritte beschreiben ein typisches Raum Abonnement und ein Nachrichten Post Szenario.

**Beständiger Chat-Client Raum Abonnement und Nachrichten Übermittlungs Anruffluss**

![Szenario für Raum Abonnements und Nachrichten Bereitstellung.](images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Szenario für Raum Abonnements und Nachrichten Bereitstellung.")

1.  Im Client für beständigen Chat klickt user1 auf **einem Chatroom beitreten**, klickt auf **Suche**und gibt dann einige Suchkriterien ein. Der Client für beständigen Chat sendet eine SIP-INFO-Nachricht, die den Befehl XCCOS **chansrch** (Raumsuche) enthält, sowie die Suchkriterien. Der Server für beständigen Chat fragt die Back-End-Datenbank ab und antwortet in einer neuen SIP-INFO-Nachricht, die eine Liste der verfügbaren Räume enthält, die den Suchkriterien entsprechen.

2.  Benutzer1 wählt den Chatroom aus, den er betreten möchte, und klickt auf **Diesem Raum folgen**. Der Client für beständigen Chat sendet beständigen Chat Server eine SIP-INFO-Nachricht, die den XCCOS- **Join** -Befehl und die Raum-ID des Chatrooms enthält, den der Benutzer ausgewählt hat. Der Server für beständigen Chat antwortet mit einer SIP-INFO-Nachricht, die die Bereitstellung von Daten enthält.

3.  Der persistent Chat-Client sendet beständigen Chat Server eine SIP-INFO-Nachricht, die den XCCOS **bccontext** -Befehl (Backchat-Kontext) enthält. Der Server für beständigen Chat Ruft den Chatverlauf ab und gibt ihn in einer separaten SIP-INFO-Nachricht an den Client für beständigen Chat zurück. An diesem Punkt betritt der Benutzer den Chatroom und ist bereit zur Teilnahme.

4.  Benutzer1 gibt eine neue Nachricht ein und klickt anschließend auf **Senden**. Der Client für beständigen Chat sendet die Nachricht in einem SIP-Info-XCCOS- **grpchat** -Befehl an den Chatroom. Der Server für beständigen Chat speichert eine Kopie dieser neuen Nachricht in der Back-End-Datenbank des beständigen Chats.

5.  Der Server für beständigen Chat sendet eine separate Kopie der **grpchat** -Nachricht für SIP-Informationen XCCOS an Benutzer2, die bereits in den Chatroom eingetreten ist.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Compliance-Anruf Flüsse für beständigen Chat

Der Server für beständigen Chat verwendet Message Queuing (auch als MSMQ bezeichnet) und eine zusätzliche Kompatibilitätsdatenbank (mgccomp), um Kompatibilitätsdaten zu verarbeiten. Als Beispiel dafür, wie Kompatibilitätsereignisse verarbeitet werden, beschreibt die folgende Ereignissequenz, wie ein Ereignis "Veröffentlichen einer Nachricht" verarbeitet wird.

1.  Ein Benutzer schreibt eine Nachricht in einem Chatroom.

2.  Der Server für beständigen Chat platziert Informationen in Bezug auf das Ereignis in einer privaten Message Queuing-Warteschlange.

3.  Compliance-Server für beständigen Chat liest dieses Ereignis aus der Warteschlange und platziert es zur späteren Verarbeitung in der mgccomp-Datenbank.

4.  Der Kompatibilitätsserver für beständigen Chat verarbeitet regelmäßig eine Reihe von Ereignissen in der Datenbank und sendet Sie zur Verarbeitung an den Kompatibilitätsadapter für beständigen Chat.

5.  Wenn der Adapter die Daten erfolgreich verarbeitet, löscht der Kompatibilitätsserver für beständigen Chat die Ereignisse aus der mgccomp-Datenbank.

</div>

</div>

<span> </span>

</div>

</div>

</div>

