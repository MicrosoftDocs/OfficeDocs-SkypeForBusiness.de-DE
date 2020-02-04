---
title: 'Lync Server 2013: Konfigurieren von Trunks'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring trunks
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398170(v=OCS.15)
ms:contentKeyID: 48183389
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1021295b375e4f28294ffb1ca5738d651f9ced2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-trunks-in-lync-server-2013"></a>Konfigurieren von Trunks in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-11-01_

Im Rahmen der Enterprise-VoIP-Bereitstellung können Sie einen trunk zwischen einem Vermittlungs Server und einem oder mehreren der folgenden Peers konfigurieren, um die PSTN-Konnektivität (Public Switched Telephone Network) für Enterprise-VoIP-Clients und-Geräte in Ihrer Organisation bereitzustellen:

  - SIP-Trunkverbindung mit einem Anbieter von Internettelefoniediensten

  - PSTN-Gateway

  - Nebenstellenanlage (Private Branch Exchange, PBX)

Ausführliche Informationen finden Sie unter [Planen der PSTN-Konnektivität in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md) in der Planungsdokumentation.

<div>


> [!IMPORTANT]  
> Bevor Sie die trunk-Konfiguration beginnen, stellen Sie sicher, dass die Topologie erstellt wurde und dass der Vermittlungs Server und sein Peer konfiguriert und miteinander verknüpft wurden. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Definieren eines Gateways im Topologie-Generator in lync Server 2013</A> in der Bereitstellungsdokumentation.



</div>

<div>


> [!NOTE]  
> Als Teil der trunk-Konfiguration können Sie das lync Server 2013-Feature für die medienumgehung aktivieren, mit dem Medien den Vermittlungs Server umgehen können. Trunks kann entweder mit oder ohne aktivierte medienumgehung konfiguriert werden, wir empfehlen jedoch dringend, diese zu aktivieren. Ausführliche Informationen finden Sie unter <A href="lync-server-2013-planning-for-media-bypass.md">Planen der medienumgehung in lync Server 2013</A> in der Planungsdokumentation.



</div>

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Mehrere trunk-Unterstützung in lync Server 2013](lync-server-2013-multiple-trunk-support.md)

  - [Zwischen trunk-Routing in lync Server 2013](lync-server-2013-inter-trunk-routing.md)

  - [Anzeigen von trunk-Konfigurationsinformationen in lync Server 2013](lync-server-2013-view-trunk-configuration-information.md)

  - [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [Konfigurieren eines Trunks ohne medienumgehung in lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [Erstellen einer neuen Sammlung von trunk-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [Löschen einer vorhandenen Sammlung von SIP-Trunk-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [Ändern der SIP-Trunk-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [Testen der SIP-Trunk-Konfigurationseinstellungen in lync Server 2013](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [Anzeigen von Informationen zu einzelnen SIP-Stämmen in lync Server 2013](lync-server-2013-view-information-about-individual-sip-trunks.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Definieren eines Gateways im Topologie-Generator in lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)  


[Planen der PSTN-Konnektivität in lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md)  
[Planung der Medienumgehung in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

