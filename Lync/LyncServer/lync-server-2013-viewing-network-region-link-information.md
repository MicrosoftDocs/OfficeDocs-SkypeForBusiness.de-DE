---
title: 'Lync Server 2013: Anzeigen von Verbindungsinformationen zu netzwerkregionen'
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
ms.openlocfilehash: 935d1a98bd4f446ec8861ae8382eb724611a945f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757279"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a><span data-ttu-id="2ac3f-102">Anzeigen von Link Informationen zu netzwerkregionen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ac3f-102">Viewing network region link information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ac3f-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2ac3f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2ac3f-104">Sie können die Verknüpfungen zwischen zwei netzwerkregionen im Rahmen der Anrufsteuerung (Call Admission Control, CAC) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-104">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="2ac3f-105">Regionen in einem Netzwerk sind über die physische WAN-Konnektivität (Wide Area Network) verbunden.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-105">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="2ac3f-106">Sie können die lync Server-Systemsteuerung verwenden, um eine vorhandene Verknüpfung zwischen zwei netzwerkregionen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-106">You can use the Lync Server Control Panel to view an existing link between two network regions.</span></span> <span data-ttu-id="2ac3f-107">Details zum Erstellen oder Ändern von Netzwerk Regions Verknüpfungen finden Sie unter [Konfigurieren von Netzwerkbereichs Links in lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span><span class="sxs-lookup"><span data-stu-id="2ac3f-107">For details about creating or modifying network region link, see [Configuring network region links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).</span></span>

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a><span data-ttu-id="2ac3f-108">So zeigen Sie einen Link zum Netzwerkbereich in der lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="2ac3f-108">To view a network region link in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2ac3f-109">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2ac3f-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2ac3f-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2ac3f-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2ac3f-112">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Regions Link**.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-112">In the left navigation bar, click **Network Configuration** and then click **Region Link**.</span></span>

4.  <span data-ttu-id="2ac3f-113">Klicken Sie auf der Seite **Regions Link** auf den Link Region, den Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-113">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2ac3f-114">Sie können nur Informationen zu einem Regions Link gleichzeitig anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-114">You can only view information about one region link at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="2ac3f-115">Wählen Sie im Menü **Bearbeiten** die Option **Details anzeigen**aus.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-115">From the **Edit** menu, select **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2ac3f-116">Anzeigen von Link Informationen zu netzwerkregionen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="2ac3f-116">Viewing Network Region Link Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2ac3f-117">Sie können Netzwerk Regions Verknüpfungen mithilfe von Windows PowerShell und dem Cmdlet **Get-CsNetworkRegionLink** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-117">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="2ac3f-118">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-118">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2ac3f-119">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="2ac3f-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-region-link-information"></a><span data-ttu-id="2ac3f-120">So zeigen Sie netzwerkregion-Verknüpfungsinformationen an</span><span class="sxs-lookup"><span data-stu-id="2ac3f-120">To view network region link information</span></span>

  - <span data-ttu-id="2ac3f-121">Wenn Sie Informationen zu allen ihren netzwerkregion-Links anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="2ac3f-121">To view information about all your network region links, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="2ac3f-122">Mit diesem Befehl werden Informationen ähnlich der folgenden zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="2ac3f-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

<span data-ttu-id="2ac3f-123">Ausführliche Informationen finden Sie unter [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="2ac3f-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2ac3f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ac3f-124">See Also</span></span>


[<span data-ttu-id="2ac3f-125">Konfigurieren von Netzwerkstandort Links in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ac3f-125">Configuring network site links in Lync Server 2013</span></span>](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

