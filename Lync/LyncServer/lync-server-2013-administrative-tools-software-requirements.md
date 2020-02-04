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
ms.openlocfilehash: 1a3f174b4f699add911149128e3d7d48aa00e1c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administrative-tools-software-requirements-in-lync-server-2013"></a><span data-ttu-id="0a7cb-102">Softwareanforderungen für Verwaltungstools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7cb-102">Administrative tools software requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a7cb-103">_**Letztes Änderungsdatum des Themas:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="0a7cb-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="0a7cb-104">In diesem Thema wird die Software beschrieben, die für die Installation und Verwendung von lync Server 2013-Verwaltungstools zusätzlich zu den Betriebssystemanforderungen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-104">This topic describes the software required to install and use Lync Server 2013 administrative tools in addition to the operating system requirements.</span></span>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="0a7cb-105">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="0a7cb-105">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="0a7cb-106">Die 64-Bit-Version von Microsoft .NET Framework 4,5 ist für lync Server 2013 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-106">The 64-bit edition of Microsoft .NET Framework 4.5 is required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="0a7cb-107">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="0a7cb-107">Windows PowerShell 3.0</span></span>

<span data-ttu-id="0a7cb-108">Windows PowerShell 3,0 ist für die Ausführung einer beliebigen Komponente von Microsoft lync Server 2013 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-108">Windows PowerShell 3.0 is required for running any component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="0a7cb-109">Weitere Informationen finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="0a7cb-109">For more information, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="windows-installer-version-45"></a><span data-ttu-id="0a7cb-110">Windows Installer, Version 4,5</span><span class="sxs-lookup"><span data-stu-id="0a7cb-110">Windows Installer Version 4.5</span></span>

<span data-ttu-id="0a7cb-111">Lync Server 2013 verwendet die Windows Installer-Technologie, um verschiedene Server Rollen zu installieren, zu deinstallieren und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-111">Lync Server 2013 uses Windows Installer technology to install, uninstall, and maintain various server roles.</span></span> <span data-ttu-id="0a7cb-112">Windows Installer, Version 4,5, steht als verteilbare Komponente für das Windows Server-Betriebssystem zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-112">Windows Installer version 4.5 is available as a redistributable component for the Windows Server operating system.</span></span> <span data-ttu-id="0a7cb-113">Windows Installer 4,5 wird mit Windows Server 2012 R2, Windows Server 2012 und Windows Server 2008 R2 ausgeliefert, was bedeutet, dass Sie das Dienstprogramm nicht für einen Computer herunterladen müssen, auf dem lync Server 2013 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-113">Windows Installer 4.5 ships with Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 meaning that you do not need to download the utility for any computer that is running Lync Server 2013.</span></span> <span data-ttu-id="0a7cb-114">(Lync Server 2013 kann nur auf Computern mit Windows Server 2012 R2, Windows Server 2012 oder Windows Server 2008 R2 installiert werden.)</span><span class="sxs-lookup"><span data-stu-id="0a7cb-114">(Lync Server 2013 can only be installed on computers running Windows Server 2012 R2, Windows Server 2012 or Windows Server 2008 R2.)</span></span>

<span data-ttu-id="0a7cb-115">Wenn Sie jedoch die lync Server-Verwaltungsshell oder den lync Server Topology Builder auf einer Administratorarbeitsstation installieren möchten, müssen Sie möglicherweise Windows Installer 4,5 herunterladen.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-115">However, if you want to install Lync Server Management Shell or Lync Server Topology Builder on an administrator workstation you might need to download Windows Installer 4.5.</span></span> <span data-ttu-id="0a7cb-116">Dieses Dienstprogramm wird mit Windows 7 und Windows 2008 R2 ausgeliefert, jedoch nicht mit früheren Versionen des Windows-Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-116">That utility ships with Windows 7 and Windows 2008 R2 but not with any previous versions of the Windows operating system.</span></span> <span data-ttu-id="0a7cb-117">Sie können Windows Installer 4,5 aus dem Microsoft Download Center herunterladen <http://go.microsoft.com/fwlink/p/?linkid=197395>.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-117">You can download Windows Installer 4.5 from the Microsoft Download Center at <http://go.microsoft.com/fwlink/p/?linkid=197395>.</span></span>

</div>

<div>

## <a name="microsoft-silverlight-5-browser-plug-in"></a><span data-ttu-id="0a7cb-118">Microsoft Silverlight 5-Browser-Plug-in</span><span class="sxs-lookup"><span data-stu-id="0a7cb-118">Microsoft Silverlight 5 browser plug-in</span></span>

<span data-ttu-id="0a7cb-119">Die lync Server 2013-Systemsteuerung ist ein webbasiertes Tool und erfordert, dass Sie die neueste Version des Microsoft Silverlight 5-Browser-Plug-ins installieren.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-119">Lync Server 2013 Control Panel is a web-based tool and requires that you install the latest version of Microsoft Silverlight 5 browser plug-in.</span></span> <span data-ttu-id="0a7cb-120">Wenn Sie die lync Server 2013-Systemsteuerung starten, wenn diese Software nicht installiert ist oder wenn eine frühere Version installiert ist, werden Sie in der Systemsteuerung von lync Server 2013 aufgefordert, die erforderliche Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0a7cb-120">When you start Lync Server 2013 Control Panel, if this software is not installed or if an earlier version is installed, Lync Server 2013 Control Panel prompts you to install the required version.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a7cb-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a7cb-121">See Also</span></span>


[<span data-ttu-id="0a7cb-122">Betriebssystemunterstützung für Server und Tools in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7cb-122">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="0a7cb-123">Infrastrukturanforderungen für Verwaltungstools in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7cb-123">Administrative tools infrastructure requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-infrastructure-requirements.md)  
[<span data-ttu-id="0a7cb-124">Erforderliche Administratorrechte und Gruppenmitgliedschaften für die Installation und Verwaltung von Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a7cb-124">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

