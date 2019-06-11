---
title: 'Lync Server 2013: Löschen von Netzwerk Regions Verknüpfungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a097626f6e5eb5de8e3503baab0f1ab9ce462549
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a><span data-ttu-id="44dc3-102">Löschen von Netzwerkbereichs Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44dc3-102">Deleting network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44dc3-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="44dc3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="44dc3-104">Sie können Verknüpfungen zwischen zwei netzwerkregionen als Teil der Anrufsteuerung (Call Admission Control, CAC) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="44dc3-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="44dc3-105">Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden.</span><span class="sxs-lookup"><span data-stu-id="44dc3-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="44dc3-106">Sie können die lync Server-Systemsteuerung verwenden, um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen zu löschen.</span><span class="sxs-lookup"><span data-stu-id="44dc3-106">You can use the Lync Server Control Panel to delete an existing link between two network regions.</span></span> <span data-ttu-id="44dc3-107">Details zum Erstellen oder Ändern von Netzwerk Regions Verknüpfungen finden Sie unter [Konfigurieren von Netzwerkbereichs Links in lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span><span class="sxs-lookup"><span data-stu-id="44dc3-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md)</span></span>

<div>

## <a name="to-delete-a-network-region-link"></a><span data-ttu-id="44dc3-108">So löschen Sie eine Netzwerk Regions Verknüpfung</span><span class="sxs-lookup"><span data-stu-id="44dc3-108">To delete a network region link</span></span>

1.  <span data-ttu-id="44dc3-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="44dc3-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="44dc3-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="44dc3-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="44dc3-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="44dc3-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="44dc3-112">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Link**.</span><span class="sxs-lookup"><span data-stu-id="44dc3-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="44dc3-113">Klicken Sie auf der Seite **Regions Link** auf den zu löschenden Regions Link.</span><span class="sxs-lookup"><span data-stu-id="44dc3-113">On the **Region Link** page, click the region link that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="44dc3-114">Sie können mehrere Regions Verknüpfungen gleichzeitig löschen.</span><span class="sxs-lookup"><span data-stu-id="44dc3-114">You can delete more than one region link at a time.</span></span> <span data-ttu-id="44dc3-115">Drücken Sie dazu STRG, und wählen Sie bei gedrückter STRG-Taste mehrere Regions Links aus.</span><span class="sxs-lookup"><span data-stu-id="44dc3-115">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="44dc3-116">Wenn Sie alle Regions Verknüpfungen auswählen möchten, klicken Sie im Menü <STRONG>Bearbeiten</STRONG> auf <STRONG>Alle auswählen</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="44dc3-116">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="44dc3-117">Wählen Sie im Menü **Bearbeiten** die Option **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="44dc3-117">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="44dc3-118">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="44dc3-118">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="44dc3-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44dc3-119">See Also</span></span>


[<span data-ttu-id="44dc3-120">Konfigurieren von Netzwerkbereichs Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44dc3-120">Configuring network region links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

