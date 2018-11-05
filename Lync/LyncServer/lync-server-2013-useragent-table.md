---
title: 'Lync Server 2013: UserAgent-Tabelle'
TOCTitle: UserAgent-Tabelle
ms:assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398939(v=OCS.15)
ms:contentKeyID: 49295551
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UserAgent-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **UserAgent** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Darin wird eine Liste der verschiedenen Benutzer-Agents gespeichert, die an in der Datenbank aufgezeichneten Sitzungen beteiligt waren. Jeder Datensatz in der Tabelle steht für einen Benutzer-Agent.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Spalte</strong></th>
<th><strong>Datentyp</strong></th>
<th><strong>Schlüssel/Index</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>UserAgentKey</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.</p></td>
</tr>
<tr class="even">
<td><p><strong>UserAgent</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Eindeutig</p></td>
<td><p>Zeichenfolge des Benutzer-Agents.</p></td>
</tr>
<tr class="odd">
<td><p><strong>UAType</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>1: Vermittlungsserver</p>
<p>2: A/V-Konferenzserver</p>
<p>4: Lync</p>
<p>8: IP-Telefon</p>
<p>16: Live Meeting-Konsole</p>
<p>32: DVT (Deployment Validation Tool)</p>
<p>64: Lync auf Macintosh-Computern</p>
<p>128: Office Communications Server 2007 R2 Attendant</p>
<p>256: Konferenzankündigungsdienst</p>
<p>512: Automatische Telefonkonferenzzentrale</p>
<p>1024: Reaktionsgruppenanwendung</p>
<p>2048: Externe Anrufsteuerung</p></td>
</tr>
</tbody>
</table>

