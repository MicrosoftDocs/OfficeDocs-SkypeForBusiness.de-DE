---
title: 'Lync Server 2013: Kapazitätsplanung für das Parken von Anrufen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Call Park
ms:assetid: 75520310-760a-4b1b-bcc1-4d724d13f87a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg416493(v=OCS.15)
ms:contentKeyID: 48184529
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd4cc9d10a3a3562c035c7bc2f64f551b70cc5da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Kapazitätsplanung für das Parken von Anrufen in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-09-13_

<div id="sectionSection0" class="section">

In der folgenden Tabelle wird das Benutzermodell des Anruf Parks beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.

<div>


> [!IMPORTANT]  
> Beachten Sie, dass für die Planung von Disaster Recovery-Kapazität jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitslasten für die Dienste des Anruf Parks in beiden Pools zu behandeln.



</div>

### <a name="call-park-user-model"></a>Benutzermodell der Funktion zum Parken von Anrufen

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metrik</th>
<th>Pro Front-End-Pool (mit 8 Front-End-Servern)</th>
<th>Pro Standard Edition-Server</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Rate für das Parken von Anrufen</p></td>
<td><p>8 pro Minute</p></td>
<td><p>1 pro Minute</p></td>
</tr>
<tr class="even">
<td><p>Rate für das Abrufen geparkter Anrufe</p></td>
<td><p>8 pro Minute</p></td>
<td><p>1 pro Minute</p></td>
</tr>
<tr class="odd">
<td><p>Durchschnittliche Parkdauer</p></td>
<td><p>60 Sekunden</p></td>
<td><p>60 Sekunden</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

