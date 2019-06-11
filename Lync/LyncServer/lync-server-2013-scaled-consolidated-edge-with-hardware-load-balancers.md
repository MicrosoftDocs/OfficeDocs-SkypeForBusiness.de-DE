---
title: 'Lync Server 2013: Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa5a395c8509961937af23c12763a5bf55cc326
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

In der Edge-Pool-Topologie werden zwei oder mehr Edgeserver als Lastenausgleichspool im Umkreisnetzwerk des Datencenters bereitgestellt. Der Hardware Lastenausgleich wird für den Datenverkehr sowohl auf der externen als auch auf der internen Edgeserver-Schnittstelle verwendet.

Wenn Ihre Organisation Unterstützung für mehr als 15.000-Access-Edgedienst-Clientverbindungen, 1.000 aktive Webkonferenz-Edgedienst-Clientverbindungen oder 500 gleichzeitige A/V-Edgedienst-Sitzungen erfordert und eine höhere Verfügbarkeit des Edgeserver wichtig ist, Diese Topologie bietet die Vorteile der Skalierbarkeit und der Failover-Unterstützung.

Die Abbildung zeigt keine Directors, eine optionale Serverrolle, die im internen Netzwerk zwischen den Edgeserver und ihren Front-End-Pools oder-Servern bereitgestellt wird. . Details zur Topologie für Directors finden Sie unter [für den Director in lync Server 2013 erforderliche Komponenten](lync-server-2013-components-required-for-the-director.md).

<div>


> [!NOTE]  
> Die angezeigte Abbildung dient zur Orientierung und zum Beispiel für die IP-Adressierung, beabsichtigt aber nicht, tatsächliche Kommunikationsflüsse mit dem korrekten ein-und ausgehenden Datenverkehr darzustellen. Die Abbildung stellt eine Ansicht des möglichen Datenverkehrs auf hoher Ebene dar. Details für den Datenverkehrs Fluss in Bezug auf eingehende (zu hörende Ports) und ausgehende (an Zielserver oder-Clients) werden in den einzelnen Szenarien im Diagramm Port Zusammenfassung dargestellt. TCP 443 ist beispielsweise eigentlich nur eingehend (an den Edgeserver oder Reverse Proxy) und ist nur ein bidirektionaler Fluss aus einer Protokoll (TCP)-Perspektive. Darüber hinaus zeigt die Abbildung die Art des Datenverkehrs an, wenn die NAT (Netzwerkadressübersetzung) Eintritt (die Zieladresse wird bei der eingehenden Änderung geändert, die Quelladresse wird beim ausgehen geändert). Beispiel für externe und interne Firewalls und Serverschnittstellen werden nur zu Referenzzwecken angezeigt. Schließlich werden beispielsweise Standard-Gateway-und-Routen Beziehungen angezeigt, sofern zutreffend. Beachten Sie auch, dass das Diagramm die DNS-Zone " <EM>. com</EM> " verwendet, um die externe DNS-Zone für Reverse-Proxy-und Edgeserver darzustellen, und die <EM>.net</EM> -DNS-Zone bezieht sich auf die interne DNS-Zone.



</div>

Neu bei Microsoft lync Server 2013 ist die Unterstützung für die IPv6-Adressierung. Ähnlich wie bei der IPv4-Adressierung müssen IPv6-Adressen so zugewiesen werden, dass die Adressenteil des zugewiesenen IPv6-Adressraums sind. Die Adressen in diesem Thema dienen nur zum Beispiel. Sie müssen IPv6-Adressen erwerben, die in Ihrer Bereitstellung funktionieren, den korrekten Bereich bereitstellen und mit interner und externer Adressierung interagieren. Windows Server bietet ein Feature, das für den Übergangs-IPv6-Betrieb und die IPv4-zu-IPv6-Kommunikation, die so genannte *Dual Stack*, wichtig ist. Der Dual Stack ist ein separater und unterschiedlicher Netzwerkstapel für IPv4 und für IPv6. Mit dem Dual Stack können Sie die Adressierung für IPv4 und IPv6 gleichzeitig zuweisen und dem Server die Kommunikation mit anderen Hosts und Clients auf der Grundlage Ihrer Anforderungen ermöglichen.

Typische Adresstypen, die Sie für die IPv6-Adressierung verwenden werden, sind die globalen IPv6-Adressen (ähnlich wie öffentliche IPv4-Adressen), eindeutige IPv6-lokale Adressen (ähnlich den privaten IPv4-Adressbereichen) und IPv6-Link-Local-Adressen (ähnlich wie bei der automatischen privaten IP-Adresse). Adressen in Windows Server für IPv4)

Netzwerkadressübersetzung-Technologien (NAT) für IPv6 sind vorhanden, die für NAT IPv6 zu IPv4 (gemeinhin als NAT64 bezeichnet) und für NAT IPv6 zu IPv6 (gemeinhin als NAT66 bezeichnet) zugelassen sind. Das vorhanden sein von NAT-Technologien bedeutet, dass die fünf Szenarien, die für lync Server-Edgeserver bereitgestellt werden, weiterhin gültig sind.

<div>


> [!WARNING]  
> IPv6 ist ein komplexes Thema und erfordert eine sorgfältige Planung mit Ihrem Netzwerkteam und Ihrem Internet Anbieter, um sicherzustellen, dass die Adressen, die Sie auf der Windows-Serverebene und auf der lync Server 2013-Ebene zuweisen, wie erwartet funktionieren. Zusätzliche Informationen zur IPv6-Adressierung und -Planung finden Sie über die Links am Ende dieses Themas.



</div>

**Konfiguration des Hardware-Lastenausgleichs**

Ausführliche Informationen finden Sie im Abschnitt "Hardware Lastenausgleich-Anforderungen für A/V-Edge" unter Komponenten, die [für den Zugriff durch externe Benutzer in lync Server 2013 erforderlich](lync-server-2013-components-required-for-external-user-access.md)sind.

**Skalierte konsolidierte Edge-Topologie (Hardwarelastenausgleich)**

![3a57cd0d-8de4-4ecc-A783-4dff5b3456a2] (images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-A783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> Wenn Sie die Anrufsteuerung (Call Admission Control, CAC) verwenden, müssen Sie der Edge-Server-internen Schnittstelle weiterhin IPv4-Adressen zuweisen. CAC verwendet IPv4-Adressen und muss für den Betrieb zur Verfügung stehen.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikatzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Portzusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwareastenausgleich in Lync Server 2013](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [DNS-Zusammenfassung für skalierte konsolidierte Edgetopologie mit Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[IP Version 6-Adressierungs Architektur](http://tools.ietf.org/html/rfc4291)  
[Globales IPv6-Unicast-Adress Format](http://tools.ietf.org/html/rfc3587)  
[Eindeutige lokale IPv6-Unicast-Adressen](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

