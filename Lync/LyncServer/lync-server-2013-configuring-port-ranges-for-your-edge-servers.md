---
title: 'Lync Server 2013: Konfigurieren von Portbereichen für Ihre Edgeserver'
description: 'Lync Server 2013: Konfigurieren von Portbereichen für Ihre Edgeserver.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring port ranges for your Edge Servers
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
ms.date: 07/24/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c085a5dbc32bbf56842984eae2ef8896ab895c65
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548251"
---
# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="127a5-103">Konfigurieren von Portbereichen für Ihre Edgeserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="127a5-103">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="127a5-104">_**Letztes Änderungsstand des Themas:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="127a5-104">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="127a5-105">Mit Edgeserver müssen Sie keine separaten Portbereiche für Audio-, Video-und Anwendungsfreigaben konfigurieren. Dementsprechend müssen die für Edgeserver verwendeten Portbereiche nicht den Portbereichen entsprechen, die mit ihren Konferenz-, Anwendungs-und Vermittlungsservern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="127a5-105">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="127a5-106">Bevor wir mit unserem Beispiel fortfahren, sollten Sie darauf hinweisen, dass diese Option zwar vorhanden ist, es wird jedoch empfohlen, die Portbereiche nicht zu ändern, da sich dies nachteilig auf einige Szenarien auswirken kann, wenn Sie den 50000-Portbereich verlassen.</span><span class="sxs-lookup"><span data-stu-id="127a5-106">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="127a5-107">Angenommen, Sie haben Ihre Konferenz-, Anwendungs-und Vermittlungsserver für die Verwendung dieser Portbereiche konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="127a5-107">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="127a5-108">Pakettyp</span><span class="sxs-lookup"><span data-stu-id="127a5-108">Packet Type</span></span></th>
<th><span data-ttu-id="127a5-109">Startport</span><span class="sxs-lookup"><span data-stu-id="127a5-109">Starting Port</span></span></th>
<th><span data-ttu-id="127a5-110">Anzahl der reservierten Ports</span><span class="sxs-lookup"><span data-stu-id="127a5-110">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="127a5-111">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="127a5-111">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="127a5-112">40803</span><span class="sxs-lookup"><span data-stu-id="127a5-112">40803</span></span></p></td>
<td><p><span data-ttu-id="127a5-113">8348</span><span class="sxs-lookup"><span data-stu-id="127a5-113">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="127a5-114">Audio</span><span class="sxs-lookup"><span data-stu-id="127a5-114">Audio</span></span></p></td>
<td><p><span data-ttu-id="127a5-115">49152</span><span class="sxs-lookup"><span data-stu-id="127a5-115">49152</span></span></p></td>
<td><p><span data-ttu-id="127a5-116">8348</span><span class="sxs-lookup"><span data-stu-id="127a5-116">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="127a5-117">Video</span><span class="sxs-lookup"><span data-stu-id="127a5-117">Video</span></span></p></td>
<td><p><span data-ttu-id="127a5-118">57500</span><span class="sxs-lookup"><span data-stu-id="127a5-118">57500</span></span></p></td>
<td><p><span data-ttu-id="127a5-119">8034</span><span class="sxs-lookup"><span data-stu-id="127a5-119">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="127a5-120"><strong>Summen</strong></span><span class="sxs-lookup"><span data-stu-id="127a5-120"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="127a5-121">24730</span><span class="sxs-lookup"><span data-stu-id="127a5-121">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="127a5-122">Wie Sie sehen können, beginnen die Portbereiche für die Audio-, Video-und Anwendungsfreigabe bei Port 40803 und umfassen insgesamt 24732 Ports.</span><span class="sxs-lookup"><span data-stu-id="127a5-122">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="127a5-123">Wenn Sie es vorziehen, können Sie eine bestimmte Edgeserver so konfigurieren, dass diese Gesamt Port Werte verwendet werden, indem Sie einen Befehl aus dem lync Server-Verwaltungsshell ausführen, der diesem ähnlich ist:</span><span class="sxs-lookup"><span data-stu-id="127a5-123">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="127a5-124">Oder führen Sie den folgenden Befehl aus, um alle Edgeserver in Ihrer Organisation gleichzeitig zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="127a5-124">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="127a5-125">Sie können die aktuellen Porteinstellungen für Ihre Edgeserver überprüfen, indem Sie den folgenden lync Server-Verwaltungsshell Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="127a5-125">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="127a5-126">Auch wenn wir diese Optionen bereitstellen, wird dringend empfohlen, dass Sie die Einstellungen für die Portkonfiguration beibehalten.</span><span class="sxs-lookup"><span data-stu-id="127a5-126">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

