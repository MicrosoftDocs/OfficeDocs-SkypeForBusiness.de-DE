---
title: 'Lync Server 2013: Überwachen des Gruppenchats'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring group chat
ms:assetid: bddcf0be-ebf3-46bc-90c7-2576877734fb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720924(v=OCS.15)
ms:contentKeyID: 63969648
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a42589db677132170e9456c998d96fd2eb1de5d2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Überwachen des Gruppenchats in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-08-04_

Es wird dringend empfohlen, das neueste [Installationsprogramm für kumulative Server Updates](https://support.microsoft.com/kb/968802) , das im Microsoft Download Center verfügbar ist, zur Verbesserung der Leistung auszuführen.

Unter der Voraussetzung, dass Sie das neueste kumulative Update ausführen, verwenden Sie die folgende Belastungstest Tabelle für Metriken, um zu verstehen, ob Ihre Gruppen Chat Server mit optimaler Integrität betrieben werden.

### <a name="test-environment-and-user-model"></a>Test Umgebung und Benutzermodell

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Drei Gruppenchatserver in einem Gruppenchat Pool mit jeweils 8 GB Arbeitsspeicher und 8 Prozessoren.</p></td>
</tr>
<tr class="even">
<td><p>Zwei lync Server 2013-Front-Ends in Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>60.000 gleichzeitige Benutzer auf drei Gruppen Chat Servern.</p></td>
</tr>
<tr class="even">
<td><p>25.000 Kanäle, die vom Gruppen Chat Pool gehostet werden.</p></td>
</tr>
<tr class="odd">
<td><p>Kanalgröße:</p>
<ul>
<li><p>Größe des kleinen Kanals: 30</p></li>
<li><p>Mittlere Kanalgröße: 150</p></li>
<li><p>Große Kanalgröße: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Kanalanzahl:</p>
<ul>
<li><p>Zahl kleine Kanäle: 24.000</p></li>
<li><p>Zahlmittel große Kanäle 800</p></li>
<li><p>Zahl große Kanäle 24</p></li>
<li><p>Gesamt Kanäle 24.824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Kanäle einladen:</p>
<ul>
<li><p>Die Hälfte der Kanäle wurden einladen Kanäle</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Anzahl der Kanäle, die ein Benutzer anschließt:</p>
<ul>
<li><p>Klein: 12</p></li>
<li><p>Mittel: 2</p></li>
<li><p>Groß: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Verknüpfungs Rate:</p>
<ul>
<li><p>10 Gesamt/Sekunde, 3.33/Sekunde pro Server</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Abmelde Rate:</p>
<ul>
<li><p>10 Gesamt/Sekunde, 3.33/Sekunde pro Server</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Chat Rate:</p>
<ul>
<li><p>20 gesamt/Sekunde, 6.66/Sekunde pro Server</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Die folgenden Leistungsindikator Nummern werden wahrscheinlich variieren, wenn unterschiedliche Hardwarespezifikationen oder Benutzerprofile verwendet werden.



</div>

### <a name="performance-counter-to-be-monitored"></a>Zu überwachende Leistungsindikator

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Leistungsindikator</th>
<th>Schwellen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Prozess (Channelservice)-&gt;% Prozessorzeit</p></td>
<td><p>Min: 0</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

