---
title: 'Lync Server 2013: Funktionsweise des beständigen Chat Servers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Persistent Chat Server works
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49684643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bf6179e1ce24264c2079b3096fa9bb8c539ca1c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-persistent-chat-server-works-in-lync-server-2013"></a>Funktionsweise des beständigen Chat Servers in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-21_

Lync Server 2013, beständiger Chat Server ermöglicht Ihnen, an mehrteiligen, themenbasierten Konversationen teilzunehmen, die im Laufe der Zeit fortbestehen. Der beständige Chat Server kann Ihrer Organisation helfen, Folgendes zu tun:

  - Verbessern der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams

  - Erweitern des Informations Bewusstseins und der Teilnahme

  - Verbessern der Kommunikation mit ihrer erweiterten Organisation

  - Reduzieren der Informationsüberlastung

  - Verbessern des Informations Bewusstseins

  - Verbessern der Verbreitung wichtiger Kenntnisse und Informationen

Sie können den Server für beständigen Chat als optionale Rolle in lync Server 2013 bereitstellen. Beständige Chat Dienste werden in einem dedizierten Pool ausgeführt, und ein beständiger Chat Serverpool hängt von einem lync Server-Pool ab, um Nachrichten an ihn weiterzuleiten. Clients verwenden eine erweiterbare Chat-Kommunikation über SIP (XCCOS). Die lync Server-Front-End-Server sind so konfiguriert, dass Sie den Datenverkehr an einen beständigen Chat Server Pool weiterleiten.

<div>

## <a name="high-level-architecture"></a>Architektur auf höherer Ebene

Die folgenden Diagramme bieten allgemeine Perspektiven auf die Architektur und Dienste des beständigen Chat Servers.

**Allgemeine Architektur der permanenten Chatserver**

![Server Architektur] für beständigen Chat (images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Server Architektur") für beständigen Chat

**Allgemeine Dienste der permanenten Chatserver**

![Server Komponenten] für beständigen Chat (images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Server Komponenten") für beständigen Chat

Auf den Server-Front-End-Servern des beständigen Chats werden zwei Dienste ausgeführt:

  - Beständiger Chat (Kanal)

  - Compliance

<div>

## <a name="persistent-chat-channel-service"></a>Beständiger Chat (Kanal)-Dienst

Der Dienst für beständigen Chat (Kanal) ist der Hauptdienst, der für den persistenten Chat Server verantwortlich ist. Dieser Dienst bietet die folgenden Funktionen:

  - Annahme eingehender Nachrichten

  - Registrierung und Auflistung der Online-Teilnehmer in einem Chatroom für beständigen Chat

  - Neuübermittlung von Nachrichten an andere Abonnenten des Kanals

  - Implementiert die Logik für die Kanalverwaltung, die Einladung zu Chatrooms, die Suche und neue Inhalts Benachrichtigungen.

Der Dienst für beständigen Chat (Kanal) speichert und greift auf Chatroom-Inhalte und andere Systemmetadaten (Autorisierungsregeln usw.) mithilfe des beständigen Chat Speichers zu. Dieser Dienst speichert Dateien, die in Chatrooms im persistenten Chat-Dateispeicher hochgeladen werden.

</div>

<div>

## <a name="compliance-service"></a>Kompatibilitätsdienst

Der Kompatibilitätsdienst ist eine optionale Komponente des Servers für beständigen Chat und ist für das Archivieren von Chat Inhalten und Ereignissen im Compliance Store für beständigen Chat verantwortlich. Wenn es in Ihrer Organisation Vorschriften gibt, nach denen Aktivitäten des beständigen Chats zu archivieren sind, können Sie den optionalen Kompatibilitätsdienst für beständigen Chat bereitstellen. Der Kompatibilitätsdienst wird auf jedem beständigen Chat Server in einem beständigen Chat-Pool installiert. Nach der Konfiguration zeichnet die beständige Chat Server-Compliance Benutzeraktivitäten auf, beispielsweise das beitreten und verlassen von Räumen sowie das Posten und Lesen von Nachrichten. Der Kompatibilitätsdienst speichert Dateien, die im beständigen Chat-Kompatibilitätsdatei Speicher archiviert werden müssen.

</div>

<div>

## <a name="persistent-chat-web-services"></a>Beständige Chat-Webdienste

Auf den lync Server-Front-End-Servern werden zwei Dienste ausgeführt, die von Internet Informationsdiensten (IIS) abhängen und als Webkomponenten implementiert sind:

  - **Beständige Chat-Webdienste für Datei Upload/-Download** Verantwortlich für das Posten und Abrufen von Dateien aus Chatrooms.

  - **Beständige Chat-Webdienste für die Chat Raumverwaltung** Verantwortlich dafür, dass Benutzer die Möglichkeit haben, ihre Chatrooms zu verwalten und neue Chatrooms zu erstellen.

</div>

</div>

<div>

## <a name="how-do-i-start-using-persistent-chat-server"></a>Wie beginne ich mit der Verwendung des beständigen Chat Servers?

Der beständige Chat Server ist eine optionale Serverrolle innerhalb der lync Server 2013-Infrastruktur. Wenn Sie die Server Funktion "beständiger Chat" installieren, können alle Benutzer, die über eine Richtlinie von einem Administrator aktiviert wurden, beständigen Chat mit dem lync 2013-Client verwenden.

Ausführliche Informationen zum Bereitstellen eines beständigen Chat Servers und zur Nutzung der Funktionen durch Richtlinien finden Sie unter [Bereitstellen eines beständigen Chat Servers in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Weitere Informationen zum Konfigurieren von Einstellungen für die Bereitstellung von beständigen Chatservern finden Sie unter [Bereitstellen eines beständigen Chat Servers in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) und [Verwalten von lync Server 2013, beständiger Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Ausführliche Informationen dazu, wie Sie Benutzer nach Richtlinie so aktivieren können, dass Sie die Funktionalität des beständigen Chats in lync 2013-Client nutzen können, finden Sie unter [Bereitstellen eines persistenten Chat Servers in lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) und [Verwalten von lync Server 2013, beständiger Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Wenn Sie die Compliance für beständigen Chat bereitgestellt haben, finden Sie weitere Informationen zum Konfigurieren von Einstellungen für die Kompatibilität unter [Verwalten von lync Server 2013, beständiger Chat Server](managing-lync-server-2013-persistent-chat-server.md) .

</div>

<div>

## <a name="persistent-chat-call-flows"></a>Beständige Chat-Anruf Flüsse

Der beständige Chat-Client kommuniziert mit dem beständigen Chatdienst mithilfe von XCCOS. In den folgenden Sequenzen werden der Anmeldevorgang und ein typisches Raum Abonnement und ein Nachrichten Post Szenario beschrieben.

<div>

## <a name="sign-in"></a>Anmeldung

Das folgende Anruffluss Diagramm und die folgenden Schritte beschreiben den Anmeldeprozess.

**Beständiger Chat-Client-Anmelde Anruffluss**

![Anruffluss Diagramm für beständigen Chat Server] (images/JJ683096.9b3b3c61-caca-42b6-853c-6a09e6ff5c44(OCS.15).jpg "Anruffluss Diagramm für beständigen Chat Server")

1.  Der beständige Chat-Client sendet zunächst ein SIP-Abonnement, um das in-Band-Bereitstellungs Dokument vom Server abzurufen. Dieses Dokument zeigt an, ob der beständige Chat für den Benutzer aktiviert oder deaktiviert ist, und die Liste der SIP-URIs für den Server Pool des beständigen Chats.

2.  Der beständige Chat-Client sendet eine SIP-Einladungsnachricht an den SIP-URI des beständigen Chat Servers, der im vorherigen Schritt abgerufen wurde. Auf die Einladungs Sequenz folgt 200 OK und ACK, und der beständige Chat-Client hat nun eine SIP-Sitzung mit einem beständigen Chat Server-Endpunkt geöffnet. Infolgedessen kommuniziert der beständige Chat-Client mit dem beständigen Chat Server durch Senden von SIP-Info-Nachrichten, die entweder Chat Nachrichten oder Befehle enthalten, die den Server zum Ausführen einer Aktion anfordern. Alle diese Nachrichten werden bestätigt, wenn der 200 OK-oder 503-Dienst nicht verfügbar ist (im Fall einer starken Serverauslastung). Wenn der Client eine 503-Antwort erhält, wird die Nachricht erneut versucht. (In diesem Beispiel ist keine 503-Antwort eingeschlossen.) Wenn der Server die Nachricht oder den Befehl akzeptiert und 200 OK sendet, stellt er eine Antwort an den Client in Form einer separaten SIP-INFO Nachricht zur Verfügung. Diese Antwort enthält einen Verweis auf den ursprünglichen Befehl.

3.  Der beständige Chat-Client sendet eine SIP-INFO-Nachricht mit dem Befehl XCCOS **getServerInfo** . Der beständige Chat Server antwortet mit einer neuen SIP-INFO Nachricht, die Informationen zur Konfiguration des beständigen Chats enthält.

4.  Der beständige Chat-Client sendet eine SIP-Info- **** Nachricht, die den Befehl XCCOS GetAssociations enthält. Der beständige Chat Server antwortet mit einer neuen SIP-INFO Nachricht, die die Liste der Chatrooms enthält, in denen der Benutzer Mitglied ist. Der beständige Chat-Client wiederholt den Befehl, um die Liste der Räume abzurufen, deren Manager der Benutzer ist.

5.  Der beständige Chat-Client ruft die Liste der befolgten Räume aus dem Dokument "Anwesenheit" ab, in dem jeder befolgte Raum durch eine Kategorie "roomSetting" dargestellt wird. Alle folgenden Chatrooms werden durch eine einzelne SIP-INFO Nachricht verbunden, die den Befehl XCCOS **btreten** enthält, der die Liste der Raum-URIs enthält. Da die Liste der nachverfolgten Räume auf dem Server gespeichert wird, verfügt jeder Client auf einem Computer über die gleiche Liste der folgenden Chatrooms für den angegebenen Benutzer-URI. Der beständige Chat-Client speichert auch die Liste der geöffneten Chatrooms (wenn diese Option vom Benutzer aktiviert ist) in der Registrierung des lokalen Computers und verknüpft jeden dieser Chatrooms bei der Anmeldung durch Senden einer SIP-INFO Nachricht, die den XCCOS- **Join** -Befehl für jeden geöffneten Chatroom enthält. . Da diese Liste in der Registrierung aufbewahrt wird, kann Sie bei zwei beständigen Chat-Clients unterschiedlich sein, die auf unterschiedlichen Computern ausgeführt werden.

6.  Für jeden beige tretenen Chatroom sendet der beständige Chat-Client eine SIP-INFO-Nachricht, die den Befehl XCCOS **bccontext** enthält. Der beständige Chat Server antwortet mit einer neuen SIP-INFO Nachricht, die die neueste Chatnachricht im Chatroom enthält.

7.  Der beständige Chat-Client sendet eine SIP-INFO-Nachricht, die eine XCCOS- **GetInv** (also Einladung) enthält, um neue Raum Einladungen anzufordern, die der Kunde noch nicht gesehen hat. In einer separaten SIP-INFO Nachricht gibt der beständige Chat Server eine Liste dieser Chatrooms zurück.

</div>

<div>

## <a name="subscribe-to-a-room-and-post-a-message"></a>Abonnieren eines Chatrooms und Posten einer Nachricht

Das folgende Anruffluss Diagramm und die folgenden Schritte beschreiben ein typisches Raum Abonnement und ein Nachrichten Post Szenario.

**Beständiger Chat-Client Raum-Abonnement und Nachrichten Buchung-Anruffluss**

![Szenario für Raum Abonnements und Nachrichten] (images/JJ683096.2d3c417e-c91b-42bd-964e-285b72bb2e44(OCS.15).jpg "Szenario für Raum Abonnements und Nachrichten")

1.  Im beständigen Chat-Client klickt Benutzer1 auf **an einem Chatroom teilnehmen**, klickt auf **Suchen**und gibt dann einige Suchkriterien ein. Der beständige Chat-Client sendet eine SIP-INFO-Nachricht, die den Befehl XCCOS **chansrch** (Raum Suche) zusammen mit den Suchkriterien enthält. Der beständige Chat Server fragt die Back-End-Datenbank ab und antwortet in einer neuen SIP-INFO Nachricht, die eine Liste der verfügbaren Räume enthält, die den Suchkriterien entsprechen.

2.  Benutzer1 wählt den Chatroom aus, dem er beitreten möchte, und klickt dann auf **diesem Chatroom folgen**. Der beständige Chat-Client sendet beständigen Chat Server eine SIP-INFO-Nachricht, die den XCCOS- **Join** -Befehl und die Raum-ID des Chatrooms enthält, den der Benutzer ausgewählt hat. Der beständige Chat Server antwortet mit einer SIP-INFO Nachricht, die die Bereitstellungsdaten enthält.

3.  Der beständige Chat-Client sendet beständigen Chat Server eine SIP-INFO-Nachricht, die den Befehl XCCOS **bccontext** (Backchat-Kontext) enthält. Der beständige Chat Server Ruft das Chat-Protokoll ab und gibt es in einer separaten SIP-INFO-Nachricht an den beständigen Chat-Client zurück. An diesem Punkt wechselt der Benutzer in den Chatroom und kann teilnehmen.

4.  Benutzer1 gibt eine neue Nachricht ein und klickt dann auf **senden**. Der beständige Chat-Client Bucht die Nachricht in einem Chatroom in einem SIP-Info-XCCOS **grpchat** Befehl. Der beständige Chat Server speichert eine Kopie dieser neuen Nachricht in der Back-End-Datenbank des beständigen Chats.

5.  Der beständige Chat Server sendet eine separate Kopie der SIP-Info-XCCOS **grpchat** -Nachricht an User2, der den Chatroom bereits betreten hat.

</div>

</div>

<div>

## <a name="persistent-chat-compliance-call-flows"></a>Compliance-Anruf Flüsse für beständigen Chat

Der Server für beständigen Chat verwendet Message Queuing (auch als MSMQ bezeichnet) und eine zusätzliche Kompatibilitätsdatenbank (mgccomp), um Kompatibilitätsdaten zu verarbeiten. Als Beispiel für die Verarbeitung von Kompatibilitäts Ereignissen beschreibt die folgende Abfolge von Ereignissen, wie ein Nachrichten Post-Ereignis verarbeitet wird.

1.  Ein Benutzer Bucht eine Nachricht in einem Raum.

2.  Der Server für beständigen Chat platziert Informationen, die sich auf das Ereignis beziehen, in einer privaten Message Queuing-Warteschlange.

3.  Der beständige Chat-Kompatibilitätsserver liest dieses Ereignis aus der Warteschlange und platziert es zur späteren Verarbeitung in der mgccomp-Datenbank.

4.  Der beständige Chat-Kompatibilitätsserver verarbeitet in regelmäßigen Abständen eine Reihe von Ereignissen in der Datenbank und sendet Sie zur Verarbeitung an den Compliance-Adapter für beständigen Chat.

5.  Wenn der Adapter die Daten erfolgreich verarbeitet, löscht der beständige Chat-Kompatibilitätsserver die Ereignisse aus der mgccomp-Datenbank.

</div>

</div>

<span> </span>

</div>

</div>

</div>

