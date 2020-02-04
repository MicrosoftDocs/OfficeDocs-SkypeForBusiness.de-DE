---
title: 'Lync Server 2013: Client- und Serverunterstützung für standortbasiertes Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Client- und Serverunterstützung für standortbasiertes Routing in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-06-18_

Standortbasiertes Routing wird von lync Server erzwungen. Lync Server kann die Netzwerk Websites identifizieren, über die Benutzer im Unternehmensnetzwerk eine Verbindung herstellen. Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, werden deren Positionen als unbekannt angesehen.

<div>

## <a name="lync-server-support"></a>Lync Server-Unterstützung

Standortbasiertes Routing erfordert, dass lync Server 2013 CU1 auf allen Front-End-Pools und Standard Edition-Servern in einer bestimmten Topologie bereitgestellt wird. Wenn lync Server 2013 CU1 auf bestimmten lync-Komponenten in der Topologie nicht installiert ist, können standortbasierte Routing Einschränkungen nicht vollständig erzwungen werden.

In der folgenden Tabelle wird die Kombination aus Serverrollen und Versionen aufgeführt, die für standortbasiertes Routing unterstützt werden.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Poolversion</th>
<th>Mediation Server-Version</th>
<th>Unterstützt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 Februar 2013 Kumulatives Update</p></td>
<td><p>Lync Server 2013 Februar 2013 Kumulatives Update</p></td>
<td><p>ja</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 Februar 2013 Kumulatives Update</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 Februar 2013 Kumulatives Update</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>nein</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 Februar 2013 Kumulatives Update</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>Beliebig</p></td>
<td><p>nein</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>Beliebig</p></td>
<td><p>nein</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Beliebig</p></td>
<td><p>nein</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Lync-Client Unterstützung

In der folgenden Tabelle sind die Clients aufgeführt, die vom standortbasierten Routing unterstützt werden.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Clienttyp</th>
<th>Unterstützt</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>ja</p></td>
<td><p>Einschließlich lync 2013 Februar 2013 Kumulatives Update</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>ja</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>nein</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>ja</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Attendant</p></td>
<td><p>ja</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync für Windows 8</p></td>
<td><p>nein</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>nein</p></td>
<td><p>VoIP muss für lync Mobile 2013-Clients deaktiviert sein, wenn Sie von Benutzern mit aktiviertem Standort basiertem Routing verwendet werden.</p></td>
</tr>
<tr class="even">
<td><p>Lync Mobile 2010</p></td>
<td><p>ja</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Wenn Sie VoIP für lync Mobile 2013-Clients deaktivieren möchten, weisen Sie der Einstellung "IP Audio/Video" eine Mobilitätsrichtlinie zu, die für alle Benutzer deaktiviert ist, die für standortbasiertes Routing aktiviert sind. Ausführlichere Informationen zu Mobilitätsrichtlinien finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planung des standortbasierten Routings in Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

