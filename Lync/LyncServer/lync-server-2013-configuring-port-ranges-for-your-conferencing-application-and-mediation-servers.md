---
title: 'Lync Server 2013: Konfigurieren von Portbereichen für Ihre Konferenz-, Anwendungs-und Vermittlungsserver'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Conferencing, Application, and Mediation servers
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
ms.date: 05/01/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecd505990b9a060c3b669700ea9192dc1ad6b84c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a><span data-ttu-id="c7004-102">Konfigurieren von Portbereichen in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="c7004-102">Configuring port ranges in Lync Server 2013 for your Conferencing, Application, and Mediation servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7004-103">_**Letztes Änderungsstand des Themas:** 2015-04-30_</span><span class="sxs-lookup"><span data-stu-id="c7004-103">_**Topic Last Modified:** 2015-04-30_</span></span>

<span data-ttu-id="c7004-p101">Um eine QoS-Infrastruktur (Quality of Service, Dienstqualität) zu implementieren, wird empfohlen, identische Portbereiche für Audio-, Video- und Anwendungsfreigaben auf Ihren Konferenz-, Anwendungs- und Vermittlungsservern zu konfigurieren. Darüber hinaus sollten Überschneidungen dieser Portbereiche vermieden werden. Ein einfaches Beispiel hierzu: Angenommen, die Ports 10000 bis 10999 werden für die Übertragung von Videos auf Ihren Konferenzservern verwendet. Dies bedeutet, dass die Ports 10000 bis 10999 auch für die Übertragung von Videos auf Ihren Anwendungs- und Vermittlungsservern reserviert werden müssen. Andernfalls kann die Dienstqualität nicht wie vorgesehen gewährleistet werden.</span><span class="sxs-lookup"><span data-stu-id="c7004-p101">In order to implement Quality of Service, you should configure identical port ranges for audio, video, and application sharing on your Conferencing, Application, and Mediation servers; furthermore, those port ranges must not overlap in any way. To use a simple example, suppose you use ports 10000 through 10999 for video on your Conferencing servers. That means that you must also reserve ports 10000 through 10999 for video on your Application and Mediation servers. If you do not, QoS will not work as expected.</span></span>

<span data-ttu-id="c7004-p102">Nehmen Sie analog dazu an, dass die Ports 10000 bis 10999 für die Übertragung von Videos reserviert wurden, während für die Übertragung von Audiosignalen die Ports 10500 bis 11999 vorgesehen sind. Dies kann zu Problemen mit der Dienstqualität führen, weil sich die Portbereiche überschneiden. Die QoS-Infrastruktur verlangt, dass jede Modalität über eine eindeutige Gruppe von Ports verfügt: Wenn Sie die Ports 10000 bis 10999 für die Übertragung von Videos verwenden, müssen Sie einen anderen Bereich (z. B. 11000 bis 11999) für die Übertragung von Audiosignalen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7004-p102">Similarly, suppose you reserve ports 10000 through 10999 for video, but then reserve ports 10500 through 11999 for audio. This can create problems for Quality of Service, because the port ranges overlap. With QoS, each modality must have a unique set of ports: if you use ports 10000 through 10999 for video, then you'll have to use a different range (for example, 11000 through 11999 for audio).</span></span>

<span data-ttu-id="c7004-111">Standardmäßig überlappen sich Audio-und Video Portbereiche nicht in Microsoft lync Server 2013; die der Anwendungsfreigabe zugewiesenen Portbereiche überlappen sich jedoch sowohl mit den Audio-als auch den Video Portbereichen.</span><span class="sxs-lookup"><span data-stu-id="c7004-111">By default, audio and video port ranges do not overlap in Microsoft Lync Server 2013; however, the port ranges assigned to application sharing overlap with both the audio and video port ranges.</span></span> <span data-ttu-id="c7004-112">(Was wiederum bedeutet, dass keines dieser Bereiche eindeutig ist.) Sie können die vorhandenen Portbereiche für Ihre Konferenz-, Anwendungs-und Vermittlungsserver überprüfen, indem Sie die folgenden drei Befehle in der lync Server 2013 Verwaltungsshell ausführen:</span><span class="sxs-lookup"><span data-stu-id="c7004-112">(Which, in turn, means that none of these ranges are unique.) You can verify the existing port ranges for your Conferencing, Application, and Mediation servers by running the following three commands from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> <span data-ttu-id="c7004-p104">Wie Sie anhand der vorstehenden Befehle erkennen können, wurden jedem Porttyp – für Audio-, Video- und Anwendungsfreigaben – zwei separate Eigenschaftenwerte zugewiesen: der Portbeginn und die Portanzahl. Der Portbeginn gibt den ersten Port an, der für diese Modalität verwendet wird. Wenn beispielsweise für den Audioportbeginn der Wert "50000" festgelegt wurde, ist der Port 50000 der erste Port, der für die Übertragung von Audiosignalen verwendet wird. Wenn die Audioportanzahl mit 2 angegeben wurde, stehen nur zwei Ports für Audiosignale zur Verfügung. (Dieser Wert dient ausschließlich der Veranschaulichung. Es handelt sich nicht um einen gültigen Wert.) Wenn der erste Port der Port 50000 ist und insgesamt nur zwei Ports vorhanden sind, muss der zweite Port 50001 sein (Portbereiche müssen immer zusammenhängend sein). Der Portbereich für Audiosignale reicht also von Port 50000 bis einschließlich Port 50001.</span><span class="sxs-lookup"><span data-stu-id="c7004-p104">As you can see in the preceding commands, each port type – audio, video, and application sharing – is assigned two separate property values: the port start and the port count. The port start indicates the first port used for that modality; for example, if the audio port start is equal to 50000 that means that the first port used for audio traffic is port 50000. If the audio port count is 2 (which is not a valid value, but is used here for illustration purposes) that means that only 2 ports are allocated for audio. If the first port is port 50000 and there are a total of two ports, that means the second port must be port 50001 (port ranges have to be contiguous). As a result, the port range for audio would be ports 50000 through 50001, inclusive.</span></span><BR><span data-ttu-id="c7004-118">Beachten Sie ferner, dass Anwendungs- und Vermittlungsserver QoS nur für Audio unterstützen. Es ist nicht erforderlich, die Video- oder Anwendungsfreigabeports in Ihren Anwendungs- oder Vermittlungsservern zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c7004-118">Note, too that Application server and Mediation server only support QoS for audio; you do not need to change video or application sharing ports in your Application servers or Mediation servers.</span></span>



</div>

<span data-ttu-id="c7004-119">Wenn Sie die drei obigen Befehle ausführen, sehen Sie, dass die Standard Port Werte für lync Server 2013 wie folgt konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="c7004-119">If you run the preceding three commands you'll see that the default port values for Lync Server 2013 are configured like this:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7004-120">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="c7004-120">Property</span></span></th>
<th><span data-ttu-id="c7004-121">Konferenzserver</span><span class="sxs-lookup"><span data-stu-id="c7004-121">Conferencing Server</span></span></th>
<th><span data-ttu-id="c7004-122">Anwendungsserver</span><span class="sxs-lookup"><span data-stu-id="c7004-122">Application Server</span></span></th>
<th><span data-ttu-id="c7004-123">Vermittlungsserver</span><span class="sxs-lookup"><span data-stu-id="c7004-123">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7004-124">AudioPortStart</span><span class="sxs-lookup"><span data-stu-id="c7004-124">AudioPortStart</span></span></p></td>
<td><p><span data-ttu-id="c7004-125">49152</span><span class="sxs-lookup"><span data-stu-id="c7004-125">49152</span></span></p></td>
<td><p><span data-ttu-id="c7004-126">49152</span><span class="sxs-lookup"><span data-stu-id="c7004-126">49152</span></span></p></td>
<td><p><span data-ttu-id="c7004-127">49152</span><span class="sxs-lookup"><span data-stu-id="c7004-127">49152</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7004-128">AudioPortCount</span><span class="sxs-lookup"><span data-stu-id="c7004-128">AudioPortCount</span></span></p></td>
<td><p><span data-ttu-id="c7004-129">8348</span><span class="sxs-lookup"><span data-stu-id="c7004-129">8348</span></span></p></td>
<td><p><span data-ttu-id="c7004-130">8348</span><span class="sxs-lookup"><span data-stu-id="c7004-130">8348</span></span></p></td>
<td><p><span data-ttu-id="c7004-131">8348</span><span class="sxs-lookup"><span data-stu-id="c7004-131">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7004-132">VideoPortStart</span><span class="sxs-lookup"><span data-stu-id="c7004-132">VideoPortStart</span></span></p></td>
<td><p><span data-ttu-id="c7004-133">57501</span><span class="sxs-lookup"><span data-stu-id="c7004-133">57501</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7004-134">VideoPortCount</span><span class="sxs-lookup"><span data-stu-id="c7004-134">VideoPortCount</span></span></p></td>
<td><p><span data-ttu-id="c7004-135">8034</span><span class="sxs-lookup"><span data-stu-id="c7004-135">8034</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7004-136">ApplicationSharingPortStart</span><span class="sxs-lookup"><span data-stu-id="c7004-136">ApplicationSharingPortStart</span></span></p></td>
<td><p><span data-ttu-id="c7004-137">49152</span><span class="sxs-lookup"><span data-stu-id="c7004-137">49152</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7004-138">ApplicationSharingPortCount</span><span class="sxs-lookup"><span data-stu-id="c7004-138">ApplicationSharingPortCount</span></span></p></td>
<td><p><span data-ttu-id="c7004-139">16383</span><span class="sxs-lookup"><span data-stu-id="c7004-139">16383</span></span></p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c7004-140">Wie bereits erwähnt, sollten Sie beim Konfigurieren lync Server-Ports für QoS sicherstellen, dass: 1) audioporteinstellungen in ihren Konferenz-, Anwendungs-und Vermittlungsservern identisch sind; und, 2) die Portbereiche überlappen sich nicht.</span><span class="sxs-lookup"><span data-stu-id="c7004-140">As noted previously, when configuring Lync Server ports for QoS, you should ensure that: 1) audio port settings are identical across yours Conferencing, Application, and Mediation servers; and, 2) port ranges do not overlap.</span></span> <span data-ttu-id="c7004-141">Wenn Sie sich die obige Tabelle genauer ansehen, werden Sie sehen, dass die Portbereiche in den drei Servertypen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="c7004-141">If you look closely at the preceding table, you will see that the port ranges are identical across the three server types.</span></span> <span data-ttu-id="c7004-142">Beispielsweise ist der Ausgangs-Audioport auf jedem Servertyp auf Port 49152 festgelegt, und die Gesamtanzahl der Ports, die für Audio auf jedem Server reserviert sind, ist ebenfalls identisch: 8348.</span><span class="sxs-lookup"><span data-stu-id="c7004-142">For example, the starting audio port is set to port 49152 on each server type, and the total number of ports reserved for audio in each server is also identical: 8348.</span></span> <span data-ttu-id="c7004-143">Die Portbereiche überlappen sich jedoch: Audioports beginnen bei Port 49152, aber auch die Ports, die für die Anwendungsfreigabe reserviert sind.</span><span class="sxs-lookup"><span data-stu-id="c7004-143">However, the port ranges overlap: audio ports start at port 49152, but so do the ports set aside for application sharing.</span></span> <span data-ttu-id="c7004-144">Um die Dienstqualität optimal nutzen zu können, sollte die Anwendungsfreigabe so konfiguriert werden, dass ein eindeutiger Portbereich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c7004-144">In order to make optimal use of Quality of Service, application sharing should be reconfigured to use a unique port range.</span></span> <span data-ttu-id="c7004-145">Beispielsweise können Sie die Anwendungsfreigabe so konfigurieren, dass Sie bei Port 40803 beginnt und 8348-Ports verwendet.</span><span class="sxs-lookup"><span data-stu-id="c7004-145">For example, you could configure application sharing to start at port 40803 and to use 8348 ports.</span></span> <span data-ttu-id="c7004-146">(Warum 8348 Ports?</span><span class="sxs-lookup"><span data-stu-id="c7004-146">(Why 8348 ports?</span></span> <span data-ttu-id="c7004-147">Wenn Sie diese Werte zusammen addieren--40803 + 8348--bedeutet dies, dass für die Anwendungsfreigabe Ports 40803 bis Port 49150 verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7004-147">If you add those values together -- 40803 + 8348 -- that means that application sharing will use ports 40803 through port 49150.</span></span> <span data-ttu-id="c7004-148">Da Audioports erst nach Port 49152 beginnen, können Sie keine überlappenden Portbereiche mehr haben.)</span><span class="sxs-lookup"><span data-stu-id="c7004-148">Because audio ports do not begin until port 49152, you will no longer have any overlapping port ranges.)</span></span>

<span data-ttu-id="c7004-p106">Nachdem Sie den neuen Portbereich für die Anwendungsfreigabe ausgewählt haben, können Sie die Änderungen mit dem Set-CsConferencingServer-Cmdlet vornehmen. Diese Änderungen müssen nicht auf den Anwendungsservern oder auf den Vermittlungsservern durchgeführt werden, da sie keinen Datenverkehr von Anwendungsfreigaben verarbeiten. Sie müssen die Portwerte auf diesen Servern lediglich ändern, wenn Sie die Ports für die Übertragung von Audiosignalen neu zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c7004-p106">After you have selected the new port range for application sharing you can make your change by using the Set-CsConferencingServer cmdlet. This change does not need to be made on your Application servers or on your Mediation servers, because these servers do not handle application sharing traffic. You only need to change port values on these servers if you decide to reassign the ports used for audio traffic.</span></span>

<span data-ttu-id="c7004-152">Um die Portwerte für die Anwendungsfreigabe auf einem einzelnen Konferenzserver zu ändern, führen Sie einen Befehl aus dem lync Server-Verwaltungsshell aus, der dem folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="c7004-152">To modify the port values for application sharing on a single Conferencing server run a command similar to this from within the Lync Server Management Shell:</span></span>

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

<span data-ttu-id="c7004-153">Wenn Sie diese Änderung auf allen Portservern vornehmen möchten, führen Sie stattdessen den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="c7004-153">If you want to make these changes on all your Conferencing servers you can run this command instead:</span></span>

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

<span data-ttu-id="c7004-154">Halten Sie, nachdem die Porteinstellungen geändert haben, die betroffenen Dienste an, und starten Sie sie neu.</span><span class="sxs-lookup"><span data-stu-id="c7004-154">After changing port settings you should stop and then restart each service affected by the changes.</span></span>

<span data-ttu-id="c7004-p107">Ihre Konferenz-, Anwendungs- und Vermittlungsserver müssen nicht notwendigerweise den gleichen Portbereich verwenden. Allerdings müssen auf allen Servern unbedingt eindeutige Portbereiche reserviert werden. Wenn Sie jedoch die gleichen Portbereiche auf allen Servern verwenden, wird dadurch die Verwaltung deutlich erleichtert.</span><span class="sxs-lookup"><span data-stu-id="c7004-p107">It is not mandatory that your Conferencing servers, Application servers, and Mediation servers share the exact same port range; the only true requirement is that you set aside unique port ranges on all your servers. However, administration will typically be easier if you use the same set of ports on all your servers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

