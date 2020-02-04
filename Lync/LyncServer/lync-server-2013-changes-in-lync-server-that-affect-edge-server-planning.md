---
title: 'Lync Server 2013: Änderungen in Lync Server, die die Planung für Edgeserver betreffen'
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
ms.openlocfilehash: 73eda15acbce7eb4b47a0a52602776e8fc830b0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Änderungen in Lync Server 2013, die die Planung für Edgeserver betreffen

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Lync Server 2013 führt neue Features ein, die die Features und Kommunikationsmethoden für Ihre Benutzer erweitern. Darüber hinaus führt lync Server 2013 Änderungen an vorhandenen Diensten durch, um die Dienste, die für Ihre Organisation verfügbar sind, besser zu integrieren und zu erweitern. Es folgt eine Zusammenfassung der Änderungen, die sich auf die Planung und Bereitstellung von lync Server 2013-Edgeserver-Diensten auswirken können.

<div>

## <a name="support-for-ipv6-addressing"></a>Unterstützung für IPv6-Adressierung

Lync Server 2013 unterstützt die IPv6-Adressierung für alle Edgeserver-Dienste. Wenn Sie IPv6-Adressen für die Schnittstellen über die Konfiguration in Windows Server bereitgestellt haben, können Sie IPv6-Adressen in ihrer Edge-Server-Konfiguration über die IP-Adressenkonfiguration im Topologie-Generator verwenden. Darüber hinaus unterstützt das Extensible Messaging and Presence Protocol (XMPP) IPv6. Es ist keine zusätzliche Konfiguration erforderlich. Wenn IPv6 in der Topologie konfiguriert ist, wird in XMPP IPv6 (sofern erforderlich) verwendet.

Eine zusätzliche Anforderung zur Unterstützung von IPv6 in lync Server 2013 ist das Erstellen von Domänennamen-Systemdaten Sätzen für Datensätze, die ermittelt und in eine IPv6-Adresse aufgelöst werden müssen. IPv6 DNS verwendet Hosteinträge, die als **AAAA** definiert sind und als "Quad-A" bezeichnet werden. Andere Datensatztypen sind mit Ihren IPv4-Pendants konsistent.

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>Unterstützung für die Bereitstellung von Extensible Messaging and Presence Protocol (XMPP)

Edgeserver führt einen vollständig integrierten XMPP-Proxy (auf den Edgeserver bereitgestellt) und ein XMPP-Gateway (bereitgestellt auf Ihren Front-End-Servern) ein. Sie können die XMPP-Föderation als optionale Komponente bereitstellen. Durch Hinzufügen und Konfigurieren des XMPP-Proxys und des XMPP-Gateways können Sie Ihren Microsoft lync 2013-Benutzern das Hinzufügen von Kontakten aus XMPP-basierten Partnern für Sofortnachrichten (im) und Anwesenheitsfunktionen ermöglichen.

<div>


> [!NOTE]  
> Derzeit bieten die XMPP-Dienste in Edgeserver nur Chatnachrichten und Anwesenheitsinformationen zwischen lync Server-Clients und XMPP-basierten Kontakten. Darüber hinaus wird XMPP nur an einer einzigen Website gehostet.



</div>

<div>


> [!IMPORTANT]  
> Die XMPP-Fähigkeit von Lync Server 2013 wird von Microsoft für den Instant-Messaging-Partnerverbund mit Google Talk getestet und unterstützt. Wenden Sie sich bei anderen XMPP-Systemen an den Drittanbieter, um zu überprüfen, ob dieser den Partnerverbund mit Lync Server 2013 unterstützt, und Empfehlungen bei Bereitstellung und Problembehandlung zu erhalten.



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>Unterstützung für die rollende Audio/Video-Authentifizierung und Server-zu-Server-Authentifizierungszertifikate

Ein Zertifikat wird verwendet, um Token zu generieren, die für Clients und andere Verbraucher des A/V-Authentifizierungsdiensts und für die Server-zu-Server-Authentifizierung ausgestellt werden. Das Audio/Video-Authentifizierungszertifikat ist vom Typ *AudioVideoAuthentication* und das Server-zu-Server-Authentifizierungszertifikat vom Typ *OAuthTokenIssuer*.

Bei der Audio-und Video Authentifizierung werden Token zur Authentifizierung von Port Zuordnungsanforderungen verwendet, und die Token werden bis zu 8 Stunden zwischengespeichert – die Standardlebensdauer des Tokens. Im Normalbetrieb ist dies eine sehr zuverlässige Methode zum Erstellen und Verteilen von Authentifizierungs Material an die a/V-Consumer. Zertifikate weisen jedoch eine begrenzte Lebensdauer auf und verfallen mit einem vordefinierten Datum und einer vordefinierten Uhrzeit (basierend auf dem Erstellungsdatum und den Richtlinien, die bei der Zertifizierungsstelle, die das Zertifikat erstellt hat, in der Regel 2 Jahre für diesen Zertifikattyp) erzwungen wurden. Wenn das Zertifikat abläuft, werden alle Token, die vom abgelaufenen Zertifikat erstellt und von Consumern zwischengespeichert wurden, ungültig. Alle Versuche, ein Token zu verwenden, das mit einem abgelaufenen Zertifikat erstellt wurde, können zu fehlgeschlagenen Medien Relay-Zuweisungen führen, und alle aktuellen Audio/Video-Sitzungen schlagen fehl. Der Client muss ein neues Token erwerben, das von einem gültigen Zertifikat erstellt wurde, um die normale Audio-und Video Funktionalität fortzusetzen.

Die Server-zu-Server-Authentifizierung wird von einem globalen Zertifikat verwaltet, das angefordert und auf alle Server in der Bereitstellung angewendet wird. Das Zertifikat ist für die Authentifizierung von Servern in lync Server 2013 sowie für die Authentifizierung bei Exchange 2013 und Microsoft SharePoint Server 2013 verantwortlich. Weitere Informationen zur Funktionsweise der Server-zu-Server-Authentifizierung finden Sie unter [Verwalten von Server-zu-Server-Authentifizierung (OAuth) und Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md). Ein sehr wichtiger Unterschied zwischen dem Authentifizierungsprozess für Audio/Video und dem Server-zu-Server-Authentifizierungsprozess ist die Lebensdauer der Authentifizierung oder Tokens. Bei der Audio/Video-Authentifizierung läuft die Authentifizierung nach acht Stunden ab. Die Server-zu-Server-Authentifizierung hat eine Lebensdauer von 24 Stunden. Sie müssen für jeden der Zertifikattypen entsprechend planen.

Neu bei lync Server 2013 ist die Möglichkeit, ein Ersatz-Audio/Video-Authentifizierungszertifikat und ein Server-zu-Server-Authentifizierungszertifikat im Vorfeld des Ablaufs des aktuellen Zertifikats zu inszenieren. Das neue Zertifikat wird dann zum Generieren neuer Token oder neuer Authentifizierungsanforderungen verwendet. das alte Zertifikat bleibt jedoch erhalten, um die aktuellen Sitzungen und Authentifizierungen zu überprüfen. Dadurch wird verhindert, dass nahezu alle Fehler aufgrund von Token-und Zertifikat ablaufen effektiv verhindert werden. Details zu diesem Feature und zur Konfiguration finden Sie unter Staging von [AV-und OAuth-Zertifikaten in lync Server 2013 using-Rolle in der Gruppe-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Geringere Abhängigkeit von der Cookie-basierten Affinität

In früheren Versionen von lync Server und Office Communications Server wurde die Cookie-basierte Affinität von den Webdiensten verwendet, um sicherzustellen, dass der Client-und Webdienste-Sitzungszustand beibehalten wurde. Lync Server 2013-Webdienste verwenden einen integrierten Affinitäts Mechanismus, der die meisten Anforderungen für die Cookie-basierte Affinität beseitigt.

<div>


> [!WARNING]  
> Der Mobile Microsoft lync 2010-Client muss weiterhin eine auf Cookies basierende Affinität verwenden und erfordert die Konfiguration von Cookie-basierter Affinität, bis Sie alle Clients auf den bevorstehenden Microsoft lync Mobile-Client migriert haben (das Datum der Veröffentlichung, das noch nicht festgelegt wurde).



</div>

Details zur Cookie-basierten Affinität in lync Server 2013 finden Sie unter [Komponenten, die für den Zugriff durch externe Benutzer in lync Server 2013 erforderlich](lync-server-2013-components-required-for-external-user-access.md)sind.

</div>

<div>

## <a name="autodiscover-enhancements"></a>Verbesserungen bei AutoErmittlung

Das Feature AutoErmittlung in lync Server 2013 ermöglicht es Clients, zusätzliche Features zu finden, die für die Kommunikation zur Verfügung gestellt werden. Die AutoErmittlung wurde erstmals im kumulativen Update für lync Server 2010: November 2011 für Mobilität und Microsoft lync 2010 Mobile eingeführt. Das Feature AutoErmittlung (auch bekannt durch die DNS-Eintragsnamen LyncDiscover und LyncDiscoverInternal) ermöglicht es Clients, Mobilitätsdienste (für Microsoft lync 2010 Mobile-Clients), die Microsoft lync Web App und den lync Web Scheduler zu finden und zu verwenden sowie Kommunikation mit Microsoft Exchange Server und SharePoint Server. AutoErmittlung wird als normaler Teil der Einrichtung und Bereitstellung Ihrer Infrastruktur und lync Server 2013-Server installiert. Der Topologie-Generator und der lync Server-Bereitstellungs-Assistent eliminieren die meisten Konfigurationsaufgaben, die im kumulativen Update für lync Server 2010: November 2011 erforderlich waren.

</div>

<div>

## <a name="services-for-mobile-clients"></a>Dienste für mobile Clients

In dem kumulativen Update für lync Server 2010: November 2011, Mobilitätsdienste in lync Server 2013, mit denen Mobiltelefone mit lync Mobile-und Tablet-Geräten mit unterstützten Apple IOS-, Android-, Windows Phone-oder Nokia-mobilen Geräten ausgeführt werden können Aktivitäten wie das Senden und empfangen von Sofortnachrichten, das Anzeigen von Kontakten und das Anzeigen von Anwesenheitsinformationen. Darüber hinaus unterstützen Mobile Geräte einige Enterprise-VoIP-Features, wie beispielsweise klicken, um an einer Konferenz teilzunehmen, über Arbeit zu anrufen, eine Rufnummer zu erreichen, Voicemail und Benachrichtigungen über verpasste Anrufe zu erhalten.

<div>


> [!NOTE]  
> Die Mobilitätsdienste verwenden den Reverse-Proxy und veröffentlichte Dienste, die auf Ihren Front-End-Servern bereitgestellt werden. Für Edgeserver sind keine Änderungen erforderlich. Minimal benötigen Sie ausgehende SIP/TCP/5061from auf dem Server, auf dem der lync Server Access Edge-Dienst ausgeführt wird.



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>Director-Rolle ist optional

Die Rolle des Director-Servers in der lync Server 2013-Topologie wurde nicht geändert. Sie hostet weiterhin Webdienste, authentifiziert eingehende Benutzeranforderungen und leitet externe Benutzer an deren Home-Pool weiter. Wenn der Director von einer empfohlenen Rolle in eine optionale Rolle geändert wird, beabsichtigt Microsoft nicht, den Wert des Directors zu schmälern. Das Ziel besteht darin, die Serveranzahl und andere Hardwareanforderungen (beispielsweise Hardwarelastenausgleichs für den Director) zu verringern, ohne die Features und Funktionen zu beeinträchtigen. Da die Front-End-Server dieselbe Aufgabe wie der Director ausführen können, ohne dass dies Auswirkungen auf die bereitgestellten Dienste hat, können Sie Directors bereitstellen, wenn Sie sich dafür entscheiden. Sie können den Director sicher ausschließen, dass der Front-End-Server die gleichen Dienste anstelle eines Directors bereitstellt.

</div>

</div>

<span> </span>

</div>

</div>

</div>

