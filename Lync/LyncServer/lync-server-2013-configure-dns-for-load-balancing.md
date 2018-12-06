---
title: 'Lync Server 2013: Konfigurieren von DNS für den Lastenausgleich'
TOCTitle: Konfigurieren von DNS für den Lastenausgleich
ms:assetid: 1b2e8414-8676-4872-8ecf-ea07196f74de
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398251(v=OCS.15)
ms:contentKeyID: 49293335
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von DNS für den Lastenausgleich in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie mindestens als Mitglied der Gruppe "Domänen-Admins" oder als Mitglied der Gruppe "DNSnsAdmins" beim Server oder bei der Domäne angemeldet sein.

Der DNS-Lastenausgleich (Domain Name System) sorgt für eine ausgewogene Verteilung des Netzwerkdatenverkehrs von Lync Server 2013, etwa des SIP- und Mediendatenverkehrs. Der DNS-Lastenausgleich wird für Front-End-Pools, Edgeserverpools, Director-Pools und eigenständige Vermittlungsserverpools unterstützt. Für einen Pool, der für den DNS-Lastenausgleich konfiguriert ist, müssen zwei vollqualifizierte Domänennamen (FQDNs) definiert werden: der reguläre Pool-FQDN (beispielsweise "pool1.contoso.com"), der vom DNS-Lastenausgleich verwendet und in die physischen IP-Adressen der Server im Pool aufgelöst wird, und ein weiterer FQDN für die Webdienste des Pools (z. B. "web1.contoso.net"), der in die virtuelle IP-Adresse des Pools aufgelöst wird. Ausführliche Informationen zum DNS-Lastenausgleich finden Sie unter [DNS-Lastenausgleich in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in der Planungsdokumentation.


> [!NOTE]
> Hardwarelastenausgleich ist weiterhin für den HTTPS-Datenverkehr zwischen Client und Server erforderlich.



Bevor Sie den DNS-Lastenausgleich verwenden können, müssen Sie folgende Schritte ausführen:

1.  Setzen Sie den FQDN für den internen Webdienstepool außer Kraft.
    

    > [!WARNING]
    > Wenn Sie den internen Webdienst mit einem eigenen FQDN überschreiben, muss der FQDN gegenüber jedem anderen Front-End-Pool, jedem anderen Director und jedem anderen Directorpool eindeutig sein.



2.  Erstellen Sie DNS-A-Einträge zum Auflösen der Pool-FQDN in die IP-Adressen aller Server im Pool.

3.  Aktivieren Sie zufällige IP-Adressen oder (für Windows Server DNS) Roundrobin.
    

    > [!NOTE]
    > Roundrobin sollte standardmäßig aktiviert werden.



## So setzen Sie den FQDN der internen Webdienste außer Kraft

1.  Starten des Topologie-Generators: Klicken Sie auf **Start**, zeigen Sie auf **Alle Programme** und dann auf **Microsoft Lync Server 2013**, und klicken Sie anschließend auf **Lync Server-Topologie-Generator**.

2.  Erweitern Sie in der Konsolenstruktur den Knoten für die Enterprise Edition-Front-End-Pools.

3.  Klicken Sie mit der rechten Maustaste auf den Pool, klicken Sie auf **Eigenschaften bearbeiten** und dann auf **Webdienste** .

4.  Aktivieren Sie unterhalb von **Interne Webdienste** das Kontrollkästchen **Vollqualifizierten Domänennamen außer Kraft setzen** .

5.  Geben Sie den Pool-FQDN ein, der in die physischen IP-Adressen der Server im Pool aufgelöst wird.

6.  Geben Sie unterhalb von **Externe Webdienste** den externen Pool-FQDN ein, der in die virtuellen IP-Adressen des Pools aufgelöst wird, und klicken Sie auf **OK** .

7.  Klicken Sie in der Konsolenstruktur auf **Lync Server 2013** und anschließend im Bereich **Aktionen** auf **Topologie veröffentlichen** .

## So erstellen Sie DNS-Hosteinträge (A) für alle internen Poolserver

1.  Klicken Sie nacheinander auf **Start** , **Alle Programme** , **Verwaltung** und **DNS** .

2.  Klicken Sie im **DNS Manager** auf den DNS-Server für die Eintragsverwaltung, um diesen zu erweitern.

3.  Klicken Sie auf **Forward-Lookupzonen** , um den Knoten zu erweitern.

4.  Klicken Sie mit der rechten Maustaste auf die DNS-Domäne, der Sie Einträge hinzufügen möchten, und klicken Sie dann auf **Neuer Host (A oder AAAA)** .

5.  Geben Sie im Feld **Name** den Namen des Hosteintrags ein (der Domänenname wird automatisch angehängt).

6.  Geben Sie im Feld für die IP-Adresse die IP-Adresse des Front-End-Servers ein, und wählen Sie anschließend **Verknüpften PTR-Eintrag erstellen** oder **Authentifizierte Benutzer können DNS-Einträge mit demselben Besitzernamen aktualisieren** , falls anwendbar.

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
    
    Ausführliche Informationen zum Erstellen von DNS-Hosteinträgen (A) finden Sie unter [Konfigurieren von DNS-Hosteinträgen für Lync Server 2013](lync-server-2013-configure-dns-host-records.md).

## So aktivieren Sie Roundrobin für Windows Server

1.  Klicken Sie nacheinander auf **Start** , **Alle Programme** , **Verwaltung** und **DNS** .

2.  Erweitern Sie **DNS** , klicken Sie mit der rechten Maustaste auf den DNS-Server, den Sie konfigurieren möchten, und klicken Sie anschließend auf **Eigenschaften** .

3.  Klicken Sie auf die Registerkarte **Erweitert** , wählen Sie **Roundrobin aktivieren** und **Netzwerkmaskenanforderung aktivieren** , und klicken Sie dann auf **OK** .
    
    ![DNS-Roundrobin (Dialogfeld)](images/Gg398251.e7bf6125-8d78-4460-8401-0a8e7e21d305(OCS.15).jpg "DNS-Roundrobin (Dialogfeld)")


> [!NOTE]
> Diese Funktion sollte standardmäßig aktiviert werden.



## Siehe auch

#### Konzepte

[DNS-Lastenausgleich in Lync Server 2013](lync-server-2013-dns-load-balancing.md)

