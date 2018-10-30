---
title: 'Lync Server 2013: Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen'
TOCTitle: Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen
ms:assetid: 2b854f6d-3d3f-4961-a5f8-a03f47740df0
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204761(v=OCS.15)
ms:contentKeyID: 49293520
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In der Edgeserverpool-Topologie werden mindestens zwei Edgeserver als Pool mit Lastenausgleich im Umkreisnetzwerk des Rechenzentrums bereitgestellt. Für Datenverkehr zur externen und internen Edgeschnittstelle wird DNS-Lastenausgleich verwendet.

Wenn Ihre Organisation mehr als 15.000 Clientverbindungen für den Zugriffs-Edgedienst, 1.000 aktive Clientverbindungen für den Lync Server-Webkonferenzdienst oder 500 gleichzeitige A/V-Edgesitzungen unterstützen muss und/oder eine hohe Verfügbarkeit des Edgeservers wichtig ist, bietet diese Topologie die Vorteile von Skalierbarkeit und Failoverunterstützung.

In der Abbildung sind Directors, eine optionale Serverrolle, die im internen Netzwerk zwischen den Edgeservern und Ihren Front-End-Pools oder Ihrem Server bereitgestellt werden, nicht dargestellt. Ausführliche Informationen zur Topologie für Directors finden Sie unter [Für den Director erforderliche Komponenten in Lync Server 2013](lync-server-2013-components-required-for-the-director.md). Die Abbildung stellt einen einzelnen Reverseproxy dar.


> [!NOTE]
> Die Abbildung dient zur Orientierung und als Beispiel für die IP-Adressierung, soll aber nicht den tatsächlichen Kommunikationsfluss mit dem entsprechenden ein- und ausgehenden Datenverkehr darstellen. Diese Abbildung stellt eine Übersicht über den möglichen Datenverkehr dar. Details des eingehenden (zu den Überwachungsports) und ausgehenden (zu den Zielservern oder Clients) Datenverkehrsflusses sind im Portübersichtsdiagramm in jedem Szenario dargestellt. Beispielsweise ist TCP&nbsp;443 nur eingehend (zum Edgeserver oder Reverseproxy) und bezüglich des Protokolls (TCP) nur ein bidirektionaler Datenfluss. Darüber hinaus ist in der Abbildung dargestellt, wie sich der Datenverkehr ändert, wenn die Netzwerkadressenübersetzung (Network Address Translation, NAT) ausgeführt wird (die Zieladresse wird für eingehenden Datenverkehr geändert, die Quelladresse wird für ausgehenden Datenverkehr geändert). Beispiele für externe und interne Firewalls sowie Serverschnittstelen dienen nur zu Referenzzwecken. Schließlich sind soweit zutreffend Beispiele für Standardgateways und Routenbeziehungen dargestellt. Beachten Sie auch, dass im Diagramm die DNS-Zone <EM>.com</EM> zur Darstellung der externen DNS-Zone sowohl für Reverseproxy als auch Edgeserver verwendet wird und dass sich die DNS-Zone <EM>.net</EM> auf die interne DNS-Zone bezieht.



Neu in Microsoft Lync Server 2013 ist die Unterstützung der IPv6-Adressierung. Ähnlich wie bei der IPv4-Adressierung müssen IPv6-Adressen so zugewiesen werden, dass die Adressen Teil Ihres zugewiesenen IPv6-Adressraums sind. Die Adressen in diesem Thema dienen nur als Beispiel. Sie müssen IPv6-Adressen verwenden, die mit Ihrer Bereitstellung kompatibel sind, den entsprechenden Adressraum unterstützen und für die interne und externe Adressierung verwendet werden können. In Windows Server gibt es ein Feature mit der Bezeichnung *dualer Stapel* , das für den IPv6-Übergangsbetrieb und die Kommunikation zwischen IPv4 und IPv6 eine wichtige Rolle spielt. Beim dualen Stapel handelt es sich um einen separaten und unabhängigen Netzwerkstapel für IPv4 und IPv6. Der duale Stapel ermöglicht die gleichzeitige Zuweisung von IPv4- und IPv6-Adressen und ermöglicht dem Server die Kommunikation mit anderen Hosts und Clients auf der Basis ihrer Anforderungen.

Typische Adresstypen, die Sie für die IPv6-Adressierung verwenden werden, sind die globalen IPv6-Adressen (vergleichbar mit den öffentlichen IPv4-Adressen), die eindeutigen lokalen IPv6-Adressen (vergleichbar mit den privaten IPv4-Adressbereichen) und die verbindungslokalen IPv6-Adressen (vergleichbar mit den automatisch zugewiesenen, privaten IP-Adressen in Windows Server für IPv4).

Für IPv6 gibt es Technologien zur Netzwerkadressenübersetzung (Network Address Translation, NAT), die NAT IPv6 zu IPv4 (im Allgemeinen als NAT64 bezeichnet) und NAT IPv6 zu IPv6 (im Allgemeinen als NAT66 bezeichnet) ermöglichen. Das Vorhandensein von NAT-Technologien bedeutet, dass die für Lync Server- Edgeserver dargestellten fünf Szenarien auch weiterhin gelten.


> [!WARNING]
> IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internetanbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows Server- und Lync Server 2013-Ebene zuweisen, erwartungsgemäß funktionieren. Zusätzliche Ressourcen zur IPv6-Adressierung und -Planung finden Sie über die Links am Ende dieses Themas.



![Skalierter konsolidierter Edgeserver – Topologie](images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "Skalierter konsolidierter Edgeserver – Topologie")


> [!IMPORTANT]
> Falls Sie den Anrufsteuerungsdienst verwenden, müssen Sie der internen Schnittstelle des Edgeservers IPv4-Adressen zuweisen. Der Anrufsteuerungsdienst verwendet IPv4-Adressen und benötigt sie für den Betrieb.



## In diesem Abschnitt

  - [Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Portzusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [DNS-Zusammenfassung für einen skalierten konsolidierten Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

## Siehe auch

#### Weitere Ressourcen

[IP Version 6-Adressierungsarchitektur](http://tools.ietf.org/html/rfc4291)  
[IPv6 Global Unicast-Adressformat](http://tools.ietf.org/html/rfc3587)  
[Unique Local IPv6-Unicastadressen](http://tools.ietf.org/html/rfc4193)

