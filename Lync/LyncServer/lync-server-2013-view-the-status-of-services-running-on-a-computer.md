---
title: 'Lync Server 2013: Anzeigen des Status von Diensten, die auf einem Computer betrieben werden'
description: 'Lync Server 2013: zeigt den Status von Diensten an, die auf einem Computer installiert sind.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 22aeb13f2beb5d3b0ee5eec8109eceeb14e40213
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571351"
---
# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="f719c-103">Anzeigen des Status von auf einem Computer ausgeführten Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f719c-103">View the status of services running on a computer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f719c-104">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="f719c-104">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="f719c-105">Sie können lync Server 2013 Systemsteuerung verwenden, um alle Dienste anzuzeigen, die auf einem bestimmten Computer in ihrer lync Server-Topologie verwendet werden, und den Status jedes Diensts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f719c-105">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="f719c-106">So zeigen Sie den Status von auf einem Computer ausgeführten Diensten an</span><span class="sxs-lookup"><span data-stu-id="f719c-106">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="f719c-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="f719c-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f719c-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f719c-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f719c-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f719c-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f719c-110">Klicken Sie auf der linken Navigationsleiste auf **Topologie**.</span><span class="sxs-lookup"><span data-stu-id="f719c-110">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="f719c-111">Sortieren oder Durchsuchen Sie die Liste auf der Seite **Status** nach Bedarf, um nach dem Computer zu suchen, den Sie interessieren, und klicken Sie dann auf den Computernamen.</span><span class="sxs-lookup"><span data-stu-id="f719c-111">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="f719c-112">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f719c-112">Do any of the following:</span></span>
    
      - <span data-ttu-id="f719c-113">Wenn Sie den aktuellen Status der auf dem Computer ausgeführten Dienste anzeigen möchten, klicken Sie auf **Dienststatus abrufen**.</span><span class="sxs-lookup"><span data-stu-id="f719c-113">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="f719c-114">Wenn Sie eine Liste der auf dem Computer ausgeführten Dienste und den Status jedes Diensts anzeigen möchten, klicken Sie auf **Eigenschaften**und dann auf **Schließen** , um zur Liste zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="f719c-114">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f719c-115">Anzeigen des Dienst Status mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f719c-115">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f719c-116">Sie können auch den Dienststatus anzeigen, indem Sie Windows PowerShell und das Cmdlet **Get-CsWindowsService** verwenden.</span><span class="sxs-lookup"><span data-stu-id="f719c-116">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="f719c-117">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="f719c-117">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f719c-118">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="f719c-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="f719c-119">So zeigen Sie den Dienststatus an</span><span class="sxs-lookup"><span data-stu-id="f719c-119">To view service status</span></span>

  - <span data-ttu-id="f719c-120">Wenn Sie den Dienststatus auf einem Computer anzeigen möchten, geben Sie einen Befehl wie den folgenden in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="f719c-120">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="f719c-121">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="f719c-121">This command returns information similar to the following:</span></span>
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

<span data-ttu-id="f719c-122">Ausführliche Informationen finden Sie unter [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span><span class="sxs-lookup"><span data-stu-id="f719c-122">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f719c-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f719c-123">See Also</span></span>


[<span data-ttu-id="f719c-124">Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f719c-124">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

