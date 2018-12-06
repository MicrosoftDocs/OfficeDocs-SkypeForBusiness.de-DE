---
title: Media-Ansicht
TOCTitle: Media-Ansicht
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49890644
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Media-Ansicht

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

In der Medienansicht werden Informationen zu einem in einer Peer-zu-Peer-Sitzung verwendeten Medientyp gespeichert. Eine Sitzung wird durch mehrere Datensätze in der Tabelle dargestellt, wenn mehr als ein Medientyp verwendet wird. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.


> [!NOTE]
> Die Medienansicht sollte nicht zur Berechnung der Mediendauer für eine Sitzung verwendet werden. Diese Ansicht enthält die Signaldetails für den Austausch von Mediendaten in einem Anruf. Der Austausch von Mediendaten erfolgt durch die INVITE-Anforderung; StartTime gibt den Zeitpunkt an, zu dem die INVITE-Anforderung gesendet wurde. Der INVITE-Zeitpunkt gibt nicht notwendigerweise die Medienstartzeit an, da die Medien erst gestartet werden, nachdem die Sitzung angenommen wurde.



Die Medienansicht enthält zusätzlich zu den unten aufgeführten Spalten alle Spalten in der [SessionDetails-Ansicht](lync-server-2013-sessiondetails-view.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Medien</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Medientyp. Weitere Informationen finden Sie unter <a href="lync-server-2013-medialist-table.md">MediaList-Tabelle in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Uhrzeit, zu der eine Medienanforderung gesendet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Sitzungsende.</p></td>
</tr>
</tbody>
</table>

