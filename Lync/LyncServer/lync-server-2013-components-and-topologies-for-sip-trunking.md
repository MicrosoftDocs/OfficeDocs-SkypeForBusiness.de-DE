---
title: 'Lync Server 2013: Komponenten und Topologien für das SIP-Trunking'
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
ms.openlocfilehash: d30c589ff02717ad49ce89d0d4e3324f6fe993e9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-sip-trunking-in-lync-server-2013"></a>Komponenten und Topologien für das SIP-Trunking in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die folgende Abbildung zeigt die SIP-Trunking-Topologie in lync Server.

**SIP-Trunking-Topologie**

![Topologie für das SIP-Trunking](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologie für das SIP-Trunking")

Wie in der Abbildung gezeigt wird das virtuelle private IP-Netzwerk (IP-VPN) für die Verbindungen zwischen dem Unternehmensnetzwerk und dem PSTN (Public Switched Telephone Network, Telefonfestnetz)-Dienstanbieter verwendet. Mit diesem privaten Netzwerk sollen IP-Verbindungen, erweiterte Sicherheit und (optional) Garantien für die Dienstqualität (Quality of Service, QoS) geboten werden. Aufgrund der Merkmale eines VPNs ist es nicht erforderlich, Transport Layer Security (TLS) für den SIP-Signaldatenverkehr oder Secure Real-Time Transport Protocol (SRTP) für den Mediendatenverkehr zu verwenden. Die Verbindungen zwischen dem Unternehmen und dem Dienstanbieter bestehen deshalb aus einfachen TCP-Verbindungen für SIP-Datenverkehr und einfachen Real-Time Transport Protocol (RTP)-Verbindungen (über UDP) für Mediendatenverkehr, der durch ein IP-VPN getunnelt werden kann. Stellen Sie sicher, dass alle Firewalls zwischen den VPN-Routern offene Ports aufweisen, damit die VPN-Router kommunizieren können. Zudem müssen die IP-Adressen der externen Edgeschnittstellen der VPN-Router öffentlich routingfähig sein.

<div>


> [!IMPORTANT]  
> Kontaktieren Sie Ihren Dienstanbieter, um zu ermitteln, ob er Unterstützung für hohe Verfügbarkeit (einschließlich Failover) bietet. Wenn ja, müssen Sie die erforderlichen Vorgehensweisen zum Einrichten von hoher Verfügbarkeit ermitteln. Müssen Sie beispielsweise nur eine IP-Adresse und einen SIP-Trunk auf jedem Vermittlungsserver konfigurieren, oder müssen mehrere SIP-Stämme auf jedem Vermittlungsserver konfiguriert werden?<BR>Wenn Sie über mehrere zentrale Websites verfügen, Fragen Sie auch, ob der Dienstanbieter Verbindungen zu und von einem anderen zentralen Standort aus aktivieren kann.



</div>

<div>


> [!NOTE]  
> Für SIP-Trunking empfehlen wir dringend, eigenständige Vermittlungsserver bereitzustellen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Bereitstellen von Vermittlungsservern und Definieren von Peers in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>

## <a name="securing-the-mediation-server-for-sip-trunking"></a>Schützen des Vermittlungsservers für das SIP-Trunking

Aus Sicherheitsgründen sollten Sie ein virtuelles LAN (VLAN) für jede Verbindung zwischen den zwei VPN-Routern einrichten. Die tatsächliche Vorgehensweise zum Einrichten eines VLANs variiert abhängig vom Routerhersteller. Ausführliche Informationen erhalten Sie von Ihrem Routeranbieter.

Sie sollten die folgenden Richtlinie befolgen:

  - Einrichten eines virtuellen LANs (VLAN) zwischen dem Vermittlungs Server und dem VPN-Router im Umkreisnetzwerk (auch bekannt als DMZ, demilitarisierte Zone und geschirmtes Subnetz).

  - Lassen Sie keine Übertragung von Broadcast- oder Multicastpaketen vom Router in das VLAN zu.

  - Blockieren Sie Routingregeln, die den Datenverkehr vom Router an eine beliebige Stelle, aber auf den Vermittlungs Server weiterleiten.

Bei Verwendung eines VPN-Servers sollten Sie die folgenden Richtlinien befolgen:

  - Einrichten eines VLAN zwischen dem VPN-Server und dem Vermittlungsserver

  - Lassen Sie keine Übertragung von Broadcast- oder Multicastpaketen vom VPN-Server in das VLAN zu.

  - Blockieren Sie jede Routingregel, die den VPN-Server Datenverkehr an eine beliebige Stelle, aber den Vermittlungsserver weiterleitet.

  - Verschlüsseln Sie Daten im VPN mithilfe von GRE (Generic Routing Encapsulation).

</div>

</div>

<span> </span>

</div>

</div>

</div>

