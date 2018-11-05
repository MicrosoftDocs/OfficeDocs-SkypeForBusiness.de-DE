---
title: 'Lync Server 2013: DNS-Anforderungen für einfache URLs'
TOCTitle: DNS-Anforderungen für einfache URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425874(v=OCS.15)
ms:contentKeyID: 49293722
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# DNS-Anforderungen für einfache URLs in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In Lync Server 2013 wird das Konzept einfacher URLs unterstützt, die den Benutzerbeitritt zu Besprechungen vereinfachen und Administratoren den Zugriff auf die Lync Server-Verwaltungstools erleichtern. Ausführliche Informationen zu einfachen URLs finden Sie unter [Planung für einfache URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

Lync Server unterstützt die folgenden drei einfachen URLs: "Meet" für Besprechungen, "Dialin" für die Einwahl, und "Admin" für den Verwaltungszugriff. Die einfachen URLs für Besprechungen und Einwahl müssen eingerichtet werden, die einfache URL für den Verwaltungszugriff ist optional. Die zur Unterstützung einfacher URLs erforderlichen DNS-Einträge (Domain Name System) richten sich danach, wie Sie die einfachen URLs definiert haben und ob Sie die Notfallwiederherstellung für einfache URLs unterstützen möchten.

## Einfache URL - Option 1

Bei Option 1 erstellen Sie eine neue Basis-URL für jede einfache URL.


> [!NOTE]
> Wenn ein Benutzer auf einen Besprechungslink mit einfacher URL klickt, legt der Server, in den der DNS-A-Eintrag aufgelöst wird, die richtige zu startende Clientsoftware fest. Nach dem Start der Clientsoftware kommuniziert diese automatisch mit dem Pool, in dem die Konferenz gehostet wird. Auf diese Weise werden Benutzer an den geeigneten Server für Besprechungsinhalte weitergeleitet - unabhängig davon, in welchen Server oder Pool die DNS-A-Einträge einfacher URLs aufgelöst werden.



### Einfache URL - Option 1

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Einfache URL</strong></p></td>
<td><p><strong>Beispiel</strong></p></td>
</tr>
<tr class="even">
<td><p>Meet</p></td>
<td><p>https://meet.contoso.com, https://meet.fabrikam.com usw. (eine URL für jede SIP-Domäne in Ihrer Organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Einwahl</p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


Wenn Sie Option 1 verwenden, müssen Sie Folgendes definieren:

  - Für jede einfache URL vom Typ "Meet" wird ein DNS-A-Eintrag benötigt, der die URL in die IP-Adresse des Directors auflöst, sofern ein solcher bereitgestellt wurde. Andernfalls sollte der Eintrag in die IP-Adresse des Geräts zum Lastenausgleich für einen Front-End-Pool aufgelöst werden. Wenn Sie keinen Pool bereitgestellt haben und eine Bereitstellung mit Standard Edition-Server verwenden, muss der DNS-A-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.
    
    Wenn Sie mehr als eine SIP-Domäne in Ihrer Organisation verwenden und diese Option wählen, müssen Sie einfache Meet-URLs für jede SIP-Domäne erstellen und benötigen einen DNS-A-Eintrag für jede einfache Meet-URL. Wenn Sie beispielsweise sowohl "contoso.com" als auch "fabrikam.com" verwenden, erstellen Sie DNS-A-Einträge für "https://meet.contoso.com" und "https://meet.fabrikam.com".
    
    Alternativ können Sie bei Verwendung mehrerer SIP-Domänen Option 3 verwenden, um die Anzahl von DNS-Einträgen und die Zertifikatanforderungen für die einfachen URLs zu minimieren. Option 3 wird weiter unten in diesem Thema beschrieben.

  - Für die einfache URL vom Typ "Dialin" wird ein DNS-A-Eintrag benötigt, der die URL in die IP-Adresse des Directors auflöst, sofern ein solcher bereitgestellt wurde. Andernfalls sollte der Eintrag in die IP-Adresse des Geräts zum Lastenausgleich für einen Front-End-Pool aufgelöst werden. Wenn Sie keinen Pool bereitgestellt haben und eine Bereitstellung mit Standard Edition-Server verwenden, muss der DNS-A-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.

  - Die einfache URL vom Typ "Admin" wird nur intern verwendet. Für sie wird ein DNS-A-Eintrag benötigt, der die URL in die IP-Adresse des Directors auflöst, sofern ein solcher bereitgestellt wurde. Andernfalls sollte der Eintrag in die IP-Adresse des Geräts zum Lastenausgleich für einen Front-End-Pool aufgelöst werden. Wenn Sie keinen Pool bereitgestellt haben und eine Bereitstellung mit Standard Edition-Server verwenden, muss der DNS-A-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.

## Einfache URL - Option 2

Bei Verwendung von Option 2 weisen die einfachen URLs vom Typ "Meet", "Dialin" und "Admin" eine gemeinsame Basis-URL auf, z. B. "lync.contoso.com". Aus diesem Grund wird nur ein DNS-A-Eintrag für die einfachen URLs benötigt, der "lync.contoso.com" in die IP-Adresse eines Director- oder Front-End-Pools auflöst. Wenn Sie keinen Pool bereitgestellt haben und eine Bereitstellung mit Standard Edition-Server verwenden, muss der DNS-A-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.

Wenn Sie mehr als eine SIP-Domäne in Ihrer Organisation verwenden, müssen Sie einfache Meet-URLs für jede SIP-Domäne erstellen und benötigen einen DNS-A-Eintrag für jede einfache Meet-URL. In diesem Beispiel basieren die drei einfachen URLs alle auf "lync.contoso.com", es wird jedoch eine zusätzliche einfache Meet-URL für "fabrikam.com" mit einer anderen Basis-URL erstellt. In diesem Beispiel müssen Sie DNS-A-Einträge für "https://lync.contoso.com" und "https://lync.fabrikam.com" erstellen. Option 3 für einfache URLs zeigt eine weitere Möglichkeit zur Handhabung von Benennung und DNS-A-Einträgen, wenn Sie über mehrere SIP-Domänen verfügen.

### Einfache URL - Option 2

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Einfache URL</strong></p></td>
<td><p><strong>Beispiel</strong></p></td>
</tr>
<tr class="even">
<td><p>Meet</p></td>
<td><p>https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet usw. (eine URL für jede SIP-Domäne in Ihrer Organisation)</p></td>
</tr>
<tr class="odd">
<td><p>Einwahl</p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


## Einfache URL - Option 3

Option 3 ist sinnvoll, wenn Sie über zahlreiche SIP-Domänen verfügen und diesen separate einfache URLs zuweisen, jedoch die Anzahl von DNS-Einträgen und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten. In diesem Beispiel benötigen Sie lediglich einen DNS-A-Eintrag der "lync.contoso.com" in die IP-Adresse eines Director- oder Front-End-Pools auflöst.

### Einfache URL - Option 3

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Einfache URL</strong></p></td>
<td><p><strong>Beispiel</strong></p></td>
</tr>
<tr class="even">
<td><p>Meet</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p>Einwahl</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p>Admin</p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


## Notfallwiederherstellungsoption für einfache URLs

Wenn Sie mehrere Standorte mit Front-End-Pools haben und Ihr DNS-Anbieter GeoDNS unterstützt, können Sie Ihre DNS-Einträge für einfache URLs einrichten, um die Notfallwiederherstellung zu unterstützen. Die Funktion für einfache URLs ist dann weiterhin verfügbar, auch wenn ein Front-End-Pool ganz ausfällt. Dieses Feature für die Notfallwiederherstellung unterstützt die einfachen URLs vom Typ **Meet** und **Dialin** .

Erstellen Sie zum Konfigurieren dieser Notfallwiederherstellung zwei GeoDNS-Adressen. Jede Adresse hat zwei DNS A- oder CNAME-Einträge. Diese werden in zwei Pools aufgelöst, die zu Notfallwiederherstellungszwecken ein Paar bilden. Eine GeoDNS-Adresse wird für den internen Zugriff verwendet und in den internen Web-FQDN oder die Lastenausgleichs-IP-Adresse für die beiden Pools aufgelöst. Die andere GeoDNS-Adresse wird für den externen Zugriff verwendet und in den externen Web-FQDN oder die Lastenausgleich-IP-Adresse für die beiden Pools aufgelöst. Im Folgenden sehen Sie ein Beispiel für eine einfache URL vom Typ **Meet** , in dem vollqualifizierte Domänennamen (FQDNs) für die Pools verwendet werden.

    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com

&nbsp;

    Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com

Erstellen Sie dann CNAME-Einträge, die Ihre einfache Meet-URL (z. B. **meet.contoso.com** ) in die beiden GeoDNS-Adressen auflösen.


> [!NOTE]
> Wenn in Ihrem Netzwerk das so genannte <EM>Hairpinning</EM> eingesetzt wird (der gesamte Datenverkehr der einfachen URL wird über den externen Link geleitet, einschließlich des Datenverkehrs aus der Organisation), können Sie einfach nur die externe GeoDNS-Adresse konfigurieren und Ihre einfache Meet-URL nur in diese externe Adresse auflösen.



Wenn Sie diese Methode verwenden, können Sie jede GeoDNS-Adresse so konfigurieren, dass entweder eine Roundrobin-Methode zur Verteilung der Anforderungen an die beiden Pools verwendet wird oder dass hauptsächlich eine Verbindung mit einem Pool hergestellt wird (z. B. mit dem Pool, der geografisch näher ist) und der andere Pool nur bei einem Konnektivitätsfehler zum Einsatz kommt.

Sie können dieselbe Konfiguration für die einfache Dialin-URL verwenden. Erstellen Sie hierzu zusätzliche Einträge wie die im vorherigen Beispiel, und ersetzen Sie dann in den DNS-Einträgen `dialin` durch `meet`. Verwenden Sie für die einfache Admin-URL eine der weiter oben in diesem Abschnitt aufgelisteten drei Optionen.

Sobald diese Konfiguration eingerichtet ist, müssen Sie eine Überwachungsanwendung verwenden, um die HTTP-Überwachung so einzurichten, dass nach Fehlern Ausschau gehalten wird. Führen Sie für den externen Zugriff eine Überwachung durch, um sicherzustellen, dass HTTPS-GET-AutoErmittlung-Anforderungen an den externen Web-FQDN oder die Lastenausgleichs-IP-Adresse für die beiden Pools erfolgreich sind. Beispielsweise dürfen die folgenden Anforderungen keinen **ACCEPT**-Header enthalten und müssen **200 OK** zurückgegeben.

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.

