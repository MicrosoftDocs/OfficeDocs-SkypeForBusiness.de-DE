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
ms.openlocfilehash: 0ce17300c6504989d132cb27301128bfbc568870
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Konfigurieren von Portbereichen für Ihre Edgeserver in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-07-24_

Mit Edgeserver müssen Sie keine separaten Portbereiche für Audio-, Video-und Anwendungsfreigaben konfigurieren. Dementsprechend müssen die für Edgeserver verwendeten Portbereiche nicht den Portbereichen entsprechen, die mit ihren Konferenz-, Anwendungs-und Vermittlungsservern verwendet werden. Bevor wir mit unserem Beispiel fortfahren, sollten Sie darauf hinweisen, dass diese Option zwar vorhanden ist, es wird jedoch empfohlen, die Portbereiche nicht zu ändern, da sich dies nachteilig auf einige Szenarien auswirken kann, wenn Sie den 50000-Portbereich verlassen.

Angenommen, Sie haben Ihre Konferenz-, Anwendungs-und Vermittlungsserver für die Verwendung dieser Portbereiche konfiguriert:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pakettyp</th>
<th>Startport</th>
<th>Anzahl der reservierten Ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anwendungsfreigabe</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>Audio</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>Video</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>Summen</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Wie Sie sehen können, beginnen die Portbereiche für die Audio-, Video-und Anwendungsfreigabe bei Port 40803 und umfassen insgesamt 24732 Ports. Wenn Sie es vorziehen, können Sie eine bestimmte Edgeserver so konfigurieren, dass diese Gesamt Port Werte verwendet werden, indem Sie einen Befehl aus dem lync Server-Verwaltungsshell ausführen, der diesem ähnlich ist:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Oder führen Sie den folgenden Befehl aus, um alle Edgeserver in Ihrer Organisation gleichzeitig zu konfigurieren:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Sie können die aktuellen Porteinstellungen für Ihre Edgeserver überprüfen, indem Sie den folgenden lync Server-Verwaltungsshell Befehl verwenden:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Auch wenn wir diese Optionen bereitstellen, wird dringend empfohlen, dass Sie die Einstellungen für die Portkonfiguration beibehalten.

</div>

<span> </span>

</div>

</div>

</div>

