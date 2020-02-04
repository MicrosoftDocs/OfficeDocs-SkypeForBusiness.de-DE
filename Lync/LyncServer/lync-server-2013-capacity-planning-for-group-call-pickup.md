---
title: 'Lync Server 2013: Kapazitätsplanung für die Gruppenanruf Abholung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Group Call Pickup
ms:assetid: 0d654a19-6cf0-4118-903d-ec2c4e519253
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ984297(v=OCS.15)
ms:contentKeyID: 51476680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d694b20d026d83b4cef37c713e38ab8066e22f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Kapazitätsplanung für die Gruppenanruf Abholung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-12_

<div id="sectionSection0" class="section">

In der folgenden Tabelle wird das Benutzermodell für die Gruppenanruf Abholung beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.

<div>


> [!IMPORTANT]  
> Die Abholung von Gruppen anrufen basiert auf der Anwendung "Parken". Beachten Sie, dass für die Planung von Disaster Recovery-Kapazität jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitsauslastungen für die Anruf Park Dienste, einschließlich der Gruppenanruf Abholung, in beiden Pools zu verarbeiten.



</div>

### <a name="group-call-pickup-user-model"></a>Gruppenanruf-Pickup-Benutzermodell

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
<td><p>Empfohlene Benutzeranzahl pro Gruppe</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Empfohlene Gruppenanzahl</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Anzahl der für die Gruppenanrufannahme aktivierten Benutzer pro Pool</p></td>
<td><p>25.000</p></td>
<td><p>3.000</p></td>
</tr>
<tr class="even">
<td><p>Maximale Rate an eingehenden Anrufen pro Pool und Minute an alle Benutzer, die für die Gruppenanrufannahme aktiviert sind</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Rate an von Benutzern mit Gruppenanrufannahme wieder aufgenommenen Anrufen pro Pool und Minute</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Für Front-End-Pools mit weniger als acht Front-End-Servern berechnen Sie die Metriken linear. Wenn der Front-End-Pool beispielsweise über einen Front-End-Server verfügt, berechnen Sie die maximale Auslastung als 1/8 der in der Tabelle angegebenen Werte.</P>
> <LI>
> <P>Sie können die empfohlene Anzahl von Benutzern pro Gruppe erhöhen oder reduzieren, solange die maximale Anzahl von Benutzern pro Pool nicht überschritten wird. Beispielsweise kann Ihr Standard Edition-Server 120-Gruppen mit 25 Benutzern pro Gruppe haben, da die Anzahl der Benutzer, die für die Gruppenanruf-Abholung aktiviert sind, sich noch innerhalb des maximal zulässigen Benutzermodells befindet (das heißt, 120 Gruppen mal 25 Benutzer sind 3.000 Benutzer, die für Gruppenanruf-Pickups aktiviert sind).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

