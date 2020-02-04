---
title: 'Lync Server 2013: FileTransfers-Tabelle'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers table
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398353(v=OCS.15)
ms:contentKeyID: 48184118
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de8a3e69c670c273bcdd91ac5895c0b1f0b15d80
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-table-in-lync-server-2013"></a>FileTransfers-Tabelle in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-28_

Jeder Datensatz stellt eine Dateiübertragungssitzung dar.


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
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>SessionID</strong></p></td>
<td><p>datetime</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Uhrzeit der Sitzungsanforderung. Wird in Verbindung mit <strong>SessionIdSeq</strong> verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primär, fremd</p></td>
<td><p>Die ID-Nummer, um die Sitzung zu identifizieren. Wird in Verbindung mit <strong>SessionID</strong> -Mal verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie <a href="lync-server-2013-dialogs-table.md">in der Tabelle Dialogfelder in lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dateiname</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td></td>
<td><p>Der Name der Datei.</p></td>
</tr>
<tr class="even">
<td><p><strong>Fileidentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td></td>
<td><p>Eindeutiger Bezeichner zur Unterscheidung Zwischendatei Übertragungen mit demselben Dateinamen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Primary</p></td>
<td><p>Wird verwendet, um jede nach Verfolgungs Nachricht als zugeordnet zu kennzeichnen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Annehmen</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Kann "wahr" oder "Null" sein. Ist "true", ist "ablehnen" und "Abbrechen" NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ablehnen</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Kann "wahr" oder "Null" sein. Ist "true", ist "akzeptieren" und "Abbrechen" NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Abbrechen</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>Kann "wahr" oder "Null" sein. Ist "true", ist "annehmen und ablehnen" NULL.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

