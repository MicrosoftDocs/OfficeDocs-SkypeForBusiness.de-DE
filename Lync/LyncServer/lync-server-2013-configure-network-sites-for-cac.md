---
title: 'Lync Server 2013: Konfigurieren von Netzwerkstandorten für die Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a44d3e25aecb33b6f3969213c682cfa90b7d5a1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="aa052-102">Konfigurieren von Netzwerkstandorten für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aa052-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa052-103">_**Letztes Änderungsstand des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="aa052-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="aa052-104">Wenn Sie bereits Netzwerkstandorte für E9-1-1 oder medienumgehung erstellt haben, können Sie die vorhandenen Netzwerkstandorte so ändern, dass ein bandbreitenrichtlinienprofil mithilfe des Cmdlets " <STRONG>CsNetworkSite</STRONG> " angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="aa052-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="aa052-105">Ein Beispiel für das Ändern eines Netzwerkstandorts finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aa052-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="aa052-106">*Netzwerkstandorte* sind die Büros oder Standorte in den einzelnen netzwerkregionen der Anrufsteuerung (Call Admission Control, CAC), E9-1-1 und Medien Umgehungs Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="aa052-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="aa052-107">Verwenden Sie die folgenden Verfahren, um Netzwerkstandorte zu erstellen, die an Netzwerkstandorten in der Beispiel Netzwerktopologie für die Anrufsteuerung ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="aa052-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="aa052-108">Diese Verfahren zeigen, wie Sie Netzwerkstandorte erstellen und konfigurieren, die von der WAN-Bandbreite abhängig sind, und daher Bandbreitenrichtlinien benötigen, die den Datenfluss in Echtzeit über Audio oder Video begrenzen.</span><span class="sxs-lookup"><span data-stu-id="aa052-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="aa052-109">In der Beispielbereitstellung für die Anrufsteuerung verfügt die Region "Nordamerika" über sechs Standorte.</span><span class="sxs-lookup"><span data-stu-id="aa052-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="aa052-110">Drei dieser Standorte sind von der WAN-Bandbreite eingeschränkt: Reno, Portland und Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="aa052-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="aa052-111">Die anderen drei Standorte, die *nicht* durch WAN-Bandbreite eingeschränkt sind: New York, Chicago und Detroit.</span><span class="sxs-lookup"><span data-stu-id="aa052-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="aa052-112">Ein Beispiel für das Erstellen oder Ändern dieser anderen Netzwerkstandorte finden Sie unter [erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="aa052-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="aa052-113">Informationen zum Anzeigen der Beispiel Netzwerktopologie finden Sie unter [example: Gathering your Requirements for Call Admission Control in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="aa052-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="aa052-114">Im folgenden Verfahren wird lync Server-Verwaltungsshell zum Erstellen eines Netzwerkstandorts verwendet.</span><span class="sxs-lookup"><span data-stu-id="aa052-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="aa052-115">Ausführliche Informationen zur Verwendung von lync Server-Systemsteuerung zum Erstellen eines Netzwerkstandorts finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern eines Netzwerkstandorts in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="aa052-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="aa052-116">So erstellen Sie Netzwerkstandorte für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="aa052-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="aa052-117">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="aa052-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="aa052-118">Führen Sie das Cmdlet **New-CsNetworkSite** aus, um Netzwerkstandorte zu erstellen und ein entsprechendes bandbreitenrichtlinienprofil auf jeden Standort anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="aa052-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="aa052-119">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="aa052-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="aa052-120">Zum Abschließen der Erstellung von Netzwerkstandorten für die gesamte Beispieltopologie wiederholen Sie Schritt 2 für die Netzwerkstandorte mit Bandbreiteneinschränkungen in den Regionen EMEA und APAC.</span><span class="sxs-lookup"><span data-stu-id="aa052-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

