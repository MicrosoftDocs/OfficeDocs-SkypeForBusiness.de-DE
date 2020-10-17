---
title: 'Lync Server 2013: Konfigurieren von VoIP-Routen für ausgehende Anrufe'
description: 'Lync Server 2013: Konfigurieren von VoIP-Routen für ausgehende Anrufe.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dd0d712295ecdd0e9a517330abcff36021e996d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542211"
---
# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="92be6-103">Konfigurieren von VoIP-Routen für ausgehende Anrufe in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92be6-103">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92be6-104">_**Letztes Änderungsstand des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="92be6-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="92be6-105">Eine lync Server 2013 VoIP-Route ordnet Zielrufnummern ein oder mehrere PSTN-Gateways (Public Switched Telephone Network) oder SIP-Trunks sowie mindestens einen PSTN-Verwendungsdaten Satz zu.</span><span class="sxs-lookup"><span data-stu-id="92be6-105">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="92be6-106">**So zeigen Sie VoIP-Routen mithilfe von lync Server-Systemsteuerung an**</span><span class="sxs-lookup"><span data-stu-id="92be6-106">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="92be6-107">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="92be6-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="92be6-108">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="92be6-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="92be6-109">Klicken Sie auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="92be6-109">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="92be6-110">Klicken Sie auf **Route**.</span><span class="sxs-lookup"><span data-stu-id="92be6-110">Click **Route**.</span></span>

4.  <span data-ttu-id="92be6-p102">Doppelklicken Sie auf eine VoIP-Route, um zusätzliche Eigenschaften aus der Liste der VoIP-Routen anzuzeigen, oder wählen Sie die Route aus, und klicken Sie auf **Bearbeiten**. Klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="92be6-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92be6-113">Sie können nur jeweils für eine einzelne Route Detailinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="92be6-113">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="92be6-114">**So zeigen Sie VoIP-Routen mithilfe von Windows PowerShell an**</span><span class="sxs-lookup"><span data-stu-id="92be6-114">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="92be6-115">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, dann auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="92be6-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="92be6-116">VoIP-Routen können mit Windows PowerShell und dem Cmdlet **Get-CsVoiceRoute** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="92be6-116">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="92be6-117">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="92be6-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="92be6-118">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von Remote-PowerShell" unter [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="92be6-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="92be6-119">Wenn Sie Informationen zu allen VoIP-Routen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="92be6-119">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="92be6-120">Hiermit werden Informationen zurückgegeben, die so oder ähnlich aussehen:</span><span class="sxs-lookup"><span data-stu-id="92be6-120">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="92be6-121">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-voice-routes.md">VoIP-Routen in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="92be6-121">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="92be6-122">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="92be6-122">In This Section</span></span>

  - [<span data-ttu-id="92be6-123">Erstellen einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92be6-123">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="92be6-124">Ändern einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92be6-124">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92be6-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92be6-125">See Also</span></span>


[<span data-ttu-id="92be6-126">Verwalten des VoIP-Routings in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92be6-126">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

