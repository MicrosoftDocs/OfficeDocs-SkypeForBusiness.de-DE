---
title: 'Lync Server 2013: Konfigurieren von standortbasiertem Routing'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a682f6b550f982f929a83bc8c2f430e89b9452fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Konfigurieren von standortbasiertem Routing in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-03-12_

Lync Server 2013 CU1, standortbasiertes Routing ist eine Funktion von Enterprise-VoIP. Standortbasiertes Routing ist ein Anruf Verwaltungsfeature, das steuert, wie Anrufe von lync Server 2013 CU1 weitergeleitet werden. Sie erzwingt Einschränkungen, ob Anrufe an PBX-oder PSTN-Ziele basierend auf dem Standort des lync-Anrufers weitergeleitet werden können. Standortbasiertes Routing wendet Anruf Autorisierungsregeln für PSTN-Anrufe auf der Grundlage des Netzwerkspeicherorts des Anrufers an. Der Standort des Anrufers wird anhand der Netzwerk Website bestimmt, die dem Netzwerk-Subnetz zugeordnet ist, an dem der Anrufer angeschlossen ist. Zum Konfigurieren des standortbasierten Routings muss zuerst Enterprise-VoIP bereitgestellt und dann netzwerkregionen,-Standorte und-Subnetze konfiguriert werden. Damit wird die Grundlage für die Aktivierung des standortbasierten Routings eingerichtet.

Vor der Bereitstellung von Standort basiertem Routing müssen Sie zuerst Enterprise-VoIP bereitstellen und netzwerkregionen,-Standorte und Netzwerk-Subnetze an Ihre Netzwerk Websites anschließen. Nach Abschluss des Vorgangs können Sie standortbasiertes Routing konfigurieren. Eine schrittweise Anleitung zum Konfigurieren von netzwerkregionen,-Websites und-Subnetzen finden Sie unter [Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Dieser Abschnitt führt Sie durch die Konfiguration des standortbasierten Routings mit dem folgenden Beispiel als Abbildung.

![Beispiel für standortbasiertes Routing für Enterprise-VoIP] (images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Beispiel für standortbasiertes Routing für Enterprise-VoIP")

  
In der folgenden Tabelle sind die in diesem Beispiel definierten Benutzer dargestellt.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Endpunkttyp</th>
<th>Ort</th>
<th>Nutzer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Firmensitz in Delhi</p></td>
<td><p>Del-lync-1, del-lync-2, del-lync-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Firmensitz in Hyderabad</p></td>
<td><p>Hyd-lync-1, Hyd-lync-2, Hyd-lync-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Unbekannt (z.b. Hotel)</p></td>
<td><p>Unk-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>Firmensitz in Delhi</p></td>
<td><p>Del-PBX-1, del-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Firmensitz in Hyderabad</p></td>
<td><p>Hyd-PBX-1, Hyd-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>Telefonfestnetz (PSTN)</p></td>
<td><p>Unbekannten</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

In der folgenden Tabelle sind die in dieser Beispielumgebung dargestellten Systeme dargestellt.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>System</th>
<th>Ort</th>
<th>Name</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 CU1-Pool</p></td>
<td><p>Beliebig</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, Vermittlungsserver</p></td>
<td><p>Beliebig</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>PSTN-Gateway 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>PSTN-Gateway 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>Hyd-GW</p></td>
</tr>
<tr class="odd">
<td><p>Telefonanlage 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>Red-PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von Enterprise-VoIP in lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Bereitstellen von netzwerkregionen,-Websites und-Subnetzen in lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Aktivieren des standortbasierten Routings in lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von erweiterten Enterprise-VoIP-Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

