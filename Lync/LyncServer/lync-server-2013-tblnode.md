---
title: 'Lync Server 2013: tblNode'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblNode
ms:assetid: a31d2961-aa83-4286-a12e-15d279c95f19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615024(v=OCS.15)
ms:contentKeyID: 48184960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e6070f6a575466d9ce7063c588e5d470e047d52
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523812"
---
# <a name="tblnode-in-lync-server-2013"></a>tblNode in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

tblNode enthält die Objektstruktur (mit Knoten der Kategorie oder des Chatrooms), die in der lync Server 2013-Systemsteuerung und administrativen Cmdlets verwaltet werden.

### <a name="columns"></a>Spalten

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Typ</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int, not null</p></td>
<td><p>Knoten-ID (eindeutige Nummer).</p></td>
</tr>
<tr class="even">
<td><p>nodeGuid</p></td>
<td><p>GUID, nicht NULL</p></td>
<td><p>Knoten-GUID.</p></td>
</tr>
<tr class="odd">
<td><p>parentID</p></td>
<td><p>int</p></td>
<td><p>Knoten-ID des übergeordneten Elements. Der Stammknoten (mit ID 1) gilt selbst als übergeordnetes Element.</p></td>
</tr>
<tr class="even">
<td><p>NodeType</p></td>
<td><p>bit, not null</p></td>
<td><p>"True" wenn der Knoten eine Kategorie ist.</p>
<p>"False" wenn der Knoten ein Chatroom ist.</p></td>
</tr>
<tr class="odd">
<td><p>nodeName</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Knotenname</p></td>
</tr>
<tr class="even">
<td><p>nodeDesc</p></td>
<td><p>nvarchar (256), not null</p></td>
<td><p>Knotenbeschreibung.</p></td>
</tr>
<tr class="odd">
<td><p>invite</p></td>
<td><p>Bit</p></td>
<td><p>Für Kategorien:</p>
<ul>
<li><p>"True" wenn Einladungen aktiviert sind.</p></li>
<li><p>"False" wenn Einladungen deaktiviert sind.</p></li>
</ul>
<p>Für Räume:</p>
<ul>
<li><p>"False", wenn Einladungen deaktiviert sind (überschreibt die übergeordnete Kategorie).</p></li>
<li><p>"Null" wenn die Einstellung zum Einladen von der übergeordneten Kategorie geerbt wird.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>angemeldet</p></td>
<td><p>Bit</p></td>
<td><p>Für Kategorien:</p>
<ul>
<li><p>"True" wenn der Chatverlauf aktiviert ist.</p></li>
<li><p>"False" wenn der Chatverlauf deaktiviert ist.</p></li>
</ul>
<p>Für Räume:</p>
<ul>
<li><p>NULL.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>filePost</p></td>
<td><p>Bit</p></td>
<td><p>Für Kategorien:</p>
<ul>
<li><p>"True" wenn Dateiuploads zugelassen sind.</p></li>
<li><p>"False" wenn Dateiuploads nicht zugelassen sind.</p></li>
</ul>
<p>Für Räume:</p>
<ul>
<li><p>NULL.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>deaktiviert</p></td>
<td><p>bit, not null</p></td>
<td><p>"True" wenn der Chatroom deaktiviert ist. Trifft nur auf Chatrooms zu. ("False" für Kategorien.)</p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Verhalten</p></td>
<td><p>smallint, not null</p></td>
<td><p>Verhalten (in der Tabelle "EnumValue" ermittelt):</p>
<ul>
<li><p>4: Normal (normale Chatrooms)</p></li>
<li><p>5: Auditorium (Auditoriumchatrooms, nur Referenten können Beiträge veröffentlichen).</p></li>
</ul>
<p>Trifft nur auf Chatrooms zu.</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>smallint, nicht NULL</p></td>
<td><p>Sichtbarkeit (in der Tabelle "EnumValue" ermittelt):</p>
<ul>
<li><p>2: Privat</p></li>
<li><p>3: Bereich</p></li>
<li><p>6: Offen</p></li>
</ul>
<p>Trifft nur auf Chatrooms zu.</p></td>
</tr>
<tr class="even">
<td><p>siopID</p></td>
<td><p>GUID</p></td>
<td><p>Add-In-GUID, falls diesem Chatroom ein Add-In zugeordnet ist. (Kategorien sind keine Add-Ins zugeordnet.)</p>
<p>Die Add-In-Informationen werden in der Tabelle "SiopWhiteList" gesucht.</p></td>
</tr>
<tr class="odd">
<td><p>nodeAddedBy</p></td>
<td><p>int, not null</p></td>
<td><p>ID des Prinzipals, der diesen Knoten erstellt hat.</p></td>
</tr>
<tr class="even">
<td><p>nodeAddedOn</p></td>
<td><p>bigint, not null</p></td>
<td><p>Zeitstempel der Knotenerstellung.</p></td>
</tr>
<tr class="odd">
<td><p>nodeUpdatedBy</p></td>
<td><p>int, not null</p></td>
<td><p>ID des Prinzipals, der die letzte Aktualisierung dieses Knotens vorgenommen hat.</p></td>
</tr>
<tr class="even">
<td><p>nodeUpdatedOn</p></td>
<td><p>bigint, not null</p></td>
<td><p>Zeitstempel der letzten Aktualisierung dieses Knotens.</p></td>
</tr>
<tr class="odd">
<td><p>purgedOn</p></td>
<td><p>Datum/Uhrzeit</p></td>
<td><p>Zeitpunkt des letzten Löschvorgangs (Entfernung von Bereichen aus der Tabelle "tblScopedPrincipal" und Rollen aus der Tabelle "tblPrincipalRole"), der Auswirkungen auf diesen Knoten hatte. Wird von der internen Cache-Aktualisierung des Chatdiensts verwendet.</p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a>Schlüssel

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Spalte</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
<tr class="even">
<td><p>Verhalten</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle "tblEnumValue.valueID".</p></td>
</tr>
<tr class="odd">
<td><p>visibility</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle "tblEnumValue.valueID".</p></td>
</tr>
<tr class="even">
<td><p>parentID</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle "tblNode.nodeID".</p></td>
</tr>
<tr class="odd">
<td><p>siopID</p></td>
<td><p>Fremdschlüssel mit Suche in der Tabelle "tblSiopWhiteList.siopId".</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

