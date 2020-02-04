---
title: 'Phase 3: Bereitstellen des lync Server 2013-pilotpools'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38a9e19ea3d9456a5e6f5b395286d77ed831f6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757679"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="84918-102">Phase 3: Bereitstellen des lync Server 2013-pilotpools</span><span class="sxs-lookup"><span data-stu-id="84918-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84918-103">_**Letztes Änderungsdatum des Themas:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="84918-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="84918-104">In diesem Abschnitt werden die erforderlichen Schritte zum Bereitstellen eines pilotpools von lync Server 2013 beschrieben.</span><span class="sxs-lookup"><span data-stu-id="84918-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="84918-105">Die Bereitstellung von lync Server 2013 erfordert die Verwendung des Topologie-Generators zum Definieren Ihrer Topologie und der Komponenten, die Sie bereitstellen möchten, Vorbereiten der Umgebung für die Bereitstellung der lync Server 2013-Komponenten und Veröffentlichen des Topologie-Designs auf dem ersten Front-End Server, und installieren und konfigurieren Sie dann die lync Server 2013-Software für die Komponenten für Ihre Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="84918-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="84918-106">Wenn Sie fertig sind, wird die Bereitstellung Ihres lync Server 2013-pilotpools mit einem vorhandenen lync Server 2010-Pool koexistieren.</span><span class="sxs-lookup"><span data-stu-id="84918-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84918-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="84918-107">In This Section</span></span>

  - [<span data-ttu-id="84918-108">Vorbereiten von Active Directory für Lync Server</span><span class="sxs-lookup"><span data-stu-id="84918-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="84918-109">Herunterladen der Topologie aus einer vorhandenen Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="84918-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="84918-110">Bereitstellen des lync Server 2013-pilotpools</span><span class="sxs-lookup"><span data-stu-id="84918-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="84918-111">Überprüfen der Koexistenz der Pilotinstallation mit Pools der Vorversion</span><span class="sxs-lookup"><span data-stu-id="84918-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="84918-112">Verbinden des Pilotpools mit Edgeservern der Vorversion</span><span class="sxs-lookup"><span data-stu-id="84918-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="84918-113">Konfigurieren von Zugriffsrichtlinien und Zertifikaten für XMPP-Gateways</span><span class="sxs-lookup"><span data-stu-id="84918-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

