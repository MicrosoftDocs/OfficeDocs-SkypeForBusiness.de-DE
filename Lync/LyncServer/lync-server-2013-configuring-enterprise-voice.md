---
title: 'Lync Server 2013: Konfigurieren von Enterprise-VoIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728935"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Konfigurieren von Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-12_

Zur Bereitstellung von Enterprise-VoIP müssen Sie Folgendes konfigurieren:

  - Erstellen eines Stamms

  - Definieren einer VoIP-Richtlinie

  - Definieren einer VoIP-Route

  - Enable Users for Enterprise Voice

<div>

## <a name="create-a-trunk"></a>Erstellen eines Stamms

Sie müssen Trunks in Ihrer Enterprise-VoIP-Bereitstellung definieren. Für standortbasiertes Routing müssen Sie eine trunk-Konfiguration pro trunk erstellen. Verwenden Sie den lync Server Topology Builder, um Ihre Trunks zu definieren, und verwenden Sie den lync Server Windows PowerShell-Befehl, New-CsTrunkConfiguration oder die lync Server-Systemsteuerung, um die entsprechenden Trunk-Konfigurationen zu definieren. Weitere Informationen zum Aktivieren von Standort basiertem Routing auf Trunk-Konfigurationen finden Sie im Abschnitt Aktivieren des standortbasierten Routings für Trunks im Thema Aktivieren des [standortbasierten Routings in lync Server 2013](lync-server-2013-enabling-location-based-routing.md). In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten Trunks veranschaulicht.

Weitere Informationen finden Sie unter [Definieren zusätzlicher Trunks im Topologie-Generator in lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Trunk-Name</th>
<th>Systemtyp</th>
<th>Name</th>
<th>Ort</th>
<th>Vermittlungsserver</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Trunk 1 del-GW</p></td>
<td><p>PSTN-Gateway</p></td>
<td><p>DEL-GW</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 2 Hyd-GW</p></td>
<td><p>PSTN-Gateway</p></td>
<td><p>Hyd-GW</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="odd">
<td><p>Trunk 3 del-PBX</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 4 Hyd-PBX</p></td>
<td><p>PBX</p></td>
<td><p>Hyd-PBX</p></td>
<td><p>Hyderabad</p></td>
<td><p>MS1</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a>Definiert VoIP-Richtlinien

Sie müssen VoIP-Richtlinien für Ihre Enterprise-VoIP-Bereitstellung definieren. Definieren Sie eine VoIP-Richtlinie, um standortbasierte Routing Einschränkungen für eine Teilmenge von Benutzern zu erzwingen, wenn nur eine Teilmenge von Ihnen für die Verwendung von Standort basiertem Routing erforderlich ist. In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Richtlinien veranschaulicht. Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.

Weitere Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen, um die Anruffunktionen und-Berechtigungen in lync Server 2013 zu autorisieren](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>VoIP-Richtlinie 1</th>
<th>VoIP-Richtlinie 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>VoIP-Richtlinienkennung</p></td>
<td><p>VoIP-Richtlinie für Delhi</p></td>
<td><p>Hyderabad-VoIP-Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Nutzungen</p></td>
<td><p>Nutzung von Delhi, Nutzung von Telefonanlagen, Telefonanlagen Hyd</p></td>
<td><p>Hyderabad-Nutzung, Nutzung von Telefonanlagen Hyd, Telefonanlagen Nutzung</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>Falsch</p></td>
<td><p>Falsch</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>Definieren von VoIP-Routen

Sie müssen VoIP-Routen für Ihre Enterprise-VoIP-Bereitstellung definieren. In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Routen veranschaulicht. Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.

Weitere Informationen finden Sie unter [Konfigurieren von VoIP-Routen für ausgehende Anrufe in lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>VoIP-Route 1</th>
<th>VoIP-Route 2</th>
<th>VoIP-Route 3</th>
<th>VoIP-Route 4</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Name</p></td>
<td><p>Delhi-Route</p></td>
<td><p>Hyderabad-Route</p></td>
<td><p>PBX del-Route</p></td>
<td><p>PBX-Hyd-Route</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Nutzungen</p></td>
<td><p>Delhi-Nutzung</p></td>
<td><p>Hyderabad-Nutzung</p></td>
<td><p>Telefonanlagen Nutzung</p></td>
<td><p>Verwendung von PBX-Hyd</p></td>
</tr>
<tr class="odd">
<td><p>Stamm</p></td>
<td><p>Trunk 1 del-GW</p></td>
<td><p>Trunk 2 Hyd-GW</p></td>
<td><p>Trunk 3 del-PBX</p></td>
<td><p>Trunk 4 Hyd-PBX</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Enable Users for Enterprise Voice

Aktivieren Sie Benutzer für Enterprise-VoIP, und weisen Sie Ihnen eine VoIP-Richtlinie zu, die Sie zuvor definiert haben. In diesem Beispiel wird in der folgenden Tabelle die in diesem Szenario verwendete Aufgabe veranschaulicht. Nur Einstellungen, die für standortbasierte Routings spezifisch sind, sind in der Tabelle zu Illustrationszwecken enthalten.

Weitere Informationen finden Sie unter [Aktivieren von Benutzern für Enterprise-VoIP in lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Benutzer in Delhi</th>
<th>Benutzer, die sich in Hyderabad befinden</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Zugehörige VoIP-Richtlinie</p></td>
<td><p>VoIP-Richtlinie für Delhi</p></td>
<td><p>Hyderabad-VoIP-Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>Beispiel Benutzer</p></td>
<td><p>Del-lync-1, del-lync-2, del-lync-3</p></td>
<td><p>Hyd-lync-1, Hyd-lync-2, Hyd-lync-3</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Konfigurieren von standortbasiertem Routing in Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

