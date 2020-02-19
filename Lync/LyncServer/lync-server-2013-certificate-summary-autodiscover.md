---
title: 'Lync Server 2013: Zertifikatzusammenfassung-AutoErmittlung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7d45183b3dac5d96d65d771bf1425546f861c38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="6cee5-102">Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6cee5-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cee5-103">_**Letztes Änderungsstand des Themas:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="6cee5-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="6cee5-104">Der lync Server 2013 AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool-Server ausgeführt und kann bei Veröffentlichung in DNS von lync-Clients zum Auffinden von Server-und Benutzerdiensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6cee5-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="6cee5-105">Wenn Sie ein Upgrade von lync Server 2010 durchführen und keine Mobilität bereitgestellt haben, müssen Sie, bevor Clients die automatische Ermittlung verwenden können, die Listen alternativer Zertifikatsantrags Teller Namen auf allen Directors ändern und Front-End-Server ausführen des AutoErmittlungsdiensts.</span><span class="sxs-lookup"><span data-stu-id="6cee5-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="6cee5-106">Darüber hinaus kann es erforderlich sein, die Listen Betreff alternativer Namen auf Zertifikaten zu ändern, die für externe Webdienst-Veröffentlichungsregeln für Reverse-Proxies verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6cee5-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="6cee5-107">Die Entscheidung, ob Listen für alternative Antragstellernamen in umgekehrten Proxys verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder an Port 443 veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="6cee5-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="6cee5-108">**Veröffentlicht auf Port 80**   keine Zertifikat Änderungen sind erforderlich, wenn die erste Abfrage an den AutoErmittlungsdienst über Port 80 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="6cee5-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="6cee5-109">Dies liegt daran, dass Mobile Geräte, auf denen lync betrieben wird, extern auf den Reverseproxy auf Port 80 zugreifen und dann intern mit einem Director oder Front-End-Server an Port 8080 überbrückt werden.</span><span class="sxs-lookup"><span data-stu-id="6cee5-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="6cee5-110">Ausführliche Informationen finden Sie im Abschnitt "erste Auto Ermittlungsverfahren mit Port 80" [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="6cee5-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="6cee5-111">**Veröffentlicht am Port 443**   die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss ein \*lyncdiscover enthalten.\< sipdomain "\> \* -Eintrag für jede SIP-Domäne in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="6cee5-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="6cee5-112">Es wird dringend empfohlen, HTTPS über HTTP zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cee5-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="6cee5-113">HTTPS verwendet Zertifikate zum Verschlüsseln des Datenverkehrs.</span><span class="sxs-lookup"><span data-stu-id="6cee5-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="6cee5-114">HTTP bietet keine Verschlüsselung, und alle gesendeten Daten sind nur-Text.</span><span class="sxs-lookup"><span data-stu-id="6cee5-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="6cee5-115">Das neuausgeben von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Prozess.</span><span class="sxs-lookup"><span data-stu-id="6cee5-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="6cee5-116">Bei öffentlichen Zertifikaten, die in der Veröffentlichungsregel des Webdiensts verwendet werden, kann das Hinzufügen mehrerer alternativer Antragstellernamen teuer werden.</span><span class="sxs-lookup"><span data-stu-id="6cee5-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="6cee5-117">Um dieses Problem zu umgehen, unterstützen wir die anfängliche automatische Ermittlungs Verbindung über Port 80, die dann an Port 8080 auf dem Director oder Front-End-Server umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="6cee5-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6cee5-118">Wenn Ihre lync Server 2013-Infrastruktur interne Zertifikate verwendet, die von einer internen Zertifizierungsstelle ausgestellt werden und Sie beabsichtigen, Mobile Geräte mit Drahtlosverbindungen zu unterstützen, muss entweder die Stammzertifikatkette von der internen Zertifizierungsstelle installiert sein. auf den mobilen Geräten oder müssen Sie zu einem öffentlichen Zertifikat in ihrer lync Server 2013 Infrastruktur wechseln.</span><span class="sxs-lookup"><span data-stu-id="6cee5-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="6cee5-119">In diesem Thema werden die zusätzlichen alternativen Antragstellernamen beschrieben, die für Director, Front-End-Server und Reverse Proxy erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="6cee5-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="6cee5-120">Es wird nur auf die hinzugefügten alternativen Antragstellernamen (San) verwiesen.</span><span class="sxs-lookup"><span data-stu-id="6cee5-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="6cee5-121">In den Planungs Abschnitten erhalten Sie Anleitungen zu den anderen Einträgen in Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="6cee5-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="6cee5-122">Ausführliche Informationen finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)und [Szenarien für Reverse Proxy in lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="6cee5-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="6cee5-123">In den folgenden Tabellen werden die San-Einträge für die AutoErmittlung für die Directorpool, die Front-End-Pool und den Reverseproxy definiert:</span><span class="sxs-lookup"><span data-stu-id="6cee5-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="6cee5-124">Directorpool-Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="6cee5-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cee5-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6cee5-125">Description</span></span></th>
<th><span data-ttu-id="6cee5-126">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="6cee5-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cee5-127">Interne URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="6cee5-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="6cee5-128">San = "lyncdiscoverinternal". &lt;Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="6cee5-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cee5-129">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="6cee5-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="6cee5-130">San = lyncdiscover. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="6cee5-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6cee5-131">Sie weisen das neu aktualisierte Zertifikat dem neuen San-Eintrag dem Standardzertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="6cee5-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="6cee5-132">Alternativ können Sie San = \* verwenden. &lt;sipdomain "&gt;.</span><span class="sxs-lookup"><span data-stu-id="6cee5-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="6cee5-133">Front-End-Pool-Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="6cee5-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cee5-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6cee5-134">Description</span></span></th>
<th><span data-ttu-id="6cee5-135">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="6cee5-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cee5-136">Interne URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="6cee5-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="6cee5-137">San = "lyncdiscoverinternal". &lt;Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="6cee5-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6cee5-138">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="6cee5-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="6cee5-139">San = lyncdiscover. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="6cee5-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6cee5-140">Sie weisen das neu aktualisierte Zertifikat dem neuen San-Eintrag dem Standardzertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="6cee5-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="6cee5-141">Alternativ können Sie San = \* verwenden. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="6cee5-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="6cee5-142">Reverseproxy-Zertifikatanforderungen (öffentliche ZS)</span><span class="sxs-lookup"><span data-stu-id="6cee5-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6cee5-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6cee5-143">Description</span></span></th>
<th><span data-ttu-id="6cee5-144">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="6cee5-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6cee5-145">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="6cee5-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="6cee5-146">San = lyncdiscover. &lt;sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="6cee5-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6cee5-147">Sie weisen das neu aktualisierte Zertifikat dem neuen San-Eintrag dem SSL-Listener auf dem Reverseproxy zu.</span><span class="sxs-lookup"><span data-stu-id="6cee5-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

