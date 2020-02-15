---
title: 'Lync Server 2013: unterstützte Technologien für Virtualisierung und bekannte Einschränkungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 387290f8fb7ab88dcb7bc987c38c4a2e3e71ec5e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="1b6fa-102">Unterstützte Virtualisierungstechnologie und bekannte Einschränkungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b6fa-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b6fa-103">_**Letztes Änderungsstand des Themas:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="1b6fa-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="1b6fa-104">Das lync VDI-Plug-in ermöglicht Audio-und Videoanrufe für unterstützte Virtualisierungstechnologie.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="1b6fa-105">Dadurch werden die für Microsoft lync Server 2010 in der [Client-Virtualisierung in Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) Whitepaper beschriebenen Funktionen erweitert.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="1b6fa-106">In Übereinstimmung mit den standardmäßigen Telefon Richtlinien ist auch die Unterstützung für E911 enthalten.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="1b6fa-107">In den folgenden Abschnitten werden die Virtualisierungstechnologien beschrieben, die vom lync VDI-Plug-in und den bekannten Funktionseinschränkungen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="1b6fa-108">Unterstützung für Virtualisierungs-Technologien</span><span class="sxs-lookup"><span data-stu-id="1b6fa-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="1b6fa-109">Das lync VDI-Plug-in unterstützt vollständiges Desktop-Remoting im Szenario für persönliche virtuelle Desktops, jedoch nicht im Szenario mit Remotedesktopsitzungen.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="1b6fa-110">Diese Szenarien können wie folgt beschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="1b6fa-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="1b6fa-111">**Unterstützt: Personalisierte virtuelle Desktops oder virtuelle Desktopinfrastruktur (VDI).**    In diesem Szenario meldet sich jeder Benutzer bei einem anpassbaren virtuellen Desktop an und kann Dateien auf dem Desktop speichern, die in mehreren Sitzungen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="1b6fa-112">Microsoft Remote Desktop Dienste, VMware Horizon View und Citrix XenDesktop sind Implementierungen, die für die Verwendung mit lync getestet wurden.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="1b6fa-113">Informationen zu anbieterspezifischen VDI-Umgebungen und Clienthardware, die von Microsoft getestet wurden, finden Sie unter [für Microsoft lync qualifizierte Infrastruktur](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="1b6fa-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="1b6fa-114">**Nicht unterstützt: Remote Desktop Sitzungen.**    In diesem Szenario meldet sich jeder Benutzer bei einer generischen virtuellen Desktopsitzung an, die nicht angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="1b6fa-115">Zu den Beispielimplementierungen Gehören Microsoft Remote Desktop Sitzungen (RDSH) und Citrix XenApp in Kombination mit Citrix Receiver.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="1b6fa-116">Das lync VDI-Plug-in unterstützt keine anderen Virtualisierungstechnologien wie Application Virtualization, die die Verwendung einer Anwendung ermöglichen, ohne dass die vollständige Anwendung lokal installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="1b6fa-117">Zu den Beispielimplementierungen Gehören Citrix XenApp und Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="1b6fa-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="1b6fa-118">Anwendungsstreaming, Anwendungs Remoting und gemischte Virtualisierungs Modi (beispielsweise Anwendungs Remoting in vollständigem Desktop-Remoting) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="1b6fa-119">Um Erweiterbarkeit zu ermöglichen, wurde das lync VDI-Plug-in für die Verwendung plattformunabhängiger APIs mit dem Namen Dynamic Virtual Channels (DVCs) entwickelt.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="1b6fa-120">Informationen zu Szenarien, die nicht explizit von lync unterstützt werden, finden Sie unter Support Statements from the VDI Solution Provider.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="1b6fa-121">Bekannte Funktionseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="1b6fa-121">Known Feature Limitations</span></span>

<span data-ttu-id="1b6fa-122">Im folgenden sind bekannte Einschränkungen beim Verwenden von lync 2013 in einer VDI-Umgebung bekannt:</span><span class="sxs-lookup"><span data-stu-id="1b6fa-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="1b6fa-123">Es gibt nur eine beschränkte Unterstützung für Anonymisierungs Funktionen für die Anrufdelegierung und den Reaktionsgruppen-Agent.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="1b6fa-124">Folgende Features werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1b6fa-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="1b6fa-125">Integrierte Optimierungsseiten für Audio- und Videogeräte</span><span class="sxs-lookup"><span data-stu-id="1b6fa-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="1b6fa-126">Video mit mehreren Ansichten.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="1b6fa-127">Aufzeichnen von Konversationen</span><span class="sxs-lookup"><span data-stu-id="1b6fa-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="1b6fa-128">Remote Desktop Dienste (RDS).</span><span class="sxs-lookup"><span data-stu-id="1b6fa-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="1b6fa-129">Anonymes Hinzufügen von Besprechungen (also beitreten von lync-Besprechungen, die von einer Organisation gehostet werden, die nicht mit Ihrer Organisation verbunden ist).</span><span class="sxs-lookup"><span data-stu-id="1b6fa-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="1b6fa-130">Verwenden des lync VDI-Plug-ins zusammen mit einem lync Phone Edition-Gerät.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="1b6fa-131">Anrufkontinuität im Fall eines Netzwerkausfalls</span><span class="sxs-lookup"><span data-stu-id="1b6fa-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="1b6fa-132">Angepasste Klingeltöne und Features für die Musik Aufbewahrung.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="1b6fa-133">Das lync VDI-Plug-in wird in einer Office 365 Umgebung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b6fa-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

