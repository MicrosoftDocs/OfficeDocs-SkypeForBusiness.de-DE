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
ms.openlocfilehash: b6eddf59f6fe4b2575e0e7d70adddb2e94c90e05
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-port-ranges-for-your-edge-servers-in-lync-server-2013"></a>Konfigurieren von Portbereichen für Ihre Edgeserver in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-07-24_

Bei Edge-Servern müssen Sie keine separaten Portbereiche für Audio-, Video-und Anwendungsfreigaben konfigurieren. Ebenso müssen die für Edgeserver verwendeten Portbereiche nicht den Portbereichen entsprechen, die mit ihren Konferenz-, Anwendungs-und Vermittlungsservern verwendet werden. Bevor wir mit unserem Beispiel fortfahren, ist es wichtig zu betonen, dass diese Option zwar vorhanden ist, aber wir empfehlen, die Portbereiche nicht zu ändern, da sich dies negativ auf einige Szenarien auswirken kann, wenn Sie den 50000-Portbereich verschieben.

Angenommen, Sie haben Ihre Konferenz-, Anwendungs-und Vermittlungsserver so konfiguriert, dass Sie diese Portbereiche verwenden:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pakettyp</th>
<th>Port wird gestartet</th>
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


Wie Sie sehen können, beginnen Ihre Portbereiche für Audio-, Video-und Anwendungsfreigabe bei Port 40803 und umfassen insgesamt 24732-Ports. Wenn Sie möchten, können Sie einen bestimmten Edgeserver so konfigurieren, dass diese Gesamt Port Werte verwendet werden, indem Sie in der lync Server-Verwaltungsshell einen ähnlichen Befehl ausführen:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Oder verwenden Sie den folgenden Befehl, um alle Edgeserver in Ihrer Organisation gleichzeitig zu konfigurieren:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Sie können die aktuellen Porteinstellungen für Ihre Edgeserver mithilfe dieses Befehls der lync Server-Verwaltungsshell überprüfen:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

Auch wenn wir diese Optionen zur Verfügung stellen, empfehlen wir Ihnen dringend, die Einstellungen für die Port-Konfiguration zu belassen.

</div>

<span> </span>

</div>

</div>

</div>

