---
title: 'Lync Server 2013: System Anforderungen für Server mit lync Server 2013'
description: 'Lync Server 2013: System Anforderungen für Server mit lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b85940294e35a953d4ffb9c07bfdaba79141485
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562651"
---
# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="cee29-103">System Anforderungen für Server mit lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cee29-103">System requirements for servers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cee29-104">_**Letztes Änderungsstand des Themas:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="cee29-104">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cee29-105">Ausführliche Informationen zu den Hardwareanforderungen finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardware Platforms for lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cee29-105">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="cee29-106">Standard Edition-und Enterprise Edition-Server verwenden dieselben Softwareanforderungen.</span><span class="sxs-lookup"><span data-stu-id="cee29-106">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="cee29-107">Server, auf denen lync Server 2013 Enterprise Edition betrieben wird, sind für große Organisationen als Haupt Organisations Bereitstellung gedacht.</span><span class="sxs-lookup"><span data-stu-id="cee29-107">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="cee29-108">Enterprise Edition-Server sind auf ca. 80.000 verwaltete Benutzer pro Pool skalierbar.</span><span class="sxs-lookup"><span data-stu-id="cee29-108">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="cee29-109">Server mit lync Server 2013 Standard Edition sind für kleinere Organisationen und Remotestandorte von der Haupt Organisations Bereitstellung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="cee29-109">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="cee29-110">Ein paar von Standard Edition-Servern kann bis zu 5.000 Benutzer unterstützen..</span><span class="sxs-lookup"><span data-stu-id="cee29-110">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="cee29-111">Ausführliche Informationen zu den Unterschieden zwischen Standard Edition-Servern und Enterprise Edition-Servern finden Sie unter Übersicht über die [Bereitstellung für lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cee29-111">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="cee29-112">Betriebssysteminstallation</span><span class="sxs-lookup"><span data-stu-id="cee29-112">Operating System Installation</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="cee29-113">Lync Server 2013 ist nur in einer 64-Bit-Version verfügbar, die 64-Bit-Hardware und eine 64-Bit-Edition des Windows Server-Betriebssystems erfordert.</span><span class="sxs-lookup"><span data-stu-id="cee29-113">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="cee29-114">Eine 32-Bit-Version von lync Server 2013 steht in dieser Version nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cee29-114">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="cee29-115">Standard Edition und Enterprise Edition-Server können eine der folgenden Optionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="cee29-115">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="cee29-116">Windows Server 2008 R2 SP1 oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="cee29-116">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="cee29-117">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="cee29-117">Windows Server 2012</span></span>

  - <span data-ttu-id="cee29-118">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="cee29-118">Windows Server 2012 R2</span></span>

<span data-ttu-id="cee29-119">Installieren Sie die Betriebssystemsoftware im Standard Edition-Server-oder Enterprise Edition-Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="cee29-119">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="cee29-120">Wenden Sie alle Updates in der vorgesehenen Reihenfolge an, um das Betriebssystem auf den neuesten Stand zu bringen und die Organisationsstandards in Bezug auf Updates zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="cee29-120">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="cee29-121">Ausführliche Informationen zu den Betriebsanforderungen finden Sie unter [Betriebssystemunterstützung für Server und Tools in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Unterstützungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cee29-121">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

> [!NOTE] 
> <span data-ttu-id="cee29-122">Das in-Place-Upgrade des Betriebssystems wird mit lync Server 2013 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cee29-122">In-place upgrade of the operating system is not supported with Lync Server 2013.</span></span>  <span data-ttu-id="cee29-123">Sie müssen einen separaten Pool bereitstellen und Benutzer mit einem anderen Betriebssystem in den neuen Pool migrieren.</span><span class="sxs-lookup"><span data-stu-id="cee29-123">You must deploy a separate pool and migrate users to the new pool with a different operating system.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cee29-124">Damit lync Server 2013 an Windows Server 2012 R2 arbeiten können, müssen Sie möglicherweise den Wert eines Registrierungsschlüssels in Windows Server ändern.</span><span class="sxs-lookup"><span data-stu-id="cee29-124">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="cee29-125">Diese Änderung ist möglicherweise erforderlich, damit Zertifikate ordnungsgemäß funktionieren, und Clients können sich bei Survivable Branch Appliances registrieren.</span><span class="sxs-lookup"><span data-stu-id="cee29-125">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="cee29-126">Weitere Informationen finden Sie unter <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A> .</span><span class="sxs-lookup"><span data-stu-id="cee29-126">For more information, see <A class=uri href="https://support.microsoft.com/kb/2901554">https://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="cee29-127">Zusätzliche Software für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cee29-127">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="cee29-128">Zusätzlich zu den für das Betriebssystem erforderlichen Updates erfordert lync Server 2013 Betriebssystem Rollen, Features und Software für den Betrieb.</span><span class="sxs-lookup"><span data-stu-id="cee29-128">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="cee29-129">Ausführliche Informationen zu der zusätzlichen Software, die vor dem Veröffentlichen der Topologie installiert werden muss, und zum Installieren von lync Server 2013 finden Sie unter [Additional Software Requirements for lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="cee29-129">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="cee29-130">Zusätzliche Software, die für alle Server Rollen erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="cee29-130">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="cee29-131">Für alle Serverrollen müssen Sie auch sicherstellen, dass Windows PowerShell Befehlszeilenschnittstelle 3,0 und Microsoft .NET Framework 4.5 installiert sind.</span><span class="sxs-lookup"><span data-stu-id="cee29-131">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="cee29-132">Darüber hinaus sind Windows PowerShell Befehlszeilenschnittstelle 3,0 und Microsoft .NET Framework 4.5 auf jedem Computer erforderlich, auf dem Sie die lync Server-Verwaltungstools ausführen werden.</span><span class="sxs-lookup"><span data-stu-id="cee29-132">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="cee29-133">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="cee29-133">Windows PowerShell 3.0</span></span>

<span data-ttu-id="cee29-134">Für lync Server 2013 müssen Sie Windows PowerShell 3,0 auf jedem Computer installieren, der an der lync Server Topologie teilnehmen soll.</span><span class="sxs-lookup"><span data-stu-id="cee29-134">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="cee29-135">Ausführliche Informationen zum Installieren von Windows PowerShell 3,0 finden Sie unter [Installing Windows PowerShell 3,0 for lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="cee29-135">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="cee29-136">Unter Windows Server &nbsp; 2008 &nbsp; R2 mit SP1 kann Windows PowerShell Befehlszeilenschnittstelle 3,0 nicht vor der Installation von Microsoft .NET Framework 4.5 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="cee29-136">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="cee29-137">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="cee29-137">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="cee29-138">Wenn Sie Microsoft .NET Framework 4.5 auf Servern installieren, auf denen lync Server 2013 auf Windows Server 2012 oder Windows Server 2012 R2 ausgeführt wird, müssen Sie einen weiteren Schritt ausführen.</span><span class="sxs-lookup"><span data-stu-id="cee29-138">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="cee29-139">Nachdem .NET Framework 4.5 installiert wurde, verwenden Sie Server-Manager, um die HTTP-Aktivierung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="cee29-139">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="cee29-140">**So installieren Sie die .NET 4,5-HTTP-Aktivierung auf Windows Server 2012 oder Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="cee29-140">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="cee29-141">Klicken Sie im **Startmenü** auf **Programme**und dann auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="cee29-141">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="cee29-142">Wählen Sie im Server-Manager unter **Zusammenfassung der Features**die Option **Features hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="cee29-142">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="cee29-143">Erweitern Sie **.NET Framework 4.5**.</span><span class="sxs-lookup"><span data-stu-id="cee29-143">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="cee29-144">Wählen Sie **WCF-Aktivierung** aus, wenn Sie nicht bereits ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="cee29-144">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="cee29-145">Wählen Sie dann **http-Aktivierung**aus.</span><span class="sxs-lookup"><span data-stu-id="cee29-145">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="cee29-146">Klicken Sie auf **weiter** , und führen Sie die Anweisungen aus, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="cee29-146">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

