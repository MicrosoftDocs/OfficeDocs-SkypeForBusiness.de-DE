---
title: 'Lync Server 2013: Übersicht über IP-Adresstypen'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: feb900c6f3d2ac426c184048986a7a751a205874
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051047"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Übersicht über IP-Adresstypen für lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-01-29_

Beim Konfigurieren von IP-Adressen in lync Server 2013 haben Sie drei Optionen. Sie können lync Server 2013 so konfigurieren, dass nur IP Version 4 (IPv4), nur IP Version 6 (IPv6) oder eine Kombination aus beidem (als *dualer Stapel*bezeichnet) unterstützt wird. Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:

  - **IPv4 nur**   IPv6 wurde erstellt, da die IPv4-Adressen auf der Welt nicht mehr funktionieren. IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen kommunizieren muss, unterstützen vielleicht derzeit noch nicht IPv6, und möglicherweise bleibt das auch noch eine ganze Weile so. Eine nur-IPv4-Konfiguration hilft sicherzustellen, dass Ihre lync Server Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.

  - **IPv6 nur**   umgekehrt wird eine vollständige IPv6-Implementierung zu diesem Zeitpunkt die Kommunikation mit vielen vorhandenen Geräten ausschließen.

  - **Dual Stack**   Dual Stack ist ein Netzwerk, in dem sowohl IPv4-als auch IPv6-Adressen aktiviert sind. Diese Konfiguration wird in lync Server 2013 unterstützt, da in den meisten Fällen der Übergang von voll-IPv4 zu voll-IPv6 einige Jahre dauern wird.

In den folgenden Abschnitten wird die Kompatibilität zwischen diesen drei Konfigurationen für verschiedene lync Server Features erläutert.

<div>


> [!NOTE]  
> Client- oder Serverkonfiguration mit reinem IPv6 wird nur zu Labor- oder Validierungszwecken unterstützt. Eine reine IPv6-Konfiguration wird in der Produktionsbereitstellung nicht unterstützt.



</div>

<div>

## <a name="client-registration"></a>Clientregistrierung


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clientendpunkt-Netzwerk</th>
<th>Servernetzwerk</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="odd">
<td><p>Dualer Stapel</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Dualer Stapel</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="odd">
<td><p>Dualer Stapel</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a>Peer-zu-Peer-Client

Peer-zu-Peer-Kommunikation umfasst Audio, Audio/Video, Anwendungsfreigabe und Dateiübertragung. Nach der erfolgreichen Registrierung beider Clients werden die folgenden Kombinationen unterstützt.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clientendpunkt 1</th>
<th>Clientendpunkt 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="odd">
<td><p>Dualer Stapel</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a>Konferenzen

Konferenzfunktionen beinhalten Audio/Video, Anwendungsfreigabe und Zusammenarbeit an Daten (Whiteboards und Dateifreigabe).


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Clientendpunkt-Netzwerk</th>
<th>Servernetzwerk</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>IPv4</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="odd">
<td><p>Dualer Stapel</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Dualer Stapel</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="odd">
<td><p>Dualer Stapel</p></td>
<td><p>IPv6</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a>Vermittlungsserver/PSTN

Lync Server 2013 unterstützt keine medienumgehung für PSTN-Anrufe (Public Switched Telephone Network), wenn der Datenverkehr über eine IPv6-Schnittstelle erfolgt. Wenn Medienumgehung erforderlich ist, sollten Sie das PSTN-Gateway mit IPv4 konfigurieren.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Primäre Schnittstelle*</th>
<th>PSTN-Schnittstelle (auf dem Vermittlungsserver)</th>
<th>Einstellung für das PSTN-Gateway</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>Dualer Stapel</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Dualer Stapel</p></td>
<td><p>Dualer Stapel</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Dualer Stapel</p></td>
<td><p>Dualer Stapel</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


\*Die primäre Schnittstelle ist die Schnittstelle, die mit den lync Server Komponenten kommuniziert.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>Peer-zu-Peer-Kommunikation mit Remotebenutzern

Peer-zu-Peer-Kommunikation mit Remotebenutzern umfasst Sofortnachrichten, Audio/Video, Anwendungsfreigabe und Dateiübertragung.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Netzwerk des Remotebenutzers</th>
<th>Edgeserver (externer Edge)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IPv4</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="even">
<td><p>Dualer Stapel</p></td>
<td><p>IPv4</p></td>
</tr>
<tr class="odd">
<td><p>Dualer Stapel</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="even">
<td><p>IPv6</p></td>
<td><p>Dualer Stapel</p></td>
</tr>
<tr class="odd">
<td><p>IPv6</p></td>
<td><p>IPv6</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a>Konfiguration mit Front-End-Pool und Edgepool

In der folgenden Tabelle ist die Unterstützungsmatrix zwischen dem Front-End-Server Pool und dem internen Edgeserver Pool dargestellt.

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a>Schema der unterstützten Kombinationen zwischen Front-End-Pool und Edgepool (interner Edge)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Edgepool: IPv4</strong></p></td>
<td><p><strong>Edgepool: Dualer Stapel</strong></p></td>
<td><p><strong>Edgepool: IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Front-End-Pool: IPv4</strong></p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p><strong>Front-End-Pool: Dualer Stapel</strong></p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p><strong>Front-End-Pool: IPv6</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Ja*</p></td>
</tr>
</tbody>
</table>


\*Verwenden Sie diese Kombination nur in einer Lab-Umgebung.

Die folgende Tabelle zeigt, welche Kombinationen zwischen den internen und externen Edge-Schnittstellen unterstützt werden.

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a>Schema der unterstützten Kombinationen zwischen Edgepool (interner Edge) und Edgepool (externer Edge)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><strong>Edgepool (externer Edge): IPv4</strong></p></td>
<td><p><strong>Edgepool (Externer Edge): Dualer Stapel</strong></p></td>
<td><p><strong>Edgepool (Externer Edge): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Edgepool (interner Edge): IPv4</strong></p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p><strong>Edgepool (interner Edge): Dualer Stapel</strong></p></td>
<td><p>Nein</p></td>
<td><p>Ja</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p><strong>Edgepool (interner Edge): IPv6</strong></p></td>
<td><p>Nein</p></td>
<td><p>Nein</p></td>
<td><p>Ja*</p></td>
</tr>
</tbody>
</table>


\*Verwenden Sie diese Kombination nur in einer Lab-Umgebung.

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a>Erweiterte Unterstützung für Enterprise-VoIP für IPv6

Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E9-1-1-Notrufdienste oder Medienumgehung beinhalten, müssen als Implementierung nur mit IPv4 oder als Dualer-Stapel-Implementierung konfiguriert werden.

<div>


> [!NOTE]  
> In einer Dual-Stacked-Bereitstellung, auch wenn ein lync-Client eine Verbindung mit einem lync Server mithilfe von IPv6 herstellt, bemühen sich lync am besten, eine geeignete IPv4-Adresse zur Unterstützung von E9-1-1 zuzuordnen.



</div>

Standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.

Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Unterstützung anderer lync Server 2013 Features für IPv6

Zusätzlich zu den zuvor erwähnten Features und Komponenten unterstützt lync Server 2013 IPv6 für die folgenden Features:

  - **Beständiger Chat**
    
    Sie konfigurieren IPv6 für beständigen Chat mithilfe des Topologie-Generators. Ausführliche Informationen zum Konfigurieren des beständigen Chats finden Sie in der Dokumentation Deploying persistent Chat Server.

  - **QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen**
    
    In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

