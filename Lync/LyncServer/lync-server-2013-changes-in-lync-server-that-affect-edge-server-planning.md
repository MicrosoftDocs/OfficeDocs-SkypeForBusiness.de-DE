---
title: 'Lync Server 2013: Änderungen in Lync Server, die die Planung für Edgeserver betreffen'
TOCTitle: Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204965(v=OCS.15)
ms:contentKeyID: 49294238
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Lync Server 2013 führt neue Funktionen ein, die die Möglichkeiten und Kommunikationsverfahren für die Benutzer erweitern. Außerdem führt Lync Server 2013 Änderungen vorhandener Dienste ein, wodurch die für Ihre Organisation verfügbaren Dienste besser integriert und erweitert werden. Im Folgenden finden Sie eine Übersicht der Änderungen, die Ihre Planung und Bereitstellung von Lync Server 2013  Edgeserverdiensten möglicherweise beeinflussen.

## Unterstützung für IPv6-Adressierung

Lync Server 2013 unterstützt IPv6-Adressierung bei allen Edgeserver-Diensten. Wenn Sie den Schnittstellen per Konfiguration in Windows Server IPv6-Adressierung verfügbar gemacht haben, können Sie in Ihrer Edgeserver-Konfiguration IPv6-Adressen über die IP-Adresskonfiguration im Topologie-Generator nutzen. Außerdem wird IPv6 auch vom XMPP-Protokoll unterstützt. Zusätzliche Konfigurationsschritte sind nicht erforderlich. Wenn IPv6 in der Topologie konfiguriert ist, wird es (wo erforderlich) von XMPP genutzt.

Bei der IPv6-Unterstützung in Lync Server 2013 ist es jedoch erforderlich, für Einträge, die gesucht und in eine IPv6-Adresse aufgelöst werden müssen, DNS-Einträge zu erstellen. IPv6-DNS arbeitet mit Host-Einträgen, die als **AAAA** ("Quad-A") definiert werden. Andere Typen von Einträgen entsprechen ihren IPv4-Gegenstücken.

## Unterstützung für XMPP-Bereitstellung (Extensible Messaging and Presence Protocol)

Neu in Edgeserver sind ein vollständig integrierter XMPP-Proxy (der auf den Edgeservern bereitgestellt wird) und ein XMPP-Gateway (das auf Ihren Front-End-Servern bereitgestellt wird). Als optionale Komponenten können Sie XMPP-Verbund bereitstellen. Durch Hinzufügen und Konfigurieren des XMPP-Proxys und XMPP-Gateways können Sie es Ihren Microsoft Lync 2013-Benutzern ermöglichen, Kontakte von XMPP-basierten Partnern für Sofortnachrichten- und Anwesenheitsfunktionen hinzuzufügen.


> [!NOTE]
> Zum gegenwärtigen Zeitpunkt bieten die XMPP-Dienste im Edgeserver nur Sofortnachrichten- und Anwesenheitsfunktionalität zwischen Lync&nbsp;Server-Clients und XMPP-basierten Kontakten. Außerdem wird XMPP nur an einem einzigen Standort gehostet.




> [!IMPORTANT]
> Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.



## Unterstützung für parallele Audio-/Video-Authentifizierung und Server-zu-Server-Authentifizierungszertifikate

Ein Zertifikat wird zum Generieren von Token verwendet, die für Clients und andere Abnehmer des A/V-Authentifizierungsdiensts und für die Server-zu-Server-Kommunikation ausgestellt werden. Das Audio-/Video-Authentifizierungszertifikat hat den Typ *AudioVideoAuthentication* , und das Server-zu-Server-Authentifizierungszertifikat ist vom Typ *OAuthTokenIssuer* .

Bei der Audio-/Video-Authentifizierung dienen Token zum Authentifizieren von Portzuordnungsanforderungen, wobei die Token für bis zu acht Stunden zwischengespeichert werden (was die standardmäßige Lebensdauer des Token ist). Im normalen Betrieb ist das eine sehr zuverlässige Methode zum Erstellen und Weitergeben von Authentifizierungsmaterialien an die A/V-Abnehmer. Zertifikate haben jedoch eine begrenzte Lebenszeit und laufen zu einem vorab festgelegten Zeitpunkt ab (je nach dem Erstellungsdatum und den umgesetzten Richtlinien bei der CA, die das Zertifikat erstellt hat - bei Zertifikaten dieses Typs für gewöhnlich 2 Jahre). Bei Ablauf des Zertifikats werden alle damit erstellten und von Abnehmern zwischengespeicherten Token ungültig. Alle Versuche, ein Token zu verwenden, das mit einem abgelaufenen Zertifikat erstellt wurde, würden zu Fehlern bei Media-Relay-Zuordnungen und aktuellen Audio-/Videositzungen führen. Um den normalen Audio-/Videobetrieb wieder aufzunehmen, müsste der Client ein neues Token abrufen, das mit einem gültigen Zertifikat erstellt wurde.

Die Server-zu-Server-Authentifizierung erfolgt mithilfe eines globalen Zertifikats, das für alle Server in der Bereitstellung angefordert und übernommen wird. Das Zertifikat dient zum Authentifizieren von Servern in Lync Server 2013 sowie zur Authentifizierung in Exchange 2013 und Microsoft SharePoint Server 2013. Weitere Informationen zur Funktionsweise von Server-zu-Server-Authentifizierung finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Ein sehr wichtiger Unterschied zwischen dem Audio-/Video-Authentifizierungsprozess und dem Server-zu-Server-Authentifizierungsprozess besteht in der Lebensdauer der Authentifizierung oder Token. Bei Audio-/Video-Authentifizierung läuft die Authentifizierung nach 8 Stunden ab. Die Server-zu-Server-Authentifizierung hat eine Lebensdauer von 24 Stunden. Das müssen Sie bei Ihren Planungen entsprechend berücksichtigen.

Neu in Lync Server 2013 ist die Möglichkeit, vor Ablauf des aktuellen Zertifikats ein Ersatzzertifikat vorzuhalten. Das neue Zertifikat kann dann zum Generieren neuer Token oder neuer Authentifizierungsanforderungen verwendet werden, während das alte Zertifikat aufbewahrt wird, um die aktuellen Sitzungen und Authentifizierungen zu verifizieren. Auf diese Weise werden fast alle durch abgelaufene Token oder Zertifikate verursachte Fehler verhindert. Ausführliche Informationen zu dieser Funktion und zur Vorgehensweise bei der Konfiguration finden Sie unter [Bereitstellen von AV- und OAuth-Zertifikaten in Lync Server 2013 mithilfe von -Roll in Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate).

## Geringere Abhängigkeit von Cookie-basierter Affinität

In vorherigen Versionen von Lync Server und Office Communications Server wurde Cookie-basierte Affinität von den Webdiensten genutzt, um sicherzustellen, dass der Sitzungsstatus von Client- und Webdiensten aufrechterhalten bleibt. Lync Server 2013-Webdienste setzen einen integrierten Affinitätsmechanismus ein, der die meisten Anforderungen in Bezug auf Cookie-basierter Affinität beseitigt.


> [!WARNING]
> Auf dem Microsoft Lync 2010 Mobile-Client muss jedoch weiterhin Cookie-basierte Affinität verwendet und konfiguriert werden, bis Sie alle Clients auf den kommenden Microsoft Lync Mobile-Client aktualisiert haben (Datum der Veröffentlichung steht noch nicht fest).



Nähere Informationen über Cookie-basierte Affinität in Lync Server 2013 finden Sie unter [Erforderliche Komponenten für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).

## Verbesserungen bei der AutoErmittlungs-Funktion

Die AutoErmittlungs-Funktion in Lync Server 2013 ermöglicht es Clients, zusätzliche Funktionen aufzufinden, die für Kommunikationszwecke verfügbar gemacht wurden sind. Die AutoErmittlung wurde im kumulativen Update für Lync Server 2010: November 2011 for Mobility und Microsoft Lync 2010 Mobile eingeführt. Diese auch unter den DNS-Eintragsnamen "LyncDiscover" und "LyncDiscoverInternal" bezeichnete Funktion ermöglicht es Clients, Mobilitätsdienste (bei Microsoft Lync 2010 Mobile-Clients), die Microsoft Lync Web App und den Lync-Webplaner sowie Kommunikationsvorgänge mit Microsoft Exchange Server und SharePoint Server aufzufinden und zu nutzen. Die AutoErmittlung wird im Rahmen der Einrichtung und Bereitstellung Ihrer Infrastruktur und Ihrer Lync Server 2013-Server installiert. Das Topologie-Generator und das Lync Server-Bereitstellungs-Assistent machen die meisten Konfigurationsaufgaben, die im kumulativen Update für Lync Server 2010: November 2011 erforderlich waren, überflüssig.

## Dienste für mobile Clients

Die im kumulativen Update für Lync Server 2010: November 2011 eingeführten Mobilitätsdienste in Lync Server 2013 machen auf Mobiltelefonen mit Lync Mobile und Tablets mit einem unterstützten Betriebssystem (Apple iOS, Android, Windows Phone) sowie Mobilgeräten von Nokia das Durchführen bestimmter Aktivitäten möglich, wie das Senden und Empfangen von Sofortnachrichten, das Anzeigen von Kontakten und von Anwesenheit. Außerdem werden von mobilen Geräten einige Enterprise-VoIP-Features unterstützt, wie zum Beispiel die Teilnahme an einer Konferenz per Mausklick, Anruf über Arbeitsplatz, Erreichbarkeit unter einer einzigen Nummer, Voicemail und Benachrichtigung zu entgangenen Anrufen.


> [!NOTE]
> Die Mobilitätsdienste verwenden den Reverseproxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt sind. Änderungen an Edgeservern sind nicht erforderlich. Sie benötigen wenigstens ausgehendes SIP/TCP/5061 von dem Server, auf dem der Lync Server-Zugriffs-Edgedienst ausgeführt wird.



## Director-Rolle ist optional

Die Rolle des Director-Servers in der Lync Server 2013-Topologie hat sich nicht geändert. Er hostet weiterhin Webdienste, authentifiziert vorab eingehende Benutzeranfragen und leitet externe Benutzer zu deren Home-Pool. Mit der Verlegung des Directors von einer empfohlenen zu einer optionalen Rolle möchte Microsoft nicht den Wert des Director herabsetzen. Dadurch sollen nur die Serveranzahl und andere Hardwareanforderungen (z. B. Hardwaregeräte zum Lastenausgleich für die Director) gesenkt werden, ohne dass es bei Features und Funktionen zu Einschränkungen kommt. Da die Front-End-Server ohne Abstriche bei den angebotenen Diensten die gleiche Arbeit wie der Director leisten, können Sie Directors nach eigenem Belieben bereitstellen. Auch wenn Sie auf den Director verzichten, werden Front-End-Server die gleichen Dienste wie ein Director leisten.

