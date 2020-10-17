---
title: 'Lync Server 2013: Kapazitätsplanung für das Parken von Anrufen'
description: 'Lync Server 2013: Kapazitätsplanung für das Parken von anrufen.'
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
ms.openlocfilehash: 053a6dabad9d10540e84e9e4f43de09057c295f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544541"
---
# <a name="capacity-planning-for-call-park-in-lync-server-2013"></a>Kapazitätsplanung für das Parken von Anrufen in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-09-13_

<div id="sectionSection0" class="section">

In der folgenden Tabelle wird das Benutzermodell für das Parken von Anrufen beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.

<div>


> [!IMPORTANT]  
> Beachten Sie, dass bei der Kapazitätsplanung für die Notfallwiederherstellung jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitslasten für die Dienste für den Parken von Anrufen in beiden Pools zu verarbeiten.



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

