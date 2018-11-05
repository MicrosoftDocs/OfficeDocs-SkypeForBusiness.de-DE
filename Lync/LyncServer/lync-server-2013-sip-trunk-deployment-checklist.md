---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung von SIP-Trunks'
TOCTitle: Prüfliste für die Bereitstellung von SIP-Trunks
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398755(v=OCS.15)
ms:contentKeyID: 49294789
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste für die Bereitstellung von SIP-Trunks für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Bevor Sie einen SIP-Trunk bereitstellen können, müssen Sie und Ihr Dienstanbieter einige grundlegende Verbindungsinformationen zu ihren jeweiligen Endpunkten des SIP-Trunks austauschen.

Für jedes ITSP-Gateway, mit dem Sie eine Verbindung herstellen, benötigen Sie die folgenden Informationen:

  - IP-Adresse

  - Vollqualifizierter Domänenname (FQDN)


> [!NOTE]
> Der Dienstanbieter bittet Sie möglicherweise, eine Verbindung mit mehreren ITSP-Gateways herzustellen. In diesem Fall müssen Sie eine Verbindung zwischen jedem ITSP-Gateway und jedem Vermittlungsserver in Ihrem Pool konfigurieren.



Die Informationen, die Sie für Ihren Dienstanbieter bereitstellen, hängen vom Verbindungstyp Ihres SIP-Trunks ab:

  - Für MPLS (Multiprotocol Label Switching)- oder private Netzwerkverbindungen stellen Sie dem ITSP die öffentlich routingfähige IP-Adresse des Routers in Ihrem Umkreisnetzwerk (auch als Demilitarized Zone, DMZ, und überwachtes Subnetz bezeichnet) bereit. Stellen Sie sicher, dass diese Adresse vom Gateway oder Session Border Controller (SBC) auf der ITSP-Seite kontaktiert werden kann. Übermitteln Sie dem ITSP zudem den FQDN Ihres Vermittlungsservers.

  - Für VPN-Verbindungen (Virtual Private Network) teilen Sie dem ITSP die IP-Adresse Ihres VPN-Servers mit.

## Überlegungen zu Zertifikaten

Fragen Sie Ihren ITSP nach den unterstützten Protokollen, um zu ermitteln, ob Sie ein Zertifikat für das SIP-Trunking benötigen:

1.  Wenn Ihr ITSP nur TCP unterstützt, benötigen Sie kein Zertifikat.

2.  Wenn Ihr ITSP Unterstützung für TLS (Transport Layer Security) bietet, muss Ihnen der ITSP ein Zertifikat bereitstellen.


> [!NOTE]
> SIP wird mit RTP (Real-time Transport Protocol) oder SRTP (Secure Real-time Transport Protocol) eingesetzt, den Protokollen für die eigentlichen VoIP-Daten in VoIP-Anrufen.



## Bereitstellungsprozess

Führen Sie die folgenden Schritte aus, um die Lync Server-Seite der SIP-Trunkverbindung zu implementieren:

1.  Erstellen und konfigurieren Sie unter Verwendung des Lync Server- Topologie-Generators die SIP-Domänentopologie. Ausführliche Informationen finden Sie unter [Definieren und Konfigurieren einer Topologie für Lync Server 2013 im Topologie-Generator](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in der Bereitstellungsdokumentation.

2.  Konfigurieren Sie in der Lync Server-Systemsteuerung das VoIP-Routing für die neue SIP-Domäne. Ausführliche Informationen finden Sie unter [Konfigurieren von Trunks in Lync Server 2013](lync-server-2013-configuring-trunks.md) in der Bereitstellungsdokumentation.

3.  Testen Sie die Konnektivität mithilfe des Cmdlets **Test-CsPstnOutboundCall**. Ausführliche Informationen finden Sie in der Dokumentation zur Lync Server-Verwaltungsshell oder in der Hilfe zur Lync Server-Verwaltungsshell.

