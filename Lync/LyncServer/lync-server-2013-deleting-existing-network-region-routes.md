---
title: 'Lync Server 2013: Löschen vorhandener Netzwerkbereichs Routen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e188ef3214088fe9c38c144fad1908d13fef162
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832584"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="32244-102">Löschen vorhandener Netzwerkbereichs Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32244-102">Deleting existing network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32244-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="32244-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="32244-104">Jede Region innerhalb einer Anruf Steuerungskonfiguration muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="32244-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="32244-105">Während die Region Links die Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einer anderen durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="32244-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="32244-106">Sie können die lync Server-Systemsteuerung verwenden, um Netzwerkbereichs Routen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="32244-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="32244-107">In der lync Server-Systemsteuerung können Sie eine Netzwerk Regions Route erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="32244-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="32244-108">Verwenden Sie dieses Thema, um vorhandene Netzwerkbereichs Routen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="32244-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="32244-109">Details zum Erstellen oder Ändern von Netzwerkbereichs Routen finden Sie unter [erstellen oder Ändern von Netzwerkbereichs Routen in lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="32244-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="32244-110">So löschen Sie eine Route des Netzwerkbereichs</span><span class="sxs-lookup"><span data-stu-id="32244-110">To delete a network region route</span></span>

1.  <span data-ttu-id="32244-111">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="32244-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="32244-112">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="32244-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="32244-113">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="32244-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="32244-114">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Route**.</span><span class="sxs-lookup"><span data-stu-id="32244-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="32244-115">Klicken Sie auf der Seite **Region Route** auf die Route, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="32244-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32244-116">Sie können mehr als eine Regions Route gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="32244-116">You can delete more than one region route at a time.</span></span> <span data-ttu-id="32244-117">Drücken Sie dazu STRG, und wählen Sie mehrere Bereichs Routen aus, während Sie die STRG-Taste gedrückt halten.</span><span class="sxs-lookup"><span data-stu-id="32244-117">To do this, press CTRL and select multiple region routes while holding down the CTRL key.</span></span> <span data-ttu-id="32244-118">Wenn Sie alle Regions Routen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="32244-118">Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="32244-119">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="32244-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="32244-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="32244-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32244-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32244-121">See Also</span></span>


[<span data-ttu-id="32244-122">Erstellen oder Ändern von Netzwerkbereichs Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32244-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="32244-123">[Konfigurieren einer Netzwerkregionenroute](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="32244-123">[Configure a Network Region Route](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="32244-124">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="32244-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="32244-125">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="32244-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="32244-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="32244-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="32244-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="32244-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

