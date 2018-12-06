---
title: 'Lync Server 2013: Neue Funktionen für den externen Benutzerzugriff'
TOCTitle: Neue Funktionen für den externen Benutzerzugriff
ms:assetid: 99da6bd5-ec14-4ad9-8f7d-37fbddf567dd
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398794(v=OCS.15)
ms:contentKeyID: 49294859
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Neue Funktionen für den externen Benutzerzugriff in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-17_

Lync Server 2013 führt neue Funktionen ein, die die Möglichkeiten und Kommunikationsverfahren für die Benutzer erweitern. Außerdem führt Lync Server 2013 Änderungen vorhandener Dienste ein, wodurch die für Ihre Organisation verfügbaren Dienste besser integriert und erweitert werden. Im Folgenden finden Sie eine Übersicht der Änderungen, die Ihre Planung und Bereitstellung von Lync Server 2013  Edgeserverdiensten möglicherweise beeinflussen.

  - **Unterstützung der IPv6-Adressierung**     Lync Server 2013 unterstützt die IPv6-Adressierung für alle Edgeserverdienste. Wenn Sie für die Schnittstellen über die Konfiguration in Windows Server IPv6-Adressen angegeben haben, können Sie in Ihrer Edgeserver-Konfiguration über die IP-Adresskonfiguration im Topologie-Generator IPv6-Adressen verwenden.
    

    > [!IMPORTANT]
    > Die Verwendung von IPv6-Adressen in Lync Server 2013 hängt von der IPv6-Unterstützung von Routern und Firewalls ab, die Ihre Organisation bereitstellt, sowie von der Unterstützung durch Ihren Internetdienstanbieter.



  - **Extensible Messaging and Presence Protocol (XMPP)**     Lync Server 2013 führt einen vollintegrierten XMPP-Proxy (auf den Edgeservern bereitgestellt) und ein XMPP-Gateway ein, das auf Ihren Front-End-Servern bereitgestellt wird. Sie können einen XMPP-Verbund als optionale Komponente bereitstellen. Das Hinzufügen und Konfigurieren des XMPP-Proxys und des XMPP-Gateways ermöglicht Ihren Microsoft Lync 2013-Benutzern das Hinzufügen von Kontakten von XMPP-basierten Partnern für Chat und Anwesenheit.
    

    > [!NOTE]
    > Die XMPP-Dienste in Lync Server 2013 bieten zurzeit nur Sofortnachrichten und Anwesenheit zwischen Lync-Clients und XMPP-basierten Kontakten.



  - **Mobilitätsdienste für mobile Clients**    Die in einem Kundenupdate für Lync Server 2010 eingeführten Mobilitätsdienste in Lync Server 2013 ermöglichen Microsoft Lync Mobile-Clients auf Mobiltelefonen und Tablets bei Verwendung unterstützter Mobilgeräte (Apple iOS, Android, Windows Phone oder Nokia) Aktivitäten wie das Senden und Empfangen von Sofortnachrichten, das Anzeigen von Kontakten und der Anwesenheit. Zudem unterstützen Mobilgeräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, geschäftlich Anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit.
    

    > [!NOTE]
    > Die Mobilitätsdienste nutzen den Reverseproxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt sind. Auf den Edgeservern sind keine Änderungen erforderlich.



  - **Directors sind eine optionale Rolle**    Die Rolle des Director-Servers in der Lync Server 2013-Topologie hat sich nicht geändert. Er hostet weiterhin Webdienste, führt eine Vorabauthentifizierung eingehender Benutzeranfragen durch und leitet externe Benutzer an ihren Pool weiter. Die Änderung des Directors von einer empfohlenen Rolle in eine optionale Rolle verringert den Wert des Directors nicht, senkt aber die Serveranzahl und andere Hardwareanforderungen (z. B. Hardwaregeräte zum Lastenausgleich für den Director), ohne sich auf die Funktionen und die Funktionalität auszuwirken. Da die Front-End-Server denselben Auftrag verwenden können wie der Director, ohne dass sich dies auf die bereitgestellten Dienste auswirkt, können Sie Directors optional bereitstellen. Sie können den Director ausschließen und sicher sein, dass die Front-End-Server an dessen Stelle dieselben Dienste bieten.

## Siehe auch

#### Konzepte

[Planen und Konfigurieren von IPv6 in Lync Server 2013](lync-server-2013-planning-for-and-configuring-ipv6.md)  

#### Weitere Ressourcen

[Planen des Zugriffs externer Benutzer in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md)  
[Planen eines XMPP-Partnerverbunds (Extensible Messaging and Presence Protocol) in Lync Server 2013](lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md)

