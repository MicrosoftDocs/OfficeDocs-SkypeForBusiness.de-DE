---
title: 'Lync Server 2013: Aktivieren von Quality of Experience'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5d3dcdc918469488b6cb0a555cb90e42fe68785
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154967"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="ef1a1-102">Aktivieren der erfahrungsqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef1a1-102">Enable Quality of Experience in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef1a1-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ef1a1-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ef1a1-104">Bei der QoE-Datenerfassung (Quality of Experience) werden numerische Daten aufgezeichnet, die die Medienqualität sowie Informationen zu Teilnehmern, Gerätenamen, Treibern, IP-Adressen und Endpunkttypen im Zusammenhang mit Anrufen und Sitzungen angeben.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-104">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="ef1a1-105">Ausführliche Informationen finden Sie unter [Planning for Monitoring in lync Server 2013](lync-server-2013-planning-for-monitoring.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-105">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="ef1a1-106">Verwenden Sie das folgende Verfahren, um QoE für Ihre gesamte Organisation oder jeden Standort in Ihrer Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-106">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ef1a1-107">Zum Aktivieren von QoE müssen Sie zunächst die Überwachung und eine Überwachungs-Back-End-Datenbank konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-107">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="ef1a1-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="ef1a1-109">So aktivieren Sie QoE mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="ef1a1-109">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="ef1a1-110">Melden Sie sich von einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe (oder gleichwertigen Benutzerrechten) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, an jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="ef1a1-111">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="ef1a1-112">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="ef1a1-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="ef1a1-113">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="ef1a1-114">Klicken Sie auf der Seite **Quality of Experience-Daten** in der Tabelle auf die entsprechende Auflistung, klicken Sie auf **Aktion**, und klicken Sie dann auf **QoE aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ef1a1-115">Aktivieren von QoE mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="ef1a1-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ef1a1-116">Sie können QoE mithilfe von Windows PowerShell und dem CmdletSet **-CsQoEConfiguration** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="ef1a1-117">Sie können dieses Cmdlet entweder über die lync Server 2013 Management-Shell oder über eine Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ef1a1-118">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="ef1a1-119">So aktivieren Sie QoE für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="ef1a1-119">To enable QoE for a single location</span></span>

  - <span data-ttu-id="ef1a1-120">Zum Aktivieren von QoE legen Sie den EnableQoE-Parameter auf true ($true) fest.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-120">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="ef1a1-121">So deaktivieren Sie QoE für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="ef1a1-121">To disable QoE for a single location</span></span>

  - <span data-ttu-id="ef1a1-122">Zum Deaktivieren von QoE legen Sie den EnableQoE-Parameter auf false ($false) fest.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-122">To disable QoE, set the EnableQoE parameter to False ($False).</span></span> <span data-ttu-id="ef1a1-123">Die Überwachung wird dadurch nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-123">This does not uninstall monitoring.</span></span> <span data-ttu-id="ef1a1-124">Es hält die Sammlung und Speicherung von QoE-Daten an.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-124">It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="ef1a1-125">So aktivieren Sie QoE an mehreren Standorten mithilfe eines einzelnen Befehls</span><span class="sxs-lookup"><span data-stu-id="ef1a1-125">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="ef1a1-126">Mit diesem Befehl wird QoE für alle derzeit in Ihrer Organisation verwendeten QoE-Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ef1a1-126">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="ef1a1-127">Ausführliche Informationen finden Sie unter [Sets-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="ef1a1-127">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ef1a1-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef1a1-128">See Also</span></span>


[<span data-ttu-id="ef1a1-129">Planen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef1a1-129">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="ef1a1-130">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef1a1-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

