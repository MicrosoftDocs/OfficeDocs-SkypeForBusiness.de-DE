---
title: 'Lync Server 2013: Serverrollen'
TOCTitle: Serverrollen
ms:assetid: 7137fc06-fca2-4e5f-9db5-10c7c29a788c
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398536(v=OCS.15)
ms:contentKeyID: 49294366
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Serverrollen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2013-10-07_

Auf jedem Server mit Lync Server wird mindestens eine *Serverrolle* ausgeführt. Eine Serverrolle ist als Satz von Lync Server-Funktionen definiert, die von diesem Server bereitgestellt werden. Sie müssen nicht alle verfügbaren Serverrollen in Ihrem Netzwerk bereitstellen. Installieren Sie lediglich die Serverrollen, die erforderliche Funktionalität bereitstellen.

Auch wenn Sie nicht mit den Serverrollen in Lync Server vertraut sind, können Sie mithilfe des Planungstools die beste Lösung für die Server ermitteln, die Sie basierend auf Ihren Funktionsanforderungen bereitstellen sollten. Dieser Abschnitt bietet eine kurze Übersicht über die Serverrollen und die allgemeinen Funktionen, die diese bereitstellen:

  - Standard Edition-Server

  - Front-End-Server und Back-End-Server

  - Edgeserver

  - Vermittlungsserver

  - Director

  - Front-End-Server für beständigen Chat

  - Beständiger Chatspeicher (Back-End-Server für beständigen Chat)

  - Kompatibilitätsspeicher für beständigen Chat (Back-End-Server zur Kompatibilität für beständigen Chat)

Um Skalierbarkeit und hohe Verfügbarkeit zu bieten, können Sie für die meisten Serverrollen *Pools* mit mehreren Servern bereitstellen, auf denen dieselbe Serverrolle ausgeführt wird. Auf allen Servern innerhalb eines Pools muss dieselbe Serverrolle ausgeführt werden. Für einige Pooltypen in Lync Server ist ein Lastenausgleichssystem erforderlich, um den Datenverkehr auf die verschiedenen Server innerhalb des Pools zu verteilen. In Lync Server wird ein DNS-Lastenausgleich (Domain Name System) unterstützt, es können aber auch Hardwaregeräte zum Lastenausgleich verwendet werden.

## Standard Edition-Server

Der Standard Edition-Server eignet sich für kleine Organisationen und für Pilotprojekte großer Organisationen. Mit dieser Version können viele Funktionen von Lync Server (einschließlich der erforderlichen Datenbanken) auf einem einzelnen Server ausgeführt werden. So können Sie die Lync Server-Funktionen zu einem deutlich geringeren Preis nutzen, erhalten jedoch keine wirklich hoch verfügbare Lösung.

Mit dem Standard Edition-Server können Sie Chatnachrichten-, Anwesenheits-, Konferenz- und Enterprise-VoIP-Funktionen nutzen, die allesamt auf einem einzigen Server ausgeführt werden.

Wenn Sie eine hoch verfügbare Lösung möchten, verwenden Sie Lync Server Enterprise Edition.

## Front-End-Server und Back-End-Server

In Lync Server Enterprise Edition ist der Front-End-Server die wichtigste Serverrolle, über die eine Vielzahl von grundlegenden Lync Server-Funktionen ausgeführt wird. Der Front-End-Server und die Back-End-Server, welche die Datenbank bereitstellen, sind die einzigen Serverrollen, die in einer Lync Server Enterprise Edition-Bereitstellung benötigt werden.

Bei einem *Front-End-Pool* handelt es sich um einen Satz von Front-End-Servern mit identischer Konfiguration, die gemeinsam zur Bereitstellung von Diensten für eine gemeinsame Benutzergruppe eingesetzt werden. Ein Pool mit mehreren Servern, auf denen dieselbe Rolle ausgeführt wird, bietet Skalierbarkeit und Failoverfunktionen.

Der Front-End-Server bietet u. a. die folgenden Funktionen:

  - Benutzerauthentifizierung und -registrierung

  - Anwesenheitsinformationen und Visitenkartenaustausch

  - Adressbuchdienste und Verteilerlistenerweiterung

  - Chatnachrichtenfunktionalität, einschließlich Chatnachrichtenkonferenzen mit mehreren Teilnehmern

  - Webkonferenzen, PSTN-Einwahlkonferenzen und A/V-Konferenzen (sofern bereitgestellt)

  - Dienste zum Hosten von Anwendungen, sowohl für im Lieferumfang von Lync Server enthaltene Anwendungen (z. B. die Konferenzzentrale und die Reaktionsgruppenanwendung) als auch für Drittanbieteranwendungen

  - Optional eine Überwachungsfunktion, um Nutzungsinformationen in Form von Kommunikationsdatensätzen und Daten zu Anruffehlern zu erfassen. Diese Informationen liefern Metriken zur Qualität der Medien (Audio und Video), die Ihr Netzwerk für Enterprise-VoIP-Anrufe und A/V-Konferenzen durchlaufen.

  - Webkomponenten zu unterstützten webbasierten Aufgaben wie Webplaner und Join Launcher.

  - Optional eine Archivierung der Chatnachrichtenkommunikation und Besprechungsinhalte, um rechtliche Vorgaben einzuhalten. Ausführliche Informationen finden Sie unter [Planen der Archivierung in Lync Server 2013](lync-server-2013-planning-for-archiving.md) in der Planungsdokumentation.
    
    In Lync Server 2010 und früheren Versionen stellten Überwachung und Archivierung eigene Serverrollen dar, die nicht gemeinsam mit dem Front-End-Server ausgeführt wurden.

  - Optional, sofern der beständige Chat aktiviert ist, Webdienste für den beständigen Chat für die Chatroom-Verwaltung und Webdienste für den beständigen Chat für das Hochladen/Herunterladen von Dateien.

Front-End-Pools bilden außerdem den primären Speicher für Benutzer- und Konferenzdaten. Die Informationen zu den einzelnen Benutzern werden auf drei Front-End-Servern im Pool repliziert und auf den Back-End-Servern gesichert.

Zusätzlich wird in einem Front-End-Pool in der Bereitstellung der *zentrale Verwaltungsserver* ausgeführt, über den grundlegende Konfigurationsdaten für alle Server mit Lync Server verwaltet und bereitgestellt werden. Über den zentraler Verwaltungsserver werden zudem die Lync Server-Verwaltungsshell und Dateiübertragungsfunktionen bereitgestellt.

Bei den Back-End-Servern handelt es sich um Datenbankserver mit Microsoft SQL Server, welche die Datenbankdienste für den Front-End-Pool bereitstellen. Die Back-End-Server werden als Sicherungsspeicher für die Benutzer- und Konferenzdaten des Pools verwendet. Außerdem bilden sie die primären Speicher für andere Datenbanken, z. B. für die Reaktionsgruppendatenbank. Sie können einen einzelnen Back-End-Server bereitstellen. Für ein Failover wird jedoch eine Lösung mit einer SQL Server-Spiegelung empfohlen. Auf Back-End-Servern wird keine Lync Server-Software ausgeführt.


> [!IMPORTANT]
> Es wird nicht empfohlen, eine Lync Server-Datenbank gemeinsam mit anderen Datenbanken auszuführen. Andernfalls können Verfügbarkeit und Leistung beeinträchtigt werden.



Die in den Datenbanken auf einem Back-End-Server gespeicherten Daten umfassen Anwesenheitsinformationen, die Kontaktlisten der Benutzer, Konferenzdaten (einschließlich dauerhafter Daten zum Zustand aller aktuellen Konferenzen) sowie Konferenzplanungsdaten.

## Edgeserver

Edgeserver ermöglichen es Benutzern, mit Benutzern außerhalb der Firewall einer Organisation zu kommunizieren und zusammenarbeiten. Diese externen Benutzer können Benutzer Ihrer Organisation umfassen, die gegenwärtig standortextern arbeiten, Benutzer aus Organisationen von Verbundpartnern sowie externe Benutzer, die zur Teilnahme an Konferenzen eingeladen wurden, die in Ihrer Lync Server-Bereitstellung gehostet werden. Edgeserver ermöglichen zudem Verbindungen mit öffentlichen Instant Messaging-Diensten, u. a. Windows Live, AOL, Yahoo\! und Google Talk.


> [!IMPORTANT]
> <UL>
> <LI>
> <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Chatdiensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P>
> <LI>
> <P>Bei PIC&nbsp;USL handelt es sich um eine Abonnementlizenz pro Benutzer und pro Monat, die für Lync&nbsp;Server oder Office&nbsp;Communications&nbsp;Server zum Einrichten eines Partnerverbunds mit Yahoo! Messenger erforderlich ist. Die Bereitstellung dieses Services durch Microsoft hing von der Unterstützung durch Yahoo! ab, deren zugrundeliegende Vereinbarung ausläuft.</P>
> <LI>
> <P>Lync ist mehr denn je ein leistungsstarkes Tool das Organisationen und Einzelpersonen weltweit verbindet. Der Partnerverbund mit Windows Live Messenger erfordert keine zusätzlichen Benutzer-/Gerätelizenzen außer der Lync Standard CAL. Der Partnerverbund mit Skype wird dieser Liste hinzugefügt und ermöglicht Lync-Benutzern, Abermillionen von Personen per Chat oder VoIP zu erreichen.</P></LI></UL>



Bei der Bereitstellung des Edgeservers werden außerdem die Mobilitätsdienste aktiviert, mit denen die Lync-Funktionalität auf mobilen Geräten unterstützt wird. Benutzer können mit unterstützten mobilen Geräten (Apple iOS, Android, Windows Phone oder Nokia) Aktionen ausführen wie Senden und Empfangen von Chatnachrichten, Anzeigen von Kontakten und Anzeigen der Anwesenheit. Zudem unterstützen mobile Geräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, geschäftliche Anrufe, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit. Das Mobilitätsfeature unterstützt auch *Pushbenachrichtigungen* für mobile Geräte, die das Ausführen von Anwendungen im Hintergrund nicht unterstützen. Eine Pushbenachrichtigung ist eine an ein mobiles Gerät gesendete Benachrichtigung über ein Ereignis, das auftritt, wenn eine mobile Anwendung inaktiv ist.

Die Edgeserver umfassen außerdem einen vollständig integrierten XMPP-Proxy (Extensible Messaging and Presence Protocol), wobei das XMPP-Gateway auf den Front-End-Servern integriert ist. Sie können diese XMPP-Komponenten konfigurieren, damit Ihre Lync Server 2013-Benutzer Kontakte von XMPP-basierten Partnern (z. B. Google Talk) für Chatnachrichten und Anwesenheitsinformationen hinzufügen können.

Ausführliche Informationen finden Sie unter [Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) in der Planungsdokumentation.

## Vermittlungsserver

Der Vermittlungsserver ist eine erforderliche Komponente für die Implementierung von Enterprise-VoIP und Einwahlkonferenzen. Der Vermittlungsserver übersetzt Signale und - in einigen Konfigurationen - Medien zwischen Ihrer internen Lync Server-Infrastruktur und einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SIP-Trunk (Session Initiation Protocol). Sie können den Vermittlungsserver gemeinsam mit dem Front-End-Sever auf demselben Server oder getrennt in einem eigenständigen Vermittlungsserverpool ausführen.

Ausführliche Informationen finden Sie unter [Vermittlungsserverkomponente in Lync Server 2013](lync-server-2013-mediation-server-component.md) in der Planungsdokumentation.

## Director

Directors können zur Authentifizierung von Lync Server-Benutzeranforderungen eingesetzt werden, verwalten jedoch keine Benutzerkonten und stellen keine Anwesenheits- oder Konferenzdienste bereit. Directors sind zur Verbesserung der Sicherheit insbesondere in Bereitstellungen nützlich, in denen der Zugriff durch externe Benutzer aktiviert ist. Der Director kann Anforderungen authentifizieren, bevor sie an interne Server weitergeleitet werden. Bei Denial-of-Service-Angriffen enden die Angriffe beim Director und erreichen nicht die Front-End-Server. Ausführliche Informationen finden Sie unter [Szenarien für den Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in der Planungsdokumentation.

## Server für beständigen Chat-Rollen

Durch den beständigen Chat können Benutzer an themenbasierten Unterhaltungen mit mehreren Teilnehmern teilnehmen, die langfristig erhalten bleiben. Auf dem Front-End-Server für beständigen Chat wird der beständige Chatdienst ausgeführt. Auf dem Back-End-Server für beständigen Chat werden die Chatverlaufsdaten sowie Informationen zu Kategorien und Chatrooms gespeichert. Auf dem optionalen Back-End-Server zur Kompatibilität für den beständigen Chat können Chatinhalte sowie Kompatibilitätsereignisse zum Zweck der Einhaltung von Bestimmungen gespeichert werden.

Auf Servern, auf denen Lync ServerStandard Edition ausgeführt wird, kann der beständige Chat auf demselben Server gemeinsam ausgeführt werden. Sie können jedoch den Front-End-Server für beständigen Chat nicht gemeinsam mit Enterprise EditionFront-End-Server ausführen.

Ausführliche Informationen finden Sie unter [Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).

## Siehe auch

#### Konzepte

[Vermittlungsserverkomponente in Lync Server 2013](lync-server-2013-mediation-server-component.md)  

#### Weitere Ressourcen

[Planen der Archivierung in Lync Server 2013](lync-server-2013-planning-for-archiving.md)  
[Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Szenarien für den Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md)  
[Planen für den Server für beständigen Chat in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md)

