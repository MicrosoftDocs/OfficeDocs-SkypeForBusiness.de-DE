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
ms.openlocfilehash: fbadec18ba7054c7b58522129fca01da7d015e7e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblcomplianceparticipant-in-lync-server-2013"></a>tblComplianceParticipant in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

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
<td><p>nvarchar (255), nicht NULL</p></td>
<td><p>Kanal-URI (Uniform Resource Identifier).</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID des Teilnehmers (entsprechend der tblPrincipal.prinID-Tabelle).</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel des Ereignisses des Beitritts.</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>NULL, wenn der Teilnehmer noch immer teilnimmt. Der Zeitstempel des Ereignisses des Verlassens des Kanals, sofern nicht NULL.</p>
<p>Diese Einträge werden schließlich entfernt, wenn das Ereignis von allen Konvertern verarbeitet wird.</p></td>
</tr>
<tr class="odd">
<td><p>userUri</p></td>
<td><p>nvarchar(255), nicht NULL</p></td>
<td><p>Benutzer-URI</p></td>
</tr>
<tr class="even">
<td><p>ServerID</p></td>
<td><p>int</p></td>
<td><p>Serveridentität (wie in tblServerIdentity.serverID).</p></td>
</tr>
<tr class="odd">
<td><p>SessionID</p></td>
<td><p>bigint</p></td>
<td><p>Serversitzung. Zufallszahl, die nach jedem Starten eines Chatdiensts generiert wird. Wird zur Unterscheidung von Sitzungen verwendet, mit dem Zweck, verwaiste Teilnehmer zu identifizieren.</p></td>
</tr>
</tbody>
</table>


### <a name="key"></a>Key

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

