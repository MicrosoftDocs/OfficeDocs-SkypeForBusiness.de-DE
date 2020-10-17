---
title: 'Lync Server 2013: Entfernen einer geräteaktualisierungsregel'
description: 'Lync Server 2013: Entfernen einer geräteaktualisierungsregel.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f0ed7436331377200a5b8719cf32a8195179402
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555781"
---
# <a name="remove-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="a1407-103">Entfernen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1407-103">Remove a Device Update rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1407-104">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="a1407-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="a1407-105">Durch das Entfernen einer geräteaktualisierungsregel wird Sie dauerhaft aus der Geräteupdate Warteschlange entfernt.</span><span class="sxs-lookup"><span data-stu-id="a1407-105">Removing a device update rule takes it permanently out of the device update queue.</span></span>

<span data-ttu-id="a1407-106">Das Entfernen einer Regel unterscheidet sich von der Deinstallation eines Updates von den Geräten in Ihrer Bereitstellung oder von ihren Testgeräten.</span><span class="sxs-lookup"><span data-stu-id="a1407-106">Removing a rule is different from uninstalling an update from the devices in your deployment or from your test devices.</span></span> <span data-ttu-id="a1407-107">Wenn Sie ein genehmigtes Update von Ihrer Bereitstellung deinstallieren möchten, stellen Sie die geräteaktualisierungsregel *wieder her* .</span><span class="sxs-lookup"><span data-stu-id="a1407-107">To uninstall an approved update from your deployment, you *restore* the device update rule.</span></span> <span data-ttu-id="a1407-108">Ausführliche Informationen finden Sie unter [Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="a1407-108">For details, see [Restore a Device Update rule in Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md).</span></span> <span data-ttu-id="a1407-109">Wenn Sie ein Update deinstallieren möchten, das Sie nicht von ihren Testgeräten genehmigt haben, setzen Sie es *zurück* .</span><span class="sxs-lookup"><span data-stu-id="a1407-109">To uninstall an update you haven’t approved from your test devices, you *reset* it.</span></span> <span data-ttu-id="a1407-110">Ausführliche Informationen finden Sie unter [Reset a Device Update Rule in lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span><span class="sxs-lookup"><span data-stu-id="a1407-110">For details, see [Reset a Device Update rule in Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).</span></span>

<span data-ttu-id="a1407-111">Sie können eine geräteaktualisierungsregel entweder mithilfe von lync Server-Systemsteuerung oder Windows PowerShell entfernen.</span><span class="sxs-lookup"><span data-stu-id="a1407-111">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="a1407-112">So entfernen Sie geräteaktualisierungsregeln mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="a1407-112">To remove device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="a1407-113">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="a1407-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a1407-114">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a1407-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a1407-115">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a1407-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a1407-116">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Navigationsschaltfläche **Geräte Update** .</span><span class="sxs-lookup"><span data-stu-id="a1407-116">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="a1407-117">Führen Sie auf der Seite **Geräte Update** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="a1407-117">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="a1407-118">Um eine Regel zu entfernen, wählen Sie die Regel aus, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="a1407-118">To remove one rule, select the rule you want to delete.</span></span>
    
      - <span data-ttu-id="a1407-119">Klicken Sie zum Entfernen aller Regeln auf das Menü **Bearbeiten** , und klicken Sie dann auf **Alle auswählen**.</span><span class="sxs-lookup"><span data-stu-id="a1407-119">To remove all rules, click the **Edit** menu, and then click **Select All**.</span></span>

5.  <span data-ttu-id="a1407-120">Klicken Sie auf **Bearbeiten** und anschließend auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="a1407-120">Click **Edit**, and then click **Delete**.</span></span>

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="a1407-121">Entfernen von geräteaktualisierungsregeln mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a1407-121">Removing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="a1407-122">Geräteaktualisierungsregeln können auch mithilfe von Windows PowerShell und dem Cmdlet **Remove-CsDeviceUpdateRule** entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="a1407-122">Device update rules can also be removed by using Windows PowerShell and the **Remove-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="a1407-123">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a1407-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a1407-124">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a1407-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a><span data-ttu-id="a1407-125">So entfernen Sie eine einzelne geräteaktualisierungsregel von einem Server</span><span class="sxs-lookup"><span data-stu-id="a1407-125">To remove a single device update rule from a server</span></span>

  - <span data-ttu-id="a1407-126">Mit dem folgenden Befehl wird die geräteaktualisierungsregel d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 "vom Webserver auf ATL-CS-001.litwareinc.com entfernt.</span><span class="sxs-lookup"><span data-stu-id="a1407-126">The following command removes the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 from the Web server on atl-cs-001.litwareinc.com.</span></span>
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a><span data-ttu-id="a1407-127">So entfernen Sie alle geräteaktualisierungsregeln von einem Server</span><span class="sxs-lookup"><span data-stu-id="a1407-127">To remove all the device update rules from a server</span></span>

  - <span data-ttu-id="a1407-128">Mit diesem Befehl werden alle geräteaktualisierungsregeln vom Webserver auf ATL-CS-001.litwareinc.com entfernt.</span><span class="sxs-lookup"><span data-stu-id="a1407-128">This command removes all the device update rules from the web server on atl-cs-001.litwareinc.com.</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

<span data-ttu-id="a1407-129">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="a1407-129">For details, see the Help topic for the [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a1407-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1407-130">See Also</span></span>


[<span data-ttu-id="a1407-131">Genehmigen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1407-131">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

