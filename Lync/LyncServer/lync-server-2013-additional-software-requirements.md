---
title: 'Lync Server 2013: zusätzliche Softwareanforderungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a4a0c2e200c779d87a13c08eada968b27a7447f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521232"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="01270-102">Zusätzliche Softwareanforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01270-102">Additional software requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01270-103">_**Letztes Änderungsstand des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="01270-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="01270-104">Zusätzlich zu den Hardware-und Betriebssystemanforderungen für Serverplattformen erfordert lync Server 2013 die Installation zusätzlicher Software auf den Servern, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="01270-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="01270-105">Ausführliche Informationen zu den Plattformanforderungen für Server, auf denen lync Server ausgeführt werden, finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System Support in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="01270-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="01270-106">Ausführliche Informationen zu den Systemanforderungen für Clientcomputer und-Geräte finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for Clients and Devices in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="01270-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="01270-107">Ausführliche Informationen zu den Softwareanforderungen für Verwaltungstools finden Sie unter <A href="lync-server-2013-administrative-tools-software-requirements.md">Software Requirements for Administration Tools in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="01270-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="01270-108">Zusätzliche Software, die für alle internen Server Rollen erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="01270-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="01270-109">In diesem Abschnitt werden die erforderlichen Softwarekomponenten für alle internen Serverrollen aufgelistet, die alle lync Server Serverrollen außer Edgeserver sind.</span><span class="sxs-lookup"><span data-stu-id="01270-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="01270-110">Die Anforderungen für die Edgeserver und Edge-Pools werden weiter unten in diesem Thema unter **zusätzliche Software für Edgeserver**aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="01270-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="01270-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="01270-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="01270-112">Auf jedem Server mit lync Server 2013 muss die richtige Version von Windows PowerShell 3,0 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="01270-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="01270-113">Ausführliche Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="01270-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="01270-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="01270-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="01270-115">Lync Server erfordert Microsoft .NET Framework 4.5 für alle internen Server Rollen und auf jedem Computer, auf dem Sie die lync Server Verwaltungstools oder Microsoft lync Server 2013, Planungs Tool ausführen werden.</span><span class="sxs-lookup"><span data-stu-id="01270-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="01270-116">Für lync Server 2013 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4.5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="01270-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="01270-117">Um es manuell zu installieren, laden Sie das Microsoft .NET 4,5 Framework aus dem Microsoft Download Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="01270-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="01270-118">Installieren von Microsoft .NET Framework 4.5 auf Servern mit Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="01270-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="01270-119">Wenn Sie Microsoft .NET Framework 4.5 auf Servern installieren, auf denen lync Server 2013 und Windows Server 2012 ausgeführt wird, müssen Sie einen weiteren Schritt ausführen.</span><span class="sxs-lookup"><span data-stu-id="01270-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="01270-120">Nachdem .NET Framework 4.5 installiert wurde, verwenden Sie Server-Manager, um die HTTP-Aktivierung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="01270-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="01270-121">**So installieren Sie die .NET 4,5-HTTP-Aktivierung auf Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="01270-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="01270-122">Klicken Sie im **Startmenü** auf **Programme**und dann auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="01270-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="01270-123">Wählen Sie im Server-Manager unter **Zusammenfassung der Features**die Option **Features hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="01270-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="01270-124">Erweitern Sie **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="01270-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="01270-125">Wählen Sie **WCF-Aktivierung** aus, wenn Sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="01270-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="01270-126">Wählen Sie dann **http-Aktivierung**aus.</span><span class="sxs-lookup"><span data-stu-id="01270-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="01270-127">Klicken Sie auf **weiter** , und führen Sie die Anweisungen aus, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="01270-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="01270-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="01270-128">Windows Identity Foundation</span></span>

<span data-ttu-id="01270-129">**WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="01270-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="01270-130">Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="01270-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="01270-131">Wählen Sie Ihr Server Betriebssystem aus der folgenden Liste aus:</span><span class="sxs-lookup"><span data-stu-id="01270-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="01270-132">Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="01270-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="01270-133">Wechseln Sie dazu zu **Software hinzufügen/entfernen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="01270-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="01270-134">Ausführliche Informationen zum Installieren von Windows Identity Foundation finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="01270-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="01270-135">Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren.</span><span class="sxs-lookup"><span data-stu-id="01270-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="01270-136">Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**von Server-Manager die Option **Features**aus.</span><span class="sxs-lookup"><span data-stu-id="01270-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="01270-137">Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="01270-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="01270-138">Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="01270-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="01270-139">Zusätzliche Software für alle Front-End-Server und Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="01270-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="01270-140">Alle Front-End-Server und Standard Edition-Server müssen auch Internet Information Services (IIS) mit bestimmten Modulen ausführen.</span><span class="sxs-lookup"><span data-stu-id="01270-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="01270-141">Darüber hinaus müssen alle Front-End-Server und Standard Edition-Server, auf denen Konferenz-, Anwendung zum Parken von anrufen-, Ankündigungs-oder Reaktionsgruppen bereitgestellt werden, Windows Media Format Runtime ausführen.</span><span class="sxs-lookup"><span data-stu-id="01270-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="01270-142">Internetinformationsdienste (IIS)</span><span class="sxs-lookup"><span data-stu-id="01270-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="01270-143">Front-End-Server und Standard Edition-Server müssen Internet Information Services (IIS) mit den folgenden Modulen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="01270-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="01270-144">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="01270-144">Static Content</span></span>

  - <span data-ttu-id="01270-145">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="01270-145">Default Document</span></span>

  - <span data-ttu-id="01270-146">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="01270-146">HTTP Errors</span></span>

  - <span data-ttu-id="01270-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="01270-147">ASP.NET</span></span>

  - <span data-ttu-id="01270-148">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="01270-148">.NET Extensibility</span></span>

  - <span data-ttu-id="01270-149">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="01270-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="01270-150">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="01270-150">ISAPI Filters</span></span>

  - <span data-ttu-id="01270-151">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="01270-151">HTTP Logging</span></span>

  - <span data-ttu-id="01270-152">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="01270-152">Logging Tools</span></span>

  - <span data-ttu-id="01270-153">Tracing</span><span class="sxs-lookup"><span data-stu-id="01270-153">Tracing</span></span>

  - <span data-ttu-id="01270-154">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="01270-154">Windows Authentication</span></span>

  - <span data-ttu-id="01270-155">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="01270-155">Request Filtering</span></span>

  - <span data-ttu-id="01270-156">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="01270-156">Static Content Compression</span></span>

  - <span data-ttu-id="01270-157">Komprimierung dynamischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="01270-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="01270-158">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="01270-158">IIS Management Console</span></span>

  - <span data-ttu-id="01270-159">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="01270-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="01270-160">Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert.)</span><span class="sxs-lookup"><span data-stu-id="01270-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="01270-161">Authentifizierung der Client Zertifikatzuordnung</span><span class="sxs-lookup"><span data-stu-id="01270-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="01270-162">Windows Media Format Laufzeit und Windows-Desktop Erfahrung</span><span class="sxs-lookup"><span data-stu-id="01270-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="01270-163">**Windows-Desktop Umgebung** Auf allen Front-End-Servern und Standard Edition-Servern, auf denen Konferenzen bereitgestellt werden, muss die Windows Media Format Runtime installiert sein, die mit Ausnahme von Windows Server 2012 als Teil der Windows-Desktopumgebung installiert wird.</span><span class="sxs-lookup"><span data-stu-id="01270-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="01270-164">Für Windows Server 2012 ist Microsoft Media Foundation erforderlich.</span><span class="sxs-lookup"><span data-stu-id="01270-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="01270-165">Die Windows Media Format-Laufzeitkomponente ist für die WMA-Dateien (Windows Media Audio) erforderlich, die in der Anwendung zum Parken von Anrufen, in der Ansageanwendung und in der Reaktionsgruppenanwendung für die Wiedergabe von Ansagen und Musik verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01270-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="01270-166">Es wird empfohlen, dass Sie Windows Desktop Experience installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="01270-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="01270-167">Wenn lync Server 2013 diese Software nicht auf dem Server findet, werden Sie aufgefordert, Sie zu installieren, und Sie müssen den Server neu starten, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="01270-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="01270-168">Zusätzliche Software für Front-End-Server und Standard Edition-Server mit Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="01270-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="01270-169">Front-End-Server benötigen .NET 3,5, das in Windows Server 2012 nicht standardmäßig installiert ist.</span><span class="sxs-lookup"><span data-stu-id="01270-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="01270-170">Um Sie zu installieren, legen Sie die Windows Server 2012 Installationsmedien in Laufwerk D ab, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="01270-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="01270-171">Ausführliche Informationen zur Installation von .NET 3,5 auf Servern mit Windows Server 2012 finden Sie unter "Überlegungen zur Microsoft .NET Framework 3.5-Bereitstellung" unter <https://go.microsoft.com/fwlink/p/?linkid=275032> .</span><span class="sxs-lookup"><span data-stu-id="01270-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="01270-172">Zusätzliche Software für Directors</span><span class="sxs-lookup"><span data-stu-id="01270-172">Additional Software for Directors</span></span>

<span data-ttu-id="01270-173">Directors müssen Internet Information Services (IIS) mit den folgenden Modulen ausführen:</span><span class="sxs-lookup"><span data-stu-id="01270-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="01270-174">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="01270-174">Static Content</span></span>

  - <span data-ttu-id="01270-175">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="01270-175">Default Document</span></span>

  - <span data-ttu-id="01270-176">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="01270-176">HTTP Errors</span></span>

  - <span data-ttu-id="01270-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="01270-177">ASP.NET</span></span>

  - <span data-ttu-id="01270-178">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="01270-178">.NET Extensibility</span></span>

  - <span data-ttu-id="01270-179">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="01270-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="01270-180">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="01270-180">ISAPI Filters</span></span>

  - <span data-ttu-id="01270-181">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="01270-181">HTTP Logging</span></span>

  - <span data-ttu-id="01270-182">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="01270-182">Logging Tools</span></span>

  - <span data-ttu-id="01270-183">Tracing</span><span class="sxs-lookup"><span data-stu-id="01270-183">Tracing</span></span>

  - <span data-ttu-id="01270-184">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="01270-184">Windows Authentication</span></span>

  - <span data-ttu-id="01270-185">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="01270-185">Request Filtering</span></span>

  - <span data-ttu-id="01270-186">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="01270-186">Static Content Compression</span></span>

  - <span data-ttu-id="01270-187">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="01270-187">IIS Management Console</span></span>

  - <span data-ttu-id="01270-188">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="01270-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="01270-189">Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert.)</span><span class="sxs-lookup"><span data-stu-id="01270-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="01270-190">Authentifizierung der Client Zertifikatzuordnung</span><span class="sxs-lookup"><span data-stu-id="01270-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="01270-191">Zusätzliche Software für Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="01270-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="01270-192">Front-End-Server für beständigen Chat müssen Message Queuing (auch als MSMQ bezeichnet) ausführen, bei dem es sich um eine Komponente von Windows Server handelt.</span><span class="sxs-lookup"><span data-stu-id="01270-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="01270-193">Informationen zum Aktivieren von MSMQ finden [Sie hier.](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="01270-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="01270-194">Zusätzliche Software für Edge-Server</span><span class="sxs-lookup"><span data-stu-id="01270-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="01270-195">Für Edgeserver ist die folgende Software erforderlich:</span><span class="sxs-lookup"><span data-stu-id="01270-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="01270-196">Auf jedem Server mit lync Server 2013 muss die richtige Version von Windows PowerShell 3,0 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="01270-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="01270-197">Ausführliche Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="01270-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="01270-198">Lync Server erfordert Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="01270-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="01270-199">Für lync Server 2013, die auf Windows Server 2008 R2 installiert sind, müssen Sie die 64-Bit-Edition von Microsoft .NET Framework 4.5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="01270-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="01270-200">Um es manuell zu installieren, laden Sie das Microsoft .NET 4,5 Framework aus dem Microsoft Download Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="01270-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="01270-201">**WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="01270-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="01270-202">Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="01270-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="01270-203">Wählen Sie Ihr Server Betriebssystem aus der folgenden Liste aus:</span><span class="sxs-lookup"><span data-stu-id="01270-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="01270-204">Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="01270-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="01270-205">Wechseln Sie dazu zu **Software hinzufügen/entfernen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="01270-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="01270-206">Ausführliche Informationen zum Installieren von Windows Identity Foundation finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="01270-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="01270-207">Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren.</span><span class="sxs-lookup"><span data-stu-id="01270-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="01270-208">Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**von Server-Manager die Option **Features**aus.</span><span class="sxs-lookup"><span data-stu-id="01270-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="01270-209">Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="01270-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="01270-210">Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="01270-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="01270-211">Installieren von mehrschichtigen Socket-Anbietern auf Medienservern</span><span class="sxs-lookup"><span data-stu-id="01270-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="01270-212">Installieren Sie keine ISA (Microsoft Internet Security and Acceleration Server)-Client Software oder andere LSP-Software (Winsock Layered Service Providers) auf allen Front-End-Servern oder eigenständigen Vermittlungsservern.</span><span class="sxs-lookup"><span data-stu-id="01270-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="01270-213">Die Installation dieser Software kann zu einer schlechten Leistung des Datenverkehrs führen.</span><span class="sxs-lookup"><span data-stu-id="01270-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01270-214">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01270-214">See Also</span></span>


[<span data-ttu-id="01270-215">Softwareanforderungen für Verwaltungstools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="01270-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

