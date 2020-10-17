---
title: 'Lync Server 2013: Konfigurieren von Portbereichen für Ihre Edgeserver'
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
ms.openlocfilehash: a9124ba5b2a800190f49a9ac81fd9a2477eac215
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535022"
---
# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a><span data-ttu-id="a00d2-102">Konfigurieren von Portbereichen für Ihre Edgeserver in lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a00d2-102">Configuring port ranges for your Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a00d2-103">_**Letztes Änderungsstand des Themas:** 2015-07-24_</span><span class="sxs-lookup"><span data-stu-id="a00d2-103">_**Topic Last Modified:** 2015-07-24_</span></span>

<span data-ttu-id="a00d2-104">Mit Edgeserver müssen Sie keine separaten Portbereiche für Audio-, Video-und Anwendungsfreigaben konfigurieren. Dementsprechend müssen die für Edgeserver verwendeten Portbereiche nicht den Portbereichen entsprechen, die mit ihren Konferenz-, Anwendungs-und Vermittlungsservern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a00d2-104">With Edge servers you do not have to configure separate port ranges for audio, video, and application sharing; likewise, the port ranges used for Edge servers do not have to match the port ranges used with your Conferencing, Application, and Mediation servers.</span></span> <span data-ttu-id="a00d2-105">Bevor wir mit unserem Beispiel fortfahren, sollten Sie darauf hinweisen, dass diese Option zwar vorhanden ist, es wird jedoch empfohlen, die Portbereiche nicht zu ändern, da sich dies nachteilig auf einige Szenarien auswirken kann, wenn Sie den 50000-Portbereich verlassen.</span><span class="sxs-lookup"><span data-stu-id="a00d2-105">Before we proceed with our example, it's important to stress that while this option exists, we do recommend you not change the port ranges, as this may adversely affect some scenarios if you move out of the 50000 port range.</span></span>

<span data-ttu-id="a00d2-106">Angenommen, Sie haben Ihre Konferenz-, Anwendungs-und Vermittlungsserver für die Verwendung dieser Portbereiche konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="a00d2-106">For example, suppose you have configured your Conferencing, Application, and Mediation servers to use these port ranges:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a00d2-107">Pakettyp</span><span class="sxs-lookup"><span data-stu-id="a00d2-107">Packet Type</span></span></th>
<th><span data-ttu-id="a00d2-108">Startport</span><span class="sxs-lookup"><span data-stu-id="a00d2-108">Starting Port</span></span></th>
<th><span data-ttu-id="a00d2-109">Anzahl der reservierten Ports</span><span class="sxs-lookup"><span data-stu-id="a00d2-109">Number of Ports Reserved</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a00d2-110">Anwendungsfreigabe</span><span class="sxs-lookup"><span data-stu-id="a00d2-110">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="a00d2-111">40803</span><span class="sxs-lookup"><span data-stu-id="a00d2-111">40803</span></span></p></td>
<td><p><span data-ttu-id="a00d2-112">8348</span><span class="sxs-lookup"><span data-stu-id="a00d2-112">8348</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00d2-113">Audio</span><span class="sxs-lookup"><span data-stu-id="a00d2-113">Audio</span></span></p></td>
<td><p><span data-ttu-id="a00d2-114">49152</span><span class="sxs-lookup"><span data-stu-id="a00d2-114">49152</span></span></p></td>
<td><p><span data-ttu-id="a00d2-115">8348</span><span class="sxs-lookup"><span data-stu-id="a00d2-115">8348</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a00d2-116">Video</span><span class="sxs-lookup"><span data-stu-id="a00d2-116">Video</span></span></p></td>
<td><p><span data-ttu-id="a00d2-117">57500</span><span class="sxs-lookup"><span data-stu-id="a00d2-117">57500</span></span></p></td>
<td><p><span data-ttu-id="a00d2-118">8034</span><span class="sxs-lookup"><span data-stu-id="a00d2-118">8034</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a00d2-119"><strong>Summen</strong></span><span class="sxs-lookup"><span data-stu-id="a00d2-119"><strong>Totals</strong></span></span></p></td>
<td><p>--</p></td>
<td><p><span data-ttu-id="a00d2-120">24730</span><span class="sxs-lookup"><span data-stu-id="a00d2-120">24730</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a00d2-121">Wie Sie sehen können, beginnen die Portbereiche für die Audio-, Video-und Anwendungsfreigabe bei Port 40803 und umfassen insgesamt 24732 Ports.</span><span class="sxs-lookup"><span data-stu-id="a00d2-121">As you can see, your port ranges for audio, video, and application sharing start at port 40803 and encompass a total of 24732 ports.</span></span> <span data-ttu-id="a00d2-122">Wenn Sie es vorziehen, können Sie eine bestimmte Edgeserver so konfigurieren, dass diese Gesamt Port Werte verwendet werden, indem Sie einen Befehl aus dem lync Server-Verwaltungsshell ausführen, der diesem ähnlich ist:</span><span class="sxs-lookup"><span data-stu-id="a00d2-122">If you prefer, you can configure a given Edge Server to use these overall port values by running a command similar to this one from within the Lync Server Management Shell:</span></span>

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

<span data-ttu-id="a00d2-123">Oder führen Sie den folgenden Befehl aus, um alle Edgeserver in Ihrer Organisation gleichzeitig zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="a00d2-123">Or, use the following command to simultaneously configure all the Edge Servers in your organization:</span></span>

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

<span data-ttu-id="a00d2-124">Sie können die aktuellen Porteinstellungen für Ihre Edgeserver überprüfen, indem Sie den folgenden lync Server-Verwaltungsshell Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="a00d2-124">You can verify the current port settings for your Edge Servers by using this Lync Server Management Shell command:</span></span>

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

<span data-ttu-id="a00d2-125">Auch wenn wir diese Optionen bereitstellen, wird dringend empfohlen, dass Sie die Einstellungen für die Portkonfiguration beibehalten.</span><span class="sxs-lookup"><span data-stu-id="a00d2-125">Again, while we do provide these options, we strongly recommend you leave things as they are for the port configuration.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

