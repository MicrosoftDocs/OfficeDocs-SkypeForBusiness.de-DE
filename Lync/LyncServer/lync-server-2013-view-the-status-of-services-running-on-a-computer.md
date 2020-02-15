---
title: 'Lync Server 2013: Anzeigen des Status von Diensten, die auf einem Computer betrieben werden'
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
ms.openlocfilehash: b2745263bc4a179c9d99bf525aebe72b0cf299e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036415"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="31055-102">Anzeigen des Status von auf einem Computer ausgeführten Diensten in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31055-102">View the status of services running on a computer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31055-103">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="31055-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="31055-104">Sie können lync Server 2013 Systemsteuerung verwenden, um alle Dienste anzuzeigen, die auf einem bestimmten Computer in ihrer lync Server-Topologie verwendet werden, und den Status jedes Diensts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="31055-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="31055-105">So zeigen Sie den Status von auf einem Computer ausgeführten Diensten an</span><span class="sxs-lookup"><span data-stu-id="31055-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="31055-106">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="31055-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="31055-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="31055-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="31055-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="31055-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="31055-109">Klicken Sie auf der linken Navigationsleiste auf **Topologie**.</span><span class="sxs-lookup"><span data-stu-id="31055-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="31055-110">Sortieren oder Durchsuchen Sie die Liste auf der Seite **Status** nach Bedarf, um nach dem Computer zu suchen, den Sie interessieren, und klicken Sie dann auf den Computernamen.</span><span class="sxs-lookup"><span data-stu-id="31055-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="31055-111">Führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="31055-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="31055-112">Wenn Sie den aktuellen Status der auf dem Computer ausgeführten Dienste anzeigen möchten, klicken Sie auf **Dienststatus abrufen**.</span><span class="sxs-lookup"><span data-stu-id="31055-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="31055-113">Wenn Sie eine Liste der auf dem Computer ausgeführten Dienste und den Status jedes Diensts anzeigen möchten, klicken Sie auf **Eigenschaften**und dann auf **Schließen** , um zur Liste zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="31055-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="31055-114">Anzeigen des Dienst Status mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="31055-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="31055-115">Sie können auch den Dienststatus anzeigen, indem Sie Windows PowerShell und das Cmdlet **Get-CsWindowsService** verwenden.</span><span class="sxs-lookup"><span data-stu-id="31055-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="31055-116">Sie können dieses Cmdlet in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="31055-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="31055-117">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="31055-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="31055-118">So zeigen Sie den Dienststatus an</span><span class="sxs-lookup"><span data-stu-id="31055-118">To view service status</span></span>

  - <span data-ttu-id="31055-119">Wenn Sie den Dienststatus auf einem Computer anzeigen möchten, geben Sie einen Befehl wie den folgenden in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="31055-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="31055-120">Mit diesem Befehl werden Informationen nach folgendem Muster zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="31055-120">This command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="31055-121">Ausführliche Informationen finden Sie unter [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span><span class="sxs-lookup"><span data-stu-id="31055-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="31055-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="31055-122">See Also</span></span>


[<span data-ttu-id="31055-123">Verwalten von Geräten, Telefonen und Clientanwendungen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31055-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

