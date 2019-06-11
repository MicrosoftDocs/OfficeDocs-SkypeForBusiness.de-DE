---
title: 'Lync Server 2013: Zurücksetzen einer geräteaktualisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab03c5c28db28ddbd883f3f50845eaf91d4fd1a9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="18b48-102">Zurücksetzen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18b48-102">Reset a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18b48-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="18b48-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="18b48-104">Wenn Ihnen die Funktionsweise eines Updates auf Ihren Testgeräten nicht gefällt, können Sie die geräteaktualisierungsregel zurücksetzen, wodurch der Status der Regel ausstehend entfernt und das Update von den Testgeräten deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="18b48-104">If you don’t like the way that an update works on your test devices, you can reset the device update rule, which removes the rule’s pending status and uninstalls the update from the test devices.</span></span>

<span data-ttu-id="18b48-105">Sie können eine geräteaktualisierungsregel entweder mithilfe der lync Server-Systemsteuerung oder mit Windows PowerShell entfernen.</span><span class="sxs-lookup"><span data-stu-id="18b48-105">You can remove a device update rule by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18b48-106">Wenn Sie eine Regel deinstallieren möchten, die Sie bereits genehmigt haben (also ein Rollup durchgeführt haben), stellen Sie Sie wieder her.</span><span class="sxs-lookup"><span data-stu-id="18b48-106">To uninstall a rule that you’ve already approved (that is, rolled out), restore it.</span></span> <span data-ttu-id="18b48-107">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-restore-a-device-update-rule.md">Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="18b48-107">For details, see <A href="lync-server-2013-restore-a-device-update-rule.md">Restore a Device Update rule in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="18b48-108">So setzen Sie eine geräteaktualisierungsregel mithilfe der lync Server-Systemsteuerung zurück</span><span class="sxs-lookup"><span data-stu-id="18b48-108">To reset a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="18b48-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="18b48-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="18b48-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="18b48-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="18b48-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="18b48-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="18b48-112">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche **Geräte Update** -Navigation.</span><span class="sxs-lookup"><span data-stu-id="18b48-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span>

4.  <span data-ttu-id="18b48-113">Führen Sie auf der Seite **Device Update** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="18b48-113">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="18b48-114">Um eine Regel zurückzusetzen, wählen Sie die Regel aus, die Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="18b48-114">To reset one rule, select the rule you want to reset.</span></span>
    
      - <span data-ttu-id="18b48-115">Wenn Sie alle Regeln zurücksetzen möchten, klicken Sie im Menü **Bearbeiten** auf **Alles markieren**.</span><span class="sxs-lookup"><span data-stu-id="18b48-115">To reset all rules, on the **Edit** menu, click **Select All**.</span></span>
    
      - <span data-ttu-id="18b48-116">Wenn Sie alle Regeln für eine Marke zurücksetzen möchten, verwenden Sie das Menü **Marken** Spalte.</span><span class="sxs-lookup"><span data-stu-id="18b48-116">To reset all rules for one brand, use the **Brand** column menu.</span></span>

5.  <span data-ttu-id="18b48-117">Klicken Sie auf **Aktion**und dann auf ausstehende **Updates Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="18b48-117">Click **Action**, and then click **Cancel pending updates**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="18b48-118">Wenn Sie sicher sind, dass Sie die von Ihnen stornierten geräteaktualisierungsregeln nie aufrollen möchten, sollten Sie Sie möglicherweise löschen.</span><span class="sxs-lookup"><span data-stu-id="18b48-118">If you’re sure you’ll never want to roll out the device update rule(s) that you cancelled, you might want to delete them.</span></span> <span data-ttu-id="18b48-119">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-remove-a-device-update-rule.md">Entfernen einer geräteaktualisierungsregel in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="18b48-119">For details, see <A href="lync-server-2013-remove-a-device-update-rule.md">Remove a Device Update rule in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="18b48-120">Zurücksetzen einer geräteaktualisierungsregel mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="18b48-120">Resetting a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="18b48-121">Geräteaktualisierungsregeln können auch mithilfe von Windows PowerShell und dem Cmdlet **Reset-CsDeviceUpdateRule** zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="18b48-121">Device update rules can also be reset by using Windows PowerShell and the **Reset-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="18b48-122">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="18b48-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18b48-123">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="18b48-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a><span data-ttu-id="18b48-124">So setzen Sie eine bestimmte geräteaktualisierungsregel auf einem Server zurück</span><span class="sxs-lookup"><span data-stu-id="18b48-124">To reset a specific device update rule on a server</span></span>

  - <span data-ttu-id="18b48-125">Mit dem folgenden Befehl wird die geräteaktualisierungsregel d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 auf dem Webserver ATL-CS-001.litwareinc.com zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="18b48-125">The following command resets the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a><span data-ttu-id="18b48-126">So setzen Sie alle geräteaktualisierungsregeln auf einem Server zurück</span><span class="sxs-lookup"><span data-stu-id="18b48-126">To reset all the device update rules on a server</span></span>

  - <span data-ttu-id="18b48-127">Mit diesem Befehl werden alle geräteaktualisierungsregeln auf dem Webserver ATL-CS-001.litwareinc.com zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="18b48-127">This command resets all the device update rules on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a><span data-ttu-id="18b48-128">So setzen Sie alle Geräteupdate Regeln mit einer bestimmten Marke zurück</span><span class="sxs-lookup"><span data-stu-id="18b48-128">To reset all the device updates rules that have a specific brand</span></span>

  - <span data-ttu-id="18b48-129">In diesem Beispiel werden alle Geräte Updates in der gesamten Organisation, die eine Marke von Microsoft aufweisen, zurückgesetzt:</span><span class="sxs-lookup"><span data-stu-id="18b48-129">In this example, all the device updates throughout the organization that have a Brand equal to Microsoft are reset:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

<span data-ttu-id="18b48-130">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="18b48-130">For details, see the Help topic for the [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="18b48-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18b48-131">See Also</span></span>


[<span data-ttu-id="18b48-132">Genehmigen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18b48-132">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

