---
title: 'Lync Server 2013: Gleichzeitiges Klingeln'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Simultaneous ringing
ms:assetid: df02f919-4d50-4832-9300-6c51f8b4fc56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994079(v=OCS.15)
ms:contentKeyID: 51803990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e3104da5e7d351bda26698087e97106cafbdff4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="simultaneous-ringing-in-lync-server-2013"></a>Gleichzeitiges Klingeln in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Wenn für den angerufenen das gleichzeitige Klingeln aktiviert ist, analysiert das standortbasierte Routing den Standort des anrufenden Teilnehmers und die Endpunkte der angerufenen Parteien, um zu bestimmen, ob der Anruf weitergeleitet werden soll.

Die folgende Tabelle zeigt einen Benutzer, der mit gleichzeitigem Klingeln konfiguriert ist, und das gleichzeitige Klingeln-Ziel ist ein Benutzer am gleichen Netzwerkstandort, an einem anderen Netzwerkstandort oder an einem unbekannten Netzwerkstandort.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Eingehender PSTN-Anruf für</th>
<th>Befindet sich am gleichen Netzwerkstandort wie der angerufene</th>
<th>Befindet sich an einem anderen Netzwerkstandort als der angerufene</th>
<th>Befindet sich an einem unbekannten Netzwerkstandort oder ist für standortbasiertes Routing nicht aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer</p></td>
<td><p>Gleichzeitiges Klingeln zulässig</p></td>
<td><p>Gleichzeitiges Klingeln nicht zulässig</p></td>
<td><p>Gleichzeitiges Klingeln nicht zulässig</p></td>
</tr>
</tbody>
</table>

  
Die folgende Tabelle zeigt einen Aufruf von einem lync-Benutzer (dh lync-Anrufer) am gleichen Netzwerkstandort, an einem anderen Netzwerkstandort oder an einem unbekannten Netzwerkstandort. Der angerufene verfügt über einen PSTN-Endpunkt (also ein Mobiltelefon), der als gleichzeitiger Ring-Zielwert konfiguriert ist. In diesem Szenario wird durch das standortbasierte Routing ermittelt, ob der Anruf an das Ziel für das gleichzeitige Klingeln (also das Mobiltelefon) des angerufenen weitergeleitet werden soll.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Gleichzeitiges Klingel Ziel</th>
<th>Befindet sich am gleichen Netzwerkstandort wie der angerufene</th>
<th>Befindet sich an einem anderen Netzwerkstandort als der angerufene</th>
<th>Befindet sich an einem unbekannten Netzwerkstandort oder ist für standortbasiertes Routing nicht aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN-Endpunkt</p></td>
<td><p>Gleichzeitiges Klingeln über die Website VoIP-Routing Richtlinie des Anrufers zulässig</p></td>
<td><p>Gleichzeitiges Klingeln über die Website VoIP-Routing Richtlinie des Anrufers zulässig</p></td>
<td><p>Gleichzeitiges Klingeln über die VoIP-Richtlinie des Anrufers in Trunks, die nicht für standortbasiertes Routing aktiviert sind</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a>Siehe auch


[Szenarien für das standortbasierte Routing in lync Server 2013](lync-server-2013-scenarios-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

