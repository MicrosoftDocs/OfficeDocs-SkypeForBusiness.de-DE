---
title: 'Lync Server 2013: Anforderungen an Zertifikate für interne Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for internal servers
ms:assetid: 0444cdbd-538c-43b1-b9a1-9d7d6cf818d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398094(v=OCS.15)
ms:contentKeyID: 48183270
ms.date: 02/17/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0351ab4f54273e1eccc09992ab933525cc2527ae
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="aad7f-102">Anforderungen an Zertifikate für interne Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aad7f-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aad7f-103">_**Letztes Änderungsdatum des Themas:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="aad7f-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="aad7f-104">Zu den internen Servern, auf denen lync Server ausgeführt wird und für die Zertifikate erforderlich sind, gehören Standard Edition-Server, Enterprise Edition-Front-End-Server, Vermittlungsserver und Director.</span><span class="sxs-lookup"><span data-stu-id="aad7f-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="aad7f-105">In der folgenden Tabelle sind die Zertifikatanforderungen für diese Server aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="aad7f-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="aad7f-106">Sie können den lync Server-Zertifikat-Assistenten verwenden, um diese Zertifikate anzufordern.</span><span class="sxs-lookup"><span data-stu-id="aad7f-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="aad7f-107">Platzhalterzertifikate werden für die alternativen Subjektnamen unterstützt, die mit den einfachen URLs im Front-End-Pool, Front-End-Server oder Director verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="aad7f-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="aad7f-108">Details zur Unterstützung von Platzhalterzertifikaten finden Sie unter <A href="lync-server-2013-wildcard-certificate-support.md">Unterstützung für Platzhalterzertifikate in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aad7f-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="aad7f-109">Obwohl eine interne Unternehmenszertifizierungsstelle für interne Server empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="aad7f-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="aad7f-110">Eine Liste der öffentlichen Zertifizierungsstellen, die Zertifikate zur Verfügung stellen, die bestimmte Anforderungen für Unified Communications (UC)-Zertifikate erfüllen und mit Microsoft zusammenarbeiten, um sicherzustellen, dass Sie mit dem lync Server-Zertifikat-Assistenten funktionieren, finden Sie im [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)Artikel Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners für Exchange Server und für Communications Server" unter.</span><span class="sxs-lookup"><span data-stu-id="aad7f-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="aad7f-111">Die Kommunikation mit anderen Anwendungen und Servern, wie etwa Exchange 2013, erfordert ein Zertifikat, das von den anderen Anwendungen und Produkten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="aad7f-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="aad7f-112">Für die 2013-Version unterstützen lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="aad7f-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="aad7f-113">Ausführliche Informationen finden Sie unter [Verwalten der Server-zu-Server-Authentifizierung (OAuth) und der Partneranwendungen in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="aad7f-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="aad7f-114">Für Verbindungen von Clients mit Windows 7-Betriebssystem, Windows Server 2008-Betriebssystem, Windows Server 2008 R2-Betriebssystem, Windows Vista-Betriebssystem und Microsoft lync Phone Edition umfasst lync Server 2013 Unterstützung für (aber nicht require) Zertifikate, die mit der SHA-256-kryptografischen Hashfunktion signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="aad7f-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="aad7f-115">Um den externen Zugriff mithilfe von SHA-256 zu unterstützen, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle mithilfe von SHA-256 ausgestellt.</span><span class="sxs-lookup"><span data-stu-id="aad7f-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="aad7f-116">In den folgenden Tabellen werden die Zertifikatanforderungen nach Serverrolle für Front-End-Pools und Standard Edition-Server angezeigt.</span><span class="sxs-lookup"><span data-stu-id="aad7f-116">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers.</span></span> <span data-ttu-id="aad7f-117">Dies sind standardmäßige Webserverzertifikate, privater Schlüssel, nicht exportierbarer Server.</span><span class="sxs-lookup"><span data-stu-id="aad7f-117">All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="aad7f-118">Beachten Sie, dass die erweiterte Schlüsselverwendung von Server automatisch konfiguriert wird, wenn Sie mit dem Zertifikat-Assistenten Zertifikate anfordern.</span><span class="sxs-lookup"><span data-stu-id="aad7f-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="aad7f-119">Jeder Zertifikatsanzeige Name muss im Computerspeicher eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="aad7f-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="aad7f-120">Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie diese im alternativen Antragstellernamen des Zertifikats hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="aad7f-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="aad7f-121">Zertifikate für den Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="aad7f-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="aad7f-122">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="aad7f-122">Certificate</span></span></th>
<th><span data-ttu-id="aad7f-123">Name des Antragstellers/gebräuchlicher Name</span><span class="sxs-lookup"><span data-stu-id="aad7f-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="aad7f-124">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="aad7f-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="aad7f-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aad7f-125">Example</span></span></th>
<th><span data-ttu-id="aad7f-126">Kommentare</span><span class="sxs-lookup"><span data-stu-id="aad7f-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aad7f-127">Standard</span><span class="sxs-lookup"><span data-stu-id="aad7f-127">Default</span></span></p></td>
<td><p><span data-ttu-id="aad7f-128">Vollqualifizierten Domänennamen (Fully Qualified Domain Name, FQDN) des Pools</span><span class="sxs-lookup"><span data-stu-id="aad7f-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="aad7f-129">FQDN des Pools und der FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="aad7f-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="aad7f-130">Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</span><span class="sxs-lookup"><span data-stu-id="aad7f-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="aad7f-131">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für „sip.sipDomäne“ (für jede vorhandene SIP-Domäne).</span><span class="sxs-lookup"><span data-stu-id="aad7f-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="aad7f-132">SN=se01.contoso.com; SAN=se01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="aad7f-133">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.</span><span class="sxs-lookup"><span data-stu-id="aad7f-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="aad7f-134">Auf dem Standard Edition-Server entspricht der Server-FQDN dem FQDN des Pools.</span><span class="sxs-lookup"><span data-stu-id="aad7f-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="aad7f-135">Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.</span><span class="sxs-lookup"><span data-stu-id="aad7f-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="aad7f-136">Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="aad7f-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aad7f-137">Web, intern</span><span class="sxs-lookup"><span data-stu-id="aad7f-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="aad7f-138">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="aad7f-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="aad7f-139">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="aad7f-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aad7f-140">Interner Web-FQDN (entspricht dem FQDN des Servers)</span><span class="sxs-lookup"><span data-stu-id="aad7f-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="aad7f-141">Einfache Besprechungs-URLs</span><span class="sxs-lookup"><span data-stu-id="aad7f-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="aad7f-142">Einfache URLs vom Typ „Dialin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-143">Einfache URLs vom Typ „Admin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-144">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="aad7f-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aad7f-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="aad7f-146">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="aad7f-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="aad7f-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aad7f-148">Sie können den internen Web-FQDN im Topologie-Generator nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="aad7f-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="aad7f-149">Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="aad7f-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="aad7f-150">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aad7f-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aad7f-151">Web, extern</span><span class="sxs-lookup"><span data-stu-id="aad7f-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="aad7f-152">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="aad7f-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="aad7f-153">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="aad7f-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aad7f-154">Externer Web-FQDN</span><span class="sxs-lookup"><span data-stu-id="aad7f-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="aad7f-155">Einfache URLs vom Typ „Dialin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-156">Einfache Besprechungs-URLs pro SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="aad7f-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="aad7f-157">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="aad7f-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aad7f-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="aad7f-159">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="aad7f-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="aad7f-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aad7f-161">Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="aad7f-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="aad7f-162">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aad7f-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="aad7f-163">Zertifikate für den Front-End-Server in einem Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="aad7f-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="aad7f-164">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="aad7f-164">Certificate</span></span></th>
<th><span data-ttu-id="aad7f-165">Name des Antragstellers/gebräuchlicher Name</span><span class="sxs-lookup"><span data-stu-id="aad7f-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="aad7f-166">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="aad7f-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="aad7f-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aad7f-167">Example</span></span></th>
<th><span data-ttu-id="aad7f-168">Kommentare</span><span class="sxs-lookup"><span data-stu-id="aad7f-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aad7f-169">Standard</span><span class="sxs-lookup"><span data-stu-id="aad7f-169">Default</span></span></p></td>
<td><p><span data-ttu-id="aad7f-170">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="aad7f-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="aad7f-171">FQDN des Pools und FQDN des Servers.</span><span class="sxs-lookup"><span data-stu-id="aad7f-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="aad7f-172">Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</span><span class="sxs-lookup"><span data-stu-id="aad7f-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="aad7f-173">Wenn dieser Pool der Server für die automatische Anmeldung für Clients ist und in Gruppenrichtlinien strikter DNS-Abgleich erforderlich ist, benötigen Sie auch Einträge für SIP. sipdomain (für jede SIP-Domäne, die Sie haben).</span><span class="sxs-lookup"><span data-stu-id="aad7f-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="aad7f-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com </span><span class="sxs-lookup"><span data-stu-id="aad7f-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="aad7f-175">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch „SAN=sip.contoso.com; SAN=sip.fabrikam.com“.</span><span class="sxs-lookup"><span data-stu-id="aad7f-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="aad7f-176">Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie automatisch zum alternativen Antragstellernamen (SAN) hinzu.</span><span class="sxs-lookup"><span data-stu-id="aad7f-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="aad7f-177">Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="aad7f-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aad7f-178">Web-intern</span><span class="sxs-lookup"><span data-stu-id="aad7f-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="aad7f-179">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="aad7f-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="aad7f-180">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="aad7f-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aad7f-181">Interner Web-FQDN (entspricht NICHT dem FQDN des Servers)</span><span class="sxs-lookup"><span data-stu-id="aad7f-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="aad7f-182">Server-FQDN</span><span class="sxs-lookup"><span data-stu-id="aad7f-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="aad7f-183">Lync-Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="aad7f-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="aad7f-184">Einfache Besprechungs-URLs</span><span class="sxs-lookup"><span data-stu-id="aad7f-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="aad7f-185">Einfache URLs vom Typ „Dialin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-186">Einfache URLs vom Typ „Admin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-187">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="aad7f-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aad7f-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="aad7f-189">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="aad7f-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="aad7f-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aad7f-191">Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="aad7f-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="aad7f-192">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aad7f-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aad7f-193">Web, extern</span><span class="sxs-lookup"><span data-stu-id="aad7f-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="aad7f-194">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="aad7f-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="aad7f-195">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="aad7f-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aad7f-196">Externer Web-FQDN</span><span class="sxs-lookup"><span data-stu-id="aad7f-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="aad7f-197">Einfache URLs vom Typ „Dialin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-198">Einfache URLs vom Typ „Admin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-199">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="aad7f-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aad7f-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="aad7f-201">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="aad7f-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="aad7f-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="aad7f-203">Wenn Sie über mehrere einfache URLs für Besprechungen verfügen, müssen Sie diese als Alternativen Betreff-Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="aad7f-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="aad7f-204">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="aad7f-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="aad7f-205">Zertifikate für Director</span><span class="sxs-lookup"><span data-stu-id="aad7f-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aad7f-206">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="aad7f-206">Certificate</span></span></th>
<th><span data-ttu-id="aad7f-207">Name des Antragstellers/gebräuchlicher Name</span><span class="sxs-lookup"><span data-stu-id="aad7f-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="aad7f-208">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="aad7f-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="aad7f-209">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aad7f-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aad7f-210">Standard</span><span class="sxs-lookup"><span data-stu-id="aad7f-210">Default</span></span></p></td>
<td><p><span data-ttu-id="aad7f-211">FQDN des Director-Pools</span><span class="sxs-lookup"><span data-stu-id="aad7f-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="aad7f-212">FQDN des Directors, FQDN des Director-Pools</span><span class="sxs-lookup"><span data-stu-id="aad7f-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="aad7f-213">Wenn dieser Pool der Server für die automatische Anmeldung für Clients ist und in Gruppenrichtlinien strikter DNS-Abgleich erforderlich ist, benötigen Sie auch Einträge für SIP. sipdomain (für jede SIP-Domäne, die Sie haben).</span><span class="sxs-lookup"><span data-stu-id="aad7f-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="aad7f-214">SN = dir-Pool.contoso.com; San = dir-Pool.contoso.com; San = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="aad7f-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="aad7f-215">Wenn dieser Director-Pool der Server für die automatische Anmeldung für Clients ist und in Gruppenrichtlinien strikter DNS-Abgleich erforderlich ist, benötigen Sie auch San = SIP. contoso. com; San = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="aad7f-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aad7f-216">Web-intern</span><span class="sxs-lookup"><span data-stu-id="aad7f-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="aad7f-217">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="aad7f-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="aad7f-218">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="aad7f-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aad7f-219">Interner Web-FQDN (entspricht dem FQDN des Servers)</span><span class="sxs-lookup"><span data-stu-id="aad7f-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="aad7f-220">Server-FQDN</span><span class="sxs-lookup"><span data-stu-id="aad7f-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="aad7f-221">Lync-Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="aad7f-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="aad7f-222">Einfache Besprechungs-URLs</span><span class="sxs-lookup"><span data-stu-id="aad7f-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="aad7f-223">Einfache URLs vom Typ „Dialin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-224">Einfache URLs vom Typ „Admin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-225">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="aad7f-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aad7f-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="aad7f-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aad7f-228">Web, extern</span><span class="sxs-lookup"><span data-stu-id="aad7f-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="aad7f-229">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="aad7f-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="aad7f-230">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="aad7f-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="aad7f-231">Externer Web-FQDN</span><span class="sxs-lookup"><span data-stu-id="aad7f-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="aad7f-232">Einfache URLs vom Typ „Dialin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-233">Einfache URLs vom Typ „Admin“</span><span class="sxs-lookup"><span data-stu-id="aad7f-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="aad7f-234">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="aad7f-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="aad7f-235">Der FQDN des Director External Web muss vom Front-End-Pool oder Front-End-Server abweichen.</span><span class="sxs-lookup"><span data-stu-id="aad7f-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="aad7f-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="aad7f-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="aad7f-238">Wenn Sie über einen eigenständigen vermittlungsserverpool verfügen, benötigen die Vermittlungsserver jeweils die in der folgenden Tabelle aufgelisteten Zertifikate.</span><span class="sxs-lookup"><span data-stu-id="aad7f-238">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table.</span></span> <span data-ttu-id="aad7f-239">Wenn Sie den Vermittlungs Server mit den Front-End-Servern collocate, genügen die Zertifikate, die in der Tabelle "Zertifikate für Front-End-Server im Front-End-Pool" weiter oben in diesem Thema aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="aad7f-239">If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="aad7f-240">Zertifikate für eigenständigen Vermittlungs Server</span><span class="sxs-lookup"><span data-stu-id="aad7f-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aad7f-241">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="aad7f-241">Certificate</span></span></th>
<th><span data-ttu-id="aad7f-242">Name des Antragstellers/gebräuchlicher Name</span><span class="sxs-lookup"><span data-stu-id="aad7f-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="aad7f-243">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="aad7f-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="aad7f-244">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aad7f-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aad7f-245">Standard</span><span class="sxs-lookup"><span data-stu-id="aad7f-245">Default</span></span></p></td>
<td><p><span data-ttu-id="aad7f-246">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="aad7f-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="aad7f-247">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="aad7f-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="aad7f-248">FQDN des Pool Mitgliedsservers</span><span class="sxs-lookup"><span data-stu-id="aad7f-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="aad7f-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="aad7f-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="aad7f-250">Zertifikate für Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="aad7f-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aad7f-251">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="aad7f-251">Certificate</span></span></th>
<th><span data-ttu-id="aad7f-252">Name des Antragstellers/gebräuchlicher Name</span><span class="sxs-lookup"><span data-stu-id="aad7f-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="aad7f-253">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="aad7f-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="aad7f-254">Beispiel</span><span class="sxs-lookup"><span data-stu-id="aad7f-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aad7f-255">Standard</span><span class="sxs-lookup"><span data-stu-id="aad7f-255">Default</span></span></p></td>
<td><p><span data-ttu-id="aad7f-256">FQDN der Anwendung</span><span class="sxs-lookup"><span data-stu-id="aad7f-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="aad7f-257">SIP. &lt;sipdomain&gt; (benötigt einen Eintrag pro SIP-Domäne)</span><span class="sxs-lookup"><span data-stu-id="aad7f-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="aad7f-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="aad7f-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="aad7f-259">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aad7f-259">See Also</span></span>


[<span data-ttu-id="aad7f-260">Unterstützung von Platzhalterzertifikaten in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aad7f-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

