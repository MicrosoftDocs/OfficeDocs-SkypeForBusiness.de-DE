---
title: 'Lync Server 2013: Bereitstellen von Vermittlungsservern und Definieren von Peers'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e9ca9fa29d2646a38a9cbf94d79ba9766b21d62
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050647"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="d4d68-102">Bereitstellen von Vermittlungsservern und Definieren von Peers in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4d68-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4d68-103">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="d4d68-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="d4d68-104">Die Enterprise-VoIP-Arbeitsauslastung, Einwahlkonferenzen und erweiterte Enterprise-VoIP-Anwendungen (Reaktionsgruppenanwendung, Anwendung zum Parken von anrufen, Anrufsteuerung (CAC) usw.) stehen in Front-End-Pools zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d4d68-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="d4d68-105">Mit lync Server 2013 ist die Funktionalität der Vermittlungsserver in den Front-End-Server integriert.</span><span class="sxs-lookup"><span data-stu-id="d4d68-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="d4d68-106">Ein separater eigenständiger Vermittlungsserver ist nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d4d68-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="d4d68-107">Front-End-Pools können direkt mit unterstützten Gateways (einem PSTN-Gateway (Public Switched Telephone Network) oder einer IP-Nebenstellenanlage kommunizieren, sodass ein Vermittlungsserver nicht als Vermittler fungieren muss.</span><span class="sxs-lookup"><span data-stu-id="d4d68-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="d4d68-108">Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar.</span><span class="sxs-lookup"><span data-stu-id="d4d68-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="d4d68-109">Um Ihre Enterprise-VoIP-Infrastruktur mit Ihrem SIP-Trunk Anbieter zu verbinden, muss ein separates Vermittlungsserver bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d4d68-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="d4d68-110">Die Verbindung zwischen lync Server (der Vermittlungsserver Komponente auf einem Front-End-Pool oder einem eigenständigen Vermittlungsserver) und einem Gateway ist als logische Zuordnung als *trunk*definiert.</span><span class="sxs-lookup"><span data-stu-id="d4d68-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="d4d68-111">In den Themen in diesem Abschnitt werden die Definition eines Trunks und die Bereitstellung eines eigenständigen Vermittlungsservers beschrieben, wenn Sie eine Verbindung mit einem SIP-Trunk herstellen.</span><span class="sxs-lookup"><span data-stu-id="d4d68-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d4d68-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d4d68-112">In This Section</span></span>

  - [<span data-ttu-id="d4d68-113">Definieren eines Vermittlungsserver im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4d68-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="d4d68-114">Definieren eines Gateways im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4d68-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="d4d68-115">Installieren der Dateien für Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4d68-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="d4d68-116">Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4d68-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="d4d68-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="d4d68-117">Related Sections</span></span>

[<span data-ttu-id="d4d68-118">Konfigurieren von Einwahlkonferenzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4d68-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

