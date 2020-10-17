---
title: 'Lync Server 2013: Verwalten der lync Server 2013 Netzwerkinfrastruktur'
description: 'Lync Server 2013: Verwalten der lync Server 2013 Netzwerkinfrastruktur.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Lync Server 2013 network infrastructure
ms:assetid: cb13456a-8f66-4595-be21-8887f30ad4eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182585(v=OCS.15)
ms:contentKeyID: 48185638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab1b5c6fe52374b012063ac26640e9bb25496ad7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564101"
---
# <a name="managing-the-lync-server-2013-network-infrastructure"></a><span data-ttu-id="ed25e-103">Verwalten der lync Server 2013 Netzwerkinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="ed25e-103">Managing the Lync Server 2013 network infrastructure</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ed25e-104">_**Letztes Änderungsstand des Themas:** 2014-02-11_</span><span class="sxs-lookup"><span data-stu-id="ed25e-104">_**Topic Last Modified:** 2014-02-11_</span></span>

<span data-ttu-id="ed25e-105">Microsoft lync Server 2013 beinhaltet Unterstützung für Anrufsteuerung und medienumgehung.</span><span class="sxs-lookup"><span data-stu-id="ed25e-105">Microsoft Lync Server 2013 includes support for call admission control (CAC) and media bypass.</span></span> <span data-ttu-id="ed25e-106">Zur Implementierung dieser Features müssen Sie ein Netzwerk aus Regionen, Standorten, Subnetzen usw. konfigurieren, mit dem Sie die Bandbreite in Situationen verwalten können, in denen Audio-und Videoübertragungen eingeschränkt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ed25e-106">To implement these features you must configure a network of regions, sites, subnets, and so on that will allow you to manage bandwidth in situations where audio and video transmissions need to be restricted.</span></span> <span data-ttu-id="ed25e-107">Sie können auch die QoS-Netzwerktechnologie (Quality of Service) verwenden, um eine optimale Benutzeroberfläche für die Audio-und Videokommunikation zu bieten.</span><span class="sxs-lookup"><span data-stu-id="ed25e-107">You can also use the Quality of Service (QoS) networking technology to help provide an optimal end-user experience for audio and video communications.</span></span>

<span data-ttu-id="ed25e-108">Sie können die lync Server-Systemsteuerung zum Einrichten und Verwalten von CAC, medienumgehung und QoS verwenden.</span><span class="sxs-lookup"><span data-stu-id="ed25e-108">You can use the Lync Server Control Panel to set up and manage CAC, media bypass, and QoS.</span></span> <span data-ttu-id="ed25e-109">Die folgenden Themen enthalten Schritte zur Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="ed25e-109">The following topics provide steps for how to do this.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ed25e-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ed25e-110">In This Section</span></span>

  - [<span data-ttu-id="ed25e-111">Verwalten der Dienstqualität (Quality of Service, QoS) in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed25e-111">Managing Quality of Service (QoS) in Lync Server 2013</span></span>](lync-server-2013-managing-quality-of-service-qos.md)

  - [<span data-ttu-id="ed25e-112">Verwalten der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed25e-112">Managing call admission control in Lync Server 2013</span></span>](lync-server-2013-managing-call-admission-control.md)

  - [<span data-ttu-id="ed25e-113">Lync Server 2013 Netzwerkschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ed25e-113">Lync Server 2013 network interfaces</span></span>](lync-server-2013-lync-server-network-interfaces.md)

  - [<span data-ttu-id="ed25e-114">Verhindern, dass neue Verbindungen für die Server Wartung lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed25e-114">Prevent new connections to Lync Server 2013 for server maintenance</span></span>](lync-server-2013-prevent-new-connections-to-lync-server-for-server-maintenance.md)

  - [<span data-ttu-id="ed25e-115">Methode für die lync-Anrufqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed25e-115">Lync Call Quality Methodology in Lync Server 2013</span></span>](lync-server-2013-poster-lync-call-quality-methodology.md)

  - [<span data-ttu-id="ed25e-116">Wichtige Integritätsindikatoren in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ed25e-116">Key Health Indicators in Lync Server 2013</span></span>](lync-server-2013-poster-key-health-indicators.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

