---
title: 'Lync Server 2013: Dateiübertragungen (Ansicht)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4469140f7f92c563a594c883d02f3add1e65c5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="filetransfers-view-in-lync-server-2013"></a>Dateiübertragungen (Ansicht) in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-01_

Die Filetransfer-Ansicht speichert Informationen zu Peer-to-Peer-Dateiübertragungssitzungen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.

<div>


> [!NOTE]  
> Die Dateiübertragungen-Ansicht enthält alle Spalten in der <A href="lync-server-2013-sessiondetails-view.md">SessionDetails-Ansicht in lync Server 2013</A> sowie die unten aufgeführten Spalten.



</div>


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
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>Der Name der übertragenen Datei.</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Wird verwendet, um jede nach Verfolgungs Nachricht als zugeordnet zu kennzeichnen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fileidentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>Eindeutiger Bezeichner zur Unterscheidung Zwischendatei Übertragungen mit demselben Dateinamen.</p></td>
</tr>
<tr class="even">
<td><p><strong>Annehmen</strong></p></td>
<td><p>bit</p></td>
<td><p>Kann "wahr" oder "Null" sein. Ist "true", ist "ablehnen" und "Abbrechen" NULL.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ablehnen</strong></p></td>
<td><p>bit</p></td>
<td><p>Kann "wahr" oder "Null" sein. Ist "true", ist "akzeptieren" und "Abbrechen" NULL.</p></td>
</tr>
<tr class="even">
<td><p><strong>Abbrechen</strong></p></td>
<td><p>bit</p></td>
<td><p>Kann "wahr" oder "Null" sein. Ist "true", ist "annehmen und ablehnen" NULL.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

