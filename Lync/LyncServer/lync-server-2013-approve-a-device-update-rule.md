---
title: 'Lync Server 2013: Genehmigen einer geräteaktualisierungsregel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25c6fad9547e9c738523ac0f460d3e6696d1920a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204424"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a><span data-ttu-id="441b2-102">Genehmigen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="441b2-102">Approve a Device Update rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="441b2-103">_**Letztes Änderungsstand des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="441b2-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="441b2-104">Nachdem Sie eine geräteaktualisierungsregel importiert haben, wird Sie auf Ihren Testgeräten installiert.</span><span class="sxs-lookup"><span data-stu-id="441b2-104">After you import a device update rule, it’s installed on your test devices.</span></span> <span data-ttu-id="441b2-105">Wenn Ihre Tests erfolgreich sind und Sie das Update für Ihre Organisation bereitstellen möchten, genehmigen Sie es entweder mithilfe von lync Server-Systemsteuerung oder Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="441b2-105">If your testing is successful, and you want to roll out the update to your organization, approve it by using either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a><span data-ttu-id="441b2-106">So genehmigen Sie eine geräteaktualisierungsregel mithilfe von lync Server-Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="441b2-106">To approve a device update rule by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="441b2-107">Melden Sie sich mit einem Benutzerkonto, dem die Rolle CsUserAdministrator oder CsAdministrator zugewiesen ist, an einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="441b2-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="441b2-108">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="441b2-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="441b2-109">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="441b2-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="441b2-110">Führen Sie auf der Seite **Geräte Update** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="441b2-110">On the **Device Update** page, do one of the following:</span></span>
    
      - <span data-ttu-id="441b2-111">Um eine Regel zu genehmigen, wählen Sie diese Regel aus.</span><span class="sxs-lookup"><span data-stu-id="441b2-111">To approve one rule, select that rule.</span></span>
    
      - <span data-ttu-id="441b2-112">Klicken Sie auf **Bearbeiten**, und klicken Sie dann auf **Alle auswählen**, um alle Regeln zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="441b2-112">To approve all rules, click **Edit**, and then click **Select All**.</span></span>

4.  <span data-ttu-id="441b2-113">Klicken Sie auf **Aktion**und dann auf **genehmigen**.</span><span class="sxs-lookup"><span data-stu-id="441b2-113">Click **Action**, and then click **Approve**.</span></span>

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="441b2-114">Genehmigen einer geräteaktualisierungsregel mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="441b2-114">Approving a Device Update Rule by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="441b2-115">Geräteaktualisierungsregeln können auch mit Windows PowerShell und dem Cmdlet **genehmigen-CsDeviceUpdateRule** genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="441b2-115">Device update rules can also be approved by using Windows PowerShell and the **Approve-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="441b2-116">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="441b2-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="441b2-117">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="441b2-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a><span data-ttu-id="441b2-118">So genehmigen Sie eine einzelne geräteaktualisierungsregel</span><span class="sxs-lookup"><span data-stu-id="441b2-118">To approve a single device update rule</span></span>

  - <span data-ttu-id="441b2-119">Mit dem folgenden Befehl wird die geräteaktualisierungsregel d5ce3c10-2588-420A-82ac-dc2d9b1222ff9 ", die auf dem Webserver ATL-CS-001.litwareinc.com gefunden wurde, genehmigt:</span><span class="sxs-lookup"><span data-stu-id="441b2-119">The following command approves the device update rule d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 found on the Web server atl-cs-001.litwareinc.com:</span></span>
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a><span data-ttu-id="441b2-120">So genehmigen Sie mehrere geräteaktualisierungsregeln</span><span class="sxs-lookup"><span data-stu-id="441b2-120">To approve multiple device update rules</span></span>

  - <span data-ttu-id="441b2-121">Mit diesem Befehl werden alle geräteaktualisierungsregeln für Geräte mit Microsoft Branding genehmigt:</span><span class="sxs-lookup"><span data-stu-id="441b2-121">This command approves all the device update rules for Microsoft-branded devices:</span></span>
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

<span data-ttu-id="441b2-122">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet " [genehmigen-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) ".</span><span class="sxs-lookup"><span data-stu-id="441b2-122">For details, see the Help topic for the [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="441b2-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="441b2-123">See Also</span></span>


[<span data-ttu-id="441b2-124">Importieren von geräteaktualisierungsregeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="441b2-124">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)  
[<span data-ttu-id="441b2-125">Wiederherstellen einer geräteaktualisierungsregel in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="441b2-125">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

