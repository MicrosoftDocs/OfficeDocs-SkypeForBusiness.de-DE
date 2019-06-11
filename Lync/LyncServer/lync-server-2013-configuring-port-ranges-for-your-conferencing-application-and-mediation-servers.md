---
title: 'Lync Server 2013: Konfigurieren von Portbereichen für Ihre Konferenz-, Anwendungs-und Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5402da56fa646c6ae6e2247baa70a5ef03b851cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="1e58e-102">Konfigurieren von Portbereichen in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="1e58e-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e58e-103">_**Letztes Änderungsdatum des Themas:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="1e58e-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="1e58e-104">Um die Qualität des Diensts zu implementieren, sollten Sie identische Portbereiche für die Audio-, Video-und Anwendungsfreigabe auf Ihren Konferenz-, Anwendungs-und Vermittlungsservern konfigurieren. Darüber hinaus dürfen sich diese Portbereiche in keiner Weise überlappen.</span><span class="sxs-lookup"><span data-stu-id="1e58e-104">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way.</span></span> <span data-ttu-id="1e58e-105">Wenn Sie ein einfaches Beispiel verwenden möchten, nehmen Sie an, dass Sie die Ports 10000 bis 10999 für Video auf Ihren Konferenzservern verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e58e-105">To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers.</span></span> <span data-ttu-id="1e58e-106">Das bedeutet, dass Sie auch Ports 10000 bis 10999 für Video auf Ihren Anwendungs-und Vermittlungsservern reservieren müssen.</span><span class="sxs-lookup"><span data-stu-id="1e58e-106">That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers.</span></span> <span data-ttu-id="1e58e-107">Wenn dies nicht der Fall ist, funktioniert QoS nicht erwartungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="1e58e-107">If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="1e58e-108">Nehmen Sie entsprechend an, dass Sie die Ports 10000 bis 10999 für Video reservieren, und dann die Ports 10500 bis 11999 für Audio reservieren.</span><span class="sxs-lookup"><span data-stu-id="1e58e-108">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio.</span></span> <span data-ttu-id="1e58e-109">Dies kann zu Problemen bei der Dienstqualität führen, da sich die Portbereiche überlappen.</span><span class="sxs-lookup"><span data-stu-id="1e58e-109">This can create problems for Quality of Service, because the port ranges overlap.</span></span> <span data-ttu-id="1e58e-110">Bei QoS muss jede Modalität über einen eindeutigen Satz von Ports verfügen: Wenn Sie Ports 10000 bis 10999 für Video verwenden, müssen Sie einen anderen Bereich verwenden (beispielsweise 11000 bis 11999 für Audio).</span><span class="sxs-lookup"><span data-stu-id="1e58e-110">With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="1e58e-111">Standardmäßig überlappen sich Audio-und Video-Portbereiche in Microsoft lync Server 2013 nicht. die der Anwendungsfreigabe zugewiesenen Portbereiche überlappen sich jedoch sowohl mit dem Audio-als auch dem Video-Portbereich.</span><span class="sxs-lookup"><span data-stu-id="1e58e-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="1e58e-112">(Was wiederum bedeutet, dass keiner dieser Bereiche eindeutig ist.) Sie können die vorhandenen Portbereiche für Ihre Konferenz-, Anwendungs-und Vermittlungsserver überprüfen, indem Sie die folgenden drei Befehle in der lync Server 2013-Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="1e58e-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="1e58e-113">Wie in den vorstehenden Befehlen zu sehen ist, werden jedem Porttyp – Audio, Video und Anwendungsfreigabe – zwei getrennte Eigenschaftswerte zugewiesen: der Port Start und die Portanzahl.</span><span class="sxs-lookup"><span data-stu-id="1e58e-113">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count.</span></span> <span data-ttu-id="1e58e-114">Der Port Start gibt den ersten Port an, der für diese Modalität verwendet wird; Wenn beispielsweise der Audioport-Start gleich 50000 ist, bedeutet dies, dass der erste Port für den Audioverkehr Port 50000 ist.</span><span class="sxs-lookup"><span data-stu-id="1e58e-114">The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000.</span></span> <span data-ttu-id="1e58e-115">Wenn die Anzahl der Audioanschlüsse 2 ist (was kein gültiger Wert ist, aber hier zur Veranschaulichung verwendet wird), bedeutet dies, dass nur zwei Ports für Audio reserviert sind.</span><span class="sxs-lookup"><span data-stu-id="1e58e-115">If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio.</span></span> <span data-ttu-id="1e58e-116">Wenn der erste Port Port 50000 ist und insgesamt zwei Ports vorhanden sind, bedeutet dies, dass der zweite Port Port 50001 sein muss (Portbereiche müssen zusammenhängend sein).</span><span class="sxs-lookup"><span data-stu-id="1e58e-116">If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous).</span></span> <span data-ttu-id="1e58e-117">Infolgedessen wäre der Portbereich für Audio die Ports 50000 bis 50001 inklusive.</span><span class="sxs-lookup"><span data-stu-id="1e58e-117">As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="1e58e-118">Beachten Sie auch, dass Anwendungsserver und Vermittlungsserver nur QoS für Audio unterstützen. Sie müssen die Video-oder Anwendungsfreigabe Anschlüsse auf Ihren Anwendungsservern oder Vermittlungsservern nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="1e58e-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="1e58e-119">Wenn Sie die vorstehenden drei Befehle ausführen, sehen Sie, dass die Standard Port Werte für lync Server 2013 wie folgt konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="1e58e-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1e58e-120">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1e58e-120">Property</span></span></th>
<th><span data-ttu-id="1e58e-121">Konferenz Server</span><span class="sxs-lookup"><span data-stu-id="1e58e-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="1e58e-122">Anwendungs Server</span><span class="sxs-lookup"><span data-stu-id="1e58e-122">Application Server</span></span></th>
<th><span data-ttu-id="1e58e-123">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="1e58e-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1e58e-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="1e58e-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="1e58e-125">49152</span><span class="sxs-lookup"><span data-stu-id="1e58e-125">49152</span></span></p></td>
<td><p><span data-ttu-id="1e58e-126">49152</span><span class="sxs-lookup"><span data-stu-id="1e58e-126">49152</span></span></p></td>
<td><p><span data-ttu-id="1e58e-127">49152</span><span class="sxs-lookup"><span data-stu-id="1e58e-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e58e-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="1e58e-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="1e58e-129">8348</span><span class="sxs-lookup"><span data-stu-id="1e58e-129">8348</span></span></p></td>
<td><p><span data-ttu-id="1e58e-130">8348</span><span class="sxs-lookup"><span data-stu-id="1e58e-130">8348</span></span></p></td>
<td><p><span data-ttu-id="1e58e-131">8348</span><span class="sxs-lookup"><span data-stu-id="1e58e-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e58e-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="1e58e-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="1e58e-133">57501</span><span class="sxs-lookup"><span data-stu-id="1e58e-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e58e-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="1e58e-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="1e58e-135">8034</span><span class="sxs-lookup"><span data-stu-id="1e58e-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1e58e-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="1e58e-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="1e58e-137">49152</span><span class="sxs-lookup"><span data-stu-id="1e58e-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1e58e-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="1e58e-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="1e58e-139">16383</span><span class="sxs-lookup"><span data-stu-id="1e58e-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1e58e-140">Wie bereits erwähnt, sollten Sie beim Konfigurieren von lync Server-Ports für QoS sicherstellen, dass: 1) audioporteinstellungen für Ihre Konferenz-, Anwendungs-und Vermittlungsserver identisch sind. und, 2) die Portbereiche überlappen sich nicht.</span><span class="sxs-lookup"><span data-stu-id="1e58e-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="1e58e-141">Wenn Sie die obige Tabelle genau betrachten, sehen Sie, dass die Portbereiche für die drei Servertypen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="1e58e-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="1e58e-142">So ist beispielsweise der Start-Audioport auf Port 49152 für jeden Servertyp eingestellt, und die Gesamtanzahl der für Audio reservierten Ports auf jedem Server ist ebenfalls identisch: 8348.</span><span class="sxs-lookup"><span data-stu-id="1e58e-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="1e58e-143">Die Portbereiche überlappen sich jedoch: Audioanschlüsse beginnen bei Port 49152, aber auch die Ports, die für die Anwendungsfreigabe reserviert sind.</span><span class="sxs-lookup"><span data-stu-id="1e58e-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="1e58e-144">Um die Qualität des Diensts optimal zu nutzen, sollte die Anwendungsfreigabe neu konfiguriert werden, um einen eindeutigen Portbereich zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e58e-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="1e58e-145">So können Sie beispielsweise die Anwendungsfreigabe so konfigurieren, dass Sie bei Port 40803 startet und 8348-Ports verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e58e-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="1e58e-146">(Warum 8348-Ports?</span><span class="sxs-lookup"><span data-stu-id="1e58e-146">(Why 8348 ports?</span></span> <span data-ttu-id="1e58e-147">Wenn Sie diese Werte zusammen--40803 + 8348-hinzufügen, bedeutet dies, dass die Anwendungsfreigabe Ports 40803 über Port 49150 verwendet.</span><span class="sxs-lookup"><span data-stu-id="1e58e-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="1e58e-148">Da Audioanschlüsse erst nach Port 49152 gestartet werden, haben Sie keine überlappenden Portbereiche mehr.)</span><span class="sxs-lookup"><span data-stu-id="1e58e-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="1e58e-149">Nachdem Sie den neuen Portbereich für die Anwendungsfreigabe ausgewählt haben, können Sie die Änderung mithilfe des Cmdlets "festlegen-CsConferencingServer" vornehmen.</span><span class="sxs-lookup"><span data-stu-id="1e58e-149">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet.</span></span> <span data-ttu-id="1e58e-150">Diese Änderung muss nicht auf Ihren Anwendungsservern oder auf Ihren Vermittlungsservern vorgenommen werden, da diese Server keinen Anwendungsfreigabe Verkehr verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="1e58e-150">This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic.</span></span> <span data-ttu-id="1e58e-151">Sie müssen nur die Portwerte auf diesen Servern ändern, wenn Sie sich entscheiden, die für den Audioverkehr verwendeten Ports neu zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1e58e-151">You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="1e58e-152">Um die Portwerte für die Anwendungsfreigabe auf einem einzelnen Konferenzserver zu ändern, führen Sie in der lync Server-Verwaltungsshell einen ähnlichen Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1e58e-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="1e58e-153">Wenn Sie diese Änderungen auf allen Konferenzservern vornehmen möchten, können Sie stattdessen diesen Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="1e58e-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="1e58e-154">Nachdem Sie die Porteinstellungen geändert haben, sollten Sie jeden von den Änderungen betroffenen Dienst beenden und neu starten.</span><span class="sxs-lookup"><span data-stu-id="1e58e-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="1e58e-155">Es ist nicht zwingend erforderlich, dass Ihre Konferenzserver, Anwendungsserver und Vermittlungsserver exakt denselben Portbereich verwenden. die einzige echte Anforderung ist, dass Sie eindeutige Portbereiche auf allen ihren Servern beiseite legen.</span><span class="sxs-lookup"><span data-stu-id="1e58e-155">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers.</span></span> <span data-ttu-id="1e58e-156">Die Verwaltung ist jedoch in der Regel einfacher, wenn Sie die gleichen Ports auf allen Servern verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e58e-156">However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

