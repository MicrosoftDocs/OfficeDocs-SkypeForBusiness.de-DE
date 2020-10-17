---
title: 'Lync Server 2013: Anzeigen von Informationen zur Netzwerk Regions Verbindung'
description: 'Lync Server 2013: Anzeigen von Link Informationen zur netzwerkregion.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0134ded9942ebda91050c1f7b0bbcfef018451a3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565361"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="1b161-103">Anzeigen von Link Informationen zu netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b161-103">Viewing network region link information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b161-104">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1b161-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1b161-105">Sie können im Rahmen der Anrufsteuerung Verbindungen zwischen zwei Netzwerkregionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1b161-105">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="1b161-106">Regionen in einem Netzwerk sind über eine physische WAN-Verbindung (Wide Area Network, Fernnetz) verbunden.</span><span class="sxs-lookup"><span data-stu-id="1b161-106">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="1b161-107">Sie können die lync Server-Systemsteuerung verwenden, um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1b161-107">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="1b161-108">Ausführliche Informationen zum Erstellen oder Ändern der Netzwerk Regions Verknüpfung finden Sie unter [Configuring Network Region Links in lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="1b161-108">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="1b161-109">So zeigen Sie einen Link zur netzwerkregion in lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="1b161-109">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1b161-110">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="1b161-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1b161-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="1b161-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1b161-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1b161-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1b161-113">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regionenverbindung**.</span><span class="sxs-lookup"><span data-stu-id="1b161-113">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="1b161-114">Klicken Sie auf der Seite **Regionenverbindung** auf die Regionenverbindung, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="1b161-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b161-115">Es können in einem Arbeitsschritt nur Informationen zu einer Regionenverbindung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1b161-115">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="1b161-116">Wählen Sie im Menü **Bearbeiten** die Option **Details anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="1b161-116">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1b161-117">Anzeigen von Link Informationen zu netzwerkregionen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="1b161-117">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1b161-118">Sie können Links zu netzwerkregionen mit Windows PowerShell und dem Cmdlet **Get-CsNetworkRegionLink** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1b161-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="1b161-119">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="1b161-119">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1b161-120">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="1b161-120">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="1b161-121">So zeigen Sie die Informationen zu einer Netzwerkregionenverbindung an</span><span class="sxs-lookup"><span data-stu-id="1b161-121">To view network region link information</span></span>

  - <span data-ttu-id="1b161-122">Geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE, um Informationen zu allen ihren netzwerkregionen-Links anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="1b161-122">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="1b161-123">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="1b161-123">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="1b161-124">Für weitere Informationen, siehe [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="1b161-124">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1b161-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b161-125">See Also</span></span>


[<span data-ttu-id="1b161-126">Konfigurieren von Netzwerkstandort Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b161-126">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

