---
title: 'Lync Server 2013: Erstellen oder Ändern von Netzwerk Regions Routen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32c5f3cdd8000892886b3273fbb33fc1b1f668e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a><span data-ttu-id="f897a-102">Erstellen oder Ändern von Netzwerk Regions Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f897a-102">Creating or modifying network region routes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f897a-103">_**Letztes Änderungsstand des Themas:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="f897a-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="f897a-104">Jede Region mit konfiguriertem Anrufsteuerungsdienst muss über eine Möglichkeit verfügen, auf jede andere Region zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f897a-104">Every region within a call admission control (CAC) configuration must have some way to access every other region.</span></span> <span data-ttu-id="f897a-105">Während die Regionenverbindungen Bandbreiteneinschränkungen für Verbindungen zwischen Regionen festlegen und auch die physischen Verbindungen darstellen, bestimmt eine Route, welchen Pfad die Verbindung von einer Region zur anderen nimmt.</span><span class="sxs-lookup"><span data-stu-id="f897a-105">While region links set bandwidth limitations on the connections between regions and also represent the physical links, a route determines which linked path the connection will traverse from one region to another.</span></span> <span data-ttu-id="f897a-106">Sie können lync Server-Systemsteuerung verwenden, um Netzwerk Regions Routen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f897a-106">You can use Lync Server Control Panel to configure network region routes.</span></span> <span data-ttu-id="f897a-107">In lync Server-Systemsteuerung können Sie eine Netzwerk Regions Route erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="f897a-107">From Lync Server Control Panel, you can create, modify, or delete a network region route.</span></span> <span data-ttu-id="f897a-108">Verwenden Sie dieses Thema, um eine Netzwerk Regions Route zu erstellen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f897a-108">Use this topic to create or modify a network region route.</span></span> <span data-ttu-id="f897a-109">Ausführliche Informationen zum Löschen einer vorhandenen Netzwerk Regions Routen finden Sie unter [Löschen vorhandener Netzwerk Regions Routen in lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span><span class="sxs-lookup"><span data-stu-id="f897a-109">For details about deleting an existing network region routes, see [Deleting existing network region routes in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).</span></span>

<div>

## <a name="to-create-a-network-region-route"></a><span data-ttu-id="f897a-110">So erstellen Sie eine Netzwerkregionenroute</span><span class="sxs-lookup"><span data-stu-id="f897a-110">To create a network region route</span></span>

1.  <span data-ttu-id="f897a-111">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f897a-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f897a-112">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f897a-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f897a-113">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f897a-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f897a-114">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenroute**.</span><span class="sxs-lookup"><span data-stu-id="f897a-114">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="f897a-115">Klicken Sie auf der Seite **Regionenroute** auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="f897a-115">On the **Region Route** page, click **New**.</span></span>

5.  <span data-ttu-id="f897a-116">Geben Sie im Abschnitt **Neue Regionenroute** im Feld **Name** einen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="f897a-116">In **New Region Route**, type a value in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f897a-117">Dieser Wert muss innerhalb Ihrer Microsoft lync Server 2013-Bereitstellung eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="f897a-117">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="f897a-118">Wählen Sie in der Dropdownliste **netzwerkregion \#1** eine der zwei Regionen aus, die über diese Route verbunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f897a-118">From the **Network region \#1** drop-down list, select one of the two regions to be connected by this route.</span></span>

7.  <span data-ttu-id="f897a-119">Wählen Sie in der Dropdownliste **netzwerkregion \#2** den anderen Bereich für diese Route aus.</span><span class="sxs-lookup"><span data-stu-id="f897a-119">From the **Network region \#2** drop-down list, select the other region for this route.</span></span> <span data-ttu-id="f897a-120">Diese Region muss sich von der für die netzwerkregion \#1 ausgewählten Region unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="f897a-120">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="f897a-p104">Fügen Sie der Route über das Listenfeld **Netzwerkregionenverbindungen** Regionenverbindungen hinzu. Klicken Sie auf die Schaltfläche **Hinzufügen**, um die Seite **Regionenverbindung** anzuzeigen. Klicken Sie auf eine Regionenverbindung, die Sie dieser Route hinzufügen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="f897a-p104">Use the **Network region links** list box to add region links to the route. Click the **Add** button to display the **Region Link** page. Click a region link to add to this route, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f897a-124">Klicken Sie erneut auf die Schaltfläche <STRONG>Hinzufügen</STRONG>, um weitere Verbindungen hinzuzufügen, oder wählen Sie eine Verbindung aus, und klicken Sie auf <STRONG>Entfernen</STRONG>, um eine Verbindung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="f897a-124">Continue to click the <STRONG>Add</STRONG> button to add more links, or select a link and click <STRONG>Remove</STRONG> to remove a link.</span></span>

    
    </div>

9.  <span data-ttu-id="f897a-125">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f897a-125">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-network-region-route"></a><span data-ttu-id="f897a-126">So ändern Sie eine Netzwerkregionenroute</span><span class="sxs-lookup"><span data-stu-id="f897a-126">To modify a network region route</span></span>

1.  <span data-ttu-id="f897a-127">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f897a-127">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f897a-128">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f897a-128">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f897a-129">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f897a-129">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f897a-130">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenroute**.</span><span class="sxs-lookup"><span data-stu-id="f897a-130">In the left navigation bar, click **Network Configuration** and then click **Region Route**.</span></span>

4.  <span data-ttu-id="f897a-131">Klicken Sie auf der Seite **Regionenroute** auf die Regionenroute, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="f897a-131">On the **Region Route** page, click the region route that you want to modify.</span></span>

5.  <span data-ttu-id="f897a-132">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="f897a-132">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f897a-133">In **Regionenroute bearbeiten** können Sie die über diese Route verbundenen Regionen und die der Route zugeordneten Regionenverbindungen ändern.</span><span class="sxs-lookup"><span data-stu-id="f897a-133">In **Edit Region Route**, you can modify the regions joined by this route and the region links associated with the route.</span></span>

7.  <span data-ttu-id="f897a-134">Klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f897a-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f897a-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f897a-135">See Also</span></span>


[<span data-ttu-id="f897a-136">Löschen vorhandener Netzwerk Regions Routen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f897a-136">Deleting existing network region routes in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

