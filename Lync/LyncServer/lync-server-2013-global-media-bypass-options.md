---
title: 'Lync Server 2013: globale Medien Umgehungs Optionen'
description: 'Lync Server 2013: globale Medien Umgehungs Optionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e69a776c13171d74666a202108fa4b5c72e224d0
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554551"
---
# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="6ca97-103">Optionen für die globale medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ca97-103">Global media bypass options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6ca97-104">_**Letztes Änderungsstand des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="6ca97-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ca97-105">In diesem Thema wird davon ausgegangen, dass Sie die medienumgehung für alle Trunks für einen bestimmten Standort oder Dienst, für den Medien die Vermittlungsserver umgehen sollen, bereits für einen Peer (ein PSTN-Gateway (Public Switched Telephone Network), eine IP-Nebenstellenanlage oder einen Session Border Controller (SBC) konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="6ca97-105">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="6ca97-106">Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie die Medienumgehung auch global aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6ca97-106">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="6ca97-107">Globale medienumgehungseinstellungen können entweder angeben, dass die medienumgehung immer für Anrufe an das PSTN versucht wird, oder dass die medienumgehung mithilfe der Zuordnung von Subnetzen zu Netzwerkstandorten und netzwerkregionen verwendet wird – ähnlich wie bei der Anrufsteuerung, einer weiteren erweiterten Sprachfunktion.</span><span class="sxs-lookup"><span data-stu-id="6ca97-107">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="6ca97-108">Wenn medienumgehung und Anrufsteuerung aktiviert sind, werden die netzwerkregion, der Netzwerkstandort und die Subnetzinformationen, die für die Anrufsteuerung angegeben sind, automatisch verwendet, wenn Sie feststellen, ob die medienumgehung eingesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6ca97-108">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="6ca97-109">Dies bedeutet, dass Sie nicht angeben können, dass die medienumgehung immer für Anrufe an das PSTN versucht wird, wenn die Anrufsteuerung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6ca97-109">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="6ca97-110">In diesem Thema wird beschrieben, wie Sie lync Server-Systemsteuerung und lync Server-Verwaltungsshell zusammen verwenden, um die globalen Einstellungen für die medienumgehung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6ca97-110">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6ca97-111">Wenn Sie diese Schritte zum Konfigurieren der Medienumgehung verwenden, wird von einer guten Konnektivität zwischen Clients und dem Vermittlungsserverpeer ausgegangen (z. B. einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SBC beim SIP-Trunking-Anbieter).</span><span class="sxs-lookup"><span data-stu-id="6ca97-111">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="6ca97-112">Wenn für die Verbindung Bandbreiteneinschränkungen gelten, kann die Medienumgehung nicht auf den Anruf angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ca97-112">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="6ca97-113">Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs.</span><span class="sxs-lookup"><span data-stu-id="6ca97-113">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="6ca97-114">Microsoft hat eine Reihe von PSTN-Gateways und SBCS mit zertifizierten Partnern getestet und einige Tests mit Cisco IP-PBX durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6ca97-114">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="6ca97-115">Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – lync Server unter aufgeführt sind <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A> .</span><span class="sxs-lookup"><span data-stu-id="6ca97-115">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="6ca97-116">Nächste Schritte: Auswählen von globalen Einstellungen für die Medienumgehung</span><span class="sxs-lookup"><span data-stu-id="6ca97-116">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="6ca97-117">Nachdem Sie für spezifische Standorte oder Dienste die Medienumgehung für beliebige Trunkverbindungen aktiviert haben, können Sie folgendermaßen fortfahren:</span><span class="sxs-lookup"><span data-stu-id="6ca97-117">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="6ca97-118">Aktivieren Sie die medienumgehung immer, wie unter [configure Media Bypass in lync Server 2013 beschrieben, um die Vermittlungsserver immer zu umgehen](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="6ca97-118">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="6ca97-119">Oder konfigurieren Sie die medienumgehung für die Verwendung von Standort-und Regionsinformationen, wie unter [configure Media Bypass Global Settings in lync Server 2013 to Use Site and Region Information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6ca97-119">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6ca97-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ca97-120">See Also</span></span>


[<span data-ttu-id="6ca97-121">Konfigurieren eines Trunks mit medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ca97-121">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="6ca97-122">Zuordnen eines Subnetzes zu einem Netzwerkstandort in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ca97-122">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="6ca97-123">Konfigurieren der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ca97-123">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="6ca97-124">Medienumgehung und Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6ca97-124">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

