---
title: 'Lync Server 2013: Aktivieren der Qualität der Benutzerfreundlichkeit'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 558e7cfef48a472b4fd9ab7f538197313a8f112a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a><span data-ttu-id="88a09-102">Aktivieren der erfahrungsqualität in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a09-102">Enable Quality of Experience in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88a09-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="88a09-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="88a09-104">Bei der QoE-Datenerfassung (Quality of Experience) werden numerische Daten aufgezeichnet, die die Medienqualität sowie Informationen zu Teilnehmern, Gerätenamen, Treibern, IP-Adressen und Endpunkttypen im Zusammenhang mit Anrufen und Sitzungen angeben.</span><span class="sxs-lookup"><span data-stu-id="88a09-104">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="88a09-105">Ausführliche Informationen finden Sie unter [Planen der Überwachung in lync Server 2013](lync-server-2013-planning-for-monitoring.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="88a09-105">For details, see [Planning for monitoring in Lync Server 2013](lync-server-2013-planning-for-monitoring.md) in the Planning documentation.</span></span>

<span data-ttu-id="88a09-106">Verwenden Sie das folgende Verfahren, um QoE in der gesamten Organisation oder für jeden Standort in Ihrer Organisation zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="88a09-106">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="88a09-107">Zur Aktivierung von QoE müssen Sie zunächst die Überwachung und eine Monitoring-Back-End-Datenbank konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="88a09-107">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="88a09-108">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-deploying-monitoring.md">Bereitstellen der Überwachung in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="88a09-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a><span data-ttu-id="88a09-109">So aktivieren Sie QoE mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="88a09-109">To enable QoE by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="88a09-110">Melden Sie sich bei einem Benutzerkonto, das ein Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder über entsprechende Benutzerrechte verfügt) oder der CsServerAdministrator-oder CsAdministrator-Rolle zugewiesen ist, bei jedem Computer an, der sich in dem Netzwerk befindet, in dem Sie lync Server 2013 bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="88a09-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="88a09-111">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="88a09-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="88a09-112">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="88a09-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="88a09-113">Klicken Sie in der linken Navigationsleiste auf **Überwachung und Archivierung** und dann auf **QoE-Daten**.</span><span class="sxs-lookup"><span data-stu-id="88a09-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="88a09-114">Klicken Sie auf der Seite **Quality of Experience-Daten** in der Tabelle auf die entsprechende Auflistung, klicken Sie auf **Aktion** und anschließend auf **QoE aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="88a09-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="88a09-115">Aktivieren von QoE mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="88a09-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="88a09-116">Sie können QoE mithilfe von Windows PowerShell und dem Cmdlet " **Satz-CsQoEConfiguration** " aktivieren.</span><span class="sxs-lookup"><span data-stu-id="88a09-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="88a09-117">Sie können dieses Cmdlet entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="88a09-117">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="88a09-118">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="88a09-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="88a09-119">So aktivieren Sie QoE für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="88a09-119">To enable QoE for a single location</span></span>

  - <span data-ttu-id="88a09-120">Zum Aktivieren von QoE legen Sie den EnableQoE-Parameter auf „True“ ($True) fest.</span><span class="sxs-lookup"><span data-stu-id="88a09-120">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="88a09-121">So deaktivieren Sie QoE für einen einzelnen Standort</span><span class="sxs-lookup"><span data-stu-id="88a09-121">To disable QoE for a single location</span></span>

  - <span data-ttu-id="88a09-p105">Zum Deaktivieren von QoE legen Sie den EnableQoE-Parameter auf „False“ ($False) fest. Die Überwachung wird dadurch nicht deinstalliert. Das Erfassen und Speichern von QoE-Daten wird unterbrochen.</span><span class="sxs-lookup"><span data-stu-id="88a09-p105">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="88a09-125">So aktivieren Sie QoE mit einem einzelnen Befehl an mehreren Standorten</span><span class="sxs-lookup"><span data-stu-id="88a09-125">To use a single command to enable QoE in multiple locations</span></span>

  - <span data-ttu-id="88a09-126">Mit diesem Befehl wird QoE für alle derzeit in Ihrer Organisation verwendeten QoE-Konfigurationseinstellungen aktiviert.</span><span class="sxs-lookup"><span data-stu-id="88a09-126">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

<span data-ttu-id="88a09-127">Ausführliche Informationen finden Sie unter [Satz-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="88a09-127">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="88a09-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="88a09-128">See Also</span></span>


[<span data-ttu-id="88a09-129">Planen der Überwachung in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a09-129">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="88a09-130">Bereitstellen der Überwachung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="88a09-130">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

