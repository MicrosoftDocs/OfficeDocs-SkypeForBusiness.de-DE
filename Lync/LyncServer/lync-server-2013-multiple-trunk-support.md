---
title: 'Lync Server 2013: mehrere trunk-Unterstützung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d13ca1a28fd28a6d280ddf3a18e57e09376e668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a><span data-ttu-id="34dcb-102">Mehrere trunk-Unterstützung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34dcb-102">Multiple trunk support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34dcb-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="34dcb-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="34dcb-104">Die lync Server 2013-Funktionalität unterstützt mehrere Zuordnungen zwischen Gateways und Vermittlungsservern.</span><span class="sxs-lookup"><span data-stu-id="34dcb-104">Lync Server 2013 functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="34dcb-105">Diese Zuordnungen werden durch Definieren eines Trunks erstellt, bei dem es sich um eine logische Zuordnung zwischen einem Vermittlungs Server Pool und einem PSTN-Gateway (Public Switched Telephone Network), Sitzungs Grenz Controller (SBC) oder IP-PBX handelt.</span><span class="sxs-lookup"><span data-stu-id="34dcb-105">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="34dcb-106">Verwenden Sie den Topologie-Generator, um Gateways mit Vermittlungsservern (also Trunks) zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="34dcb-106">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

  - <span data-ttu-id="34dcb-107">Um einen trunk in lync Server 2013 zuzuweisen oder zu entfernen, müssen Sie zuerst einen trunk im Topologie-Generator definieren.</span><span class="sxs-lookup"><span data-stu-id="34dcb-107">To assign or remove a trunk in Lync Server 2013, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="34dcb-108">Ein trunk besteht aus der folgenden Zuordnung: vollständig qualifizierter Domänenname (Fully Qualified Domain Name, FQDN), Mediation Server-Abhör Port, Gateway-FQDN und Gateway-Abhör Port.</span><span class="sxs-lookup"><span data-stu-id="34dcb-108">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>

  - <span data-ttu-id="34dcb-109">Zum Konfigurieren mehrerer Trunks können Sie mehrere Zuordnungen zwischen dem gleichen Gateway und dem Vermittlungs Server erstellen.</span><span class="sxs-lookup"><span data-stu-id="34dcb-109">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="34dcb-110">Dies bietet zusätzliche Widerstandsfähigkeit für die Enterprise-VoIP-Infrastruktur, die besonders in interoperational-Szenarien (Private Branch Exchange) verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="34dcb-110">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span>

<span data-ttu-id="34dcb-111">Beim Definieren eines Trunks muss er einer Route zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="34dcb-111">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="34dcb-112">Um einen trunk einer Route zuzuordnen, definieren Sie einen einfachen Namen für den trunk im Topologie-Generator.</span><span class="sxs-lookup"><span data-stu-id="34dcb-112">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="34dcb-113">Dieser einfache Name wird als trunk-Name in der lync Server-Systemsteuerung verwendet, in der Trunks Routen zugeordnet werden können.</span><span class="sxs-lookup"><span data-stu-id="34dcb-113">This simple name is used as the trunk name in the Lync Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="34dcb-114">Der einfache trunk-Name wird als Gateway-Name aus der lync Server-Verwaltungsshell verwendet.</span><span class="sxs-lookup"><span data-stu-id="34dcb-114">The simple trunk name is used as the gateway name from the Lync Server Management Shell.</span></span>

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

<span data-ttu-id="34dcb-115">Der Administrator muss einen Standard trunk auswählen, der einem Vermittlungs Server zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="34dcb-115">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="34dcb-116">Klicken Sie im Topologie-Generator mit der rechten Maustaste auf den zugehörigen Vermittlungs Server, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="34dcb-116">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="34dcb-117">Geben Sie das Standardgateway für den Vermittlungs Server an.</span><span class="sxs-lookup"><span data-stu-id="34dcb-117">Specify the default gateway for the Mediation Server.</span></span>

<span data-ttu-id="34dcb-118">Das folgende Diagramm zeigt die verschiedenen Trunks, die für jeden Vermittlungs Server und jedes Gateway definiert sind.</span><span class="sxs-lookup"><span data-stu-id="34dcb-118">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span>

<span data-ttu-id="34dcb-119">**M-N trunk-Routing**</span><span class="sxs-lookup"><span data-stu-id="34dcb-119">**M-N Trunk Routing**</span></span>

<span data-ttu-id="34dcb-120">![Mehrere trunk Aufgaben.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Mehrere trunk Aufgaben.")</span><span class="sxs-lookup"><span data-stu-id="34dcb-120">![Multiple trunk assignments.](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "Multiple trunk assignments.")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

