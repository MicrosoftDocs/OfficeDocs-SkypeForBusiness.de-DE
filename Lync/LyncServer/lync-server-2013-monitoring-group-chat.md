---
title: 'Lync Server 2013: Überwachen des Gruppen-Chats'
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
ms.openlocfilehash: fa350924503f430ec0494cc5e1eb17f7878084a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-group-chat-in-lync-server-2013"></a>Überwachen des Gruppen-Chats in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-08-04_

Es wird dringend empfohlen, das neueste im Microsoft Download Center verfügbare [kumulative Server Update-Installationsprogramm](http://support.microsoft.com/kb/968802) zur Verbesserung der Leistung zu führen.

Unter der Voraussetzung, dass Sie das neueste kumulative Update ausführen, verwenden Sie die folgende Belastungstest Tabelle für Metriken, um zu verstehen, ob Ihre Gruppen-Chat Server mit optimaler Integrität ausgeführt werden.

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
<td><p>Drei Gruppen-Chat Server in einem Gruppen-Chat-Pool mit jeweils 8 GB Arbeitsspeicher und 8 Prozessoren.</p></td>
</tr>
<tr class="even">
<td><p>Zwei lync Server 2013-Front-Ends in Enterprise Edition</p></td>
</tr>
<tr class="odd">
<td><p>60.000 gleichzeitige Benutzer in drei Gruppen Chat Servern.</p></td>
</tr>
<tr class="even">
<td><p>25.000-Kanäle, die vom Gruppen-Chat-Pool gehostet werden.</p></td>
</tr>
<tr class="odd">
<td><p>Kanalgröße:</p>
<ul>
<li><p>Größe des kleinen Kanals: 30</p></li>
<li><p>Mittlere Kanalgröße: 150</p></li>
<li><p>Größe des großen Kanals: 2500</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Kanalanzahl:</p>
<ul>
<li><p>Zahl kleine Kanäle: 24.000</p></li>
<li><p>Zahl Medium Kanäle 800</p></li>
<li><p>Zahl große Kanäle 24</p></li>
<li><p>Gesamtzahl der Kanäle 24.824</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Kanäle einladen:</p>
<ul>
<li><p>Die Hälfte der Kanäle waren Einladungs Kanäle</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Die Anzahl der Kanäle, die ein Benutzer verknüpft:</p>
<ul>
<li><p>Klein: 12</p></li>
<li><p>Mittel: 2</p></li>
<li><p>Groß: 1</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Teilnahmegebühr:</p>
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
<td><p>Chat-Gebühr:</p>
<ul>
<li><p>20 gesamt/Sekunde, 6.66/Sekunde pro Server</p></li>
</ul></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> Die folgenden Leistungsindikator Nummern variieren wahrscheinlich, wenn verschiedene Hardwarespezifikationen oder Benutzerprofile verwendet werden.



</div>

### <a name="performance-counter-to-be-monitored"></a>Zu überwachenden Leistungsindikator

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Leistungsindikator</th>
<th>Schwellenwerte</th>
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

