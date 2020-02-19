---
title: 'Lync Server 2013: IIS-Konfiguration'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d284fa2082c886a583baf116893f792535a096b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="41011-102">IIS-Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41011-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41011-103">_**Letztes Änderungsstand des Themas:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="41011-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="41011-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie beim Computer mit den Mindestberechtigungen eines lokalen Administrators und Domänenbenutzers angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="41011-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="41011-105">Bevor Sie die Front-End-Server für lync Server 2013, Standard Edition oder den ersten Front-End-Server in einem Pool konfigurieren und installieren, installieren und konfigurieren Sie die Server Rolle und Webdienste für Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="41011-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="41011-106">Wenn in Ihrer Organisation IIS und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk gefunden werden müssen, können Sie den Installationspfad für die lync Server 2013 Dateien im Dialogfeld Setup ändern, wenn Sie die lync Server 2013 erst installieren. Verwaltungstools.</span><span class="sxs-lookup"><span data-stu-id="41011-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="41011-107">Sie installieren die Verwaltungstools vor der Installation von IIS.</span><span class="sxs-lookup"><span data-stu-id="41011-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="41011-108">Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden auch die restlichen lync Server 2013 Dateien auf diesem Laufwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="41011-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="41011-109">Informationen zu dtails finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">install lync Server 2013 Administration Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="41011-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="41011-110">Ausführliche Informationen zum Verschieben des von Windows Server-Manager bereitgestellten Verzeichnis Inetpub bei der Installation von <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>IIS finden Sie unter.</span><span class="sxs-lookup"><span data-stu-id="41011-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="41011-111">In der folgenden Tabelle sind die erforderlichen IIS 7,5-Rollendienste angegeben.</span><span class="sxs-lookup"><span data-stu-id="41011-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="41011-112">IIS 7,5-Rollendienste</span><span class="sxs-lookup"><span data-stu-id="41011-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41011-113">Rollenüberschrift</span><span class="sxs-lookup"><span data-stu-id="41011-113">Role Heading</span></span></th>
<th><span data-ttu-id="41011-114">Rollendienst</span><span class="sxs-lookup"><span data-stu-id="41011-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41011-115">Allgemeine HTTP-Funktionen installiert</span><span class="sxs-lookup"><span data-stu-id="41011-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="41011-116">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="41011-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-117">Allgemeine HTTP-Funktionen installiert</span><span class="sxs-lookup"><span data-stu-id="41011-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="41011-118">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="41011-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-119">Allgemeine HTTP-Funktionen installiert</span><span class="sxs-lookup"><span data-stu-id="41011-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="41011-120">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="41011-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-121">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="41011-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="41011-122">ASP.NET</span></span></p>
<p><span data-ttu-id="41011-123">Windows Server 2012 erfordert auch ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="41011-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-124">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="41011-125">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="41011-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-126">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="41011-127">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="41011-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-128">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="41011-129">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="41011-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-130">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="41011-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="41011-131">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="41011-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-132">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="41011-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="41011-133">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="41011-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-134">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="41011-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="41011-135">Tracing</span><span class="sxs-lookup"><span data-stu-id="41011-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-136">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41011-136">Security</span></span></p></td>
<td><p><span data-ttu-id="41011-137">Anonyme Authentifizierung (standardmäßig installiert und aktiviert)</span><span class="sxs-lookup"><span data-stu-id="41011-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-138">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41011-138">Security</span></span></p></td>
<td><p><span data-ttu-id="41011-139">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="41011-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-140">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41011-140">Security</span></span></p></td>
<td><p><span data-ttu-id="41011-141">Clientzertifikatzuordnungs-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="41011-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-142">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41011-142">Security</span></span></p></td>
<td><p><span data-ttu-id="41011-143">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="41011-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-144">Leistung</span><span class="sxs-lookup"><span data-stu-id="41011-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="41011-145">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="41011-145">Static content compression</span></span></p>
<p><span data-ttu-id="41011-146">Komprimierung dynamischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="41011-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-147">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="41011-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="41011-148">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="41011-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-149">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="41011-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="41011-150">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="41011-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="41011-151">Auf dem Betriebssystem Windows Server 2008 R2 SP1 x64 können Sie Windows PowerShell 2,0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="41011-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="41011-152">Sie müssen zunächst das Modul "ServerManager" importieren und anschließend die IIS 7.5-Rolle und -Rollendienste installieren.</span><span class="sxs-lookup"><span data-stu-id="41011-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="41011-153">Die anonyme Authentifizierung wird bei der Installation der IIS-Serverrolle standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="41011-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="41011-154">Sie können die anonyme Authentifizierung nach der Installation von IIS verwalten.</span><span class="sxs-lookup"><span data-stu-id="41011-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="41011-155">Ausführliche Informationen finden Sie unter "Aktivieren der <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>anonymen Authentifizierung (IIS 7.0)" unter.</span><span class="sxs-lookup"><span data-stu-id="41011-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="41011-156">In der folgenden Tabelle werden die erforderlichen IIS 8,0-und IIS 8,5-Rollendienste für Windows Server 2012 und Windows Server 2012 R2 angegeben.</span><span class="sxs-lookup"><span data-stu-id="41011-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="41011-157">Für Windows Server 2012 und Windows Server 2012 R2 wurde das Cmdlet Add-Cmdlets durch das Cmdlet Install-Cmdlets ersetzt.</span><span class="sxs-lookup"><span data-stu-id="41011-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="41011-158">Ausführliche Informationen finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-Cmdlets</A>.</span><span class="sxs-lookup"><span data-stu-id="41011-158">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="41011-159">IIS 8,0 und IIS 8,5-Rollendienste</span><span class="sxs-lookup"><span data-stu-id="41011-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41011-160">Rollenüberschrift</span><span class="sxs-lookup"><span data-stu-id="41011-160">Role Heading</span></span></th>
<th><span data-ttu-id="41011-161">Rollendienst</span><span class="sxs-lookup"><span data-stu-id="41011-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41011-162">Webserver (IIS)</span><span class="sxs-lookup"><span data-stu-id="41011-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="41011-163">Webserver</span><span class="sxs-lookup"><span data-stu-id="41011-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-164">Allgemeine HTTP-Features</span><span class="sxs-lookup"><span data-stu-id="41011-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="41011-165">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="41011-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-166">Allgemeine HTTP-Features</span><span class="sxs-lookup"><span data-stu-id="41011-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="41011-167">Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="41011-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-168">Allgemeine HTTP-Features</span><span class="sxs-lookup"><span data-stu-id="41011-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="41011-169">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="41011-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-170">Allgemeine HTTP-Features</span><span class="sxs-lookup"><span data-stu-id="41011-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="41011-171">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="41011-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-172">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="41011-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="41011-173">HTTP-Umleitung</span><span class="sxs-lookup"><span data-stu-id="41011-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-174">Systemzustand und Diagnose</span><span class="sxs-lookup"><span data-stu-id="41011-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="41011-175">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="41011-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-176">Systemzustand und Diagnose</span><span class="sxs-lookup"><span data-stu-id="41011-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="41011-177">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="41011-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-178">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="41011-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="41011-179">Anforderungsüberwachung</span><span class="sxs-lookup"><span data-stu-id="41011-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-180">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="41011-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="41011-181">Tracing</span><span class="sxs-lookup"><span data-stu-id="41011-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-182">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41011-182">Security</span></span></p></td>
<td><p><span data-ttu-id="41011-183">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="41011-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-184">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41011-184">Security</span></span></p></td>
<td><p><span data-ttu-id="41011-185">Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="41011-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-186">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41011-186">Security</span></span></p></td>
<td><p><span data-ttu-id="41011-187">Authentifizierung der Client Zertifikatzuordnung</span><span class="sxs-lookup"><span data-stu-id="41011-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-188">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="41011-188">Security</span></span></p></td>
<td><p><span data-ttu-id="41011-189">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="41011-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-190">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="41011-191">.NET-Erweiterbarkeit 3,5</span><span class="sxs-lookup"><span data-stu-id="41011-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-192">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="41011-193">.NET-Erweiterbarkeit 4,5</span><span class="sxs-lookup"><span data-stu-id="41011-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-194">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="41011-195">ASP.NET 3,5</span><span class="sxs-lookup"><span data-stu-id="41011-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-196">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="41011-197">ASP.NET 4,5</span><span class="sxs-lookup"><span data-stu-id="41011-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-198">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="41011-199">ISAPI-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="41011-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-200">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="41011-201">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="41011-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-202">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="41011-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="41011-203">Serverseitige Includes</span><span class="sxs-lookup"><span data-stu-id="41011-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-204">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="41011-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="41011-205">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="41011-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-206">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="41011-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="41011-207">IIS 6-Metabase-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="41011-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-208">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="41011-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="41011-209">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="41011-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-210">.NET 3,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="41011-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="41011-211">.NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="41011-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-212">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="41011-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="41011-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="41011-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-214">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="41011-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="41011-215">ASP.NET 4,5</span><span class="sxs-lookup"><span data-stu-id="41011-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-216">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="41011-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="41011-217">HTTP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="41011-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-218">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="41011-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="41011-219">TCP-Port Freigabe</span><span class="sxs-lookup"><span data-stu-id="41011-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-220">Intelligenter Hintergrundübertragungsdienst</span><span class="sxs-lookup"><span data-stu-id="41011-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="41011-221">IIS-Server Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="41011-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-222">Freihand- und Handschriftdienste</span><span class="sxs-lookup"><span data-stu-id="41011-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="41011-223">Freihand- und Handschriftdienste</span><span class="sxs-lookup"><span data-stu-id="41011-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="41011-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="41011-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="41011-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-226">Benutzeroberflächen und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="41011-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="41011-227">Grafische Verwaltungs Tools und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="41011-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-228">Benutzeroberflächen und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="41011-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="41011-229">Desktop Umgebung</span><span class="sxs-lookup"><span data-stu-id="41011-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-230">Benutzeroberflächen und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="41011-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="41011-231">Server-grafische Shell</span><span class="sxs-lookup"><span data-stu-id="41011-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="41011-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="41011-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="41011-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41011-234">Windows-Prozessaktivierungsdienst</span><span class="sxs-lookup"><span data-stu-id="41011-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="41011-235">Prozessmodell</span><span class="sxs-lookup"><span data-stu-id="41011-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41011-236">Windows-Prozessaktivierungsdienst</span><span class="sxs-lookup"><span data-stu-id="41011-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="41011-237">Konfigurations-APIs</span><span class="sxs-lookup"><span data-stu-id="41011-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="41011-238">In Windows Server 2012 und Windows Server 2012 R2 können Sie Windows PowerShell 3,0 zum Installieren der IIS-Anforderungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="41011-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="41011-239">Geben Sie unter Verwendung des Server-Moduls in Windows PowerShell 3,0 Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="41011-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="41011-240">Neu mit Windows Server 2012 ist der-source-Parameter, der definiert, wo die Windows Server 2012 Quellmedien gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="41011-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="41011-241">Die Medien können als DVD-Laufwerk (beispielsweise D:\Sources\Sxs) oder für eine Netzwerkfreigabe definiert werden, in der die Mediendateien kopiert wurden (beispielsweise \\fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="41011-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41011-242">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41011-242">See Also</span></span>


[<span data-ttu-id="41011-243">IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41011-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

