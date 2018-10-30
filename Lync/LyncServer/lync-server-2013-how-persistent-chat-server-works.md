---
title: Funktionsweise von Persistent Chat Server in Lync Server 2013
TOCTitle: Funktionsweise von Persistent Chat Server in Lync Server 2013
ms:assetid: 3d04e9a1-3f0c-458e-bcbe-d27c8c464276
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ683096(v=OCS.15)
ms:contentKeyID: 49890713
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Funktionsweise von Persistent Chat Server in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-11-21_

Lync Server 2013, Server für beständigen Chat ermöglicht Ihnen die Teilnahme an themenbasierten Unterhaltungen mit mehreren Teilnehmern, die im Verlauf erhalten bleiben. Server für beständigen Chat kann Ihre Organisation bei Folgendem unterstützen:

  - Verbesserung der Kommunikation zwischen geografisch verteilten und funktionsübergreifenden Teams

  - Förderung von Informationsbewusstsein und aktiver Teilnahme

  - Verbesserung der Kommunikation über alle Unternehmensbereiche hinweg

  - Verringerung der Informationsüberlastung

  - Verbesserung des Informationsbewusstseins

  - Gezielte Weitergabe wichtigen Wissens und wichtiger Informationen

Sie können Server für beständigen Chat als optionale Rolle mit Lync Server 2013 bereitstellen. Beständiger Chat-Dienste werden in einem dedizierten Pool ausgeführt, und ein Serverpool für beständigen Chat ist abhängig von einem Lync Server-Pool, der Nachrichten an ihn weiterleitet. Clients verwenden eXtensible Chat Communication Over SIP (XCCOS). Die Lync Server-Front-End-Server sind so konfiguriert, dass sie den Datenverkehr an einen Serverpool für beständigen Chat weiterleiten.

## Allgemeine Architektur

Die folgenden Diagramme enthalten allgemeine Punkte zu Server für beständigen Chat-Architektur und -Diensten.

**Allgemeine Architektur der permanenten Chatserver**

![Architektur des Servers für beständigen Chat](images/JJ683096.5db6f36f-4461-4d87-ba77-463b7ffe609b(OCS.15).jpg "Architektur des Servers für beständigen Chat")

**Allgemeine Dienste der permanenten Chatserver**

![Komponenten des Servers für beständigen Chat](images/JJ683096.b6d743aa-3a86-4081-aaef-4fe3257db4e7(OCS.15).jpg "Komponenten des Servers für beständigen Chat")

Auf den Server für beständigen Chat-Front-End-Server werden zwei Dienste ausgeführt:

  - Beständiger Chat (Kanal)

  - Kompatibilität

## Beständiger Chat- (Kanal-) Dienst

Der Beständiger Chat- (Kanal-) Dienst ist der Hauptdienst, der für Server für beständigen Chat verantwortlich ist. Dieser Dienst bietet folgende Funktionen:

  - Annahme eingehender Nachrichten

  - Registrierung und Auflistung der Online-Teilnehmer in einem Beständiger Chatroom

  - Neuübermittlung von Nachrichten an andere Abonnenten des Kanals

  - Implementierung der Logik zur Kanalverwaltung, Chatroomeinladung, Suche und Benachrichtigungen über neue Inhalte

Der Beständiger Chat-Kanal-Dienst speichert Chatroominhalte und andere System-Metadaten (Autorisierungsregeln usw.) mithilfe des Beständiger Chatspeichers und greift darauf zu. Dieser Dienst speichert Dateien, die in Chatrooms hochgeladen werden, im Beständiger Chat-Dateispeicher.

## Kompatibilitätsdienst

Der Kompatibilitätsdienst ist eine optionale Komponente von Server für beständigen Chat und verantwortlich für die Archivierung von Chatinhalten und Ereignissen im Beständiger Chat-Kompatibilitätsspeicher. Wenn Ihre Organisation über Vorschriften verfügt, die eine Archivierung von Beständiger Chat-Aktivitäten erfordern, können Sie den optionalen Beständiger Chat-Kompatibilitätsdienst bereitstellen. Der Kompatibilitätsdienst ist auf jedem Server für beständigen Chat in einem Beständiger Chat-Pool installiert. Wenn er konfiguriert ist, zeichnet der Server für beständigen Chat-Kompatibilitätsdienst Benutzeraktivitäten wie das Betreten und Verlassen von Räumen oder das Veröffentlichen und Lesen von Nachrichten auf. Der Kompatibilitätsdienst speichert Dateien, die archiviert werden müssen, im Beständiger Chat-Kompatibilitätsdateispeicher.

## Beständiger Chat-Webdienste

Auf den Lync ServerFront-End-Server werden zwei Dienste ausgeführt, die von Internetinformationsdienste (Internet Information Services, IIS) abhängig sind und als Webkomponenten implementiert werden:

  - **Beständiger Chat-Webdienste für das Hoch-/Herunterladen von Dateien:** Verantwortlich für das Veröffentlichen und Abrufen von Dateien in bzw. aus Chatrooms.

  - **Beständiger Chat-Webdienste zur Chatroomverwaltung:** Verantwortlich dafür, Benutzern zu ermöglichen, ihre Chatrooms zu verwalten und neue Chatrooms zu erstellen.

## Gewusst wie: Mit der Verwendung von Server für beständigen Chat beginnen

Server für beständigen Chat ist eine optionale Serverrolle innerhalb der Lync Server 2013-Infrastruktur. Wenn Sie die Server für beständigen Chat-Rolle installieren, können alle Benutzer, die aufgrund einer Richtlinie durch einen Administrator dafür aktiviert wurden, Beständiger Chat mit dem Lync 2013-Client verwenden. Ausführliche Informationen zur Bereitstellung von Server für beständigen Chat und zur Aktivierung der Nutzung der Fähigkeiten durch Benutzer per Richtlinie finden Sie unter [Bereitstellen des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md).

Ausführliche Informationen zur Konfiguration von Einstellungen auf Ihrer Server für beständigen Chat-Bereitstellung finden Sie unter [Bereitstellen des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) und [Verwalten von Lync Server 2013 Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Ausführliche Informationen zur Aktivierung von Benutzern per Richtlinie, sodass sie Beständiger Chat-Funktionen auf dem Lync 2013-Client nutzen können, finden Sie unter [Bereitstellen des Servers für beständigen Chat in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) und [Verwalten von Lync Server 2013 Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md).

Wenn Sie die Beständiger Chat-Kompatibilität bereitgestellt haben, finden Sie unter [Verwalten von Lync Server 2013 Persistent Chat Server](managing-lync-server-2013-persistent-chat-server.md) ausführliche Informationen zur Konfiguration von Kompatibilitätseinstellungen.

## Beständiger Chat-Anrufflüsse

Der Lync-Client kommuniziert mit dem Beständiger Chat-Dienst über XCCOS. Die folgenden Sequenzen beschreiben den Anmeldevorgang und ein typisches Szenario beim Abonnieren eines Raums und beim Veröffentlichen einer Nachricht.

## Anmeldung

In der folgenden Sequenz wird der Anmeldevorgang beschrieben.

1.  Der Lync-Client sendet zunächst einen SIP SUBSCRIBE, um das In-Band-Bereitstellungsdokument vom Server abzurufen. Dieses Dokument gibt an, ob Beständiger Chat für den Benutzer aktiviert oder deaktiviert ist, und es enthält die Liste der SIP-URIs für den Serverpool für beständigen Chat.

2.  Der Lync-Client sendet eine SIP INVITE-Nachricht an die SIP-URI des Server für beständigen Chats, die er im vorigen Schritt empfangen hat. Auf die INVITE-Sequenz folgen "200 OK" und "ACK". Der Lync-Client hat nun eine SIP-Sitzung mit einem Server für beständigen Chat-Endpunkt eröffnet. Folglich kommuniziert der Client mit dem Server für beständigen Chat durch Senden von SIP INFO-Nachrichten, die entweder Chatnachrichten oder Befehle zur Ausführung einer Aktion durch den Server enthalten. All diese Nachrichten werden entweder mit "200 OK" oder "503 - Dienst nicht verfügbar" (bei hoher Serverauslastung) angenommen. Wenn der Client eine 503-Antwort erhält, versucht er, die Nachricht erneut zu senden. (Dieses Beispiel enthält keine 503-Antwort.) Wenn der Server die Nachricht oder den Befehl annimmt und "200 OK" zurücksendet, gibt er eine Antwort an den Client in Form einer separaten SIP INFO-Nachricht. Diese Antwort enthält einen Verweis auf den ursprünglichen Befehl.

3.  Der Lync-Client sendet eine SIP INFO-Nachricht, die den XCCOS-Befehl **getserverinfo** enthält. Der Server für beständigen Chat antwortet mit einer neuen SIP INFO-Nachricht, die Informationen über die Beständiger ChatDienstkonfiguration enthält.

4.  Der Lync-Client sendet eine SIP INFO-Nachricht, die den XCCOS-Befehl **getassociations** enthält. Der Server für beständigen Chat antwortet mit einer neuen SIP INFO-Nachricht, die die Liste der Räume enthält, deren Mitglied der Benutzer ist. Der Lync-Client wiederholt den Befehl zum Abrufen der Liste mit Räumen, in denen der Benutzer Manager ist.

5.  Der Lync-Client empfängt die Liste der Räume, denen der Benutzer folgt, aus dem Anwesenheitsdokument, wobei jeder der Räume, denen der Benutzer folgt, durch eine "roomSetting"-Kategorie dargestellt wird. Der Beitritt zu allen Räumen, denen der Benutzer folgt, geschieht durch eine einzige SIP INFO-Nachricht, die den XCCOS-Befehl **bjoin** mit der Liste der Raum-URIs enthält. Da die Liste der Räume, denen der Benutzer folgt, auf dem Server gespeichert ist, verfügt jeder Client auf jedem Computer für die angegebene Benutzer-URI über dieselbe Liste der Räume, denen der Benutzer folgt. Der Lync-Client speichert auch die Liste der geöffneten Räume (wenn diese Option durch den Benutzer aktiviert wird) in der lokalen Registrierung des Computers und betritt jeden dieser Räume bei der Anmeldung durch das Senden einer SIP INFO-Nachricht mit dem XCCOS-Befehl **join** für jeden geöffneten Raum. Da diese Liste in der Registrierung aufbewahrt wird, kann sie auf zwei Lync-Clients, die auf verschiedenen Computern ausgeführt werden, unterschiedlich sein.

6.  Für jeden Raum, den der Benutzer betritt, sendet der Lync-Client eine SIP INFO-Nachricht mit dem XCCOS-Befehl **bccontext**. Der Server für beständigen Chat antwortet mit einer neuen SIP INFO-Nachricht, die die neueste Chatnachricht in diesem Raum enthält.

7.  Der Lync-Client sendet eine SIP INFO-Nachricht mit dem XCCOS-Befehl **getinv** ("get invitation", Einladung erhalten), um neue Raumeinladungen anzufordern, die der Client noch nicht gesehen hat. Der Server für beständigen Chat gibt in einer separaten SIP INFO-Nachricht eine Liste dieser Räume zurück.

## Abonnieren eines Raums und Veröffentlichen einer Nachricht

Die folgende Sequenz beschreibt ein typisches Szenario beim Abonnieren eines Raums und beim Veröffentlichen einer Nachricht.

1.  Benutzer1 klickt im Lync-Client auf **Chatroom betreten**, anschließend auf **Suche** und gibt einige Suchkriterien ein. Der Client sendet eine SIP INFO-Nachricht mit dem XCCOS-Befehl **chansrch** (Raumsuche) sowie den Suchkriterien. Der Server für beständigen Chat fragt die Back-End-Datenbank ab und antwortet mit einer neuen SIP INFO-Nachricht mit einer Liste verfügbarer Räume, die den Suchkriterien entsprechen.

2.  Benutzer1 wählt den Chatroom aus, den er betreten möchte, und klickt auf **Diesem Raum folgen**. Der Client sendet dem Server für beständigen Chat eine SIP INFO-Nachricht mit dem XCCOS-Befehl **join** und der Raum-ID des Chatrooms, den der Benutzer ausgewählt hat. Der Server für beständigen Chat antwortet mit einer SIP INFO-Nachricht mit den Bereitstellungsdaten.

3.  Der Lync-Client sendet dem Server für beständigen Chat eine SIP INFO-Nachricht mit dem XCCOS-Befehl **bccontext** ("backchat context", Backchat-Kontext). Der Server für beständigen Chat ruft den Chatverlauf ab und gibt ihn in einer separaten SIP INFO-Nachricht an den Client zurück. An diesem Punkt betritt der Benutzer den Chatroom und ist bereit zur Teilnahme.

4.  Benutzer1 gibt eine neue Nachricht ein und klickt anschließend auf **Senden**. Der Lync-Client veröffentlicht die Nachricht im Chatroom mit einem SIP INFO-XCCOS-Befehl **grpchat**. Der Server für beständigen Chat speichert eine Kopie dieser neuen Nachricht in der Beständiger Chat-Back-End-Datenbank.

5.  Der Server für beständigen Chat sendet eine separate Kopie der SIP INFO-XCCOS-Nachricht **grpchat** an Benutzer2, der den Chatroom bereits betreten hat.

## Beständiger Chat-Kompatibilitäts-Anrufflüsse

Der Server für beständigen Chat verwendet Message Queuing (auch als MSMQ bezeichnet) und eine zusätzliche Kompatibilitätsdatenbank (mgccomp) zur Verarbeitung von Kompatibilitätsdaten. Als Beispiel dafür, wie Kompatibilitätsereignisse verarbeitet werden, beschreibt die folgende Ereignissequenz, wie ein Ereignis "Veröffentlichen einer Nachricht" verarbeitet wird.

1.  Ein Benutzer schreibt eine Nachricht in einem Chatroom.

2.  Der Server für beständigen Chat platziert Informationen über das Ereignis in einer privaten Message Queuing-Warteschlange.

3.  Der Beständiger Chat-Kompatibilitätsserver liest das Ereignis in der Warteschlange und platziert es zur späteren Verarbeitung in der mgccomp-Datenbank.

4.  Der Beständiger Chat-Kompatibilitätsserver verarbeitet periodisch einen Satz von Ereignissen in der Datenbank und sendet sie zur Verarbeitung an den Beständiger Chat-Kompatibilitätsadapter.

5.  Wenn der Adapter die Daten erfolgreich verarbeitet hat, löscht der Beständiger Chat-Kompatibilitätsserver die Ereignisse aus der mgccomp-Datenbank.

