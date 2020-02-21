---
title: 'Lync Server 2013: DNS-Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS load balancing
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398634(v=OCS.15)
ms:contentKeyID: 48184625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47469a8b47273c077a96196b06b827ac13a0e336
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>DNS-Lastenausgleich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-01-15_

Lync Server aktiviert den DNS-Lastenausgleich, eine Softwarelösung, die den Verwaltungsaufwand für den Lastenausgleich in Ihrem Netzwerk erheblich reduzieren kann. Der DNS-Lastenausgleich balanciert den für lync Server eindeutigen Netzwerkdatenverkehr aus, beispielsweise SIP-Datenverkehr und Mediendatenverkehr.

Wenn Sie den DNS-Lastenausgleich bereitstellen, wird der Verwaltungsaufwand Ihrer Organisation für Hardwarelastenausgleich minimiert. Darüber hinaus entfällt die komplexe Problembehandlung zur Beseitigung von Fehlern, die durch eine falsche Konfiguration des Lastenausgleichs für SIP-Datenverkehr entstehen. Zudem können Sie Serververbindungen verhindern, sodass Sie Server offline schalten können. Der DNS-Lastenausgleich stellt ferner sicher, dass sich durch Hardwarelastenausgleich hervorgerufene Probleme nicht auf den SIP-Datenverkehr auswirken, etwa auf die grundlegende Anrufweiterleitung.

Wenn Sie DNS-Lastenausgleich verwenden, können Sie möglicherweise auch kostengünstigere Hardwaregeräte zum Lastenausgleich anschaffen, da diese nicht für alle Arten von Datenverkehr eingesetzt werden müssen. Sie sollten Lastenausgleichsmodule verwenden, die Interoperabilitäts Qualifizierungstests mit lync Server bestanden haben. Ausführliche Informationen zum Testen der Lastenausgleichsmodul-Interoperabilität finden Sie unter "lync Server 2010 Lasten [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452)Ausgleichs Partner" unter.

Der DNS-Lastenausgleich wird für Front-End-Pools, Edgeserverpools, Director-Pools und eigenständige Vermittlungsserverpools unterstützt.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>DNS-Lastenausgleich in Front-End-Pools und Director-Pools

Sie können den DNS-Lastenausgleich für den SIP-Datenverkehr in Front-End-Pools und Director-Pools verwenden. Auch wenn Sie einen DNS-Lastenausgleich konfiguriert haben, müssen Sie dennoch auch Hardwaregeräte zum Lastenausgleich für diese Pools verwenden, jedoch nur für den HTTPS-Datenverkehr von Client zu Server. Das Hardwaregerät zum Lastenausgleich wird für HTTPS-Datenverkehr von Clients über die Ports 443 und 80 verwendet.

Auch wenn für diese Pools weiterhin Hardwaregeräte zum Lastenausgleich benötigt werden, müssen diese vornehmlich für den HTTPS-Datenverkehr eingerichtet und verwaltet werden. Dies stellt für Administratoren von Hardwaregeräten zum Lastenausgleich jedoch eine gängige Aufgabe dar.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS-Lastenausgleich und Unterstützung älterer Clients und Server

Der DNS-Lastenausgleich unterstützt das automatische Failover nur für Server, auf denen lync Server 2013 oder lync Server 2010 sowie für lync 2013-und lync 2010-Clients verwendet wird. Frühere Versionen von Clients und Office Communications Server können weiterhin mit Pools mit dem DNS-Lastenausgleich verbunden werden, wenn Sie jedoch keine Verbindung mit dem ersten Server herstellen können, auf den der DNS-Lastenausgleich verweist, kann kein Failover auf einen anderen Server im Pool ausgeführt werden. .

Wenn Sie Exchange um verwenden, müssen Sie darüber hinaus mindestens Exchange 2010 SP1 verwenden, um Unterstützung für lync Server DNS-Lastenausgleich zu erhalten. Wenn Sie eine frühere Version von Exchange verwenden, verfügen die Benutzer nicht über Failoverfunktionen für diese Exchange um Szenarien:

  - Wiedergeben von Enterprise-VoIP-Voicemail über ein Telefon

  - Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale

Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools

Für die Bereitstellung von DNS-Lastenausgleich in Front-End-Pools und Director-Pools müssen einige zusätzliche Schritte im Zusammenhang mit FQDNs und DNS-Einträgen ausgeführt werden.

  - Ein Pool, der DNS-Lastenausgleich verwendet, muss über zwei FQDNs verfügen: den regulären Pool-FQDN (beispielsweise pool01.contoso.com), der vom DNS-Lastenausgleich verwendet und in die physischen IP-Adressen der Server im Pool aufgelöst wird, und einen weiteren FQDN für die Webdienste des Pools (z. B. web01.contoso.com), der in die virtuelle IP-Adresse des Pools aufgelöst wird.
    
    Wenn Sie im Topologie-Generator den DNS-Lastenausgleich für einen Pool bereitstellen möchten, müssen Sie zum Erstellen dieses zusätzlichen FQDN für die Webdienste des Pools das Kontrollkästchen **internen Webdienste Pool-FQDN außer Kraft setzen** aktivieren und in der Seite **Webdienste-URLs für diesen Pool angeben** den FQDN eingeben.

  - Um den vom DNS-Lastenausgleich verwendeten FQDN zu unterstützen, müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. pool01.contoso.com) in die IP-Adressen aller Server im Pool bereitstellen (z. B. 192.168.1.1, 192.168.1.2 usw.). Schließen Sie nur die IP-Adressen von Servern ein, die gegenwärtig bereitgestellt sind.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie mehr als eine Front-End-Pool oder Front-End-Server der FQDN der externen Webdienste eindeutig sein muss. Wenn Sie beispielsweise den externen Webdienste-FQDN eines Front-End-Server als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für eine andere Front-End-Pool oder Front-End-Server verwenden. Wenn Sie auch Directors bereitstellen, muss der FQDN für externe Webdienste, der für einen Director-oder Directorpool definiert ist, von einem anderen Director oder Directorpool sowie von Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>DNS-Lastenausgleich in Edgeserverpools

Sie können den DNS-Lastenausgleich in Edgeserverpools bereitstellen. In diesem Fall müssen einige Faktoren berücksichtigt werden.

Bei Verwendung des DNS-Lastenausgleichs auf Ihren Edgeservern verfügen Sie in den folgenden Szenarien nicht länger über eine Failoverfunktion:

  - Partnerverbund mit Organisationen, die Versionen von Office Communications Server, die vor lync Server 2010 veröffentlicht wurden, ausführt.

  - Instant Message Exchange mit Benutzern von öffentlichen Instant Messaging-Diensten (im) AOLand\!Yahoo, zusätzlich zu XMPP-basierten Anbietern und Servern wie Google Talk.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google Talk ist derzeit der einzige unterstützte XMPP-Partner.</P>
    > <LI>
    > <P>Seit dem 1. September 2012 ist die Microsoft lync Public Chat Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für neue oder erneuerte Verträge verfügbar. Kunden mit aktiven Lizenzen können weiterhin mit Yahoo! zusammenarbeiten. Messenger, bis der Dienst das Datum heruntergefahren hat. Ein End-of-Life-Datum vom Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for Public Instant Messenger Connectivity in lync Server 2013</A>.</P></LI></UL>

    
    </div>

Diese Szenarien werden unterstützt, solange alle Edgeserver im Pool verfügbar sind und ausgeführt werden. Wenn jedoch einer der Edgeserver ausfällt, werden Anforderungen für diese Szenarien nicht an einen anderen Edgeserver weitergeleitet, sondern können nicht verarbeitet werden.

Wenn Sie Exchange um verwenden, müssen Sie mindestens Exchange 2013 verwenden, um Unterstützung für lync Server DNS-Lastenausgleich auf Edge zu erhalten. Wenn Sie eine frühere Version von Exchange verwenden, verfügen die Remotebenutzer nicht über Failoverfunktionen für diese Exchange um Szenarien:

  - Wiedergeben von Enterprise-VoIP-Voicemail über ein Telefon

  - Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale

Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.

Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Bereitstellen von DNS-Lastenausgleich in Edgeserverpools

Zur Bereitstellung des DNS-Lastenausgleichs für die externe Schnittstelle Ihres Edgeserverpools benötigen Sie die folgenden DNS-Einträge:

  - Für den Zugriffs-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Zugriffs-Edgediensts (beispielsweise SIP.contoso.com) in die IP-Adresse des Zugriffs-Edgedienst auf einem der Edgeserver im Pool auflösen.

  - Für den Webkonferenz-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Webkonferenz-Edgediensts (beispielsweise webconf.contoso.com) in die IP-Adresse des Webkonferenz-Edgedienst auf einem der Edgeserver im Pool auflösen.

  - Für den Audio/Video-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Audio/Video-Edgedienst (beispielsweise AV.contoso.com) in die IP-Adresse des A/V-Edgedienst auf einem der Edgeserver im Pool auflösen.

Zur Bereitstellung des DNS-Lastenausgleichs für die interne Schnittstelle Ihres Edgeserverpools müssen Sie einen DNS-A-Eintrag hinzufügen, der den internen FQDN des Edgeserverpools in die IP-Adressen der einzelnen Server innerhalb des Pools auflöst.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Verwenden des DNS-Lastenausgleichs in Vermittlungsserverpools

Sie können den DNS-Lastenausgleich in eigenständigen Vermittlungsserverpools verwenden. Der gesamte SIP- und Mediendatenverkehr wird durch den DNS-Lastenausgleich verteilt.

Zur Bereitstellung des DNS-Lastenausgleichs in einem Vermittlungsserverpool müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. mediationpool1.contoso.com) in die IP-Adressen aller Server im Pool (z.<B. 192.168.1.1, 192.168.1.2 usw.) bereitstellen.
.

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blockieren des Datenverkehrs auf einem Server mit DNS-Lastenausgleich

Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr auf einem bestimmten Computer blockieren müssen, reicht es nicht aus, die IP-Adresseinträge aus dem Pool-FQDN einfach zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen.

Beachten Sie, dass lync Server 2013 für den Server-zu-Server-Datenverkehr einen Topologie-fähigen Lastenausgleich verwendet. Die Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs der Server in der Topologie zu erhalten und den Datenverkehr automatisch an die Server zu verteilen. Um zu verhindern, dass ein Server den Server-zu-Server-Datenverkehr empfängt, müssen Sie den Server aus der Topologie entfernen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

