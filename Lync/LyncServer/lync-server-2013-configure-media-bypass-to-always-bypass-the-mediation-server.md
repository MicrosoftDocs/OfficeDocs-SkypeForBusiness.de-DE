---
title: 'Lync Server 2013: Konfigurieren Sie die medienumgehung so, dass die Vermittlungsserver immer umgangen wird.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76cf44ee24c94b4a243fe84db1f3bbf7a28ba2e2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="cda6e-102">Konfigurieren der medienumgehung in lync Server 2013, um die Vermittlungsserver immer zu umgehen</span><span class="sxs-lookup"><span data-stu-id="cda6e-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cda6e-103">_**Letztes Änderungsstand des Themas:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="cda6e-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cda6e-104">In diesem Thema wird davon ausgegangen, dass Sie die Medienumgehung für Trunkverbindungen mit einem Peer (PSTN-Gateway, IP-Nebenstellenanlage oder Session Border Controller [SBC] des Anbieters von Internettelefoniediensten [Internet Telephony Service Provider, ITSP]) bereits für einen bestimmten Standort oder Dienst konfiguriert haben, für den die Medienverarbeitung durch den Vermittlungsserver umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="cda6e-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="cda6e-105">Sie können keine dauerhafte Umgehung der Mediendatenverarbeitung durch den Vermittlungsserver konfigurieren, wenn Sie gleichzeitig die Anrufsteuerung (Call Admission Control, CAC) aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cda6e-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="cda6e-106">Diese Einstellungen sind nicht kompatibel und sind daher gegenseitig ausschließende Einstellungen in der Benutzeroberfläche von lync Server-Systemsteuerung.</span><span class="sxs-lookup"><span data-stu-id="cda6e-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="cda6e-107">Zusätzlich zur Aktivierung der Medienumgehung für einzelne Trunkverbindungen, die einem Peer zum Vermittlungsserver zugeordnet sind, müssen Sie auch die globalen Einstellungen für die Medienumgehung konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="cda6e-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="cda6e-108">Wenn Sie die Schritte in diesem Thema zum Konfigurieren globaler Einstellungen für die medienumgehung verwenden, wird davon ausgegangen, dass Sie über eine gute Verbindung zwischen lync-Endpunkten und allen Peers verfügen, für die Sie die medienumgehung für die trunkverbindung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="cda6e-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="cda6e-109">Wenn Sie keine gute Verbindung zwischen lync Server Endpunkten und allen Peers mit dem Vermittlungsserver haben, dessen zugehörige trunk Verbindungen für die medienumgehung aktiviert wurden, müssen Sie die globalen Einstellungen für die medienumgehung so konfigurieren, dass Standort-und Regionsinformationen verwendet werden, wenn Verwenden der medienumgehung</span><span class="sxs-lookup"><span data-stu-id="cda6e-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="cda6e-110">Auf diese Weise kann die Umgehung der Mediendatenverarbeitung durch den Vermittlungsserver besser gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="cda6e-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="cda6e-111">Verwenden Sie dazu die Schritte unter [configure Media Bypass Global Settings in lync Server 2013, um Standort-und Regionsinformationen zu verwenden](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) und [ein Subnetz einem Netzwerkstandort in lync Server 2013 zuzuordnen](lync-server-2013-associate-a-subnet-with-a-network-site.md) .</span><span class="sxs-lookup"><span data-stu-id="cda6e-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="cda6e-112">So aktivieren Sie die Medienumgehung global zur dauerhaften Umgehung des Vermittlungsservers</span><span class="sxs-lookup"><span data-stu-id="cda6e-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="cda6e-113">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cda6e-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cda6e-114">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cda6e-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="cda6e-115">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="cda6e-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="cda6e-116">Doppelklicken Sie in der Liste auf die Konfiguration **Global**.</span><span class="sxs-lookup"><span data-stu-id="cda6e-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="cda6e-117">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Medienumgehung aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="cda6e-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="cda6e-118">Klicken Sie auf **Immer umgehen**.</span><span class="sxs-lookup"><span data-stu-id="cda6e-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="cda6e-119">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="cda6e-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cda6e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cda6e-120">See Also</span></span>


[<span data-ttu-id="cda6e-121">Konfigurieren der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cda6e-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="cda6e-122">Optionen für die globale medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cda6e-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="cda6e-123">Medienumgehung und Vermittlungsserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cda6e-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="cda6e-124">Planen der medienumgehung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cda6e-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

