---
title: 'Lync Server 2013: Vorbereiten und Installieren von Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for and installing Best Practices Analyzer
ms:assetid: 550613dd-dc08-482e-9980-a3fe187cd162
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591347(v=OCS.15)
ms:contentKeyID: 48184149
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f5992b45d8930bac880f66422d10ddbd4b94f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-and-installing-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="9b191-102">Vorbereiten und Installieren von Best Practices Analyzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b191-102">Preparing for and installing Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b191-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="9b191-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="9b191-104">Sie müssen als Mitglied der Gruppe Administratoren angemeldet sein, um die in diesem Thema beschriebenen Aufgaben ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="9b191-104">You must be logged on as a member of the Administrators group to perform the tasks that are described in this topic.</span></span>

<div>

## <a name="system-requirements-for-best-practices-analyzer-installation"></a><span data-ttu-id="9b191-105">System Anforderungen für die Installation von Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="9b191-105">System Requirements for Best Practices Analyzer Installation</span></span>

<span data-ttu-id="9b191-106">Damit Sie lync Server 2013, Best Practices Analyzer zum Durchsuchen Ihrer Umgebung ausführen können, muss auf dem Computer eine 64-Bit-Version eines der folgenden Betriebssysteme ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="9b191-106">To run Lync Server 2013, Best Practices Analyzer to scan your environment, the computer must be running a 64-bit edition of one of the following operating systems:</span></span>

  - <span data-ttu-id="9b191-107">Windows Server 2008 R2 mit Service Pack 1 (SP1) Standard Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-107">Windows Server 2008 R2 with Service Pack 1 (SP1) Standard operating system</span></span>

  - <span data-ttu-id="9b191-108">Windows Server 2008 R2 mit SP1 Enterprise-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-108">Windows Server 2008 R2 with SP1 Enterprise operating system</span></span>

  - <span data-ttu-id="9b191-109">Windows Server 2008 R2 mit SP1 Datacenter-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-109">Windows Server 2008 R2 with SP1 Datacenter operating system</span></span>

  - <span data-ttu-id="9b191-110">Windows Server 2012 Datacenter-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-110">Windows Server 2012 Datacenter operating system</span></span>

  - <span data-ttu-id="9b191-111">Windows Server 2012 Standard-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-111">Windows Server 2012 Standard operating system</span></span>

  - <span data-ttu-id="9b191-112">Windows Server 2012 Enterprise-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-112">Windows Server 2012 Enterprise operating system</span></span>

  - <span data-ttu-id="9b191-113">Windows Server 2012 R2 Datacenter-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-113">Windows Server 2012 R2 Datacenter operating system</span></span>

  - <span data-ttu-id="9b191-114">Windows Server 2012 R2 Standard-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-114">Windows Server 2012 R2 Standard operating system</span></span>

  - <span data-ttu-id="9b191-115">Windows Server 2012 R2 Enterprise-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-115">Windows Server 2012 R2 Enterprise operating system</span></span>

  - <span data-ttu-id="9b191-116">Windows 8-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-116">Windows 8 operating system</span></span>

  - <span data-ttu-id="9b191-117">Windows 7-Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="9b191-117">Windows 7 operating system</span></span>

<span data-ttu-id="9b191-118">Auf dem Computer muss außerdem Folgendes ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="9b191-118">The computer must also be running the following:</span></span>

  - <span data-ttu-id="9b191-119">Microsoft .NET Framework 4,5.</span><span class="sxs-lookup"><span data-stu-id="9b191-119">Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="9b191-120">Bei lync Server 2013 müssen Sie die 64-Bit-Version von Microsoft .NET Framework 4,5 auf dem Server manuell installieren, bevor Sie lync Server 2013 installieren.</span><span class="sxs-lookup"><span data-stu-id="9b191-120">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span>

  - <span data-ttu-id="9b191-121">Lync Server 2013, Core Components.</span><span class="sxs-lookup"><span data-stu-id="9b191-121">Lync Server 2013, Core Components.</span></span>

  - <span data-ttu-id="9b191-122">WMI-abwärts Kompatibilitätspaket.</span><span class="sxs-lookup"><span data-stu-id="9b191-122">WMI Backward Compatibility Package.</span></span> <span data-ttu-id="9b191-123">Ausführliche Informationen finden Sie unter [Installieren des WMI-abwärts Kompatibilitätspakets](install-wmi-backward-compatibility-package.md) in der Migrationsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9b191-123">For details, see [Install WMI Backward Compatibility package](install-wmi-backward-compatibility-package.md) in the Migration documentation.</span></span>

  - <span data-ttu-id="9b191-124">Windows PowerShell 3,0.</span><span class="sxs-lookup"><span data-stu-id="9b191-124">Windows PowerShell 3.0.</span></span> <span data-ttu-id="9b191-125">Ausführliche Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in der Bereitstellungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="9b191-125">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md) in the Deployment documentation.</span></span>

<span data-ttu-id="9b191-126">Sie können Best Practices Analyzer auf Computern mit einem unterstützten Betriebssystem installieren, das nicht lync Server 2013, Core Components oder WMI-abwärts Kompatibilitätspaket ausführt, aber Sie können Best Practices Analyzer auf diesen Computern nur zum Anzeigen von Berichten verwenden, nicht zum Ausführen von Scans.</span><span class="sxs-lookup"><span data-stu-id="9b191-126">You can install Best Practices Analyzer on computers with a supported operating system that are not running Lync Server 2013, Core Components or WMI Backward Compatibility Package, but you can use Best Practices Analyzer on those computers only to view reports, not to run scans.</span></span>

</div>

<div>

## <a name="choosing-a-computer-for-installation"></a><span data-ttu-id="9b191-127">Auswählen eines Computers für die Installation</span><span class="sxs-lookup"><span data-stu-id="9b191-127">Choosing a Computer for Installation</span></span>

<span data-ttu-id="9b191-128">Wir empfehlen, dass Sie lync Server 2013, Best Practices Analyzer auf einem Computer installieren, der für die Verwaltung von lync Server 2013 reserviert ist.</span><span class="sxs-lookup"><span data-stu-id="9b191-128">We recommend that you install Lync Server 2013, Best Practices Analyzer on a computer that is dedicated to Lync Server 2013 management.</span></span> <span data-ttu-id="9b191-129">Sie können das Tool auf einem Server mit lync Server 2013 oder einem Administratorcomputer installieren, auf dem lync Server 2013-Verwaltungstools ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9b191-129">You can install the tool on a server running Lync Server 2013 or an administrative computer running Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="9b191-130">Wenn Sie das Tool auf einem Server installieren, auf dem lync Server ausgeführt wird, empfehlen wir, dass Sie das Tool verwenden, um nur diesen Server zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9b191-130">If you install the tool on a server that is running Lync Server, we recommend that you use the tool to scan only that server.</span></span>

</div>

<div>

## <a name="installing-best-practices-analyzer"></a><span data-ttu-id="9b191-131">Installieren von Best Practices Analyzer</span><span class="sxs-lookup"><span data-stu-id="9b191-131">Installing Best Practices Analyzer</span></span>

<span data-ttu-id="9b191-132">Sie können das Best Practices Analyzer für lync Server 2013 unter [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539)herunterladen.</span><span class="sxs-lookup"><span data-stu-id="9b191-132">You can download the Best Practices Analyzer for Lync Server 2013 at [http://go.microsoft.com/fwlink/p/?linkId=266539](http://go.microsoft.com/fwlink/p/?linkid=266539).</span></span>

<span data-ttu-id="9b191-133">Wenn Sie Best Practices Analyzer installieren möchten, starten Sie die Microsoft Installer-Datei RtcBPA. msi auf dem Computer, auf dem Sie das Tool installieren möchten, und folgen Sie dann den Anweisungen auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="9b191-133">To install Best Practices Analyzer, start the Microsoft Installer file RtcBPA.msi on the computer where you want to install the tool, and then follow the instructions on the screen.</span></span> <span data-ttu-id="9b191-134">Der Standardspeicherort für die Installation der Programmdateien \<ist System\>\\Drive-\\Programmdateien lync\\Server 2013 BPA.</span><span class="sxs-lookup"><span data-stu-id="9b191-134">The default location for installing the program files is \<system drive\>\\Program Files\\Lync Server 2013\\BPA.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

