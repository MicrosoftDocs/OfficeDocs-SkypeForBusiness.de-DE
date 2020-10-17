---
title: 'Lync Server 2013: Löschen vorhandener Netzwerk Regions Routen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f07a0331563c4d78c4e8fc3391b7f8423a2ecc21
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525392"
---
# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="8c06c-102">Löschen vorhandener Netzwerk Regions Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c06c-102">Deleting existing network region routes in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c06c-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="8c06c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="8c06c-104">Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="8c06c-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="8c06c-105">Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt.</span><span class="sxs-lookup"><span data-stu-id="8c06c-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="8c06c-106">Sie können lync Server-Systemsteuerung verwenden, um Netzwerk Regions Routen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="8c06c-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="8c06c-107">In lync Server-Systemsteuerung können Sie eine Netzwerk Regions Route erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="8c06c-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="8c06c-108">In diesem Thema wird beschrieben, wie vorhandene Netzwerkregionenrouten gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="8c06c-108">Use this topic to delete existing network region routes.</span></span> <span data-ttu-id="8c06c-109">Ausführliche Informationen zum Erstellen oder Ändern von Netzwerk Regions Routen finden Sie unter [erstellen oder Ändern von Netzwerk Regions Routen in lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="8c06c-109">For details about creating or modifying network region routes, see [Creating or modifying network region routes in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).</span></span>

<div>

## <a name="to-delete-a-network-region-route"></a><span data-ttu-id="8c06c-110">So löschen Sie eine Netzwerkregionenroute</span><span class="sxs-lookup"><span data-stu-id="8c06c-110">To delete a network region route</span></span>

1.  <span data-ttu-id="8c06c-111">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="8c06c-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8c06c-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8c06c-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8c06c-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8c06c-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8c06c-114">Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenroute**.</span><span class="sxs-lookup"><span data-stu-id="8c06c-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="8c06c-115">Klicken Sie auf der Seite **Regionenroute** auf die Regionenroute, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="8c06c-115">On the **Region Route** page, click the region route that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8c06c-p103">Sie können mehrere Regionenrouten in einem Arbeitsschritt löschen. Wählen Sie dazu mit gedrückter STRG-TASTE mehrere Regionenrouten aus. Wenn Sie alle Regionenrouten auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8c06c-p103">You can delete more than one region route at a time. To do this, press CTRL and select multiple region routes while holding down the CTRL key. Or, to select all region routes, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="8c06c-119">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="8c06c-119">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="8c06c-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8c06c-120">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8c06c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c06c-121">See Also</span></span>


[<span data-ttu-id="8c06c-122">Erstellen oder Ändern von Netzwerk Regions Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c06c-122">Creating or modifying network region routes in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-region-routes.md)  


<span data-ttu-id="8c06c-123">[Konfigurieren einer Netzwerkregionenroute](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="8c06c-123">[Configure a Network Region Route](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))</span></span>  


[<span data-ttu-id="8c06c-124">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8c06c-124">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[<span data-ttu-id="8c06c-125">Gruppe-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8c06c-125">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[<span data-ttu-id="8c06c-126">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8c06c-126">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[<span data-ttu-id="8c06c-127">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="8c06c-127">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

