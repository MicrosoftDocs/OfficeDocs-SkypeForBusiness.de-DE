---
title: 'Lync Server 2013: Orts basiertes Routing und beratende Anruf Übertragungen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Location-Based Routing and consultative call transfers
ms:assetid: b12460c2-36c8-481f-b867-fe10dc1c0bdf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362836(v=OCS.15)
ms:contentKeyID: 56335089
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7c7b73efb670c5569b8c4600c1759e981cda211
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831938"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-based-routing-and-consultative-call-transfers-in-lync-server-2013"></a>Übertragungen von standortbasierten Routing-und beratenden anrufen in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-07-31_

Neben der Durchsetzung von Standort basiertem Routing zu lync-Besprechungen erzwingt die standortbasierte Routing Konferenz Anwendung standortbasierte Routing Einschränkungen für beratende Anruf Übertragungen, die an PSTN-Endpunkte abtreten. Bei einer beratenden Anrufübertragung handelt es sich um einen Anruf zwischen zwei Parteien, bei dem eine der Parteien den Anruf an einen neuen Nutzer übermittelt. Ein PSTN-Endpunkt ruft beispielsweise Benutzer a (lync-aufgerufener) auf. Benutzer A bestimmt, dass der PSTN-Benutzer an Benutzer B weitergeleitet werden soll (lync-Benutzer). Der Benutzer A platziert den Anruf mit dem PSTN-Benutzer in Wartestellung und ruft Benutzer b an, der sich mit dem PSTN-Benutzer unterhalten möchte. Benutzer a übergibt den Anruf in Wartestellung an Benutzer B.

**Anruffluss bei einer Anrufdurchstellung mit Ankündigung**

![Orts basiertes Routing für Konferenz Diagramme] (images/Dn362836.e4d43d6f-23d2-49c9-b12b-15248a743f92(OCS.15).jpg "Orts basiertes Routing für Konferenz Diagramme")

Wenn ein für standortbasiertes Routing aktivierter Benutzer eine beratende Anrufübertragung eines PSTN-Endpunkts initiiert (wie in der vorhergehenden Abbildung dargestellt), werden zwei aktive Anrufe, ein Anruf zwischen dem PSTN-Benutzer und dem lync-Benutzer a und der andere zwischen lync-Benutzer a und lync-Benutzer B erstellt. Das folgende Verhalten wird von der standortbasierten Routing Konferenz Anwendung erzwungen:

  - Wenn das SIP Trunk-Routing des PSTN-Anrufs autorisiert ist, den PSTN-Anruf an die Netzwerk Website weiterzuleiten, auf der sich der lync-Benutzer B (also das Übertragungsziel) befindet, wird die Anrufübertragung zugelassen. Andernfalls wird die Übertragung von beratenden anrufen blockiert. Diese Autorisierung erfolgt auf der Grundlage des Standorts der übertragenen Partei, die sich am gleichen Netzwerkstandort wie der SIP-Stamm befindet, der den aktiven Anruf an den PSTN-Endpunkt weiterleitet.

  - Wenn der SIP-Trunk-Routing der eingehende PSTN-Anruf nicht autorisiert ist, Anrufe an die Netzwerk Website weiterzuleiten, auf der sich die übertragene Partei (lync-Benutzer B) befindet oder sich die übertragene Partei an einer unbekannten Netzwerk Website befindet, wird die beratende Anrufübertragung an das PSTN durchgeführt. Endpunkt (dh Anrufübergabe Ziel) wird blockiert.

In der folgenden Tabelle wird beschrieben, wie standortbasierte Routing Einschränkungen von der standortbasierten Routing Konferenz Anwendung für Beratenden Anruf Übertragungen angewendet werden. Zwar sind Nebenstellenanlagenendgeräte nicht direkt einem Netzwerkstandort zugewiesen, aber die SIP-Vermittlungsleitung, an die die jeweilige Nebenstellenanlage angeschlossen ist, kann einem Netzwerkstandort zugewiesen sein. Daher kann ein Nebenstellenanlagenendgerät indirekt einem Netzwerkstandort zugewiesen sein.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Netzwerkstandort des Teilnehmers, dessen Anruf durchgestellt wird</p></td>
<td><p>Netzwerk Website des Anruf Weiterleitungs Ziels</p></td>
<td><p>Verhalten</p></td>
</tr>
<tr class="even">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Lync-Benutzer an derselben Netzwerk Website (also Website 1)</p></td>
<td><p>Eine beratende Übertragung ist zulässig.</p></td>
</tr>
<tr class="odd">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</p></td>
<td><p>Eine beratende Übertragung ist nicht zulässig.</p></td>
</tr>
<tr class="even">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Lync-Benutzer in einer unbekannten Netzwerk Website</p></td>
<td><p>Eine beratende Übertragung ist nicht zulässig.</p></td>
</tr>
<tr class="odd">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Federated lync-Benutzer</p></td>
<td><p>Eine beratende Übertragung ist nicht zulässig.</p></td>
</tr>
<tr class="even">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>PBX-Endpunkt am gleichen Standort (also Standort 1)</p></td>
<td><p>Eine beratende Übertragung ist zulässig.</p></td>
</tr>
<tr class="odd">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>PBX-Endpunkt an verschiedenen Standorten (also Standort 2)</p></td>
<td><p>Eine beratende Übertragung ist nicht zulässig.</p></td>
</tr>
<tr class="even">
<td><p>PBX-Endpunkt am gleichen Standort (also Standort 1)</p></td>
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Eine beratende Übertragung ist zulässig.</p></td>
</tr>
<tr class="odd">
<td><p>PBX-Endpunkt an einer anderen Website (also Standort 2)</p></td>
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Eine beratende Übertragung ist nicht zulässig.</p></td>
</tr>
<tr class="even">
<td><p>PBX-Endpunkt auf einer beliebigen Website</p></td>
<td><p>Lync-Benutzer an derselben Netzwerk Website (also Website 1)</p></td>
<td><p>Eine beratende Übertragung ist zulässig.</p></td>
</tr>
<tr class="odd">
<td><p>PBX-Endpunkt auf einer beliebigen Website</p></td>
<td><p>Lync-Benutzer an verschiedenen Netzwerkstandorten (also Standort 2)</p></td>
<td><p>Eine beratende Übertragung ist zulässig.</p></td>
</tr>
<tr class="even">
<td><p>PBX-Endpunkt auf einer beliebigen Website</p></td>
<td><p>Lync-Benutzer in einer unbekannten Netzwerk Website</p></td>
<td><p>Eine beratende Übertragung ist zulässig.</p></td>
</tr>
<tr class="odd">
<td><p>PBX-Endpunkt auf einer beliebigen Website</p></td>
<td><p>Federated lync-Benutzer</p></td>
<td><p>Eine beratende Übertragung ist zulässig.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

