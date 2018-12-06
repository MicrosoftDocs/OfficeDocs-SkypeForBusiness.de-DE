---
title: Konfigurieren von Portbereichen für Edgeserver
TOCTitle: Konfigurieren von Portbereichen für Edgeserver
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204996(v=OCS.15)
ms:contentKeyID: 49294345
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren von Portbereichen für Edgeserver

 

_**Letztes Änderungsdatum des Themas:** 2015-07-24_

Durch den Einsatz von Edgeservern müssen Sie keine separaten Portbereiche für Audio, Video und Anwendungsfreigabe konfigurieren. Zudem müssen die für die Edgeserver verwendeten Portbereiche nicht mit den Portbereichen übereinstimmen, die Sie für Ihre Konferenz-, Anwendungs- und Vermittlungsserver verwenden. Um jedoch die Administration zu vereinfachen, können Sie die Portbereiche Ihrer Edgeserver auch ändern, sodass sie mit den Portbereichen auf Ihren anderen Servern übereinstimmen. Nehmen wir beispielsweise an, Sie haben Ihre Konferenz- Anwendungs- und Vermittlungsserver für diese drei Portbereiche konfiguriert:


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
<td><p><strong>Gesamt</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


Wie Sie sehen können, starten Ihre Portbereiche für Audio, Video und die Anwendungsfreigabe bei Port 40803 und umfassen insgesamt 24732 Ports. Sie können einen bestimmten Edgeserver auch so konfigurieren, dass er diese gesamten Portwerte verwendet. Führen Sie dazu einen ähnlichen Befehl wie diesen in der Lync Server-Verwaltungsshell aus:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

Oder führen Sie den folgenden Befehl aus, um alle Edgeserver in Ihrer Organisation gleichzeitig zu konfigurieren:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

Über den folgenden Befehl in der Lync Server-Verwaltungsshell können Sie die aktuellen Porteinstellungen für Ihre Edgeserver überprüfen:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

