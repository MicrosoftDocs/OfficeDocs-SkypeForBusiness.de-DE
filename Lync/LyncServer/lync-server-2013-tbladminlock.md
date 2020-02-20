---
title: 'Lync Server 2013: adminlock'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblAdminLock
ms:assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558665(v=OCS.15)
ms:contentKeyID: 48184560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58bf1c04cb24f8fee668cd21f24fc7c9c1c5341d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142191"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladminlock-in-lync-server-2013"></a>adminlock in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-06-25_

Die „tblAdminLock“-Tabelle enthält die Administratorsperre, die zur Ausführung bestimmter Administratorbefehle erforderlich ist.

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
<td><p>lockExpiresTime</p></td>
<td><p>datetime, nicht NULL</p></td>
<td><p>Ablaufdatum und -zeit der Sperre. Der Besitzer kann diesen Wert in regelmäßigen Abständen verlängern.</p></td>
</tr>
<tr class="even">
<td><p>lockServerID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Servers, der die Sperre besitzt.</p></td>
</tr>
<tr class="odd">
<td><p>lockActorID</p></td>
<td><p>int, nicht NULL</p></td>
<td><p>ID des Prinzipals, der die Sperre besitzt.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

