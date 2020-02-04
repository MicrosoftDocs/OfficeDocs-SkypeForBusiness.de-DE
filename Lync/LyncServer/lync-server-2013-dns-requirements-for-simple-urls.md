---
title: 'Lync Server 2013: DNS-Anforderungen für einfache URLs'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for simple URLs
ms:assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425874(v=OCS.15)
ms:contentKeyID: 48183912
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfc827a1cd48bdc6a7a15b8ba54f7ac451d1b352
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a>DNS-Anforderungen für einfache URLs in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-22_

Lync Server 2013 unterstützt einfache URLs, mit denen Sie Ihren Benutzern die Teilnahme an Besprechungen erleichtern und die Verwaltung von lync Server-Verwaltungstools für Ihre Administratoren einfacher machen können. Ausführliche Informationen zu einfachen URLs finden Sie unter [Planen einfacher URLs in lync Server 2013](lync-server-2013-planning-for-simple-urls.md).

Lync Server unterstützt die folgenden drei einfachen URLs: Besprechung, Einwahl und Administrator. Sie müssen einfache URLs für Meet und Dial-in einrichten, und die einfache Administrator-URL ist optional. Die DNS-Einträge (Domain Name System), die Sie zur Unterstützung einfacher URLs benötigen, hängen davon ab, wie Sie diese einfachen URLs definiert haben und ob Sie die Disaster Recovery für einfache URLs unterstützen möchten.

<div>

## <a name="simple-url-option-1"></a>Einfache URL-Option 1

In Option 1 erstellen Sie für jede einfache URL eine neue Basis-URL.

<div class="">


> [!NOTE]  
> Wenn ein Benutzer auf einen einfachen URL-Besprechungslink klickt, wird der Server, auf dem der DNS-a-Eintrag aufgelöst wird, ermittelt, um die richtige Client Software zu starten. Nachdem die Client Software gestartet wurde, kommuniziert sie automatisch mit dem Pool, in dem die Konferenz gehostet wird. Auf diese Weise werden Benutzer an den entsprechenden Server für Besprechungsinhalte weitergeleitet, unabhängig davon, in welchem Server oder Pool die einfache URL-DNS-A-Einträge aufgelöst werden.



</div>

### <a name="simple-url-option-1"></a>Einfache URL-Option 1

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
<td><p>Treffen</p></td>
<td><p>https://meet.contoso.comhttps://meet.fabrikam.comusw. (eine für jede SIP-Domäne in Ihrer Organisation)</p></td>
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


Wenn Sie Option 1 verwenden, müssen Sie Folgendes definieren:

  - Für jede einfache URL-Besprechung benötigen Sie einen DNS-a-Eintrag, der die URL zur IP-Adresse des Directors auflöst, wenn Sie eine bereitgestellt haben. Andernfalls sollte Sie in die IP-Adresse des Load Balancer eines Front-End-Pools aufgelöst werden. Wenn Sie keinen Pool bereitgestellt haben und eine Standard Edition-Server Bereitstellung verwenden, muss der DNS-a-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.
    
    Wenn in Ihrer Organisation mehr als eine SIP-Domäne vorhanden ist und Sie diese Option verwenden, müssen Sie für jede SIP-Domäne einfache URLs erstellen, und für jede einfache URL muss ein DNS-a-Eintrag erstellt werden. Wenn Sie beispielsweise sowohl contoso.com als auch fabrikam.com haben, erstellen Sie DNS-A-Einträge für https://meet.contoso.com beide https://meet.fabrikam.comund.
    
    Wenn Sie aber über mehrere SIP-Domänen verfügen und den DNS-Eintrag und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten, verwenden Sie Option 3 wie weiter unten in diesem Thema beschrieben.

  - Für die einfache Dial-in-URL benötigen Sie einen DNS-a-Eintrag, der die URL zur IP-Adresse des Directors auflöst, wenn Sie eine bereitgestellt haben. Andernfalls sollte Sie in die IP-Adresse des Load Balancer eines Front-End-Pools aufgelöst werden. Wenn Sie keinen Pool bereitgestellt haben und eine Standard Edition-Server Bereitstellung verwenden, muss der DNS-a-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.

  - Die einfache Administrator-URL ist nur intern. Hierfür ist ein DNS-a-Eintrag erforderlich, bei dem die URL zur IP-Adresse des Directors aufgelöst wird, wenn eine solche bereitgestellt wurde. Andernfalls sollte Sie in die IP-Adresse des Load Balancer eines Front-End-Pools aufgelöst werden. Wenn Sie keinen Pool bereitgestellt haben und eine Standard Edition-Server Bereitstellung verwenden, muss der DNS-a-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.

</div>

<div>

## <a name="simple-url-option-2"></a>Einfache URL-Option 2

Bei Option 2 verfügen die einfachen URLs für Besprechungen, Einwahl und Administratoren über eine allgemeine Basis-URL, beispielsweise lync.contoso.com. Daher benötigen Sie nur einen DNS-A-Eintrag für diese einfachen URLs, wodurch lync.contoso.com in die IP-Adresse eines Director-Pools oder eines Front-End-Pools aufgelöst wird. Wenn Sie keinen Pool bereitgestellt haben und eine Standard Edition-Server Bereitstellung verwenden, muss der DNS-a-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.

Beachten Sie Folgendes: Wenn in Ihrer Organisation mehr als eine SIP-Domäne vorhanden ist, müssen Sie für jede SIP-Domäne immer noch einfache URLs erstellen, und für jede einfache URL muss ein DNS-a-Eintrag erstellt werden. In diesem Beispiel werden drei einfache URLs, die alle auf lync.contoso.com basieren, als zusätzliche einfache URL für fabrikam.com mit einer anderen Basis-URL eingerichtet. In diesem Beispiel müssen Sie DNS-A-Einträge für beide https://lync.contoso.com und https://lync.fabrikam.comerstellen. Die einfache URL-Option 3 zeigt eine andere Möglichkeit zur Behandlung von Namen-und DNS-Einträgen, wenn Sie über mehrere SIP-Domänen verfügen.

### <a name="simple-url-option-2"></a>Einfache URL-Option 2

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
<td><p>Treffen</p></td>
<td><p>https://lync.contoso.com/Meethttps://lync.fabrikam.com/Meetusw. (eine für jede SIP-Domäne in Ihrer Organisation)</p></td>
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


</div>

<div>

## <a name="simple-url-option-3"></a>Einfache URL-Option 3

Option 3 ist besonders nützlich, wenn Sie über viele SIP-Domänen verfügen und diese über getrennte einfache URLs verfügen möchten, aber den DNS-Eintrag und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten. In diesem Beispiel benötigen Sie nur einen DNS-A-Eintrag, mit dem lync.contoso.com in die IP-Adresse eines Director-Pools oder eines Front-End-Pools aufgelöst wird.

### <a name="simple-url-option-3"></a>Einfache URL-Option 3

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
<td><p>Treffen</p></td>
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


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a>Disaster Recovery-Option für einfache URLs

Wenn Sie über mehrere Websites verfügen, die Front-End-Pools enthalten und Ihr DNS-Anbieter GeoDNS unterstützt, können Sie Ihre DNS-Einträge für einfache URLs einrichten, um die Disaster Recovery zu unterstützen, damit die einfache URL-Funktionalität auch dann fortgesetzt wird, wenn ein ganzer Front-End-Pool ausfällt. Dieses Disaster Recovery-Feature unterstützt die einfachen URLs Meet und Dial-in.

Um dies zu konfigurieren, erstellen Sie zwei GeoDNS-Adressen. Jede Adresse hat zwei DNS-A-oder CNAME-Einträge, die in zwei Pools aufgelöst werden, die für Disaster Recovery-Zwecke kombiniert werden. Eine GeoDNS-Adresse wird für den internen Zugriff verwendet und in die IP-Adresse des internen webfqdn oder des Lastenausgleichsmoduls für die beiden Pools aufgelöst. Die andere GeoDNS-Adresse wird für den externen Zugriff verwendet und in die IP-Adresse des externen webfqdn oder des Load Balancer für die beiden Pools aufgelöst. Im folgenden finden Sie ein Beispiel für die einfache URL "erfüllen" mit den FQDNs für die Pools.

   ```
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

Erstellen Sie dann CNAME-Einträge, die ihre einfache URL (beispielsweise Meet.contoso.com) zu den beiden GeoDNS-Adressen auflösen.

<div class="">


> [!NOTE]  
> Wenn in Ihrem Netzwerk <EM>hairpinning</EM> (Routing aller einfachen URL-Datenverkehr über den externen Link, einschließlich Datenverkehr, der aus Ihrer Organisation stammt) verwendet wird, können Sie einfach die externe GeoDNS-Adresse konfigurieren und ihre einfache URL für die Besprechung nur an diese externe Adresse auflösen.



</div>

Wenn Sie diese Methode verwenden, können Sie jede GeoDNS-Adresse so konfigurieren, dass entweder eine Round Robin-Methode zum Verteilen von Anforderungen an die beiden Pools verwendet wird, oder wenn Sie eine Verbindung in erster Linie mit einem Pool (wie etwa dem geografisch näher gelegenen Pool) herstellen und den anderen Pool nur verwenden, wenn Verbindungsfehler

Sie können die gleiche Konfiguration für die Einwahl einfache URL einrichten. Erstellen Sie dazu zusätzliche Datensätze wie im vorherigen Beispiel, die `dialin` `meet` in den DNS-Einträgen ersetzt werden. Verwenden Sie für die einfache Administrator-URL eine der drei oben in diesem Abschnitt aufgeführten Optionen.

Sobald diese Konfiguration eingerichtet ist, müssen Sie eine Überwachungsanwendung verwenden, um die HTTP-Überwachung so einzurichten, dass Fehler überwacht werden. Überwachen Sie für externen Zugriff, um sicherzustellen, dass HTTPS AutoDiscovery-Anforderungen an die externe Web-FQDN-oder Load Balancer-IP-Adresse für die beiden Pools erhalten erfolgreich sind. Die folgenden Anforderungen dürfen beispielsweise keinen **Accept** -Header enthalten und müssen **200 OK**zurückgeben.

    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root

Für den internen Zugriff müssen Sie Port 5061 auf der internal Web FQDN-oder Load Balancer-IP-Adresse für die beiden Pools überwachen. Wenn Verbindungsfehler erkannt werden, müssen die VIP für diese Pools die Ports 80, 443 und 444 schließen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

