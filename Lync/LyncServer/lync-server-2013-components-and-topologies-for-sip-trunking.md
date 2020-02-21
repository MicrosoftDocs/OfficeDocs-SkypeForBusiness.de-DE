---
title: 'Lync Server 2013: Komponenten und Topologien für SIP-Trunking'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for SIP trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398720(v=OCS.15)
ms:contentKeyID: 48184775
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efdbe65f05d6cc3c3b004380d915927a120145a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Komponenten und Topologien für SIP-Trunking in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

In der folgenden Abbildung ist die SIP-Trunking-Topologie in lync Server dargestellt.

**SIP-Trunking-Topologie**

![SIP-Trunking-Topologie](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "SIP-Trunking-Topologie")

Wie im Diagramm dargestellt, wird ein IP-virtuelles privates Netzwerk (VPN) für die Konnektivität zwischen dem Unternehmensnetzwerk und dem PSTN-Dienstanbieter (Public Switched Telephone Network) verwendet. Der Zweck dieses privaten Netzwerks besteht darin, IP-Konnektivität bereitzustellen, die Sicherheit zu erhöhen und (optional) Qualitätsgarantien (Quality of Service, QoS) zu erhalten. Aufgrund der Beschaffenheit eines VPN müssen Sie TLS (Transport Layer Security) für den SIP-Signalisierungs Datenverkehr oder das Secure Real-Time Transport Protocol (SRTP) für den Mediendatenverkehr nicht verwenden. Verbindungen zwischen dem Unternehmen und dem Dienstanbieter bestehen daher aus einfachen TCP-Verbindungen für SIP und RTP (Plain Real-Time Transport Protocol) (über UDP) für Medien, die über ein IP-VPN getunnelt werden. Stellen Sie sicher, dass für alle Firewalls zwischen den VPN-Routern Ports geöffnet sind, damit die VPN-Router kommunizieren können, und dass die IP-Adressen an den externen Rändern der VPN-Router öffentlich geroutet werden.

<div>


> [!IMPORTANT]  
> Wenden Sie sich an Ihren Dienstanbieter, um zu ermitteln, ob er Unterstützung für hohe Verfügbarkeit bietet, einschließlich Failover. Wenn dies der Fall ist, müssen Sie die Verfahren für die Einrichtung bestimmen. Müssen Sie beispielsweise pro Vermittlungsserver nur eine IP-Adresse und einen SIP-Trunk konfigurieren, oder müssen mehrere SIP-Trunks pro Vermittlungsserver konfiguriert werden?<BR>Wenn Sie über mehrere zentrale Standorte verfügen, Fragen Sie auch, ob der Dienstanbieter Verbindungen zu und von einem anderen zentralen Standort aus aktivieren kann.



</div>

<div>


> [!NOTE]  
> Für das SIP-Trunking wird dringend empfohlen, eigenständige Vermittlungsserver bereitzustellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and Definition Peers in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>Sichern des Vermittlungsserver für SIP-Trunking

Aus Sicherheitsgründen sollten Sie für jede Verbindung zwischen den beiden VPN-Routern ein virtuelles LAN (VLAN) einrichten. Der eigentliche Prozess für die Einrichtung eines VLAN variiert von einem Router-Hersteller zu einem anderen. Weitere Informationen erhalten Sie von Ihrem Router-Anbieter.

Es wird empfohlen, folgende Richtlinien zu befolgen:

  - Richten Sie ein virtuelles LAN (VLAN) zwischen dem Vermittlungsserver und dem VPN-Router im Umkreisnetzwerk ein (auch als DMZ, demilitarisierte Zone und überwachtes Subnetz bezeichnet).

  - Lassen Sie keine Übertragung von Broadcast-oder Multicastpaketen vom Router in das VLAN zu.

  - Blockieren Sie alle Routingregeln, die Datenverkehr vom Router an eine beliebige Stelle weiterleiten, jedoch auf den Vermittlungsserver.

Wenn Sie einen VPN-Server verwenden, sollten Sie die folgenden Richtlinien befolgen:

  - Richten Sie ein VLAN zwischen dem VPN-Server und dem Vermittlungsserver ein.

  - Lassen Sie keine Übertragung von Broadcast-oder Multicastpaketen vom VPN-Server an das VLAN zu.

  - Blockieren Sie alle Routingregeln, die den VPN-Server Datenverkehr an eine beliebige Stelle weiterleiten, jedoch auf den Vermittlungsserver.

  - Verschlüsseln Sie Daten im VPN mithilfe von GRE (Generic Routing Encapsulation).

</div>

</div>

<span> </span>

</div>

</div>

</div>

