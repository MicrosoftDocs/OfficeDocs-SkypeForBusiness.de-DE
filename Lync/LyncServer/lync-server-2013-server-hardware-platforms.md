---
title: Lync Server 2013 Server-Hardwareplattformen
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server hardware platforms
ms:assetid: c964c1c0-0153-472b-88ad-a38866e0df0c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398835(v=OCS.15)
ms:contentKeyID: 48185395
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1a1dddb7fe87ebc877ed16048a42a17760c2053
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Server Hardwareplattformen für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-07-28_

Lync Server 2013 Server Rollen und Computer, auf denen lync Server Verwaltungstools betrieben werden, benötigen 64-Bit-Hardware.

Die für lync Server 2013 Bereitstellung verwendete spezifische Hardware kann je nach Größe und Verwendungsanforderungen variieren. In diesem Abschnitt wird die empfohlene Hardware beschrieben. Obwohl es sich hierbei um Empfehlungen handelt, nicht um Anforderungen, kann die Verwendung von Hardware, die diese Empfehlungen nicht erfüllt, zu erheblichen Leistungsproblemen und anderen Problemen führen.

<div>

## <a name="recommended-hardware-platform"></a>Empfohlene Hardware Plattform

Um eine optimale Leistung zu erzielen, sollten Sie lync Server auf Servern mit Hardware ausführen, die die Anforderungen in der folgenden Tabelle erfüllen. Wenn Sie weniger leistungsfähige Hardware verwenden, können Funktionsprobleme oder eine schlechte Leistung auftreten. Beachten Sie, dass diese Hardwareanforderungen höher sind als bei früheren Versionen von lync Server, vor allem, weil in lync Server 2013 alle Front-End-Server SQL Server ausführen.

<div>


> [!NOTE]  
> NIC-Teaming wird unterstützt und sollte für lync Server transparent sein. Ausführliche Informationen finden Sie unter <A href="https://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server oder lync Server und Netzwerkadapter-Teaming</A>.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>Empfohlene Hardware für Front-End-Server, Back-End-Server, Standard Edition-Server, persistent Chat-Server und persistent Chat Store und Compliance Store für beständigen Chat (Back-End-Serverrollen für den Server für beständigen Chat)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardwarekomponente</th>
<th>Empfohlen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><p>64-Bit Dualprozessor, Hex-Core, 2,26 Gigahertz (GHz) oder höher.</p>
<p>Intel Itanium-Prozessoren werden für lync Server-Server Rollen nicht unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>32 Gigabyte (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Datenträger</p></td>
<td><ul>
<li><p>8 oder mehr 10.000 RPM-Festplatten mit mindestens 72 GB freiem Speicherplatz.</p>
<p>Zwei der Datenträger sollten RAID 1 verwenden, und sechs sollten RAID 10 verwenden.</p>
<p>-Oder</p></li>
<li><p>Solid State Drives (SSDs), die ähnliche Leistung wie mechanische Festplattenlaufwerke mit 8 10.000-rpm bieten.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 wird empfohlen, für die ein Teaming mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse erforderlich ist).</p>
<div>

> [!NOTE]  
> Duale oder Multi-Homed-Konfigurationen werden für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat nicht unterstützt.<BR>ILO/DRAC/etc. Verbindungen, die nicht dem Betriebs System ausgesetzt sind und zum Überwachen und Verwalten der Server Hardware verwendet werden, stellen keinen Multi-Homed-Server dar und werden daher unterstützt.


</div></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="recommended-hardware-for-edge-servers-standalone-mediation-servers-and-directors"></a>Empfohlene Hardware für Edgeserver, eigenständige Vermittlungsserver und Directors

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Hardwarekomponente</th>
<th>Empfohlen</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>Dualprozessor mit 64 Bit, Quad-Core, 2,0 Gigahertz (GHz) oder höher.</p>
<p>-Oder</p></li>
<li><p>64-Bit-4-Wege-Prozessor, Dual-Core, 2,0 GHz oder höher.</p></li>
</ul>
<p>Intel Itanium-Prozessoren werden für lync Server-Server Rollen nicht unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>16 Gigabyte (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Datenträger</p></td>
<td><ul>
<li><p>4 oder mehr 10.000 RPM-Festplatten mit mindestens 72 GB freiem Speicherplatz.</p>
<p>Die Datenträger sollten sich in einer 2X-RAID-1-Konfiguration befinden.</p>
<p>-Oder</p></li>
<li><p>Solid State Drives (SSDs), die ähnliche Leistung wie mechanische Festplattenlaufwerke mit 4 10.000-rpm bieten.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (2 wird empfohlen, für die ein Teaming mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse erforderlich ist). 2 Netzwerkschnittstellen sind auf Edge-Servern erforderlich und werden auf eigenständigen Vermittlungsservern unterstützt.</p></li>
</ul>
<div>

> [!NOTE]  
> Duale oder Multi-Homed-Konfigurationen werden für Directors nicht unterstützt.<BR>ILO/DRAC/etc. Verbindungen, die nicht dem Betriebs System ausgesetzt sind und zum Überwachen und Verwalten der Server Hardware verwendet werden, stellen keinen Multi-Homed-Server dar und werden daher unterstützt.


</div>
<p>Edgeserver benötigen zwei Netzwerkschnittstellen mit zwei Netzwerkadaptern, 1 Gbit/s oder höher (oder zwei gekoppelte Netzwerkadapter für insgesamt vier, wobei jedes Paar mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse zusammenarbeitet, wobei insgesamt zwei Paare verwendet werden).</p>
<p>Die Installation zusätzlicher Netzwerkschnittstellenkarten (NICs), um die Konfiguration einer bestimmten PSTN-IP-Adresse zuzulassen, wird auf eigenständigen Vermittlungsservern unterstützt.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

