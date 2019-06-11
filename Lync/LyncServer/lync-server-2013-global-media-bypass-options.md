---
title: 'Lync Server 2013: globale Medien Umgehungs Optionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ebe39b6faeffd36f0dfc9e25959fe7a0b356153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832128"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="1f5f7-102">Globale Medien Umgehungs Optionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f5f7-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f5f7-103">_**Letztes Änderungsdatum des Themas:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="1f5f7-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f5f7-104">In diesem Thema wird davon ausgegangen, dass Sie die medienumgehung für alle Trunks an einen Peer (ein öffentliches Switched Telephone Network (PSTN)-Gateway, eine IP-Telefonanlage oder einen Session Border Controller (SBC) bei einem Internet-Telefoniedienst) für eine bestimmte Website oder einen bestimmten Dienst für dem der Vermittlungs Server von Medien umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1f5f7-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="1f5f7-p101">Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zugeordnet sind, müssen Sie die Medienumgehung auch global aktivieren. Über globale Einstellungen für die Medienumgehung können Sie entweder angeben, dass die Medienumgehung auf Anrufe über das Telefonfestnetz immer angewendet wird oder dass die Medienumgehung auf der Grundlage von Zuordnungen von Subnetzen zu Netzwerkstandorten und Netzwerkregionen angewendet wird – ähnlich wie bei der Anrufsteuerung, einer anderen erweiterten VoIP-Funktion. Wenn sowohl die Medienumgehung als auch die Anrufsteuerung aktiviert wurden, werden die Informationen zu Netzwerkregionen, Netzwerkstandorten und Subnetzen, die für die Anrufsteuerung konfiguriert wurden, automatisch für Entscheidungen zur Verwendung der Medienumgehung herangezogen. Dies bedeutet, dass Sie die Medienumgehung nicht auf alle Anrufe über das Telefonfestnetz anwenden können, wenn die Anrufsteuerung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1f5f7-p101">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally. Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature. When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass. This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="1f5f7-109">In diesem Thema wird beschrieben, wie Sie die lync Server-Systemsteuerung und die lync Server-Verwaltungsshell zusammen verwenden, um globale medienumgehungseinstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="1f5f7-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f5f7-110">Wenn Sie diese Schritte zum Konfigurieren der Medienumgehung verwenden, wird von einer guten Konnektivität zwischen Clients und dem Vermittlungsserverpeer ausgegangen (z. B. einem PSTN-Gateway, einer IP-Nebenstellenanlage oder einem SBC beim SIP-Trunkinganbieter).</span><span class="sxs-lookup"><span data-stu-id="1f5f7-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="1f5f7-111">Wenn für die Verbindung Bandbreiteneinschränkungen gelten, kann die Medienumgehung nicht auf den Anruf angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f5f7-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="1f5f7-112">Die Medienumgehung funktioniert nicht mit allen PSTN-Gateways, IP-Nebenstellenanlagen und SBCs.</span><span class="sxs-lookup"><span data-stu-id="1f5f7-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="1f5f7-113">Microsoft hat eine Reihe von PSTN-Gateways und SBCs mit zertifizierten Partnern getestet und einige Tests mit IP-Nebenstellenanlagen von Cisco durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="1f5f7-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="1f5f7-114">Die medienumgehung wird nur mit Produkten und Versionen unterstützt, die unter Unified Communications Open Interoperability Program – <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>lync Server unter aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="1f5f7-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="1f5f7-115">Nächste Schritte: auswählen globaler medienumgehungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="1f5f7-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="1f5f7-116">Nachdem Sie die medienumgehung für alle trunk-Verbindungen zu einem Peer für bestimmte Websites oder Dienste aktiviert haben, verwenden Sie den folgenden Inhalt:</span><span class="sxs-lookup"><span data-stu-id="1f5f7-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="1f5f7-117">Aktivieren Sie die medienumgehung immer, wie unter [Konfigurieren der medienumgehung in lync Server 2013 beschrieben, um den Vermittlungsserver immer zu umgehen](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="1f5f7-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="1f5f7-118">Oder konfigurieren Sie die medienumgehung für die Verwendung von Website-und Regionsinformationen, wie unter [Konfigurieren der globalen Einstellungen für medienumgehung in lync Server 2013 beschrieben, um Website-und Regionsinformationen zu verwenden](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span><span class="sxs-lookup"><span data-stu-id="1f5f7-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1f5f7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f5f7-119">See Also</span></span>


[<span data-ttu-id="1f5f7-120">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f5f7-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="1f5f7-121">Zuordnen eines Subnetzes zu einem Netzwerkstandort in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f5f7-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="1f5f7-122">Konfigurieren der Medienumgehung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f5f7-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="1f5f7-123">Medienumgehung und Vermittlungsserver in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f5f7-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

