---
title: 'Lync Server 2013: Aktivieren der Anrufsteuerung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857dce2203bf9713676113ba4fa0e8b6f4ec5a60
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187768"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="60ec2-102">Aktivieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60ec2-102">Enabling call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60ec2-103">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="60ec2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="60ec2-104">Bei der Anrufsteuerung handelt es sich um ein Netzwerk aus Regionen, Standorten und Subnetzen, mit dem Sie basierend auf der verfügbaren Bandbreite Einschränkungen für Audio- und Videoübertragungen festlegen können.</span><span class="sxs-lookup"><span data-stu-id="60ec2-104">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth.</span></span> <span data-ttu-id="60ec2-105">Nach der Konfiguration des Anrufsteuerungsnetzwerks müssen Sie die Anrufsteuerung aktivieren, um die Bandbreiteneinschränkungen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="60ec2-105">After you configure the CAC network, you must enable CAC to enforce the bandwidth limitations.</span></span> <span data-ttu-id="60ec2-106">Dazu können Sie lync Server-Systemsteuerung verwenden.</span><span class="sxs-lookup"><span data-stu-id="60ec2-106">You can use Lync Server Control Panel to do this.</span></span>

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a><span data-ttu-id="60ec2-107">So aktivieren Sie die Anrufsteuerung in lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="60ec2-107">To enable CAC from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="60ec2-108">Melden Sie sich bei einem Benutzerkonto, das Mitglied der RTCUniversalServerAdmins-Gruppe ist (oder gleichwertige Benutzerrechte hat) oder der CsAdministrator-Rolle zugewiesen ist, an einem beliebigen Computer in ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="60ec2-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="60ec2-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="60ec2-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="60ec2-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="60ec2-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="60ec2-111">Klicken Sie in der linken Navigationsleiste auf **Netzwerkkonfiguration** und dann auf **Global**.</span><span class="sxs-lookup"><span data-stu-id="60ec2-111">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="60ec2-112">Klicken Sie auf der Seite **Global** auf die Konfiguration **Global**.</span><span class="sxs-lookup"><span data-stu-id="60ec2-112">On the **Global** page, click the **Global** configuration.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="60ec2-113">Für jede Microsoft lync Server 2013-Bereitstellung kann nur ein Netzwerk konfiguriert werden, sodass in der Liste nie mehr als eine Netzwerkkonfiguration vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="60ec2-113">Only one network can be configured for any Microsoft Lync Server 2013 deployment, so there will never be more than one network configuration in the list.</span></span> <span data-ttu-id="60ec2-114">Die globale Konfiguration kann nicht umbenannt werden.</span><span class="sxs-lookup"><span data-stu-id="60ec2-114">You cannot rename the Global configuration.</span></span>

    
    </div>

5.  <span data-ttu-id="60ec2-115">Klicken Sie im Menü **Bearbeiten** auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="60ec2-115">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="60ec2-116">Aktivieren Sie auf der Seite **Globale Einstellungen bearbeiten** das Kontrollkästchen **Anrufsteuerung aktivieren**, und klicken Sie auf **Commit**.</span><span class="sxs-lookup"><span data-stu-id="60ec2-116">On the **Edit Global Setting** page, select the **Enable call admission control** check box, and then click **Commit**.</span></span>

<span data-ttu-id="60ec2-p104">Beim Klicken auf **Commit** wird die Konfiguration getestet. Das Dialogfeld **Globale Einstellungen bearbeiten** wird geschlossen, und die Seite **Global** wird erneut angezeigt. Wenn in Ihrer Netzwerkkonfiguration Fehler oder Inkonsistenzen ermittelt werden, die eine ordnungsgemäße Funktionsweise verhindern, wird eine Warnung angezeigt (wenn die einzelnen Regionen beispielsweise nicht über eine regionenübergreifende Route miteinander verbunden sind).</span><span class="sxs-lookup"><span data-stu-id="60ec2-p104">When you click **Commit**, you run a test of the configuration. The **Edit Global Settings** dialog box closes, returning you to the **Global** page. You will receive a warning if any errors or inconsistencies are discovered in your network configuration that will prevent it from working correctly (for example, if every region is not connected to every other region through an interregion route).</span></span>

<span data-ttu-id="60ec2-p105">Nach dem Ändern Ihrer Netzwerkkonfiguration können Sie die Überprüfung erneut ausführen, indem Sie die globale Konfiguration öffnen und auf **Commit** klicken. Es ist nicht erforderlich, die Anrufsteuerung zunächst zu deaktivieren: Lassen Sie das Kontrollkästchen aktiviert, und klicken Sie auf **Commit**. Dieser Vorgang kann zu einem beliebigen Zeitpunkt ausgeführt werden, ohne Konfigurationsänderungen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="60ec2-p105">If you make changes to your network configuration, you can run the validation check again by opening the Global configuration and clicking **Commit**. You do not need to disable CAC first: leave the check box checked and click **Commit**. You can do this at any time without making any configuration changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60ec2-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60ec2-123">See Also</span></span>


[<span data-ttu-id="60ec2-124">Übersicht über die Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60ec2-124">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  


[<span data-ttu-id="60ec2-125">Planung der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60ec2-125">Planning for call admission control in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-admission-control.md)  
[<span data-ttu-id="60ec2-126">Konfigurieren der Anrufsteuerung in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60ec2-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="60ec2-127">Get-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="60ec2-127">Get-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[<span data-ttu-id="60ec2-128">Gruppe-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="60ec2-128">Set-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[<span data-ttu-id="60ec2-129">Remove-CsNetworkConfiguration</span><span class="sxs-lookup"><span data-stu-id="60ec2-129">Remove-CsNetworkConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

