---
title: 'Lync Server 2013: Hardware- und Softwareanforderungen für den Director'
TOCTitle: Hardware- und Softwareanforderungen für den Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398560(v=OCS.15)
ms:contentKeyID: 49294425
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hardware- und Softwareanforderungen für den Director in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-05-19_

In diesem Abschnitt werden die Hardware- und Softwareanforderungen für Director sowie die unterstützten Szenarien für das Verbinden dieses Directors beschrieben.

## Hardwareanforderungen für Director

In der folgenden Tabelle werden die Hardwareanforderungen für Director aufgelistet:

### Hardwareanforderungen für Director-Server

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
<li><p>64-Bit-Prozessor, Vierkern, mindestens 2,0 GHz</p></li>
<li><p>64-Bit-Dualprozessor, Doppelkern, mindestens 2,0 GHz</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>4 GB</p></td>
</tr>
<tr class="odd">
<td><p>Festplatte</p></td>
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


## Softwareanforderungen für Director

Die Rolle des Directors kann nur auf Servern bereitgestellt werden, auf denen Lync Server 2013 Enterprise Edition ausgeführt wird.

Eines der folgenden 64-Bit-Betriebssysteme ist für alle Rollen von Directorserforderlich:

  - Das Windows Server 2008 R2 Standard-Betriebssystem mit Service Pack 1 (SP1)

  - Das Windows Server 2008 R2 Enterprise-Betriebssystem mit Service Pack 1 (SP1)

  - Das Windows Server 2008 R2 Datacenter-Betriebssystem mit Service Pack 1 (SP1)

  - Das Betriebssystem Windows Server 2012 Standard

  - Das Betriebssystem Windows Server 2012 Datacenter

Lync Server 2013 erfordert zudem die Installation der folgenden Programme und Updates, die im Thema [Zusätzliche Serverunterstützung und Anforderungen in Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md) genannt werden

## Unterstützte Kollokation

Die Director-Serverrolle kann nicht mit einer anderen Serverrolle in Lync Server 2013 verbunden werden. Wenn Sie jedoch keine Director bereitstellen, wird diese Serverrolle von Front-End-Servern übernommen.

