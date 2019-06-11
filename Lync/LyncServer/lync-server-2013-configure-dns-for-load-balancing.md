---
title: 'Lync Server 2013: Konfigurieren von DNS für den Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e370d3b66e82b02bd5668fc1c9cab4ee41da759
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Konfigurieren von DNS für den Lastenausgleich in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Um dieses Verfahren erfolgreich durchführen zu können, sollten Sie am Server oder in der Domäne minimal als Mitglied der Gruppe der Domänenadministratoren oder als Mitglied der DnsAdmins-Gruppe angemeldet sein.

Der DNS-Lastenausgleich (Domain Name System) balanciert den Netzwerkdatenverkehr aus, der für lync Server 2013 eindeutig ist, wie etwa SIP-Datenverkehr und Mediendatenverkehr. Der DNS-Lastenausgleich wird für Front-End-Pools, Edge-Pools, Director-Pools und eigenständige Vermittlungs Pools unterstützt. Für einen Pool, der für die Verwendung des DNS-Lastenausgleichs konfiguriert ist, müssen zwei vollqualifizierte Domänennamen (FQDNs) definiert sein: der reguläre Pool-FQDN, der vom DNS-Lastenausgleich verwendet wird (beispielsweise pool1.contoso.com) und der auf die physischen IPS der Server im Pool aufgelöst wird. und einen weiteren FQDN für die Webdienste des Pools (beispielsweise web1.contoso.net), der in die virtuelle IP-Adresse des Pools aufgelöst wird. Details zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

<div>


> [!NOTE]  
> Für den HTTPS-Datenverkehr zwischen Client und Server ist weiterhin Hardware Lastenausgleich erforderlich.



</div>

Bevor Sie den DNS-Lastenausgleich verwenden können, müssen Sie die folgenden Schritte ausführen:

1.  Überschreiben Sie den internen FQDN des Webdienste-Pools.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie beschließen, die internen Webdienste mit einem selbst definierten FQDN zu überschreiben, muss jeder FQDN für jeden anderen Front-End-Pool, Director oder Director-Pool eindeutig sein.

    
    </div>

2.  Erstellen Sie DNS-A-Hosteinträge, um den FQDN des Pools in die IP-Adressen aller Server im Pool aufzulösen.

3.  Aktivieren Sie die zufällige IP-Adresse, oder aktivieren Sie für Windows Server-DNS Round Robin.
    
    <div>
    

    > [!NOTE]  
    > Round Robin sollte standardmäßig aktiviert sein.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>So heben Sie den internen FQDN von Webdiensten auf

1.  Starten Sie den Topologie-Generator: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topology Builder**.

2.  Erweitern Sie in der Konsolenstruktur den Knoten Enterprise Edition-Front-End-Pools.

3.  Klicken Sie mit der rechten Maustaste auf den Pool, klicken Sie auf **** **Eigenschaften bearbeiten**, und klicken Sie dann auf Webdienste.

4.  Aktivieren Sie unter **interne**Webdienste das Kontrollkästchen **FQDN überschreiben** .

5.  Geben Sie den FQDN des Pools ein, der in die physischen IP-Adressen der Server im Pool aufgelöst wird.

6.  Geben Sie unter **externe**Webdienste den FQDN des externen Pools ein, der in die virtuellen IP-Adressen des Pools aufgelöst wird, und klicken Sie dann auf **OK**.

7.  Klicken Sie in der Konsolenstruktur auf **lync Server 2013**, und klicken Sie dann im Bereich **Aktionen** auf **Topologie veröffentlichen**.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>So erstellen Sie DNS-Host Einträge (A) für alle internen Pool Server

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

2.  Klicken Sie im **DNS-Manager**auf den DNS-Server, der Ihre Datensätze verwaltet, um Sie zu erweitern.

3.  Klicken Sie auf **Forward-Lookupzonen** , um Sie zu erweitern.

4.  Klicken Sie mit der rechten Maustaste auf die DNS-Domäne, der Sie Datensätze hinzufügen müssen, und klicken Sie dann auf **neuer Host (A oder AAAA)**.

5.  Geben Sie im Feld **Name** den Namen des Hosteintrags ein (der Domänenname wird automatisch angehängt).

6.  Geben Sie im Feld IP-Adresse die IP-Adresse des einzelnen Front-End-Servers ein, und wählen Sie dann **zugehörigen Zeigereintrag erstellen** aus, oder **ermöglichen Sie es jedem authentifizierten Benutzer, DNS-Einträge mit demselben Besitzernamen zu aktualisieren**, sofern zutreffend.

7.  Erstellen Sie weiterhin Datensätze für alle Member-Front-End-Server, die am DNS-Lastenausgleich beteiligt sind.
    
    Wenn Sie beispielsweise über einen Pool mit dem Namen pool1.contoso.com und drei Front-End-Server verfügen, erstellen Sie die folgenden DNS-Einträge:
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>FQDN</th>
    <th>Typ</th>
    <th>Daten</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.1</p></td>
    </tr>
    <tr class="even">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.2</p></td>
    </tr>
    <tr class="odd">
    <td><p>Pool1.contoso.com</p></td>
    <td><p>Host (A)</p></td>
    <td><p>192.168.1.3</p></td>
    </tr>
    </tbody>
    </table>
    
    Details zum Erstellen von DNS-Hosteinträgen (A) finden Sie unter [Konfigurieren von DNS-Hosteinträgen für lync Server 2013](lync-server-2013-configure-dns-host-records.md).

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>So aktivieren Sie Round Robin für Windows Server

1.  Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Verwaltung**, und klicken Sie dann auf **DNS**.

2.  Erweitern Sie **DNS**, klicken Sie mit der rechten Maustaste auf den DNS-Server, den Sie konfigurieren möchten, und klicken Sie dann auf **Eigenschaften**.

3.  Klicken Sie auf die Registerkarte **erweitert** , wählen Sie **Round Robin aktivieren** und **Netzmaske aktivieren**aus, und klicken Sie dann auf **OK**.
    
    ![DNS Round Robin (Dialogfeld] ) (images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS Round Robin (Dialogfeld") )

<div>


> [!NOTE]  
> Dieses Feature sollte standardmäßig aktiviert sein.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

