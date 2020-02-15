---
title: 'Lync Server 2013: Kapazitätsplanung für die gruppenanrufannahme'
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
ms.openlocfilehash: 403a00887cb64b33075f173499e855eb8783bb20
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-group-call-pickup-in-lync-server-2013"></a>Kapazitätsplanung für die gruppenanrufannahme in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-12_

<div id="sectionSection0" class="section">

In der folgenden Tabelle wird das Benutzermodell für die gruppenanrufannahme beschrieben, das Sie als Grundlage für die Kapazitäts Planungsanforderungen verwenden können.

<div>


> [!IMPORTANT]  
> Die gruppenanrufannahme basiert auf dem Anwendung zum Parken von anrufen. Beachten Sie, dass bei der Kapazitätsplanung für die Notfallwiederherstellung jeder Pool eines gekoppelten Pools in der Lage sein sollte, die Arbeitslasten für die Dienste für den Parken von anrufen, einschließlich der gruppenanrufannahme, in beiden Pools zu verarbeiten.



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
<td><p>Empfohlene Anzahl von Benutzern pro Gruppe</p></td>
<td><p>50</p></td>
<td><p>50</p></td>
</tr>
<tr class="even">
<td><p>Empfohlene Anzahl von Gruppen</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Anzahl von Benutzern pro Pool, die für die gruppenanrufannahme aktiviert sind</p></td>
<td><p>25.000</p></td>
<td><p>3,000</p></td>
</tr>
<tr class="even">
<td><p>Maximale Anzahl eingehender Anrufe an Gesamtbenutzer, die für die gruppenanrufannahme pro Pool pro Minute aktiviert sind</p></td>
<td><p>500</p></td>
<td><p>60</p></td>
</tr>
<tr class="odd">
<td><p>Maximale Anzahl von anrufen, die von Benutzern mit der gruppenanrufannahme pro Pool pro Minute abgerufen werden</p></td>
<td><p>200</p></td>
<td><p>25</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Für Front-End-Pools mit weniger als acht Front-End-Servern sollten Sie die Metriken linear berechnen. Wenn Ihr Front-End-Pool beispielsweise über eine Front-End-Server verfügt, berechnen Sie die maximale Last als 1/8 der in der Tabelle gezeigten Werte.</P>
> <LI>
> <P>Sie können die empfohlene Anzahl von Benutzern pro Gruppe und Anzahl von Gruppen erweitern oder verringern, solange Sie die maximale Anzahl von Benutzern pro Pool nicht überschreiten. Beispielsweise kann Ihre Standard Edition-Server 120 Gruppen mit 25 Benutzern pro Gruppe haben, da die Anzahl der Benutzer, die für die gruppenanrufannahme aktiviert sind, sich immer noch innerhalb des Benutzermodell Maximums befindet (120 Gruppen mal 25 Benutzer 3.000 Benutzer sind, die für die gruppenanrufannahme aktiviert sind).</P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

