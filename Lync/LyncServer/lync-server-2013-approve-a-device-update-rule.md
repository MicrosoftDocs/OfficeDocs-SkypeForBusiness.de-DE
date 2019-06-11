---
title: 'Lync Server 2013: Genehmigen einer geräteaktualisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa560be6b8c341310c4831277902dab6f2e5552c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="11ea3-102">Genehmigen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11ea3-102">Approve a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="11ea3-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="11ea3-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="11ea3-104">Nachdem Sie eine geräteaktualisierungsregel importiert haben, ist Sie auf Ihren Testgeräten installiert.</span><span class="sxs-lookup"><span data-stu-id="11ea3-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="11ea3-105">Wenn die Tests erfolgreich sind und Sie das Update für Ihre Organisation bereitzustellen möchten, genehmigen Sie es entweder mithilfe der lync Server-Systemsteuerung oder Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="11ea3-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="11ea3-106">So genehmigen Sie eine geräteaktualisierungsregel mithilfe der lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="11ea3-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="11ea3-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="11ea3-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="11ea3-108">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="11ea3-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="11ea3-109">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="11ea3-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="11ea3-110">Führen Sie auf der Seite **Device Update** eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="11ea3-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="11ea3-111">Wenn Sie eine Regel genehmigen möchten, wählen Sie diese Regel aus.</span><span class="sxs-lookup"><span data-stu-id="11ea3-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="11ea3-112">Um alle Regeln zu genehmigen, klicken Sie auf **Bearbeiten**und dann auf **Alle auswählen**.</span><span class="sxs-lookup"><span data-stu-id="11ea3-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="11ea3-113">Klicken Sie auf **Aktion**und dann \*\*\*\* auf genehmigen.</span><span class="sxs-lookup"><span data-stu-id="11ea3-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="11ea3-114">Genehmigen einer geräteaktualisierungsregel mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="11ea3-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="11ea3-115">Geräteaktualisierungsregeln können auch mithilfe von Windows PowerShell und dem Cmdlet " **genehmigen-CsDeviceUpdateRule** " genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="11ea3-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="11ea3-116">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="11ea3-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="11ea3-117">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="11ea3-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="11ea3-118">So genehmigen Sie eine einzelne geräteaktualisierungsregel</span><span class="sxs-lookup"><span data-stu-id="11ea3-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="11ea3-119">Der folgende Befehl genehmigt die geräteaktualisierungsregel d5ce3c10-2588-420A-82ac-dc2d9b1222ff9, die auf dem Webserver ATL-CS-001.litwareinc.com gefunden wurde:</span><span class="sxs-lookup"><span data-stu-id="11ea3-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="11ea3-120">So genehmigen Sie mehrere geräteaktualisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="11ea3-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="11ea3-121">Dieser Befehl genehmigt alle geräteaktualisierungsregeln für Geräte mit Microsoft-Branding:</span><span class="sxs-lookup"><span data-stu-id="11ea3-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="11ea3-122">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [genehmigen-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) ".</span><span class="sxs-lookup"><span data-stu-id="11ea3-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="11ea3-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11ea3-123">See Also</span></span>


[<span data-ttu-id="11ea3-124">Importieren von geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11ea3-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="11ea3-125">Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="11ea3-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

