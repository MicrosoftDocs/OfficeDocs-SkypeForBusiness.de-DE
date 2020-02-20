---
title: 'Lync Server 2013: Änderungen an lync Server, die sich auf die Edgeserver Planung auswirken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be2944125e5338dcc9b90b54f19fac003ec07287
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Änderungen in lync Server 2013, die sich auf die Edgeserver Planung auswirken

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-22_

In lync Server 2013 werden neue Features vorgestellt, die die Features und Kommunikationsmethoden für Ihre Benutzer erweitern. Darüber hinaus führt lync Server 2013 Änderungen an vorhandenen Diensten durch, um die für Ihre Organisation verfügbaren Dienste besser zu integrieren und zu erweitern. Im folgenden finden Sie eine Zusammenfassung der Änderungen, die sich auf die Planung und Bereitstellung von lync Server 2013 Edgeserver Diensten auswirken können.

<div>

## <a name="support-for-ipv6-addressing"></a>Unterstützung für IPv6-Adressierung

Lync Server 2013 unterstützt die IPv6-Adressierung für alle Edgeserver Dienste. Wenn Sie IPv6-Adressen für die Schnittstellen über die Konfiguration in Windows Server bereitgestellt haben, können Sie IPv6-Adressen in ihrer Edgeserver Konfiguration über die IP-Adresskonfiguration im Topologie-Generator verwenden. Außerdem wird IPv6 auch vom XMPP-Protokoll unterstützt. Zusätzliche Konfigurationsschritte sind nicht erforderlich. Wenn IPv6 in der Topologie konfiguriert ist, wird es (wo erforderlich) von XMPP genutzt.

Eine zusätzliche Anforderung zur Unterstützung von IPv6 in lync Server 2013 besteht darin, Domänennamen-Systemeinträge für Datensätze zu erstellen, die ermittelt und in eine IPv6-Adresse aufgelöst werden müssen. IPv6-DNS arbeitet mit Host-Einträgen, die als **AAAA** ("Quad-A") definiert werden. Andere Typen von Einträgen entsprechen ihren IPv4-Gegenstücken.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Unterstützung für XMPP-Bereitstellung (Extensible Messaging and Presence Protocol)

Edgeserver stellt einen vollständig integrierten XMPP-Proxy (auf den Edgeserver bereitgestellt) und ein XMPP-Gateway (bereitgestellt auf Ihren Front-End-Servern) vor. Sie können einen XMPP-Verbund als optionale Komponente bereitstellen. Indem Sie den XMPP-Proxy und das XMPP-Gateway hinzufügen und konfigurieren, können Sie Ihren Microsoft lync 2013 Benutzern das Hinzufügen von Kontakten aus XMPP-basierten Partnern für Chatnachrichten und Anwesenheit ermöglichen.

<div>


> [!NOTE]  
> Derzeit stellen die XMPP-Dienste in Edgeserver nur Chatnachrichten und Anwesenheitsinformationen zwischen lync Server-Clients und XMPP-basierten Kontakten bereit. Außerdem wird XMPP nur an einem einzigen Standort gehostet.



</div>

<div>


> [!IMPORTANT]  
> Die XMPP-Funktion von lync Server 2013 wird von Microsoft für den Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich für alle anderen XMPP-Systeme an den Drittanbieter, um zu überprüfen, ob der Partnerverbund mit lync Server 2013 und für alle Bereitstellungs-oder Problem Behandlungsempfehlungen unterstützt wird.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Unterstützung für parallele Audio-/Video-Authentifizierung und Server-zu-Server-Authentifizierungszertifikate

Ein Zertifikat wird zum Generieren von Token verwendet, die für Clients und andere Abnehmer des A/V-Authentifizierungsdiensts und für die Server-zu-Server-Kommunikation ausgestellt werden. Das Audio-/Video-Authentifizierungszertifikat hat den Typ *AudioVideoAuthentication*, und das Server-zu-Server-Authentifizierungszertifikat ist vom Typ *OAuthTokenIssuer*.

Bei der Audio-/Video-Authentifizierung dienen Token zum Authentifizieren von Portzuordnungsanforderungen, wobei die Token für bis zu acht Stunden zwischengespeichert werden (was die standardmäßige Lebensdauer des Token ist). Im normalen Betrieb ist das eine sehr zuverlässige Methode zum Erstellen und Weitergeben von Authentifizierungsmaterialien an die A/V-Abnehmer. Zertifikate haben jedoch eine begrenzte Lebenszeit und laufen zu einem vorab festgelegten Zeitpunkt ab (je nach dem Erstellungsdatum und den umgesetzten Richtlinien bei der CA, die das Zertifikat erstellt hat – bei Zertifikaten dieses Typs für gewöhnlich 2 Jahre). Bei Ablauf des Zertifikats werden alle damit erstellten und von Abnehmern zwischengespeicherten Token ungültig. Alle Versuche, ein Token zu verwenden, das mit einem abgelaufenen Zertifikat erstellt wurde, würden zu Fehlern bei Media-Relay-Zuordnungen und aktuellen Audio-/Videositzungen führen. Um den normalen Audio-/Videobetrieb wieder aufzunehmen, müsste der Client ein neues Token abrufen, das mit einem gültigen Zertifikat erstellt wurde.

Die Server-zu-Server-Authentifizierung erfolgt mithilfe eines globalen Zertifikats, das für alle Server in der Bereitstellung angefordert und übernommen wird. Das Zertifikat ist für die Authentifizierung von Servern in lync Server 2013 sowie für die Authentifizierung bei Exchange 2013 und Microsoft SharePoint Server 2013 verantwortlich. Weitere Informationen zur Funktionsweise der Server-zu-Server-Authentifizierung finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Ein sehr wichtiger Unterschied zwischen dem Audio-/Video-Authentifizierungsprozess und dem Server-zu-Server-Authentifizierungsprozess besteht in der Lebensdauer der Authentifizierung oder Token. Bei Audio-/Video-Authentifizierung läuft die Authentifizierung nach 8 Stunden ab. Die Server-zu-Server-Authentifizierung hat eine Lebensdauer von 24 Stunden. Das müssen Sie bei Ihren Planungen entsprechend berücksichtigen.

Neu für lync Server 2013 ist die Möglichkeit, ein Ersatz-Audio/Video-Authentifizierungszertifikat und ein Server-zu-Server-Authentifizierungszertifikat im Vorfeld des Ablaufs des aktuellen Zertifikats zu inszenieren. Das neue Zertifikat wird dann zum Generieren neuer Tokens oder neuer Authentifizierungsanforderungen verwendet. behält jedoch das alte Zertifikat für die Überprüfung der aktuellen Sitzungen und Authentifizierungen bei.. Dadurch werden nahezu alle Fehler aufgrund von Token-und Zertifikat Ablauf wirksam verhindert. Ausführliche Informationen zu diesem Feature und zu seiner Konfiguration finden Sie unter [Staging AV and OAuth certificates in lync Server 2013 using-Roll in CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Geringere Abhängigkeit von Cookie-basierter Affinität

In früheren Versionen von lync Server und Office Communications Server wurde die Cookie-basierte Affinität von den Webdiensten verwendet, um sicherzustellen, dass der Client-und Webdienst Sitzungszustand beibehalten wurde. Lync Server 2013-Webdienste verwenden einen integrierten Affinitäts Mechanismus, der die meisten Anforderungen an die Cookie-basierte Affinität eliminiert.

<div>


> [!WARNING]  
> Der Microsoft lync 2010 Mobile-Client muss weiterhin eine Cookie-basierte Affinität verwenden und eine Konfiguration der Cookie-basierten Affinität erfordern, bis Sie alle Clients zum bevorstehenden Microsoft lync Mobile-Client migriert haben (Veröffentlichungsdatum noch nicht festgelegt).



</div>

Ausführliche Informationen zur Cookie-basierten Affinität in lync Server 2013 finden Sie unter [für den Zugriff durch externe Benutzer in lync Server 2013 erforderliche Komponenten](lync-server-2013-components-required-for-external-user-access.md).

</div>

<div>

## <a name="autodiscover-enhancements"></a>Verbesserungen bei der AutoErmittlungs-Funktion

Das Auto Ermittlungs Feature in lync Server 2013 ermöglicht Clients das Auffinden zusätzlicher Features, die für die Kommunikation verfügbar gemacht werden. Die AutoErmittlung wurde erstmals im kumulativen Update für lync Server 2010: November 2011 für Mobilität und Microsoft lync 2010 Mobile eingeführt. Das Auto Ermittlungs Feature (auch bekannt durch die DNS-Eintragsnamen LyncDiscover und "lyncdiscoverinternal") ermöglicht Clients das Auffinden und Verwenden von Mobilitätsdiensten (für Microsoft lync 2010 Mobile Clients), die Microsoft lync Web App und den lync-Webplaner sowie Kommunikation mit Exchange Server und SharePoint Server. Die AutoErmittlung wird als normaler Teil des Setups und der Bereitstellung Ihrer Infrastruktur und lync Server 2013 Server installiert. Mit dem Topologie-Generator und dem lync Server-Bereitstellungs-Assistenten werden die meisten Konfigurationsaufgaben beseitigt, die im kumulativen Update für lync Server 2010 erforderlich waren: November 2011.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Dienste für mobile Clients

Im kumulativen Update für lync Server 2010: November 2011 wurden Mobilitätsdienste in lync Server 2013 für Mobiltelefone, auf denen lync Mobile und Tablet-Geräte mit unterstützten Apple IOS-, Android-, Windows Phone-oder Nokia-Mobilgeräten ausgeführt werden, für die Ausführung von Aktivitäten wie das Senden und empfangen von Chatnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsinformationen. Zudem unterstützen Mobilgeräte einige Enterprise-VoIP-Features, beispielsweise die Teilnahme an einer Besprechung durch Klicken, geschäftlich Anrufen, Erreichbarkeit unter einer Nummer, Voicemail und Anrufe in Abwesenheit.

<div>


> [!NOTE]  
> Die Mobilitätsdienste verwenden den Reverseproxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt sind. Änderungen an Edgeservern sind nicht erforderlich. Minimal benötigen Sie ausgehende SIP/TCP/5061from auf dem Server, auf dem die lync Server Zugriffs-Edgedienst läuft.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>Director-Rolle ist optional

Die Rolle des Director-Servers in der lync Server 2013-Topologie wurde nicht geändert. Er hostet weiterhin Webdienste, authentifiziert vorab eingehende Benutzeranfragen und leitet externe Benutzer zu deren Home-Pool. Wenn Sie den Director von einer empfohlenen Rolle in eine optionale Rolle ändern, beabsichtigt Microsoft nicht, den Wert des Directors zu verringern. Das Ziel besteht darin, die Anzahl von Servern und andere Hardwareanforderungen zu reduzieren (beispielsweise Hardwarelastenausgleich für den Director), ohne dass Features und Funktionen beeinträchtigt werden. Da die Front-End-Server dieselbe Aufgabe wie der Director ausführen können und keine Auswirkungen auf die bereitgestellten Dienste haben, können Sie Directors bereitstellen, wenn Sie sich für entscheiden. Sie können den Director sicher mit Sicherheit ausschließen, dass die Front-End-Server dieselben Dienste anstelle eines Directors bereitstellen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

