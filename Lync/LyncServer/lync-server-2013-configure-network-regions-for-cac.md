---
title: 'Lync Server 2013: Konfigurieren von netzwerkregionen für CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="b14bf-102">Konfigurieren von netzwerkregionen für CAC in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b14bf-102">Configure network regions for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b14bf-103">_**Letztes Änderungsdatum des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="b14bf-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b14bf-104">Wenn Sie bereits netzwerkregionen für E9-1-1 oder Media Bypass erstellt haben, können Sie die vorhandenen netzwerkregionen ändern, indem Sie mithilfe des Cmdlets " <STRONG>festlegen-CsNetworkRegion</STRONG> " spezifische Einstellungen für die Anrufannahme Steuerung (CAC) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b14bf-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="b14bf-105">Ein Beispiel für das Ändern eines Netzwerkbereichs finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b14bf-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="b14bf-106">*Netzwerkregionen* sind die Netzwerkhubs oder Backbones, die bei der Konfiguration von CAC, E9-1-1 und medienumgehung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b14bf-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="b14bf-107">Gehen Sie wie folgt vor, um netzwerkregionen zu erstellen, die in der Beispiel Netzwerktopologie für CAC an netzwerkregionen ausgerichtet sind.</span><span class="sxs-lookup"><span data-stu-id="b14bf-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="b14bf-108">Informationen zum Anzeigen der Beispiel Netzwerktopologie finden Sie unter [Beispiel: Sammeln Ihrer Anforderungen für die Anrufsteuerung in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="b14bf-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="b14bf-109">Die Beispiel Netzwerktopologie für CAC umfasst drei Regionen: Nordamerika, EMEA und APAC.</span><span class="sxs-lookup"><span data-stu-id="b14bf-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="b14bf-110">Jede Region hat eine angegebene zentrale Website.</span><span class="sxs-lookup"><span data-stu-id="b14bf-110">Each region has a specified central site.</span></span> <span data-ttu-id="b14bf-111">Für die Region Nordamerika hat der designierte zentrale Standort den Namen Chicago.</span><span class="sxs-lookup"><span data-stu-id="b14bf-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="b14bf-112">Das folgende Verfahren zeigt ein Beispiel dafür, wie Sie das Cmdlet **New-CsNetworkRegion** zum Erstellen der Region Nordamerika verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b14bf-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b14bf-113">Im folgenden Verfahren wird die lync Server-Verwaltungsshell zum Erstellen eines Netzwerkbereichs verwendet.</span><span class="sxs-lookup"><span data-stu-id="b14bf-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="b14bf-114">Details zur Verwendung der lync Server-Systemsteuerung zum Erstellen eines Netzwerkbereichs finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern eines Netzwerkbereichs in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="b14bf-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="b14bf-115">So erstellen Sie einen Netzwerkbereich für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="b14bf-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="b14bf-116">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="b14bf-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b14bf-117">Führen Sie für jede Region, die Sie erstellen müssen, das Cmdlet **New-CsNetworkRegion** aus.</span><span class="sxs-lookup"><span data-stu-id="b14bf-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="b14bf-118">Wenn Sie beispielsweise die Region Nordamerika erstellen möchten, führen Sie Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="b14bf-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="b14bf-119">Wiederholen Sie Schritt 2, um die netzwerkregionen EMEA und APAC zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b14bf-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

