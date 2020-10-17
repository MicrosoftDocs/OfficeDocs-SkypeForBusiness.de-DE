---
title: 'Lync Server 2013: Löschen von Netzwerk Regions Links'
description: 'Lync Server 2013: Löschen von Netzwerk Regions Links.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a17c1ec64460e0f7cb447597f94aadd7fd2a9ca
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545331"
---
# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="e84b9-103">Löschen von Netzwerk Regions Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e84b9-103">Deleting network region links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e84b9-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="e84b9-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="e84b9-105">Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e84b9-105">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="e84b9-106">Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden.</span><span class="sxs-lookup"><span data-stu-id="e84b9-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="e84b9-107">Sie können die lync Server-Systemsteuerung verwenden, um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e84b9-107">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="e84b9-108">Ausführliche Informationen zum Erstellen oder Ändern der Netzwerk Regions Verknüpfung finden Sie unter [Configuring Network Region Links in lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="e84b9-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="e84b9-109">So löschen Sie eine Netzwerkregionenverbindung</span><span class="sxs-lookup"><span data-stu-id="e84b9-109">To delete a network region link</span></span>

1.  <span data-ttu-id="e84b9-110">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="e84b9-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="e84b9-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="e84b9-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="e84b9-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="e84b9-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="e84b9-113">Klicken Sie auf der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="e84b9-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="e84b9-114">Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="e84b9-114">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e84b9-p103">Sie können mehrere Regionenverbindungen in einem Arbeitsschritt löschen. Drücken Sie hierzu die STRG-TASTE, und wählen Sie bei gedrückter STRG-TASTE mehrere Netzwerkregionen aus. Wenn Sie alle Netzwerkregionen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e84b9-p103">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="e84b9-118">Wählen Sie im Menü **Bearbeiten** die Option **Löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="e84b9-118">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="e84b9-119">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e84b9-119">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e84b9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e84b9-120">See Also</span></span>


[<span data-ttu-id="e84b9-121">Konfigurieren von Netzwerk Regions Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e84b9-121">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

