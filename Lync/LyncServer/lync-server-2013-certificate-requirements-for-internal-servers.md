---
title: 'Lync Server 2013: Zertifikatanforderungen für interne Server'
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
ms.openlocfilehash: 38bd350a4b552d63b635f8ec5a25ed7803de4b55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-internal-servers-in-lync-server-2013"></a><span data-ttu-id="4083b-102">Zertifikatanforderungen für interne Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4083b-102">Certificate requirements for internal servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4083b-103">_**Letztes Änderungsstand des Themas:** 2017-02-17_</span><span class="sxs-lookup"><span data-stu-id="4083b-103">_**Topic Last Modified:** 2017-02-17_</span></span>

<span data-ttu-id="4083b-104">Zu den internen Servern, auf denen lync Server ausführt und für die Zertifikate erforderlich sind, gehören Standard Edition-Server, Enterprise Edition Front-End-Server, Vermittlungsserver und Director.</span><span class="sxs-lookup"><span data-stu-id="4083b-104">Internal servers that are running Lync Server and that require certificates include Standard Edition server, Enterprise Edition Front End Server, Mediation Server, and Director.</span></span> <span data-ttu-id="4083b-105">Die folgende Tabelle zeigt die Zertifikatanforderungen für diese Server.</span><span class="sxs-lookup"><span data-stu-id="4083b-105">The following table shows the certificate requirements for these servers.</span></span> <span data-ttu-id="4083b-106">Sie können den Assistenten für lync Server Zertifikate verwenden, um diese Zertifikate anzufordern.</span><span class="sxs-lookup"><span data-stu-id="4083b-106">You can use the Lync Server certificate wizard to request these certificates.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4083b-107">Platzhalterzertifikate werden für die alternativen Antragstellernamen unterstützt, die den einfachen URLs im Front-End-Pool, Front-End-Server oder Director zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4083b-107">Wildcard certificates are supported for the subject alternative names associated with the simple URLs on the Front End pool, Front End Server, or Director.</span></span> <span data-ttu-id="4083b-108">Ausführliche Informationen zur Unterstützung von Platzhalterzertifikaten finden Sie unter <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard Certificate Support in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4083b-108">For details about wildcard certificate support, see <A href="lync-server-2013-wildcard-certificate-support.md">Wildcard certificate support in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="4083b-109">Wenngleich für interne Server die Verwendung einer internen Unternehmenszertifizierungsstelle empfohlen wird, können Sie auch eine öffentliche Zertifizierungsstelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="4083b-109">Although an internal enterprise certification authority (CA) is recommended for internal servers, you can also use a public CA.</span></span> <span data-ttu-id="4083b-110">Eine Liste der öffentlichen Zertifizierungsstellen mit Zertifikaten, die bestimmte Anforderungen an Unified Communications-Zertifikate (UC) erfüllen und mit Microsoft zusammenarbeiten, um sicherzustellen, dass Sie mit dem Assistenten für lync Server Zertifikate kompatibel sind, finden Sie in [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)Artikel Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server" unter.</span><span class="sxs-lookup"><span data-stu-id="4083b-110">For a list of public CAs that provide certificates that comply with specific requirements for unified communications (UC) certificates and have partnered with Microsoft to ensure they work with the Lync Server Certificate Wizard, see article Microsoft Knowledge Base 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<span data-ttu-id="4083b-111">Für die Kommunikation mit anderen Anwendungen und Servern wie Exchange 2013 ist ein Zertifikat erforderlich, das von den anderen Anwendungen und Produkten unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="4083b-111">Communication with other applications and servers, such as Exchange 2013, requires a certificate that is supported by the other applications and products.</span></span> <span data-ttu-id="4083b-112">Für das 2013-Release, lync Server 2013 und andere Microsoft-Serverprodukte, einschließlich Exchange 2013 und SharePoint Server, wird das Open Authorization (OAuth)-Protokoll für die Server-zu-Server-Authentifizierung und-Autorisierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4083b-112">For the 2013 release, Lync Server 2013 and other Microsoft server products, including Exchange 2013 and SharePoint Server, support the Open Authorization (OAuth) protocol for server-to-server authentication and authorization.</span></span> <span data-ttu-id="4083b-113">Ausführliche Informationen finden Sie unter [Managing Server-to-Server Authentication (OAuth) and Partner Applications in lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in der Bereitstellungsdokumentation oder in der Betriebsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="4083b-113">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) in the Deployment documentation or the Operations documentation.</span></span>

<span data-ttu-id="4083b-114">Für Verbindungen von Clients, die Windows 7 Betriebssystem, Windows Server 2008 Betriebssystem, Windows Server 2008 R2-Betriebssystem, Windows Vista Betriebssystem und Microsoft lync Phone Edition ausführen, enthält lync Server 2013 Unterstützung für (aber keine erfordern) Zertifikate, die mit der kryptografischen Hashfunktion von SHA-256 signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4083b-114">For connections from clients running Windows 7 operating system, Windows Server 2008 operating system, Windows Server 2008 R2 operating system, Windows Vista operating system, and Microsoft Lync Phone Edition, Lync Server 2013 includes support for (but does not require) certificates signed using the SHA-256 cryptographic hash function.</span></span> <span data-ttu-id="4083b-115">Damit der externe Zugriff über SHA-256 unterstützt wird, wird das externe Zertifikat von einer öffentlichen Zertifizierungsstelle ausgestellt, die SHA-256 verwendet.</span><span class="sxs-lookup"><span data-stu-id="4083b-115">To support external access using SHA-256, the external certificate is issued by a public CA using SHA-256.</span></span>

<span data-ttu-id="4083b-p106">In der folgenden Tabelle werden die Zertifikatanforderungen nach Serverrolle für Front-End-Pools und Standard Edition-Server aufgeführt. Es handelt sich in allen Fällen um standardmäßige, nicht exportierbare Webserverzertifikate mit privatem Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="4083b-p106">The following tables show certificate requirements by server role for Front End pools and Standard Edition servers. All these are standard web server certificates, private key, non-exportable.</span></span>

<span data-ttu-id="4083b-118">Beachten Sie, dass die erweiterte Schlüsselverwendung (Enhanced Key Usage, EKU) für Server automatisch konfiguriert wird, wenn Sie den Zertifikat-Assistenten zum Anfordern von Zertifikaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4083b-118">Note that server enhanced key usage (EKU) is automatically configured when you use the certificate wizard to request certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4083b-119">Jeder Zertifikatanzeige Name muss im Computerspeicher eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="4083b-119">Each certificate Friendly Name must be unique in the computer store.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4083b-120">Wenn Sie sipinternal.contoso.com oder sipexternal.contoso.com in Ihrem DNS konfiguriert haben, müssen Sie Sie im alternativen Antragstellernamen des Zertifikats hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4083b-120">If you have configured sipinternal.contoso.com or sipexternal.contoso.com in your DNS, you will need to add them in the certificate’s Subject Alternative Name.</span></span>



</div>

### <a name="certificates-for-standard-edition-server"></a><span data-ttu-id="4083b-121">Zertifikate für Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="4083b-121">Certificates for Standard Edition Server</span></span>

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
<th><span data-ttu-id="4083b-122">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="4083b-122">Certificate</span></span></th>
<th><span data-ttu-id="4083b-123">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="4083b-123">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="4083b-124">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="4083b-124">Subject alternative name</span></span></th>
<th><span data-ttu-id="4083b-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4083b-125">Example</span></span></th>
<th><span data-ttu-id="4083b-126">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="4083b-126">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4083b-127">Standard</span><span class="sxs-lookup"><span data-stu-id="4083b-127">Default</span></span></p></td>
<td><p><span data-ttu-id="4083b-128">Vollqualifizierter Domänenname (FQDN) des Pools</span><span class="sxs-lookup"><span data-stu-id="4083b-128">Fully qualified domain name (FQDN) of the pool</span></span></p></td>
<td><p><span data-ttu-id="4083b-129">FQDN des Pools und FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="4083b-129">FQDN of the pool and the FQDN of the server</span></span></p>
<p><span data-ttu-id="4083b-130">Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</span><span class="sxs-lookup"><span data-stu-id="4083b-130">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="4083b-131">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich (Domain Name System) festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).</span><span class="sxs-lookup"><span data-stu-id="4083b-131">If this pool is the auto-logon server for clients and strict Domain Name System (DNS) matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="4083b-132">SN = SE01. contoso. com; San = SE01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-132">SN=se01.contoso.com; SAN=se01.contoso.com</span></span></p>
<p><span data-ttu-id="4083b-133">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".</span><span class="sxs-lookup"><span data-stu-id="4083b-133">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="4083b-134">Auf einem Standard Edition-Server entspricht der Server-FQDN dem Pool-FQDN.</span><span class="sxs-lookup"><span data-stu-id="4083b-134">On Standard Edition server, the server FQDN is the same as the pool FQDN.</span></span></p>
<p><span data-ttu-id="4083b-135">Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.</span><span class="sxs-lookup"><span data-stu-id="4083b-135">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="4083b-136">Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4083b-136">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4083b-137">Web, intern</span><span class="sxs-lookup"><span data-stu-id="4083b-137">Web internal</span></span></p></td>
<td><p><span data-ttu-id="4083b-138">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="4083b-138">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="4083b-139">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="4083b-139">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4083b-140">Interner Web-FQDN (entspricht dem FQDN des Servers)</span><span class="sxs-lookup"><span data-stu-id="4083b-140">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="4083b-141">Einfache URLs vom Typ "Meet"</span><span class="sxs-lookup"><span data-stu-id="4083b-141">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="4083b-142">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="4083b-142">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-143">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="4083b-143">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-144">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="4083b-144">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4083b-145">SN = SE01. contoso. com; San = SE01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-145">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="4083b-146">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="4083b-146">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="4083b-147">SN = SE01. contoso. com; San = SE01. contoso. com; San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-147">SN=se01.contoso.com; SAN=se01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4083b-148">Sie können den internen webfqdn im Topologie-Generator nicht außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="4083b-148">You cannot override the Internal web FQDN in Topology Builder.</span></span></p>
<p><span data-ttu-id="4083b-149">Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="4083b-149">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="4083b-150">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4083b-150">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4083b-151">Web, extern</span><span class="sxs-lookup"><span data-stu-id="4083b-151">Web external</span></span></p></td>
<td><p><span data-ttu-id="4083b-152">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="4083b-152">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="4083b-153">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="4083b-153">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4083b-154">Externer Web-FQDN</span><span class="sxs-lookup"><span data-stu-id="4083b-154">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="4083b-155">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="4083b-155">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-156">Erfüllen einfacher URLs pro SIP-Domäne</span><span class="sxs-lookup"><span data-stu-id="4083b-156">Meet simple URLs per SIP domain</span></span></p></li>
<li><p><span data-ttu-id="4083b-157">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="4083b-157">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4083b-158">SN = SE01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-158">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="4083b-159">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="4083b-159">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="4083b-160">SN = SE01. contoso. com; San = webcon01. contoso. com; San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-160">SN=se01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4083b-161">Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="4083b-161">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="4083b-162">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4083b-162">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-front-end-server-in-a-front-end-pool"></a><span data-ttu-id="4083b-163">Zertifikate für Front-End-Server in einem Front-End-Pool</span><span class="sxs-lookup"><span data-stu-id="4083b-163">Certificates for Front End Server in a Front End Pool</span></span>

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
<th><span data-ttu-id="4083b-164">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="4083b-164">Certificate</span></span></th>
<th><span data-ttu-id="4083b-165">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="4083b-165">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="4083b-166">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="4083b-166">Subject alternative name</span></span></th>
<th><span data-ttu-id="4083b-167">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4083b-167">Example</span></span></th>
<th><span data-ttu-id="4083b-168">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="4083b-168">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4083b-169">Standard</span><span class="sxs-lookup"><span data-stu-id="4083b-169">Default</span></span></p></td>
<td><p><span data-ttu-id="4083b-170">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="4083b-170">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="4083b-171">FQDN des Pools und FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="4083b-171">FQDN of the pool and FQDN of the server.</span></span></p>
<p><span data-ttu-id="4083b-172">Wenn mehrere SIP-Domänen vorhanden sind und die automatische Clientkonfiguration aktiviert wurde, erkennt der Zertifikat-Assistent die unterstützten FQDNs für SIP-Domänen und fügt diese hinzu.</span><span class="sxs-lookup"><span data-stu-id="4083b-172">If you have multiple SIP domains and have enabled automatic client configuration, the certificate wizard detects and adds each supported SIP domain FQDNs.</span></span></p>
<p><span data-ttu-id="4083b-173">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).</span><span class="sxs-lookup"><span data-stu-id="4083b-173">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="4083b-174">SN = EEpool. contoso. com; San = EEpool. contoso. com; San = ee01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-174">SN=eepool.contoso.com; SAN=eepool.contoso.com; SAN=ee01.contoso.com</span></span></p>
<p><span data-ttu-id="4083b-175">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".</span><span class="sxs-lookup"><span data-stu-id="4083b-175">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
<td><p><span data-ttu-id="4083b-176">Der Assistent erkennt alle SIP-Domänen, die Sie während der Installation angegeben haben, und fügt sie dem alternativen Antragstellernamen (SAN) automatisch hinzu.</span><span class="sxs-lookup"><span data-stu-id="4083b-176">The wizard detects any SIP domains you specified during setup and automatically adds them to the subject alternative name.</span></span></p>
<p><span data-ttu-id="4083b-177">Sie können dieses Zertifikat auch für die Server-zu-Server-Authentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="4083b-177">You can also use this certificate for Server-to-Server Authentication.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4083b-178">Web, intern</span><span class="sxs-lookup"><span data-stu-id="4083b-178">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="4083b-179">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="4083b-179">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="4083b-180">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="4083b-180">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4083b-181">Interner FQDN des Webs (nicht identisch mit dem FQDN des Servers)</span><span class="sxs-lookup"><span data-stu-id="4083b-181">Internal web FQDN (which is NOT the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="4083b-182">Server-FQDN</span><span class="sxs-lookup"><span data-stu-id="4083b-182">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="4083b-183">Lync-Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="4083b-183">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="4083b-184">Einfache URLs vom Typ "Meet"</span><span class="sxs-lookup"><span data-stu-id="4083b-184">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="4083b-185">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="4083b-185">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-186">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="4083b-186">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-187">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="4083b-187">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4083b-188">SN = ee01. contoso. com; San = ee01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-188">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="4083b-189">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="4083b-189">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="4083b-190">SN = ee01. contoso. com; San = ee01. contoso. com; San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-190">SN=ee01.contoso.com; SAN=ee01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4083b-191">Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="4083b-191">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="4083b-192">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4083b-192">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4083b-193">Web, extern</span><span class="sxs-lookup"><span data-stu-id="4083b-193">Web external</span></span></p></td>
<td><p><span data-ttu-id="4083b-194">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="4083b-194">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="4083b-195">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="4083b-195">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4083b-196">Externer Web-FQDN</span><span class="sxs-lookup"><span data-stu-id="4083b-196">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="4083b-197">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="4083b-197">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-198">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="4083b-198">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-199">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="4083b-199">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4083b-200">SN = ee01. contoso. com; San = webcon01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-200">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="4083b-201">Mit einem Platzhalterzertifikat:</span><span class="sxs-lookup"><span data-stu-id="4083b-201">Using a wildcard certificate:</span></span></p>
<p><span data-ttu-id="4083b-202">SN = ee01. contoso. com; San = webcon01. contoso. com; San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-202">SN=ee01.contoso.com; SAN=webcon01.contoso.com; SAN=\*.contoso.com</span></span></p></td>
<td><p><span data-ttu-id="4083b-203">Wenn Sie über mehrere einfache URLs vom Typ "Meet" verfügen, müssen Sie alle als alternative Antragstellernamen einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="4083b-203">If you have multiple Meet simple URLs, you must include all of them as subject alternative names.</span></span></p>
<p><span data-ttu-id="4083b-204">Platzhaltereinträge werden für die Einträge für einfache URLs unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4083b-204">Wildcard entries are supported for the simple URL entries.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-director"></a><span data-ttu-id="4083b-205">Zertifikate für Director</span><span class="sxs-lookup"><span data-stu-id="4083b-205">Certificates for Director</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4083b-206">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="4083b-206">Certificate</span></span></th>
<th><span data-ttu-id="4083b-207">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="4083b-207">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="4083b-208">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="4083b-208">Subject alternative name</span></span></th>
<th><span data-ttu-id="4083b-209">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4083b-209">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4083b-210">Standard</span><span class="sxs-lookup"><span data-stu-id="4083b-210">Default</span></span></p></td>
<td><p><span data-ttu-id="4083b-211">FQDN des Director-Pools</span><span class="sxs-lookup"><span data-stu-id="4083b-211">FQDN of the Director pool</span></span></p></td>
<td><p><span data-ttu-id="4083b-212">Director-FQDN, FQDN des Director-Pools</span><span class="sxs-lookup"><span data-stu-id="4083b-212">FQDN of the Director, FQDN of the Director pool</span></span></p>
<p><span data-ttu-id="4083b-213">Wenn es sich bei diesem Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch Einträge für "sip.sipDomäne" (für jede vorhandene SIP-Domäne).</span><span class="sxs-lookup"><span data-stu-id="4083b-213">If this pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need entries for sip.sipdomain (for each SIP domain you have).</span></span></p></td>
<td><p><span data-ttu-id="4083b-214">SN = dir-Pool.contoso.com; San = dir-Pool.contoso.com; San = dir01. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-214">SN=dir-pool.contoso.com; SAN=dir-pool.contoso.com; SAN=dir01.contoso.com</span></span></p>
<p><span data-ttu-id="4083b-215">Wenn es sich bei diesem Director-Pool um den Server für die automatische Anmeldung für Clients handelt und in den Gruppenrichtlinien der exakte DNS-Abgleich festgelegt ist, benötigen Sie auch "SAN=sip.contoso.com; SAN=sip.fabrikam.com".</span><span class="sxs-lookup"><span data-stu-id="4083b-215">If this Director pool is the auto-logon server for clients and strict DNS matching is required in group policy, you also need SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4083b-216">Web, intern</span><span class="sxs-lookup"><span data-stu-id="4083b-216">Web Internal</span></span></p></td>
<td><p><span data-ttu-id="4083b-217">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="4083b-217">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="4083b-218">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="4083b-218">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4083b-219">Interner Web-FQDN (entspricht dem FQDN des Servers)</span><span class="sxs-lookup"><span data-stu-id="4083b-219">Internal web FQDN (which is the same as the FQDN of the server)</span></span></p></li>
<li><p><span data-ttu-id="4083b-220">Server-FQDN</span><span class="sxs-lookup"><span data-stu-id="4083b-220">Server FQDN</span></span></p></li>
<li><p><span data-ttu-id="4083b-221">Lync-Pool-FQDN</span><span class="sxs-lookup"><span data-stu-id="4083b-221">Lync pool FQDN</span></span></p></li>
<li><p><span data-ttu-id="4083b-222">Einfache URLs vom Typ "Meet"</span><span class="sxs-lookup"><span data-stu-id="4083b-222">Meet simple URLs</span></span></p></li>
<li><p><span data-ttu-id="4083b-223">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="4083b-223">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-224">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="4083b-224">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-225">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="4083b-225">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4083b-226">SN = dir01. contoso. com; San = dir01. contoso. com; San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com; San = admin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-226">SN=dir01.contoso.com; SAN=dir01.contoso.com; SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com; SAN=admin.contoso.com</span></span></p>
<p><span data-ttu-id="4083b-227">SN = dir01. contoso. com; San = dir01. contoso. com San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-227">SN=dir01.contoso.com; SAN=dir01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4083b-228">Web, extern</span><span class="sxs-lookup"><span data-stu-id="4083b-228">Web external</span></span></p></td>
<td><p><span data-ttu-id="4083b-229">FQDN des Servers</span><span class="sxs-lookup"><span data-stu-id="4083b-229">FQDN of the server</span></span></p></td>
<td><p><span data-ttu-id="4083b-230">Jeder der folgenden:</span><span class="sxs-lookup"><span data-stu-id="4083b-230">Each of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4083b-231">Externer Web-FQDN</span><span class="sxs-lookup"><span data-stu-id="4083b-231">External web FQDN</span></span></p></li>
<li><p><span data-ttu-id="4083b-232">Einfache URLs vom Typ "Dialin"</span><span class="sxs-lookup"><span data-stu-id="4083b-232">Dial-in simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-233">Einfache URL vom Typ "Admin"</span><span class="sxs-lookup"><span data-stu-id="4083b-233">Admin simple URL</span></span></p></li>
<li><p><span data-ttu-id="4083b-234">Oder ein Platzhaltereintrag für die einfachen URLs</span><span class="sxs-lookup"><span data-stu-id="4083b-234">Or, a wildcard entry for the simple URLs</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4083b-235">Der externe Director-webfqdn muss sich von dem Front-End-Pool oder Front-End-Server unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="4083b-235">The Director external web FQDN must be different from the Front End pool or Front End Server.</span></span></p>
<p><span data-ttu-id="4083b-236">SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = Meet. contoso. com; San = Meet. fabrikam. com; San = dialin. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-236">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=meet.contoso.com; SAN=meet.fabrikam.com; SAN=dialin.contoso.com</span></span></p>
<p><span data-ttu-id="4083b-237">SN = dir01. contoso. com; San = directorwebcon01. contoso. com San = \*. contoso. com</span><span class="sxs-lookup"><span data-stu-id="4083b-237">SN=dir01.contoso.com; SAN=directorwebcon01.contoso.com SAN=\*.contoso.com</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4083b-p107">Wenn Sie über einen eigenständigen Vermittlungsserverpool verfügen, muss jeder der darin enthaltenen Vermittlungsserver über die in der folgenden Tabelle aufgelisteten Zertifikate verfügen. Wenn Sie einen Vermittlungsserver mit den Front-End-Servern verbinden, reichen die in der Tabelle "Zertifikate für Front-End-Server im Front-End-Pool" (weiter oben) aufgeführten Zertifikate aus.</span><span class="sxs-lookup"><span data-stu-id="4083b-p107">If you have a stand-alone Mediation Server pool, the Mediation Servers in it each need the certificates listed in the following table. If you collocate Mediation Server with the Front End Servers, the certificates listed in the “Certificates for Front End Server in Front End Pool” table earlier in this topic are sufficient.</span></span>

### <a name="certificates-for-stand-alone-mediation-server"></a><span data-ttu-id="4083b-240">Zertifikate für eigenständige Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="4083b-240">Certificates for Stand-alone Mediation Server</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4083b-241">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="4083b-241">Certificate</span></span></th>
<th><span data-ttu-id="4083b-242">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="4083b-242">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="4083b-243">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="4083b-243">Subject alternative name</span></span></th>
<th><span data-ttu-id="4083b-244">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4083b-244">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4083b-245">Standard</span><span class="sxs-lookup"><span data-stu-id="4083b-245">Default</span></span></p></td>
<td><p><span data-ttu-id="4083b-246">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="4083b-246">FQDN of the pool</span></span></p></td>
<td><p><span data-ttu-id="4083b-247">FQDN des Pools</span><span class="sxs-lookup"><span data-stu-id="4083b-247">FQDN of the pool</span></span></p>
<p><span data-ttu-id="4083b-248">FQDN des Poolmitgliedsservers</span><span class="sxs-lookup"><span data-stu-id="4083b-248">FQDN of pool member server</span></span></p></td>
<td><p><span data-ttu-id="4083b-249">SN = medsvr-Pool.contoso.net; San = medsvr-Pool.contoso.net; San = medsvr01. contoso. net</span><span class="sxs-lookup"><span data-stu-id="4083b-249">SN=medsvr-pool.contoso.net; SAN=medsvr-pool.contoso.net; SAN=medsvr01.contoso.net</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="certificates-for-survivable-branch-appliance"></a><span data-ttu-id="4083b-250">Zertifikate für eine Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="4083b-250">Certificates for Survivable Branch Appliance</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4083b-251">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="4083b-251">Certificate</span></span></th>
<th><span data-ttu-id="4083b-252">Antragstellername/Allgemeiner Name</span><span class="sxs-lookup"><span data-stu-id="4083b-252">Subject name/ Common name</span></span></th>
<th><span data-ttu-id="4083b-253">Alternativer Antragstellername</span><span class="sxs-lookup"><span data-stu-id="4083b-253">Subject alternative name</span></span></th>
<th><span data-ttu-id="4083b-254">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4083b-254">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4083b-255">Standard</span><span class="sxs-lookup"><span data-stu-id="4083b-255">Default</span></span></p></td>
<td><p><span data-ttu-id="4083b-256">FQDN der Appliance</span><span class="sxs-lookup"><span data-stu-id="4083b-256">FQDN of the appliance</span></span></p></td>
<td><p><span data-ttu-id="4083b-257">SIP. &lt;sipdomain "&gt; (benötigt einen Eintrag pro SIP-Domäne)</span><span class="sxs-lookup"><span data-stu-id="4083b-257">SIP.&lt;sipdomain&gt; (need one entry per SIP domain)</span></span></p></td>
<td><p><span data-ttu-id="4083b-258">SN = sba01. contoso. net; San = SIP. contoso. com; San = SIP. fabrikam. com</span><span class="sxs-lookup"><span data-stu-id="4083b-258">SN=sba01.contoso.net; SAN=sip.contoso.com; SAN=sip.fabrikam.com</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="4083b-259">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4083b-259">See Also</span></span>


[<span data-ttu-id="4083b-260">Unterstützung von Platzhalterzertifikaten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4083b-260">Wildcard certificate support in Lync Server 2013</span></span>](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

