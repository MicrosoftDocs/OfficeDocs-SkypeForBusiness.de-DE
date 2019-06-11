---
title: 'Lync Server 2013: Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported virtualization technologies and known limitations
ms:assetid: 6d3d749d-e840-4c05-afae-d6e69e7616aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204982(v=OCS.15)
ms:contentKeyID: 48184428
ms.date: 02/07/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b5c99151be45f70d1d95fa0a89835ebb6f7d352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-virtualization-technologies-and-known-limitations-in-lync-server-2013"></a><span data-ttu-id="f1823-102">Unterstützte Virtualisierungstechnologien und bekannte Einschränkungen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1823-102">Supported virtualization technologies and known limitations in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1823-103">_**Letztes Änderungsdatum des Themas:** 2017-02-06_</span><span class="sxs-lookup"><span data-stu-id="f1823-103">_**Topic Last Modified:** 2017-02-06_</span></span>

<span data-ttu-id="f1823-104">Das lync VDI-Plug-in ermöglicht Audio-und Videoanrufe nach unterstützten Virtualisierungstechnologien.</span><span class="sxs-lookup"><span data-stu-id="f1823-104">The Lync VDI plug-in allows audio and video calling for supported virtualization technologies.</span></span> <span data-ttu-id="f1823-105">Dadurch wird die für Microsoft lync Server 2010 in der [Client-Virtualisierung in Microsoft lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) -Whitepaper skizzierte Funktionalität erweitert.</span><span class="sxs-lookup"><span data-stu-id="f1823-105">This extends the functionality outlined for Microsoft Lync Server 2010 in the [Client Virtualization in Microsoft Lync 2010](https://go.microsoft.com/fwlink/?linkid=330447) white paper.</span></span> <span data-ttu-id="f1823-106">Gemäß Standardtelefonvorschriften ist auch Unterstützung für E911 enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1823-106">In compliance with standard telephone regulations, support for E911 is also included.</span></span> <span data-ttu-id="f1823-107">In den folgenden Abschnitten werden die Virtualisierungstechnologien beschrieben, die vom lync-VDI-Plug-in und den bekannten Funktionseinschränkungen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f1823-107">The following sections describe the virtualization technologies that are supported by the Lync VDI plug-in and the known feature limitations.</span></span>

<div>

## <a name="support-for-virtualization-technologies"></a><span data-ttu-id="f1823-108">Unterstützung für Virtualisierungstechnologien</span><span class="sxs-lookup"><span data-stu-id="f1823-108">Support for Virtualization Technologies</span></span>

<span data-ttu-id="f1823-109">Das lync-VDI-Plug-in unterstützt das vollständige Desktop-Remoting im Szenario des persönlichen virtuellen Desktops, aber nicht im Szenario der Remotedesktopsitzung.</span><span class="sxs-lookup"><span data-stu-id="f1823-109">The Lync VDI plug-in supports full desktop remoting in the personal virtual desktop scenario, but not in the remote desktop session scenario.</span></span> <span data-ttu-id="f1823-110">Diese Szenarien können wie folgt beschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="f1823-110">These scenarios can be described as follows:</span></span>

  - <span data-ttu-id="f1823-111">**Unterstützt: Personalisierte virtuelle Desktops oder Virtual Desktop Infrastructure (VDI).**    In diesem Szenario meldet sich jeder Benutzer an einem anpassbaren virtuellen Desktop an und kann Dateien auf dem Desktop speichern, die in allen Sitzungen beibehalten werden.</span><span class="sxs-lookup"><span data-stu-id="f1823-111">**Supported: Personalized Virtual Desktops or Virtual Desktop Infrastructure (VDI).**   In this scenario, each user logs on to a customizable virtual desktop and is able to save files on the desktop that persist across sessions.</span></span> <span data-ttu-id="f1823-112">Microsoft Remote Desktop Dienste, VMware Horizon View und Citrix XenDesktop sind Implementierungen, die für die Verwendung mit lync getestet wurden.</span><span class="sxs-lookup"><span data-stu-id="f1823-112">Microsoft Remote Desktop Services, VMware Horizon View, and Citrix XenDesktop are implementations that have been tested for use with Lync.</span></span> <span data-ttu-id="f1823-113">Informationen zu herstellerspezifischen VDI-Umgebungen und Clienthardware, die von Microsoft getestet wurden, finden Sie unter [für Microsoft lync qualifizierte Infrastruktur](https://go.microsoft.com/fwlink/?linkid=313435).</span><span class="sxs-lookup"><span data-stu-id="f1823-113">For information about vendor-specific VDI environments and client hardware that have been tested by Microsoft, see [Infrastructure qualified for Microsoft Lync](https://go.microsoft.com/fwlink/?linkid=313435).</span></span>

  - <span data-ttu-id="f1823-114">**Nicht unterstützt: Remote Desktop Sitzungen.**    In diesem Szenario meldet sich jeder Benutzer bei einer generischen virtuellen Desktopsitzung an, die nicht angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="f1823-114">**Not supported: Remote Desktop Sessions.**   In this scenario, each user logs on to a generic virtual desktop session that cannot be customized.</span></span> <span data-ttu-id="f1823-115">Zu den Beispielimplementierungen gehören Microsoft-Remotedesktopsitzungen (RDSH) und Citrix XenApp in Kombination mit Citrix Receiver.</span><span class="sxs-lookup"><span data-stu-id="f1823-115">Example implementations include Microsoft Remote Desktop Sessions (RDSH) and Citrix XenApp combined with Citrix Receiver.</span></span>

<span data-ttu-id="f1823-116">Das lync-VDI-Plug-in unterstützt keine anderen Virtualisierungstechnologien wie Application Virtualization, was die Verwendung einer Anwendung ermöglicht, ohne dass die vollständige Anwendung lokal installiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="f1823-116">The Lync VDI plug-in does not support other virtualization technologies, such as application virtualization, which allows the use of an application without requiring installation of the full application locally.</span></span> <span data-ttu-id="f1823-117">Zu den Beispielimplementierungen gehören Citrix XenApp und Microsoft Application Virtualization (App-V).</span><span class="sxs-lookup"><span data-stu-id="f1823-117">Example implementations include Citrix XenApp and Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="f1823-118">Anwendungsstreaming, Anwendungsremoting und gemischte Virtualisierungsmodi (zum Beispiel Anwendungsremoting in vollem Desktopremoting) werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1823-118">Application streaming, application remoting, and mixed virtualization modes (for example, application remoting in full desktop remoting) are not supported.</span></span>

<span data-ttu-id="f1823-119">Um die Erweiterbarkeit zu ermöglichen, wurde das lync VDI-Plug-in für die Verwendung von plattformunabhängigen APIs mit dem Namen Dynamic Virtual Channels (DVCs) entwickelt.</span><span class="sxs-lookup"><span data-stu-id="f1823-119">To allow extensibility, the Lync VDI plug-in was designed to use platform-independent APIs called Dynamic Virtual Channels (DVCs).</span></span> <span data-ttu-id="f1823-120">Informationen zu Szenarien, die nicht explizit von lync unterstützt werden, finden Sie unter Support-Statements des VDI-Lösungsanbieters.</span><span class="sxs-lookup"><span data-stu-id="f1823-120">For scenarios that are not explicitly supported by Lync, refer to support statements from the VDI solution provider.</span></span>

</div>

<div>

## <a name="known-feature-limitations"></a><span data-ttu-id="f1823-121">Bekannte Funktionseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="f1823-121">Known Feature Limitations</span></span>

<span data-ttu-id="f1823-122">Im folgenden sind bekannte Einschränkungen bei der Verwendung von lync 2013 in einer VDI-Umgebung bekannt:</span><span class="sxs-lookup"><span data-stu-id="f1823-122">The following are known limitations when you use Lync 2013 in a VDI environment:</span></span>

  - <span data-ttu-id="f1823-123">Es gibt nur begrenzte Unterstützung für die Anonymisierungs Funktionen für Anruf Delegierungen und Reaktionsgruppen-Agents.</span><span class="sxs-lookup"><span data-stu-id="f1823-123">There is limited support for Call Delegation and Response Group Agent Anonymization features.</span></span>

  - <span data-ttu-id="f1823-124">Folgende Features werden nicht unterstützt:</span><span class="sxs-lookup"><span data-stu-id="f1823-124">There is no support for the following features:</span></span>
    
      - <span data-ttu-id="f1823-125">Integrierte Optimierungsseiten für Audio- und Videogeräte</span><span class="sxs-lookup"><span data-stu-id="f1823-125">Integrated Audio Device and Video Device tuning pages.</span></span>
    
      - <span data-ttu-id="f1823-126">Mehransicht für Video</span><span class="sxs-lookup"><span data-stu-id="f1823-126">Multiple-view video.</span></span>
    
      - <span data-ttu-id="f1823-127">Aufzeichnen von Konversationen</span><span class="sxs-lookup"><span data-stu-id="f1823-127">Recording of conversations.</span></span>
    
      - <span data-ttu-id="f1823-128">Remote Desktop Dienste (RDS).</span><span class="sxs-lookup"><span data-stu-id="f1823-128">Remote Desktop Services (RDS).</span></span>
    
      - <span data-ttu-id="f1823-129">Anonyme Teilnahme an Besprechungen (also an lync-Besprechungen, die von einer Organisation gehostet werden, die nicht mit Ihrer Organisation in Verbindung steht).</span><span class="sxs-lookup"><span data-stu-id="f1823-129">Joining meetings anonymously (that is, joining Lync meetings hosted by an organization that does not federate with your organization).</span></span>
    
      - <span data-ttu-id="f1823-130">Verwenden des lync-VDI-Plug-ins zusammen mit einem lync Phone Edition-Gerät.</span><span class="sxs-lookup"><span data-stu-id="f1823-130">Using the Lync VDI plug-in along with a Lync Phone Edition device.</span></span>
    
      - <span data-ttu-id="f1823-131">Anrufkontinuität im Fall eines Netzwerkausfalls</span><span class="sxs-lookup"><span data-stu-id="f1823-131">Call continuity in case of a network outage.</span></span>
    
      - <span data-ttu-id="f1823-132">Features für benutzerdefinierte Klingeltöne und Wartemusik</span><span class="sxs-lookup"><span data-stu-id="f1823-132">Customized ringtones and music-on-hold features.</span></span>

  - <span data-ttu-id="f1823-133">Das lync-VDI-Plug-in wird in einer Office 365-Umgebung nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1823-133">The Lync VDI plug-in is not supported in an Office 365 environment.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

