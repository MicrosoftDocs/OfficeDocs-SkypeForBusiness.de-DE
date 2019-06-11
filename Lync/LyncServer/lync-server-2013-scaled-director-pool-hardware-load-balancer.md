---
title: 'Lync Server 2013: Skalierter Directorpool (Hardwarelastenausgleich)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0faf0983830466b44c91532f4fd80d72abb37fd7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822188"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a>Skalierter Directorpool (Hardwarelastenausgleich) in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-08_

Ein skalierten Director-Pool, in dem mehr als ein Director bereitgestellt wird, um zusätzliche Kapazität zu verarbeiten und hohe Verfügbarkeit bereitzustellen, erfordert Lastenausgleich, um die Client-und Server Kommunikation an alle Mitglieder des Pools zu verteilen. Ein Director hostet Webdienste ähnlich wie ein Front-End-Pool. Für die Webdienste ist ein Hardware Lastenausgleich erforderlich.

In den folgenden Themen werden die Planungsüberlegungen zum Bereitstellen eines Director-Pools mithilfe des Hardwarelastenausgleichs beschrieben. Wenn Sie beabsichtigen, den Hardwarelastenausgleich und den DNS-Lastenausgleich für den Director-Pool zu verwenden, lesen Sie das Thema [skalierten Director-Pool – DNS-Lastenausgleich und Hardwarelastenausgleich in lync Server 2013, in](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) dem die Planungsanforderungen für diese Topologie beschrieben sind.

![cfa892b9-5b24-4245-b5bd-c5da21984eeb] (images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikatzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Portzusammenfassung für einen skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [DNS-Übersicht für skalierten Directorpool (Hardwarelastenausgleich) in Lync Server 2013](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

