---
title: 'Lync Server 2013: Anzeigen von Routeninformationen für netzwerkregionen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8299bd598edf18b7ed7f06088e4bfbbcebab354
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a><span data-ttu-id="bc1c6-102">Anzeigen von Routeninformationen zu netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc1c6-102">Viewing network region route information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc1c6-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bc1c6-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bc1c6-104">Jede Region innerhalb einer Anruf Steuerungskonfiguration muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="bc1c6-105">Während die Region Links die Bandbreiteneinschränkungen für die Verbindungen zwischen Regionen festlegen und auch die physischen Links darstellen, bestimmt eine Route, welchen verknüpften Pfad die Verbindung von einem Bereich zu einer anderen durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="bc1c6-106">Gehen Sie wie folgt vor, um vorhandene Netzwerkbereichs Routen in der lync Server 2013-Systemsteuerung oder in der lync Server 2013-Verwaltungsshell anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-106">Use the following procedures to view existing network region routes in Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="bc1c6-107">Details zum Erstellen oder Ändern von Netzwerkbereichs Routen finden Sie unter [erstellen oder Ändern von Netzwerkbereichs Routen in lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="bc1c6-107">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a><span data-ttu-id="bc1c6-108">So zeigen Sie netzwerkregion-Routeninformationen in der lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="bc1c6-108">To view network region route information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="bc1c6-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="bc1c6-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bc1c6-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bc1c6-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bc1c6-112">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Route**.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-112">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="bc1c6-113">Klicken Sie auf der Seite **Route des Bereichs** auf die Route, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-113">On the **Region Route** page, click the region route that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bc1c6-114">Sie können jeweils nur eine Regions Route anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-114">You can only view one region route at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="bc1c6-115">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-115">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="bc1c6-116">Anzeigen von Routeninformationen des Netzwerkbereichs mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="bc1c6-116">Viewing Network Region Route Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="bc1c6-117">Netzwerkregion-Routeninformationen können mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkInterRegionRoute angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-117">Network region route information can be viewed by using Windows PowerShell and the Get-CsNetworkInterRegionRoute cmdlet.</span></span> <span data-ttu-id="bc1c6-118">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="bc1c6-119">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-route-information"></a><span data-ttu-id="bc1c6-120">So zeigen Sie netzwerkregion-Routeninformationen an</span><span class="sxs-lookup"><span data-stu-id="bc1c6-120">To view network region route information</span></span>

  - <span data-ttu-id="bc1c6-121">Geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen Routen des Netzwerkbereichs anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="bc1c6-121">To view information about all your network region routes, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkInterRegionRoute
    
    <span data-ttu-id="bc1c6-122">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="bc1c6-122">That will return information similar to this:</span></span>
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

<span data-ttu-id="bc1c6-123">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .</span><span class="sxs-lookup"><span data-stu-id="bc1c6-123">For more information, see the help topic for the [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc1c6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc1c6-124">See Also</span></span>


[<span data-ttu-id="bc1c6-125">Erstellen oder Ändern von Netzwerkbereichs Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc1c6-125">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[<span data-ttu-id="bc1c6-126">Löschen vorhandener Netzwerkbereichs Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc1c6-126">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

