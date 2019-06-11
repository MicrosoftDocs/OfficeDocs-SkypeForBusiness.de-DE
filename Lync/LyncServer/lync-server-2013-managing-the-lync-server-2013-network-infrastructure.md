---
title: 'Lync Server 2013: Verwalten der Lync Server 2013-Netzwerkinfrastruktur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bd95ac0259e86f3ac8fd39a09276bffa88cfc75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827718"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="86039-102">Verwalten der Lync Server 2013-Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="86039-102">Managing the Lync Server 2013 network infrastructure</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86039-103">_**Letztes Änderungsdatum des Themas:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="86039-103">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="86039-104">Microsoft lync Server 2013 umfasst die Unterstützung für die Anrufannahme Steuerung (CAC) und die medienumgehung.</span><span class="sxs-lookup"><span data-stu-id="86039-104">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="86039-105">Um diese Features zu implementieren, müssen Sie ein Netzwerk von Regionen, Websites, Subnets usw. konfigurieren, mit dem Sie die Bandbreite in Situationen verwalten können, in denen Audio-und Videoübertragungen eingeschränkt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="86039-105">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="86039-106">Sie können auch die Quality of Service (QoS)-Netzwerktechnologie verwenden, um ein optimales Endbenutzererlebnis für Audio-und Videokommunikation zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="86039-106">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="86039-107">Sie können die lync Server-Systemsteuerung verwenden, um CAC, medienumgehung und QoS einzurichten und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="86039-107">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="86039-108">In den folgenden Themen finden Sie eine schrittweise Anleitung dazu.</span><span class="sxs-lookup"><span data-stu-id="86039-108">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="86039-109">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="86039-109">In This Section</span></span>

  - [<span data-ttu-id="86039-110">Verwalten von QoS (Quality of Service) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86039-110">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="86039-111">Verwalten der Anruf Zulassungs Steuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86039-111">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="86039-112">Lync Server 2013-Netzwerkschnittstellen</span><span class="sxs-lookup"><span data-stu-id="86039-112">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="86039-113">Verhindern neuer Verbindungen mit lync Server 2013 für die Server Wartung</span><span class="sxs-lookup"><span data-stu-id="86039-113">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="86039-114">Methodik der lync-Anrufqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86039-114">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="86039-115">Wichtige Integritätsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="86039-115">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

