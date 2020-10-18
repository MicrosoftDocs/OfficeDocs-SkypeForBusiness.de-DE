---
title: IIS-Anforderungen für Front-End-Pools und Standard Edition-Server
description: IIS-Anforderungen für Front-End-Pools und Standard Edition-Server.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f56452c7e47352333ac3ac5a51d649b0828a0ff9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573341"
---
# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="a7df1-103">IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a7df1-103">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a7df1-104">_**Letztes Änderungsstand des Themas:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="a7df1-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="a7df1-105">Für Standard Edition-Server und Front-End-Server und Directors erstellt das lync Server 2013-Installationsprogramm virtuelle Verzeichnisse in Internet Information Services (IIS) für die folgenden Zwecke:</span><span class="sxs-lookup"><span data-stu-id="a7df1-105">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="a7df1-106">So ermöglichen Sie Benutzern das Herunterladen von Dateien aus dem Adressbuchdienst</span><span class="sxs-lookup"><span data-stu-id="a7df1-106">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="a7df1-107">So aktivieren Sie Clients zum Abrufen von Updates</span><span class="sxs-lookup"><span data-stu-id="a7df1-107">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="a7df1-108">So aktivieren Sie Konferenzen</span><span class="sxs-lookup"><span data-stu-id="a7df1-108">To enable conferencing</span></span>

  - <span data-ttu-id="a7df1-109">So ermöglichen Sie Benutzern das Herunterladen von Besprechungsinhalten</span><span class="sxs-lookup"><span data-stu-id="a7df1-109">To enable users to download meeting content</span></span>

  - <span data-ttu-id="a7df1-110">So ermöglichen Sie Benutzern das Erweitern von Verteilergruppen</span><span class="sxs-lookup"><span data-stu-id="a7df1-110">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="a7df1-111">So aktivieren Sie Telefonkonferenzen</span><span class="sxs-lookup"><span data-stu-id="a7df1-111">To enable phone conferencing</span></span>

  - <span data-ttu-id="a7df1-112">So aktivieren Sie Reaktionsgruppenfeatures</span><span class="sxs-lookup"><span data-stu-id="a7df1-112">To enable response group features</span></span>

<span data-ttu-id="a7df1-113">Darüber hinaus erstellt das kumulative Update für lync Server 2010: November 2011-Installer virtuelle Verzeichnisse in IIS für die folgenden Zwecke:</span><span class="sxs-lookup"><span data-stu-id="a7df1-113">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="a7df1-114">Auf Front-End-Servern oder Standard Edition-Servern zur Unterstützung von Mobilitätsfunktionen wie Instant Messaging (Sofortnachrichten) und Anwesenheit auf mobilen Geräten</span><span class="sxs-lookup"><span data-stu-id="a7df1-114">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="a7df1-115">Auf Front-End-Servern oder Standard Edition-Servern und auf Directors, damit Mobile Geräte mobilitätsressourcen automatisch ermitteln können</span><span class="sxs-lookup"><span data-stu-id="a7df1-115">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="a7df1-116">Bei der Bereitstellung von Mobility wird die Verwendung von IIS 7,5 empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a7df1-116">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="a7df1-117">Das Installationsprogramm für lync Server Mobility Service legt einige ASP.net-Flags fest, um die Leistung zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="a7df1-117">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="a7df1-118">IIS 7.5 ist standardmäßig unter Windows Server 2008 R2 installiert, und der Mobilitätsdienst-Installer ändert die ASP.NET-Einstellungen automatisch.</span><span class="sxs-lookup"><span data-stu-id="a7df1-118">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="a7df1-119">Wenn Sie IIS 7.0 unter Windows Server 2008 verwenden, müssen Sie diese Einstellungen manuell ändern.</span><span class="sxs-lookup"><span data-stu-id="a7df1-119">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="a7df1-120">Für lync Server müssen die folgenden IIS-Module installiert werden:</span><span class="sxs-lookup"><span data-stu-id="a7df1-120">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a7df1-121">Wenn in Ihrer Organisation IIS und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk lokalisiert werden müssen, können Sie den Installationspfad für die lync Server Dateien im Dialogfeld Setup ändern.</span><span class="sxs-lookup"><span data-stu-id="a7df1-121">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="a7df1-122">Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen lync Server Dateien auf diesem Laufwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a7df1-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="a7df1-123">Ausführliche Informationen zum Verschieben des von Windows Server-Manager bereitgestellten Verzeichnis Inetpub bei der Installation von IIS finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="a7df1-123">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="a7df1-124">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="a7df1-124">Static Content</span></span>

  - <span data-ttu-id="a7df1-125">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="a7df1-125">Default Document</span></span>

  - <span data-ttu-id="a7df1-126">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="a7df1-126">HTTP Errors</span></span>

  - <span data-ttu-id="a7df1-127">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a7df1-127">ASP.NET</span></span>

  - <span data-ttu-id="a7df1-128">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="a7df1-128">.NET Extensibility</span></span>

  - <span data-ttu-id="a7df1-129">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="a7df1-129">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="a7df1-130">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="a7df1-130">ISAPI Filters</span></span>

  - <span data-ttu-id="a7df1-131">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="a7df1-131">HTTP Logging</span></span>

  - <span data-ttu-id="a7df1-132">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="a7df1-132">Logging Tools</span></span>

  - <span data-ttu-id="a7df1-133">Tracing</span><span class="sxs-lookup"><span data-stu-id="a7df1-133">Tracing</span></span>

  - <span data-ttu-id="a7df1-134">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a7df1-134">Windows Authentication</span></span>

  - <span data-ttu-id="a7df1-135">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="a7df1-135">Request Filtering</span></span>

  - <span data-ttu-id="a7df1-136">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="a7df1-136">Static Content Compression</span></span>

  - <span data-ttu-id="a7df1-137">Komprimierung dynamischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="a7df1-137">Dynamic Content Compression</span></span>

  - <span data-ttu-id="a7df1-138">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="a7df1-138">IIS Management Console</span></span>

  - <span data-ttu-id="a7df1-139">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="a7df1-139">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="a7df1-140">Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert)</span><span class="sxs-lookup"><span data-stu-id="a7df1-140">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="a7df1-141">Authentifizierung der Client Zertifikatzuordnung</span><span class="sxs-lookup"><span data-stu-id="a7df1-141">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="a7df1-142">In der folgenden Tabelle sind die URIs für die virtuellen Verzeichnisse für den internen Zugriff und die Dateisystemressourcen aufgeführt, auf die Sie sich berufen.</span><span class="sxs-lookup"><span data-stu-id="a7df1-142">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="a7df1-143">Virtuelle Verzeichnisse für internen Zugriff</span><span class="sxs-lookup"><span data-stu-id="a7df1-143">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a7df1-144">Feature</span><span class="sxs-lookup"><span data-stu-id="a7df1-144">Feature</span></span></th>
<th><span data-ttu-id="a7df1-145">URI des virtuellen Verzeichnisses</span><span class="sxs-lookup"><span data-stu-id="a7df1-145">Virtual directory URI</span></span></th>
<th><span data-ttu-id="a7df1-146">Bezug auf</span><span class="sxs-lookup"><span data-stu-id="a7df1-146">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a7df1-147">Adressbuchserver</span><span class="sxs-lookup"><span data-stu-id="a7df1-147">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="a7df1-148">https:// &lt; Interner FQDN &gt; /ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="a7df1-148">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="a7df1-149">Speicherort der Adressbuch Server-Downloaddateien für interne Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a7df1-149">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7df1-150">AutoErmittlungsdienst</span><span class="sxs-lookup"><span data-stu-id="a7df1-150">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="a7df1-151">https:// &lt; Interner FQDN &gt; /autodiscover</span><span class="sxs-lookup"><span data-stu-id="a7df1-151">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="a7df1-152">Speicherort des lync Server AutoErmittlungsdiensts, der mobilitätsressourcen für Benutzer interner mobiler Geräte sucht.</span><span class="sxs-lookup"><span data-stu-id="a7df1-152">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7df1-153">Clientupdates</span><span class="sxs-lookup"><span data-stu-id="a7df1-153">Client updates</span></span></p></td>
<td><p><span data-ttu-id="a7df1-154">http:// &lt; Interner FQDN &gt; /AutoUpdate/int</span><span class="sxs-lookup"><span data-stu-id="a7df1-154">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="a7df1-155">Speicherort der Updatedateien für interne computerbasierte Clients.</span><span class="sxs-lookup"><span data-stu-id="a7df1-155">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7df1-156">Conf</span><span class="sxs-lookup"><span data-stu-id="a7df1-156">Conf</span></span></p></td>
<td><p><span data-ttu-id="a7df1-157">http:// &lt; Interner FQDN &gt; /conf/int</span><span class="sxs-lookup"><span data-stu-id="a7df1-157">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="a7df1-158">Speicherort von Konferenzressourcen für interne Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a7df1-158">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7df1-159">Geräte Updates</span><span class="sxs-lookup"><span data-stu-id="a7df1-159">Device updates</span></span></p></td>
<td><p><span data-ttu-id="a7df1-160">http:// &lt; Interner FQDN &gt; /DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="a7df1-160">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="a7df1-161">Speicherort der UC-Geräteaktualisierungsdateien (Unified Communications) für interne UC-Geräte.</span><span class="sxs-lookup"><span data-stu-id="a7df1-161">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7df1-162">Besprechung</span><span class="sxs-lookup"><span data-stu-id="a7df1-162">Meeting</span></span></p></td>
<td><p><span data-ttu-id="a7df1-163">http:// &lt; Interner FQDN &gt; /etc/Place/NULL</span><span class="sxs-lookup"><span data-stu-id="a7df1-163">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="a7df1-164">Speicherort des Besprechungsinhalts für interne Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a7df1-164">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7df1-165">Mobilitätsdienst</span><span class="sxs-lookup"><span data-stu-id="a7df1-165">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="a7df1-166">https:// &lt; Interner FQDN &gt; /MCX</span><span class="sxs-lookup"><span data-stu-id="a7df1-166">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="a7df1-167">Speicherort der Mobilitätsdienst Ressourcen für Benutzer interner mobiler Geräte.</span><span class="sxs-lookup"><span data-stu-id="a7df1-167">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7df1-168">Gruppenerweiterung und Adressbuch-Webabfragedienst</span><span class="sxs-lookup"><span data-stu-id="a7df1-168">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="a7df1-169">http:// &lt; Interner FQDN &gt; /GroupExpansion/int/Service.asmx</span><span class="sxs-lookup"><span data-stu-id="a7df1-169">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="a7df1-170">Speicherort des Webdiensts, der die Gruppenerweiterung für interne Benutzer ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a7df1-170">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="a7df1-171">Außerdem wird der Speicherort des Adressbuch-Webabfragedienst, der Informationen zur globalen Adressliste für interne lync Mobile Microsoft lync 2010 Mobile-Clients bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a7df1-171">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7df1-172">Telefonkonferenzen</span><span class="sxs-lookup"><span data-stu-id="a7df1-172">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="a7df1-173">http:// &lt; Interner FQDN &gt; /PhoneConferencing/int</span><span class="sxs-lookup"><span data-stu-id="a7df1-173">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="a7df1-174">Speicherort der Telefonkonferenz Daten für interne Benutzer.</span><span class="sxs-lookup"><span data-stu-id="a7df1-174">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a7df1-175">Geräte Updates</span><span class="sxs-lookup"><span data-stu-id="a7df1-175">Device updates</span></span></p></td>
<td><p><span data-ttu-id="a7df1-176">http:// &lt; Interner FQDN &gt; /RequestHandler</span><span class="sxs-lookup"><span data-stu-id="a7df1-176">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="a7df1-177">Speicherort des Anforderungshandlers für den Geräte Update-Webdienst, mit dem interne UC-Geräteprotokolle hochladen und nach Updates suchen können.</span><span class="sxs-lookup"><span data-stu-id="a7df1-177">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a7df1-178">Reaktionsgruppenanwendung</span><span class="sxs-lookup"><span data-stu-id="a7df1-178">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="a7df1-179">http:// &lt; Interner FQDN &gt; /RgsConfig</span><span class="sxs-lookup"><span data-stu-id="a7df1-179">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="a7df1-180">http:// &lt; Interner FQDN &gt; /RgsClients</span><span class="sxs-lookup"><span data-stu-id="a7df1-180">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="a7df1-181">Speicherort des Reaktionsgruppen-Konfigurationstools.</span><span class="sxs-lookup"><span data-stu-id="a7df1-181">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="a7df1-182">Für Front-End-Pools in einer konsolidierten Konfiguration müssen Sie IIS bereitstellen, bevor Sie dem Pool Server hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="a7df1-182">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="Sicherheits" alt="security" /><span data-ttu-id="a7df1-184">Sicherheitshinweis:</span><span class="sxs-lookup"><span data-stu-id="a7df1-184">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a7df1-185">Sie müssen das IIS-Verwaltungs-Snap-in verwenden, um das vom IIS-Webkomponentenserver verwendete Zertifikat zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="a7df1-185">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

