---
title: 'Lync Server 2013: Zusätzliche Softwareanforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e21a375fecbd109e108806dc816a9fa3fce81a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839921"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="ae7ac-102">Zusätzliche Softwareanforderungen für Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae7ac-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae7ac-103">_**Letztes Änderungsdatum des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="ae7ac-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="ae7ac-104">Zusätzlich zu den Hardware-und Betriebssystemanforderungen für Serverplattformen erfordert lync Server 2013 die Installation zusätzlicher Software auf den von Ihnen bereitgestellten Servern.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ae7ac-105">Details zu den Plattformanforderungen für Server mit lync Server finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server-Hardwareplattformen für lync Server 2013</A> und <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server-und Tools-Betriebssystemunterstützung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="ae7ac-106">Ausführliche Informationen zu den Systemanforderungen für Clientcomputer und Geräte finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planen von Clients und Geräten in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="ae7ac-107">Details zu den Softwareanforderungen für Verwaltungstools finden Sie unter <A href="lync-server-2013-administrative-tools-software-requirements.md">Softwareanforderungen für Verwaltungstools in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="ae7ac-108">Zusätzliche Software, die für alle internen Server Rollen erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="ae7ac-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="ae7ac-109">Dieser Abschnitt listet Software auf, die für alle internen Serverrollen erforderlich ist, bei denen es sich um alle lync Server-Serverrollen mit Ausnahme von Edgeserver handelt.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="ae7ac-110">Die Anforderungen für die Edgeserver und Edge-Pools sind weiter unten in diesem Thema unter **zusätzliche Software für Edgeserver**aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="ae7ac-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="ae7ac-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="ae7ac-112">Auf jedem Server, auf dem lync Server 2013 ausgeführt wird, muss die richtige Version von Windows PowerShell 3,0 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="ae7ac-113">Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="ae7ac-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="ae7ac-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="ae7ac-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="ae7ac-115">Lync Server erfordert Microsoft .NET Framework 4,5 auf allen internen Server Rollen und auf allen Computern, auf denen Sie die lync Server-Verwaltungstools oder Microsoft lync Server 2013, Planungs Tool, ausführen werden.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="ae7ac-116">Bei lync Server 2013 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4,5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="ae7ac-117">Wenn Sie die Datei manuell installieren möchten, laden Sie das Microsoft .NET 4,5-Framework aus dem Microsoft Download Center unter[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="ae7ac-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="ae7ac-118">Installieren von Microsoft .NET Framework 4,5 auf Servern mit Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="ae7ac-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="ae7ac-119">Wenn Sie Microsoft .NET Framework 4,5 auf Servern installieren, auf denen lync Server 2013 und Windows Server 2012 ausgeführt wird, müssen Sie einen weiteren Schritt ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="ae7ac-120">Verwenden Sie nach der Installation von .NET Framework 4,5 den Server-Manager, um die HTTP-Aktivierung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="ae7ac-121">**So installieren Sie die .NET 4,5-HTTP-Aktivierung unter Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="ae7ac-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="ae7ac-122">Klicken Sie im **Startmenü** auf **Programme**und dann auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="ae7ac-123">Wählen Sie im Server-Manager unter **Zusammenfassung der Features**die Option **Features hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="ae7ac-124">Erweitern Sie **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="ae7ac-125">Wählen Sie **WCF-Aktivierung** aus, wenn Sie noch nicht ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="ae7ac-126">Wählen Sie dann **http-Aktivierung**aus.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="ae7ac-127">Klicken Sie auf **weiter** , und folgen Sie den Anweisungen, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="ae7ac-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="ae7ac-128">Windows Identity Foundation</span></span>

<span data-ttu-id="ae7ac-129">**WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="ae7ac-130">Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="ae7ac-131">Wählen Sie das Betriebssystem Ihres Servers aus der folgenden Liste aus:</span><span class="sxs-lookup"><span data-stu-id="ae7ac-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="ae7ac-132">Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="ae7ac-133">Wechseln Sie dazu zu **Programme hinzufügen/entfernen**, **installierte Updates anzeigen**, und suchen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="ae7ac-134">Informationen zum Installieren von Windows Identity Foundation finden Sie [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)unter.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="ae7ac-135">Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="ae7ac-136">Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**des Server-Managers **Features**aus.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="ae7ac-137">Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="ae7ac-138">Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="ae7ac-139">Zusätzliche Software für alle Front-End-Server und Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="ae7ac-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="ae7ac-140">Alle Front-End-Server und Standard Edition-Server müssen auch Internet Informationsdienste (IIS) mit bestimmten Modulen ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="ae7ac-141">Darüber hinaus müssen alle Front-End-Server und Standard Edition-Server, auf denen Konferenz-, Anruf Park-, Ankündigungs-oder Antwortgruppen bereitgestellt werden, die Windows Media-Format Laufzeit ausführen.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="ae7ac-142">Internetinformationsdienste (Internet Information Services, IIS)</span><span class="sxs-lookup"><span data-stu-id="ae7ac-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="ae7ac-143">Front-End-Server und Standard Edition-Server müssen Internet Informationsdienste (IIS) mit den folgenden Modulen ausführen:</span><span class="sxs-lookup"><span data-stu-id="ae7ac-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="ae7ac-144">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="ae7ac-144">Static Content</span></span>

  - <span data-ttu-id="ae7ac-145">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="ae7ac-145">Default Document</span></span>

  - <span data-ttu-id="ae7ac-146">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="ae7ac-146">HTTP Errors</span></span>

  - <span data-ttu-id="ae7ac-147">ASP.net</span><span class="sxs-lookup"><span data-stu-id="ae7ac-147">ASP.NET</span></span>

  - <span data-ttu-id="ae7ac-148">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="ae7ac-148">.NET Extensibility</span></span>

  - <span data-ttu-id="ae7ac-149">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="ae7ac-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="ae7ac-150">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="ae7ac-150">ISAPI Filters</span></span>

  - <span data-ttu-id="ae7ac-151">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-151">HTTP Logging</span></span>

  - <span data-ttu-id="ae7ac-152">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="ae7ac-152">Logging Tools</span></span>

  - <span data-ttu-id="ae7ac-153">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-153">Tracing</span></span>

  - <span data-ttu-id="ae7ac-154">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-154">Windows Authentication</span></span>

  - <span data-ttu-id="ae7ac-155">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-155">Request Filtering</span></span>

  - <span data-ttu-id="ae7ac-156">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="ae7ac-156">Static Content Compression</span></span>

  - <span data-ttu-id="ae7ac-157">Komprimierung dynamischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="ae7ac-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="ae7ac-158">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="ae7ac-158">IIS Management Console</span></span>

  - <span data-ttu-id="ae7ac-159">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="ae7ac-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="ae7ac-160">Anonyme Authentifizierung (standardmäßig installiert, wenn IIS installiert ist)</span><span class="sxs-lookup"><span data-stu-id="ae7ac-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="ae7ac-161">Clientzertifikatzuordnungs-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="ae7ac-162">Windows Media Format-Laufzeit und Windows-Desktop Experience</span><span class="sxs-lookup"><span data-stu-id="ae7ac-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="ae7ac-163">**Windows-Desktop Umgebung** Auf allen Front-End-Servern und Standard Edition-Servern, auf denen Konferenzen bereitgestellt werden, muss die Windows Media-Format Laufzeit installiert sein, die, mit Ausnahme von Windows Server 2012, als Teil der Windows-Desktopumgebung installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="ae7ac-164">Windows Server 2012 erfordert Microsoft Media Foundation.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="ae7ac-165">Die Windows Media-Format Laufzeit ist erforderlich, um die Windows Media-Audio-Dateien (WMA) auszuführen, die von den Anwendungen für die Anruf Park-, Ankündigungs-und Reaktionsgruppen für Ankündigungen und Musik abgespielt werden.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="ae7ac-166">Wir empfehlen, dass Sie die Windows-Desktopumgebung installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="ae7ac-167">Wenn lync Server 2013 diese Software auf dem Server nicht findet, werden Sie aufgefordert, Sie zu installieren, und dann müssen Sie den Server neu starten, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="ae7ac-168">Zusätzliche Software für Front-End-Server und Standard Edition-Server, die unter Windows Server 2012 ausgeführt werden</span><span class="sxs-lookup"><span data-stu-id="ae7ac-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="ae7ac-169">Für Front-End-Server ist .NET 3,5 erforderlich, das unter Windows Server 2012 nicht standardmäßig installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="ae7ac-170">Installieren Sie das Windows Server 2012-Installationsmedium auf Laufwerk D, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="ae7ac-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="ae7ac-171">Details zur Installation von .NET 3,5 auf Servern mit Windows Server 2012 finden Sie unter "Microsoft .NET Framework 3,5-Bereitstellungs <https://go.microsoft.com/fwlink/p/?linkid=275032>Überlegungen" unter.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="ae7ac-172">Zusätzliche Software für Directors</span><span class="sxs-lookup"><span data-stu-id="ae7ac-172">Additional Software for Directors</span></span>

<span data-ttu-id="ae7ac-173">Directors müssen Internet Informationsdienste (IIS) mit den folgenden Modulen ausführen:</span><span class="sxs-lookup"><span data-stu-id="ae7ac-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="ae7ac-174">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="ae7ac-174">Static Content</span></span>

  - <span data-ttu-id="ae7ac-175">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="ae7ac-175">Default Document</span></span>

  - <span data-ttu-id="ae7ac-176">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="ae7ac-176">HTTP Errors</span></span>

  - <span data-ttu-id="ae7ac-177">ASP.net</span><span class="sxs-lookup"><span data-stu-id="ae7ac-177">ASP.NET</span></span>

  - <span data-ttu-id="ae7ac-178">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="ae7ac-178">.NET Extensibility</span></span>

  - <span data-ttu-id="ae7ac-179">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="ae7ac-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="ae7ac-180">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="ae7ac-180">ISAPI Filters</span></span>

  - <span data-ttu-id="ae7ac-181">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-181">HTTP Logging</span></span>

  - <span data-ttu-id="ae7ac-182">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="ae7ac-182">Logging Tools</span></span>

  - <span data-ttu-id="ae7ac-183">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-183">Tracing</span></span>

  - <span data-ttu-id="ae7ac-184">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-184">Windows Authentication</span></span>

  - <span data-ttu-id="ae7ac-185">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-185">Request Filtering</span></span>

  - <span data-ttu-id="ae7ac-186">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="ae7ac-186">Static Content Compression</span></span>

  - <span data-ttu-id="ae7ac-187">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="ae7ac-187">IIS Management Console</span></span>

  - <span data-ttu-id="ae7ac-188">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="ae7ac-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="ae7ac-189">Anonyme Authentifizierung (standardmäßig installiert, wenn IIS installiert ist)</span><span class="sxs-lookup"><span data-stu-id="ae7ac-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="ae7ac-190">Clientzertifikatzuordnungs-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="ae7ac-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="ae7ac-191">Zusätzliche Software für beständige Chat-Front-End-Server</span><span class="sxs-lookup"><span data-stu-id="ae7ac-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="ae7ac-192">Beständige Chat-Front-End-Server müssen Message Queuing (auch als MSMQ bezeichnet) ausführen, einer Komponente von Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="ae7ac-193">Informationen zum Aktivieren von MSMQ finden [Sie hier.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="ae7ac-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="ae7ac-194">Zusätzliche Software für Edgeserver</span><span class="sxs-lookup"><span data-stu-id="ae7ac-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="ae7ac-195">Edgeserver erfordern die folgende Software:</span><span class="sxs-lookup"><span data-stu-id="ae7ac-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="ae7ac-196">Auf jedem Server, auf dem lync Server 2013 ausgeführt wird, muss die richtige Version von Windows PowerShell 3,0 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="ae7ac-197">Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="ae7ac-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="ae7ac-198">Für lync Server ist Microsoft .NET Framework 4,5 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="ae7ac-199">Für lync Server 2013, das unter Windows Server 2008 R2 installiert ist, müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4,5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="ae7ac-200">Wenn Sie die Datei manuell installieren möchten, laden Sie das Microsoft .NET 4,5-Framework aus dem Microsoft Download Center unter[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="ae7ac-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="ae7ac-201">**WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="ae7ac-202">Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="ae7ac-203">Wählen Sie das Betriebssystem Ihres Servers aus der folgenden Liste aus:</span><span class="sxs-lookup"><span data-stu-id="ae7ac-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="ae7ac-204">Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="ae7ac-205">Wechseln Sie dazu zu **Programme hinzufügen/entfernen**, **installierte Updates anzeigen**, und suchen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="ae7ac-206">Informationen zum Installieren von Windows Identity Foundation finden Sie [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)unter.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="ae7ac-207">Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="ae7ac-208">Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**des Server-Managers **Features**aus.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="ae7ac-209">Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="ae7ac-210">Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="ae7ac-211">Installieren Sie keine Layered Socket-Anbieter auf Medienservern.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="ae7ac-212">Installieren Sie keine Microsoft Internet Security and Acceleration (ISA) Server-Client Software oder eine andere Winsock-Schicht Service Anbieter-Software (LSP) auf allen Front-End-Servern oder eigenständigen Vermittlungsservern.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="ae7ac-213">Die Installation dieser Software kann zu schlechter Leistung des Medien Verkehrs führen.</span><span class="sxs-lookup"><span data-stu-id="ae7ac-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ae7ac-214">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae7ac-214">See Also</span></span>


[<span data-ttu-id="ae7ac-215">Softwareanforderungen für Verwaltungstools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae7ac-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

