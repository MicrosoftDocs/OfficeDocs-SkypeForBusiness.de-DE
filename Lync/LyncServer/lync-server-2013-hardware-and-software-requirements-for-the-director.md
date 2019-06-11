---
title: 'Lync Server 2013: Hardware- und Softwareanforderungen für den Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Hardware- und Softwareanforderungen für den Director in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-20_

In diesem Abschnitt werden die Hardware-und Softwareanforderungen für den Director sowie die unterstützten Zusammensetzungs Szenarien für den Director erläutert.

<div>

## <a name="hardware-requirements-for-the-director"></a>Hardware Anforderungen für den Director

In der folgenden Tabelle sind die Hardwareanforderungen für den Director aufgeführt:

### <a name="hardware-requirements-for-the-director"></a>Hardware Anforderungen für den Director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardwarekomponente</th>
<th>Mindestanforderung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>64-Bit-Prozessor, Quad-Core, 2,0 GHz oder höher</p></li>
<li><p>64-Bit-Dualprozessor, Dual-Core, 2,0 GHz oder höher</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>4 Gigabyte (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Festplatte</p></td>
<td><ul>
<li><p>10K RPM-Festplattenlaufwerk (HDD)</p></li>
<li><p>Hochleistungs-Solid-State-Laufwerk (SSD) mit gleicher oder besserer Leistung als 10.000-RPM-HDD</p></li>
<li><p>2X RAID 10 (gestreifte und gespiegelte) 15K-RPM-Datenträger für Datenbankdateien</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>Dual 1 Gigabit pro Sekunde (Gbit/s)-Netzwerkadapter (empfohlen)</p></li>
<li><p>Einzelner 1 Gbit/s-Netzwerkadapter (unterstützt)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Software Anforderungen für den Director

Die Director-Rolle kann nur auf Servern bereitgestellt werden, auf denen lync Server 2013 Enterprise Edition ausgeführt wird.

Für die Directors ist eines der folgenden 64-Bit-Betriebssysteme erforderlich:

  - Das Betriebssystem Windows Server 2008 R2 mit Service Pack 1

  - Das Windows Server 2008 R2 Enterprise-Betriebssystem mit Service Pack 1

  - Das Windows Server 2008 R2 Datacenter-Betriebssystem mit Service Pack 1

  - Das Betriebssystem Windows Server 2012 Standard

  - Das Betriebssystem Windows Server 2012 Datacenter

Lync Server 2013 erfordert auch die Installation der folgenden Programme und Updates, die im Thema [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)ausführlich beschrieben sind.

</div>

<div>

## <a name="supported-collocation"></a>Unterstützte Anordnung

Die Director-Serverrolle kann nicht mit einer anderen Serverrolle in lync Server 2013 kombiniert werden. Wenn Sie jedoch keinen Director bereitstellen, übernimmt der Front-End-Server die Rolle.

</div>

</div>

<span> </span>

</div>

</div>

</div>

