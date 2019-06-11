---
title: 'Lync Server 2013: Bereitstellungsvorgang beim standortbasierten Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 108dd35c7f184c974a317f68901c94bc81e9e403
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Bereitstellungsvorgang beim standortbasierten Routing in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-09_

Dieses Thema bietet eine Übersicht über den Prozess, der bei der Konfiguration des standortbasierten Routings erforderlich ist. Sie müssen lync Server Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie standortbasiertes Routing konfigurieren. Die für standortbasiertes Routing erforderlichen Komponenten sind bereits installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.

### <a name="location-based-routing-deployment-process"></a>Standortbasierter Routing Bereitstellungsprozess

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Erforderliche Gruppen und Rollen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Bereitstellen von Enterprise-VoIP</p></td>
<td><ul>
<li><p>Konfigurieren von Trunks</p></li>
<li><p>Erstellen von VoIP-Richtlinien</p></li>
<li><p>Definieren von VoIP-Routen</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Bereitstellen von Enterprise-VoIP</p></td>
</tr>
<tr class="even">
<td><p>Überprüfen Ihrer Enterprise-VoIP-Bereitstellung</p></td>
<td></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Konfigurieren von netzwerkregionen,-Websites und-Subnetzen</p></td>
<td><ul>
<li><p>Erstellen von netzwerkregionen</p></li>
<li><p>Erstellen von Netzwerk Websites</p></li>
<li><p>Ordnet Subnetze mit Netzwerkstandorten zu</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Informationen zu netzwerkregionen,-Websites und-Subnetzen<br />
Erstellen oder Ändern eines Netzwerkbereichs<br />
Erstellen oder Ändern einer Netzwerk Website<br />
Zuordnen eines Subnetzes zu einer Netzwerk Website</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren des standortbasierten Routings</p></td>
<td><ul>
<li><p>Erstellen von VoIP-Routing Richtlinien</p></li>
<li><p>Separate trunk-Konfiguration pro trunk definieren</p></li>
<li><p>Ändern von VoIP-Richtlinien</p></li>
<li><p>Aktivieren der standortbasierten Routing Konfiguration</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="sample-deployment"></a>Beispielbereitstellung

Die folgende Bereitstellung dient zur Veranschaulichung der Mechanismen, die durch standortbasiertes Routing aktiviert sind.

![e1bd2230-44da-4784-b359-24572b6ce02d] (images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>Eingehende PSTN-Anrufe

Ein Administrator kann den festgelegten trunk aktivieren, um Anrufe an "Standort 1 Gateway" für standortbasiertes Routing weiterzuleiten und das "Standort 1 Gateway" zu Site 1 zu verknüpfen. Sobald die Option aktiviert ist, werden Anrufe, die über "Standort 1 Gateway" weitergeleitet werden, nur an Benutzer weitergeleitet, die sich in Standort 1 befinden. Alle Anrufe, die über den trunk "Standort 1 Gateway" geleitet werden, der für Benutzer an einer anderen Website bestimmt ist, wie etwa Standort 2, werden blockiert, um eine PSTN-Maut Umgehung zu verhindern.

Alle eingehenden PSTN-Anrufe über "Standort 1 Gateway" dürfen nur an Endpunkte weitergeleitet werden, die sich in Standort 1 befinden. Wenn beispielsweise "lync-Benutzer 1" zu Website 2 reist, werden alle eingehenden PSTN-Anrufe über "Standort 1 Gateway" nicht an die Endpunkte von "lync User 1" weitergeleitet, die sich in Standort 2 befinden. Dieselbe Routingregel gilt, wenn "lync-Benutzer 1" zu einer unbekannten Netzwerk Website reist, in der der Standort des Benutzers nicht ermittelt werden kann.

In der folgenden Tabelle wird die Benutzeroberfläche von "lync User 1" in diesem Kontext erläutert.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Lync User 1-Endpunkte, die sich in Network Site 1 befinden</th>
<th>Lync User 1-Endpunkte, die sich in Network Site 2 befinden</th>
<th>Lync User 1-Endpunkte, die sich auf einer unbekannten Netzwerk Website befinden</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Eingehende PSTN-Anrufe an lync-Benutzer 1</p></td>
<td><p>Anrufe werden an Endpunkte an diesem Speicherort weitergeleitet.</p></td>
<td><p>Anrufe werden an diesem Standort nicht an Endpunkte weitergeleitet.</p></td>
<td><p>Anrufe werden an diesem Standort nicht an Endpunkte weitergeleitet.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>Ausgehende PSTN-Anrufe

Auf VoIP-Routen wird in beiden VoIP-Richtlinien verwiesen, die Benutzern direkt zugewiesen sind, und für VoIP-Routing Richtlinien, die Netzwerk Websites zugewiesen sind. Beide Richtlinien enthalten Verweise auf Routen, die verwendet werden können, um einen Anruf anders weiterzuleiten. Beispielsweise kann ein Administrator eine VoIP-Routing Richtlinie für alle Benutzer definieren, die sich auf der Netzwerk Website 1 befinden, um alle ausgehenden Anrufe über das "Standort 1 Gateway" weiterzuleiten, während die VoIP-Richtlinie einiger Benutzer eine Route für alle ausgehenden Anrufe über das "Standort-2-Gateway" definiert. Während sich diese Benutzer auf der Netzwerk Website 1 befinden, werden Ihre ausgehenden Anrufe über das "Standort 1 Gateway" weitergeleitet.

Wenn sich ein Benutzer in einer Netzwerk Website befindet, die für standortbasiertes Routing konfiguriert ist, setzt die VoIP-Routing Richtlinien Route des Netzwerkstandorts die VoIP-Richtlinien Route des Benutzers außer Kraft. Diese Regel eignet sich besonders für Benutzer, die temporär zu einer anderen Website wechseln. In diesem speziellen Fall wird ein Nutzer immer ein Gateway verwenden, das lokal an seinem Standort liegt; Wenn sich "lync User 3" auf "Website 2" befindet, werden alle ausgehenden Anrufe über "Standort 2-Gateway" weitergeleitet, aber wenn er zu Site 1 reist, werden alle ausgehenden Anrufe, die Sie bei Standort 1 getätigt haben, durch "Standort 1 Gateway" weitergeleitet.

In der folgenden Tabelle wird die Benutzeroberfläche von lync User 1 veranschaulicht, die einen ausgehenden Anruf von den folgenden Netzwerkstandorten aus durchführen.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Netzwerk Website 1</th>
<th>Netzwerk Website 2</th>
<th>Unbekannte Netzwerk Website oder für standortbasiertes Routing nicht aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisierung ausgehender Anrufe</p></td>
<td><p>Lync-Benutzer-1-VoIP-Richtlinie</p></td>
<td><p>Lync-Benutzer-1-VoIP-Richtlinie</p></td>
<td><p>Lync-Benutzer-1-VoIP-Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>Weiterleiten von ausgehenden Anrufen</p></td>
<td><p>Website 1 – VoIP-Routing Richtlinie</p></td>
<td><p>Website 2 – VoIP-Routing Richtlinie</p></td>
<td><p>VoIP-Richtlinie des Benutzers und nur für Systeme, die für standortbasiertes Routing nicht aktiviert sind</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>Anruf Übertragungen und Weiterleitungen

Wenn Anrufe übertragen oder weitergeleitet werden, wird das Routing von Anrufen vom standortbasierten Routing beeinflusst.

Die folgende Tabelle zeigt, wie lync-Benutzer 1 einen PSTN-Anruf an einen anderen lync-Benutzer übertragen oder weiterleiten.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzer initiiert Anrufübertragung oder Weiterleitung</th>
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer in der Netzwerk Website nicht für standortbasiertes Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer 1</p></td>
<td><p>Anrufweiterleitung oder -durchstellung ist erlaubt</p></td>
<td><p>Anrufweiterleitung oder -durchstellung ist nicht erlaubt</p></td>
<td><p>Anrufweiterleitung oder -durchstellung ist nicht erlaubt</p></td>
</tr>
</tbody>
</table>

  
Die folgende Tabelle zeigt, wie sich das standortbasierte Routing auf die Weiterleitung des Anrufs auswirkt, basierend auf dem Standort des lync-Benutzers, der übertragen wird (lync User 2, lync User 4 usw.) an einen PSTN-Endpunkt


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Endpunkt, an den der Anruf übertragen oder weitergeleitet wird</th>
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer in der Netzwerk Website nicht für standortbasiertes Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Endpunkt im öffentlichen Telefonnetz</p></td>
<td><p>Anrufweiterleitung oder-Übertragung wird über Website 1-VoIP-Routing Richtlinie und-Ausstieg über das Website 1-Gateway weitergeleitet</p></td>
<td><p>Anrufweiterleitung oder-Übertragung wird über die Website 2-VoIP-Routing Richtlinie und den Ausstieg über das Standort-2-Gateway weitergeleitet</p></td>
<td><p>Anrufweiterleitung oder-Übertragung wird über die lync-Benutzer VoIP-Richtlinie und den Ausstieg über ein Gateway weitergeleitet, das für standortbasiertes Routing nicht aktiviert ist (sofern verfügbar)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>Paralleles Anrufen

Sobald standortbasiertes Routing in der Beispieltopologie konfiguriert ist, werden die folgenden Interaktionen erzwungen.

In der folgenden Tabelle wird gezeigt, ob das standortbasierte Routing das gleichzeitige Klingeln für verschiedene lync-Benutzer ermöglicht (also lync-Benutzer 2, lync-Benutzer 4 usw.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Eingehendes PSTN-Anruf Ziel</th>
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer in der Netzwerk Website nicht für standortbasiertes Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer 1</p></td>
<td><p>Gleichzeitiges Klingeln ist zulässig</p></td>
<td><p>Gleichzeitiges Klingeln ist nicht zulässig</p></td>
<td><p>Gleichzeitiges Klingeln ist nicht zulässig</p></td>
</tr>
</tbody>
</table>

  
In der folgenden Tabelle wird gezeigt, ob ein standortbasiertes Routing das gleichzeitige Anrufen an einen PSTN-Endpunkt von verschiedenen lync-Benutzern ermöglicht (also lync-Benutzer 2, lync-Benutzer 4 usw.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ziel für paralleles Anrufen</th>
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer in der Netzwerk Website nicht für standortbasiertes Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer 1-Mobiltelefon (PSTN-Endpunkt)</p></td>
<td><p>Anrufweiterleitung über die VoIP-Routing Richtlinie des Netzwerkstandorts und den Ausstieg über das Website 1-Gateway</p></td>
<td><p>Anrufweiterleitung über die VoIP-Routing Richtlinie des Netzwerkstandorts und den Ausstieg über das Gateway des Standorts 2</p></td>
<td><p>Anrufweiterleitung über die VoIP-Richtlinie für Anrufer und wird über ein PSTN-Gateway auslaufen, das für standortbasiertes Routing nicht aktiviert ist</p></td>
</tr>
</tbody>
</table>


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

