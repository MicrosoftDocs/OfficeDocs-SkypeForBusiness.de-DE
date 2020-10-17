---
title: 'Lync Server 2013: Konfigurieren des Location-Based Routings'
description: 'Lync Server 2013: Konfigurieren des Location-Based Routings.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570881"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Konfigurieren Location-Based Routings in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-03-12_

Lync Server 2013 ku1 ist Location-Based Routing ein Feature von Enterprise-VoIP. Location-Based Routing ist ein Anruf Verwaltungsfeature, das steuert, wie Anrufe von lync Server 2013 ku1 weitergeleitet werden. Es erzwingt Einschränkungen, ob Anrufe basierend auf dem Standort des lync-Anrufers an PBX-oder PSTN-Ziele weitergeleitet werden können. Location-Based Routing wendet Anruf Autorisierungsregeln basierend auf dem Netzwerkstandort des Anrufers auf PSTN-Anrufe an. Der Speicherort des Anrufers wird basierend auf dem Netzwerkstandort bestimmt, der dem Netzwerk Subnetz zugeordnet ist, mit dem der Anrufer verbunden ist. Zum Konfigurieren Location-Based Routings müssen Sie zunächst Enterprise-VoIP bereitstellen und dann netzwerkregionen, Standorte und Subnetze konfigurieren. Dadurch wird die Grundlage für die Aktivierung Location-Based Routings eingerichtet.

Vor der Bereitstellung Location-Based Routing müssen Sie zunächst Enterprise-VoIP bereitstellen und netzwerkregionen,-Standorte und Netzwerk-Subnetze ihren Netzwerkstandorten zuordnen. Nach Abschluss des Vorgangs können Sie Location-Based Routing konfigurieren. Schritte zum Konfigurieren von netzwerkregionen, Standorten und Subnetzen finden Sie unter [Deploying Advanced Enterprise Voice Features in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Dieser Abschnitt führt Sie durch die Konfiguration von Location-Based Routing mit dem folgenden Beispiel als Illustration.

![Beispiel für Enterprise-VoIP-standortbasiertes Routing](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Beispiel für Enterprise-VoIP-standortbasiertes Routing")

  
In der folgenden Tabelle werden die in diesem Beispiel definierten Benutzer dargestellt.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Endpunkttyp</th>
<th>Standort</th>
<th>Benutzer</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Unternehmenszentrale in Delhi</p></td>
<td><p>Del-lync-1, del-lync-2, del-lync-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Firmenzentrale in Hyderabad</p></td>
<td><p>Hyd-lync-1, Hyd-lync-2, Hyd-lync-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Unbekannt (d. h. Hotel)</p></td>
<td><p>Unk-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>PBX</p></td>
<td><p>Unternehmenszentrale in Delhi</p></td>
<td><p>Del-PBX-1, del-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>PBX</p></td>
<td><p>Firmenzentrale in Hyderabad</p></td>
<td><p>Hyd-PBX-1, Hyd-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>Unbekannt</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

Die folgende Tabelle stellt die in dieser Beispielumgebung dargestellten Systeme dar.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>System</th>
<th>Standort</th>
<th>Name</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 ku1-Pool</p></td>
<td><p>Beliebiger Wert</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 ku1, Vermittlungsserver</p></td>
<td><p>Beliebiger Wert</p></td>
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
<td><p>Nebenstellenanlage 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>Nebenstellenanlage 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>Red-PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>In diesem Abschnitt

  - [Konfigurieren von Enterprise-VoIP in lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Bereitstellen von netzwerkregionen, Standorten und Subnetzen in lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Aktivieren Location-Based Routings in lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Bereitstellen von erweiterten Enterprise-VoIP-Funktionen in lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

