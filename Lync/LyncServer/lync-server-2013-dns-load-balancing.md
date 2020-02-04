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
ms.openlocfilehash: 30d3b88ac66ad7dc6dd3216d941f4a99fc2feedd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-load-balancing-in-lync-server-2013"></a>DNS-Lastenausgleich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-01-15_

Lync Server ermöglicht den DNS-Lastenausgleich, eine Softwarelösung, die den Verwaltungsaufwand für den Lastenausgleich in Ihrem Netzwerk erheblich verringern kann. Der DNS-Lastenausgleich balanciert den Netzwerkdatenverkehr, der für lync Server eindeutig ist, wie etwa SIP-Datenverkehr und Mediendatenverkehr.

Wenn Sie den DNS-Lastenausgleich bereitstellen, wird der Verwaltungsaufwand Ihres Unternehmens für Hardware-Lastenausgleichs Komponenten minimiert. Darüber hinaus wird eine komplexe Problembehandlung von Problemen im Zusammenhang mit der Fehlkonfiguration von Last-Balancern für den SIP-Datenverkehr eliminiert. Sie können auch Serververbindungen verhindern, damit Sie Server offline schalten können. Durch den DNS-Lastenausgleich wird auch sichergestellt, dass die Probleme mit dem Hardwarelastenausgleich keine Auswirkungen auf Elemente des SIP-Datenverkehrs wie einfaches Anrufrouting haben.

Wenn Sie den DNS-Lastenausgleich verwenden, sind Sie möglicherweise auch in der Lage, kostengünstigere Hardwarelastenausgleichs zu erwerben, als wenn Sie den Hardwarelastenausgleich für alle Arten von Datenverkehr verwendet haben. Sie sollten Load-Balancer verwenden, die Interoperabilitäts Qualifizierungstests mit lync Server bestanden haben. Ausführliche Informationen zum Testen der Lastenausgleichsmodul-Interoperabilität finden Sie unter "lync Server 2010 Load [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)Balancer Partners" unter.

Der DNS-Lastenausgleich wird für Front-End-Pools, Edge-Server-Pools, Director-Pools und eigenständige Vermittlungsserver Pools unterstützt.

<div>

## <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>DNS-Lastenausgleich in Front-End-Pools und Director-Pools

Sie können den DNS-Lastenausgleich für den SIP-Datenverkehr in Front-End-Pools und Director-Pools verwenden. Wenn der DNS-Lastenausgleich bereitgestellt wird, müssen Sie weiterhin Hardwarelastenausgleichs für diese Pools verwenden, jedoch nur für den HTTPS-Datenverkehr zwischen Client und Server. Das Hardware-Lastenausgleichsmodul wird für HTTPS-Datenverkehr von Clients über Ports 443 und 80 verwendet.

Obwohl Sie weiterhin Hardwarelastenausgleichs für diese Pools benötigen, werden deren Einrichtung und Verwaltung in erster Linie für den HTTPS-Datenverkehr verwendet, den die Administratoren von Hardwarelastenausgleich-Geräten gewohnt sind.

<div>

## <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS-Lastenausgleich und Unterstützung älterer Clients und Server

Der DNS-Lastenausgleich unterstützt das automatische Failover nur für Server mit lync Server 2013 oder lync Server 2010 sowie für lync 2013-und lync 2010-Clients. Frühere Versionen von Clients und Office Communications Server können weiterhin mit Pools verbunden werden, auf denen der DNS-Lastenausgleich ausgeführt wird, doch wenn Sie keine Verbindung mit dem ersten Server herstellen können, auf den der DNS-Lastenausgleich verweist, kann ein Failover zu einem anderen Server im Pool nicht durchgeführt werden. .

Wenn Sie Exchange um verwenden, müssen Sie darüber hinaus mindestens Exchange 2010 SP1 verwenden, um Unterstützung für den DNS-Lastenausgleich von lync Server zu erhalten. Wenn Sie eine frühere Version von Exchange verwenden, verfügen Ihre Benutzer nicht über Failoverfunktionen für diese Exchange um-Szenarien:

  - Wiedergeben Ihrer Enterprise-Voicemail auf dem Telefon

  - Übertragen von Anrufen von einer automatischen Exchange UM-Telefonzentrale

Alle anderen Exchange um-Szenarien funktionieren ordnungsgemäß.

</div>

<div>

## <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Bereitstellen des DNS-Lastenausgleichs in Front-End-Pools und Director-Pools

Für die Bereitstellung des DNS-Lastenausgleichs in Front-End-Pools und Director-Pools müssen Sie einige zusätzliche Schritte mit FQDNs und DNS-Einträgen durchführen.

  - Ein Pool, der den DNS-Lastenausgleich verwendet, muss zwei FQDNs aufweisen: den regulären Pool-FQDN, der vom DNS-Lastenausgleich (wie pool01.contoso.com) verwendet wird, und er wird in die physischen IPS der Server im Pool aufgelöst, und ein anderer FQDN für die Webdienste des Pools (wie web01.contoso.com), der in die virtuelle IP-Adresse des Pools aufgelöst wird.
    
    Wenn Sie im Topologie-Generator den DNS-Lastenausgleich für einen Pool bereitstellen möchten, müssen Sie zum Erstellen dieses zusätzlichen FQDN für die Webdienste des Pools das Kontrollkästchen **FQDN des internen Webdienste-Pool außer Kraft setzen** aktivieren und den FQDN in der Seite **Geben Sie die Webdienste-URLs für diesen Pool angeben** ein.

  - Zur Unterstützung des vom DNS-Lastenausgleich verwendeten FQDN müssen Sie DNS bereitstellen, um den Pool-FQDN (wie pool01.contoso.com) in die IP-Adressen aller Server im Pool aufzulösen (beispielsweise 192.168.1.1, 192.168.1.2 usw.). Sie sollten nur die IP-Adressen der Server einbeziehen, die derzeit bereitgestellt werden.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie über mehr als einen Front-End-Pool oder Front-End-Server verfügen, muss der FQDN der externen Webdienste eindeutig sein. Wenn Sie beispielsweise den FQDN eines externen Webdiensts eines Front-End-Servers als <STRONG>pool01.contoso.com</STRONG>definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen anderen Front-End-Pool oder Front-End-Server verwenden. Wenn Sie Directors auch bereitstellen, müssen die für Director-oder Director-Pools definierten externen Webdienst-FQDN für jeden anderen Director-oder Director-Pool sowie für jeden Front-End-Pool oder Front-End-Server eindeutig sein. Wenn Sie beschließen, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.

    
    </div>

</div>

</div>

<div>

## <a name="dns-load-balancing-on-edge-server-pools"></a>DNS-Lastenausgleich auf Edgeserver-Pools

Sie können den DNS-Lastenausgleich auf Edgeserver-Pools bereitstellen. Wenn Sie dies tun, müssen Sie sich mit einigen Überlegungen vertraut machen.

Die Verwendung des DNS-Lastenausgleichs auf Ihren Edge-Servern führt in den folgenden Szenarien zu einem Verlust der Failover-Fähigkeit:

  - Föderation mit Organisationen, die Versionen von Office Communications Server ausführen, die vor lync Server 2010 veröffentlicht wurden.

  - Direkter Nachrichtenaustausch mit Benutzern von öffentlichen Instant Messaging-Diensten (im) AOLand\!Yahoo, zusätzlich zu XMPP-basierten Anbietern und Servern wie Google Talk.
    
    <div>
    

    > [!IMPORTANT]  
    > <UL>
    > <LI>
    > <P>Google Talk ist derzeit der einzige unterstützte XMPP-Partner.</P>
    > <LI>
    > <P>Ab dem 1. September, 2012, ist die Microsoft lync Public im Connectivity-Benutzerabonnementlizenz ("PIC USL") nicht mehr für den Kauf von neuen oder erneuernden Vereinbarungen verfügbar. Kunden mit aktiven Lizenzen sind in der Lage, weiterhin mit Yahoo! zu verbünden Messenger, bis der Dienst das Datum beendet hat. Datum des Endes des Lebenszyklus von Juni 2014 für AOL und Yahoo! wurde angekündigt. Ausführliche Informationen finden Sie <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">unter Unterstützung für öffentliche Instant Messenger-Konnektivität in lync Server 2013</A>.</P></LI></UL>

    
    </div>

Diese Szenarien funktionieren so lange, wie alle Edgeserver im Pool ausgeführt werden, aber wenn ein Edgeserver nicht verfügbar ist, werden alle Anforderungen für diese Szenarien, die an ihn gesendet werden, nicht mehr an einen anderen Edgeserver weitergeleitet.

Wenn Sie Exchange um verwenden, müssen Sie mindestens Exchange 2013 verwenden, um Unterstützung für den lync Server-DNS-Lastenausgleich auf Edge zu erhalten. Wenn Sie eine frühere Version von Exchange verwenden, verfügen die Remotebenutzer nicht über Failoverfunktionen für diese Exchange um-Szenarien:

  - Wiedergeben Ihrer Enterprise-Voicemail auf dem Telefon

  - Übertragen von Anrufen von einer automatischen Exchange UM-Telefonzentrale

Alle anderen Exchange um-Szenarien funktionieren ordnungsgemäß.

Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.

<div>

## <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Bereitstellen des DNS-Lastenausgleichs auf Edgeserver-Pools

Zum Bereitstellen des DNS-Lastenausgleichs auf der externen Schnittstelle Ihres Edge-Server Pools benötigen Sie die folgenden DNS-Einträge:

  - Für den Access Edge-Dienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Access-Edgedienst (beispielsweise SIP.contoso.com) in die IP-Adresse des Access Edge-Diensts auf einem der Edgeserver im Pool auflösen.

  - Für den Web Conferencing Edge-Dienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Webkonferenz-Edgedienst (beispielsweise webconf.contoso.com) in die IP-Adresse des Webkonferenz-Edgedienst auf einem der Edgeserver im Pool auflösen.

  - Für den Audio/Video Edge-Dienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Audio/Video-Edgedienst (beispielsweise AV.contoso.com) in die IP-Adresse des A/V Edge-Diensts auf einem der Edgeserver im Pool auflösen.

Zum Bereitstellen des DNS-Lastenausgleichs auf der internen Schnittstelle Ihres Edge-Server Pools müssen Sie einen DNS-A-Eintrag hinzufügen, der den internen FQDN des Edge-Server Pools in die IP-Adresse jedes Servers im Pool auflöst.

</div>

</div>

<div>

## <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Verwenden des DNS-Lastenausgleichs in Vermittlungs Server Pools

Sie können den DNS-Lastenausgleich für eigenständige Vermittlungs Server Pools verwenden. Der gesamte SIP-und Mediendatenverkehr wird durch den DNS-Lastenausgleich ausgeglichen.

Zum Bereitstellen des DNS-Lastenausgleichs in einem Vermittlungs Server Pool müssen Sie DNS bereitstellen, um den Pool-FQDN (beispielsweise mediationpool1.contoso.com) in die IP-Adressen aller Server im Pool aufzulösen (beispielsweise 192.168.1.1, 192.168.1.2 usw.).

</div>

<div>

## <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Blockieren des Datenverkehrs auf einem Server mit DNS-Lastenausgleich

Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr an einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen.

Beachten Sie, dass lync Server 2013 für den Server-zu-Server-Datenverkehr Topologie-bewusste Lastenverteilung verwendet. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs von Servern in der Topologie abzurufen und den Datenverkehr automatisch auf die Server zu verteilen. Wenn Sie verhindern möchten, dass ein Server Server-zu-Server-Datenverkehr empfängt, müssen Sie den Server aus der Topologie entfernen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

