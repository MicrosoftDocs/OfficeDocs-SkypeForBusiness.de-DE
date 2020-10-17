---
title: 'Lync Server 2013: Löschen vorhandener netzwerkregionen'
description: 'Lync Server 2013: Löschen vorhandener netzwerkregionen.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network regions
ms:assetid: c7293a2f-2b49-4c4a-903f-f7edcea2bc5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721882(v=OCS.15)
ms:contentKeyID: 49733815
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b148f0bd92ad398ab7057a5a291bf3245df3e47e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552671"
---
# <a name="deleting-existing-network-regions-in-lync-server-2013"></a><span data-ttu-id="d4e7b-103">Löschen vorhandener netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4e7b-103">Deleting existing network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4e7b-104">_**Letztes Änderungsstand des Themas:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="d4e7b-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="d4e7b-105">Eine Netzwerkregion verbindet verschiedene Teile eines Netzwerks, das sich über verschiedene geografische Bereiche erstreckt.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-105">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d4e7b-106">Jede Netzwerkregion muss einem zentralen Standort zugeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-106">Every network region must be associated with a central site.</span></span> <span data-ttu-id="d4e7b-107">Der zentrale Standort ist der Rechenzentrumsstandort, an dem der Bandbreitenrichtliniendienst für die Anrufsteuerung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-107">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="d4e7b-108">Sie können lync Server-Systemsteuerung zum Konfigurieren von netzwerkregionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-108">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="d4e7b-109">Netzwerkregionen umfassen Einstellungen, mit denen definiert wird, ob für Audio- und Videoverbindungen alternative Pfade über das Internet zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-109">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="d4e7b-110">Im lync Server-Systemsteuerung können Sie eine netzwerkregion erstellen, ändern oder löschen.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-110">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="d4e7b-111">Verwenden Sie dieses Thema, um vorhandene netzwerkregionen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-111">Use this topic to delete existing network regions.</span></span> <span data-ttu-id="d4e7b-112">Ausführliche Informationen zum Erstellen oder Ändern vorhandener netzwerkregionen finden Sie unter [erstellen oder Ändern von netzwerkregionen in lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="d4e7b-112">For details about creating or modifying existing network regions, see [Creating or modifying network regions in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).</span></span>

<div>

## <a name="to-delete-a-network-region"></a><span data-ttu-id="d4e7b-113">So löschen Sie eine netzwerkregion</span><span class="sxs-lookup"><span data-stu-id="d4e7b-113">To delete a network region</span></span>

1.  <span data-ttu-id="d4e7b-114">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4e7b-115">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4e7b-116">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d4e7b-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4e7b-117">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Region**.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-117">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="d4e7b-118">Klicken Sie auf der Seite **Region** auf die Region, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-118">On the **Region** page, click the region you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d4e7b-119">Sie können mehr als eine Region gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-119">You can delete more than one region at a time.</span></span> <span data-ttu-id="d4e7b-120">Drücken Sie dazu STRG, und wählen Sie bei gedrückter STRG-Taste mehrere Regionen aus.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-120">To do this, press CTRL and select multiple regions while holding down the CTRL key.</span></span> <span data-ttu-id="d4e7b-121">Wenn Sie alle Regionen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d4e7b-121">Or, to select all regions, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="d4e7b-122">Klicken Sie im Menü **Bearbeiten** auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-122">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="d4e7b-123">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-123">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="d4e7b-124">Eine netzwerkregion kann nicht entfernt werden, wenn Sie einem Netzwerkstandort zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-124">A network region cannot be removed if it is associated with a network site.</span></span> <span data-ttu-id="d4e7b-125">Wenn Sie versuchen, eine Region zu entfernen, die einer Website zugeordnet ist, wird eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d4e7b-125">If you attempt to remove a region associated with a site you will receive an error message.</span></span> <span data-ttu-id="d4e7b-126">Wenn Sie sehen möchten, ob eine Region einem Standort zugeordnet ist, wählen Sie die Region aus, und klicken Sie dann im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Details anzeigen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="d4e7b-126">To see if a region is associated with any sites, select the region and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4e7b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4e7b-127">See Also</span></span>


[<span data-ttu-id="d4e7b-128">Erstellen oder Ändern von netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4e7b-128">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

