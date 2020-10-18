---
title: 'Lync Server 2013: Zertifikatzusammenfassung-AutoErmittlung'
description: 'Lync Server 2013: Zertifikatzusammenfassung-AutoErmittlung.'
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
ms.openlocfilehash: ae421401421434a4c4069c1d90ee287dfb016997
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574711"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="b5989-103">Zertifikatzusammenfassung-AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5989-103">Certificate summary - Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5989-104">_**Letztes Änderungsstand des Themas:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="b5989-104">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="b5989-105">Der lync Server 2013 AutoErmittlungsdienst wird auf dem Director-und Front-End-Pool-Server ausgeführt und kann bei Veröffentlichung in DNS von lync-Clients zum Auffinden von Server-und Benutzerdiensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5989-105">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="b5989-106">Wenn Sie ein Upgrade von lync Server 2010 durchführen und keine Mobilität bereitgestellt haben, müssen Sie, bevor Clients die automatische Ermittlung verwenden können, die Listen alternativer Zertifikatsantrags Teller Namen auf allen Directors ändern und Front-End-Server ausführen des AutoErmittlungsdiensts.</span><span class="sxs-lookup"><span data-stu-id="b5989-106">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="b5989-107">Darüber hinaus kann es erforderlich sein, die Listen Betreff alternativer Namen auf Zertifikaten zu ändern, die für externe Webdienst-Veröffentlichungsregeln für Reverse-Proxies verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5989-107">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="b5989-108">Die Entscheidung, ob Listen für alternative Antragstellernamen in umgekehrten Proxys verwendet werden sollen, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder an Port 443 veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="b5989-108">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="b5989-109">**Veröffentlicht am Port 80**     Wenn die erste Abfrage an den AutoErmittlungsdienst über Port 80 erfolgt, sind keine Änderungen am Zertifikat erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b5989-109">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="b5989-110">Dies liegt daran, dass Mobile Geräte, auf denen lync betrieben wird, extern auf den Reverseproxy auf Port 80 zugreifen und dann intern mit einem Director oder Front-End-Server an Port 8080 überbrückt werden.</span><span class="sxs-lookup"><span data-stu-id="b5989-110">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="b5989-111">Ausführliche Informationen finden Sie im Abschnitt "erste Auto Ermittlungsverfahren mit Port 80" [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="b5989-111">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="b5989-112">**Veröffentlicht am Port 443**     Die Liste der alternativen Antragstellernamen für Zertifikate, die von der Veröffentlichungsregel für externe Webdienste verwendet werden, muss ein \*lyncdiscover enthalten. \<sipdomain\> \*</span><span class="sxs-lookup"><span data-stu-id="b5989-112">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>*</span></span> <span data-ttu-id="b5989-113">Eintrag für jede SIP-Domäne in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="b5989-113">entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b5989-114">Es wird dringend empfohlen, HTTPS über HTTP zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5989-114">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="b5989-115">HTTPS verwendet Zertifikate zum Verschlüsseln des Datenverkehrs.</span><span class="sxs-lookup"><span data-stu-id="b5989-115">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="b5989-116">HTTP bietet keine Verschlüsselung, und alle gesendeten Daten sind nur-Text.</span><span class="sxs-lookup"><span data-stu-id="b5989-116">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="b5989-117">Das neuausgeben von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Prozess.</span><span class="sxs-lookup"><span data-stu-id="b5989-117">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="b5989-118">Bei öffentlichen Zertifikaten, die in der Veröffentlichungsregel des Webdiensts verwendet werden, kann das Hinzufügen mehrerer alternativer Antragstellernamen teuer werden.</span><span class="sxs-lookup"><span data-stu-id="b5989-118">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="b5989-119">Um dieses Problem zu umgehen, unterstützen wir die anfängliche automatische Ermittlungs Verbindung über Port 80, die dann an Port 8080 auf dem Director oder Front-End-Server umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b5989-119">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b5989-120">Wenn Ihre lync Server 2013-Infrastruktur interne Zertifikate verwendet, die von einer internen Zertifizierungsstelle ausgestellt werden und Sie mobile Geräte mit Drahtlosverbindung unterstützen möchten, muss entweder die Stammzertifikatkette von der internen Zertifizierungsstelle auf den mobilen Geräten installiert sein, oder Sie müssen zu einem öffentlichen Zertifikat in ihrer lync Server 2013 Infrastruktur wechseln.</span><span class="sxs-lookup"><span data-stu-id="b5989-120">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="b5989-121">In diesem Thema werden die zusätzlichen alternativen Antragstellernamen beschrieben, die für Director, Front-End-Server und Reverse Proxy erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="b5989-121">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="b5989-122">Es wird nur auf die hinzugefügten alternativen Antragstellernamen (San) verwiesen.</span><span class="sxs-lookup"><span data-stu-id="b5989-122">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="b5989-123">In den Planungs Abschnitten erhalten Sie Anleitungen zu den anderen Einträgen in Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="b5989-123">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="b5989-124">Ausführliche Informationen finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)und [Szenarien für Reverse Proxy in lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="b5989-124">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="b5989-125">In den folgenden Tabellen werden die San-Einträge für die AutoErmittlung für die Directorpool, die Front-End-Pool und den Reverseproxy definiert:</span><span class="sxs-lookup"><span data-stu-id="b5989-125">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="b5989-126">Directorpool-Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="b5989-126">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5989-127">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5989-127">Description</span></span></th>
<th><span data-ttu-id="b5989-128">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="b5989-128">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5989-129">Interne URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="b5989-129">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b5989-130">San = "lyncdiscoverinternal". &lt; Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="b5989-130">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5989-131">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="b5989-131">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b5989-132">San = lyncdiscover. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="b5989-132">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b5989-133">Sie weisen das neu aktualisierte Zertifikat dem neuen San-Eintrag dem Standardzertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="b5989-133">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="b5989-134">Alternativ können Sie San = \* verwenden. &lt; sipdomain " &gt; .</span><span class="sxs-lookup"><span data-stu-id="b5989-134">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="b5989-135">Front-End-Pool-Zertifikatanforderungen</span><span class="sxs-lookup"><span data-stu-id="b5989-135">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5989-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5989-136">Description</span></span></th>
<th><span data-ttu-id="b5989-137">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="b5989-137">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5989-138">Interne URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="b5989-138">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b5989-139">San = "lyncdiscoverinternal". &lt; Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="b5989-139">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5989-140">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="b5989-140">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b5989-141">San = lyncdiscover. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="b5989-141">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b5989-142">Sie weisen das neu aktualisierte Zertifikat dem neuen San-Eintrag dem Standardzertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="b5989-142">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="b5989-143">Alternativ können Sie San = \* verwenden. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="b5989-143">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="b5989-144">Reverseproxy-Zertifikatanforderungen (öffentliche ZS)</span><span class="sxs-lookup"><span data-stu-id="b5989-144">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5989-145">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b5989-145">Description</span></span></th>
<th><span data-ttu-id="b5989-146">Eintrag für alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="b5989-146">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5989-147">Externe URL des AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="b5989-147">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="b5989-148">San = lyncdiscover. &lt; sipdomain "&gt;</span><span class="sxs-lookup"><span data-stu-id="b5989-148">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b5989-149">Sie weisen das neu aktualisierte Zertifikat dem neuen San-Eintrag dem SSL-Listener auf dem Reverseproxy zu.</span><span class="sxs-lookup"><span data-stu-id="b5989-149">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

