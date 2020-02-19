---
title: Installieren von Betriebssystemen und erforderlicher Software auf Servern
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install operating systems and prerequisite software on servers
ms:assetid: 055991e0-5aeb-43fc-a7ba-d4b02316d73b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398103(v=OCS.15)
ms:contentKeyID: 48183288
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69ad97d578073e2b0f9ed08d929007c33e59b8fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="05469-102">Installieren von Betriebssystemen und erforderlicher Software auf Servern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05469-102">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05469-103">_**Letztes Änderungsstand des Themas:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="05469-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="05469-104">Nachdem Sie die Hardware- und Systeminfrastruktur eingerichtet haben, müssen Sie die geeigneten Windows-Betriebssysteme und Updates sowie alle weiteren erforderlichen Softwarekomponenten auf sämtlichen Servern installieren, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="05469-104">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="05469-105">Dies umfasst jede lync Server 2013-Server Rolle sowie alle weiteren Infrastrukturserver oder Server, auf denen SQL Server für Ihre Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="05469-105">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="05469-106">Im vorliegenden Abschnitt wird die Installation der Betriebssysteme und der erforderlichen Softwarekomponenten für interne Server beschrieben.</span><span class="sxs-lookup"><span data-stu-id="05469-106">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="05469-107">Wenn Sie Edgeserver bereitstellen, um den Zugriff durch externe Benutzer zu unterstützen, müssen Sie auch Betriebssysteme und die erforderliche Software für diese Server installieren, einschließlich Edgeserver und Reverse-Proxyservern.</span><span class="sxs-lookup"><span data-stu-id="05469-107">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="05469-108">Ausführliche Informationen zum Vorbereiten von Servern zur Unterstützung des Zugriffs durch externe Benutzer finden Sie unter <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="05469-108">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="05469-109">Installieren von Windows-Betriebssystemen auf Servern</span><span class="sxs-lookup"><span data-stu-id="05469-109">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="05469-110">Installieren Sie auf jedem Server, den Sie bereitstellen, das entsprechende Windows-Betriebssystem wie folgt:</span><span class="sxs-lookup"><span data-stu-id="05469-110">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="05469-111">**Server mit lync Server 2013**   ausführliche Informationen zu den Betriebssystemanforderungen für Server mit lync Server 2013 finden Sie in der Unterstützungsdokumentation unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) .</span><span class="sxs-lookup"><span data-stu-id="05469-111">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="05469-112">**Datenbankserver**   ausführliche Informationen zu den Betriebssystemanforderungen für Datenbankserver, einschließlich der Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank finden Sie in der SQL Server Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="05469-112">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="05469-113">Informationen zu SQL Server 2012 finden Sie in [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)der SQL Server 2012-Online Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="05469-113">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="05469-114">Wenn Sie lync Server 2013 unter Windows Server&nbsp;2008&nbsp;R2 mit SP1 installieren, müssen Sie zuerst das Update installieren, das im Microsoft Knowledge-Artikel 2646886, "Update: Heap corruption" auftritt, wenn ein Modul die InsertEntityBody-Methode in IIS 7,5 aufruft, unter <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="05469-114">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="05469-115">Sie müssen auch die Registrierung wie im KB-Artikel, Ereignis- <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">IDs 32402, 61045, in lync Server 2013 auf Windows Server 2012 R2 installierten Front-End-Servern angemeldet sind</A>, ändern.</span><span class="sxs-lookup"><span data-stu-id="05469-115">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="05469-116">Installieren von Windows-Updates auf Servern</span><span class="sxs-lookup"><span data-stu-id="05469-116">Install Windows Update on Servers</span></span>

<span data-ttu-id="05469-117">Installieren Sie die folgenden Updates von Windows Update auf jedem Server:</span><span class="sxs-lookup"><span data-stu-id="05469-117">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="05469-118">**Windows Update für Server mit lync Server 2013**   ausführliche Informationen zu den Updates von Windows Update, die für Server mit lync Server 2013 erforderlich sind, finden Sie unter [Additional Software Requirements for lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="05469-118">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="05469-119">**Datenbankserver**   ausführliche Informationen zu den Updates, die für Datenbankserver erforderlich sind, einschließlich der Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank finden Sie in der Dokumentation zu SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="05469-119">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="05469-120">Informationen zu SQL Server 2012 finden Sie in [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)der SQL Server 2012-Online Dokumentation unter.</span><span class="sxs-lookup"><span data-stu-id="05469-120">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="05469-121">Installieren zusätzlich erforderlicher Softwarekomponenten auf Servern</span><span class="sxs-lookup"><span data-stu-id="05469-121">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="05469-122">Lync Server 2013 erfordert die Installation der folgenden zusätzlichen Software auf Servern:</span><span class="sxs-lookup"><span data-stu-id="05469-122">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="05469-123">**Die erforderliche Software für Server, auf denen lync Server 2013**   die zusätzlichen Softwarevoraussetzungen für Server mit lync Server 2013 basieren, hängen von der bereitzustellenden Serverrolle ab.</span><span class="sxs-lookup"><span data-stu-id="05469-123">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="05469-124">Ausführliche Informationen zu den spezifischen Softwareanforderungen für die einzelnen Server finden Sie in der Planungsdokumentation unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) .</span><span class="sxs-lookup"><span data-stu-id="05469-124">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="05469-125">**WindowsIdentity Foundation**   lync Server 2013 erfordert die Installation von WindowsIdentity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="05469-125">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="05469-126">Um zu überprüfen, ob Sie bereits auf Ihrem Computer installiert wurde, wechseln Sie zur Systemsteuerung, klicken Sie auf **Programme und Funktionen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Microsoft Windows**nach.</span><span class="sxs-lookup"><span data-stu-id="05469-126">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="05469-127">Ausführliche Informationen zum Installieren von Windows Identity Foundation finden [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)Sie unter.</span><span class="sxs-lookup"><span data-stu-id="05469-127">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="05469-128">**Microsoft .NET Framework 4.5**   die 64-Bit-Version von Microsoft .NET Framework 4.5 ist für lync Server 2013 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="05469-128">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="05469-129">**Erforderliche Software für Datenbankserver**   ausführliche Informationen zu den für Datenbankserver erforderlichen Windows-Updates, einschließlich der Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank finden Sie in der [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015)Dokumentation zu SQL Server 2012 unter.</span><span class="sxs-lookup"><span data-stu-id="05469-129">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="05469-130">Lync Server 2013 wird Microsoft SQL Server 2012 Express automatisch auf jedem Standard Edition-Server und auf jedem Server mit lync Server 2013 installiert, auf dem sich der lokale Konfigurationsspeicher befindet.</span><span class="sxs-lookup"><span data-stu-id="05469-130">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="05469-131">**Windows Media Format Laufzeit**   für alle Front-End-Server und Standard Edition-Server, auf denen Konferenzen bereitgestellt werden, muss die Windows Media Format Runtime installiert sein.</span><span class="sxs-lookup"><span data-stu-id="05469-131">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="05469-132">Die Windows Media Format-Laufzeitkomponente ist für die WMA-Dateien (Windows Media Audio) erforderlich, die in der Anwendung zum Parken von Anrufen, in der Ansageanwendung und in der Reaktionsgruppenanwendung für die Wiedergabe von Ansagen und Musik verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05469-132">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="05469-133">Für Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format Runtime mit Microsoft Media Foundation installiert.</span><span class="sxs-lookup"><span data-stu-id="05469-133">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="05469-134">Für Windows Server&nbsp;2008 und Windows Server&nbsp;2008&nbsp;R2 wird die Windows Media Format Runtime als Teil der Windows-Desktop Umgebung installiert.</span><span class="sxs-lookup"><span data-stu-id="05469-134">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="05469-135">Es wird empfohlen, dass Sie Windows Desktop Experience installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="05469-135">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="05469-136">Wenn lync Server 2013 diese Software nicht auf dem Server findet, werden Sie aufgefordert, Sie zu installieren, und Sie müssen den Server neu starten, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="05469-136">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

