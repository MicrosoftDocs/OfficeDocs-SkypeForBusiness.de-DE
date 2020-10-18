---
title: 'Lync Server 2013: Zertifikatanforderungen für interne Server'
description: 'Lync Server 2013: Zertifikatanforderungen für interne Server.'
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
ms.openlocfilehash: dc1a627dd762c849b848087a96e00e19d320ef01
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575211"
---
# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="ff9dc-103">Zertifikatanforderungen für interne Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff9dc-103">Certificate requirements for internal servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff9dc-104">_**Letztes Änderungsstand des Themas:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="ff9dc-104">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="ff9dc-105">Zu den internen Servern, auf denen lync Server ausführt und für die Zertifikate erforderlich sind, gehören Standard Edition-Server, Enterprise Edition Front-End-Server, Vermittlungsserver und Director.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-105">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="ff9dc-106">Die folgende Tabelle zeigt die Zertifikatanforderungen für diese Server.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-106">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="ff9dc-107">Sie können den Assistenten für lync Server Zertifikate verwenden, um diese Zertifikate anzufordern.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-107">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="ff9dc-108">Platzhalterzertifikate werden für die alternativen Antragstellernamen unterstützt, die den einfachen URLs im Front-End-Pool, Front-End-Server oder Director zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-108">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="ff9dc-109">Ausführliche Informationen zur Unterstützung von Platzhalterzertifikaten finden Sie unter <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard Certificate Support in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-109">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ff9dc-110">Wenngleich für interne Server die Verwendung einer internen Unternehmenszertifizierungsstelle empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-110">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="ff9dc-111">Eine Liste der öffentlichen Zertifizierungsstellen mit Zertifikaten, die bestimmte Anforderungen an Unified Communications-Zertifikate (UC) erfüllen und mit Microsoft zusammenarbeiten, um sicherzustellen, dass Sie mit dem Assistenten für lync Server Zertifikate kompatibel sind, finden Sie in Artikel Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server" unter [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834) .</span><span class="sxs-lookup"><span data-stu-id="ff9dc-111">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="ff9dc-112">Für die Kommunikation mit anderen Anwendungen und Servern wie Exchange 2013 ist ein Zertifikat erforderlich, das von den anderen Anwendungen und Produkten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-112">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="ff9dc-113">Für das 2013-Release, lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, wird das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-113">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="ff9dc-114">Ausführliche Informationen finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-114">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="ff9dc-115">Für Verbindungen von Clients, die Windows 7 Betriebssystem, Windows Server 2008 Betriebssystem, Windows Server 2008 R2-Betriebssystem, Windows Vista Betriebssystem und Microsoft lync Phone Edition ausführen, enthält lync Server 2013 Unterstützung für (jedoch nicht erforderliche) Zertifikate, die mit der kryptografischen Hashfunktion von SHA-256 signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-115">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="ff9dc-116">Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-116">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="ff9dc-p106">In der folgenden Tabelle werden die Zertifikatanforderungen nach Serverrolle für Front-End-Pools und Standard Edition-Server aufgeführt. Es handelt sich in allen Fällen um standardmäßige, nicht exportierbare Webserverzertifikate mit privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="ff9dc-119">Beachten Sie, dass die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für Server automatisch konfiguriert wird, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-119">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff9dc-120">Jeder Zertifikatanzeige Name muss im Computerspeicher eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-120">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ff9dc-121">Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie Sie im alternativen Antragstellernamen des Zertifikats hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-121">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="ff9dc-122">Zertifikate für Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="ff9dc-122">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="ff9dc-123">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ff9dc-123">Certificate</span></span></th>
<th><span data-ttu-id="ff9dc-124">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="ff9dc-124">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ff9dc-125">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ff9dc-125">Subject alternative name</span></span></th>
<th><span data-ttu-id="ff9dc-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff9dc-126">Example</span></span></th>
<th><span data-ttu-id="ff9dc-127">Kommentare</span><span class="sxs-lookup"><span data-stu-id="ff9dc-127">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff9dc-128">Standard</span><span class="sxs-lookup"><span data-stu-id="ff9dc-128">Default</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-129">Vollqualifizierter Domänenname (FQDN) des Pools</span><span class="sxs-lookup"><span data-stu-id="ff9dc-129">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-130">FQDN des Pools und FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="ff9dc-130">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="ff9dc-131">Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-131">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="ff9dc-132">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).</span><span class="sxs-lookup"><span data-stu-id="ff9dc-132">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-133">SN = SE01. contoso. com; San = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-133">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="ff9dc-134">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".</span><span class="sxs-lookup"><span data-stu-id="ff9dc-134">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-135">Auf einem Standard Edition-Server entspricht der Server-FQDN dem Pool-FQDN.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-135">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="ff9dc-136">Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-136">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="ff9dc-137">Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-137">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9dc-138">Web, intern</span><span class="sxs-lookup"><span data-stu-id="ff9dc-138">Web internal</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-139">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="ff9dc-139">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-140">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-140">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff9dc-141">Interner Web-FQDN (entspricht dem FQDN des Servers)</span><span class="sxs-lookup"><span data-stu-id="ff9dc-141">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-142">Einfache URLs vom Typ "Meet"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-142">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-143">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-143">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-144">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-144">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-145">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="ff9dc-145">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff9dc-146">SN = SE01. contoso. com; San = SE01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-146">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="ff9dc-147">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-147">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="ff9dc-148">SN = SE01. contoso. com; San = SE01. contoso. com; San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-148">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-149">Sie können den internen webfqdn im Topologie-Generator nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-149">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="ff9dc-150">Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-150">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="ff9dc-151">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-151">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9dc-152">Web, extern</span><span class="sxs-lookup"><span data-stu-id="ff9dc-152">Web external</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-153">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="ff9dc-153">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-154">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-154">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff9dc-155">Externer Web-FQDN</span><span class="sxs-lookup"><span data-stu-id="ff9dc-155">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-156">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-156">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-157">Erfüllen einfacher URLs pro SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="ff9dc-157">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-158">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="ff9dc-158">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff9dc-159">SN = SE01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-159">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="ff9dc-160">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-160">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="ff9dc-161">SN = SE01. contoso. com; San = webcon01. contoso. com; San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-161">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-162">Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-162">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="ff9dc-163">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-163">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="ff9dc-164">Zertifikate für Front-End-Server in einem Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="ff9dc-164">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="ff9dc-165">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ff9dc-165">Certificate</span></span></th>
<th><span data-ttu-id="ff9dc-166">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="ff9dc-166">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ff9dc-167">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ff9dc-167">Subject alternative name</span></span></th>
<th><span data-ttu-id="ff9dc-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff9dc-168">Example</span></span></th>
<th><span data-ttu-id="ff9dc-169">Kommentare</span><span class="sxs-lookup"><span data-stu-id="ff9dc-169">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff9dc-170">Standard</span><span class="sxs-lookup"><span data-stu-id="ff9dc-170">Default</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-171">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="ff9dc-171">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-172">FQDN des Pools und FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="ff9dc-172">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="ff9dc-173">Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-173">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="ff9dc-174">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).</span><span class="sxs-lookup"><span data-stu-id="ff9dc-174">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-175">SN = EEpool. contoso. com; San = EEpool. contoso. com; San = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-175">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="ff9dc-176">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".</span><span class="sxs-lookup"><span data-stu-id="ff9dc-176">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-177">Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-177">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="ff9dc-178">Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-178">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9dc-179">Web, intern</span><span class="sxs-lookup"><span data-stu-id="ff9dc-179">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-180">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="ff9dc-180">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-181">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-181">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff9dc-182">Interner FQDN des Webs (nicht identisch mit dem FQDN des Servers)</span><span class="sxs-lookup"><span data-stu-id="ff9dc-182">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-183">Server-FQDN</span><span class="sxs-lookup"><span data-stu-id="ff9dc-183">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-184">Lync-Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="ff9dc-184">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-185">Einfache URLs vom Typ "Meet"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-185">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-186">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-186">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-187">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-187">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-188">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="ff9dc-188">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff9dc-189">SN = ee01. contoso. com; San = ee01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-189">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="ff9dc-190">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-190">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="ff9dc-191">SN = ee01. contoso. com; San = ee01. contoso. com; San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-191">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-192">Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-192">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="ff9dc-193">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-193">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9dc-194">Web, extern</span><span class="sxs-lookup"><span data-stu-id="ff9dc-194">Web external</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-195">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="ff9dc-195">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-196">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-196">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff9dc-197">Externer Web-FQDN</span><span class="sxs-lookup"><span data-stu-id="ff9dc-197">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-198">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-198">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-199">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-199">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-200">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="ff9dc-200">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff9dc-201">SN = ee01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-201">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="ff9dc-202">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-202">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="ff9dc-203">SN = ee01. contoso. com; San = webcon01. contoso. com; San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-203">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-204">Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-204">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="ff9dc-205">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-205">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="ff9dc-206">Zertifikate für Director</span><span class="sxs-lookup"><span data-stu-id="ff9dc-206">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff9dc-207">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ff9dc-207">Certificate</span></span></th>
<th><span data-ttu-id="ff9dc-208">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="ff9dc-208">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ff9dc-209">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ff9dc-209">Subject alternative name</span></span></th>
<th><span data-ttu-id="ff9dc-210">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff9dc-210">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff9dc-211">Standard</span><span class="sxs-lookup"><span data-stu-id="ff9dc-211">Default</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-212">FQDN des Director-Pools</span><span class="sxs-lookup"><span data-stu-id="ff9dc-212">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-213">Director-FQDN, FQDN des Director-Pools</span><span class="sxs-lookup"><span data-stu-id="ff9dc-213">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="ff9dc-214">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).</span><span class="sxs-lookup"><span data-stu-id="ff9dc-214">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-215">SN = dir-Pool.contoso.com; San = dir-Pool.contoso.com; San = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-215">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="ff9dc-216">Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".</span><span class="sxs-lookup"><span data-stu-id="ff9dc-216">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff9dc-217">Web, intern</span><span class="sxs-lookup"><span data-stu-id="ff9dc-217">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-218">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="ff9dc-218">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-219">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-219">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff9dc-220">Interner Web-FQDN (entspricht dem FQDN des Servers)</span><span class="sxs-lookup"><span data-stu-id="ff9dc-220">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-221">Server-FQDN</span><span class="sxs-lookup"><span data-stu-id="ff9dc-221">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-222">Lync-Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="ff9dc-222">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-223">Einfache URLs vom Typ "Meet"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-223">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-224">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-224">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-225">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-225">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-226">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="ff9dc-226">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff9dc-227">SN = dir01. contoso. com; San = dir01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-227">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="ff9dc-228">SN = dir01. contoso. com; San = dir01. contoso. com San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-228">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff9dc-229">Web, extern</span><span class="sxs-lookup"><span data-stu-id="ff9dc-229">Web external</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-230">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="ff9dc-230">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-231">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="ff9dc-231">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff9dc-232">Externer Web-FQDN</span><span class="sxs-lookup"><span data-stu-id="ff9dc-232">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-233">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-233">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-234">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="ff9dc-234">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="ff9dc-235">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="ff9dc-235">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="ff9dc-236">Der externe Director-webfqdn muss sich von dem Front-End-Pool oder Front-End-Server unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-236">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="ff9dc-237">SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="ff9dc-238">SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-238">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff9dc-p107">Wenn Sie über einen eigenständigen Vermittlungsserverpool verfügen, muss jeder der darin enthaltenen Vermittlungsserver über die in der folgenden Tabelle aufgelisteten Zertifikate verfügen. Wenn Sie einen Vermittlungsserver mit den Front-End-Servern verbinden, reichen die in der Tabelle "Zertifikate für Front-End-Server im Front-End-Pool" (weiter oben) aufgeführten Zertifikate aus.</span><span class="sxs-lookup"><span data-stu-id="ff9dc-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="ff9dc-241">Zertifikate für eigenständige Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="ff9dc-241">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff9dc-242">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ff9dc-242">Certificate</span></span></th>
<th><span data-ttu-id="ff9dc-243">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="ff9dc-243">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ff9dc-244">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ff9dc-244">Subject alternative name</span></span></th>
<th><span data-ttu-id="ff9dc-245">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff9dc-245">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff9dc-246">Standard</span><span class="sxs-lookup"><span data-stu-id="ff9dc-246">Default</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-247">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="ff9dc-247">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-248">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="ff9dc-248">FQDN of the pool</span></span></p>
<p><span data-ttu-id="ff9dc-249">FQDN des Poolmitgliedsservers</span><span class="sxs-lookup"><span data-stu-id="ff9dc-249">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-250">SN = medsvr-Pool.contoso.net; San = medsvr-Pool.contoso.net; San = medsvr01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="ff9dc-250">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="ff9dc-251">Zertifikate für eine Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="ff9dc-251">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff9dc-252">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="ff9dc-252">Certificate</span></span></th>
<th><span data-ttu-id="ff9dc-253">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="ff9dc-253">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="ff9dc-254">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="ff9dc-254">Subject alternative name</span></span></th>
<th><span data-ttu-id="ff9dc-255">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ff9dc-255">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff9dc-256">Standard</span><span class="sxs-lookup"><span data-stu-id="ff9dc-256">Default</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-257">FQDN der Appliance</span><span class="sxs-lookup"><span data-stu-id="ff9dc-257">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-258">SIP. &lt; sipdomain " &gt; (benötigt einen Eintrag pro SIP-Domäne)</span><span class="sxs-lookup"><span data-stu-id="ff9dc-258">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="ff9dc-259">SN = sba01. contoso. net; San = SIP. contoso. com; San = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="ff9dc-259">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="ff9dc-260">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff9dc-260">See Also</span></span>


[<span data-ttu-id="ff9dc-261">Unterstützung von Platzhalterzertifikaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ff9dc-261">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

