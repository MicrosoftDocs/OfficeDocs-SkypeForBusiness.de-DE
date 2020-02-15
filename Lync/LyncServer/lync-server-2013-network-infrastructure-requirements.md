---
title: Lync Server 2013 Anforderungen an die Netzwerkinfrastruktur
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93e68a7aecd8c1390993d25d23668813cad0abbf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008217"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Anforderungen an die Netzwerkinfrastruktur für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-18_

Die Netzwerkadapterkarte jedes Servers in der lync Server 2013 Topologie muss mindestens 1 Gigabit pro Sekunde (Gbit/s) unterstützen. Im Allgemeinen sollten Sie alle Serverrollen innerhalb der lync Server Topologie mit einer geringen Wartezeit und einer hohen Bandbreite für lokales Netzwerk (Local Area Network, LAN) verbinden. Die Größe des LAN ist von der Größe der Topologie abhängig:

  - In Standard Edition-Topologien sollten sich die Server in einem Netzwerk befinden, das 1 Gbit/s-Ethernet oder eine gleichwertige unterstützt.

  - In Front-End-Pool Topologien sollten sich die meisten Server in einem Netzwerk befinden, das mehr als 1 Gbit/s unterstützt, insbesondere bei der Unterstützung von Audio/Video-Konferenzen und Anwendungsfreigaben (a/V).

Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.

<div>

## <a name="audiovideo-network-requirements"></a>Netzwerkanforderungen für die Audio/Video-Unterstützung

Die Netzwerkanforderungen für Audio/Video (a/V) in einer lync Server-Bereitstellung umfassen Folgendes:

  - Wenn Sie einen einzelnen Edgeserver oder einen Edgepool mithilfe des DNS-Lastenausgleichs bereitstellen, können Sie die externe Firewall als NAT konfigurieren. Sie können keine interne Firewall mit NAT konfigurieren. Ausführliche Informationen zu diesen Anforderungen finden Sie unter [bestimmen der externen A/V-Firewall-und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in der Planungsdokumentation.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie über eine Edgepool verfügen und einen Hardwaregerät zum Lastenausgleich verwenden, müssen Sie auf jedem Edgeserver öffentliche IP-Adressen verwenden, und Sie können NAT nicht für die Server oder den Pool an Ihrem NAT-Gerät verwenden (beispielsweise die Firewall oder ein anderes Infrastruktur Gerät, das NAT inbou ND-oder ausgehenden Datenverkehr). Ausführliche Informationen finden Sie unter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port Summary – skalierter konsolidierter Edgeserver mit Hardwarelastenausgleichs in lync Server 2013</A> in der Dokumentation zur Planung externer Benutzerzugriffe.

    
    </div>

  - Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.

  - Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden. Ausführliche Informationen finden Sie unter [IPSec Exceptions in lync Server 2013](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.

Mit folgenden Maßnahmen können Sie optimale Medienqualität sicherstellen:

  - Richten Sie die Netzwerkverbindungen so ein, dass sie bei Spitzenauslastung einen Durchsatz von 65 KBit/s pro Audiostream und 500 KBit/s pro Videostream (sofern aktiviert) unterstützen. Eine bidirektionale Audio- oder Videositzung umfasst zwei Datenströme.

  - Um unerwartete Spitzenwerte im Datenverkehr oberhalb dieser Ebene und eine erhöhte Nutzung im Laufe der Zeit zu bewältigen, können sich lync Server Medien Endpunkte an unterschiedliche Netzwerkbedingungen anpassen und Lasten von dreimal so hoch wie der Durchsatz (siehe vorheriger Absatz) für Audio und Video, während die Beibehaltung annehmbarer Qualität. Gehen Sie jedoch nicht davon aus, dass diese Anpassungsfähigkeit ein unter bereitgestelltes Netzwerk unterstützt. In einem untergeordneten Netzwerk wird die Fähigkeit der lync Server Medien Endpunkte, dynamische unterschiedliche Netzwerkbedingungen (beispielsweise ein vorübergehender hoher Paketverlust) zu bewältigen, reduziert.

  - Für Netzwerkverbindungen, deren Bereitstellung sehr kostspielig und aufwendig ist, können Sie eine Dimensionierung für ein niedrigeres Datenverkehrsaufkommen erwägen. In diesem Szenario lassen Sie die Elastizität der lync Server Medien Endpunkte den Unterschied zwischen dem Datenverkehrsvolumen und der Spitzen Daten verkehrsstufe absorbieren, wobei sich die Sprachqualität verringert. Gleichzeitig verringert sich der Puffer, der andernfalls zum Auffangen plötzlicher Datenspitzen zur Verfügung steht.

  - Bei Verbindungen, die kurzfristig nicht ausreichend dimensioniert werden können (beispielsweise an einem Standort mit sehr schlechten WAN-Verbindungen) kann es ratsam sein, die Videofunktion für bestimmte Benutzer zu deaktivieren.

  - Stellen Sie bei der Netzwerkbereitstellung sicher, dass bei Spitzenauslastung eine maximale End-to-End-Verzögerung (Latenz) von 150 ms auftritt. Latenz ist die einzige Netzwerk Schädigung, die lync Server Medienkomponenten nicht verringern können, und es ist wichtig, die Schwachstellen zu finden und zu beseitigen.

  - Schließen Sie für Server, auf denen Antivirensoftware ausgeführt wird, alle Server mit lync Server in der Ausnahmeliste ein, um optimale Leistung und Audioqualität zu gewährleisten.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Netzwerkanforderungen für Konferenzen

Die Bandbreite, die zum Herunterladen von Konferenz Inhalten vom Internet Information Services (IIS) Server verwendet wird, hängt von der Größe der hochgeladenen Inhalte ab.

</div>

</div>

<span> </span>

</div>

</div>

</div>

