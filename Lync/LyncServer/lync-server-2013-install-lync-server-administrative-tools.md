---
title: 'Lync Server 2013: Installieren von Lync Server-Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server administrative tools
ms:assetid: 842b85e4-2eeb-464f-b1c1-ceb8cc04f8d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398665(v=OCS.15)
ms:contentKeyID: 48184695
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1115d5848806f95d35a158f36b7689967cec5d4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-lync-server-2013-administrative-tools"></a><span data-ttu-id="f2ff6-102">Installieren von Lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="f2ff6-102">Install Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2ff6-103">_**Letztes Änderungsdatum des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f2ff6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f2ff6-104">In diesem Thema wird beschrieben, wie Sie die Verwaltungstools installieren, die Sie zum Bereitstellen und Verwalten von lync Server 2013 verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-104">This topic describes how to install the administrative tools you need to use to deploy and manage Lync Server 2013.</span></span> <span data-ttu-id="f2ff6-105">Die Verwaltungstools werden standardmäßig auf jedem Server installiert, auf dem lync Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-105">The administrative tools are installed by default on each server running Lync Server 2013.</span></span> <span data-ttu-id="f2ff6-106">Darüber hinaus können Sie die Verwaltungstools auf anderen Computern installieren, beispielsweise in dedizierten Verwaltungskonsolen.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-106">Additionally, you can install the administrative tools on other computers, such as dedicated administrative consoles.</span></span> <span data-ttu-id="f2ff6-107">Wir empfehlen dringend, dass Sie die Verwaltungstools auf einem Computer installieren, der sich in der gleichen Domäne oder Gesamtstruktur wie die von Ihnen erstellte lync Server 2013-Bereitstellung befindet, weil Sie dadurch sicherstellen, dass die Schritte zur Vorbereitung der Active Directory-Domänendienste bereits ausgeführt werden. Complete, mit dem Sie die Verwaltungstools auf diesem Computer später zum Veröffentlichen Ihrer Topologie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-107">We strongly recommend that you install the administrative tools on a computer that is in the same domain or forest as the Lync Server 2013 deployment you are creating because by doing so you make sure that Active Directory Domain Services preparation steps are already complete, which enables you to use the administrative tools on that computer later to publish your topology.</span></span>

<span data-ttu-id="f2ff6-108">Stellen Sie sicher, dass Sie die Anforderungen für Infrastruktur, Betriebssystem, Software und Administratorrechte überprüfen, bevor Sie die lync Server 2013-Verwaltungstools installieren oder verwenden.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-108">Make sure that you review infrastructure, operating system, software, and administrator rights requirements before you install or use the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="f2ff6-109">Details zu den Infrastrukturanforderungen finden Sie unter [Infrastrukturanforderungen für Verwaltungstools in lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ff6-109">For details about infrastructure requirements, see [Administrative tools infrastructure requirements in Lync Server 2013](lync-server-2013-administrative-tools-infrastructure-requirements.md).</span></span> <span data-ttu-id="f2ff6-110">Ausführliche Informationen zu den Anforderungen des Betriebssystems und der Software zum Installieren der lync Server 2013-Verwaltungstools finden Sie unter [Unterstützung des Betriebssystems Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md)und [Zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="f2ff6-110">For details about operating system and software requirements to install the Lync Server 2013 administrative tools, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md), [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md), and [Additional server support and requirements in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).</span></span> <span data-ttu-id="f2ff6-111">Details zu den Benutzerrechten und Berechtigungen, die für die Installation und Verwendung der Tools erforderlich sind, finden Sie unter [Administrator Rechte und Berechtigungen, die für die Einrichtung und Verwaltung von lync Server 2013 erforderlich](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)sind.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-111">For details about the user rights and permissions required to install and use the tools, see [Administrator rights and permissions required for setup and administration of Lync Server 2013](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2ff6-112">Wenn Ihre Organisation erfordert, dass Sie Internet Informationsdienste (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk finden, können Sie den Pfad für den Installationspfad für die lync Server-Dateien im Dialogfeld einrichten ändern.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-112">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="f2ff6-113">Wenn Sie die Setup Dateien in diesem Pfad, einschließlich OCSCore. msi, installieren, werden die restlichen lync Server 2013-Dateien ebenfalls auf diesem Laufwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-113">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span>



</div>

<div>

## <a name="to-install-the-lync-server-2013-administrative-tools"></a><span data-ttu-id="f2ff6-114">So installieren Sie die lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="f2ff6-114">To install the Lync Server 2013 administrative tools</span></span>

1.  <span data-ttu-id="f2ff6-115">Melden Sie sich als lokaler Administrator (Mindestanforderung) an dem Computer an, auf dem Sie die Verwaltungstools installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-115">Log on as a local administrator (minimum requirement) to the computer where you want to install the administrative tools.</span></span> <span data-ttu-id="f2ff6-116">Wenn Sie als ein Standardbenutzer unter den Betriebssystemen Windows Vista oder Windows 7 angemeldet sind und die Benutzerkontensteuerung (User Account Control, UAC) aktiviert ist, werden Sie aufgefordert, den lokalen Administrator oder einen Domänen äquivalenten Benutzernamen und das Kennwort einzugeben.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-116">If you are logged on as an a standard user on the Windows Vista or Windows 7 operating systems, and User Account Control (UAC) is enabled, you will be prompted for the local administrator or a domain equivalent user name and password.</span></span>

2.  <span data-ttu-id="f2ff6-117">Suchen Sie das Installationsmedium auf dem Computer, und doppelklicken Sie \\dann\\auf\\Setup amd64 Setup. exe.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-117">Locate the installation media on your computer, and then double-click \\Setup\\amd64\\Setup.exe.</span></span>

3.  <span data-ttu-id="f2ff6-118">Wenn Sie aufgefordert werden, die Microsoft Visual C++ 2008-Distribution zu installieren, klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-118">If you are prompted to install the Microsoft Visual C++ 2008 distributable, click **Yes**.</span></span>

4.  <span data-ttu-id="f2ff6-119">Klicken Sie auf der Seite **Microsoft lync Server 2013-Installationsspeicherort** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-119">On the **Microsoft Lync Server 2013 Installation Location** page, click **OK**.</span></span> <span data-ttu-id="f2ff6-120">Ändern Sie diesen Pfad zu einem anderen Speicherort oder Laufwerk, wenn die Dateien an einem anderen Speicherort installiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-120">Change this path to another location or drive if you need to have the files installed to another location.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f2ff6-121">Wenn Ihre Organisation erfordert, dass Sie Internet Informationsdienste (IIS) und alle Webdienste auf einem anderen Laufwerk als dem Systemlaufwerk finden, können Sie den Pfad für den Installationspfad für die lync Server 2013-Dateien im Dialogfeld einrichten ändern.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-121">If your organization requires that you locate Internet Information Services (IIS) and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box.</span></span> <span data-ttu-id="f2ff6-122">Wenn Sie die Setup Dateien in diesem Pfad installieren, einschließlich OCSCore. msi, werden auch die restlichen lync Server 2013-Dateien auf diesem Laufwerk bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive too.</span></span>

    
    </div>

5.  <span data-ttu-id="f2ff6-123">Überprüfen Sie auf der Seite Endbenutzer- **Lizenzvertrag** die Lizenzbedingungen, klicken Sie auf **Ich akzeptiere**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-123">On the **End User License Agreement** page, review the license terms, click **I accept**, and then click **OK**.</span></span> <span data-ttu-id="f2ff6-124">Dieser Schritt ist erforderlich, bevor Sie fortfahren können.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-124">This step is required before you can continue.</span></span>

6.  <span data-ttu-id="f2ff6-125">Klicken Sie auf der Seite **Microsoft lync Server 2013 – Deployment-Assistent** auf **Administrator Tools installieren**.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-125">On the **Microsoft Lync Server 2013 – Deployment Wizard** page, click **Install Administrator Tools**.</span></span>

7.  <span data-ttu-id="f2ff6-126">Wenn die Installation erfolgreich abgeschlossen wurde, klicken Sie auf **Beenden**.</span><span class="sxs-lookup"><span data-stu-id="f2ff6-126">When the installation successfully completes, click **Exit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2ff6-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2ff6-127">See Also</span></span>


[<span data-ttu-id="f2ff6-128">Öffnen der lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="f2ff6-128">Open Lync Server 2013 administrative tools</span></span>](lync-server-2013-open-lync-server-administrative-tools.md)  


[<span data-ttu-id="f2ff6-129">Lync Server 2013-Verwaltungstools</span><span class="sxs-lookup"><span data-stu-id="f2ff6-129">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

