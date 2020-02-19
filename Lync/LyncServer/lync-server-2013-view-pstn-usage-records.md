---
title: 'Lync Server 2013: Anzeigen von PSTN-Verwendungsdatensätzen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50bd216cbef24d92497d2724bd147dd92bb0abd8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136673"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="3841f-102">Anzeigen von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3841f-102">View PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3841f-103">_**Letztes Änderungsstand des Themas:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3841f-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3841f-104">Ein PSTN-Verwendungsdatensatz gibt eine Anrufklasse (z. B. interne Anrufe, Ortsgespräche oder Ferngespräche) an, die von den verschiedenen Benutzern oder Benutzergruppen in einer Organisation getätigt werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="3841f-104">A public switched telephone network (PSTN) usage record specifies a class of call (such as internal, local, or long distance) that can be made by various users or groups of users in an organization.</span></span> <span data-ttu-id="3841f-105">Ausführliche Informationen finden Sie unter [PSTN-Verwendungsdaten Sätze in lync Server 2013](lync-server-2013-pstn-usage-records.md) in der Planungsdokumentation.</span><span class="sxs-lookup"><span data-stu-id="3841f-105">For details, see [PSTN usage records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) in the Planning documentation.</span></span>

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a><span data-ttu-id="3841f-106">So zeigen Sie einen PSTN-Verwendungsdaten Satz mithilfe von lync Server-Systemsteuerung an</span><span class="sxs-lookup"><span data-stu-id="3841f-106">To view a PSTN usage record by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3841f-107">Melden Sie sich am Computer als Mitglied der RTCUniversalServerAdmins-Gruppe oder als Mitglied der CsVoiceAdministrator-, CsServerAdministrator-oder CsAdministrator-Rolle an.</span><span class="sxs-lookup"><span data-stu-id="3841f-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3841f-108">Ausführliche Informationen finden Sie unter [Delegate Setup Permissions in lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3841f-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3841f-109">Öffnen Sie ein Browserfenster, und geben Sie die admin-URL ein, um das lync Server-Systemsteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3841f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3841f-110">Ausführliche Informationen zu den verschiedenen Methoden, die Sie zum Starten von lync Server-Systemsteuerung verwenden können, finden Sie unter [Open lync Server 2013 Administration Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3841f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3841f-111">Klicken Sie in der linken Navigationsleiste auf **VoIP-Routing** und dann auf **PSTN-Verwendung**.</span><span class="sxs-lookup"><span data-stu-id="3841f-111">In the left navigation bar, click **Voice Routing** and then click **PSTN Usage**.</span></span>

4.  <span data-ttu-id="3841f-112">Markieren Sie auf der Seite **PSTN-Verwendung** den PSTN-Verwendungsdatensatz, die Sie anzeigen möchten. Klicken Sie dann auf **Bearbeiten** und anschließend auf **Details anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="3841f-112">On the **PSTN Usage** page, highlight the PSTN usage record you want to view, click **Edit** and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3841f-113">Auf einer schreibgeschützten Seite des ausgewählten PSTN-Verwendungsdatensatzes werden die zugehörigen Routen und VoIP-Richtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3841f-113">A read-only page of the selected PSTN usage record shows the associated routes and associated voice policies.</span></span>

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3841f-114">Anzeigen von PSTN-Verwendungsinformationen mithilfe von Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="3841f-114">Viewing PSTN Usage Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3841f-115">Sie können auch PSTN-Verwendungen anzeigen, indem Sie Windows PowerShell und das Cmdlet **Get-CsPstnUsage** verwenden.</span><span class="sxs-lookup"><span data-stu-id="3841f-115">You can also view PSTN usages by using Windows PowerShell and the **Get-CsPstnUsage** cmdlet.</span></span> <span data-ttu-id="3841f-116">Dieses Cmdlet kann entweder über die lync Server 2013-Verwaltungsshell oder über eine Remotesitzung von Windows PowerShell ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3841f-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3841f-117">Ausführliche Informationen zur Verwendung von Remote Windows PowerShell zum Herstellen einer Verbindung mit lync Server finden Sie im lync Server Windows PowerShell Blog-Artikel "schnell Start: Verwalten von Microsoft lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)mithilfe von Remote-PowerShell" unter.</span><span class="sxs-lookup"><span data-stu-id="3841f-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3841f-118">So zeigen Sie PSTN-Verwendungsinformationen mithilfe von Windows PowerShell-Cmdlets an</span><span class="sxs-lookup"><span data-stu-id="3841f-118">To view PSTN usage information by using Windows PowerShell cmdlets</span></span>

  - <span data-ttu-id="3841f-119">Wenn Sie Informationen zu allen PSTN-Verwendungen anzeigen möchten, geben Sie den folgenden Befehl in das lync Server-Verwaltungsshell ein, und drücken Sie dann die EINGABETASTE:</span><span class="sxs-lookup"><span data-stu-id="3841f-119">To view information about all of your PSTN usages, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsPstnUsage
    
    <span data-ttu-id="3841f-120">Mit diesem Befehl werden Informationen nach folgendem Muster zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="3841f-120">This command returns information similar to the following:</span></span>
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

<span data-ttu-id="3841f-121">Weitere Einzelheiten dazu finden Sie unter [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span><span class="sxs-lookup"><span data-stu-id="3841f-121">For details, see [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3841f-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3841f-122">See Also</span></span>


[<span data-ttu-id="3841f-123">Erstellen einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3841f-123">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="3841f-124">Ändern einer VoIP-Richtlinie und Konfigurieren von PSTN-Verwendungsdatensätzen in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3841f-124">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

