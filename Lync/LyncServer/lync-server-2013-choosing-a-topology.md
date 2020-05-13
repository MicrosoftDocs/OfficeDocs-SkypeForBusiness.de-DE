---
title: 'Lync Server 2013: Auswählen einer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a75e1e829b59ff66df6b598c63b35f2f78981e4
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Auswählen einer Topologie in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Letztes Änderungsstand des Themas:** 2013-02-21_

Bei der Auswahl einer Topologie können Sie eine der folgenden unterstützten Optionen verwenden:

<div>


> [!NOTE]
> Wenn Sie Erfahrung mit Microsoft lync Server 2010 haben, werden Sie, sofern nicht anders angegeben, die Anleitung hier weitgehend unverändert finden.



</div>

  - [Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleichssystemen in lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.



</div>

In der folgenden Tabelle sind die Funktionen zusammengefasst, die mit den unterstützten Microsoft lync Server 2013 Topologien verfügbar sind. Die Spaltenüberschriften geben die Funktionalität an, die für eine bestimmte Edgekonfigurationsoption zur Verfügung steht. Beispielsweise ist für die skalierte Edgetopologie (DNS-Lastenausgleich) angegeben, dass sie hohe Verfügbarkeit unterstützt, nicht routingfähige private IP-Adressen (mit NAT) oder routingfähige öffentliche IP-Adressen verwenden kann, die externen Edgeschnittstellen zugewiesen sind, und die Kosten senkt, da kein Hardwaregerät zum Lastenausgleich erforderlich ist.

Unterstützte Edge-Failover-Szenarien bei DNS-Lastenausgleich sind lync-to-lync-Punkte-zu-Ort-Sitzungen, lync-Konferenzsitzungen, lync-zu-PSTN-Sitzungen, Office 365 und Microsoft 365. Edge-Failover-Szenarien, die nicht vom DNS-Lastenausgleich profitieren, sind Failover für Remotebenutzer Exchange Unified Messaging (um) (vor Exchange 2010 SP1), die Verbindung mit öffentlichen Instant Messaging-Verbindungen und den Verbund mit Servern, auf denen Office Communications Server läuft.

### <a name="summary-of-edge-server-topology-options"></a>Zusammenfassung der Topologieoptionen für Edgeserver

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Topologie</th>
<th>Hohe Verfügbarkeit</th>
<th>Zusätzliche DNS-A-Einträge für externe Edgeserver im Edgepool erforderlich</th>
<th>Edge-Failover für lync-zu-lync-Sitzungen</th>
<th>Edge-Failover für lync-zu-lync-EUM/PIC/OCS-Verbund Sitzungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Einzelner Edgeserver mit Netzwerkadressenübersetzung (Network Address Translation, NAT)</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Einzelner Edgeserver mit öffentlicher IP-Adresse</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Skalierter Edgeserver (DNS-Lastenausgleich) mit NAT</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Skalierter Edgeserver (DNS-Lastenausgleich) mit öffentlicher IP-Adresse</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Skalierter Edgeserver (Hardwarelastenausgleich)</p></td>
<td><p>Ja</p></td>
<td><p>Nein (ein DNS A-Eintrag pro VIP)</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
</tr>
</tbody>
</table>


**\*** Failover für die Verbindung mit öffentlichen Instant Messaging-Verbindungen und Verbund mit Servern mit Office Communications Server ist mit dem DNS-Lastenausgleich nicht verfügbar. Für Exchange um (Remotebenutzer)-Failover mithilfe des DNS-Lastenausgleichs ist Exchange Server 2010 SP1 oder höher erforderlich.



> [!NOTE]
> Für Topologien mit einem einzelnen Edgeserver und mit einem skalierten Edgeserver (mit DNS-Lastenausgleich) kann Folgendes verwendet werden:
> <ul><li><p>Routingfähige öffentliche IP-Adressen</p></li>
> <li><p>Nicht routingfähige private IP-Adresse, wenn die symmetrische Netzwerkadressübersetzung (NAT) verwendet wird</p></li>
>
> <ul><li> Wenn Sie die öffentliche IP-Adresse oder private IP-Adresse mit NAT verwenden, verwenden Sie weiterhin die gleiche Anzahl von IP-Adressen basierend auf Ihrer Konfigurationsoption im Topologie-Generator. Sie können die Edgeserver so konfigurieren, dass eine einzelne IP-Adresse mit verschiedenen Ports pro Dienst verwendet wird, oder Sie verwenden unterschiedliche IP-Adressen pro Dienst, verwenden jedoch denselben Port (standardmäßig TCP 443).</li></ul>>
> Wenn Sie sich für die Verwendung von nicht routingfähigen privaten IP-Adressen mit NAT entscheiden:
> <ul><li><p>Sie müssen routingfähige private IP-Adressen für alle drei externen Schnittstellen verwenden.</p></li>
> <li><p>Sie müssen ein symmetrisches NAT-Gerät für eingehenden und ausgehenden Datenverkehr konfigurieren.</p></li></ul>>
> Für eine Topologie mit skaliertem Edgeserver (mit Hardwarelastenausgleich) müssen öffentliche IP-Adressen verwendet werden.



Lync Server 2013 unterstützt das Platzieren von Zugriffs-, Webkonferenz-und a/V-Edge-Schnittstellen hinter einem Router oder einer Firewall, die Netzwerkadressübersetzung (Network Address Translation, NAT) für einzelne und skalierte konsolidierte Edgeserver Topologien ausführt.

Bei Verwendung der Netzwerkadressenübersetzung für alle externen Edgeschnittstellen muss der DNS-Lastenausgleich implementiert werden. Im Vergleich mit der Verwendung eines Hardwarelastenausgleichs ermöglicht die Verwendung von DNS-Lastenausgleich die Reduzierung der Anzahl von öffentlichen IP-Adressen pro Edgeserver in einem Edgepool, wie in der folgenden Liste beschrieben:

  - Lync Server 2013 skalierter konsolidierter Edgeserver (DNS-Lastenausgleich) erfordert drei öffentliche IP-Adressen für jeden Edgeserver in einem Edgepool.

  - Lync Server 2013 skalierten konsolidierten Edgeserver (Hardwarelastenausgleich) erfordert drei öffentliche IP-Adressen für die virtuellen IP-Adressen des Lastenausgleichs (eine einmalige Anforderung, die nicht erhöht wird, wenn dem Pool weitere Edgeserver hinzugefügt werden) sowie drei öffentliche IP-Adressen pro Edgeserver in einem Pool.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (IP-Adresse pro Rolle)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anzahl von Edgeservern pro Pool</th>
<th>Anzahl erforderlicher IP-Adressen lync Server 2013 (DNS-Lastenausgleich)</th>
<th>Anzahl erforderlicher IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>6 </p></td>
<td><p>3 (1 pro VIP) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9 </p></td>
<td><p>3 (1 pro VIP) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>12 </p></td>
<td><p>3 (1 pro VIP) + 12</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>15 </p></td>
<td><p>3 (1 pro VIP) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (eine IP-Adresse für alle Rollen)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anzahl von Edgeservern pro Pool</th>
<th>Anzahl erforderlicher IP-Adressen lync Server 2013 (DNS-Lastenausgleich)</th>
<th>Anzahl erforderlicher IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2 </p></td>
<td><p>2 </p></td>
<td><p>1 (1 pro VIP) + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1 (1 pro VIP) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4 </p></td>
<td><p>4 </p></td>
<td><p>1 (1 pro VIP) + 4</p></td>
</tr>
<tr class="even">
<td><p>5 </p></td>
<td><p>5</p></td>
<td><p>1 (1 pro VIP) + 5</p></td>
</tr>
</tbody>
</table>


Die wichtigsten Aspekte bei der Topologieauswahl sind hohe Verfügbarkeit und Lastenausgleich. Die Anforderung zur Bereitstellung hoher Verfügbarkeit kann sich auf die Entscheidung zum Lastenausgleich auswirken.

  - **Hohe Verfügbarkeit**   Wenn Sie hohe Verfügbarkeit benötigen, stellen Sie mindestens zwei Edgeserver in einem Pool bereit. Bei einem einzelnen Edgepool werden bis zu zwölf Edgeserver unterstützt. Wenn mehr Kapazität benötigt wird, können Sie mehrere Edgepools bereitstellen. Als allgemeine Regel benötigen 10% der Benutzer externen Zugriff.
    
    <div>
    

    > [!IMPORTANT]
    > Mit dem Topologie-Generator können Sie bis zu zwanzig Edgeserver in einem einzigen Edgepool konfigurieren. Die getestete und unterstützte maximale Anzahl von Edgeserver in einem Pool ist zwölf, und der Topologie-Generator, der eine Zahl größer als zwölf zulässt, sollte nicht als implizierte Unterstützung für mehr als zwölf Edgeserver in einem einzigen Edgepool ausgelegt werden.

    
    </div>

  - **Hardware Lastenausgleich**   Hardware Lastenausgleich wird für den Lastenausgleich lync Server 2013 Edgeserver unterstützt, wenn öffentlich routingfähige IP-Adressen für die externen Edge-Schnittstellen verwendet werden. Beispielsweise würden Sie diesen Ansatz in Situationen wählen, in denen ein Failover für eine der folgenden Anwendungen erforderlich ist:
    
      - Verbindung mit öffentlichen Instant Messaging-Diensten
    
      - Partnerverbund mit Microsoft Office Communications Server 2007 oder Microsoft Office Communications Server 2007 R2 ausführenden Unternehmen
    
      - Externer Zugriff auf Exchange 2007 Unified Messaging (UM) oder Exchange 2010 UM
        
        <div>
        

        > [!IMPORTANT]
        > Der DNS-Lastenausgleich für Exchange 2010 SP1 und neuer wird für Exchange um unterstützt.

        
        </div>
    
    Diese drei Anwendungen funktionieren weiterhin, bieten jedoch keine Unterstützung für den DNS-Lastenausgleich und stellen nur eine Verbindung mit dem ersten Edgeserver im Pool her. Wenn dieser Server nicht verfügbar ist, kann keine Verbindung hergestellt werden. Wenn beispielsweise mehrere Edgeserver in einem Pool bereitgestellt werden, um den Datenverkehr für den Partnerverbund zu verarbeiten, empfängt nur ein Zugriffsproxy Daten, während die anderen Proxys sich im Leerlauf befinden.

<div>


> [!IMPORTANT]
> Die Verwendung des DNS-Lastenausgleichs wird empfohlen, wenn Sie mit lync Server 2010 und Office 365 oder Microsoft 365 einen Verbund mit Unternehmen durchsetzen. Beachten Sie, dass erhebliche Leistungseinbußen zu verzeichnen sind, wenn die meisten Verbundpartner Office Communications Server 2007 oder Office Communications Server 2007 R2 verwenden.



</div>

</div>

<span> </span>

</div>

</div>

</div>

