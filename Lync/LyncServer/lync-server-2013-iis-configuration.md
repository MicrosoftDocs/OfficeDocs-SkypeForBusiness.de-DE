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
ms.openlocfilehash: 1fc8895a144b4911560af8fd6a2f12d576f3ec14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528152"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="89213-102">IIS-Konfiguration in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89213-102">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89213-103">_**Letztes Änderungsstand des Themas:** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="89213-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="89213-104">Zum erfolgreichen Durchführen dieses Verfahrens müssen Sie beim Computer mit den Mindestberechtigungen eines lokalen Administrators und Domänenbenutzers angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="89213-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="89213-105">Bevor Sie die Front-End-Server für lync Server 2013, Standard Edition oder den ersten Front-End-Server in einem Pool konfigurieren und installieren, installieren und konfigurieren Sie die Server Rolle und Webdienste für Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="89213-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="89213-106">Wenn in Ihrer Organisation IIS und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk lokalisiert werden müssen, können Sie den Installationspfad für die lync Server 2013 Dateien im Dialogfeld Setup ändern, wenn Sie die lync Server 2013-Verwaltungstools zunächst installieren.</span><span class="sxs-lookup"><span data-stu-id="89213-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="89213-107">Sie installieren die Verwaltungstools vor der Installation von IIS.</span><span class="sxs-lookup"><span data-stu-id="89213-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="89213-108">Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore.msi, werden auch die restlichen lync Server 2013 Dateien auf diesem Laufwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="89213-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="89213-109">Informationen zu dtails finden Sie unter <A href="lync-server-2013-install-lync-server-administrative-tools.md">install lync Server 2013 Administration Tools</A>.</span><span class="sxs-lookup"><span data-stu-id="89213-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="89213-110">Ausführliche Informationen zum Verschieben des von Windows Server-Manager bereitgestellten Verzeichnis Inetpub bei der Installation von IIS finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .</span><span class="sxs-lookup"><span data-stu-id="89213-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="89213-111">In der folgenden Tabelle sind die erforderlichen IIS 7,5-Rollendienste angegeben.</span><span class="sxs-lookup"><span data-stu-id="89213-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="89213-112">IIS 7,5-Rollendienste</span><span class="sxs-lookup"><span data-stu-id="89213-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89213-113">Rollenüberschrift</span><span class="sxs-lookup"><span data-stu-id="89213-113">Role Heading</span></span></th>
<th><span data-ttu-id="89213-114">Rollendienst</span><span class="sxs-lookup"><span data-stu-id="89213-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89213-115">Allgemeine HTTP-Funktionen installiert</span><span class="sxs-lookup"><span data-stu-id="89213-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="89213-116">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="89213-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-117">Allgemeine HTTP-Funktionen installiert</span><span class="sxs-lookup"><span data-stu-id="89213-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="89213-118">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="89213-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-119">Allgemeine HTTP-Funktionen installiert</span><span class="sxs-lookup"><span data-stu-id="89213-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="89213-120">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="89213-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-121">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="89213-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="89213-122">ASP.NET</span></span></p>
<p><span data-ttu-id="89213-123">Windows Server 2012 erfordert auch ASP. NET 4.5</span><span class="sxs-lookup"><span data-stu-id="89213-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-124">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="89213-125">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="89213-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-126">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="89213-127">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="89213-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-128">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="89213-129">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="89213-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-130">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="89213-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="89213-131">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="89213-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-132">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="89213-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="89213-133">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="89213-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-134">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="89213-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="89213-135">Tracing</span><span class="sxs-lookup"><span data-stu-id="89213-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-136">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="89213-136">Security</span></span></p></td>
<td><p><span data-ttu-id="89213-137">Anonyme Authentifizierung (standardmäßig installiert und aktiviert)</span><span class="sxs-lookup"><span data-stu-id="89213-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-138">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="89213-138">Security</span></span></p></td>
<td><p><span data-ttu-id="89213-139">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89213-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-140">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="89213-140">Security</span></span></p></td>
<td><p><span data-ttu-id="89213-141">Clientzertifikatzuordnungs-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89213-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-142">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="89213-142">Security</span></span></p></td>
<td><p><span data-ttu-id="89213-143">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="89213-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-144">Leistung</span><span class="sxs-lookup"><span data-stu-id="89213-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="89213-145">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="89213-145">Static content compression</span></span></p>
<p><span data-ttu-id="89213-146">Komprimierung dynamischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="89213-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-147">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="89213-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="89213-148">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="89213-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-149">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="89213-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="89213-150">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="89213-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="89213-151">Auf dem Betriebssystem Windows Server 2008 R2 SP1 x64 können Sie Windows PowerShell 2,0 verwenden.</span><span class="sxs-lookup"><span data-stu-id="89213-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="89213-152">Sie müssen zunächst das Modul "ServerManager" importieren und anschließend die IIS 7.5-Rolle und -Rollendienste installieren.</span><span class="sxs-lookup"><span data-stu-id="89213-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="89213-153">Die anonyme Authentifizierung wird bei der Installation der IIS-Serverrolle standardmäßig installiert.</span><span class="sxs-lookup"><span data-stu-id="89213-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="89213-154">Sie können die anonyme Authentifizierung nach der Installation von IIS verwalten.</span><span class="sxs-lookup"><span data-stu-id="89213-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="89213-155">Ausführliche Informationen finden Sie unter "Aktivieren der anonymen Authentifizierung (IIS 7.0)" unter <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .</span><span class="sxs-lookup"><span data-stu-id="89213-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="89213-156">In der folgenden Tabelle werden die erforderlichen IIS 8,0-und IIS 8,5-Rollendienste für Windows Server 2012 und Windows Server 2012 R2 angegeben.</span><span class="sxs-lookup"><span data-stu-id="89213-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="89213-157">Für Windows Server 2012 und Windows Server 2012 R2 wurde das Cmdlet Add-WindowsFeature durch das Install-WindowsFeature-Cmdlet ersetzt.</span><span class="sxs-lookup"><span data-stu-id="89213-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="89213-158">Ausführliche Informationen finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">install-Cmdlets</A>.</span><span class="sxs-lookup"><span data-stu-id="89213-158">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="89213-159">IIS 8,0 und IIS 8,5-Rollendienste</span><span class="sxs-lookup"><span data-stu-id="89213-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89213-160">Rollenüberschrift</span><span class="sxs-lookup"><span data-stu-id="89213-160">Role Heading</span></span></th>
<th><span data-ttu-id="89213-161">Rollendienst</span><span class="sxs-lookup"><span data-stu-id="89213-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89213-162">Webserver (IIS)</span><span class="sxs-lookup"><span data-stu-id="89213-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="89213-163">Webserver</span><span class="sxs-lookup"><span data-stu-id="89213-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-164">Allgemeine HTTP-Features</span><span class="sxs-lookup"><span data-stu-id="89213-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="89213-165">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="89213-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-166">Allgemeine HTTP-Features</span><span class="sxs-lookup"><span data-stu-id="89213-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="89213-167">Verzeichnissuche</span><span class="sxs-lookup"><span data-stu-id="89213-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-168">Allgemeine HTTP-Features</span><span class="sxs-lookup"><span data-stu-id="89213-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="89213-169">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="89213-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-170">Allgemeine HTTP-Features</span><span class="sxs-lookup"><span data-stu-id="89213-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="89213-171">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="89213-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-172">Allgemeine HTTP-Funktionen</span><span class="sxs-lookup"><span data-stu-id="89213-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="89213-173">HTTP-Umleitung</span><span class="sxs-lookup"><span data-stu-id="89213-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-174">Systemzustand und Diagnose</span><span class="sxs-lookup"><span data-stu-id="89213-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="89213-175">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="89213-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-176">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="89213-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="89213-177">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="89213-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-178">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="89213-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="89213-179">Anforderungsüberwachung</span><span class="sxs-lookup"><span data-stu-id="89213-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-180">Integrität und Diagnose</span><span class="sxs-lookup"><span data-stu-id="89213-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="89213-181">Tracing</span><span class="sxs-lookup"><span data-stu-id="89213-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-182">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="89213-182">Security</span></span></p></td>
<td><p><span data-ttu-id="89213-183">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="89213-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-184">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="89213-184">Security</span></span></p></td>
<td><p><span data-ttu-id="89213-185">Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="89213-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-186">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="89213-186">Security</span></span></p></td>
<td><p><span data-ttu-id="89213-187">Authentifizierung der Client Zertifikatzuordnung</span><span class="sxs-lookup"><span data-stu-id="89213-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-188">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="89213-188">Security</span></span></p></td>
<td><p><span data-ttu-id="89213-189">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="89213-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-190">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="89213-191">.NET-Erweiterbarkeit 3,5</span><span class="sxs-lookup"><span data-stu-id="89213-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-192">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="89213-193">.NET-Erweiterbarkeit 4,5</span><span class="sxs-lookup"><span data-stu-id="89213-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-194">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="89213-195">ASP.NET 3,5</span><span class="sxs-lookup"><span data-stu-id="89213-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-196">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="89213-197">ASP.NET 4,5</span><span class="sxs-lookup"><span data-stu-id="89213-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-198">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="89213-199">ISAPI-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="89213-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-200">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="89213-201">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="89213-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-202">Anwendungsentwicklung</span><span class="sxs-lookup"><span data-stu-id="89213-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="89213-203">Serverseitige Includes</span><span class="sxs-lookup"><span data-stu-id="89213-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-204">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="89213-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="89213-205">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="89213-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-206">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="89213-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="89213-207">IIS 6-Metabase-Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="89213-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-208">Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="89213-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="89213-209">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="89213-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-210">.NET 3,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="89213-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="89213-211">.NET 3,5 Framework</span><span class="sxs-lookup"><span data-stu-id="89213-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-212">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="89213-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="89213-213">.NET Framework 4,5</span><span class="sxs-lookup"><span data-stu-id="89213-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-214">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="89213-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="89213-215">ASP.NET 4,5</span><span class="sxs-lookup"><span data-stu-id="89213-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-216">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="89213-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="89213-217">HTTP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="89213-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-218">.NET 4,5 Framework-Features</span><span class="sxs-lookup"><span data-stu-id="89213-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="89213-219">TCP-Port Freigabe</span><span class="sxs-lookup"><span data-stu-id="89213-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-220">Intelligenter Hintergrundübertragungsdienst</span><span class="sxs-lookup"><span data-stu-id="89213-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="89213-221">IIS-Server Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="89213-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-222">Freihand- und Handschriftdienste</span><span class="sxs-lookup"><span data-stu-id="89213-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="89213-223">Freihand- und Handschriftdienste</span><span class="sxs-lookup"><span data-stu-id="89213-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-224">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="89213-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="89213-225">Media Foundation</span><span class="sxs-lookup"><span data-stu-id="89213-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-226">Benutzeroberflächen und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="89213-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="89213-227">Grafische Verwaltungs Tools und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="89213-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-228">Benutzeroberflächen und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="89213-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="89213-229">Desktop Umgebung</span><span class="sxs-lookup"><span data-stu-id="89213-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-230">Benutzeroberflächen und Infrastruktur</span><span class="sxs-lookup"><span data-stu-id="89213-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="89213-231">Server-grafische Shell</span><span class="sxs-lookup"><span data-stu-id="89213-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-232">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="89213-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="89213-233">Windows Identity Foundation 3,5</span><span class="sxs-lookup"><span data-stu-id="89213-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89213-234">Windows-Prozessaktivierungsdienst</span><span class="sxs-lookup"><span data-stu-id="89213-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="89213-235">Prozessmodell</span><span class="sxs-lookup"><span data-stu-id="89213-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89213-236">Windows-Prozessaktivierungsdienst</span><span class="sxs-lookup"><span data-stu-id="89213-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="89213-237">Konfigurations-APIs</span><span class="sxs-lookup"><span data-stu-id="89213-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="89213-238">In Windows Server 2012 und Windows Server 2012 R2 können Sie Windows PowerShell 3,0 zum Installieren der IIS-Anforderungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="89213-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="89213-239">Geben Sie unter Verwendung des Server-Moduls in Windows PowerShell 3,0 Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="89213-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="89213-240">Neu mit Windows Server 2012 ist der-source-Parameter, der definiert, wo die Windows Server 2012 Quellmedien gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="89213-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="89213-241">Die Medien können als DVD-Laufwerk (beispielsweise D:\Sources\Sxs) oder für eine Netzwerkfreigabe definiert werden, in der die Mediendateien kopiert wurden (beispielsweise \\ fileserver\windows2012\sources\Sxs).</span><span class="sxs-lookup"><span data-stu-id="89213-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="89213-242">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89213-242">See Also</span></span>


[<span data-ttu-id="89213-243">IIS-Anforderungen für Front-End-Pools und Standard Edition-Server in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89213-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

