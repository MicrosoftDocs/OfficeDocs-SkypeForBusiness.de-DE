---
title: 'Lync Server 2013: Komponenten und Topologien für das SIP-Trunking'
TOCTitle: Komponenten und Topologien für das SIP-Trunking
ms:assetid: 8ed9a9d0-517e-4f36-a131-22cdafa257fa
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398720(v=OCS.15)
ms:contentKeyID: 49294719
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Komponenten und Topologien für das SIP-Trunking in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Die folgende Abbildung zeigt die Topologie für das SIP-Trunking in Lync Server.

**Topologie für das SIP-Trunking**

![Topologie für das SIP-Trunking](images/Gg398720.669fb55d-7c81-4e21-9421-fabc43d6e064(OCS.15).jpg "Topologie für das SIP-Trunking")

Wie in der Abbildung gezeigt, wird das virtuelle private IP-Netzwerk (IP-VPN) für die Verbindungen zwischen dem Unternehmensnetzwerk und dem PSTN (Public Switched Telephone Network, Telefonfestnetz)-Dienstanbieter verwendet. Mit diesem privaten Netzwerk sollen IP-Verbindungen, erweiterte Sicherheit und (optional) Garantien für die Dienstqualität (Quality of Service, QoS) geboten werden. Aufgrund der Merkmale eines VPNs ist es nicht erforderlich, Transport Layer Security (TLS) für den SIP-Signaldatenverkehr oder Secure Real-Time Transport Protocol (SRTP) für den Mediendatenverkehr zu verwenden. Die Verbindungen zwischen dem Unternehmen und dem Dienstanbieter bestehen deshalb aus einfachen TCP-Verbindungen für SIP-Datenverkehr und einfachen Real-Time Transport Protocol (RTP)-Verbindungen (über UDP) für Mediendatenverkehr, der durch ein IP-VPN getunnelt werden kann. Stellen Sie sicher, dass alle Firewalls zwischen den VPN-Routern offene Ports aufweisen, damit die VPN-Router kommunizieren können. Zudem müssen die IP-Adressen der externen Edgeschnittstellen der VPN-Router öffentlich routingfähig sein.


> [!IMPORTANT]
> Kontaktieren Sie Ihren Dienstanbieter, um zu ermitteln, ob er Unterstützung für hohe Verfügbarkeit (einschließlich Failover) bietet. Wenn ja, müssen Sie die erforderlichen Vorgehensweisen zum Einrichten von hoher Verfügbarkeit ermitteln. Müssen Sie z.&nbsp;B. nur eine IP-Adresse und einen SIP-Trunk auf jedem Vermittlungsserver konfigurieren, oder müssen auf jedem Vermittlungsserver mehrere SIP-Trunks konfiguriert werden?<BR>Wenn Sie über mehr als einen zentraler Standorte verfügen, fragen Sie den Dienstanbieter zudem, ob Verbindungen zwischen den zentraler Standorten hergestellt werden können.




> [!NOTE]
> Für SIP-Trunking wird die Bereitstellung eines eigenständigen Vermittlungsservers dringend empfohlen. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013</A> in der Bereitstellungsdokumentation.



## Schützen des Vermittlungsservers für das SIP-Trunking

Aus Sicherheitsgründen sollten Sie ein virtuelles LAN (VLAN) für jede Verbindung zwischen den zwei VPN-Routern einrichten. Die tatsächliche Vorgehensweise zum Einrichten eines VLANs variiert abhängig vom Routerhersteller. Ausführliche Informationen erhalten Sie von Ihrem Routeranbieter.

Sie sollten die folgenden Richtlinie befolgen:

  - Richten Sie ein virtuelles LAN (VLAN) zwischen dem Vermittlungsserver und dem VPN-Router im Umkreisnetzwerk ein (auch als Demilitarized Zone, DMZ, und überwachtes Subnetz bezeichnet).

  - Lassen Sie keine Übertragung von Broadcast- oder Multicastpaketen vom Router in das VLAN zu.

  - Blockieren Sie alle Routingregeln, über die Datenverkehr vom Router an ein anderes Ziel als den Vermittlungsserver weitergeleitet wird.

Bei Verwendung eines VPN-Servers sollten Sie die folgenden Richtlinie befolgen:

  - Richten Sie ein VLAN zwischen dem VPN-Server und dem Vermittlungsserver ein.

  - Lassen Sie keine Übertragung von Broadcast- oder Multicastpaketen vom VPN-Server in das VLAN zu.

  - Blockieren Sie alle Routingregeln, über die Datenverkehr vom VPN-Server an ein anderes Ziel als den Vermittlungsserver weitergeleitet wird.

  - Verschlüsseln Sie Daten im VPN mithilfe von GRE (Generic Routing Encapsulation).

