---
title: 'Lync Server 2013: zusätzliche Softwareanforderungen'
description: 'Lync Server 2013: zusätzliche Softwareanforderungen.'
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
ms.openlocfilehash: fbc36f23a2246c9d653e47954064182c756f0dff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553041"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="e52bc-103">Zusätzliche Softwareanforderungen für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e52bc-103">Additional software requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e52bc-104">_**Letztes Änderungsstand des Themas:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="e52bc-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="e52bc-105">Zusätzlich zu den Hardware-und Betriebssystemanforderungen für Serverplattformen erfordert lync Server 2013 die Installation zusätzlicher Software auf den Servern, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e52bc-105">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e52bc-106">Ausführliche Informationen zu den Plattformanforderungen für Server, auf denen lync Server ausgeführt werden, finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and Tools Operating System Support in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e52bc-106">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="e52bc-107">Ausführliche Informationen zu den Systemanforderungen für Clientcomputer und-Geräte finden Sie unter <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for Clients and Devices in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="e52bc-107">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="e52bc-108">Ausführliche Informationen zu den Softwareanforderungen für Verwaltungstools finden Sie unter <A href="lync-server-2013-administrative-tools-software-requirements.md">Software Requirements for Administration Tools in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e52bc-108">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="e52bc-109">Zusätzliche Software, die für alle internen Server Rollen erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="e52bc-109">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="e52bc-110">In diesem Abschnitt werden die erforderlichen Softwarekomponenten für alle internen Serverrollen aufgelistet, die alle lync Server Serverrollen außer Edgeserver sind.</span><span class="sxs-lookup"><span data-stu-id="e52bc-110">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="e52bc-111">Die Anforderungen für die Edgeserver und Edge-Pools werden weiter unten in diesem Thema unter **zusätzliche Software für Edgeserver**aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e52bc-111">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="e52bc-112">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="e52bc-112">Windows PowerShell 3.0</span></span>

<span data-ttu-id="e52bc-113">Auf jedem Server mit lync Server 2013 muss die richtige Version von Windows PowerShell 3,0 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="e52bc-113">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="e52bc-114">Ausführliche Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="e52bc-114">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="e52bc-115">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="e52bc-115">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="e52bc-116">Lync Server erfordert Microsoft .NET Framework 4.5 für alle internen Server Rollen und auf jedem Computer, auf dem Sie die lync Server Verwaltungstools oder Microsoft lync Server 2013, Planungs Tool ausführen werden.</span><span class="sxs-lookup"><span data-stu-id="e52bc-116">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="e52bc-117">Für lync Server 2013 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4.5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="e52bc-117">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="e52bc-118">Um es manuell zu installieren, laden Sie das Microsoft .NET 4,5 Framework aus dem Microsoft Download Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="e52bc-118">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="e52bc-119">Installieren von Microsoft .NET Framework 4.5 auf Servern mit Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e52bc-119">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="e52bc-120">Wenn Sie Microsoft .NET Framework 4.5 auf Servern installieren, auf denen lync Server 2013 und Windows Server 2012 ausgeführt wird, müssen Sie einen weiteren Schritt ausführen.</span><span class="sxs-lookup"><span data-stu-id="e52bc-120">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="e52bc-121">Nachdem .NET Framework 4.5 installiert wurde, verwenden Sie Server-Manager, um die HTTP-Aktivierung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e52bc-121">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="e52bc-122">**So installieren Sie die .NET 4,5-HTTP-Aktivierung auf Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="e52bc-122">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="e52bc-123">Klicken Sie im **Startmenü** auf **Programme**und dann auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="e52bc-123">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="e52bc-124">Wählen Sie im Server-Manager unter **Zusammenfassung der Features**die Option **Features hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="e52bc-124">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="e52bc-125">Erweitern Sie **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="e52bc-125">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="e52bc-126">Wählen Sie **WCF-Aktivierung** aus, wenn Sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="e52bc-126">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="e52bc-127">Wählen Sie dann **http-Aktivierung**aus.</span><span class="sxs-lookup"><span data-stu-id="e52bc-127">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="e52bc-128">Klicken Sie auf **weiter** , und führen Sie die Anweisungen aus, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e52bc-128">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="e52bc-129">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="e52bc-129">Windows Identity Foundation</span></span>

<span data-ttu-id="e52bc-130">**WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e52bc-130">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="e52bc-131">Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="e52bc-131">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="e52bc-132">Wählen Sie Ihr Server Betriebssystem aus der folgenden Liste aus:</span><span class="sxs-lookup"><span data-stu-id="e52bc-132">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="e52bc-133">Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e52bc-133">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="e52bc-134">Wechseln Sie dazu zu **Software hinzufügen/entfernen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="e52bc-134">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="e52bc-135">Ausführliche Informationen zum Installieren von Windows Identity Foundation finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="e52bc-135">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="e52bc-136">Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e52bc-136">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="e52bc-137">Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**von Server-Manager die Option **Features**aus.</span><span class="sxs-lookup"><span data-stu-id="e52bc-137">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="e52bc-138">Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="e52bc-138">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="e52bc-139">Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="e52bc-139">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="e52bc-140">Zusätzliche Software für alle Front-End-Server und Standard Edition-Server</span><span class="sxs-lookup"><span data-stu-id="e52bc-140">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="e52bc-141">Alle Front-End-Server und Standard Edition-Server müssen auch Internet Information Services (IIS) mit bestimmten Modulen ausführen.</span><span class="sxs-lookup"><span data-stu-id="e52bc-141">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="e52bc-142">Darüber hinaus müssen alle Front-End-Server und Standard Edition-Server, auf denen Konferenz-, Anwendung zum Parken von anrufen-, Ankündigungs-oder Reaktionsgruppen bereitgestellt werden, Windows Media Format Runtime ausführen.</span><span class="sxs-lookup"><span data-stu-id="e52bc-142">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="e52bc-143">Internetinformationsdienste (IIS)</span><span class="sxs-lookup"><span data-stu-id="e52bc-143">Internet Information Services (IIS)</span></span>

<span data-ttu-id="e52bc-144">Front-End-Server und Standard Edition-Server müssen Internet Information Services (IIS) mit den folgenden Modulen ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="e52bc-144">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="e52bc-145">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="e52bc-145">Static Content</span></span>

  - <span data-ttu-id="e52bc-146">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="e52bc-146">Default Document</span></span>

  - <span data-ttu-id="e52bc-147">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="e52bc-147">HTTP Errors</span></span>

  - <span data-ttu-id="e52bc-148">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e52bc-148">ASP.NET</span></span>

  - <span data-ttu-id="e52bc-149">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="e52bc-149">.NET Extensibility</span></span>

  - <span data-ttu-id="e52bc-150">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="e52bc-150">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="e52bc-151">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="e52bc-151">ISAPI Filters</span></span>

  - <span data-ttu-id="e52bc-152">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="e52bc-152">HTTP Logging</span></span>

  - <span data-ttu-id="e52bc-153">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="e52bc-153">Logging Tools</span></span>

  - <span data-ttu-id="e52bc-154">Tracing</span><span class="sxs-lookup"><span data-stu-id="e52bc-154">Tracing</span></span>

  - <span data-ttu-id="e52bc-155">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e52bc-155">Windows Authentication</span></span>

  - <span data-ttu-id="e52bc-156">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="e52bc-156">Request Filtering</span></span>

  - <span data-ttu-id="e52bc-157">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="e52bc-157">Static Content Compression</span></span>

  - <span data-ttu-id="e52bc-158">Komprimierung dynamischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="e52bc-158">Dynamic Content Compression</span></span>

  - <span data-ttu-id="e52bc-159">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="e52bc-159">IIS Management Console</span></span>

  - <span data-ttu-id="e52bc-160">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="e52bc-160">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="e52bc-161">Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert.)</span><span class="sxs-lookup"><span data-stu-id="e52bc-161">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="e52bc-162">Authentifizierung der Client Zertifikatzuordnung</span><span class="sxs-lookup"><span data-stu-id="e52bc-162">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="e52bc-163">Windows Media Format Laufzeit und Windows-Desktop Erfahrung</span><span class="sxs-lookup"><span data-stu-id="e52bc-163">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="e52bc-164">**Windows-Desktop Umgebung** Auf allen Front-End-Servern und Standard Edition-Servern, auf denen Konferenzen bereitgestellt werden, muss die Windows Media Format Runtime installiert sein, die mit Ausnahme von Windows Server 2012 als Teil der Windows-Desktopumgebung installiert wird.</span><span class="sxs-lookup"><span data-stu-id="e52bc-164">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="e52bc-165">Für Windows Server 2012 ist Microsoft Media Foundation erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e52bc-165">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="e52bc-166">Die Windows Media Format-Laufzeitkomponente ist für die WMA-Dateien (Windows Media Audio) erforderlich, die in der Anwendung zum Parken von Anrufen, in der Ansageanwendung und in der Reaktionsgruppenanwendung für die Wiedergabe von Ansagen und Musik verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e52bc-166">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="e52bc-167">Es wird empfohlen, dass Sie Windows Desktop Experience installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="e52bc-167">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="e52bc-168">Wenn lync Server 2013 diese Software nicht auf dem Server findet, werden Sie aufgefordert, Sie zu installieren, und Sie müssen den Server neu starten, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="e52bc-168">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="e52bc-169">Zusätzliche Software für Front-End-Server und Standard Edition-Server mit Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e52bc-169">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="e52bc-170">Front-End-Server benötigen .NET 3,5, das in Windows Server 2012 nicht standardmäßig installiert ist.</span><span class="sxs-lookup"><span data-stu-id="e52bc-170">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="e52bc-171">Um Sie zu installieren, legen Sie die Windows Server 2012 Installationsmedien in Laufwerk D ab, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e52bc-171">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="e52bc-172">Ausführliche Informationen zur Installation von .NET 3,5 auf Servern mit Windows Server 2012 finden Sie unter "Überlegungen zur Microsoft .NET Framework 3.5-Bereitstellung" unter <https://go.microsoft.com/fwlink/p/?linkid=275032> .</span><span class="sxs-lookup"><span data-stu-id="e52bc-172">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="e52bc-173">Zusätzliche Software für Directors</span><span class="sxs-lookup"><span data-stu-id="e52bc-173">Additional Software for Directors</span></span>

<span data-ttu-id="e52bc-174">Directors müssen Internet Information Services (IIS) mit den folgenden Modulen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e52bc-174">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="e52bc-175">Statischer Inhalt</span><span class="sxs-lookup"><span data-stu-id="e52bc-175">Static Content</span></span>

  - <span data-ttu-id="e52bc-176">Standarddokument</span><span class="sxs-lookup"><span data-stu-id="e52bc-176">Default Document</span></span>

  - <span data-ttu-id="e52bc-177">HTTP-Fehler</span><span class="sxs-lookup"><span data-stu-id="e52bc-177">HTTP Errors</span></span>

  - <span data-ttu-id="e52bc-178">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="e52bc-178">ASP.NET</span></span>

  - <span data-ttu-id="e52bc-179">.NET-Erweiterbarkeit</span><span class="sxs-lookup"><span data-stu-id="e52bc-179">.NET Extensibility</span></span>

  - <span data-ttu-id="e52bc-180">ISAPI-Erweiterungen (Internet Server API)</span><span class="sxs-lookup"><span data-stu-id="e52bc-180">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="e52bc-181">ISAPI-Filter</span><span class="sxs-lookup"><span data-stu-id="e52bc-181">ISAPI Filters</span></span>

  - <span data-ttu-id="e52bc-182">HTTP-Protokollierung</span><span class="sxs-lookup"><span data-stu-id="e52bc-182">HTTP Logging</span></span>

  - <span data-ttu-id="e52bc-183">Protokollierungstools</span><span class="sxs-lookup"><span data-stu-id="e52bc-183">Logging Tools</span></span>

  - <span data-ttu-id="e52bc-184">Tracing</span><span class="sxs-lookup"><span data-stu-id="e52bc-184">Tracing</span></span>

  - <span data-ttu-id="e52bc-185">Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e52bc-185">Windows Authentication</span></span>

  - <span data-ttu-id="e52bc-186">Anforderungsfilterung</span><span class="sxs-lookup"><span data-stu-id="e52bc-186">Request Filtering</span></span>

  - <span data-ttu-id="e52bc-187">Komprimierung statischer Inhalte</span><span class="sxs-lookup"><span data-stu-id="e52bc-187">Static Content Compression</span></span>

  - <span data-ttu-id="e52bc-188">IIS-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="e52bc-188">IIS Management Console</span></span>

  - <span data-ttu-id="e52bc-189">IIS-Verwaltungsskripts und -tools</span><span class="sxs-lookup"><span data-stu-id="e52bc-189">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="e52bc-190">Anonyme Authentifizierung (wird bei der Installation von IIS standardmäßig installiert.)</span><span class="sxs-lookup"><span data-stu-id="e52bc-190">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="e52bc-191">Authentifizierung der Client Zertifikatzuordnung</span><span class="sxs-lookup"><span data-stu-id="e52bc-191">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="e52bc-192">Zusätzliche Software für Front-End-Server für beständigen Chat</span><span class="sxs-lookup"><span data-stu-id="e52bc-192">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="e52bc-193">Front-End-Server für beständigen Chat müssen Message Queuing (auch als MSMQ bezeichnet) ausführen, bei dem es sich um eine Komponente von Windows Server handelt.</span><span class="sxs-lookup"><span data-stu-id="e52bc-193">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="e52bc-194">Informationen zum Aktivieren von MSMQ finden [Sie hier.](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="e52bc-194">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="e52bc-195">Zusätzliche Software für Edge-Server</span><span class="sxs-lookup"><span data-stu-id="e52bc-195">Additional Software for Edge Servers</span></span>

<span data-ttu-id="e52bc-196">Für Edgeserver ist die folgende Software erforderlich:</span><span class="sxs-lookup"><span data-stu-id="e52bc-196">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="e52bc-197">Auf jedem Server mit lync Server 2013 muss die richtige Version von Windows PowerShell 3,0 installiert sein.</span><span class="sxs-lookup"><span data-stu-id="e52bc-197">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="e52bc-198">Ausführliche Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="e52bc-198">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="e52bc-199">Lync Server erfordert Microsoft .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="e52bc-199">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="e52bc-200">Für lync Server 2013, die auf Windows Server 2008 R2 installiert sind, müssen Sie die 64-Bit-Edition von Microsoft .NET Framework 4.5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="e52bc-200">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="e52bc-201">Um es manuell zu installieren, laden Sie das Microsoft .NET 4,5 Framework aus dem Microsoft Download Center unter [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="e52bc-201">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="e52bc-202">**WindowsIdentity Foundation** in lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e52bc-202">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="e52bc-203">Windows Server 2008 R2 und Windows Server 2012 erfordern unterschiedliche Verfahren zum Installieren der Windows Identify Foundation.</span><span class="sxs-lookup"><span data-stu-id="e52bc-203">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="e52bc-204">Wählen Sie Ihr Server Betriebssystem aus der folgenden Liste aus:</span><span class="sxs-lookup"><span data-stu-id="e52bc-204">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="e52bc-205">Windows Server 2008 R2 für Windows Server 2008 R2 überprüfen Sie, ob Sie bereits auf Ihrem Computer installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e52bc-205">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="e52bc-206">Wechseln Sie dazu zu **Software hinzufügen/entfernen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Windows** nach dem Eintrag **Windows Identity Foundation (KB974405)**.</span><span class="sxs-lookup"><span data-stu-id="e52bc-206">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="e52bc-207">Ausführliche Informationen zum Installieren von Windows Identity Foundation finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="e52bc-207">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="e52bc-208">Windows Server 2012 für Windows Server 2012 verwenden Sie den **Server-Manager** , um die Windows Identity Foundation zu installieren.</span><span class="sxs-lookup"><span data-stu-id="e52bc-208">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="e52bc-209">Wählen Sie im **Assistenten zum Hinzufügen von Rollen und Features**von Server-Manager die Option **Features**aus.</span><span class="sxs-lookup"><span data-stu-id="e52bc-209">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="e52bc-210">Wählen Sie **Windows Identity Foundation 3,5** aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="e52bc-210">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="e52bc-211">Klicken Sie auf **weiter**, und klicken Sie dann auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="e52bc-211">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="e52bc-212">Installieren von mehrschichtigen Socket-Anbietern auf Medienservern</span><span class="sxs-lookup"><span data-stu-id="e52bc-212">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="e52bc-213">Installieren Sie keine ISA (Microsoft Internet Security and Acceleration Server)-Client Software oder andere LSP-Software (Winsock Layered Service Providers) auf allen Front-End-Servern oder eigenständigen Vermittlungsservern.</span><span class="sxs-lookup"><span data-stu-id="e52bc-213">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="e52bc-214">Die Installation dieser Software kann zu einer schlechten Leistung des Datenverkehrs führen.</span><span class="sxs-lookup"><span data-stu-id="e52bc-214">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e52bc-215">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e52bc-215">See Also</span></span>


[<span data-ttu-id="e52bc-216">Softwareanforderungen für Verwaltungstools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e52bc-216">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

