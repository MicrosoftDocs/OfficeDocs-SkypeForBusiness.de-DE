---
title: 'Lync Server 2013: Überwachen der Back-End-lync Server Speicherleistung'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e48db772a35177571b1affe7c69674cc7fce07ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Überwachen der Back-End-lync Server 2013 Speicherleistung

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2014-05-02_

Die lync Server 2013 Back-End-Datenbanken sind ein sehr wichtiger Bestandteil der lync Server 2013-Bereitstellung. Es wird empfohlen, die Datenbanken und die entsprechenden Transaktionsprotokolle ständig zu überwachen, um sicherzustellen, dass das lync Server 2013 Back-End optimal ausgeführt wird.

In der folgenden Tabelle werden Leistungsindikatoren aufgeführt, die überwacht werden sollten, um Informationen zur Speicherleistung zu erhalten. Die Basiswerte für diese Leistungsindikatoren müssen zuerst bestimmt werden (wenn das System normal ist, die erwartete Last), um die Leistungsänderungen zu verstehen, wenn das System beansprucht wird.

### <a name="performance-counters-to-be-monitored"></a>Zu überwachende Leistungsindikatoren

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Leistungsindikator</th>
<th>Baseline-Schwellenwerte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transaktionen/s (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transaktionen/Sek. (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transaktionen/SEK (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Protokollleerungen/s (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Protokollleerungen/Sek. (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Protokollleerungen/s (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Datenträgerübertragungen/SEK (Lesen + Schreiben) – RTC-DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Datenträgerübertragungen/SEK-RTC-Protokoll</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Datenträgerübertragungen/SEK-RTCDyn DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Datenträgerübertragungen/SEK-RTCdyn-Protokoll</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

