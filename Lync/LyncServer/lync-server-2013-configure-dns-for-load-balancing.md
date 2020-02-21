---
title: 'Lync Server 2013: Konfigurieren von DNS für den Lastenausgleich'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for load balancing
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398251(v=OCS.15)
ms:contentKeyID: 48183540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d8b2059048823c1a8f063d0d7832759ec64e6341
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-load-balancing-in-lync-server-2013"></a>Konfigurieren von DNS für den Lastenausgleich in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-01_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNS-Admins" beim Server oder bei der Domäne angemeldet sein.

Bei Domain Name System (DNS) Lastenausgleich wird der für lync Server 2013 eindeutige Netzwerkdatenverkehr wie SIP-Datenverkehr und Mediendatenverkehr ausgeglichen. Der DNS-Lastenausgleich wird für Front-End-Pools, Edgeserverpools, Director-Pools und eigenständige Vermittlungsserverpools unterstützt. Für einen Pool, der für die Verwendung des DNS-Lastenausgleichs konfiguriert ist, müssen zwei vollqualifizierte Domänennamen (FQDNs) definiert sein: der reguläre Pool-FQDN, der vom DNS-Lastenausgleich verwendet wird (beispielsweise pool1.contoso.com) und der in die physischen IPS der Server im Pool aufgelöst wird. und einen weiteren FQDN für die Webdienste des Pools (beispielsweise web1.contoso.net), der in die virtuelle IP-Adresse des Pools aufgelöst wird. Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.

<div>


> [!NOTE]  
> Hardwarelastenausgleich ist weiterhin für den HTTPS-Datenverkehr zwischen Client und Server erforderlich.



</div>

Bevor Sie den DNS-Lastenausgleich verwenden können, müssen Sie folgende Schritte ausführen:

1.  Überschreiben Sie den internen FQDN des Webdienste Pools.
    
    <div>
    

    > [!WARNING]  
    > Wenn Sie die internen Webdienste mit einem selbst definierten FQDN außer Kraft setzen möchten, muss jeder FQDN von jedem anderen Front-End-Pool, Director oder einem Directorpool eindeutig sein.

    
    </div>

2.  Erstellen Sie DNS-A-Einträge zum Auflösen der Pool-FQDN in die IP-Adressen aller Server im Pool.

3.  Aktivieren Sie zufällige IP-Adressen oder (für Windows Server DNS) Roundrobin.
    
    <div>
    

    > [!NOTE]  
    > Roundrobin sollte standardmäßig aktiviert werden.

    
    </div>

<div>

## <a name="to-override-internal-web-services-fqdn"></a>So setzen Sie den FQDN der internen Webdienste außer Kraft

1.  Starten Sie den Topologie-Generator: Klicken Sie im **Startmenü**auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den Knoten für die Enterprise Edition-Front-End-Pools.

3.  Klicken Sie mit der rechten Maustaste auf den Pool, klicken Sie auf **Eigenschaften bearbeiten** und dann auf **Webdienste**.

4.  Aktivieren Sie unterhalb von **Interne Webdienste** das Kontrollkästchen **Vollqualifizierten Domänennamen außer Kraft setzen**.

5.  Geben Sie den Pool-FQDN ein, der in die physischen IP-Adressen der Server im Pool aufgelöst wird.

6.  Geben Sie unterhalb von **Externe Webdienste** den externen Pool-FQDN ein, der in die virtuellen IP-Adressen des Pools aufgelöst wird, und klicken Sie auf **OK**.

7.  Klicken Sie in der Konsolenstruktur auf **lync Server 2013**, und klicken Sie dann im Bereich **Aktionen** auf **Topologie veröffentlichen**.

</div>

<div>

## <a name="to-create-dns-host-a-records-for-all-internal-pool-servers"></a>So erstellen Sie DNS-Hosteinträge (A) für alle internen Poolserver

1.  Klicken Sie nacheinander auf **Start**, **Alle Programme**, **Verwaltung** und **DNS**.

2.  Klicken Sie im **DNS Manager** auf den DNS-Server für die Eintragsverwaltung, um diesen zu erweitern.

3.  Klicken Sie auf **Forward-Lookupzonen**, um den Knoten zu erweitern.

4.  Klicken Sie mit der rechten Maustaste auf die DNS-Domäne, der Sie Einträge hinzufügen möchten, und klicken Sie dann auf **Neuer Host (A oder AAAA)**.

5.  Geben Sie im Feld **Name** den Namen des Hosteintrags ein (der Domänenname wird automatisch angehängt).

6.  Geben Sie im Feld für die IP-Adresse die IP-Adresse des Front-End-Servers ein, und wählen Sie anschließend **Verknüpften PTR-Eintrag erstellen** oder **Authentifizierte Benutzer können DNS-Einträge mit demselben Besitzernamen aktualisieren**, falls anwendbar.

7.  Fahren Sie mit der Erstellung von Einträgen für alle Front-End-Mitgliedsserver fort, die in den DNS-Lastenausgleich einbezogen werden sollen.
    
    Wenn Sie beispielsweise über einen Pool namens "pool1.contoso.com" und drei Front-End-Server verfügen, erstellen Sie die folgenden DNS-Einträge:
    
    
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
    
    Ausführliche Informationen zum Erstellen von DNS-Hosteinträgen (A) finden Sie unter [Konfigurieren von DNS-Hosteinträgen für lync Server 2013](lync-server-2013-configure-dns-host-records.md).

</div>

<div>

## <a name="to-enable-round-robin-for-windows-server"></a>So aktivieren Sie Roundrobin für Windows Server

1.  Klicken Sie nacheinander auf **Start**, **Alle Programme**, **Verwaltung** und **DNS**.

2.  Erweitern Sie **DNS**, klicken Sie mit der rechten Maustaste auf den DNS-Server, den Sie konfigurieren möchten, und klicken Sie anschließend auf **Eigenschaften**.

3.  Klicken Sie auf die Registerkarte **Erweitert**, wählen Sie **Roundrobin aktivieren** und **Netzwerkmaskenanforderung aktivieren**, und klicken Sie dann auf **OK**.
    
    ![DNS-Roundrobin-Dialogfeld](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS-Roundrobin-Dialogfeld")

<div>


> [!NOTE]  
> Diese Funktion sollte standardmäßig aktiviert werden.



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

