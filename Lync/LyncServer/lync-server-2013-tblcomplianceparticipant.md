---
title: 'Lync Server 2013: tblComplianceParticipant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558655(v=OCS.15)
ms:contentKeyID: 48184262
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 484948a01c82dc8ca256e3e50e484c94a9b81de4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>tblComplianceParticipant in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-12_

tblComplianceParticipant enthält die aktuellen Teilnehmer pro Kanal und pro Server.

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
<td><p>channelUri</p></td>
<td><p>nvarchar (255); nicht NULL</p></td>
<td><p>Kanal Uniform Resource Identifier (URI).</p></td>
</tr>
<tr class="even">
<td><p>UserID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID des Teilnehmers (entsprechend der Tabelle tblPrincipal. prinID).</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel des Joining-Ereignisses</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>NULL, wenn der Teilnehmer noch verbunden ist. Der Zeitstempel des Kanals, der das Ereignis verlässt, wenn nicht NULL.</p>
<p>Diese Einträge werden schließlich entfernt, wenn alle Übersetzer das Ereignis verarbeiten.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar (255); nicht NULL</p></td>
<td><p>Benutzer-URI.</p></td>
</tr>
<tr class="even">
<td><p>ServerID</p></td>
<td><p>int</p></td>
<td><p>Serveridentität (wie in der Tabelle tblServerIdentity. Server-ID).</p></td>
</tr>
<tr class="odd">
<td><p>SessionID</p></td>
<td><p>bigint</p></td>
<td><p>Server Sitzung. Hierbei handelt es sich um eine Zufallszahl, die bei jedem Start eines Chat-Diensts generiert wird. Sie wird zur Unterscheidung von Sitzungen zum Zweck der Identifizierung verwaister Teilnehmer verwendet.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Schlüssel

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
<td><p>&lt;channelUri, UserID, joinedAt&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

