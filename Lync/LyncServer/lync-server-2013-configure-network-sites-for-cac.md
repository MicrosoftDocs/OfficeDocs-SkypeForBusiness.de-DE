---
title: 'Lync Server 2013: Konfigurieren von Netzwerk Websites für CAC'
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
ms.openlocfilehash: 0958c74d6f1ce587886b7a8456aee44381c00ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758363"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a><span data-ttu-id="1b4d1-102">Konfigurieren von Netzwerk Websites für CAC in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b4d1-102">Configure network sites for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b4d1-103">_**Letztes Änderungsdatum des Themas:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="1b4d1-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="1b4d1-104">Wenn Sie bereits Netzwerk Websites für E9-1-1 oder Media Bypass erstellt haben, können Sie die vorhandenen Netzwerk Websites so ändern, dass ein bandbreitenrichtlinienprofil mithilfe des Cmdlets " <STRONG>CsNetworkSite</STRONG> " angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-104">If you have already created network sites for E9-1-1 or media bypass, you can modify the existing network sites to apply a bandwidth policy profile by using the <STRONG>Set-CsNetworkSite</STRONG> cmdlet.</span></span> <span data-ttu-id="1b4d1-105">Ein Beispiel für das Ändern einer Netzwerk Website finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-105">For an example of how to modify a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="1b4d1-106">*Netzwerk Websites* sind die Büros oder Standorte innerhalb der einzelnen netzwerkregionen der Anruf Zulassungs Steuerung (CAC), E9-1-1 und Media Bypass-Bereitstellungen.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-106">*Network sites* are the offices or locations within each network region of call admission control (CAC), E9-1-1, and media bypass deployments.</span></span> <span data-ttu-id="1b4d1-107">Führen Sie die folgenden Verfahren aus, um Netzwerk Websites zu erstellen, die in der Beispiel Netzwerktopologie für CAC an Netzwerk Websites ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-107">Use the following procedures to create network sites that align to network sites in the example network topology for CAC.</span></span> <span data-ttu-id="1b4d1-108">In diesen Verfahren wird gezeigt, wie Netzwerk Websites erstellt und konfiguriert werden, die durch WAN-Bandbreite eingeschränkt sind, und daher Bandbreitenrichtlinien erforderlich sind, die den Echt Zeit Durchsatz von Audio-oder Videodaten einschränken.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-108">These procedures show how to create and configure network sites that are constrained by WAN bandwidth and therefore require bandwidth policies that limit real-time audio or video traffic flow.</span></span>

<span data-ttu-id="1b4d1-109">Im Beispiel für die CAC-Bereitstellung verfügt die Region Nordamerika über sechs Websites.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-109">In the example CAC deployment, the North America region has six sites.</span></span> <span data-ttu-id="1b4d1-110">Drei dieser Websites sind durch die WAN-Bandbreite beschränkt: Reno, Portland und Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-110">Three of these sites are constrained by WAN bandwidth: Reno, Portland, and Albuquerque.</span></span> <span data-ttu-id="1b4d1-111">Die anderen drei Websites, die *nicht* von der WAN-Bandbreite abhängig sind: New York, Chicago und Detroit.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-111">The other three sites, which are *not* constrained by WAN bandwidth: New York, Chicago, and Detroit.</span></span> <span data-ttu-id="1b4d1-112">Ein Beispiel zum Erstellen oder Ändern dieser anderen Netzwerk Websites finden Sie unter [erstellen oder Ändern einer Netzwerk Website in lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="1b4d1-112">For an example of how to create or modify those other network sites, see [Create or modify a network site in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).</span></span>

<span data-ttu-id="1b4d1-113">Informationen zum Anzeigen der Beispiel Netzwerktopologie finden Sie unter [Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-113">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="1b4d1-114">Im folgenden Verfahren wird die lync Server-Verwaltungsshell zum Erstellen einer Netzwerk Website verwendet.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-114">In the following procedure, Lync Server Management Shell is used to create a network site.</span></span> <span data-ttu-id="1b4d1-115">Details zur Verwendung der lync Server-Systemsteuerung zum Erstellen einer Netzwerk Website finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-site.md">erstellen oder Ändern einer Netzwerk Website in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-115">For details about using Lync Server Control Panel to create a network site, see <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a><span data-ttu-id="1b4d1-116">So erstellen Sie Netzwerk Websites für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="1b4d1-116">To create network sites for call admission control</span></span>

1.  <span data-ttu-id="1b4d1-117">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1b4d1-118">Führen Sie das Cmdlet **New-CsNetworkSite** aus, um Netzwerk Websites zu erstellen und auf jede Website ein entsprechendes bandbreitenrichtlinienprofil anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-118">Run the **New-CsNetworkSite** cmdlet to create network sites and apply an appropriate bandwidth policy profile to each site.</span></span> <span data-ttu-id="1b4d1-119">Führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1b4d1-119">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  <span data-ttu-id="1b4d1-120">Um das Erstellen von Netzwerk Websites für die gesamte Beispieltopologie abzuschließen, wiederholen Sie Schritt 2 für die Netzwerk Websites mit Bandbreiteneinschränkungen in den Regionen EMEA und APAC.</span><span class="sxs-lookup"><span data-stu-id="1b4d1-120">To finish creating network sites for the entire example topology, repeat step 2 for the bandwidth-constrained network sites in the EMEA and APAC regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

