---
title: 'Lync Server 2013: Skalierter Directorpool – DNS-Lastenausgleich und Hardwarelastenausgleich'
TOCTitle: Skalierter Directorpool – DNS-Lastenausgleich und Hardwarelastenausgleich
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205142(v=OCS.15)
ms:contentKeyID: 49294947
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Skalierter Directorpool – DNS-Lastenausgleich und Hardwarelastenausgleich in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2012-10-22_

Für einen skalierten Directorpool, bei dem mehr als ein Director zum Verarbeiten zusätzlicher Kapazitäten und zum Bereitstellen einer hohen Verfügbarkeit bereitgestellt wird, muss der Lastenausgleich die Client- und Serverkommunikation auf alle Mitglieder des Pools verteilen. Ein Director hostet Webdienste genauso wie ein Front-End-Pool. Für die Bereitstellung des Lastenausgleichs können Sie entweder den Hardwarelastenausgleich oder DNS-Lastenausgleich (Domain Name System) und den Hardwarelastenausgleich verwenden. Der Hardwarelastenausgleich ist für die Webdienste erforderlich, und der DNS-Lastenausgleich allein bietet nicht die für Webdienste erforderlichen Funktionen.

In den folgenden Themen werden die Planungsaspekte zum Bereitstellen eines Directorpools mithilfe des DNS-Lastenausgleichs in Kombination mit dem Hardwarelastenausgleich beschrieben. Wenn Sie den Hardwarelastenausgleich ohne DNS-Lastenausgleich für den Directorpool verwenden möchten, lesen Sie die Informationen unter dem Thema [Skalierter Directorpool (Hardwarelastenausgleich) in Lync Server 2013](lync-server-2013-scaled-director-pool-hardware-load-balancer.md). Darin werden die Planungsanforderungen für diese Topologie beschrieben.

![Skalierter Directorpool](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "Skalierter Directorpool")

## In diesem Abschnitt

  - [Zertifikatzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Portzusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [DNS-Zusammenfassung für DNS- und Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

