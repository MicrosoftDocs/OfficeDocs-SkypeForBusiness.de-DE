---
title: 'Lync Server 2013: Serverhardwareplattformen'
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
ms.openlocfilehash: 95c8b0e9b1e13d845672cff07d30b7f2ac1a5b22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-hardware-platforms-for-lync-server-2013"></a>Serverhardwareplattformen für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-07-28_

Serverfunktionen von lync Server 2013 und Computern, auf denen lync Server-Verwaltungstools ausgeführt werden, erfordern 64-Bit-Hardware.

Die spezifische Hardware, die für die lync Server 2013-Bereitstellung verwendet wird, kann abhängig von der Größe und den Verwendungsanforderungen variieren. In diesem Abschnitt wird die empfohlene Hardware beschrieben. Wenngleich es sich hier nicht um Anforderungen, sondern um Empfehlungen handelt, kann der Einsatz von Hardware, die diesen Empfehlungen nicht entspricht, zu erheblichen Leistungsproblemen und sonstigen Problemen führen.

<div>

## <a name="recommended-hardware-platform"></a>Empfohlene Hardwareplattform

Für eine optimale Leistung empfehlen wir, dass Sie lync Server auf Servern mit Hardware ausführen, die die Anforderungen in der folgenden Tabelle erfüllt. Wenn Sie weniger leistungsfähige Hardware verwenden, treten möglicherweise Funktionsprobleme oder eine schlechte Leistung auf. Beachten Sie, dass diese Hardwareanforderungen höher als in früheren Versionen von lync Server sind, hauptsächlich deshalb, weil in lync Server 2013 alle Front-End-Server SQL Server ausführen.

<div>


> [!NOTE]  
> NIC-Teaming wird unterstützt und sollte für lync Server transparent sein. Ausführliche Informationen finden Sie unter <A href="http://go.microsoft.com/fwlink/p/?linkid=389910">Communications Server-oder lync Server-und Netzwerkadapter-Teaming</A>.



</div>

### <a name="recommended-hardware-for-front-end-servers-back-end-servers-standard-edition-servers-persistent-chat-servers-and-persistent-chat-store-and-persistent-chat-compliance-store-back-end-server-roles-for-persistent-chat-server"></a>Empfohlene Hardware für Front-End-Server, Back-End-Server, Standard Edition-Server, Server für beständigen Chat, Speicher für beständigen Chat und Compliance-Speicher für beständigen Chat (Back-End-Serverrollen für Server für beständigen Chat)

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
<td><p>64-Bit-Dualprozessor, Sechskern, mindestens 2,26 GHz.</p>
<p>Intel Itanium-Prozessoren werden für lync Server-Serverrollen nicht unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>32 GB.</p></td>
</tr>
<tr class="odd">
<td><p>Festplatte</p></td>
<td><ul>
<li><p>Mindestens 8 Festplattenlaufwerke mit 10.000 U/min und mindestens 72 GB freiem Speicherplatz</p>
<p>Zwei Festplatten sollten RAID 1 verwenden und sechs Festplatten sollten RAID 10 verwenden.</p>
<p>-Oder</p></li>
<li><p>Festkörperlaufwerke (SSDs) mit einer ähnlichen Leistung wie 8 mechanische Festplattenlaufwerke mit 10.000 U/min.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür ein Teamvorgang mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist).</p>
<div>

> [!NOTE]  
> Dualkonfigurationen oder mehrfach vernetzte Konfigurationen werden für Front-End-Server, Back-End-Server, Standard Edition-Server und Server für beständigen Chat nicht unterstützt.<BR>ILO/DRAC/usw. Verbindungen, die nicht dem Betriebs System ausgesetzt sind und zur Überwachung und Verwaltung der Server Hardware verwendet werden, stellen keinen mehrfach vernetzten Server dar und werden daher unterstützt.


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
<li><p>64-Bit-Dualprozessor, Quad-Core, 2,0 Gigahertz (GHz) oder höher</p>
<p>-Oder</p></li>
<li><p>64-Bit-4-Wege-Prozessor, Dual-Core, 2,0 GHz oder höher</p></li>
</ul>
<p>Intel Itanium-Prozessoren werden für lync Server-Serverrollen nicht unterstützt.</p></td>
</tr>
<tr class="even">
<td><p>Arbeitsspeicher</p></td>
<td><p>16 Gigabyte (GB).</p></td>
</tr>
<tr class="odd">
<td><p>Festplatte</p></td>
<td><ul>
<li><p>4 oder mehr 10.000-rpm-Festplattenlaufwerke mit mindestens 72 GB freiem Speicherplatz.</p>
<p>Die Festplatten sollten in einer 2x-RAID-1-Konfiguration sein.</p>
<p>-Oder</p></li>
<li><p>Festkörperlaufwerke (SSDs) mit einer ähnlichen Leistung wie 4 mechanische Festplattenlaufwerke mit 10.000 U/min.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Netzwerk</p></td>
<td><ul>
<li><p>1 Dual-Port-Netzwerkadapter, mindestens 1 GBit/s (2 werden empfohlen, wofür ein Teamvorgang mit einer einzelnen MAC-Adresse und einer einzelnen IP-Adresse erforderlich ist). zwei Netzwerkschnittstellen sind auf Edge-Servern erforderlich und werden auf eigenständigen Vermittlungsservern unterstützt.</p></li>
</ul>
<div>

> [!NOTE]  
> Dual-oder Multi-Homed-Konfigurationen werden für Directors nicht unterstützt.<BR>ILO/DRAC/usw. Verbindungen, die nicht dem Betriebs System ausgesetzt sind und zur Überwachung und Verwaltung der Server Hardware verwendet werden, stellen keinen mehrfach vernetzten Server dar und werden daher unterstützt.


</div>
<p>Für Edgeserver sind zwei Netzwerkschnittstellen erforderlich, bei denen es sich um Dual-Port-Netzwerkadapter, 1 Gbit/s oder höher (oder zwei gekoppelte Netzwerkadapter, für insgesamt vier) handelt, wobei jedes Paar mit einer einzelnen Mac-Adresse und einer einzelnen IP-Adresse für insgesamt zwei Paare zusammengestellt wird.</p>
<p>Die Installation zusätzlicher Netzwerkschnittstellenkarten (NICs), um die Konfiguration einer bestimmten PSTN-IP-Adresse zu ermöglichen, wird auf eigenständigen Vermittlungsservern unterstützt.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

