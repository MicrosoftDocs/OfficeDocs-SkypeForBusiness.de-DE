---
title: 'Lync Server 2013: Auswählen einer Topologie'
TOCTitle: Auswählen einer Topologie
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425716(v=OCS.15)
ms:contentKeyID: 49293434
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Auswählen einer Topologie in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der Auswahl einer Topologie können Sie eine der folgenden unterstützten Optionen verwenden:


> [!NOTE]
> Wenn Sie bereits Erfahrung mit Microsoft Lync Server 2010 haben, werden Sie feststellen, dass die meisten Schritte im Vergleich zur Vorgängerversion unverändert sind, sofern nicht anders angegeben.



  - [Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen und NAT in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Skalierter konsolidierter Edgeserver mit Hardwarelastenausgleich in Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)


> [!IMPORTANT]
> Für die interne Edgeschnittstelle und die externe Edgeschnittstelle muss derselbe Typ von Lastenausgleich verwendet werden. Es ist nicht möglich, für eine Edgeschnittstelle den DNS-Lastenausgleich und für die andere Edgeschnittstelle ein Hardwaregerät zum Lastenausgleich zu verwenden.



In der folgenden Tabelle wird beschrieben, welche Funktionalität für die von Microsoft Lync Server 2013 unterstützten Topologien zur Verfügung steht. Die Spaltenüberschriften geben die Funktionalität an, die für eine bestimmte Edgekonfigurationsoption zur Verfügung steht. Beispielsweise ist für die skalierte Edgetopologie (DNS-Lastenausgleich) angegeben, dass sie hohe Verfügbarkeit unterstützt, nicht routingfähige private IP-Adressen (mit NAT) oder routingfähige öffentliche IP-Adressen verwenden kann, die externen Edgeschnittstellen zugewiesen sind, und die Kosten senkt, da kein Hardwaregerät zum Lastenausgleich erforderlich ist.

Unterstützte Edgefailoverszenarien mit DNS-Lastenausgleich umfassen Punkt-zu-Punkt-Sitzungen zwischen Lync und Lync, Lync-Konferenzsitzungen, Lync-zu-Telefonfestnetz-Sitzungen und Office 365. Edgefailoverszenarien, die keinen DNS-Lastenausgleich verwenden, umfassen Failoverszenarien für Remotebenutzer ( Exchange Unified Messaging (UM) vor Exchange 2010 mit SP1), Verbindungen mit öffentlichen Chatdiensten und einen Partnerverbund mit Servern, auf denen Office Communications Server ausgeführt wird.

### Zusammenfassung der Topologieoptionen für Edgeserver

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
<th>Edgefailover für Lync-zu- Lync-Sitzungen</th>
<th>Edgefailover für EUM/PIC/OCS-Verbundsitzungen zwischen Lync und Lync</th>
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


**\*** Failover für Verbindungen mit öffentlichen Chatdiensten und Partnerverbund mit Servern, auf denen Office Communications Server nicht mit DNS-Lastenausgleich verfügbar ist. Das Failover für Exchange UM (Remotebenutzer) mit DNS-Lastenausgleich erfordert Exchange Server 2010 Support Package 1 oder neuer.

> [!NOTE]  
> Für Topologien mit einem einzelnen Edgeserver und mit einem skalierten Edgeserver (mit DNS-Lastenausgleich) kann Folgendes verwendet werden:
> <ul>
> <li><p>Routingfähige öffentliche IP-Adressen</p></li>
> <li><p>Nicht-routingfähige private IP-Adresse, wenn die symmetrische Netzwerkadressenübersetzung (Network Address Translation, NAT) verwendet wird</p></li></ul>   
>
   > Bei Verwendung einer öffentlichen oder privaten IP-Adresse mit NAT, verwenden Sie weiterhin dieselbe Anzahl an IP-Adressen basierend auf Ihrer Konfigurationsauswahl im Topologie-Generator. Sie können den Edgeserver entweder für die Verwendung einer einzelnen IP-Adresse mit unterschiedlichen Ports für Dienste konfigurieren oder unterschiedliche IP-Adressen für Dienste mit demselben Port (standardmäßig TCP&nbsp;443) verwenden.
>
> Wenn Sie sich für die Verwendung von nicht-routingfähigen privaten IP-Adressen mit NAT entscheiden:
> 
> <ul><li><p>Sie müssen routingfähige private IP-Adressen für alle drei externen Schnittstellen verwenden.</p></li>
> <li><p>Sie müssen ein symmetrisches NAT-Gerät für eingehenden und ausgehenden Datenverkehr konfigurieren.</p></li></ul>
> 
> Für eine Topologie mit skaliertem Edgeserver (mit Hardwarelastenausgleich) müssen öffentliche IP-Adressen verwendet werden.


Lync Server 2013 unterstützt das Platzieren von externen Zugriffs-, Webkonferenz- und A/V-Edgeschnittstellen hinter einem Router oder einer Firewall, die eine Netzwerkadressenübersetzung (NAT) für Topologien mit einzelnen sowie skalierten und konsolidierten Edgeservern durchführen.

Bei Verwendung der Netzwerkadressenübersetzung für alle externen Edgeschnittstellen muss der DNS-Lastenausgleich implementiert werden. Im Vergleich mit der Verwendung eines Hardwarelastenausgleichs ermöglicht die Verwendung von DNS-Lastenausgleich die Reduzierung der Anzahl von öffentlichen IP-Adressen pro Edgeserver in einem Edgepool, wie in der folgenden Liste beschrieben:

  - Lync Server 2013 Skalierte konsolidierte Edgetopologie (DNS-Lastenausgleich)   Erfordert drei öffentliche IP-Adressen für jeden Edgeserver in einem Edgepool.

  - Lync Server 2013 Skalierte konsolidierte Edgetopologie (Hardwarelastenausgleich)   Erfordert drei öffentliche IP-Adressen für die virtuellen IP-Adressen des Hardwaregeräts zum Lastenausgleich (diese einmalige Anforderung bleibt beim Hinzufügen weiterer Edgeserver zum Pool unverändert) sowie drei öffentliche IP-Adressen pro Edgeserver in einem Pool.

### IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (IP-Adresse pro Rolle)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anzahl von Edgeservern pro Pool</th>
<th>Anzahl erforderlicher IP-Adressen Lync Server 2013 (DNS-Lastenausgleich)</th>
<th>Anzahl von erforderlichen IP-Adressen für Lync Server 2013 (Hardwarelastenausgleich)</th>
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


### IP-Adressanforderungen für eine skalierte konsolidierte Edgetopologie (eine IP-Adresse für alle Rollen)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Anzahl von Edgeservern pro Pool</th>
<th>Anzahl erforderlicher IP-Adressen Lync Server 2013 (DNS-Lastenausgleich)</th>
<th>Anzahl von erforderlichen IP-Adressen für Lync Server 2013 (Hardwarelastenausgleich)</th>
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


Die wichtigsten Aspekte bei der Topologieauswahl sind hohe Verfügbarkeit und Lastenausgleich. Die Anforderung zur Bereitstellung hoher Verfügbarkeit kann sich auf die Entscheidung zum Lastenausgleich auswirken.

  - **Hohe Verfügbarkeit**   Wenn Sie hohe Verfügbarkeit sicherstellen müssen, stellen Sie mindestens zwei Edgeserver in einem Pool bereit. Ein einzelner Edgepool kann bis zu zwölf Edgeserver unterstützen. Wenn mehr Kapazität benötigt wird, können Sie mehrere Edgepools bereitstellen. Als allgemeine Regel benötigen 10 % der Benutzer externen Zugriff.
    

    > [!IMPORTANT]
    > Der Topologie-Generator ermöglicht Ihnen das Konfigurieren von bis zu 20&nbsp; Edgeservern in einem Edgepool. Die getestete und unterstützte maximale Anzahl von Edgeservern in einem Pool ist zwölf. Lässt der Topologie-Generator eine höhere Anzahl zu, darf trotzdem nicht davon ausgegangen werden, dass mehr als zwölf&nbsp; Edgeserver in einem Edgepool unterstützt werden.



  - **Hardwarelastenausgleich**   Der Hardwarelastenausgleich wird zum Lastenausgleich für Lync Server 2013- Edgeserver verwendet, wenn öffentlich routingfähige IP-Adressen für die externen Edgeschnittstellen verwendet werden. Beispielsweise würden Sie diesen Ansatz in Situationen wählen, in denen ein Failover für eine der folgenden Anwendungen erforderlich ist:
    
      - Verbindung mit öffentlichen Instant Messaging-Diensten
    
      - Partnerverbund mit Unternehmen, die Microsoft Office Communications Server 2007 oder Microsoft Office Communications Server 2007 R2 ausführen
    
      - Externer Zugriff auf Exchange 2007 Unified Messaging (UM) oder Exchange 2010 UM
        

        > [!IMPORTANT]
        > DNS-Lastenausgleich für Exchange 2010 SP1 und neuer wird unterstützt für Exchange UM.

    
    Diese drei Anwendungen funktionieren weiterhin, bieten jedoch keine Unterstützung für den DNS-Lastenausgleich und stellen nur eine Verbindung mit dem ersten Edgeserver im Pool her. Wenn dieser Server nicht verfügbar ist, kann keine Verbindung hergestellt werden. Wenn beispielsweise mehrere Edgeserver in einem Pool bereitgestellt werden, um den Datenverkehr für den Partnerverbund zu verarbeiten, empfängt nur ein Zugriffsproxy Daten, während die anderen Proxys sich im Leerlauf befinden.


> [!IMPORTANT]
> Die Verwendung des DNS-Lastenausgleichs wird empfohlen, wenn Sie einen Partnerverbund mit Unternehmen eingerichtet haben, die Lync Server 2010 und Microsoft Office 365 ausführen. Bedenken Sie, dass es zu erheblichen Auswirkungen auf die Leistung kommt, wenn Ihre Verbundpartner Office Communications Server 2007 oder Office Communications Server 2007 R2 verwenden.


