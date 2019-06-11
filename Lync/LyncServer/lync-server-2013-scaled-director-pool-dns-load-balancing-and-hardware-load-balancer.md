---
title: Skalierter Directorpool – DNS-Lastenausgleich und Hardwarelastenausgleich
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cd92304ca3a1147737958ad9d9fc94a49b2e5e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Skalierter Directorpool – DNS-Lastenausgleich und Hardwarelastenausgleich in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Ein skalierten Director-Pool, in dem mehr als ein Director zur Behandlung zusätzlicher Kapazität bereitgestellt wird und eine hohe Verfügbarkeit bereitgestellt wird, erfordert Lastenausgleich, um die Client-und Server Kommunikation an alle Mitglieder des Pools zu verteilen. Ein Director hostet Webdienste ähnlich wie ein Front-End-Pool. Um den Lastenausgleich bereitzustellen, können Sie entweder den Hardwarelastenausgleich oder den Lastenausgleich für DNS (Domain Name System) oder den Hardwarelastenausgleich verwenden. Für die Webdienste ist ein Hardware Lastenausgleich erforderlich, und allein der DNS-Lastenausgleich bietet nicht die für die Webdienste erforderlichen Funktionen.

In den folgenden Themen werden die Planungsüberlegungen zum Bereitstellen eines Director-Pools mithilfe des DNS-Lastenausgleichs in Verbindung mit dem Hardwarelastenausgleich beschrieben. Wenn Sie beabsichtigen, den Hardwarelastenausgleich, aber nicht den DNS-Lastenausgleich für den Director-Pool zu verwenden, lesen Sie das Thema [skalierten Director-Pool – Hardwarelastenausgleich in lync Server 2013, in](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) dem die Planungsanforderungen für diese Topologie beschrieben sind.

![Skalierter Director-Pool] (images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Skalierter Director-Pool")

<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Zertifikatzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Portzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [DNS-Zusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

