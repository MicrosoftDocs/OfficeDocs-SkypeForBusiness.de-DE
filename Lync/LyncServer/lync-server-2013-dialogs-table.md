---
title: 'Lync Server 2013: Dialogs-Tabelle'
TOCTitle: Dialogs-Tabelle
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg425954(v=OCS.15)
ms:contentKeyID: 49293889
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Dialogs-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Dialogs** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und die Informationen über **DialogIDs** für Peer-zu-Peer-Sitzungen enthält.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Datentyp</th>
<th>Schlüssel/Index</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Zeitpunkt der Sitzungsanforderung; wird zusammen mit <strong>SessionIDSeq</strong> zur eindeutigen Identifikation einer Sitzung verwendet.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>ID zur Identifikation der Sitzung. Wird zusammen mit <strong>SessionIDTime</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalChecksum</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Prüfsumme von <strong>ExternalID</strong> . Dieses Feld wird verwendet, um die Geschwindigkeit von Datenbanksuchvorgängen zu steigern.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExternalId</strong></p></td>
<td><p>varbinary(775)</p></td>
<td><p> </p></td>
<td><p>SIP-DialogID, gespeichert als Binärwert. Das Format des Binärwerts lautet:</p>
<p><strong>dialog;from-tag;to-tag</strong></p>
<p>Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:</p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

