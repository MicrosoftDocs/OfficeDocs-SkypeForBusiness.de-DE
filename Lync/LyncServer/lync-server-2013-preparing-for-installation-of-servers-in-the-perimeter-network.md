---
title: Vorbereiten der Installation von Servern im Umkreisnetzwerk
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing for installation of servers in the perimeter network
ms:assetid: 5e6c457a-f964-4ef7-a709-97abda9c673a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398416(v=OCS.15)
ms:contentKeyID: 48184292
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7168c1e32bd4ceb1466678d08a3d7ca9e6dc69e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-for-installation-of-servers-in-the-perimeter-network-for-lync-server-2013"></a><span data-ttu-id="0e003-102">Vorbereiten der Installation von Servern im Umkreisnetzwerk für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-102">Preparing for installation of servers in the perimeter network for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e003-103">_**Letztes Änderungsstand des Themas:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0e003-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0e003-104">Vor dem Einrichten von Edgeserverkomponenten müssen Sie sicherstellen, dass die Computer die Systemanforderungen erfüllen. Darüber hinaus müssen Sie einige vorbereitende Schritte für die Bereitstellung von Edgeserverkomponenten ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e003-104">Before you set up Edge Server components, you need to ensure that computers that you are setting up meet system requirements and complete other prerequisite steps required for deployment of Edge Server components.</span></span>

<span data-ttu-id="0e003-105">Bevor Sie beginnen, sollten Sie in der Planungsdokumentation die folgenden Themen für die Referenzarchitektur lesen, die Sie bereitstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="0e003-105">Before you begin, review the details in the following topics in the Planning documentation for the reference architecture that you want to deploy:</span></span>

  - [<span data-ttu-id="0e003-106">Einzelner konsolidierter Edgeserver mit privaten IP-Adressen und NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="0e003-107">Einzelner konsolidierter Edgeserver mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="0e003-108">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit privaten IP-Adressen mithilfe von NAT in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="0e003-109">Skalierter konsolidierter Edgeserver, DNS-Lastenausgleich mit öffentlichen IP-Adressen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="0e003-110">Skalierter konsolidierter Edgeserver mit Hardware-Lastenausgleichssystemen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e003-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0e003-111">In This Section</span></span>

  - [<span data-ttu-id="0e003-112">Konfigurieren von DNS für die Edge-Unterstützung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-112">Configure DNS for edge support in Lync Server 2013</span></span>](lync-server-2013-configure-dns-for-edge-support.md)

  - [<span data-ttu-id="0e003-113">Einrichten von Hardware-Lastenausgleich für skalierte Edge-Topologien in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-113">Set up hardware load balancers for scaled edge topologies in Lync Server 2013</span></span>](lync-server-2013-set-up-hardware-load-balancers-for-scaled-edge-topologies.md)

  - [<span data-ttu-id="0e003-114">Konfigurieren von Firewalls und Ports für den Zugriff durch externe Benutzer in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-114">Configure firewalls and ports for external user access in Lync Server 2013</span></span>](lync-server-2013-configure-firewalls-and-ports-for-external-user-access.md)

  - [<span data-ttu-id="0e003-115">Ermitteln der Anforderungen für externe A/V-Firewalls und Ports für lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-115">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [<span data-ttu-id="0e003-116">Anfordern von Zertifikaten für Edge-Komponenten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e003-116">Request certificates for edge components in Lync Server 2013</span></span>](lync-server-2013-request-certificates-for-edge-components.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

