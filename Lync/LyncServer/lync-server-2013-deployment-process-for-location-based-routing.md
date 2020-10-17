---
title: 'Lync Server 2013: Bereitstellungsprozess für Location-Based Routing'
description: 'Lync Server 2013: Bereitstellungsprozess für Location-Based Routing.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Location-Based Routing
ms:assetid: 9e923e72-83fc-4a4f-8937-28a55739ed3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994055(v=OCS.15)
ms:contentKeyID: 51803966
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c321d9b0eada6e9501b2ded69120feae36be171
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551061"
---
# <a name="deployment-process-for-location-based-routing-in-lync-server-2013"></a>Bereitstellungsprozess für Location-Based Routing in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-09_

Dieses Thema bietet eine Übersicht über den Prozess, der beim Konfigurieren Location-Based Routings erforderlich ist. Sie müssen lync Server Enterprise Edition oder Standard Edition mit Enterprise-VoIP bereitstellen, bevor Sie Location-Based Routing konfigurieren. Die für Location-Based Routing erforderlichen Komponenten sind bereits installiert und aktiviert, wenn Sie Enterprise-VoIP bereitstellen.

### <a name="location-based-routing-deployment-process"></a>Location-Based Routing Bereitstellungsprozess

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
<td><p>Konfigurieren von netzwerkregionen, Standorten und Subnetzen</p></td>
<td><ul>
<li><p>Erstellen von netzwerkregionen</p></li>
<li><p>Erstellen von Netzwerkstandorten</p></li>
<li><p>Assoziierte Subnetze mit Netzwerkstandorten</p></li>
</ul></td>
<td><p>CSVoiceAdmins<br />
CsAdministrator<br />
CsServerAdministrator</p></td>
<td><p>Grundlegende Informationen zu Netzwerkregionen, Standorten und Subnetzen<br />
Erstellen oder Ändern einer Netzwerkregion<br />
Erstellen oder Ändern eines Netzwerkstandorts<br />
Zuordnen eines Subnetzes zu einem Netzwerkstandort</p></td>
</tr>
<tr class="even">
<td><p>Konfigurieren des Location-Based Routings</p></td>
<td><ul>
<li><p>Erstellen von Richtlinien für das VoIP-Routing</p></li>
<li><p>Definieren einer separaten trunkkonfiguration pro trunk</p></li>
<li><p>Ändern von VoIP-Richtlinien</p></li>
<li><p>Aktivieren Location-Based Routing Konfiguration</p></li>
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

Die folgende Bereitstellung wird verwendet, um die durch Location-Based Routing aktivierten Mechanismen zu veranschaulichen.

![e1bd2230-44da-4784-b359-24572b6ce02d](images/JJ994055.e1bd2230-44da-4784-b359-24572b6ce02d(OCS.15).png "e1bd2230-44da-4784-b359-24572b6ce02d")

<div>

## <a name="incoming-pstn-calls"></a>Eingehende PSTN-Anrufe

Ein Administrator kann den definierten trunk aktivieren, um Anrufe an "Standort 1-Gateway" für Location-Based Routing weiterzuleiten und das "Standort 1-Gateway" zu Standort 1 zuzuordnen. Nach der Aktivierung werden Anrufe, die über das Gateway "Standort 1" weitergeleitet werden, nur an Benutzer weitergeleitet, die sich an Standort 1 befinden. Alle Anrufe, die über den trunk "Standort 1-Gateway" geleitet werden, der für Benutzer an einem anderen Standort bestimmt ist, wie etwa Standort 2, werden blockiert, um eine PSTN-Maut Umgehung zu verhindern.

Alle eingehenden PSTN-Anrufe über "Standort 1-Gateway" dürfen nur an Endpunkte an Standort 1 weitergeleitet werden. Wenn beispielsweise "lync Benutzer 1" zu Standort 2 reist, werden alle eingehenden PSTN-Anrufe über "Standort 1-Gateway" nicht an die Endpunkte von "lync User 1" an Standort 2 weitergeleitet. Dieselbe Routingregel gilt, wenn "lync Benutzer 1" zu einem unbekannten Netzwerkstandort reist, in dem der Speicherort des Benutzers nicht ermittelt werden kann.

In der folgenden Tabelle wird die Benutzerfreundlichkeit von "lync User 1" in diesem Kontext erläutert.


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
<th>Lync User 1-Endpunkte an Netzwerkstandort 1</th>
<th>Lync User 1-Endpunkte an Netzwerkstandort 2</th>
<th>Lync User 1-Endpunkte befinden sich an einem unbekannten Netzwerkstandort</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Eingehende PSTN-Anrufe an lync-Benutzer 1</p></td>
<td><p>Anrufe werden an diesem Speicherort an Endpunkte weitergeleitet.</p></td>
<td><p>Anrufe werden an diesem Speicherort nicht an Endpunkte weitergeleitet.</p></td>
<td><p>Anrufe werden an diesem Speicherort nicht an Endpunkte weitergeleitet.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="outgoing-pstn-calls"></a>Ausgehende PSTN-Anrufe

Auf VoIP-Routen wird in beiden VoIP-Richtlinien verwiesen, die direkt Benutzern zugewiesen sind, sowie auf VoIP-Routing Richtlinien, die Netzwerkstandorten zugewiesen sind. Beide Richtlinien enthalten Verweise auf Routen, die verwendet werden können, um einen Anruf anders weiterzuleiten. Beispielsweise kann ein Administrator eine VoIP-Routing Richtlinie für alle Benutzer definieren, die sich im Netzwerkstandort 1 befinden, um alle ausgehenden Anrufe über das Gateway "Standort 1" weiterzuleiten, während die VoIP-Richtlinie einiger Benutzer eine Route für alle ausgehenden Anrufe über das Gateway "Standort 2" definiert. Während sich diese Benutzer im Netzwerkstandort 1 befinden, werden Ihre ausgehenden Anrufe über das Gateway "Standort 1" weitergeleitet.

Wenn sich ein Benutzer an einem Netzwerkstandort befindet, der für Location-Based Routing konfiguriert ist, überschreibt die Route der VoIP-Routing Richtlinie des Netzwerkstandorts die VoIP-Richtlinien Route des Benutzers. Diese Regel ist besonders nützlich für Benutzer, die vorübergehend zu einer anderen Website navigieren. In diesem speziellen Fall verwendet ein Benutzer immer ein Gateway, das lokal an seinem Standort ist; Wenn sich "lync User 3" unter "Standort 2" befindet, werden alle ausgehenden Anrufe über "Standort-2-Gateway" weitergeleitet, aber wenn er zu Standort 1 reist, werden alle ausgehenden Anrufe, die bei Standort 1 getätigt werden, über "Standort 1-Gateway" weitergeleitet.

In der folgenden Tabelle wird die Benutzererfahrung von lync User 1, die einen ausgehenden Anruf von den folgenden Netzwerkstandorten aus durch zeigt, dargestellt.


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
<th>Netzwerkstandort 1</th>
<th>Netzwerkstandort 2</th>
<th>Unbekannter Netzwerkstandort oder nicht für Location-Based Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autorisierung für ausgehende Anrufe</p></td>
<td><p>VoIP-Richtlinie für lync-Benutzer 1</p></td>
<td><p>VoIP-Richtlinie für lync-Benutzer 1</p></td>
<td><p>VoIP-Richtlinie für lync-Benutzer 1</p></td>
</tr>
<tr class="even">
<td><p>Weiterleiten von ausgehenden Anrufen</p></td>
<td><p>VoIP-Routing Richtlinie für Standort 1</p></td>
<td><p>VoIP-Routing Richtlinie für Standort 2</p></td>
<td><p>VoIP-Richtlinie des Benutzers und nur für nicht für Location-Based Routing aktivierte Systeme</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="call-transfers-and-forwards"></a>Anruf Übertragungen und-Weiterleitungen

Wenn Anrufe übertragen oder weitergeleitet werden, ist das Routing von Anrufen von Location-Based Routing betroffen.

In der folgenden Tabelle wird lync-Benutzer 1, der einen PSTN-Anruf an einen anderen lync-Benutzer übertragen oder weiterleitet, dargestellt.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Benutzer, der die Anrufweiterleitung initiiert oder weiterleitet</th>
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer im Netzwerkstandort nicht für Location-Based Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync-Benutzer 1</p></td>
<td><p>Anrufweiterleitung oder-Übertragung ist zulässig</p></td>
<td><p>Anrufweiterleitung oder-Übertragung ist nicht zulässig</p></td>
<td><p>Anrufweiterleitung oder-Übertragung ist nicht zulässig</p></td>
</tr>
</tbody>
</table>

  
In der folgenden Tabelle wird veranschaulicht, wie sich Location-Based Routing auf die Weiterleitung des Anrufs basierend auf dem Standort des übertragenden lync-Benutzers (lync Benutzer 2, lync-Benutzer 4 usw.) an einen PSTN-Endpunkt auswirkt.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Endpunkt, an den der Anruf übertragen oder an diese weitergeleitet wird</th>
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer im Netzwerkstandort nicht für Location-Based Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PSTN-Endpunkt</p></td>
<td><p>Anrufweiterleitung oder-Übertragung wird über Standort 1-VoIP-Routing Richtlinie und Ausstieg über Standort 1-Gateway weitergeleitet.</p></td>
<td><p>Anrufweiterleitung oder-Übertragung wird über Standort 2-VoIP-Routing Richtlinie und Ausstieg über Standort-2-Gateway weitergeleitet.</p></td>
<td><p>Anrufweiterleitung oder-Übertragung wird über die VoIP-Richtlinie für lync-Benutzer weitergeleitet und über ein Gateway nicht für standortbasiertes Routing aktiviert (sofern verfügbar)</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="simultaneous-ringing"></a>Gleichzeitiges Klingeln

Nachdem das standortbasierte Routing in der Beispieltopologie konfiguriert wurde, werden die folgenden Interaktionen erzwungen.

In der folgenden Tabelle wird gezeigt, ob Location-Based Routing das gleichzeitige Klingeln für verschiedene lync-Benutzer ermöglicht (also lync User 2, lync User 4 usw.).


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ziel eines eingehenden PSTN-Anrufs</th>
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer im Netzwerkstandort nicht für Location-Based Routing aktiviert</th>
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

  
In der folgenden Tabelle wird gezeigt, ob Location-Based Routing das gleichzeitige Klingeln an einem PSTN-Endpunkt von verschiedenen lync-Benutzern ermöglicht (also lync User 2, lync User 4 usw.).


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
<th>Lync-Benutzer 2</th>
<th>Lync-Benutzer 4</th>
<th>Lync-Benutzer im Netzwerkstandort nicht für Location-Based Routing aktiviert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mobiltelefon für lync-Benutzer 1 (PSTN-Endpunkt)</p></td>
<td><p>Anrufweiterleitung über die VoIP-Routing Richtlinie des Netzwerkstandorts und Ausstieg über Standort 1-Gateway</p></td>
<td><p>Anruf weitergeleitet über die VoIP-Routing Richtlinie von Netzwerkstandort 2 und Ausgangspunkt über Standort 2-Gateway</p></td>
<td><p>Anrufweiterleitung über die VoIP-Richtlinie für Anrufer und Austritt über ein PSTN-Gateway, das für Location-Based Routing nicht aktiviert ist</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Planen von Location-Based Routing in lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

