---
title: Installieren von Betriebssystemen und erforderlicher Software auf Servern
description: Installieren von Betriebssystemen und erforderlicher Software auf Servern.
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
ms.openlocfilehash: 2bae9e57db9c2f1d3f3bde7ce9cc7071b73aa01d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574131"
---
# <a name="install-operating-systems-and-prerequisite-software-on-servers-for-lync-server-2013"></a><span data-ttu-id="43943-103">Installieren von Betriebssystemen und erforderlicher Software auf Servern für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="43943-103">Install operating systems and prerequisite software on servers for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43943-104">_**Letztes Änderungsstand des Themas:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="43943-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<span data-ttu-id="43943-105">Nachdem Sie die Hardware- und Systeminfrastruktur eingerichtet haben, müssen Sie die geeigneten Windows-Betriebssysteme und Updates sowie alle weiteren erforderlichen Softwarekomponenten auf sämtlichen Servern installieren, die Sie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="43943-105">After you have set up the hardware and system infrastructure, you need to install the appropriate Windows operating systems and updates, in addition to all other prerequisite software on each server that you are deploying.</span></span> <span data-ttu-id="43943-106">Dies umfasst jede lync Server 2013-Server Rolle sowie alle weiteren Infrastrukturserver oder Server, auf denen SQL Server für Ihre Bereitstellung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="43943-106">This includes each Lync Server 2013 server role and any additional infrastructure servers or servers running SQL Server that are required for your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="43943-107">Im vorliegenden Abschnitt wird die Installation der Betriebssysteme und der erforderlichen Softwarekomponenten für interne Server beschrieben.</span><span class="sxs-lookup"><span data-stu-id="43943-107">This section describes installation of operating systems and prerequisite software for internal servers.</span></span> <span data-ttu-id="43943-108">Wenn Sie Edgeserver bereitstellen, um den Zugriff durch externe Benutzer zu unterstützen, müssen Sie auch Betriebssysteme und die erforderliche Software für diese Server installieren, einschließlich Edgeserver und Reverse-Proxyservern.</span><span class="sxs-lookup"><span data-stu-id="43943-108">If you are deploying Edge Servers to support external user access, you also need to install operating systems and prerequisite software for those servers, including Edge Servers and reverse proxy servers.</span></span> <span data-ttu-id="43943-109">Ausführliche Informationen zum Vorbereiten von Servern zur Unterstützung des Zugriffs durch externe Benutzer finden Sie unter <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</A> in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="43943-109">For details about preparing servers to support external user access, see <A href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="install-windows-operating-systems-on-servers"></a><span data-ttu-id="43943-110">Installieren von Windows-Betriebssystemen auf Servern</span><span class="sxs-lookup"><span data-stu-id="43943-110">Install Windows Operating Systems on Servers</span></span>

<span data-ttu-id="43943-111">Installieren Sie auf jedem Server, den Sie bereitstellen, das entsprechende Windows-Betriebssystem wie folgt:</span><span class="sxs-lookup"><span data-stu-id="43943-111">On each server that you are deploying, install the appropriate Windows operating system as follows:</span></span>

  - <span data-ttu-id="43943-112">**Server mit lync Server 2013**     Ausführliche Informationen zu den Betriebssystemanforderungen für Server, auf denen lync Server 2013 ausführen, finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="43943-112">**Servers running Lync Server 2013**   For details about the operating system requirements for servers running Lync Server 2013, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

  - <span data-ttu-id="43943-113">**Datenbankserver**     Ausführliche Informationen zu den Betriebssystemanforderungen für Datenbankserver, einschließlich der Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank finden Sie in der SQL Server Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="43943-113">**Database servers**   For details about operating system requirements for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server documentation.</span></span> <span data-ttu-id="43943-114">Informationen zu SQL Server 2012 finden Sie in der SQL Server 2012-Online Dokumentation unter [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="43943-114">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="43943-115">Wenn Sie lync Server 2013 unter Windows Server &nbsp; 2008 &nbsp; R2 mit SP1 installieren, müssen Sie zuerst das Update installieren, das im Microsoft Knowledge-Artikel 2646886, "Update: Heap corruption" auftritt, wenn ein Modul die InsertEntityBody-Methode in IIS 7,5 aufruft, unter <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886"> https://go.microsoft.com/fwlink/p/?linkid=3052&amp ; kbid = 2646886</A>.</span><span class="sxs-lookup"><span data-stu-id="43943-115">If you are installing Lync Server 2013 on Windows Server&nbsp;2008&nbsp;R2 with SP1, you must first install the update described in the Microsoft Knowledge Based article 2646886, “FIX: Heap corruption occurs when a module calls the InsertEntityBody method in IIS 7.5”, at <A class=uri href="https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=2646886">https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2646886</A>.</span></span><BR><span data-ttu-id="43943-116">Sie müssen auch die Registrierung wie im KB-Artikel, Ereignis- <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">IDs 32402, 61045, in lync Server 2013 auf Windows Server 2012 R2 installierten Front-End-Servern angemeldet sind</A>, ändern.</span><span class="sxs-lookup"><span data-stu-id="43943-116">You must also modify the registry as described in the KB article, <A href="https://go.microsoft.com/fwlink/p/?linkid=506893">Event IDs 32402, 61045 are logged in Lync Server 2013 Front End servers that are installed in Windows Server 2012 R2</A>.</span></span>



</div>

</div>

<div>

## <a name="install-windows-update-on-servers"></a><span data-ttu-id="43943-117">Installieren von Windows-Updates auf Servern</span><span class="sxs-lookup"><span data-stu-id="43943-117">Install Windows Update on Servers</span></span>

<span data-ttu-id="43943-118">Installieren Sie die folgenden Updates von Windows Update auf jedem Server:</span><span class="sxs-lookup"><span data-stu-id="43943-118">Install the following updates from Windows Update on each server:</span></span>

  - <span data-ttu-id="43943-119">**Windows Update für Server mit lync Server 2013**     Ausführliche Informationen zu den Updates von Windows Update, die für Server mit lync Server 2013 erforderlich sind, finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="43943-119">**Windows Update for servers running Lync Server 2013**   For details about the updates from Windows Update that are required for servers running Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="43943-120">**Datenbankserver**     Ausführliche Informationen zu den Updates von Windows Update, die für Datenbankserver erforderlich sind, einschließlich der Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank, finden Sie in der Dokumentation zu SQL Server 2012.</span><span class="sxs-lookup"><span data-stu-id="43943-120">**Database servers**   For details about the updates from Windows Update that are required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation.</span></span> <span data-ttu-id="43943-121">Informationen zu SQL Server 2012 finden Sie in der SQL Server 2012-Online Dokumentation unter [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="43943-121">For SQL Server 2012, see the SQL Server 2012 Books Online at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>

</div>

<div>

## <a name="install-other-prerequisite-software-on-servers"></a><span data-ttu-id="43943-122">Installieren zusätzlich erforderlicher Softwarekomponenten auf Servern</span><span class="sxs-lookup"><span data-stu-id="43943-122">Install Other Prerequisite Software on Servers</span></span>

<span data-ttu-id="43943-123">Lync Server 2013 erfordert die Installation der folgenden zusätzlichen Software auf Servern:</span><span class="sxs-lookup"><span data-stu-id="43943-123">Lync Server 2013 requires the installation of the following additional software on servers:</span></span>

  - <span data-ttu-id="43943-124">**Erforderliche Software für Server mit lync Server 2013**     Die zusätzlichen Softwarevoraussetzungen für Server, auf denen lync Server 2013 ausführt, hängen von der bereitzustellenden Serverrolle ab.</span><span class="sxs-lookup"><span data-stu-id="43943-124">**Prerequisite software for servers running Lync Server 2013**   The additional software prerequisites for servers running Lync Server 2013 depend on the server role being deployed.</span></span> <span data-ttu-id="43943-125">Ausführliche Informationen zu den spezifischen Softwareanforderungen für die einzelnen Server finden Sie in der Planungsdokumentation unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) .</span><span class="sxs-lookup"><span data-stu-id="43943-125">For details about the specific software requirements for each server, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="43943-126">**Windows Identity Foundation**     Lync Server 2013 erfordert die Installation von Windows Identity Foundation, um Server-zu-Server-Authentifizierungsszenarien zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="43943-126">**Windows Identity Foundation**   Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server-to-server authentication scenarios.</span></span> <span data-ttu-id="43943-127">Um zu überprüfen, ob Sie bereits auf Ihrem Computer installiert wurde, wechseln Sie zur Systemsteuerung, klicken Sie auf **Programme und Funktionen**, **zeigen Sie installierte Updates**an, und schauen Sie unter **Microsoft Windows**nach.</span><span class="sxs-lookup"><span data-stu-id="43943-127">To verify that it has already been installed on your computer, go to Control Panel, click **Programs and Features**, **View installed updates**, and look under **Microsoft Windows**.</span></span> <span data-ttu-id="43943-128">Ausführliche Informationen zum Installieren von Windows Identity Foundation finden Sie unter [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) .</span><span class="sxs-lookup"><span data-stu-id="43943-128">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="43943-129">**Microsoft .NET Framework 4.5**     Die 64-Bit-Edition von Microsoft .NET Framework 4.5 ist für lync Server 2013 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="43943-129">**Microsoft .NET Framework 4.5**   The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

  - <span data-ttu-id="43943-130">**Erforderliche Software für Datenbankserver**     Ausführliche Informationen zu den Windows-Updates, die für Datenbankserver erforderlich sind, einschließlich der Back-End-Datenbank, Archivierungsdatenbank und Überwachungsdatenbank finden Sie in der Dokumentation zu SQL Server 2012 unter [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015) .</span><span class="sxs-lookup"><span data-stu-id="43943-130">**Prerequisite software for database servers**   For details about the Windows Update required for database servers, including the back-end database, Archiving database, and Monitoring database, see the SQL Server 2012 documentation at [https://go.microsoft.com/fwlink/p/?linkId=218015](https://go.microsoft.com/fwlink/p/?linkid=218015).</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="43943-131">Lync Server 2013 wird Microsoft SQL Server 2012 Express automatisch auf jedem Standard Edition-Server und auf jedem Server mit lync Server 2013 installiert, auf dem sich der lokale Konfigurationsspeicher befindet.</span><span class="sxs-lookup"><span data-stu-id="43943-131">Lync Server 2013 automatically installs Microsoft SQL Server 2012 Express on each Standard Edition server and each server running Lync Server 2013 on which the local configuration store is located.</span></span>

    
    </div>

  - <span data-ttu-id="43943-132">**Windows Media Format Laufzeit**     Auf allen Front-End-Servern und Standard Edition-Servern, auf denen Konferenzen bereitgestellt werden, muss die Windows Media Format Runtime installiert sein.</span><span class="sxs-lookup"><span data-stu-id="43943-132">**Windows Media Format Runtime**   All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed.</span></span> <span data-ttu-id="43943-133">Die Windows Media Format-Laufzeitkomponente ist für die WMA-Dateien (Windows Media Audio) erforderlich, die in der Anwendung zum Parken von Anrufen, in der Ansageanwendung und in der Reaktionsgruppenanwendung für die Wiedergabe von Ansagen und Musik verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43943-133">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="43943-134">Für Windows Server 2012 und Windows Server 2012 R2 wird die Windows Media Format Runtime mit Microsoft Media Foundation installiert.</span><span class="sxs-lookup"><span data-stu-id="43943-134">For Windows Server 2012 and Windows Server 2012 R2 the Windows Media Format Runtime installs with Microsoft Media Foundation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="43943-135">Für Windows Server &nbsp; 2008 und Windows Server &nbsp; 2008 &nbsp; R2 wird die Windows Media Format Runtime als Teil der Windows-Desktop Umgebung installiert.</span><span class="sxs-lookup"><span data-stu-id="43943-135">For Windows Server&nbsp;2008 and Windows Server&nbsp;2008&nbsp;R2 the Windows Media Format Runtime installs as part of the Windows Desktop Experience.</span></span> <span data-ttu-id="43943-136">Es wird empfohlen, dass Sie Windows Desktop Experience installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="43943-136">It is recommended that you install Windows Desktop Experience before you install Lync Server 2013.</span></span> <span data-ttu-id="43943-137">Wenn lync Server 2013 diese Software nicht auf dem Server findet, werden Sie aufgefordert, Sie zu installieren, und Sie müssen den Server neu starten, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="43943-137">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

