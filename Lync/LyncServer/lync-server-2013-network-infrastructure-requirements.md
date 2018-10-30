---
title: Anforderungen an die Netzwerkinfrastruktur
TOCTitle: Anforderungen an die Netzwerkinfrastruktur
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425841(v=OCS.15)
ms:contentKeyID: 49293649
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Anforderungen an die Netzwerkinfrastruktur

 

_**Letztes Änderungsdatum des Themas:** 2014-08-28_

Die Netzwerkadapterkarte für jeden Server in der Lync Server 2013-Topologie muss mindestens 1 GBit/s (Gigabit pro Sekunde) unterstützen. Im Allgemeinen sollten alle Serverrollen innerhalb der Lync Server-Topologie über ein LAN mit geringer Latenz und hoher Bandbreite verbunden werden. Die Größe des LAN ist von der Größe der Topologie abhängig:

  - In Standard Edition-Topologien sollten sich die Server in einem Netzwerk befinden, das 1 GBit/s Ethernet oder eine vergleichbare Leistung unterstützt.

  - In Front-End-Pool-Topologien sollten sich die meisten Server in einem Netzwerk befinden, das mehr als 1 GBit/s unterstützt – insbesondere dann, wenn A/V-Konferenzen und Anwendungsfreigabe unterstützt werden.

Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.

## Netzwerkanforderungen für die Audio/Video-Unterstützung

Die Netzwerkanforderungen für Audio/Video (A/V) in einer Lync Server-Bereitstellung lauten wie folgt:

  - Wenn Sie einen einzelnen Edgeserver oder einen Edgepool mit DNS-Lastenausgleich bereitstellen, können Sie die externe Firewall als Firewall mit Netzwerkadressenübersetzung (NAT) konfigurieren. Sie können keine interne Firewall mit NAT konfigurieren. Ausführliche Informationen zu diesen Anforderungen finden Sie unter [Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in der Planungsdokumentation.
    

    > [!IMPORTANT]
    > Wenn Sie einen Edgepool haben und ein Hardwaregerät zum Lastenausgleich verwenden, müssen Sie auf jedem Edgeserver öffentliche IP-Adressen verwenden und können NAT nicht für die Server oder den Pool des NAT-Geräts verwenden (z.&nbsp;B. die Firewall oder ein anderes Gerät in der Infrastruktur, das für den eingehenden oder ausgehenden Datenverkehr eine Netzwerkadressenübersetzung durchführt). Ausführliche Informationen finden Sie unter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich in Lync Server 2013</A> in der Dokumentation zum Planen des Zugriffs externer Benutzer.



  - Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.

  - Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden. Ausführliche Informationen finden Sie unter [IPSec-Ausnahmen](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.

Mit folgenden Maßnahmen können Sie optimale Medienqualität sicherstellen:

  - Richten Sie die Netzwerkverbindungen so ein, dass sie bei Spitzenauslastung einen Durchsatz von 65 KBit/s pro Audiostream und 500 KBit/s pro Videostream (sofern aktiviert) unterstützen. Eine bidirektionale Audio- oder Videositzung umfasst zwei Datenströme.

  - Um unerwartete Spitzen im Datenverkehr über diesem Niveau und eine zunehmend stärkere Nutzung zu bewältigen, können Lync Server-Medienendpunkte an unterschiedliche Netzwerkbedingungen angepasst werden. Sie können in Audio- und Videositzungen unter Beibehaltung akzeptabler Qualität Lasten unterstützen, die dreimal so hoch liegen wie der Durchsatz (siehe vorangehender Abschnitt). Diese Anpassungsfähigkeit wird in einem unterdimensionierten Netzwerk nicht unterstützt. In einem unterdimensionierten Netzwerk ist die Fähigkeit der Lync Server-Medienendpunkte zur dynamischen Anpassung an sich ändernde Netzwerkbedingungen (z. B. ein temporärer hoher Paketverlust) eingeschränkt.

  - Für Netzwerkverbindungen, deren Bereitstellung sehr kostspielig und aufwendig ist, können Sie eine Dimensionierung für ein niedrigeres Datenverkehrsaufkommen erwägen. In diesem Szenario sorgt die Flexibilität der Lync Server-Medienendpunkte dafür, die Differenz zwischen regulärem Datenverkehrsaufkommen und der Spitzenlast mit leichten Einschränkungen bei der Sprachqualität auszugleichen. Gleichzeitig verringert sich der Puffer, der andernfalls zum Auffangen plötzlicher Datenspitzen zur Verfügung steht.

  - Bei Verbindungen, die kurzfristig nicht ausreichend dimensioniert werden können (beispielsweise an einem Standort mit sehr schlechten WAN-Verbindungen) kann es ratsam sein, die Videofunktion für bestimmte Benutzer zu deaktivieren.

  - Stellen Sie bei der Netzwerkbereitstellung sicher, dass bei Spitzenauslastung eine maximale End-to-End-Verzögerung (Latenz) von 150 ms auftritt. Die Latenz ist eine Netzwerkbeeinträchtigung, die sich nicht durch die Lync Server-Medienkomponenten verringern lässt, und es ist wichtig, Schwachpunkte zu finden und auszuschließen.

  - Für Server, auf denen Antivirensoftware ausgeführt wird, schließen Sie alle Server mit Lync Server in die Ausnahmeliste ein, um eine optimale Leistung und Audioqualität zu gewährleisten.

## Netzwerkanforderungen für Konferenzen

Die Bandbreite, die zum Herunterladen von Konferenzinhalten vom Server mit den Internetinformationsdienste (Internet Information Services, IIS) benötigt wird, richtet sich nach der Größe der hochgeladenen Inhalte.

