---
title: 'Lync Server 2013: skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleich'
description: 'Lync Server 2013: skalierter konsolidierter Edgeserver mit Hardwaregerät zum Lastenausgleich.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 808c03e0d6f2836719599c6cad9ec83e1c96b207
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547651"
---
# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleichssystemen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-21_

In der Edgepool Topologie werden zwei oder mehr Edgeserver als Pool mit Lastenausgleich im Umkreisnetzwerk des Datencenters bereitgestellt. Der Hardware Lastenausgleich wird für den Datenverkehr sowohl für die externe als auch für die interne Edgeserver Schnittstellen verwendet.

Wenn Ihre Organisation Unterstützung für mehr als 15.000 Zugriffs-Edgedienst-Clientverbindungen, 1.000 Active Webkonferenz-Edgedienst-Clientverbindungen oder 500 gleichzeitige A/V-Edgedienst Sitzungen und hohe Verfügbarkeit der Edgeserver wichtig ist, bietet diese Topologie die Vorteile von Skalierbarkeit und Failover-Unterstützung.

In der Abbildung werden Directors, eine optionale Serverrolle, die im internen Netzwerk zwischen den Edgeserver und ihren Front-End-Pools oder-Servern bereitgestellt wird, nicht angezeigt. . Ausführliche Informationen zur Topologie für Directors finden Sie unter [für den Director in lync Server 2013 erforderliche Komponenten](lync-server-2013-components-required-for-the-director.md).

<div>


> [!NOTE]  
> Die Abbildung dient zur Orientierung und als Beispiel für die IP-Adressierung, soll aber nicht den tatsächlichen Kommunikationsfluss mit dem entsprechenden ein- und ausgehenden Datenverkehr darstellen. Diese Abbildung stellt eine Übersicht über den möglichen Datenverkehr dar. Details des eingehenden (zu den Überwachungsports) und ausgehenden (zu den Zielservern oder Clients) Datenverkehrsflusses sind im Portübersichtsdiagramm in jedem Szenario dargestellt. TCP 443 ist beispielsweise nur eingehend (nur für den Edgeserver oder Reverseproxy) und stellt nur einen bidirektionalen Fluss aus einer Protokoll-(TCP-) Perspektive dar. Darüber hinaus ist in der Abbildung dargestellt, wie sich der Datenverkehr ändert, wenn die Netzwerkadressenübersetzung (Network Address Translation, NAT) ausgeführt wird (die Zieladresse wird für eingehenden Datenverkehr geändert, die Quelladresse wird für ausgehenden Datenverkehr geändert). Beispiele für externe und interne Firewalls sowie Serverschnittstelen dienen nur zu Referenzzwecken. Schließlich sind soweit zutreffend Beispiele für Standardgateways und Routenbeziehungen dargestellt. Beachten Sie auch, dass das Diagramm die <EM>. com</EM> -DNS-Zone verwendet, um die externe DNS-Zone für Reverse-Proxy-und Edgeserver darzustellen, und die <EM>.net</EM> -DNS-Zone auf die interne DNS-Zone verweist.



</div>

Neu in Microsoft lync Server 2013 ist die Unterstützung der IPv6-Adressierung. Genauso wie bei IPv4-Adressierung müssen auch IPv6-Adressen so zugewiesen werden, dass sie zu Ihrem zugeordneten IPv6-Adressraum gehören. Die in diesem Thema verwendeten IPv6-Adressen dienen nur zu Beispielzwecken. Sie müssen sich richtige IPv6-Adressen besorgen, die in Ihrer Bereitstellung funktionieren, den korrekten Raum zuweisen und mit interner und externer Adressierung zusammenarbeiten sollen. Windows Server stellt ein Feature bereit, das für den IPv6-Übergangs Betrieb und die IPv4-zu-IPv6-Kommunikation mit dem Namen *Dual Stack*wichtig ist. Der Dual-Stack ist ein separater und jeweils eigener Netzwerkstapel für IPv4 und für IPv6. Der Dual-Stack ermöglicht es Ihnen, sowohl IPv4- als auch IPv6-Adressen parallel zuzuweisen, und er ermöglicht es dem Server, mit anderen Hosts und Clients gemäß deren Anforderungen zu kommunizieren.

Typische Adresstypen, die Sie für die IPv6-Adressierung verwenden werden, sind die globalen IPv6-Adressen (vergleichbar mit öffentlichen IPv4-Adressen), eindeutige lokale IPv6-Adressen (vergleichbar mit den privaten IPv4-Adressbereichen) und lokale IPv6-Linkadressen (ähnlich wie bei automatischen privaten IP-Adressen in Windows Server für IPv4).

Es existieren NAT-Technologien für IPv6, die die Netzwerkadressübersetzung von IPv6 nach IPv4 (im Allgmeinen als NAT64 bezeichnet) und von IPv6 nach IPv6 (im Allgemeinen als NAT66 bezeichnet) ermöglicht. Das vorhanden sein von NAT-Technologien bedeutet, dass die fünf Szenarien, die für lync Server Edgeserver angezeigt werden, noch gültig sind.

<div>


> [!WARNING]  
> IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internet Anbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows Server-Ebene und auf der lync Server 2013 Ebene zuweisen, erwartungsgemäß funktionieren. Zusätzliche Ressourcen zur IPv6-Adressierung und -Planung finden Sie unter den Links am Ende dieses Themas.



</div>

**Konfiguration des Hardwaregeräts zum Lastenausgleich**

Ausführliche Informationen finden Sie im Abschnitt "Anforderungen an das Hardware Gerät zum Lastenausgleich für A/V-Edge" in Komponenten, die [für den Zugriff durch externe Benutzer in lync Server 2013 erforderlich](lync-server-2013-components-required-for-external-user-access.md)sind.

**Skalierte konsolidierte Edgetopologie (Hardwarelastenausgleich)**

![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) verwenden, müssen Sie der internen Edgeserver-Schnittstelle weiterhin IPv4-Adressen zuweisen. Für CAC werden IPv4-Adressen verwendet, und sie müssen für den Betrieb verfügbar sein.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikatzusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Port Zusammenfassung für einen skalierten konsolidierten Edgeserver mit Hardwarelastenausgleichs für den Lastenausgleich in lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [DNS-Zusammenfassung – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs in lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[IP-Adressierungs Architektur der Version 6](https://tools.ietf.org/html/rfc4291)  
[Globales Unicast-Adress Format in IPv6](https://tools.ietf.org/html/rfc3587)  
[Eindeutige lokale IPv6-Unicast-Adressen](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

