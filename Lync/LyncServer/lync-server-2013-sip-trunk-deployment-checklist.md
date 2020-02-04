---
title: 'Lync Server 2013: Prüfliste für die Bereitstellung von SIP-Trunks'
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
ms.openlocfilehash: ef670fc4ae9e8a9acba3277a00fc0daf6ff766b3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunk-deployment-checklist-for-lync-server-2013"></a>Prüfliste für die Bereitstellung von SIP-Trunks für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-21_

Bevor Sie einen SIP-Trunk bereitstellen können, müssen Sie und Ihr Dienstanbieter einige grundlegende Verbindungsinformationen zu ihren jeweiligen SIP-Trunk-Endpunkten austauschen.

Rufen Sie die folgenden Informationen für jedes ITSP-Gateway ab, mit dem Sie eine Verbindung herstellen:

  - IP-Adresse

  - Vollständig qualifizierter Domänenname (FQDN)

<div>


> [!NOTE]  
> Der Dienstanbieter fordert Sie möglicherweise auf, mit mehr als einem ITSP-Gateway zu verbinden. In diesem Fall müssen Sie eine Verbindung zwischen jedem ITSP-Gateway und jedem Vermittlungs Server in Ihrem Pool konfigurieren.



</div>

Die Informationen, die Sie Ihrem Dienstanbieter geben, hängen von Ihrem SIP Trunk-Verbindungstyp ab:

  - Für Multiprotocol-Label-Switching (MPLS) oder private Netzwerkverbindungen geben Sie der ITSP die öffentlich routingfähige IP-Adresse des Routers in Ihrem Umkreisnetzwerk (auch bekannt als DMZ, demilitarisierte Zone und geschirmtes Subnetz). Überprüfen Sie, ob der Gateway-oder Session Border Controller (SBC) am ITSP diese Adresse erreichen kann. Geben Sie dem ITSP auch den FQDN Ihres Vermittlungsservers.

  - Geben Sie für VPN-Verbindungen (virtuelles privates Netzwerk) der ITSP die IP-Adresse Ihres VPN-Servers ein.

<div>

## <a name="certificate-considerations"></a>Überlegungen zu Zertifikaten

Wenn Sie feststellen möchten, ob Sie ein Zertifikat für SIP-Trunking benötigen, erkundigen Sie sich bei Ihrem ITSP zu Protokollunterstützung:

1.  Wenn Ihr ITSP nur TCP (Transmission Control Protocol) unterstützt, benötigen Sie kein Zertifikat.

2.  Wenn Ihr ITSP TLS (Transport Layer Security) unterstützt, muss Ihnen der ITSP ein Zertifikat zur Verfügung stellen.

<div>


> [!NOTE]  
> SIP funktioniert in Verbindung mit RTP (Real-Time Transport Protocol) oder SRTP (Secure Real-Time Transport Protocol), den Protokollen, die die eigentlichen Sprach Daten in VoIP-Anrufen (Voice over Internet Protocol) verwalten.



</div>

</div>

<div>

## <a name="deployment-process"></a>Bereitstellungsprozess

Führen Sie die folgenden Schritte aus, um die lync Server-Seite der SIP Trunk-Verbindung zu implementieren:

1.  Erstellen und konfigurieren Sie mithilfe des lync Server Topology Builder die SIP-Domänentopologie. Ausführliche Informationen finden Sie unter [definieren und Konfigurieren einer Topologie im Topologie-Generator für lync Server 2013](lync-server-2013-define-and-configure-a-topology-in-topology-builder.md) in der Bereitstellungsdokumentation.

2.  Konfigurieren Sie mithilfe der lync Server-Systemsteuerung das VoIP-Routing für die neue SIP-Domäne. Ausführliche Informationen finden Sie unter [Konfigurieren von Trunks in lync Server 2013](lync-server-2013-configuring-trunks.md) in der Bereitstellungsdokumentation.

3.  Testen Sie die Konnektivität mithilfe des Cmdlets **Test-CsPstnOutboundCall** . Ausführliche Informationen finden Sie in der Dokumentation zur lync Server-Verwaltungsshell oder in der Hilfe zur lync Server-Verwaltungsshell.

</div>

</div>

<span> </span>

</div>

</div>

</div>

