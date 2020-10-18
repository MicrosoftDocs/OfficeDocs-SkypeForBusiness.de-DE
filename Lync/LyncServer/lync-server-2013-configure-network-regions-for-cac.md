---
title: 'Lync Server 2013: Konfigurieren von netzwerkregionen für die Anrufsteuerung'
description: 'Lync Server 2013: Konfigurieren von netzwerkregionen für die Anrufsteuerung.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f016e0c943963ea4ce9739bd486c6996da502e73
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577561"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="19ea5-103">Konfigurieren von netzwerkregionen für die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19ea5-103">Configure network regions for CAC in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19ea5-104">_**Letztes Änderungsstand des Themas:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="19ea5-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="19ea5-105">Wenn Sie bereits Netzwerkregionen für E9-1-1 oder die Medienumgehung erstellt haben, können Sie diesen Netzwerkregionen mithilfe des <STRONG>Set-CsNetworkRegion</STRONG>-Cmdlets Einstellungen für die Anrufsteuerung (Call Admission Control, CAC) hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="19ea5-105">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="19ea5-106">Ein Beispiel für das Ändern einer netzwerkregion finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern einer netzwerkregion in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="19ea5-106">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="19ea5-107">Bei einer *Netzwerkregion* handelt es sich um den Netzwerkhub oder Netzwerkbackbone, der in der Konfiguration von Anrufsteuerung, E9-1-1 und Medienumgehung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="19ea5-107">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="19ea5-108">Erstellen Sie mithilfe des folgenden Verfahrens Netzwerkregionen gemäß denen in der Beispielnetzwerktopologie für die Anrufsteuerung.</span><span class="sxs-lookup"><span data-stu-id="19ea5-108">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="19ea5-109">Informationen zum Anzeigen der Beispiel Netzwerktopologie finden Sie unter [example: Gathering your Requirements for Call Admission Control in lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="19ea5-109">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="19ea5-110">Die Beispielnetzwerktopologie für die Anrufsteuerung umfasst drei Regionen: Nordamerika, EMEA und APAC.</span><span class="sxs-lookup"><span data-stu-id="19ea5-110">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="19ea5-111">Jede Region verfügt über einen eigenen zentralen Standort.</span><span class="sxs-lookup"><span data-stu-id="19ea5-111">Each region has a specified central site.</span></span> <span data-ttu-id="19ea5-112">Der Name des zentralen Standorts in der Region "North America" lautet CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="19ea5-112">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="19ea5-113">Das folgende Beispiel zeigt, wie Sie die Region "North America" mithilfe des **New-CsNetworkRegion**-Cmdlets erstellen können.</span><span class="sxs-lookup"><span data-stu-id="19ea5-113">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19ea5-114">Im folgenden Verfahren wird lync Server-Verwaltungsshell verwendet, um eine netzwerkregion zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="19ea5-114">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="19ea5-115">Ausführliche Informationen zur Verwendung lync Server-Systemsteuerung zum Erstellen einer netzwerkregion finden Sie unter <A href="lync-server-2013-create-or-modify-a-network-region.md">erstellen oder Ändern einer netzwerkregion in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="19ea5-115">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="19ea5-116">So erstellen Sie eine Netzwerkregion für die Anrufsteuerung</span><span class="sxs-lookup"><span data-stu-id="19ea5-116">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="19ea5-117">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="19ea5-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="19ea5-118">Führen Sie für jede Region, die Sie erstellen möchten, das **New-CsNetworkRegion**-Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="19ea5-118">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="19ea5-119">Zum Erstellen der Region "North America" führen Sie beispielsweise den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="19ea5-119">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="19ea5-120">Wiederholen Sie Schritt 2, um die Netzwerkregionen "EMEA" und "APAC" zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="19ea5-120">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

