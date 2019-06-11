---
title: 'Lync Server 2013: Auswählen einer Topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa98d479ca2bfeaf6214bbd1e66bb3f41b09782
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Auswählen einer Topologie in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Letztes Änderungsdatum des Themas:** 2013-02-21_

Wenn Sie eine Topologie auswählen, können Sie eine der folgenden unterstützten Topologie-Optionen verwenden:

<div>


> [!NOTE]
> Wenn Sie über Erfahrungen mit Microsoft lync Server 2010 verfügen, finden Sie, sofern nicht anders angegeben, die Anleitungen hier weitgehend unverändert.



</div>

  - [Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.



</div>

In der folgenden Tabelle sind die Funktionen zusammengefasst, die mit den unterstützten Microsoft lync Server 2013-Topologien verfügbar sind. Die Spaltenüberschriften geben die Funktionalität an, die für eine bestimmte Edge-Konfigurationsoption verfügbar ist. Wenn Sie beispielsweise die Option skalierten Edge (DNS Load Balanced) verwenden, können Sie sehen, dass Sie eine hohe Verfügbarkeit unterstützt, nicht routingfähige private IP-Adressen (mit NAT) oder routingfähige öffentliche IP-Adressen verwenden, die den Edge-externen Schnittstellen zugewiesen sind, und die Kosten reduzieren, da eine das Hardware-Lastenausgleichsmodul ist nicht erforderlich.

Edge-Failover-Szenarien, die beim DNS-Lastenausgleich unterstützt werden, sind lync-zu-Punkt-Sitzungen, lync-Konferenzsitzungen, lync-zu-PSTN-Sitzungen und Office 365. Edge-Failover-Szenarien, die nicht vom DNS-Lastenausgleich profitieren, sind Failover für Remotebenutzer Exchange Unified Messaging (um) (vor Exchange 2010 SP1), öffentliche Instant Messaging (im)-Konnektivität und Verbund mit Servern, auf denen Office Communications ausgeführt wird. Server.

### <a name="summary-of-edge-server-topology-options"></a>Zusammenfassung der Optionen für die Edgeserver-Topologie

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
<th>Hochverfügbarkeit</th>
<th>Zusätzliche DNS-A-Einträge für externen Edgeserver im Edge-Pool erforderlich</th>
<th>Edge-Failover für lync-zu-lync-Sitzungen</th>
<th>Edge-Failover für lync-zu-lync-EUM/PIC/OCS-Verbund Sitzungen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Single Edge mit NAT</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Single Edge mit öffentlicher IP-Adresse</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Skalierte Kante (DNS Load Balanced) mithilfe von NAT</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Skalierter Edge (DNS Load Balanced) mit öffentlicher IP-Adresse</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Lastenausgleich für skalierte Edge-Hardware</p></td>
<td><p>Ja</p></td>
<td><p>Nein (ein DNS A-Eintrag pro VIP)</p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
</tr>
</tbody>
</table>


**\*** Failover für öffentliche Instant Messaging (im)-Konnektivität und Föderation mit Servern, auf denen Office Communications Server ausgeführt wird, ist im DNS-Lastenausgleich nicht verfügbar. Exchange um-Failover (Remotebenutzer) mithilfe des DNS-Lastenausgleichs erfordert Exchange Server 2010 SP1 oder höher.



> [!NOTE]
> Topologien mit einem Edge und einem skalierten Edge (DNS Load Balanced) können verwendet werden:
> <ul><li><p>Routingfähige öffentliche IP-Adressen</p></li>
> <li><p>Nicht routingfähige private IP-Adresse, wenn eine symmetrische Netzwerkadressübersetzung (Network Address Translation, NAT) verwendet wird</p></li>
>
> <ul><li> Wenn Sie die öffentliche IP-Adresse oder private IP-Adresse mit NAT verwenden, verwenden Sie weiterhin die gleiche Anzahl von IP-Adressen basierend auf Ihrer Konfigurationswahl im Topologie-Generator. Sie können den Edgeserver so konfigurieren, dass eine einzelne IP-Adresse mit unterschiedlichen Ports pro Dienst verwendet wird, oder Sie können unterschiedliche IP-Adressen pro Dienst verwenden, aber denselben Port verwenden (standardmäßig TCP 443).</li></ul>>
> Wenn Sie sich entschließen, nicht routingfähige private IP-Adressen mit NAT zu verwenden:
> <ul><li><p>Sie müssen routingfähige private IP-Adressen für alle drei externen Schnittstellen verwenden.</p></li>
> <li><p>Sie müssen symmetrische NAT für eingehenden und ausgehenden Datenverkehr konfigurieren.</p></li></ul>>
> Die Topologie für skalierte Kanten (Hardwarelastenausgleich) muss öffentliche IP-Adressen verwenden.



Lync Server 2013 unterstützt das Platzieren von Access-, Webkonferenz-und a/V-Edge-externen Schnittstellen hinter einem Router oder einer Firewall, die Netzwerkadressübersetzung (Network Address Translation, NAT) sowohl für einzelne als auch für skalierte konsolidierte Edge-Server-Topologien ausführt.

Die Verwendung von NAT für alle externen Edge-Schnittstellen erfordert die Verwendung des DNS-Lastenausgleichs. Im Vergleich zur Verwendung von Hardwarelastenausgleichs können Sie mithilfe des DNS-Lastenausgleichs ohne NAT die Anzahl der öffentlichen IP-Adressen pro Edgeserver in einem Edge-Pool reduzieren, wie in der folgenden Liste beschrieben:

  - Der von lync Server 2013 skalierte konsolidierte Edge (DNS Load Balanced) erfordert drei öffentliche IP-Adressen für jeden Edgeserver in einem Edge-Pool.

  - Der von lync Server 2013 skalierte konsolidierte Edge (Hardwarelastenausgleich) erfordert drei öffentliche IP-Adressen für virtuelle IP-Adressen des Lastenausgleichs (eine einmalige Anforderung, die nicht inkrementiert, wenn dem Pool weitere Edgeserver hinzugefügt werden) sowie drei öffentliche IP-Adressen pro Edgeserver in einem Pool.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>IP-Adressen Anforderungen für den skalierten konsolidierten Edge (IP-Adresse pro Rolle)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anzahl der Edgeserver pro Pool</th>
<th>Anzahl der erforderlichen IP-Adressen lync Server 2013 (DNS Load Balanced)</th>
<th>Anzahl der erforderlichen IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>6</p></td>
<td><p>3 (1 pro VIP) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>9</p></td>
<td><p>3 (1 pro VIP) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3 (1 pro VIP) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>15</p></td>
<td><p>3 (1 pro VIP) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>IP-Adressen Anforderungen für skalierten konsolidierten Edge (einzelne IP-Adresse für alle Rollen)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anzahl der Edgeserver pro Pool</th>
<th>Anzahl der erforderlichen IP-Adressen lync Server 2013 (DNS Load Balanced)</th>
<th>Anzahl der erforderlichen IP-Adressen lync Server 2013 (Hardwarelastenausgleich)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>2</p></td>
<td><p>1 (1 pro VIP) + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1 (1 pro VIP) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>4</p></td>
<td><p>1 (1 pro VIP) + 4</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>5</p></td>
<td><p>1 (1 pro VIP) + 5</p></td>
</tr>
</tbody>
</table>


Die primären Entscheidungspunkte für die Topologie-Auswahl sind hohe Verfügbarkeit und Lastenausgleich. Die Voraussetzung für hohe Verfügbarkeit kann die Entscheidung über den Lastenausgleich beeinflussen.

  - **Höhere Verfügbarkeit**   Wenn Sie eine höhere Verfügbarkeit benötigen, müssen Sie mindestens zwei Edgeserver in einem Pool bereitstellen. Ein einzelner Edge-Pool unterstützt bis zu zwölf Edge-Server. Wenn mehr Kapazität erforderlich ist, können Sie mehrere Edge-Pools bereitstellen. In der Regel benötigen 10% einer bestimmten Nutzerbasis externen Zugriff.
    
    <div>
    

    > [!IMPORTANT]
    > Mit dem Topology Builder können Sie bis zu zwanzig Edgeserver in einem einzigen Edge-Pool konfigurieren. Die getestete und unterstützte maximale Anzahl von Edgeserver in einem Pool ist zwölf, und der Topologie-Generator, der eine Zahl größer als zwölf zulässt, sollte nicht als implizierte Unterstützung für mehr als zwölf Edgeserver in einem einzigen Edge-Pool ausgelegt werden.

    
    </div>

  - **Hardware Lastenausgleich**   Der Hardware Lastenausgleich wird für den Lastenausgleich von lync Server 2013-Edgeserver unterstützt, wenn öffentlich routingfähige IP-Adressen für die externen Edge-Schnittstellen verwendet werden. Diese Vorgehensweise wird beispielsweise in Situationen verwendet, in denen ein Failover für eine der folgenden Anwendungen erforderlich ist:
    
      - Verbindung mit öffentlichen Chatdiensten
    
      - Föderation mit Unternehmen, auf denen Microsoft Office Communications Server 2007 oder Microsoft Office Communications Server 2007 R2 ausgeführt wird
    
      - Externer Zugriff auf Exchange 2007 Unified Messaging (um) oder Exchange 2010 um
        
        <div>
        

        > [!IMPORTANT]
        > Der DNS-Lastenausgleich für Exchange 2010 SP1 und höher wird für Exchange um unterstützt.

        
        </div>
    
    Diese drei Anwendungen funktionieren weiterhin, sind aber nicht für den DNS-Lastenausgleich bekannt und stellen nur eine Verbindung mit dem ersten Edgeserver im Pool her. Wenn dieser Server nicht verfügbar ist, schlägt die Verbindung fehl. Wenn beispielsweise mehrere Edgeserver in einem Pool bereitgestellt werden, um die Auslastung des Federated-Datenverkehrs zu behandeln, erhält nur ein Zugriffsproxy tatsächlich Datenverkehr, während die anderen Server im Leerlauf sind.

<div>


> [!IMPORTANT]
> Die Verwendung des DNS-Lastenausgleichs wird empfohlen, wenn Sie mit Unternehmen zusammenarbeiten, die lync Server 2010 und Microsoft Office 365 verwenden. Beachten Sie, dass es erhebliche Auswirkungen auf die Leistung gibt, wenn die meisten ihrer Verbundpartner Office Communications Server 2007 oder Office Communications Server 2007 R2 verwenden.



</div>

</div>

<span> </span>

</div>

</div>

</div>

