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

# <a name="configuring-port-ranges-in-lync-server-2013-for-your-conferencing-application-and-mediation-servers"></a>Konfigurieren von Portbereichen in lync Server 2013 für Ihre Konferenz-, Anwendungs-und Vermittlungsserver

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-04-30_

Um eine QoS-Infrastruktur (Quality of Service, Dienstqualität) zu implementieren, wird empfohlen, identische Portbereiche für Audio-, Video- und Anwendungsfreigaben auf Ihren Konferenz-, Anwendungs- und Vermittlungsservern zu konfigurieren. Darüber hinaus sollten Überschneidungen dieser Portbereiche vermieden werden. Ein einfaches Beispiel hierzu: Angenommen, die Ports 10000 bis 10999 werden für die Übertragung von Videos auf Ihren Konferenzservern verwendet. Dies bedeutet, dass die Ports 10000 bis 10999 auch für die Übertragung von Videos auf Ihren Anwendungs- und Vermittlungsservern reserviert werden müssen. Andernfalls kann die Dienstqualität nicht wie vorgesehen gewährleistet werden.

Nehmen Sie analog dazu an, dass die Ports 10000 bis 10999 für die Übertragung von Videos reserviert wurden, während für die Übertragung von Audiosignalen die Ports 10500 bis 11999 vorgesehen sind. Dies kann zu Problemen mit der Dienstqualität führen, weil sich die Portbereiche überschneiden. Die QoS-Infrastruktur verlangt, dass jede Modalität über eine eindeutige Gruppe von Ports verfügt: Wenn Sie die Ports 10000 bis 10999 für die Übertragung von Videos verwenden, müssen Sie einen anderen Bereich (z. B. 11000 bis 11999) für die Übertragung von Audiosignalen verwenden.

Standardmäßig überlappen sich Audio-und Video Portbereiche nicht in Microsoft lync Server 2013; die der Anwendungsfreigabe zugewiesenen Portbereiche überlappen sich jedoch sowohl mit den Audio-als auch den Video Portbereichen. (Was wiederum bedeutet, dass keines dieser Bereiche eindeutig ist.) Sie können die vorhandenen Portbereiche für Ihre Konferenz-, Anwendungs-und Vermittlungsserver überprüfen, indem Sie die folgenden drei Befehle in der lync Server 2013 Verwaltungsshell ausführen:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

<div>


> [!WARNING]  
> Wie Sie anhand der vorstehenden Befehle erkennen können, wurden jedem Porttyp – für Audio-, Video- und Anwendungsfreigaben – zwei separate Eigenschaftenwerte zugewiesen: der Portbeginn und die Portanzahl. Der Portbeginn gibt den ersten Port an, der für diese Modalität verwendet wird. Wenn beispielsweise für den Audioportbeginn der Wert "50000" festgelegt wurde, ist der Port 50000 der erste Port, der für die Übertragung von Audiosignalen verwendet wird. Wenn die Audioportanzahl mit 2 angegeben wurde, stehen nur zwei Ports für Audiosignale zur Verfügung. (Dieser Wert dient ausschließlich der Veranschaulichung. Es handelt sich nicht um einen gültigen Wert.) Wenn der erste Port der Port 50000 ist und insgesamt nur zwei Ports vorhanden sind, muss der zweite Port 50001 sein (Portbereiche müssen immer zusammenhängend sein). Der Portbereich für Audiosignale reicht also von Port 50000 bis einschließlich Port 50001.<BR>Beachten Sie ferner, dass Anwendungs- und Vermittlungsserver QoS nur für Audio unterstützen. Es ist nicht erforderlich, die Video- oder Anwendungsfreigabeports in Ihren Anwendungs- oder Vermittlungsservern zu ändern.



</div>

Wenn Sie die drei obigen Befehle ausführen, sehen Sie, dass die Standard Port Werte für lync Server 2013 wie folgt konfiguriert sind:


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
<th>Konferenzserver</th>
<th>Anwendungsserver</th>
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


Wie bereits erwähnt, sollten Sie beim Konfigurieren lync Server-Ports für QoS sicherstellen, dass: 1) audioporteinstellungen in ihren Konferenz-, Anwendungs-und Vermittlungsservern identisch sind; und, 2) die Portbereiche überlappen sich nicht. Wenn Sie sich die obige Tabelle genauer ansehen, werden Sie sehen, dass die Portbereiche in den drei Servertypen identisch sind. Beispielsweise ist der Ausgangs-Audioport auf jedem Servertyp auf Port 49152 festgelegt, und die Gesamtanzahl der Ports, die für Audio auf jedem Server reserviert sind, ist ebenfalls identisch: 8348. Die Portbereiche überlappen sich jedoch: Audioports beginnen bei Port 49152, aber auch die Ports, die für die Anwendungsfreigabe reserviert sind. Um die Dienstqualität optimal nutzen zu können, sollte die Anwendungsfreigabe so konfiguriert werden, dass ein eindeutiger Portbereich verwendet wird. Beispielsweise können Sie die Anwendungsfreigabe so konfigurieren, dass Sie bei Port 40803 beginnt und 8348-Ports verwendet. (Warum 8348 Ports? Wenn Sie diese Werte zusammen addieren--40803 + 8348--bedeutet dies, dass für die Anwendungsfreigabe Ports 40803 bis Port 49150 verwendet werden. Da Audioports erst nach Port 49152 beginnen, können Sie keine überlappenden Portbereiche mehr haben.)

Nachdem Sie den neuen Portbereich für die Anwendungsfreigabe ausgewählt haben, können Sie die Änderungen mit dem Set-CsConferencingServer-Cmdlet vornehmen. Diese Änderungen müssen nicht auf den Anwendungsservern oder auf den Vermittlungsservern durchgeführt werden, da sie keinen Datenverkehr von Anwendungsfreigaben verarbeiten. Sie müssen die Portwerte auf diesen Servern lediglich ändern, wenn Sie die Ports für die Übertragung von Audiosignalen neu zuweisen.

Um die Portwerte für die Anwendungsfreigabe auf einem einzelnen Konferenzserver zu ändern, führen Sie einen Befehl aus dem lync Server-Verwaltungsshell aus, der dem folgenden ähnelt:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Wenn Sie diese Änderung auf allen Portservern vornehmen möchten, führen Sie stattdessen den folgenden Befehl aus:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Halten Sie, nachdem die Porteinstellungen geändert haben, die betroffenen Dienste an, und starten Sie sie neu.

Ihre Konferenz-, Anwendungs- und Vermittlungsserver müssen nicht notwendigerweise den gleichen Portbereich verwenden. Allerdings müssen auf allen Servern unbedingt eindeutige Portbereiche reserviert werden. Wenn Sie jedoch die gleichen Portbereiche auf allen Servern verwenden, wird dadurch die Verwaltung deutlich erleichtert.

</div>

<span> </span>

</div>

</div>

</div>

