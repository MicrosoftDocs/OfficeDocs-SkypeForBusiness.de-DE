---
title: 'Lync Server 2013: Aufzeichnung von Anrufdetails aktivieren'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c66c63b4890c011be91236516a15a32c0065a8f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="dd1a8-102">Aktivieren der Aufzeichnung von Anrufdetails in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1a8-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd1a8-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dd1a8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dd1a8-p101">Bei der Aufzeichnung von Kommunikationsdatensätzen werden Nutzungs- und Diagnoseinformationen über Peer-zu-Peer-Aktivitäten aufgezeichnet, z. B. Chat, VoIP-Anrufe (Voice over Internet Protocol), Anwendungsfreigabe, Dateiübertragung und Besprechungen. Anhand der Nutzungsdaten kann die Rendite berechnet werden, und die Diagnosedaten können zur Problembehandlung bei Peer-zu-Peer-Aktivitäten und Besprechungen eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="dd1a8-106">Verwenden Sie das folgende Verfahren, um die Aufzeichnung von Kommunikationsdatensätzen (KDS) in der gesamten Organisation oder für jeden Standort in Ihrer Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd1a8-107">Zur Aktivierung von KDS müssen Sie die Überwachung und eine Überwachungsdatenbank konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="dd1a8-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="dd1a8-109">So aktivieren Sie KDS mit lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="dd1a8-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dd1a8-110">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="dd1a8-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dd1a8-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dd1a8-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dd1a8-113">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **Aufzeichnung von Kommunikationsdatensätzen**.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="dd1a8-114">Klicken Sie auf der Seite **Aufzeichnung von Kommunikationsdatensätzen** in der Tabelle auf den geeigneten Standort, klicken Sie auf **Aktion** und anschließend auf **KDS aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd1a8-115">KDS ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dd1a8-116">Aktivieren von KDS mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="dd1a8-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dd1a8-117">Sie können KDS mit Windows PowerShell und dem Cmdlet " **Set-CsCdrConfiguration** " aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="dd1a8-118">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dd1a8-119">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="dd1a8-120">So aktivieren Sie KDS für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="dd1a8-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="dd1a8-121">Sie können KDS aktivieren, indem Sie den Parameter EnableCDR auf True ($True) setzen.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="dd1a8-122">So deaktivieren Sie KDS für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="dd1a8-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="dd1a8-123">Sie können KDS deaktivieren, indem Sie den Parameter EnableCDR auf False ($False) setzen.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="dd1a8-124">Durch das Deaktivieren von KDS wird die Überwachung nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="dd1a8-125">Es hält die Sammlung und Speicherung von KDS-Daten an.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="dd1a8-126">So verwenden Sie einen einzelnen Befehl zum Aktivieren von KDS an mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="dd1a8-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="dd1a8-127">Mit diesem Befehl wird KDS für alle derzeit in der Organisation verwendeten KDS-Einstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="dd1a8-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="dd1a8-128">Weitere Informationen finden Sie im Hilfethema zum Cmdlet " [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) ".</span><span class="sxs-lookup"><span data-stu-id="dd1a8-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dd1a8-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd1a8-129">See Also</span></span>


[<span data-ttu-id="dd1a8-130">Planen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1a8-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="dd1a8-131">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1a8-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

