---
title: 'Lync Server 2013: Zertifikatzusammenfassung – AutoErmittlung'
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
ms.openlocfilehash: 8956c8a0ed4e149f336e6670aaf5b262f1868748
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736665"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a><span data-ttu-id="a8a6e-102">Zertifikatzusammenfassung – AutoErmittlung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a8a6e-102">Certificate summary - Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8a6e-103">_**Letztes Änderungsdatum des Themas:** 2013-02-14_</span><span class="sxs-lookup"><span data-stu-id="a8a6e-103">_**Topic Last Modified:** 2013-02-14_</span></span>

<span data-ttu-id="a8a6e-104">Der lync Server 2013-AutoErmittlungsdienst wird auf den Director-und Front-End-Pool Servern ausgeführt und kann bei Veröffentlichung in DNS von lync-Clients zum Auffinden von Server-und Benutzerdiensten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-104">The Lync Server 2013 Autodiscover Service runs on the Director and Front End pool servers, and when published in DNS, can be used by Lync clients to locate server and user services.</span></span> <span data-ttu-id="a8a6e-105">Wenn Sie ein Upgrade von lync Server 2010 durchführen und keine Mobilität bereitstellen, bevor Clients die automatische Ermittlung verwenden können, müssen Sie die Listen für alternative Namen für Zertifikats Subjekte auf jedem Director-und Front-End-Server ändern, auf dem der AutoErmittlungsdienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-105">If you are upgrading from Lync Server 2010 and did not deploy Mobility, before clients can use automatic discovery, you must modify certificate subject alternative name lists on any Director and Front End Server running the Autodiscover Service.</span></span> <span data-ttu-id="a8a6e-106">Darüber hinaus ist es möglicherweise erforderlich, die Listen Betreff alternativer Name auf Zertifikaten zu ändern, die für externe Webdienst Veröffentlichungsregeln für umgekehrte Proxys verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-106">In addition, it may be necessary to modify the subject alternative name lists on certificates used for external web service publishing rules on reverse proxies.</span></span>

<span data-ttu-id="a8a6e-107">Die Entscheidung darüber, ob die Listen Betreff alternativer Namen in umgekehrten Proxys verwendet werden, basiert darauf, ob Sie den AutoErmittlungsdienst auf Port 80 oder auf Port 443 veröffentlichen:</span><span class="sxs-lookup"><span data-stu-id="a8a6e-107">The decision about whether to use subject alternative name lists on reverse proxies is based on whether you publish the Autodiscover Service on port 80 or on port 443:</span></span>

  - <span data-ttu-id="a8a6e-108">**Veröffentlicht auf Port 80**   es sind keine Zertifikat Änderungen erforderlich, wenn die ursprüngliche Abfrage des AutoErmittlungsdiensts über Port 80 erfolgt.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-108">**Published on port 80**   No certificate changes are required if the initial query to the Autodiscover Service occurs over port 80.</span></span> <span data-ttu-id="a8a6e-109">Dies liegt daran, dass Mobile Geräte, auf denen lync ausgeführt wird, auf den Reverseproxy auf Port 80 extern zugreifen und dann intern mit einem Director oder Front-End-Server auf Port 8080 überbrückt werden.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-109">This is because mobile devices running Lync will access the reverse proxy on port 80 externally and then be bridged to a Director or Front End Server on port 8080 internally.</span></span> <span data-ttu-id="a8a6e-110">Ausführliche Informationen finden Sie im Abschnitt "ursprünglicher Auto Ermittlungsprozess mit Port 80" unter [Technische Voraussetzungen für Mobilität in lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="a8a6e-110">For details, see the "Initial Autodiscover Process Using Port 80" section [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md).</span></span>

  - <span data-ttu-id="a8a6e-111">**Veröffentlicht auf Port 443**   die Liste der alternativen Subjektnamen für Zertifikate, die von der externen Webdienste-Veröffentlichungsregel verwendet werden, muss eine \*lyncdiscover enthalten.\< sipdomain\> \* -Eintrag für jede SIP-Domäne innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-111">**Published on port 443**   The subject alternative name list on certificates used by the external web services publishing rule must contain a *lyncdiscover.\<sipdomain\>* entry for each SIP domain within your organization.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a8a6e-112">Es wird dringend empfohlen, HTTPS über HTTP zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-112">We highly recommend using HTTPS over HTTP.</span></span> <span data-ttu-id="a8a6e-113">HTTPS verwendet Zertifikate, um den Datenverkehr zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-113">HTTPS uses certificates to encrypt traffic.</span></span> <span data-ttu-id="a8a6e-114">HTTP bietet keine Verschlüsselung, und die gesendeten Daten sind nur Text.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-114">HTTP does not provide for encryption, and any data sent will be plain text.</span></span>

    
    </div>

<span data-ttu-id="a8a6e-115">Das erneute ausgeben von Zertifikaten mithilfe einer internen Zertifizierungsstelle ist in der Regel ein einfacher Prozess.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-115">Reissuing certificates by using an internal certificate authority is typically a simple process.</span></span> <span data-ttu-id="a8a6e-116">Bei öffentlichen Zertifikaten, die für die Veröffentlichungsregel des Webdiensts verwendet werden, kann das Hinzufügen von Einträgen mit mehreren Alternativen Subjekten teuer werden.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-116">But for public certificates used on the web service publishing rule, adding multiple subject alternative name entries can become expensive.</span></span> <span data-ttu-id="a8a6e-117">Um dieses Problem zu umgehen, unterstützen wir die anfängliche automatische Ermittlungs Verbindung über Port 80, die dann auf Port 8080 auf dem Director-oder Front-End-Server umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-117">To work around this issue, we support the initial automatic discovery connection over port 80, which is then redirected to port 8080 on the Director or Front End Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a8a6e-118">Wenn Ihre lync Server 2013-Infrastruktur interne Zertifikate verwendet, die von einer internen Zertifizierungsstelle (Certification Authority, ca) ausgestellt wurden und Sie beabsichtigen, Mobile Geräte drahtlos zu unterstützen, muss entweder die Stammzertifikatkette von der internen Zertifizierungsstelle installiert werden. auf den mobilen Geräten oder müssen Sie zu einem öffentlichen Zertifikat in ihrer lync Server 2013-Infrastruktur wechseln.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-118">If your Lync Server 2013 infrastructure uses internal certificates that are issued from an internal certification authority (CA) and you plan to support mobile devices connecting wirelessly, either the root certificate chain from the internal CA must be installed on the mobile devices or you must change to a public certificate on your Lync Server 2013 infrastructure.</span></span>



</div>

<span data-ttu-id="a8a6e-119">In diesem Thema werden die für Director, Front-End-Server und Reverse Proxy erforderlichen zusätzlichen alternativen Namen für Subjekte beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-119">This topic describes the added subject alternative names required for the Director, Front End Server and reverse proxy.</span></span> <span data-ttu-id="a8a6e-120">Es werden nur die zusätzlichen alternativen Namen (Subject Alternative Names, San) referenziert.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-120">Only the added subject alternative names (SAN) are referenced.</span></span> <span data-ttu-id="a8a6e-121">In den Planungs Abschnitten finden Sie Anleitungen zu den anderen Einträgen auf Zertifikaten.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-121">Refer to the planning sections for guidance on the other entries on certificates.</span></span> <span data-ttu-id="a8a6e-122">Ausführliche Informationen finden Sie unter [Szenarien für den Director in lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Szenarien für den Zugriff durch externe Benutzer in lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)und [Szenarien für den Reverse Proxy in lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="a8a6e-122">For details, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md), [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md), and [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md).</span></span>

<span data-ttu-id="a8a6e-123">In den folgenden Tabellen werden die San-Einträge für die AutoErmittlung für den Director-Pool, den Front-End-Pool und den Reverse-Proxy definiert:</span><span class="sxs-lookup"><span data-stu-id="a8a6e-123">The following tables define the Autodiscover SAN entries for the Director pool, the Front End pool, and the reverse proxy:</span></span>

### <a name="director-pool-certificate-requirements"></a><span data-ttu-id="a8a6e-124">Anforderungen des Director-Pool Zertifikats</span><span class="sxs-lookup"><span data-stu-id="a8a6e-124">Director Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8a6e-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8a6e-125">Description</span></span></th>
<th><span data-ttu-id="a8a6e-126">Eintrag für den alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="a8a6e-126">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8a6e-127">URL des internen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="a8a6e-127">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a8a6e-128">San = lyncdiscoverinternal. &lt;Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="a8a6e-128">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8a6e-129">URL des externen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="a8a6e-129">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a8a6e-130">San = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a8a6e-130">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a8a6e-131">Sie weisen das neu aktualisierte Zertifikat mit dem neuen San-Eintrag dem Standardzertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-131">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="a8a6e-132">Sie können auch San = \* verwenden. &lt;sipdomain&gt;.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-132">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;.</span></span>



</div>

### <a name="front-end-pool-certificate-requirements"></a><span data-ttu-id="a8a6e-133">Anforderungen für das Front-End-Pool Zertifikat</span><span class="sxs-lookup"><span data-stu-id="a8a6e-133">Front End Pool Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8a6e-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8a6e-134">Description</span></span></th>
<th><span data-ttu-id="a8a6e-135">Eintrag für den alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="a8a6e-135">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8a6e-136">URL des internen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="a8a6e-136">Internal Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a8a6e-137">San = lyncdiscoverinternal. &lt;Interner Domänenname&gt;</span><span class="sxs-lookup"><span data-stu-id="a8a6e-137">SAN=lyncdiscoverinternal.&lt;internal domain name&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8a6e-138">URL des externen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="a8a6e-138">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a8a6e-139">San = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a8a6e-139">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a8a6e-140">Sie weisen das neu aktualisierte Zertifikat mit dem neuen San-Eintrag dem Standardzertifikat zu.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-140">You assign the newly updated certificate with the new SAN entry to the Default certificate.</span></span> <span data-ttu-id="a8a6e-141">Sie können auch San = \* verwenden. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a8a6e-141">Alternatively, you can use SAN=\*.&lt;sipdomain&gt;</span></span>



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a><span data-ttu-id="a8a6e-142">Zertifikatanforderungen für Reverse Proxy (öffentliche Zertifizierungsstelle)</span><span class="sxs-lookup"><span data-stu-id="a8a6e-142">Reverse Proxy (Public CA) Certificate Requirements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8a6e-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a8a6e-143">Description</span></span></th>
<th><span data-ttu-id="a8a6e-144">Eintrag für den alternativen Antragstellernamen</span><span class="sxs-lookup"><span data-stu-id="a8a6e-144">Subject alternative name entry</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8a6e-145">URL des externen AutoErmittlungsdiensts</span><span class="sxs-lookup"><span data-stu-id="a8a6e-145">External Autodiscover Service URL</span></span></p></td>
<td><p><span data-ttu-id="a8a6e-146">San = lyncdiscover. &lt;sipdomain&gt;</span><span class="sxs-lookup"><span data-stu-id="a8a6e-146">SAN=lyncdiscover.&lt;sipdomain&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="a8a6e-147">Sie weisen das neu aktualisierte Zertifikat dem SSL-Listener auf dem Reverse-Proxy mit dem neuen San-Eintrag zu.</span><span class="sxs-lookup"><span data-stu-id="a8a6e-147">You assign the newly updated certificate with the new SAN entry to the SSL Listener on the reverse proxy.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

