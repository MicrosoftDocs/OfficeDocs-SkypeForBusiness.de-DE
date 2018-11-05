---
title: 'Lync Server 2013: Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich'
TOCTitle: Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398478(v=OCS.15)
ms:contentKeyID: 49294255
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

In der Edgepool-Topologie werden zwei oder mehr Edgeserver als Lastenausgleichpool im Umkreisnetzwerk des Rechenzentrums bereitgestellt. Hardwarelastenausgleich wird für Datenverkehr zu den externen sowie internen Edgeserver-Schnittstellen verwendet.

Wenn Ihre Organisation Unterstützung für mehr als 15.000 Zugriffs-Edgedienst-Clientverbindungen, 1.000 aktive Webkonferenz-Edgedienst-Clientverbindungen oder 500 gleichzeitige A/V-Edgedienst-Sitzungen benötigt und der Edgeserver unbedingt hochverfügbar sein muss, bietet diese Topologie den Vorteil von Skalierbarkeit und Failover-Unterstützung.

In der Abbildung nicht gezeigt werden die Directors, die eine optionale Serverrolle sind, die im internen Netzwerk zwischen den Edgeserver und Ihrem Front-End-Pools oder Server bereitgestellt wird. Nähere Einzelheiten zur Topologie für Directors finden Sie unter [Für den Director erforderliche Komponenten in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).


> [!NOTE]
> Die Abbildung dient zur Orientierung und als Beispiel zur IP-Adressierung. Sie stellt jedoch nicht die tatsächlichen Kommunikationsflüsse mit dem korrekten ein- und ausgehenden Datenverkehr dar. Gezeigt wird nur eine allgemeine Darstellung möglicher Verkehrsflüsse. Die Einzelheiten zum Datenverkehrsfluss in eingehender (zu Überwachungsports) und ausgehender Richtung (zu Zielservern oder -clients) sind in den einzelnen Szenarien jeweils im Diagramm "Portübersicht" abgebildet. So ist zum Beispiel TCP 443 real gesehen nur eingehend (zum Edgeserver oder Reverseproxy) und nur aus Sicht des TCP-Protokolls bidirektional. Außerdem zeigt die Abbildung, welche Änderungen beim Einsatz von NAT (Network Address Translation, Netzwerkadressenübersetzung ) im Datenverkehr vorgenommen werden (bei eingehendem Datenverkehr wird die Zieladresse, bei ausgehendem Datenverkehr die Quelladresse geändert). Das gezeigte Beispiel mit externer und interner Firewall sowie Serverschnittstellen dient nur zu Referenzzwecken. Und wo zutreffend, sind auch noch Beispiele für ein Standardgateway und Routenbeziehungen abgebildet. Beachten Sie auch, dass die DNS-Zone <EM>.com</EM> im Diagramm die externe DNS-Zone sowohl für den Reverseproxy als auch die Edgeserver bildet und die DNS-Zone <EM>.net</EM> auf die interne DNS-Zone verweist.



Neu in Microsoft Lync Server 2013 ist die Unterstützung der IPv6-Adressierung. Ähnlich wie bei der IPv4-Adressierung müssen IPv6-Adressen so zugewiesen werden, dass die Adressen Teil Ihres zugewiesenen IPv6-Adressraums sind. Die Adressen in diesem Thema dienen nur als Beispiel. Sie müssen IPv6-Adressen verwenden, die mit Ihrer Bereitstellung kompatibel sind, den entsprechenden Adressraum unterstützen und für die interne und externe Adressierung verwendet werden können. In Windows Server gibt es ein Feature mit der Bezeichnung *dualer Stapel* , das für den IPv6-Übergangsbetrieb und die Kommunikation zwischen IPv4 und IPv6 eine wichtige Rolle spielt. Beim dualen Stapel handelt es sich um einen separaten und unabhängigen Netzwerkstapel für IPv4 und IPv6. Der duale Stapel ermöglicht die gleichzeitige Zuweisung von IPv4- und IPv6-Adressen und ermöglicht dem Server die Kommunikation mit anderen Hosts und Clients auf der Basis ihrer Anforderungen.

Typische Adresstypen, die Sie für die IPv6-Adressierung verwenden werden, sind die globalen IPv6-Adressen (vergleichbar mit den öffentlichen IPv4-Adressen), die eindeutigen lokalen IPv6-Adressen (vergleichbar mit den privaten IPv4-Adressbereichen) und die verbindungslokalen IPv6-Adressen (vergleichbar mit den automatisch zugewiesenen, privaten IP-Adressen in Windows Server für IPv4).

Für IPv6 gibt es Technologien zur Netzwerkadressenübersetzung (Network Address Translation, NAT), die NAT IPv6 zu IPv4 (im Allgemeinen als NAT64 bezeichnet) und NAT IPv6 zu IPv6 (im Allgemeinen als NAT66 bezeichnet) ermöglichen. Das Vorhandensein von NAT-Technologien bedeutet, dass die für Lync Server- Edgeserver dargestellten fünf Szenarien auch weiterhin gelten.


> [!WARNING]
> IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internetanbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows Server- und Lync Server 2013-Ebene zuweisen, erwartungsgemäß funktionieren. Zusätzliche Ressourcen zur IPv6-Adressierung und -Planung finden Sie über die Links am Ende dieses Themas.



**Konfiguration des Hardwaregeräts zum Lastenausgleich**

Ausführliche Informationen finden Sie im Abschnitt "Anforderungen bei Verwendung eines Hardwaregeräts zum Lastenausgleich für A/V-Edgeserver" unter [Erforderliche Komponenten für den Zugriff durch externe Benutzer in Lync Server 2013](lync-server-2013-components-required-for-external-user-access.md).

**Skalierte konsolidierte Edgetopologie (Hardwarelastenausgleich)**

![Skalierter konsolidierter Edgeserver – Topologie](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "Skalierter konsolidierter Edgeserver – Topologie")


> [!IMPORTANT]
> Falls Sie den Anrufsteuerungsdienst verwenden, müssen Sie der internen Schnittstelle des Edgeservers IPv4-Adressen zuweisen. Der Anrufsteuerungsdienst verwendet IPv4-Adressen und benötigt sie für den Betrieb.



## In diesem Abschnitt

  - [Zertifikatzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich in Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

## Siehe auch

#### Weitere Ressourcen

[IP Version 6-Adressierungsarchitektur](http://tools.ietf.org/html/rfc4291)  
[IPv6 Global Unicast-Adressformat](http://tools.ietf.org/html/rfc3587)  
[Unique Local IPv6-Unicastadressen](http://tools.ietf.org/html/rfc4193)

