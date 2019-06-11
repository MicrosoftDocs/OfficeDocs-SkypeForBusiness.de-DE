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

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren von Portbereichen in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-04-30_

Um die Qualität des Diensts zu implementieren, sollten Sie identische Portbereiche für die Audio-, Video-und Anwendungsfreigabe auf Ihren Konferenz-, Anwendungs-und Vermittlungsservern konfigurieren. Darüber hinaus dürfen sich diese Portbereiche in keiner Weise überlappen. Wenn Sie ein einfaches Beispiel verwenden möchten, nehmen Sie an, dass Sie die Ports 10000 bis 10999 für Video auf Ihren Konferenzservern verwenden. Das bedeutet, dass Sie auch Ports 10000 bis 10999 für Video auf Ihren Anwendungs-und Vermittlungsservern reservieren müssen. Wenn dies nicht der Fall ist, funktioniert QoS nicht erwartungsgemäß.

Nehmen Sie entsprechend an, dass Sie die Ports 10000 bis 10999 für Video reservieren, und dann die Ports 10500 bis 11999 für Audio reservieren. Dies kann zu Problemen bei der Dienstqualität führen, da sich die Portbereiche überlappen. Bei QoS muss jede Modalität über einen eindeutigen Satz von Ports verfügen: Wenn Sie Ports 10000 bis 10999 für Video verwenden, müssen Sie einen anderen Bereich verwenden (beispielsweise 11000 bis 11999 für Audio).

Standardmäßig überlappen sich Audio-und Video-Portbereiche in Microsoft lync Server 2013 nicht. die der Anwendungsfreigabe zugewiesenen Portbereiche überlappen sich jedoch sowohl mit dem Audio-als auch dem Video-Portbereich. (Was wiederum bedeutet, dass keiner dieser Bereiche eindeutig ist.) Sie können die vorhandenen Portbereiche für Ihre Konferenz-, Anwendungs-und Vermittlungsserver überprüfen, indem Sie die folgenden drei Befehle in der lync Server 2013-Verwaltungsshell ausführen:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> Wie in den vorstehenden Befehlen zu sehen ist, werden jedem Porttyp – Audio, Video und Anwendungsfreigabe – zwei getrennte Eigenschaftswerte zugewiesen: der Port Start und die Portanzahl. Der Port Start gibt den ersten Port an, der für diese Modalität verwendet wird; Wenn beispielsweise der Audioport-Start gleich 50000 ist, bedeutet dies, dass der erste Port für den Audioverkehr Port 50000 ist. Wenn die Anzahl der Audioanschlüsse 2 ist (was kein gültiger Wert ist, aber hier zur Veranschaulichung verwendet wird), bedeutet dies, dass nur zwei Ports für Audio reserviert sind. Wenn der erste Port Port 50000 ist und insgesamt zwei Ports vorhanden sind, bedeutet dies, dass der zweite Port Port 50001 sein muss (Portbereiche müssen zusammenhängend sein). Infolgedessen wäre der Portbereich für Audio die Ports 50000 bis 50001 inklusive.<BR>Beachten Sie auch, dass Anwendungsserver und Vermittlungsserver nur QoS für Audio unterstützen. Sie müssen die Video-oder Anwendungsfreigabe Anschlüsse auf Ihren Anwendungsservern oder Vermittlungsservern nicht ändern.



</div>

Wenn Sie die vorstehenden drei Befehle ausführen, sehen Sie, dass die Standard Port Werte für lync Server 2013 wie folgt konfiguriert sind:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Eigenschaft</th>
<th>Konferenz Server</th>
<th>Anwendungs Server</th>
<th>Vermittlungsserver</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>


Wie bereits erwähnt, sollten Sie beim Konfigurieren von lync Server-Ports für QoS sicherstellen, dass: 1) audioporteinstellungen für Ihre Konferenz-, Anwendungs-und Vermittlungsserver identisch sind. und, 2) die Portbereiche überlappen sich nicht. Wenn Sie die obige Tabelle genau betrachten, sehen Sie, dass die Portbereiche für die drei Servertypen identisch sind. So ist beispielsweise der Start-Audioport auf Port 49152 für jeden Servertyp eingestellt, und die Gesamtanzahl der für Audio reservierten Ports auf jedem Server ist ebenfalls identisch: 8348. Die Portbereiche überlappen sich jedoch: Audioanschlüsse beginnen bei Port 49152, aber auch die Ports, die für die Anwendungsfreigabe reserviert sind. Um die Qualität des Diensts optimal zu nutzen, sollte die Anwendungsfreigabe neu konfiguriert werden, um einen eindeutigen Portbereich zu verwenden. So können Sie beispielsweise die Anwendungsfreigabe so konfigurieren, dass Sie bei Port 40803 startet und 8348-Ports verwendet. (Warum 8348-Ports? Wenn Sie diese Werte zusammen--40803 + 8348-hinzufügen, bedeutet dies, dass die Anwendungsfreigabe Ports 40803 über Port 49150 verwendet. Da Audioanschlüsse erst nach Port 49152 gestartet werden, haben Sie keine überlappenden Portbereiche mehr.)

Nachdem Sie den neuen Portbereich für die Anwendungsfreigabe ausgewählt haben, können Sie die Änderung mithilfe des Cmdlets "festlegen-CsConferencingServer" vornehmen. Diese Änderung muss nicht auf Ihren Anwendungsservern oder auf Ihren Vermittlungsservern vorgenommen werden, da diese Server keinen Anwendungsfreigabe Verkehr verarbeiten. Sie müssen nur die Portwerte auf diesen Servern ändern, wenn Sie sich entscheiden, die für den Audioverkehr verwendeten Ports neu zuzuweisen.

Um die Portwerte für die Anwendungsfreigabe auf einem einzelnen Konferenzserver zu ändern, führen Sie in der lync Server-Verwaltungsshell einen ähnlichen Befehl aus:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Wenn Sie diese Änderungen auf allen Konferenzservern vornehmen möchten, können Sie stattdessen diesen Befehl ausführen:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Nachdem Sie die Porteinstellungen geändert haben, sollten Sie jeden von den Änderungen betroffenen Dienst beenden und neu starten.

Es ist nicht zwingend erforderlich, dass Ihre Konferenzserver, Anwendungsserver und Vermittlungsserver exakt denselben Portbereich verwenden. die einzige echte Anforderung ist, dass Sie eindeutige Portbereiche auf allen ihren Servern beiseite legen. Die Verwaltung ist jedoch in der Regel einfacher, wenn Sie die gleichen Ports auf allen Servern verwenden.

</div>

<span> </span>

</div>

</div>

</div>

