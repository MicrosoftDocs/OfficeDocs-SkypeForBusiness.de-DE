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
ms.openlocfilehash: e888df769a6cf36c3285a167b61a291a7d2c8b9f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a>Konfigurieren von Enterprise-VoIP in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-12_

Um Enterprise-VoIP bereitzustellen, müssen Sie Folgendes konfigurieren:

  - Erstellen eines Trunks

  - Definieren einer VoIP-Richtlinie

  - Definieren einer VoIP-Route

  - Aktivieren von Benutzern für Enterprise-VoIP

<div>

## <a name="create-a-trunk"></a>Erstellen eines Trunks

Sie müssen Trunks in Ihrer Enterprise-VoIP-Bereitstellung definieren. Für das standortbasierte Routing müssen Sie eine trunkkonfiguration pro trunk erstellen. Verwenden Sie den lync Server Topologie-Generator, um Ihre Trunks zu definieren, und verwenden Sie den lync Server Windows PowerShell-Befehl, New-CsTrunkConfiguration oder den lync Server-Systemsteuerung, um die entsprechenden Trunk Konfigurationen zu definieren. Weitere Informationen zum Aktivieren des standortbasierten Routings auf Trunk Konfigurationen finden Sie im Abschnitt Aktivieren des standortbasierten Routings für Trunks, im Thema Aktivieren des [standortbasierten Routings in lync Server 2013](lync-server-2013-enabling-location-based-routing.md). In diesem Beispiel werden in der folgenden Tabelle die Trunks dargestellt, die in diesem Szenario verwendet werden.

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
<th>Trunk Name</th>
<th>Systemtyp</th>
<th>Name</th>
<th>Standort</th>
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
<td><p>Trunk 3 del-Nebenstellenanlage</p></td>
<td><p>PBX</p></td>
<td><p>DEL-PBX</p></td>
<td><p>Delhi</p></td>
<td><p>MS1</p></td>
</tr>
<tr class="even">
<td><p>Trunk 4 Hyd-Nebenstellenanlage</p></td>
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

Sie müssen VoIP-Richtlinien für Ihre Enterprise-VoIP-Bereitstellung definieren. Definieren Sie eine VoIP-Richtlinie zum Erzwingen von standortbasierten Routing Einschränkungen für eine Teilmenge von Benutzern, wenn nur eine Teilmenge davon für die Verwendung des standortbasierten Routings erforderlich ist. In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Richtlinien erläutert. Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.

Weitere Informationen finden Sie unter [Konfigurieren von VoIP-Richtlinien und PSTN-Verwendungsdatensätzen zum Autorisieren von Anruffunktionen und-Berechtigungen in lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).


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
<td><p>VoIP-Richtlinien-ID</p></td>
<td><p>VoIP-Richtlinie für Delhi</p></td>
<td><p>Hyderabad-VoIP-Richtlinie</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Verwendungen</p></td>
<td><p>Verwendung von Delhi, PBX del Usage, PBX Hyd</p></td>
<td><p>Verwendung von Hyderabad, Nebenstellenanlagen Hyd, PBX del Usage</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>False</p></td>
<td><p>False</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a>Definieren von VoIP-Routen

Sie müssen VoIP-Routen für Ihre Enterprise-VoIP-Bereitstellung definieren. In diesem Beispiel werden in der folgenden Tabelle die in diesem Szenario verwendeten VoIP-Routen dargestellt. Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.

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
<td><p>Nebenstellenanlage del Route</p></td>
<td><p>PBX-Hyd-Route</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Verwendungen</p></td>
<td><p>Delhi-Nutzung</p></td>
<td><p>Hyderabad-Nutzung</p></td>
<td><p>PBX del-Nutzung</p></td>
<td><p>PBX-Hyd-Verwendung</p></td>
</tr>
<tr class="odd">
<td><p>Stamm</p></td>
<td><p>Trunk 1 del-GW</p></td>
<td><p>Trunk 2 Hyd-GW</p></td>
<td><p>Trunk 3 del-Nebenstellenanlage</p></td>
<td><p>Trunk 4 Hyd-Nebenstellenanlage</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a>Aktivieren von Benutzern für Enterprise-VoIP

Aktivieren Sie Benutzer für Enterprise-VoIP, und weisen Sie Ihnen eine VoIP-Richtlinie zu, die Sie zuvor definiert haben. In diesem Beispiel wird in der folgenden Tabelle die in diesem Szenario verwendete Zuweisung dargestellt. Zur Veranschaulichung werden nur Einstellungen, die für das standortbasierte Routing spezifisch sind, in der Tabelle aufgeführt.

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
<th>Benutzer, die sich in Delhi befinden</th>
<th>Benutzer, die sich in Hyderabad befinden</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Zugeordnete VoIP-Richtlinie</p></td>
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


[Konfigurieren des standortbasierten Routings in lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

