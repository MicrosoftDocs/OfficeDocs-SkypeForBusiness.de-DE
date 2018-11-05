---
title: 'Lync Server 2013: Liste der Kompatibilitätstabellen für den Server für beständigen Chat'
TOCTitle: Liste der Kompatibilitätstabellen für den Server für beständigen Chat
ms:assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ215878(v=OCS.15)
ms:contentKeyID: 49294633
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Liste der Kompatibilitätstabellen für den Server für beständigen Chat in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Das Schema der Kompatibilitätsdatenbank von Beständiger Chat besteht aus den folgendes Tabellen.

## Liste der Kompatibilitätstabellen von Server für beständigen Chat


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tabelle</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcompliancedata.md">tblComplianceData in Lync Server 2013</a></p></td>
<td><p>Enthält die Genehmigungsereignisse, die noch nicht vom konfigurierten Adapter verarbeitet wurden.</p>
<p>Diese Tabelle enthält Beständiger Chat-bezogene Ereignisse, wie z. B. Chatnachrichten und Dateidownloads. (Teilnehmerereignisse werden von der tblComplianceParticipant-Tabelle nachverfolgt.)</p>
<p>(Die Server, von denen die Ereignisse in dieser Tabelle verarbeitet wurden, werden in der tblComplianceFanout-Tabelle aufgelistet.)</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancefanout.md">tblComplianceFanout in Lync Server 2013</a></p></td>
<td><p>Enthält die Server, von denen ein Genehmigungsereignis verarbeitet wurde. Diese Tabelle steht in engem Zusammenhang mit der tblComplianceData-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tblcomplianceparticipant.md">tblComplianceParticipant in Lync Server 2013</a></p></td>
<td><p>Enthält aktuelle Teilnehmer pro Chat-Dienst und pro Server. Diese Tabelle wird basierend auf Verknüpfungs- und Genehmigungsereignissen verwaltet, die vom Beständiger Chat-Dienst empfangen wurde.</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-tblcompliancestate.md">tblComplianceState in Lync Server 2013</a></p></td>
<td><p>Enthält poolweite Informationen zum Kompatibilitätszustand.</p></td>
</tr>
</tbody>
</table>

