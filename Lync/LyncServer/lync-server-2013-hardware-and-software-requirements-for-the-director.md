---
title: 'Lync Server 2013: Hardware-und Softwareanforderungen für den Director'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b00e294291bcafb859cc900ca71463f1315cdfe8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536862"
---
# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Hardware-und Softwareanforderungen für den Director in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-10-20_

In diesem Abschnitt werden die Hardware-und Softwareanforderungen für den Director sowie die unterstützten Zusammenstellungs Szenarien für den Director erläutert.

<div>

## <a name="hardware-requirements-for-the-director"></a>Hardwareanforderungen für Director-Server

In der folgenden Tabelle sind die Hardwareanforderungen für den Director aufgeführt:

### <a name="hardware-requirements-for-the-director"></a>Hardwareanforderungen für Director-Server

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
<li><p>64-Bit-Prozessor, Vierkern, mindestens 2,0 GHz</p></li>
<li><p>64-Bit-Dualprozessor, Doppelkern, mindestens 2,0 GHz</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>4 GB</p></td>
</tr>
<tr class="odd">
<td><p>Datenträger</p></td>
<td><ul>
<li><p>HDD-Festplattenlaufwerk mit 10.000 U/min</p></li>
<li><p>SSD-Hochleistungslaufwerk mit gleicher oder höherer Leistung als eine HDD-Festplatte mit 10.000 U/min</p></li>
<li><p>2 RAID 10-Datenträger (Stripeset und gespiegelt), 15.000 U/min, für Datenbankdatendateien</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>Dual-Port-Netzwerkkarten mit 1 GBit/s (empfohlen)</p></li>
<li><p>Single-Port-Netzwerkkarte mit 1 GBit/s (unterstützt)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Software Anforderungen für den Director

Die Director-Rolle kann nur auf Servern bereitgestellt werden, die lync Server 2013 Enterprise Edition ausführt.

Eines der folgenden 64-Bit-Betriebssysteme ist für die Directors erforderlich:

  - Das Windows Server 2008 R2 Standard Betriebssystem mit Service Pack 1

  - Das Windows Server 2008 R2 Enterprise-Betriebssystem mit Service Pack 1

  - Das Windows Server 2008 R2 Datacenter-Betriebssystem mit Service Pack 1

  - Das Windows Server 2012 Standard-Betriebssystem

  - Das Betriebssystem des Windows Server 2012-Rechenzentrums

Lync Server 2013 erfordert auch die Installation der folgenden Programme und Updates, die im Thema [zusätzliche Server Unterstützung und-Anforderungen in lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md)erläutert werden.

</div>

<div>

## <a name="supported-collocation"></a>Unterstützte Zusammenstellungen

Die Director-Serverrolle kann nicht mit einer anderen Serverrolle in lync Server 2013 zusammengefasst werden. Wenn Sie jedoch keinen Director bereitstellen, wird die Rolle von den Front-End-Servern übernommen.

</div>

</div>

<span> </span>

</div>

</div>

</div>

