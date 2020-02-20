---
title: 'Lync Server 2013: Softwareanforderungen für Verwaltungstools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administrative tools software requirements
ms:assetid: 2fb172c3-7b84-4e49-981c-2a17e7a00a29
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195653(v=OCS.15)
ms:contentKeyID: 48183740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8756545969f90cbece7bbac628577a51015e371
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="8c2d3-102">Softwareanforderungen für Verwaltungstools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2d3-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c2d3-103">_**Letztes Änderungsstand des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="8c2d3-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="8c2d3-104">In diesem Thema wird die Software beschrieben, die zum Installieren und Verwenden von lync Server 2013 Verwaltungstools zusätzlich zu den Betriebssystemanforderungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="8c2d3-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="8c2d3-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="8c2d3-106">Die 64-Bit-Edition von Microsoft .NET Framework 4.5 ist für lync Server 2013 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="8c2d3-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="8c2d3-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="8c2d3-108">Windows PowerShell 3,0 ist für die Ausführung einer beliebigen Komponente von Microsoft lync Server 2013 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="8c2d3-109">Weitere Informationen finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="8c2d3-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="8c2d3-110">Windows Installer, Version 4.5</span><span class="sxs-lookup"><span data-stu-id="8c2d3-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="8c2d3-111">Lync Server 2013 verwendet Windows Installer-Technologie, um verschiedene Server Rollen zu installieren, zu deinstallieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="8c2d3-112">Windows Installer, Version 4.5, ist als weitervertreibbare Komponente für das Windows Server-Betriebssystem verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="8c2d3-113">Windows Installer 4,5 ist mit Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2en ausgeliefert, was bedeutet, dass Sie das Dienstprogramm nicht für einen Computer herunterladen müssen, auf dem lync Server 2013 läuft.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="8c2d3-114">(Lync Server 2013 kann nur auf Computern mit Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 installiert werden.)</span><span class="sxs-lookup"><span data-stu-id="8c2d3-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="8c2d3-115">Wenn Sie jedoch lync Server-Verwaltungsshell oder lync Server Topologie-Generator auf einer Administratorarbeitsstation installieren möchten, müssen Sie möglicherweise Windows Installer 4,5 herunterladen.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="8c2d3-116">Dieses Dienstprogramm wird mit Windows 7 und Windows 2008 R2 ausgeliefert, jedoch nicht mit früheren Versionen des Windows-Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="8c2d3-117">Sie können Windows Installer 4,5 aus dem Microsoft Download Center herunterladen <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <https://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="8c2d3-118">Microsoft Silverlight 5 Browser-Plug-in</span><span class="sxs-lookup"><span data-stu-id="8c2d3-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="8c2d3-119">Lync Server 2013-Systemsteuerung ist ein webbasiertes Tool und erfordert, dass Sie die neueste Version von Microsoft Silverlight 5 Browser-Plug-in installieren.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="8c2d3-120">Wenn Sie lync Server 2013 Systemsteuerung starten, wenn diese Software nicht installiert ist oder wenn eine frühere Version installiert ist, werden Sie von lync Server 2013 Systemsteuerung aufgefordert, die erforderliche Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="8c2d3-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c2d3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c2d3-121">See Also</span></span>


[<span data-ttu-id="8c2d3-122">Betriebssystemunterstützung für Server und Tools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2d3-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="8c2d3-123">Infrastrukturanforderungen für Verwaltungstools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c2d3-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="8c2d3-124">Für die Einrichtung und Verwaltung von lync Server 2013 erforderliche Administrator Rechte und-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8c2d3-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

