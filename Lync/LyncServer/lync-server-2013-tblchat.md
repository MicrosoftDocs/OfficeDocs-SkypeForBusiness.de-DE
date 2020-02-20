---
title: 'Lync Server 2013: tblChat'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblChat
ms:assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615031(v=OCS.15)
ms:contentKeyID: 48185203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c189e0a7d4c17b43d83a30f6dc9c282f5dbe3d24
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblchat-in-lync-server-2013"></a>tblChat in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-12_

tblChat enthält alle Chatnachrichten.

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
<td><p>channelId</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Knoten-ID</p></td>
</tr>
<tr class="even">
<td><p>Chat-Nr</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Eindeutige fortlaufende Zahl (pro Knoten-ID), die die Reihenfolge der Chatrooms identifiziert, generiert von der tblLastChatId-Tabelle.</p></td>
</tr>
<tr class="odd">
<td><p>chatDate</p></td>
<td><p>bigint, nicht NULL</p></td>
<td><p>Zeitstempel für die Chatnachricht.</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>Prinzipal-ID des Bereitstellers.</p></td>
</tr>
<tr class="odd">
<td><p>isalert</p></td>
<td><p>bit, nicht NULL</p></td>
<td><p>TRUE, wenn es sich bei der Nachricht um eine Fehlermeldung handelt, andernfalls FALSE.</p></td>
</tr>
<tr class="even">
<td><p>content</p></td>
<td><p>nvarchar (max), nicht NULL</p></td>
<td><p>Chatinhalt (Nur-Text-Version). Der Inhalt ist normalerweise einfacher Text mit den folgenden Ausnahmen:</p>
<ul>
<li><p>Dateien sind als Links vom Typ ma-filelink: dargestellt.</p></li>
<li><p>Links sind als HTML-Elemente dargestellt (obwohl der Inhaltstyp nicht als HTML betrachtet werden kann).</p></li>
<li><p>Textabschnitte sind in einem Format wie "[STORY]...." verschlüsselt.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>RTF</p></td>
<td><p>varchar (max)</p></td>
<td><p>Chatinhalt (RTF-Version). Kann NULL sein, wenn vom Client nicht bereitgestellt.</p></td>
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
<td><p>&lt;Kanal-Nr, Chat&gt;</p></td>
<td><p>Primärschlüssel</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

