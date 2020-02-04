---
title: 'Lync Server 2013: Konfigurieren von VoIP-Routen für ausgehende Anrufe'
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
ms.openlocfilehash: f8b425ce1e0627645f84223f36f6fc0de18b5af8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="a533b-102">Konfigurieren von VoIP-Routen für ausgehende Anrufe in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a533b-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a533b-103">_**Letztes Änderungsdatum des Themas:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a533b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a533b-104">Eine lync Server 2013-VoIP-Route verknüpft Zielrufnummern mit einem oder mehreren PSTN-Gateways (Public Switched Telephone Network) oder SIP-Stämmen sowie einem oder mehreren PSTN-Nutzungsdaten Sätzen.</span><span class="sxs-lookup"><span data-stu-id="a533b-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="a533b-105">**So zeigen Sie VoIP-Routen mithilfe der lync Server-Systemsteuerung an**</span><span class="sxs-lookup"><span data-stu-id="a533b-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="a533b-106">Öffnen Sie ein Browserfenster, und geben Sie dann die Administrator-URL ein, um die lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="a533b-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a533b-107">Details zu den verschiedenen Methoden, die Sie zum Starten der lync Server-Systemsteuerung verwenden können, finden Sie unter [Öffnen von lync Server 2013-Verwaltungstools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a533b-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="a533b-108">Klicken Sie auf **VoIP-Routing**.</span><span class="sxs-lookup"><span data-stu-id="a533b-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="a533b-109">Klicken Sie auf **Route**.</span><span class="sxs-lookup"><span data-stu-id="a533b-109">Click **Route**.</span></span>

4.  <span data-ttu-id="a533b-110">Doppelklicken Sie auf eine VoIP-Route, um weitere Eigenschaften aus der Liste der VoIP-Routen anzuzeigen, oder wählen Sie die Route aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="a533b-110">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**.</span></span> <span data-ttu-id="a533b-111">Klicken Sie dann auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a533b-111">Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a533b-112">Sie können nur detaillierte Informationen zu einer einzelnen Route gleichzeitig anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a533b-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="a533b-113">**So zeigen Sie VoIP-Routen mithilfe von Windows PowerShell an**</span><span class="sxs-lookup"><span data-stu-id="a533b-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="a533b-114">Starten Sie die lync Server-Verwaltungsshell: Klicken Sie auf **Start**, klicken Sie auf **Alle Programme**, klicken Sie auf **Microsoft lync Server 2013**, und klicken Sie dann auf **lync Server-Verwaltungsshell**.</span><span class="sxs-lookup"><span data-stu-id="a533b-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="a533b-115">VoIP-Routen können mithilfe von Windows PowerShell und dem Cmdlet **Get-CsVoiceRoute** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="a533b-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="a533b-116">Dieses Cmdlet kann entweder in der lync Server 2013-Verwaltungsshell oder in einer Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a533b-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a533b-117">Details zum Verwenden der Remote-Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im Windows PowerShell-Blog Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 mithilfe von [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="a533b-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="a533b-118">Wenn Sie Informationen zu allen VoIP-Routen anzeigen möchten, geben Sie den folgenden Befehl in der lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="a533b-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="a533b-119">Es werden etwa folgende Informationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="a533b-119">That will return information similar to this:</span></span>
    
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
> <span data-ttu-id="a533b-120">Ausführliche Informationen finden Sie unter <A href="lync-server-2013-voice-routes.md">VoIP-Routen in lync Server 2013</A> in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="a533b-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a533b-121">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a533b-121">In This Section</span></span>

  - [<span data-ttu-id="a533b-122">Erstellen einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a533b-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="a533b-123">Ändern einer VoIP-Route in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a533b-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a533b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a533b-124">See Also</span></span>


[<span data-ttu-id="a533b-125">Verwalten des VoIP-Routings in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a533b-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

