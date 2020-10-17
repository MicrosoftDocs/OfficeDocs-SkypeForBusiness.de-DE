---
title: 'Lync Server 2013: DNS-Anforderungen für einfache URLs'
description: 'Lync Server 2013: DNS-Anforderungen für einfache URLs.'
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
ms.openlocfilehash: 84cc893fc06e9c57dcad6506d692b4484827b56a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564961"
---
# <a name="dns-requirements-for-simple-urls-in-lync-server-2013"></a><span data-ttu-id="98b01-103">DNS-Anforderungen für einfache URLs in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="98b01-103">DNS requirements for simple URLs in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98b01-104">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="98b01-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="98b01-105">Lync Server 2013 unterstützt einfache URLs, die die Teilnahme an Besprechungen für Ihre Benutzer erleichtern und Ihnen das Einstieg in lync Server Verwaltungstools für Ihre Administratoren erleichtern.</span><span class="sxs-lookup"><span data-stu-id="98b01-105">Lync Server 2013 supports simple URLs, which make joining meetings easier for your users, and make getting to Lync Server administrative tools easier for your administrators.</span></span> <span data-ttu-id="98b01-106">Ausführliche Informationen zu einfachen URLs finden Sie unter [Planning for Simple URLs in lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="98b01-106">For details about simple URLs, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<span data-ttu-id="98b01-107">Lync Server unterstützt die folgenden drei einfachen URLs: Meet, Einwahl und Administrator. Sie müssen einfache URLs für "Meet" und "Dial-in" einrichten, und die einfache admin-URL ist optional.</span><span class="sxs-lookup"><span data-stu-id="98b01-107">Lync Server supports the following three simple URLs: Meet, Dial-In, and Admin. You are required to set up simple URLs for Meet and Dial-In, and the Admin simple URL is optional.</span></span> <span data-ttu-id="98b01-108">Die zur Unterstützung einfacher URLs erforderlichen DNS-Einträge (Domain Name System) richten sich danach, wie Sie die einfachen URLs definiert haben und ob Sie die Notfallwiederherstellung für einfache URLs unterstützen möchten.</span><span class="sxs-lookup"><span data-stu-id="98b01-108">The Domain Name System (DNS) records that you need to support simple URLs depend on how you have defined these simple URLs, and whether you want to support disaster recovery for Simple URLs.</span></span>

<div>

## <a name="simple-url-option-1"></a><span data-ttu-id="98b01-109">Einfache URL – Option 1</span><span class="sxs-lookup"><span data-stu-id="98b01-109">Simple URL Option 1</span></span>

<span data-ttu-id="98b01-110">Bei Option 1 erstellen Sie eine neue Basis-URL für jede einfache URL.</span><span class="sxs-lookup"><span data-stu-id="98b01-110">In Option 1, you create a new base URL for each simple URL.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="98b01-p103">Wenn ein Benutzer auf einen Besprechungslink mit einfacher URL klickt, legt der Server, in den der DNS-A-Eintrag aufgelöst wird, die richtige zu startende Clientsoftware fest. Nach dem Start der Clientsoftware kommuniziert diese automatisch mit dem Pool, in dem die Konferenz gehostet wird. Auf diese Weise werden Benutzer an den geeigneten Server für Besprechungsinhalte weitergeleitet – unabhängig davon, in welchen Server oder Pool die DNS-A-Einträge einfacher URLs aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="98b01-p103">When a user clicks a simple URL meeting link, the server that the DNS A record resolves to determines the correct client software to start. After the client software is started, it automatically communicates with the pool where the conference is hosted. This way, users are directed to the appropriate server for meeting content no matter which server or pool the simple URL DNS A records resolve to.</span></span>



</div>

### <a name="simple-url-option-1"></a><span data-ttu-id="98b01-114">Einfache URL – Option 1</span><span class="sxs-lookup"><span data-stu-id="98b01-114">Simple URL Option 1</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98b01-115"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="98b01-115"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="98b01-116"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="98b01-116"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b01-117">Erfüllen</span><span class="sxs-lookup"><span data-stu-id="98b01-117">Meet</span></span></p></td>
<td><p><span data-ttu-id="98b01-118">https://meet.contoso.com, https://meet.fabrikam.com usw. (eine für jede SIP-Domäne in Ihrer Organisation)</span><span class="sxs-lookup"><span data-stu-id="98b01-118">https://meet.contoso.com, https://meet.fabrikam.com, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b01-119">Einwahl</span><span class="sxs-lookup"><span data-stu-id="98b01-119">Dial-in</span></span></p></td>
<td><p>https://dialin.contoso.com</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b01-120">Administrator</span><span class="sxs-lookup"><span data-stu-id="98b01-120">Admin</span></span></p></td>
<td><p>https://admin.contoso.com</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="98b01-121">Wenn Sie Option 1 verwenden, müssen Sie Folgendes definieren:</span><span class="sxs-lookup"><span data-stu-id="98b01-121">If you use Option 1, you must define the following:</span></span>

  - <span data-ttu-id="98b01-p104">Für jede einfache URL vom Typ "Meet" wird ein DNS-A-Eintrag benötigt, der die URL in die IP-Adresse des Directors auflöst, sofern ein solcher bereitgestellt wurde. Andernfalls sollte der Eintrag in die IP-Adresse des Geräts zum Lastenausgleich für einen Front-End-Pool aufgelöst werden. Wenn Sie keinen Pool bereitgestellt haben und eine Bereitstellung mit Standard Edition-Server verwenden, muss der DNS-A-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="98b01-p104">For each Meet simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>
    
    <span data-ttu-id="98b01-125">Wenn Sie mehr als eine SIP-Domäne in Ihrer Organisation verwenden und diese Option wählen, müssen Sie einfache Meet-URLs für jede SIP-Domäne erstellen und benötigen einen DNS-A-Eintrag für jede einfache Meet-URL.</span><span class="sxs-lookup"><span data-stu-id="98b01-125">If you have more than one SIP domain in your organization and you use this option, you must create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="98b01-126">Wenn Sie beispielsweise sowohl contoso.com als auch fabrikam.com haben, erstellen Sie DNS-A-Einträge für beide https://meet.contoso.com und https://meet.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="98b01-126">For example, if you have both contoso.com and fabrikam.com, you will create DNS A records for both https://meet.contoso.com and https://meet.fabrikam.com.</span></span>
    
    <span data-ttu-id="98b01-127">Alternativ können Sie bei Verwendung mehrerer SIP-Domänen Option 3 verwenden, um die Anzahl von DNS-Einträgen und die Zertifikatanforderungen für die einfachen URLs zu minimieren. Option 3 wird weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="98b01-127">Alternatively, if you have multiple SIP domains and you want to minimize the DNS record and certificate requirements for these simple URLs, use Option 3 as described later in this topic.</span></span>

  - <span data-ttu-id="98b01-p106">Für die einfache URL vom Typ "Dialin" wird ein DNS-A-Eintrag benötigt, der die URL in die IP-Adresse des Directors auflöst, sofern ein solcher bereitgestellt wurde. Andernfalls sollte der Eintrag in die IP-Adresse des Geräts zum Lastenausgleich für einen Front-End-Pool aufgelöst werden. Wenn Sie keinen Pool bereitgestellt haben und eine Bereitstellung mit Standard Edition-Server verwenden, muss der DNS-A-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="98b01-p106">For the Dial-in simple URL, you need a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

  - <span data-ttu-id="98b01-p107">Die einfache URL vom Typ "Admin" wird nur intern verwendet. Für sie wird ein DNS-A-Eintrag benötigt, der die URL in die IP-Adresse des Directors auflöst, sofern ein solcher bereitgestellt wurde. Andernfalls sollte der Eintrag in die IP-Adresse des Geräts zum Lastenausgleich für einen Front-End-Pool aufgelöst werden. Wenn Sie keinen Pool bereitgestellt haben und eine Bereitstellung mit Standard Edition-Server verwenden, muss der DNS-A-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="98b01-p107">The Admin simple URL is internal only. It requires a DNS A record that resolves the URL to the IP address of the Director, if you have one deployed. Otherwise, it should resolve to the IP address of the load balancer of a Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

</div>

<div>

## <a name="simple-url-option-2"></a><span data-ttu-id="98b01-135">Einfache URL – Option 2</span><span class="sxs-lookup"><span data-stu-id="98b01-135">Simple URL Option 2</span></span>

<span data-ttu-id="98b01-p108">Bei Verwendung von Option 2 weisen die einfachen URLs vom Typ "Meet", "Dialin" und "Admin" eine gemeinsame Basis-URL auf, z. B. "lync.contoso.com". Aus diesem Grund wird nur ein DNS-A-Eintrag für die einfachen URLs benötigt, der "lync.contoso.com" in die IP-Adresse eines Director- oder Front-End-Pools auflöst. Wenn Sie keinen Pool bereitgestellt haben und eine Bereitstellung mit Standard Edition-Server verwenden, muss der DNS-A-Eintrag in die IP-Adresse eines Standard Edition-Servers in Ihrer Organisation aufgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="98b01-p108">With Option 2, the Meet, Dial-in, and Admin simple URLs all have a common base URL, such as lync.contoso.com. Therefore, you need only one DNS A record for these simple URLs, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool. If you have not deployed a pool and are using a Standard Edition server deployment, the DNS A record must resolve to the IP address of one Standard Edition server in your organization.</span></span>

<span data-ttu-id="98b01-139">Wenn Sie mehr als eine SIP-Domäne in Ihrer Organisation verwenden, müssen Sie einfache Meet-URLs für jede SIP-Domäne erstellen und benötigen einen DNS-A-Eintrag für jede einfache Meet-URL.</span><span class="sxs-lookup"><span data-stu-id="98b01-139">Note that if you have more than one SIP domain in your organization, you must still create Meet simple URLs for each SIP domain and you need a DNS A record for each Meet simple URL.</span></span> <span data-ttu-id="98b01-140">In diesem Beispiel basieren die drei einfachen URLs alle auf "lync.contoso.com", es wird jedoch eine zusätzliche einfache Meet-URL für "fabrikam.com" mit einer anderen Basis-URL erstellt.</span><span class="sxs-lookup"><span data-stu-id="98b01-140">In this example, while three simple URLs are all based on lync.contoso.com, an additional Meet simple URL for fabrikam.com is set up with a different base URL.</span></span> <span data-ttu-id="98b01-141">In diesem Beispiel müssen Sie DNS-A-Einträge für https://lync.contoso.com und erstellen https://lync.fabrikam.com .</span><span class="sxs-lookup"><span data-stu-id="98b01-141">In this example, you must create DNS A records for both https://lync.contoso.com and https://lync.fabrikam.com.</span></span> <span data-ttu-id="98b01-142">Option 3 für einfache URLs zeigt eine weitere Möglichkeit zur Handhabung von Benennung und DNS-A-Einträgen, wenn Sie über mehrere SIP-Domänen verfügen.</span><span class="sxs-lookup"><span data-stu-id="98b01-142">Simple URL Option 3 shows another way to handle naming and DNS A records if you have multiple SIP domains.</span></span>

### <a name="simple-url-option-2"></a><span data-ttu-id="98b01-143">Einfache URL – Option 2</span><span class="sxs-lookup"><span data-stu-id="98b01-143">Simple URL Option 2</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98b01-144"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="98b01-144"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="98b01-145"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="98b01-145"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b01-146">Erfüllen</span><span class="sxs-lookup"><span data-stu-id="98b01-146">Meet</span></span></p></td>
<td><p><span data-ttu-id="98b01-147">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet usw. (eine für jede SIP-Domäne in Ihrer Organisation)</span><span class="sxs-lookup"><span data-stu-id="98b01-147">https://lync.contoso.com/Meet, https://lync.fabrikam.com/Meet, and so on (one for each SIP domain in your organization)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b01-148">Einwahl</span><span class="sxs-lookup"><span data-stu-id="98b01-148">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b01-149">Administrator</span><span class="sxs-lookup"><span data-stu-id="98b01-149">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simple-url-option-3"></a><span data-ttu-id="98b01-150">Einfache URL – Option 3</span><span class="sxs-lookup"><span data-stu-id="98b01-150">Simple URL Option 3</span></span>

<span data-ttu-id="98b01-p110">Option 3 ist sinnvoll, wenn Sie über zahlreiche SIP-Domänen verfügen und diesen separate einfache URLs zuweisen, jedoch die Anzahl von DNS-Einträgen und die Zertifikatanforderungen für diese einfachen URLs minimieren möchten. In diesem Beispiel benötigen Sie lediglich einen DNS-A-Eintrag der "lync.contoso.com" in die IP-Adresse eines Director- oder Front-End-Pools auflöst.</span><span class="sxs-lookup"><span data-stu-id="98b01-p110">Option 3 is most useful if you have many SIP domains, and you want them to have separate simple URLs but want to minimize the DNS record and certificate requirements for these simple URLs. In this example, you need only one DNS A record, which resolves lync.contoso.com to the IP address of a Director pool or Front End pool.</span></span>

### <a name="simple-url-option-3"></a><span data-ttu-id="98b01-153">Einfache URL – Option 3</span><span class="sxs-lookup"><span data-stu-id="98b01-153">Simple URL Option 3</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98b01-154"><strong>Einfache URL</strong></span><span class="sxs-lookup"><span data-stu-id="98b01-154"><strong>Simple URL</strong></span></span></p></td>
<td><p><span data-ttu-id="98b01-155"><strong>Beispiel</strong></span><span class="sxs-lookup"><span data-stu-id="98b01-155"><strong>Example</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b01-156">Erfüllen</span><span class="sxs-lookup"><span data-stu-id="98b01-156">Meet</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Meet</p>
<p>https://lync.contoso.com/fabrikamSIPdomain/Meet</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b01-157">Einwahl</span><span class="sxs-lookup"><span data-stu-id="98b01-157">Dial-in</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Dialin</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b01-158">Administrator</span><span class="sxs-lookup"><span data-stu-id="98b01-158">Admin</span></span></p></td>
<td><p>https://lync.contoso.com/contosoSIPdomain/Admin</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="disaster-recovery-option-for-simple-urls"></a><span data-ttu-id="98b01-159">Notfallwiederherstellungsoption für einfache URLs</span><span class="sxs-lookup"><span data-stu-id="98b01-159">Disaster Recovery Option for Simple URLs</span></span>

<span data-ttu-id="98b01-160">Wenn Sie über mehrere Websites verfügen, die Front-End-Pools enthalten, und Ihr DNS-Anbieter GeoDNS unterstützt, können Sie Ihre DNS-Einträge für einfache URLs zur Unterstützung der Notfallwiederherstellung einrichten, sodass die einfache URL-Funktionalität auch dann fortgesetzt wird, wenn ein ganzer Front-End-Pool ausfällt.</span><span class="sxs-lookup"><span data-stu-id="98b01-160">If you have multiple sites that contain Front End pools and your DNS provider supports GeoDNS, you can set up your DNS records for Simple URLs to support disaster recovery, so that Simple URL functionality continues even if one entire Front End pool goes down.</span></span> <span data-ttu-id="98b01-161">Diese Notfallwiederherstellungsfunktion unterstützt die einfachen URLs Meet und Dial-in.</span><span class="sxs-lookup"><span data-stu-id="98b01-161">This disaster recovery feature supports the Meet and Dial-In simple URLs.</span></span>

<span data-ttu-id="98b01-p112">Erstellen Sie zum Konfigurieren dieser Notfallwiederherstellung zwei GeoDNS-Adressen. Jede Adresse hat zwei DNS A- oder CNAME-Einträge. Diese werden in zwei Pools aufgelöst, die zu Notfallwiederherstellungszwecken ein Paar bilden. Eine GeoDNS-Adresse wird für den internen Zugriff verwendet und in den internen Web-FQDN oder die Lastenausgleichs-IP-Adresse für die beiden Pools aufgelöst. Die andere GeoDNS-Adresse wird für den externen Zugriff verwendet und in den externen Web-FQDN oder die Lastenausgleich-IP-Adresse für die beiden Pools aufgelöst. Im Folgenden sehen Sie ein Beispiel für eine einfache URL vom Typ Meet, in dem vollqualifizierte Domänennamen (FQDNs) für die Pools verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="98b01-p112">To configure this, create two GeoDNS addresses. Each address has two DNS A or CNAME records that resolve to two pools which are paired together for disaster recovery purposes. One GeoDNS address is used for internal access, and resolves to the internal web FQDN or load balancer IP address for the two pools. The other GeoDNS address is used for external access and resolves to the external web FQDN or load balancer IP address for the two pools. The following is an example for the Meet simple URL, using the FQDNs for the pools.</span></span>

   ```console
    Meet-int.geolb.contoso.com
         Pool1InternalWebFQDN.contoso.com
         Pool2InternalWebFQDN.contoso.com
   ```

   ```console
   Meet-ext.geolb.contoso.com
         Pool1ExternalWebFQDN.contoso.com
         Pool2ExternalWebFQDN.contoso.com
   ``` 

<span data-ttu-id="98b01-167">Erstellen Sie dann CNAME-Einträge, die Ihre einfache Meet-URL (z. B. meet.contoso.com) in die beiden GeoDNS-Adressen auflösen.</span><span class="sxs-lookup"><span data-stu-id="98b01-167">Then create CNAME records that resolve your Meet simple URL (such as meet.contoso.com) to the two GeoDNS addresses.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="98b01-168">Wenn in Ihrem Netzwerk das so genannte <EM>Hairpinning</EM> eingesetzt wird (der gesamte Datenverkehr der einfachen URL wird über den externen Link geleitet, einschließlich des Datenverkehrs aus der Organisation), können Sie einfach nur die externe GeoDNS-Adresse konfigurieren und Ihre einfache Meet-URL nur in diese externe Adresse auflösen.</span><span class="sxs-lookup"><span data-stu-id="98b01-168">If your network uses <EM>hairpinning</EM> (routing all your Simple URL traffic through the external link, including traffic that comes from within your organization), then you can just configure the external GeoDNS address and resolve your Meet simple URL to only that external address.</span></span>



</div>

<span data-ttu-id="98b01-169">Wenn Sie diese Methode verwenden, können Sie jede GeoDNS-Adresse so konfigurieren, dass entweder eine Roundrobin-Methode zur Verteilung der Anforderungen an die beiden Pools verwendet wird oder dass hauptsächlich eine Verbindung mit einem Pool hergestellt wird (z. B. mit dem Pool, der geografisch näher ist) und der andere Pool nur bei einem Konnektivitätsfehler zum Einsatz kommt.</span><span class="sxs-lookup"><span data-stu-id="98b01-169">When you use this method, you can configure each GeoDNS address to use either a round robin method to distribute requests to the two pools, or to connect primarily to one pool (such as the pool located geographically closer) and use the other pool only in case of connectivity failure.</span></span>

<span data-ttu-id="98b01-170">Sie können dieselbe Konfiguration für die einfache Dialin-URL verwenden.</span><span class="sxs-lookup"><span data-stu-id="98b01-170">You can set up the same configuration for the Dial-In simple URL.</span></span> <span data-ttu-id="98b01-171">Erstellen Sie dazu zusätzliche Datensätze wie die im vorherigen Beispiel, und ersetzen Sie Sie `dialin` `meet` in den DNS-Einträgen.</span><span class="sxs-lookup"><span data-stu-id="98b01-171">To do so, create additional records like those in the previous example, substituting `dialin` for `meet` in the DNS records.</span></span> <span data-ttu-id="98b01-172">Verwenden Sie für die einfache Admin-URL eine der weiter oben in diesem Abschnitt aufgelisteten drei Optionen.</span><span class="sxs-lookup"><span data-stu-id="98b01-172">For the Admin simple URL, use one of the three options listed earlier in this section.</span></span>

<span data-ttu-id="98b01-173">Sobald diese Konfiguration eingerichtet ist, müssen Sie eine Überwachungsanwendung verwenden, um die HTTP-Überwachung so einzurichten, dass nach Fehlern Ausschau gehalten wird.</span><span class="sxs-lookup"><span data-stu-id="98b01-173">Once this configuration is set up, you must use a monitoring application to set up HTTP monitoring to watch for failures.</span></span> <span data-ttu-id="98b01-174">Überwachen Sie für den externen Zugriff, um sicherzustellen, dass HTTPS AutoDiscovery-Anforderungen an den externen webfqdn oder die IP-Adresse des Lastenausgleichs für die beiden Pools erhalten erfolgreich sind.</span><span class="sxs-lookup"><span data-stu-id="98b01-174">For external access, monitor to make sure that HTTPS GET autodiscovery requests to the external web FQDN or load balancer IP address for the two pools are successful.</span></span> <span data-ttu-id="98b01-175">Beispielsweise dürfen die folgenden Anforderungen keinen **ACCEPT**-Header enthalten und müssen **200 OK** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="98b01-175">For example, the following requests must not contain any **ACCEPT** header and must return **200 OK**.</span></span>

```console
    HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
    HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

<span data-ttu-id="98b01-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span><span class="sxs-lookup"><span data-stu-id="98b01-p115">For internal access, you must monitor port 5061 on the internal web FQDN or load balancer IP address for the two pools. If any connectivity failures are detected, the VIP for these pools must close ports 80, 443 and 444.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

