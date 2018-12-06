---
title: DNS-Lastenausgleich in Lync Server 2013
TOCTitle: DNS-Lastenausgleich in Lync Server 2013
ms:assetid: 7ed0ed20-33ad-4253-926d-21d392590ae7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398634(v=OCS.15)
ms:contentKeyID: 49294544
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Lastenausgleich in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In Lync Server wird der DNS-Lastenausgleich aktiviert. Es handelt sich hierbei um eine Softwarelösung, mit der der Verwaltungsaufwand für den Lastenausgleich in Ihrem Netzwerk erheblich verringert werden kann. Der DNS-Lastenausgleich sorgt für eine ausgewogene Verteilung des Netzwerkdatenverkehrs von Lync Server, etwa des SIP- und Mediendatenverkehrs.

Wenn Sie DNS-Lastenausgleich implementieren, können Sie den Verwaltungsaufwand für Hardwaregeräte zum Lastenausgleich in Ihrer Organisation minimieren. Darüber hinaus entfällt die komplexe Problembehandlung zur Beseitigung von Fehlern, die durch eine falsche Konfiguration des Lastenausgleichs für SIP-Datenverkehr entstehen. Zudem können Sie Serververbindungen verhindern, sodass Sie Server offline schalten können. Der DNS-Lastenausgleich stellt ferner sicher, dass sich durch Hardwarelastenausgleich hervorgerufene Probleme nicht auf den SIP-Datenverkehr auswirken, etwa auf die grundlegende Anrufweiterleitung.

Wenn Sie DNS-Lastenausgleich verwenden, können Sie möglicherweise auch kostengünstigere Hardwaregeräte zum Lastenausgleich anschaffen, da diese nicht für alle Arten von Datenverkehr eingesetzt werden müssen. Dennoch sollten Sie Lastenausgleichssysteme verwenden, die für Interoperabilität mit Lync Server getestet und qualifiziert wurden. Ausführliche Informationen zu Interoperabilitätstests für Lastenausgleichssysteme finden Sie auf der Webseite "Lync Server 2010 Load Balancer Partners" unter <http://go.microsoft.com/fwlink/?linkid=202452>.

Der DNS-Lastenausgleich wird für Front-End-Pools, Edgeserverpools, Director-Pools und eigenständige Vermittlungsserverpools unterstützt.

## DNS-Lastenausgleich in Front-End-Pools und Director-Pools

Sie können den DNS-Lastenausgleich für den SIP-Datenverkehr in Front-End-Pools und Director-Pools verwenden. Auch wenn Sie einen DNS-Lastenausgleich konfiguriert haben, müssen Sie dennoch auch Hardwaregeräte zum Lastenausgleich für diese Pools verwenden, jedoch nur für den HTTPS-Datenverkehr von Client zu Server. Das Hardwaregerät zum Lastenausgleich wird für HTTPS-Datenverkehr von Clients über die Ports 443 und 80 verwendet.

Auch wenn für diese Pools weiterhin Hardwaregeräte zum Lastenausgleich benötigt werden, müssen diese vornehmlich für den HTTPS-Datenverkehr eingerichtet und verwaltet werden. Dies stellt für Administratoren von Hardwaregeräten zum Lastenausgleich jedoch eine gängige Aufgabe dar.

## DNS-Lastenausgleich und Unterstützung älterer Clients und Server

Der DNS-Lastenausgleich unterstützt ein automatisches Failover nur für Server mit Lync Server 2013- oder Lync Server 2010-Clients und für Lync 2013- und Lync 2010-Clients. Frühere Versionen von Clients und Office Communications Server können sich weiterhin mit Pools verbinden, in denen der DNS-Lastenausgleich durchgeführt wird. Wenn sie jedoch keine Verbindung mit dem ersten Server herstellen können, an den sie vom DNS-Lastenausgleich verwiesen werden, ist kein Failover auf einen anderen Server innerhalb des Pools möglich.

Wenn Sie zudem Exchange UM verwenden, verfügt nur Exchange 2010 mit SP1 oder mit dem neuesten Service Pack über integrierte Unterstützung für den DNS-Lastenausgleich in Lync Server. Bei Verwendung früherer Exchange-Versionen verfügen Sie nicht über Failoverfunktionen für diese Exchange UM-Szenarien:

  - Wiedergeben von Enterprise-VoIP-Voicemail über ein Telefon

  - Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale

Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.

## Bereitstellen von DNS-Lastenausgleich in Front-End-Pools und Director-Pools

Für die Bereitstellung von DNS-Lastenausgleich in Front-End-Pools und Director-Pools müssen einige zusätzliche Schritte im Zusammenhang mit FQDNs und DNS-Einträgen ausgeführt werden.

  - Ein Pool, der DNS-Lastenausgleich verwendet, muss über zwei FQDNs verfügen: den regulären Pool-FQDN (beispielsweise **pool01.contoso.com**), der vom DNS-Lastenausgleich verwendet und in die physischen IP-Adressen der Server im Pool aufgelöst wird, und einen weiteren FQDN für die Webdienste des Pools (z. B. **web01.contoso.com**), der in die virtuelle IP-Adresse des Pools aufgelöst wird.
    
    Wenn Sie den DNS-Lastenausgleich für einen Pool bereitstellen möchten, müssen Sie zum Erstellen dieses zusätzlichen vollqualifizierten Domänennamens für die Webdienste des Pools im Topologie-Generator auf der Seite **Webdienste-URLs für diesen Pool angeben** das Kontrollkästchen **FQDN der internen Webdienste außer Kraft setzen** aktivieren und den FQDN eingeben.

  - Um den vom DNS-Lastenausgleich verwendeten FQDN zu unterstützen, müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. `pool01.contoso.com`) in die IP-Adressen aller Server im Pool bereitstellen (z. B. 192.168.1.1, 192.168.1.2 usw.). Schließen Sie nur die IP-Adressen von Servern ein, die gegenwärtig bereitgestellt sind.
    

    > [!WARNING]
    > Wenn Sie mehr als einen Front-End-Pool oder Front-End-Server haben, muss der FQDN für externe Webdienste eindeutig sein. Wenn Sie beispielsweise <STRONG>pool01.contoso.com</STRONG> als FQDN für externe Webdienste eines Front-End-Servers definieren, können Sie <STRONG>pool01.contoso.com</STRONG> nicht für einen weiteren Front-End-Pool oder Front-End-Server verwenden. Wenn Sie außerdem Directors bereitstellen, darf der FQDN für externe Webdienste, den Sie für einen beliebigen Director oder Directorpool definieren, weder für andere Director oder Directorpools noch für andere Front-End-Pools oder Front-End-Server verwendet werden. Wenn Sie die internen Webdienste mit einem eigenen FQDN außer Kraft setzen, darf kein FQDN mit irgendeinem anderen Front-End-Pool, Director oder Directorpool übereinstimmen.



## DNS-Lastenausgleich in Edgeserverpools

Sie können den DNS-Lastenausgleich in Edgeserverpools bereitstellen. In diesem Fall müssen einige Faktoren berücksichtigt werden.

Bei Verwendung des DNS-Lastenausgleichs auf Ihren Edgeservern verfügen Sie in den folgenden Szenarien nicht länger über eine Failoverfunktion:

  - Partnerverbund mit Organisationen, in denen Versionen von Office Communications Server ausgeführt werden, die vor Lync Server 2010 veröffentlicht wurden.

  - Austausch von Chatnachrichten mit Benutzern öffentlicher Instant Messaging-Dienste wie AOL und Yahoo\!, zusätzlich zu XMPP-basierten Anbietern und Servern wie z. B. Google Talk.
    

    > [!IMPORTANT]
    > <UL>
    > <LI>
    > <P>Google Talk ist derzeit der einzige unterstützte XMPP-Partner.</P>
    > <LI>
    > <P>Ab dem 1. September 2012 kann die Microsoft Lync-Benutzerabonnementlizenz für die Verbindung mit öffentlichen Instant Messaging-Diensten ("PIC USL") nicht mehr neu erworben werden, und Verträge können nicht verlängert werden. Kunden mit aktiven Lizenzen können den Partnerverbund mit Yahoo! Messenger weiterhin nutzen, bis der Dienst eingestellt wird. Als Datum der Einstellung des Diensts für AOL und Yahoo! wurde Juni 2014 angekündigt. Einzelheiten hierzu finden Sie unter <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Unterstützen von Verbindungen mit öffentlichen Chatdiensten in Lync Server 2013</A>.</P></LI></UL>



Diese Szenarien werden unterstützt, solange alle Edgeserver im Pool verfügbar sind und ausgeführt werden. Wenn jedoch einer der Edgeserver ausfällt, werden Anforderungen für diese Szenarien nicht an einen anderen Edgeserver weitergeleitet, sondern können nicht verarbeitet werden.

Wenn Sie Exchange UM verwenden, müssen Sie mindestens Exchange 2013 verwenden, um Unterstützung für den DNS-Lastenausgleich in Lync Server auf Edge zu erhalten. Bei Verwendung früherer Exchange-Versionen verfügen Ihre Remotebenutzer nicht über Failoverfunktionen für diese Exchange UM-Szenarien:

  - Wiedergeben von Enterprise-VoIP-Voicemail über ein Telefon

  - Weiterleiten von Anrufen von einer automatischen Exchange UM-Telefonzentrale

Alle anderen Exchange UM-Szenarien funktionieren ordnungsgemäß.

Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.

## Bereitstellen von DNS-Lastenausgleich in Edgeserverpools

Zur Bereitstellung des DNS-Lastenausgleichs für die externe Schnittstelle Ihres Edgeserverpools benötigen Sie die folgenden DNS-Einträge:

  - Für den Zugriffs-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Zugriffs-Edgediensts (z. B. "sip.contoso.com") in die IP-Adresse des Zugriffs-Edgediensts von auf einem der Edgeserver im Pool auflösen.

  - Für den Webkonferenz-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des Webkonferenz-Edgediensts (z. B. "webconf.contoso.com") in die IP-Adresse des Webkonferenz-Edgediensts auf einem der Edgeserver im Pool auflösen.

  - Für den A/V-Edgedienst benötigen Sie einen Eintrag für jeden Server im Pool. Jeder Eintrag muss den FQDN des A/V-Edgediensts (z. B. "av.contoso.com") in die IP-Adresse des A/V-Edgediensts auf einem der Edgeserver im Pool auflösen.

Zur Bereitstellung des DNS-Lastenausgleichs für die interne Schnittstelle Ihres Edgeserverpools müssen Sie einen DNS-A-Eintrag hinzufügen, der den internen FQDN des Edgeserverpools in die IP-Adressen der einzelnen Server innerhalb des Pools auflöst.

## Verwenden des DNS-Lastenausgleichs in Vermittlungsserverpools

Sie können den DNS-Lastenausgleich in eigenständigen Vermittlungsserverpools verwenden. Der gesamte SIP- und Mediendatenverkehr wird durch den DNS-Lastenausgleich verteilt.

Zur Bereitstellung des DNS-Lastenausgleichs in einem Vermittlungsserverpool müssen Sie DNS für die Auflösung des Pool-FQDN (z. B. **mediationpool1.contoso.com**) in die IP-Adressen aller Server im Pool (z.\<B. 192.168.1.1, 192.168.1.2 usw.) bereitstellen. .

## Blockieren von Datenverkehr an einen Server mit dem DNS-Lastenausgleich

Wenn Sie den DNS-Lastenausgleich verwenden und den Datenverkehr an einen bestimmten Computer blockieren müssen, reicht es nicht aus, einfach nur die IP-Adresseinträge aus dem Pool-FQDN zu entfernen. Sie müssen auch den DNS-Eintrag für den Computer entfernen.

Beachten Sie, dass Lync Server 2013 für den Datenverkehr zwischen Servern einen topologieerkennenden Lastenausgleich verwendet. Server lesen die veröffentlichte Topologie im zentralen Verwaltungsspeicher, um die FQDNs von Servern in der Topologie abzurufen, und verteilen den Datenverkehr automatisch unter den Servern. Um den Datenverkehr zwischen Servern für einen bestimmten Server zu blockieren, müssen Sie diesen Server aus der Topologie entfernen.

