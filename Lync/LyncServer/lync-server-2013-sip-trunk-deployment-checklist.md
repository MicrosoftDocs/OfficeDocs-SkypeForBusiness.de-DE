---
title: 'Lync Server 2013: Prüfliste für SIP-Trunk Bereitstellung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunk deployment checklist
ms:assetid: 94f4f03e-19d5-4198-92be-e4076dbb959a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398755(v=OCS.15)
ms:contentKeyID: 48184891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09c9916be9b32eb4a1fb0a5981cc6769bafc3420
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519702"
---
# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Prüfliste für SIP-Trunk Bereitstellung für lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-21_

Bevor Sie einen SIP-Trunk bereitstellen können, müssen Sie und Ihr Dienstanbieter einige grundlegende Verbindungsinformationen zu ihren jeweiligen Endpunkten des SIP-Trunks austauschen.

Für jedes ITSP-Gateway, mit dem Sie eine Verbindung herstellen, benötigen Sie die folgenden Informationen:

  - IP-Adresse

  - Vollqualifizierter Domänenname (FQDN)

<div>


> [!NOTE]  
> Der Dienstanbieter bittet Sie möglicherweise, eine Verbindung mit mehreren ITSP-Gateways herzustellen. In diesem Fall müssen Sie eine Verbindung zwischen jedem ITSP-Gateway und jedem Vermittlungsserver in Ihrem Pool konfigurieren.



</div>

Die Informationen, die Sie für Ihren Dienstanbieter bereitstellen, hängen vom Verbindungstyp Ihres SIP-Trunks ab:

  - Für MPLS (Multiprotocol Label Switching)- oder private Netzwerkverbindungen stellen Sie dem ITSP die öffentlich routingfähige IP-Adresse des Routers in Ihrem Umkreisnetzwerk (auch als Demilitarized Zone, DMZ, und überwachtes Subnetz bezeichnet) bereit. Stellen Sie sicher, dass diese Adresse vom Gateway oder Session Border Controller (SBC) auf der ITSP-Seite kontaktiert werden kann. Geben Sie dem ITSP auch den FQDN ihrer Vermittlungsserver.

  - Für VPN-Verbindungen (Virtual Private Network) teilen Sie dem ITSP die IP-Adresse Ihres VPN-Servers mit.

<div>

## <a name="certificate-considerations"></a>Überlegungen zu Zertifikaten

Fragen Sie Ihren ITSP nach den unterstützten Protokollen, um zu ermitteln, ob Sie ein Zertifikat für das SIP-Trunking benötigen:

1.  Wenn Ihr ITSP nur TCP unterstützt, benötigen Sie kein Zertifikat.

2.  Wenn Ihr ITSP Unterstützung für TLS (Transport Layer Security) bietet, muss Ihnen der ITSP ein Zertifikat bereitstellen.

<div>


> [!NOTE]  
> SIP wird mit RTP (Real-time Transport Protocol) oder SRTP (Secure Real-time Transport Protocol) eingesetzt, den Protokollen für die eigentlichen VoIP-Daten in VoIP-Anrufen.



</div>

</div>

<div>

## <a name="deployment-process"></a>Bereitstellungsprozess

Führen Sie die folgenden Schritte aus, um die lync Server Seite der SIP-trunkverbindung zu implementieren:

1.  Erstellen und konfigurieren Sie mithilfe des lync Server Topologie-Generators die SIP-Domänentopologie. Ausführliche Informationen finden Sie unter [definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in der Bereitstellungsdokumentation.

2.  Konfigurieren Sie mithilfe der lync Server-Systemsteuerung das VoIP-Routing für die neue SIP-Domäne. Ausführliche Informationen finden Sie unter [Configuring Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md) in der Bereitstellungsdokumentation.

3.  Testen Sie die Konnektivität mithilfe des Cmdlets **Test-CsPstnOutboundCall**. Ausführliche Informationen finden Sie in der lync Server-Verwaltungsshell Dokumentation oder in der Hilfe zu lync Server-Verwaltungsshell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

