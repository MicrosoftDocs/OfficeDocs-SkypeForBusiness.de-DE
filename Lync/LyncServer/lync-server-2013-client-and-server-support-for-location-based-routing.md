---
title: 'Lync Server 2013: Client-und Server Unterstützung für standortbasiertes Routing'
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
ms.openlocfilehash: daf0fb3656a5a57a5e4c7a6c25b7a08d29f79e86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Client-und Server Unterstützung für standortbasiertes Routing in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-06-18_

Das standortbasierte Routing wird von lync Server erzwungen. Lync Server können die Netzwerkstandorte identifizieren, auf denen Benutzer innerhalb des Unternehmensnetzwerks eine Verbindung herstellen. Da sich Remotebenutzer außerhalb des Unternehmensnetzwerks befinden, wird Ihr Standort als unbekannt betrachtet.

<div>

## <a name="lync-server-support"></a>Lync Server Support

Für das standortbasierte Routing muss lync Server 2013 ku1 auf allen Front-End-Pools und Standard Edition-Servern in einer bestimmten Topologie bereitgestellt werden. Wenn lync Server 2013 ku1 nicht auf bestimmten lync-Komponenten in der Topologie installiert ist, können standortbasierte Routing Einschränkungen nicht vollständig erzwungen werden.

In der folgenden Tabelle ist die Kombination von Serverrollen und Versionen aufgeführt, die für das standortbasierte Routing unterstützt werden.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Pool Version</th>
<th>Vermittlungsserver Version</th>
<th>Unterstützt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Kumulatives Update für lync Server 2013 Februar 2013</p></td>
<td><p>Kumulatives Update für lync Server 2013 Februar 2013</p></td>
<td><p>ja</p></td>
</tr>
<tr class="even">
<td><p>Kumulatives Update für lync Server 2013 Februar 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Kumulatives Update für lync Server 2013 Februar 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Kumulatives Update für lync Server 2013 Februar 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>Beliebiger Wert</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>Beliebiger Wert</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Beliebiger Wert</p></td>
<td><p>Nein</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Lync-Client Unterstützung

In der folgenden Tabelle werden die Clients aufgeführt, die standortbasiertes Routing unterstützt.


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
<th>Details</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>ja</p></td>
<td><p>Einschließlich lync 2013 Kumulatives Update vom 2013. Februar</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>ja</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Nein</p></td>
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
<td><p>Nein</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Mobile 2013</p></td>
<td><p>Nein</p></td>
<td><p>VoIP muss für lync Mobile 2013-Clients deaktiviert werden, wenn Sie von Benutzern mit aktiviertem Standort basiertem Routing verwendet werden.</p></td>
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
> Wenn Sie VoIP für lync Mobile 2013-Clients deaktivieren möchten, weisen Sie eine Mobilitätsrichtlinie mit der Einstellung IP-Audio/Video zu, die für alle Benutzer deaktiviert ist, die für das standortbasierte Routing aktiviert sind. Weitere Informationen zur Mobilitätsrichtlinie finden Sie unter <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen des standortbasierten Routings in lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

