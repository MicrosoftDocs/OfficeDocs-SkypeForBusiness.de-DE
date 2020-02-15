---
title: 'Lync Server 2013: standortbasiertes Routing und beratende Anruf Übertragungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72ddbba79bf0de777c8567164475ab573d09a2c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Standortbasiertes Routing und Anrufweiterleitung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-07-31_

Zusätzlich zum Erzwingen eines standortbasierten Routings für lync-Besprechungen erzwingt die standortbasierte Routing Konferenz Anwendung standortbasierte Routing Einschränkungen für Anrufe, die an PSTN-Endpunkten austreten. Bei einer beratenden Anrufweiterleitung handelt es sich um einen Anruf zwischen zwei Parteien, bei dem eine der Parteien den Anruf an einen neuen Benutzer überträgt. Ein PSTN-Endpunkt ruft beispielsweise Benutzer a (lync-angerufener) auf. Benutzer A bestimmt, dass der PSTN-Benutzer an Benutzer B (lync-Benutzer) weitergeleitet werden soll. Benutzer a platziert den Anruf mit dem PSTN-Benutzer in der Warteschleife und ruft Benutzer b an, der mit dem PSTN-Benutzer zu sprechen akzeptiert. Der Benutzer a übergibt den Anruf einhalten an Benutzer B.

**Anruffluss für Anrufweiterleitung mit beratender Funktion**

![Standortbasiertes Routing für Konferenz Diagramm](images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Standortbasiertes Routing für Konferenz Diagramm")

Wenn ein Benutzer, der für standortbasiertes Routing aktiviert ist, eine beratende Anrufweiterleitung eines PSTN-Endpunkts initiiert (wie in der obigen Abbildung dargestellt), werden zwei aktive Anrufe, ein Anruf zwischen dem PSTN-Benutzer und dem lync-Benutzer a und der andere zwischen lync-Benutzer a und lync-Benutzer B erstellt. Das folgende Verhalten wird von der standortbasierten Routing Konferenz Anwendung erzwungen:

  - Wenn das SIP-Trunk Routing der PSTN-Anruf autorisiert ist, den PSTN-Anruf an den Netzwerkstandort weiterzuleiten, auf dem sich der lync-Benutzer B (also das Übertragungsziel) befindet, wird die Anrufweiterleitung zugelassen. Andernfalls wird die beratende Anrufweiterleitung blockiert. Diese Autorisierung wird basierend auf dem Standort des übertragenen Teilnehmers am gleichen Netzwerkstandort wie der SIP-Trunk ausgeführt, der den aktiven Anruf an den PSTN-Endpunkt weiterleitet.

  - Wenn das SIP-Trunk Routing der eingehende PSTN-Anruf nicht zum Weiterleiten von Anrufen an den Netzwerkstandort autorisiert ist, auf dem sich der übermittelte Teilnehmer (lync User B) befindet oder sich der übertragene Teilnehmer an einem unbekannten Netzwerkstandort befindet, wird die Anrufweiterleitung an das PSTN weitergeleitet. Endpunkt (dh Anruf Übertragungsziel) wird blockiert.

In der folgenden Tabelle wird beschrieben, wie standortbasierte Routing Einschränkungen von der standortbasierten Routing Konferenz Anwendung für beratende Anruf Übertragungen angewendet werden. Obwohl PBX-Endpunkte keinem Netzwerkstandort direkt zugeordnet sind, kann dem SIP-Trunk, mit dem die Nebenstellenanlage verbunden ist, ein Netzwerkstandort zugewiesen werden. Daher kann der PBX-Endpunkt indirekt einem Netzwerkstandort zugeordnet werden.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Netzwerkstandort der Anruf übertragenden Partei</p></td>
<td><p>Netzwerkstandort des Anruf Übertragungs Ziels</p></td>
<td><p>Verhalten</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Endpunkt</p></td>
<td><p>Lync-Benutzer am gleichen Netzwerkstandort (also Standort 1)</p></td>
<td><p>Beratende Übertragung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>PSTN-Endpunkt</p></td>
<td><p>Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</p></td>
<td><p>Die beratende Übertragung wird nicht zugelassen.</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Endpunkt</p></td>
<td><p>Lync-Benutzer an einem unbekannten Netzwerkstandort</p></td>
<td><p>Die beratende Übertragung wird nicht zugelassen.</p></td>
</tr>
<tr class="odd">
<td><p>PSTN-Endpunkt</p></td>
<td><p>Verbund-lync-Benutzer</p></td>
<td><p>Die beratende Übertragung wird nicht zugelassen.</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Endpunkt</p></td>
<td><p>Nebenstellen Endpunkt am gleichen Standort (Standort 1)</p></td>
<td><p>Beratende Übertragung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>PSTN-Endpunkt</p></td>
<td><p>Nebenstellen Endpunkt an verschiedenen Standorten (also Standort 2)</p></td>
<td><p>Die beratende Übertragung wird nicht zugelassen.</p></td>
</tr>
<tr class="even">
<td><p>Nebenstellen Endpunkt am gleichen Standort (Standort 1)</p></td>
<td><p>PSTN-Endpunkt</p></td>
<td><p>Beratende Übertragung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>Nebenstellen Endpunkt an einem anderen Standort (also Standort 2)</p></td>
<td><p>PSTN-Endpunkt</p></td>
<td><p>Die beratende Übertragung wird nicht zugelassen.</p></td>
</tr>
<tr class="even">
<td><p>PBX-Endpunkt an einem beliebigen Standort</p></td>
<td><p>Lync-Benutzer am gleichen Netzwerkstandort (also Standort 1)</p></td>
<td><p>Beratende Übertragung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>PBX-Endpunkt an einem beliebigen Standort</p></td>
<td><p>Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</p></td>
<td><p>Beratende Übertragung wird zugelassen</p></td>
</tr>
<tr class="even">
<td><p>PBX-Endpunkt an einem beliebigen Standort</p></td>
<td><p>Lync-Benutzer an einem unbekannten Netzwerkstandort</p></td>
<td><p>Beratende Übertragung wird zugelassen</p></td>
</tr>
<tr class="odd">
<td><p>PBX-Endpunkt an einem beliebigen Standort</p></td>
<td><p>Verbund-lync-Benutzer</p></td>
<td><p>Beratende Übertragung wird zugelassen</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

