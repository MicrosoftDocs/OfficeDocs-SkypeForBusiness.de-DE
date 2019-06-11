---
title: 'Lync Server 2013: Anzeigen von Netzwerk Website Informationen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 788440d02a3f41198a870f8419cece4dc8e66900
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a><span data-ttu-id="6c336-102">Anzeigen von Netzwerk Website Informationen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c336-102">Viewing network site information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c336-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="6c336-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="6c336-104">Netzwerk Websites sind die Büros oder Standorte, die in den einzelnen Regionen einer Anrufannahme Steuerung oder erweiterten 9-1-1-Bereitstellung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="6c336-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="6c336-105">Sie können Netzwerk Website Informationen entweder in der lync Server 2013-Systemsteuerung oder in der lync Server-Verwaltungsshell anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6c336-105">You can view network site information in either Lync Server 2013 Control Panel or Lync Server Management Shell .</span></span> <span data-ttu-id="6c336-106">Details zum Erstellen oder Ändern von Netzwerk Websites finden Sie unter [erstellen oder Ändern von Netzwerk Websites in lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="6c336-106">For details about creating or modifying network sites, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a><span data-ttu-id="6c336-107">So zeigen Sie Netzwerk Website Informationen in der lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="6c336-107">To view network site information in Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6c336-108">Melden Sie sich mit einem Benutzerkonto, das Mitglied der Gruppe "RTCUniversalServerAdmins" ist (oder über gleichwertige Benutzerrechte verfügt) oder dem die Rolle "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="6c336-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6c336-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6c336-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6c336-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6c336-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6c336-111">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** , und klicken Sie dann auf **Website**.</span><span class="sxs-lookup"><span data-stu-id="6c336-111">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="6c336-112">Klicken Sie auf der Seite **Website** auf die Website, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="6c336-112">On the **Site** page, click the site that you want to view.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6c336-113">Sie können nur Informationen für eine Website gleichzeitig anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6c336-113">You can only view information for one site at a time.</span></span>

    
    </div>

5.  <span data-ttu-id="6c336-114">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6c336-114">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6c336-115">Anzeigen von Netzwerk Website Informationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="6c336-115">Viewing Network Site Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6c336-116">Sie können Netzwerk Website Informationen mithilfe von Windows PowerShell und dem Cmdlet Get-CsNetworkSite anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6c336-116">You can view network site information by using Windows PowerShell and the Get-CsNetworkSite cmdlet.</span></span> <span data-ttu-id="6c336-117">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6c336-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6c336-118">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="6c336-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-site-information"></a><span data-ttu-id="6c336-119">So zeigen Sie Netzwerk Website Informationen an</span><span class="sxs-lookup"><span data-stu-id="6c336-119">To view network site information</span></span>

  - <span data-ttu-id="6c336-120">Wenn Sie Informationen zu allen Ihren Netzwerk Websites anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="6c336-120">To view information about all your network sites, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkSite
    
    <span data-ttu-id="6c336-121">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="6c336-121">That will return information similar to this:</span></span>
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

<span data-ttu-id="6c336-122">Weitere Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .</span><span class="sxs-lookup"><span data-stu-id="6c336-122">For more information, see the help topic for the [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6c336-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6c336-123">See Also</span></span>


[<span data-ttu-id="6c336-124">Erstellen oder Ändern von Netzwerk Websites in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c336-124">Creating or modifying network sites in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-sites.md)  
[<span data-ttu-id="6c336-125">Löschen einer vorhandenen Netzwerk Website in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c336-125">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

