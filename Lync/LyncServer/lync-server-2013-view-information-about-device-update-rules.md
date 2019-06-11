---
title: 'Lync Server 2013: Anzeigen von Informationen zu geräteaktualisierungsregeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d873cbd80e599313b60a57cfc28eb9752d85ef66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a><span data-ttu-id="04543-102">Anzeigen von Informationen zu Geräte Update Regeln in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04543-102">View information about Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04543-103">_**Letztes Änderungsdatum des Themas:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="04543-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="04543-104">Anzeigen von Details zu geräteaktualisierungsregeln, die bereits importiert wurden, einschließlich Typ, Modell und Marke der Geräte, auf die das Update angewendet wird; Version und Art des Updates; und das Gebietsschema und den Pool für das Update.</span><span class="sxs-lookup"><span data-stu-id="04543-104">View details about device update rules that have already been imported, including the type, model, and brand of devices the update applies to; version and type of update; and locale and pool for the update.</span></span> <span data-ttu-id="04543-105">Informationen stehen für alle importierten geräteaktualisierungsregeln zur Verfügung – für diejenigen, die genehmigt, bereitgestellt (genehmigt), zurückgerufen (wiederhergestellt) sind und die Sie nicht verwenden möchten (Reset).</span><span class="sxs-lookup"><span data-stu-id="04543-105">Information is available for all imported device update rules—those that are pending approval, deployed (approved), recalled (restored), and those you’ve decided not to use (reset).</span></span> <span data-ttu-id="04543-106">Greifen Sie entweder in der lync Server-Systemsteuerung oder in Windows PowerShell auf diese Informationen zu.</span><span class="sxs-lookup"><span data-stu-id="04543-106">Access this information from either Lync Server Control Panel or Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04543-107">Details zum Importieren, genehmigen, zurücksetzen, wiederherstellen und Entfernen von Regeln finden Sie in den Themen unter <A href="lync-server-2013-device-update-rules.md">Geräte Update Regeln in lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="04543-107">For details about how to import, approve, reset, restore, and remove rules, see the topics listed at <A href="lync-server-2013-device-update-rules.md">Device Update rules in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="04543-108">So zeigen Sie geräteaktualisierungsregeln mithilfe der lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="04543-108">To view device update rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="04543-109">Melden Sie sich mit einem Benutzerkonto, dem die Rolle "CsUserAdministrator" oder "CsAdministrator" zugewiesen ist, auf einem beliebigen Computer in Ihrer internen Bereitstellung an.</span><span class="sxs-lookup"><span data-stu-id="04543-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="04543-110">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="04543-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="04543-111">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="04543-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="04543-112">Klicken Sie in der linken Navigationsleiste auf **Clients**, und klicken Sie dann auf die Schaltfläche **Geräte Update** -Navigation.</span><span class="sxs-lookup"><span data-stu-id="04543-112">In the left navigation bar, click **Clients**, and then click the **Device Update** navigation button.</span></span> <span data-ttu-id="04543-113">Importierte Regeln werden auf der Seite **Device Update** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="04543-113">Imported rules are listed on the **Device Update** page.</span></span>

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="04543-114">Anzeigen von geräteaktualisierungsregeln mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="04543-114">Viewing Device Update Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="04543-115">Detaillierte Informationen zu allen Geräteupdate Regeln können auch mithilfe von Windows PowerShell und dem Cmdlet **Get-CsDeviceUpdateRule** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="04543-115">Detailed information about all your device update rules can also be viewed by using Windows PowerShell and the **Get-CsDeviceUpdateRule** cmdlet.</span></span> <span data-ttu-id="04543-116">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="04543-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04543-117">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="04543-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>.</span></span>



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a><span data-ttu-id="04543-118">So zeigen Sie alle geräteaktualisierungsregeln an</span><span class="sxs-lookup"><span data-stu-id="04543-118">To view all your device update rules</span></span>

  - <span data-ttu-id="04543-119">Mit dem folgenden Befehl werden Informationen zu allen Geräteupdate Regeln zurückgegeben, die für die Verwendung in Ihrer Organisation konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="04543-119">The following command returns information about all the device updates rules configured for use in your organization:</span></span>
    
        Get-CsDeviceUpdateRule
    
    <span data-ttu-id="04543-120">Der Befehl gibt für jede Ihrer geräteaktualisierungsregeln Informationen zurück, die den folgenden ähneln:</span><span class="sxs-lookup"><span data-stu-id="04543-120">The command returns information similar to the following for each of your device update rules:</span></span>
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a><span data-ttu-id="04543-121">So zeigen Sie alle geräteaktualisierungsregeln auf einem bestimmten Webserver an</span><span class="sxs-lookup"><span data-stu-id="04543-121">To view all the device update rules on a specific web server</span></span>

  - <span data-ttu-id="04543-122">Wenn Sie die geräteaktualisierungsregeln auf einem bestimmten Computer anzeigen möchten, verwenden Sie den Parameter Filter, gefolgt von der Serveridentität und\*dem Platzhalterzeichen ().</span><span class="sxs-lookup"><span data-stu-id="04543-122">To view the device update rules on a specific computer, use the Filter parameter followed by the server Identity and the wildcard character (\*).</span></span> <span data-ttu-id="04543-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="04543-123">For example:</span></span>
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

<span data-ttu-id="04543-124">Ausführliche Informationen finden Sie im Hilfethema zum Cmdlet [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .</span><span class="sxs-lookup"><span data-stu-id="04543-124">For details, see the Help topic for the [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

