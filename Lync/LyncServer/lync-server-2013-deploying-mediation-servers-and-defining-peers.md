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
ms.openlocfilehash: b20f5e733dddd34971ca3a5070e99364785e147a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a><span data-ttu-id="91aa6-102">Bereitstellen von Vermittlungsservern und Definieren von Peers in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91aa6-102">Deploying Mediation Servers and defining peers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91aa6-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="91aa6-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="91aa6-104">Die Enterprise-VoIP-Arbeitsauslastung, Einwahlkonferenzen und erweiterte Enterprise-VoIP-Anwendungen (reaktionsgruppenanwendung, Anruf Park Anwendung, Anrufsteuerung (CAC) usw.) stehen in Front-End-Pools zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="91aa6-104">The Enterprise Voice workload, dial-in conferencing, and advanced Enterprise Voice applications (Response Group application, Call Park application, call admission control (CAC), and so on), are available in Front End pools.</span></span> <span data-ttu-id="91aa6-105">Mit lync Server 2013 ist die Funktionalität des Vermittlungsservers in den Front-End-Server integriert.</span><span class="sxs-lookup"><span data-stu-id="91aa6-105">With Lync Server 2013, the functionality of the Mediation Server is built into the Front End Server.</span></span> <span data-ttu-id="91aa6-106">Ein separater eigenständiger Vermittlungs Server ist nicht mehr erforderlich.</span><span class="sxs-lookup"><span data-stu-id="91aa6-106">A separate stand-alone Mediation Server is no longer necessary.</span></span> <span data-ttu-id="91aa6-107">Front-End-Pools können direkt mit unterstützten Gateways (einem Public Switched Telephone Network (PSTN)-Gateway oder einer IP-Telefonanlage) kommunizieren, wodurch die Notwendigkeit eines Vermittlungsservers, der als Vermittler fungiert, entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="91aa6-107">Front End pools can communicate directly with supported gateways (a public switched telephone network (PSTN) gateway or an IP-PBX), removing the need for a Mediation Server to serve as an intermediary.</span></span>

<span data-ttu-id="91aa6-108">Die einzige Ausnahme stellt die Konfiguration eines SIP-Trunks zum Herstellen einer Verbindung mit einem Session Border Controller (SBC) für einen Anbieter von Internettelefoniediensten dar.</span><span class="sxs-lookup"><span data-stu-id="91aa6-108">The only exception is if you configure a SIP trunk to connect to a Session Border Controller for an Internet Telephony Service Provider.</span></span> <span data-ttu-id="91aa6-109">Wenn Sie Ihre Enterprise-VoIP-Infrastruktur mit Ihrem SIP-Trunk-Anbieter verbinden möchten, muss ein separater Vermittlungs Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="91aa6-109">To connect your Enterprise Voice infrastructure to your SIP trunk provider, a separate Mediation Server must be deployed.</span></span>

<span data-ttu-id="91aa6-110">Die Verbindung zwischen lync Server (der Vermittlungsserver Komponente in einem Front-End-Pool oder einem eigenständigen Vermittlungsserver) und einem Gateway wird als logische Zuordnung als " *trunk*" definiert.</span><span class="sxs-lookup"><span data-stu-id="91aa6-110">The connection between Lync Server (the Mediation Server component on a Front End pool or stand-alone Mediation Server) and a gateway is defined as a logical association called a *trunk*.</span></span> <span data-ttu-id="91aa6-111">In den Themen in diesem Abschnitt wird beschrieben, wie Sie einen trunk definieren und wie Sie einen eigenständigen Vermittlungs Server bereitstellen, wenn Sie eine Verbindung mit einem SIP-Stamm herstellen.</span><span class="sxs-lookup"><span data-stu-id="91aa6-111">The topics in this section describe how to define a trunk and how to deploy a stand-alone Mediation Server, if you connect to a SIP trunk.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="91aa6-112">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="91aa6-112">In This Section</span></span>

  - [<span data-ttu-id="91aa6-113">Definieren eines Vermittlungsservers im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91aa6-113">Define a Mediation Server in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [<span data-ttu-id="91aa6-114">Definieren eines Gateways im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91aa6-114">Define a gateway in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [<span data-ttu-id="91aa6-115">Installieren der Dateien für den Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91aa6-115">Install the files for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-install-the-files-for-mediation-server.md)

  - [<span data-ttu-id="91aa6-116">Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91aa6-116">Define additional trunks in Topology Builder in Lync Server 2013</span></span>](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a><span data-ttu-id="91aa6-117">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="91aa6-117">Related Sections</span></span>

[<span data-ttu-id="91aa6-118">Konfigurieren von Einwahlkonferenzen in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91aa6-118">Configuring dial-in conferencing in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

