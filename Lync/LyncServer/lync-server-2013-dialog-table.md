---
title: 'Lync Server 2013: Dialog-Tabelle'
TOCTitle: Dialog-Tabelle
ms:assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398313(v=OCS.15)
ms:contentKeyID: 49293953
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Dialog-Tabelle in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Bei der **Dialog** -Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird; jeder Datensatz steht für einen SIP-Dialog (Session Initiation Protocol).


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>Zeitpunkt, zu dem der QoE-Agent (Quality of Excellence) den ersten Bericht von einem Anrufer oder Angerufenen empfängt. Wird zusammen mit <strong>SessionSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren.</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>Sequenznummer zur Unterscheidung von Sitzungen, die dieselbe <strong>ConferenceDateTime</strong> aufweisen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogID</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p></p></td>
<td><p>Dialog-ID, die global eindeutig ist.</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogIDChecksum</strong></p></td>
<td><p>int</p></td>
<td><p>index</p></td>
<td><p>Prüfsumme der Dialog-ID.</p></td>
</tr>
</tbody>
</table>

