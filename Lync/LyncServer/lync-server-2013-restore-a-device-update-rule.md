---
title: 'Lync Server 2013: Wiederherstellen einer geräteaktualisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0416092c7021d599ec7e516d72c19e8baa3c598
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="c641d-102">Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c641d-102">Restore a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c641d-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="c641d-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="c641d-104">Wenn Sie eine geräteaktualisierungsregel von den Geräten in Ihrer Bereitstellung deinstallieren möchten, stellen Sie Sie wieder her.</span><span class="sxs-lookup"><span data-stu-id="c641d-104">To uninstall a device update rule from the devices in your deployment, restore it.</span></span> <span data-ttu-id="c641d-105">Durch das Wiederherstellen einer geräteaktualisierungsregel wird das Update deinstalliert und die vorherige Version dieser Regel neu installiert.</span><span class="sxs-lookup"><span data-stu-id="c641d-105">Restoring a device update rule both uninstalls the update and reinstalls the previous version of that rule.</span></span>

<span data-ttu-id="c641d-106">Sie können eine geräteaktualisierungsregel entweder mithilfe der lync Server-Systemsteuerung oder mit Windows PowerShell wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="c641d-106">You can restore a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="c641d-107">So stellen Sie geräteaktualisierungsregeln mithilfe der lync Server-Systemsteuerung wieder her</span><span class="sxs-lookup"><span data-stu-id="c641d-107">To restore device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="c641d-108">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="c641d-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c641d-109">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c641d-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="c641d-110">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c641d-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="c641d-111">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche **Geräte Update** -Navigation.</span><span class="sxs-lookup"><span data-stu-id="c641d-111">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="c641d-112">Führen Sie auf der Seite **Device Update** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="c641d-112">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="c641d-113">Wenn Sie eine Regel wiederherstellen möchten, wählen Sie diese Regel aus.</span><span class="sxs-lookup"><span data-stu-id="c641d-113">To restore one rule, select that rule.</span></span>
    
      - <span data-ttu-id="c641d-114">Wenn Sie alle Regeln wiederherstellen möchten, klicken Sie auf **Bearbeiten**und dann auf **Alle auswählen**.</span><span class="sxs-lookup"><span data-stu-id="c641d-114">To restore all rules, click **Edit**, and then click **Select All**.</span></span>

5.  <span data-ttu-id="c641d-115">Klicken Sie auf das Menü **Aktion** und dann auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="c641d-115">Click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c641d-116">Wiederherstellen von geräteaktualisierungsregeln mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="c641d-116">Restoring Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="c641d-117">Geräteupdate Regeln können auch mithilfe von Windows PowerShell und dem Cmdlet **Restore-CsDeviceUpdateRule** wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c641d-117">Device updates rules can also be restored by using Windows PowerShell and the **Restore-CsDeviceUpdateRule** cmdlet..</span></span> <span data-ttu-id="c641d-118">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c641d-118">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c641d-119">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="c641d-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a><span data-ttu-id="c641d-120">So stellen Sie eine einzelne geräteaktualisierungsregel auf einem Server wieder her</span><span class="sxs-lookup"><span data-stu-id="c641d-120">To restore a single device update rule on a server</span></span>

  - <span data-ttu-id="c641d-121">Mit dem folgenden Befehl wird die geräteaktualisierungsregel d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 auf dem Webserver ATL-CS-001.litwareinc.com wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="c641d-121">The following command restores the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="c641d-122">So stellen Sie alle geräteaktualisierungsregeln auf einem Server wieder her</span><span class="sxs-lookup"><span data-stu-id="c641d-122">To restore all the device update rules on a server</span></span>

  - <span data-ttu-id="c641d-123">Mit diesem Befehl werden alle geräteaktualisierungsregeln auf dem Webserver ATL-CS-001.litwareinc.com wiederhergestellt:</span><span class="sxs-lookup"><span data-stu-id="c641d-123">This command restores all the device update rules on the web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

<span data-ttu-id="c641d-124">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="c641d-124">For details, see the Help topic for the [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

