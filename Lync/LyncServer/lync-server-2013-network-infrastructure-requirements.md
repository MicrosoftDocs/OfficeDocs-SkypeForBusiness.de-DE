---
title: Anforderungen für die Netzwerkinfrastruktur in lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc1f74705469bf3a024d84848942eae972e0a629
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Anforderungen an die Netzwerkinfrastruktur für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-18_

Die Netzwerkadapterkarte jedes Servers in der lync Server 2013-Topologie muss mindestens 1 Gigabit pro Sekunde (Gbit/s) unterstützen. Im Allgemeinen sollten Sie alle Serverrollen innerhalb der lync Server-Topologie mit einem lokalen Netzwerk (LAN) mit geringer Latenz und großer Bandbreite verbinden. Die Größe des LANs hängt von der Größe der Topologie ab:

  - In Standard Edition-Topologien sollten sich die Server in einem Netzwerk befinden, das 1 Gbit/s Ethernet oder eine Entsprechung unterstützt.

  - In Front-End-Pool Topologien sollten sich die meisten Server in einem Netzwerk befinden, das mehr als 1 Gbit/s unterstützt, insbesondere bei der Unterstützung von Audio/Video-Konferenzen (a/V) und Anwendungsfreigabe.

Zur Integration in das Telefonfestnetz (Public Switched Telephone Network, PSTN) können Sie entweder T1/E1-Leitungen oder das SIP-Trunking verwenden.

<div>

## <a name="audiovideo-network-requirements"></a>Audio/Video-Netzwerkanforderungen

Zu den Netzwerkanforderungen für Audio/Video (a/V) in einer lync Server-Bereitstellung gehören die folgenden:

  - Wenn Sie einen einzelnen Edgeserver oder einen Edge-Pool mithilfe des DNS-Lastenausgleichs bereitstellen, können Sie die externe Firewall als NAT konfigurieren. Sie können die interne Firewall nicht als NAT konfigurieren. Details zu diesen Anforderungen finden Sie unter [Ermitteln der externen A/V-Firewall und Portanforderungen für lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) in der Planungsdokumentation.
    
    <div>
    

    > [!IMPORTANT]  
    > Wenn Sie über einen Edge-Pool verfügen und ein Hardware-Lastenausgleichsmodul verwenden, müssen Sie öffentliche IP-Adressen auf jedem der Edgeserver verwenden, und Sie können NAT nicht für die Server oder den Pool auf Ihrem NAT-Gerät verwenden (beispielsweise die Firewall oder ein anderes Infrastruktur Gerät, das NAT-inbou ND-oder ausgehenden Datenverkehr). Ausführliche Informationen finden Sie unter <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port Zusammenfassung – skalierter konsolidierter Edge mit Hardwarelastenausgleichs in lync Server 2013</A> in der Dokumentation zur Planung für den externen Benutzer Zugriff.

    
    </div>

  - Wenn Ihre Organisation eine QoS-Infrastruktur (Quality of Service) verwendet, wird das Mediensubsystem auf den Betrieb innerhalb der vorhandenen Infrastruktur ausgelegt.

  - Wenn Sie IPsec (Internet Protocol Security) verwenden, wird empfohlen, IPsec für die Portbereiche zu deaktivieren, die für die Übertragung von A/V-Datenverkehr verwendet werden. Ausführliche Informationen finden Sie unter [IPsec-Ausnahmen in lync Server 2013](lync-server-2013-ipsec-exceptions.md) in der Planungsdokumentation.

Gehen Sie wie folgt vor, um eine optimale Medienqualität zu gewährleisten:

  - Stellen Sie Ihre Netzwerk Links bereit, um den Durchsatz von 65 Kbit/s pro Audio-Stream und 500 KBit/s pro Videostream zu unterstützen, sofern diese während der Spitzennutzungszeiten aktiviert sind. Eine bidirektionale Audio-oder Videositzung besteht aus zwei Streams.

  - Um unerwartete Spitzen im Datenverkehr über dieser Ebene zu bewältigen und die Nutzung im Laufe der Zeit zu vermehren, können lync Server Media-Endpunkte sich an unterschiedliche Netzwerkbedingungen anpassen und Lasten des dreifachen Durchsatzes (siehe vorheriger Absatz) für Audio und Video unterstützen, während Sie immer noch Beibehaltung akzeptabler Qualität. Gehen Sie jedoch nicht davon aus, dass diese Anpassungsfähigkeit ein unter bereitgestelltes Netzwerk unterstützt. In einem unter bereitgestellten Netzwerk wird die Möglichkeit, dass die lync Server-Medien Endpunkte dynamisch mit unterschiedlichen Netzwerkbedingungen (beispielsweise temporärer hoher Paketverlust) umgehen können, verringert.

  - Bei Netzwerk Links, bei denen die Bereitstellung extrem kostspielig und schwierig ist, müssen Sie möglicherweise die Bereitstellung für ein geringeres Datenaufkommen in Frage stellen. Lassen Sie in diesem Szenario die Elastizität der lync Server-Medien Endpunkte den Unterschied zwischen dem Verkehrsaufkommen und dem Höchstwert für den Datenverkehr absorbieren, und zwar zu den Kosten einer gewissen Verringerung der Sprachqualität. Darüber hinaus gibt es eine Verringerung der Kopffreiheit, die sonst zur Aufnahme von plötzlichen Peaks im Verkehr zur Verfügung steht.

  - Für Links, die kurzfristig nicht richtig bereitgestellt werden können (beispielsweise eine Website mit sehr schlechten WAN-Links), sollten Sie das Deaktivieren von Video für bestimmte Benutzer in Frage stellen.

  - Stellen Sie Ihr Netzwerk bereit, um eine maximale End-to-End-Verzögerung (Latenz) von 150 Millisekunden (MS) unter Spitzenlast zu gewährleisten. Latenz ist die einzige Netzwerk Beeinträchtigung, die lync Server-Medienkomponenten nicht verringern können, und es ist wichtig, die Schwachstellen zu finden und zu eliminieren.

  - Berücksichtigen Sie bei Servern mit Antivirensoftware alle Server, auf denen lync Server ausgeführt wird, in der Ausnahmeliste, um eine optimale Leistung und Audioqualität zu gewährleisten.

</div>

<div>

## <a name="conferencing-network-requirements"></a>Netzwerkanforderungen für Konferenzen

Die Bandbreite, die zum Herunterladen von Konferenz Inhalten vom IIS-Server (Internet Information Services) verwendet wird, hängt von der Größe des hochgeladenen Inhalts ab.

</div>

</div>

<span> </span>

</div>

</div>

</div>

