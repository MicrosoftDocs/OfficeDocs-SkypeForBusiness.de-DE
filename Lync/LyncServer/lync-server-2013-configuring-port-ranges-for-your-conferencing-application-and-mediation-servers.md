---
title: Konfigurieren von Portbereichen für Konferenz-, Anwendungs- und Vermittlungsserver
TOCTitle: Konfigurieren von Portbereichen für Konferenz-, Anwendungs- und Vermittlungsserver
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204872(v=OCS.15)
ms:contentKeyID: 49293960
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Portbereichen für Konferenz-, Anwendungs- und Vermittlungsserver

 

_**Letztes Änderungsdatum des Themas:** 2015-04-30_

Um eine QoS-Infrastruktur (Quality of Service, Dienstqualität) zu implementieren, wird empfohlen, identische Portbereiche für Audio-, Video- und Anwendungsfreigaben auf Ihren Konferenz-, Anwendungs- und Vermittlungsservern zu konfigurieren. Darüber hinaus sollten Überschneidungen dieser Portbereiche vermieden werden. Ein einfaches Beispiel hierzu: Angenommen, die Ports 10000 bis 10999 werden für die Übertragung von Videos auf Ihren Konferenzservern verwendet. Dies bedeutet, dass die Ports 10000 bis 10999 auch für die Übertragung von Videos auf Ihren Anwendungs- und Vermittlungsservern reserviert werden müssen. Andernfalls kann die Dienstqualität nicht wie vorgesehen gewährleistet werden.

Nehmen Sie analog dazu an, dass die Ports 10000 bis 10999 für die Übertragung von Videos reserviert wurden, während für die Übertragung von Audiosignalen die Ports 10500 bis 11999 vorgesehen sind. Dies kann zu Problemen mit der Dienstqualität führen, weil sich die Portbereiche überschneiden. Die QoS-Infrastruktur verlangt, dass jede Modalität über eine eindeutige Gruppe von Ports verfügt: Wenn Sie die Ports 10000 bis 10999 für die Übertragung von Videos verwenden, müssen Sie einen anderen Bereich (z. B. 11000 bis 11999) für die Übertragung von Audiosignalen verwenden.

Die Audio- und Videoportbereiche in Microsoft Lync Server 2013 überschneiden sich standardmäßig nicht. Es liegt jedoch eine Überschneidung der Portbereiche für die Anwendungsfreigabe mit den Portbereichen für die Audio- und für die Videoübertragung vor. (Diese Portbereiche sind also nicht eindeutig.) Sie können die bestehenden Portbereiche Ihrer Konferenz-, Anwendungs- und Vermittlungsserver überprüfen, indem Sie die nachstehend angegebenen drei Befehle in der Verwaltungsshell für Lync Server 2013 ausführen:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount


> [!WARNING]
> Wie Sie anhand der vorstehenden Befehle erkennen können, wurden jedem Porttyp – für Audio-, Video- und Anwendungsfreigaben – zwei separate Eigenschaftenwerte zugewiesen: der Portbeginn und die Portanzahl. Der Portbeginn gibt den ersten Port an, der für diese Modalität verwendet wird. Wenn beispielsweise für den Audioportbeginn der Wert "50000" festgelegt wurde, ist der Port 50000 der erste Port, der für die Übertragung von Audiosignalen verwendet wird. Wenn die Audioportanzahl mit 2 angegeben wurde, stehen nur zwei Ports für Audiosignale zur Verfügung. (Dieser Wert dient ausschließlich der Veranschaulichung. Es handelt sich nicht um einen gültigen Wert.) Wenn der erste Port der Port 50000 ist und insgesamt nur zwei Ports vorhanden sind, muss der zweite Port 50001 sein (Portbereiche müssen immer zusammenhängend sein). Der Portbereich für Audiosignale reicht also von Port 50000 bis einschließlich Port 50001.<BR>Beachten Sie ferner, dass Anwendungs- und Vermittlungsserver QoS nur für Audio unterstützen. Es ist nicht erforderlich, die Video- oder Anwendungsfreigabeports in Ihren Anwendungs- oder Vermittlungsservern zu ändern.



Wenn Sie die drei vorstehenden Befehle ausführen, erkennen Sie, dass die Standardportwerte für Lync Server 2013 wie folgt konfiguriert wurden:


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


Wie bereits erläutert, müssen beim Konfigurieren von Lync Server-Ports einige Dinge beachtet werden: 1) Die Audioporteinstellungen müssen auf allen Konferenz-, Anwendungs- und Vermittlungsservern identisch sein. 2) Die Portbereiche dürfen sich nicht überschneiden. In der obenstehenden Tabelle sehen Sie, dass die Portbereiche aller drei Servertypen übereinstimmen. So ist der Startaudioport auf jedem Servertyp auf 49152 festgelegt, und insgesamt wurden auf jedem Server insgesamt 8348 Ports für die Übertragung von Audiosignalen reserviert. Allerdings liegt eine Überlappung der Portbereiche vor: Die Audioports beginnen bei 49152, und auch die für die Anwendungsfreigabe reservierten Ports beginnen bei diesem Wert. Um eine optimale Dienstqualität zu gewährleisten, sollte die Anwendungsfreigabe neu konfiguriert werden. Zudem sollte ein anderer Portbereich verwendet werden. Beispielsweise können Sie festlegen, dass die Ports für die Anwendungsfreigabe bei 40803 beginnen und 8348 Ports verwendet werden sollen. Der Grund für die Verwendung von 8348 Ports lautet: Wenn Sie die Werte 40803 und 8348 addieren, werden die Ports 40803 bis 49151 von der Anwendungsfreigabe verwendet. Da die Audioports erst bei 49152 beginnen, kann die Überschneidung der Portbereiche so aufgelöst werden.

Nachdem Sie den neuen Portbereich für die Anwendungsfreigabe ausgewählt haben, können Sie die Änderungen mit dem Set-CsConferencingServer-Cmdlet vornehmen. Diese Änderungen müssen nicht auf den Anwendungsservern oder auf den Vermittlungsservern durchgeführt werden, da sie keinen Datenverkehr von Anwendungsfreigaben verarbeiten. Sie müssen die Portwerte auf diesen Servern lediglich ändern, wenn Sie die Ports für die Übertragung von Audiosignalen neu zuweisen.

Führen Sie einen Befehl wie den folgenden in der Lync Server-Verwaltungsshell aus, um die Portwerte für die Anwendungsfreigabe auf einem einzelnen Konferenzserver zu ändern:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

Wenn Sie diese Änderung auf allen Portservern vornehmen möchten, führen Sie stattdessen den folgenden Befehl aus:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

Halten Sie, nachdem die Porteinstellungen geändert haben, die betroffenen Dienste an, und starten Sie sie neu.

Ihre Konferenz-, Anwendungs- und Vermittlungsserver müssen nicht notwendigerweise den gleichen Portbereich verwenden. Allerdings müssen auf allen Servern unbedingt eindeutige Portbereiche reserviert werden. Wenn Sie jedoch die gleichen Portbereiche auf allen Servern verwenden, wird dadurch die Verwaltung deutlich erleichtert.

