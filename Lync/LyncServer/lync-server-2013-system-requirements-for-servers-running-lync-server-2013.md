---
title: 'Lync Server 2013: Systemanforderungen für Server mit Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for servers running Lync Server 2013
ms:assetid: 781d487d-5958-416a-becb-904d9af3cc0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398588(v=OCS.15)
ms:contentKeyID: 48184564
ms.date: 07/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ad30b9687c9566adb7936612e71ae9f41e69095
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-servers-running-lync-server-2013"></a><span data-ttu-id="61a78-102">Systemanforderungen für Server mit Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61a78-102">System requirements for servers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61a78-103">_**Letztes Änderungsdatum des Themas:** 2014-07-24_</span><span class="sxs-lookup"><span data-stu-id="61a78-103">_**Topic Last Modified:** 2014-07-24_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61a78-104">Details zu den Hardwareanforderungen finden Sie unter <A href="lync-server-2013-server-hardware-platforms.md">Server Hardwareplattformen für lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="61a78-104">For details about hardware requirements, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="61a78-105">Standard Edition-und Enterprise Edition-Server haben die gleichen Softwareanforderungen.</span><span class="sxs-lookup"><span data-stu-id="61a78-105">Standard Edition and Enterprise Edition servers share the same software requirements.</span></span>

<span data-ttu-id="61a78-106">Server mit lync Server 2013, Enterprise Edition, sind für große Organisationen als die wichtigste organisatorische Bereitstellung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="61a78-106">Servers running Lync Server 2013, Enterprise Edition are intended for large organizations as the main organizational deployment.</span></span> <span data-ttu-id="61a78-107">Der Enterprise Edition-Server wurde für die Skalierung auf ungefähr 80.000-verwaltete Benutzer pro Pool konzipiert.</span><span class="sxs-lookup"><span data-stu-id="61a78-107">Enterprise Edition server is designed to scale to approximately 80,000 homed users per pool.</span></span> <span data-ttu-id="61a78-108">Server, auf denen lync Server 2013, Standard Edition ausgeführt wird, sind für kleinere Organisationen und Remotestandorte von der Haupt Bereitstellung der Organisation vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="61a78-108">Servers running Lync Server 2013, Standard Edition are intended for smaller organizations and remote locations from the main organization deployment.</span></span> <span data-ttu-id="61a78-109">Ein paar von Standard Edition-Servern kann bis zu 5.000-Benutzer unterstützen.</span><span class="sxs-lookup"><span data-stu-id="61a78-109">One pair of Standard Edition servers can support up to 5,000 users..</span></span> <span data-ttu-id="61a78-110">Einzelheiten zu den Unterschieden zwischen Standard Edition-Servern und Enterprise Edition-Servern finden Sie unter Übersicht über die [Bereitstellung von lync Server 2013](lync-server-2013-deployment-overview.md).</span><span class="sxs-lookup"><span data-stu-id="61a78-110">For details on the differences between Standard Edition servers and Enterprise Edition servers, see [Deployment overview for Lync Server 2013](lync-server-2013-deployment-overview.md).</span></span>

<div>

## <a name="operating-system-installation"></a><span data-ttu-id="61a78-111">Installation des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="61a78-111">Operating System Installation</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="61a78-112">Lync Server 2013 ist nur in einer 64-Bit-Edition verfügbar, die eine 64-Bit-Hardware und eine 64-Bit-Version des Windows Server-Betriebssystems erfordert.</span><span class="sxs-lookup"><span data-stu-id="61a78-112">Lync Server 2013 is available only in a 64-bit edition, which requires 64-bit hardware and a 64-bit edition of the Windows Server operating system.</span></span> <span data-ttu-id="61a78-113">Eine 32-Bit-Version von lync Server 2013 ist in dieser Version nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="61a78-113">A 32-bit edition of Lync Server 2013 is not available with this release.</span></span>



</div>

<span data-ttu-id="61a78-114">Standard Edition und Enterprise Edition Server können eine der folgenden Aktionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="61a78-114">Standard Edition and Enterprise Edition server can use any of the following:</span></span>

  - <span data-ttu-id="61a78-115">Windows Server 2008 R2 SP1 oder neuestes Service Pack</span><span class="sxs-lookup"><span data-stu-id="61a78-115">Windows Server 2008 R2 SP1 or latest service pack</span></span>

  - <span data-ttu-id="61a78-116">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="61a78-116">Windows Server 2012</span></span>

  - <span data-ttu-id="61a78-117">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="61a78-117">Windows Server 2012 R2</span></span>

<span data-ttu-id="61a78-118">Installieren Sie die Betriebssystemsoftware auf dem Standard Edition-Server oder Enterprise Edition-Front-End-Server.</span><span class="sxs-lookup"><span data-stu-id="61a78-118">Install the operating system software on the Standard Edition Server or Enterprise Edition Front End Server.</span></span> <span data-ttu-id="61a78-119">Wenden Sie alle Updates an, um das Betriebssystem auf das neueste Update und die erforderliche Aktualisierungsstufe zu bringen, die mit den Standards Ihrer Organisation in Einklang steht.</span><span class="sxs-lookup"><span data-stu-id="61a78-119">Apply all updates in order to bring the operating system up to the latest update and required update level consistent with your organization’s standards.</span></span> <span data-ttu-id="61a78-120">Weitere Informationen zu den Betriebsanforderungen finden Sie unter unter [Stützung von Server-und Tools-Betriebssystemen in lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in der Dokumentation zur Unterstützung.</span><span class="sxs-lookup"><span data-stu-id="61a78-120">For more details about the operating requirements, see [Server and tools operating system support in Lync Server 2013](lync-server-2013-server-and-tools-operating-system-support.md) in the Supportability documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61a78-121">Damit lync Server 2013 unter Windows Server 2012 R2 funktioniert, müssen Sie möglicherweise den Wert eines Registrierungsschlüssels in Windows Server ändern.</span><span class="sxs-lookup"><span data-stu-id="61a78-121">For Lync Server 2013 to work on Windows Server 2012 R2, you may need to change the value of a registry key in Windows Server.</span></span> <span data-ttu-id="61a78-122">Diese Änderung ist möglicherweise erforderlich, damit Zertifikate ordnungsgemäß funktionieren, und Clients können sich bei Überlebenden Branch-Appliances registrieren.</span><span class="sxs-lookup"><span data-stu-id="61a78-122">This change may be necessary for certificates to work correctly, and for clients to register with Survivable Branch Appliances.</span></span> <span data-ttu-id="61a78-123">Weitere Informationen finden Sie unter <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.</span><span class="sxs-lookup"><span data-stu-id="61a78-123">For more information, see <A class=uri href="http://support.microsoft.com/kb/2901554">http://support.microsoft.com/kb/2901554</A>.</span></span>



</div>

<div>

## <a name="additional-software-for-lync-server-2013"></a><span data-ttu-id="61a78-124">Zusätzliche Software für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="61a78-124">Additional Software for Lync Server 2013</span></span>

<span data-ttu-id="61a78-125">Zusätzlich zu den für das Betriebssystem erforderlichen Updates erfordert lync Server 2013 die Verwendung von Betriebssystem Rollen,-Features und-Software.</span><span class="sxs-lookup"><span data-stu-id="61a78-125">In addition to the updates required for the operating system, Lync Server 2013 requires operating system roles, features, and software to operate.</span></span> <span data-ttu-id="61a78-126">Details zur zusätzlichen Software, die vor der Veröffentlichung Ihrer Topologie und der Installation von lync Server 2013 installiert werden muss, finden Sie unter [zusätzliche Softwareanforderungen für lync Server 2013](lync-server-2013-additional-software-requirements.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="61a78-126">For details about the additional software that must be installed prior to publishing your topology and installing Lync Server 2013, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-necessary-for-all-server-roles"></a><span data-ttu-id="61a78-127">Zusätzliche Software, die für alle Server Rollen erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="61a78-127">Additional Software Necessary for All Server Roles</span></span>

<span data-ttu-id="61a78-128">Auf allen Serverrollen müssen Sie auch sicherstellen, dass die Windows PowerShell-Befehlszeilenschnittstelle 3,0 und Microsoft .NET Framework 4,5 installiert sind.</span><span class="sxs-lookup"><span data-stu-id="61a78-128">On all server roles, you must also make sure that Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are installed.</span></span>

<span data-ttu-id="61a78-129">Darüber hinaus sind Windows PowerShell-Befehlszeilenschnittstellen 3,0 und Microsoft .NET Framework 4,5 auf jedem Computer erforderlich, auf dem die lync Server-Verwaltungstools ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="61a78-129">Additionally, Windows PowerShell command-line interface 3.0 and Microsoft .NET Framework 4.5 are required on any computer where you will run the Lync Server administrative tools.</span></span>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="61a78-130">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="61a78-130">Windows PowerShell 3.0</span></span>

<span data-ttu-id="61a78-131">Lync Server 2013 erfordert, dass Sie Windows PowerShell 3,0 auf jedem Computer installieren, der an ihrer lync Server-Topologie teilnehmen wird.</span><span class="sxs-lookup"><span data-stu-id="61a78-131">Lync Server 2013 requires you to install Windows PowerShell 3.0 on each computer that will take part in your Lync Server topology.</span></span> <span data-ttu-id="61a78-132">Details zur Installation von Windows PowerShell 3,0 finden Sie unter [Installieren von Windows PowerShell 3,0 für lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span><span class="sxs-lookup"><span data-stu-id="61a78-132">For details about installing Windows PowerShell 3.0, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="61a78-133">Unter Windows Server&nbsp;2008&nbsp;R2 mit SP1 kann die Windows PowerShell-Befehlszeilenschnittstelle 3,0 nicht vor der Installation von Microsoft .NET Framework 4,5 installiert werden.</span><span class="sxs-lookup"><span data-stu-id="61a78-133">On Windows Server&nbsp;2008&nbsp;R2 with SP1, Windows PowerShell command-line interface 3.0 cannot be installed before installing Microsoft .NET Framework 4.5.</span></span>



</div>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="61a78-134">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="61a78-134">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="61a78-135">Wenn Sie Microsoft .NET Framework 4,5 auf Servern installieren, auf denen lync Server 2013 unter Windows Server 2012 oder Windows Server 2012 R2 ausgeführt wird, müssen Sie einen weiteren Schritt ausführen.</span><span class="sxs-lookup"><span data-stu-id="61a78-135">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 on Windows Server 2012 or Windows Server 2012 R2, you must perform one additional step.</span></span> <span data-ttu-id="61a78-136">Verwenden Sie nach der Installation von .NET Framework 4,5 den Server-Manager, um die HTTP-Aktivierung zu installieren.</span><span class="sxs-lookup"><span data-stu-id="61a78-136">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="61a78-137">**So installieren Sie die .NET 4,5-HTTP-Aktivierung unter Windows Server 2012 oder Windows Server 2012 R2**</span><span class="sxs-lookup"><span data-stu-id="61a78-137">**To Install .NET 4.5 HTTP Activation on Windows Server 2012 or Windows Server 2012 R2**</span></span>

1.  <span data-ttu-id="61a78-138">Klicken Sie im **Startmenü** auf **Programme**und dann auf **Verwaltung**, und klicken Sie dann auf **Server-Manager**.</span><span class="sxs-lookup"><span data-stu-id="61a78-138">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="61a78-139">Wählen Sie im Server-Manager unter **Zusammenfassung der Features**die Option **Features hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="61a78-139">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="61a78-140">Erweitern Sie **.NET Framework 4,5**.</span><span class="sxs-lookup"><span data-stu-id="61a78-140">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="61a78-141">Wählen Sie **WCF-Aktivierung** aus, wenn Sie noch nicht ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="61a78-141">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="61a78-142">Wählen Sie dann **http-Aktivierung**aus.</span><span class="sxs-lookup"><span data-stu-id="61a78-142">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="61a78-143">Klicken Sie auf **weiter** , und folgen Sie den Anweisungen, um die Installation abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="61a78-143">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

