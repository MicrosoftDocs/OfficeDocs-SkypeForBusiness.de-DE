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
ms.openlocfilehash: 9d1172fc7da9600de036312adb05548b51dea6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a>Übersicht über IP-Adresstypen für Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-01-29_

Bei der Konfiguration von IP-Adressen in lync Server 2013 stehen Ihnen drei Optionen zur Auswahl. Sie können lync Server 2013 so konfigurieren, dass nur IP, Version 4 (IPv4), nur IP Version 6 (IPv6) oder eine Kombination aus beidem (als *dualer Stack*bezeichnet) unterstützt wird. Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:

  - ****   IPv6 wurde nur erstellt, weil die IPv4-Adressen für die Welt nicht verfügbar sind. IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen möglicherweise kommunizieren muss, unterstützen derzeit noch nicht IPv6 und möglicherweise bleibt das auch noch eine ganze Weile so. Eine reine IPv4-Konfiguration wird dabei helfen, sicherzustellen, dass Ihre lync Server-Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.

  - **IPv6 nur**   umgekehrt schließt eine vollständige IPv6-Implementierung zu diesem Zeitpunkt die Kommunikation mit vielen vorhandenen Geräten aus.

  - **Dual Stack**   Dual Stack ist ein Netzwerk, in dem sowohl IPv4-als auch IPv6-Adressen aktiviert sind. Diese Konfiguration wird in lync Server 2013 unterstützt, da in den meisten Fällen der Übergang von Full-IPv4 zu voll-IPv6 mehrere Jahre dauern wird.

In den folgenden Abschnitten wird die Kompatibilität zwischen diesen drei Konfigurationen für verschiedene lync Server-Features erläutert.

<div>


> [!NOTE]  
> Client- oder Serverkonfiguration mit reinem IPv6 wird nur zu Labor- oder Validierungszwecken unterstützt. Eine reine IPv6-Konfiguration wird in der serienmäßigen Bereitstellung nicht unterstützt.



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

## <a name="peer-to-peer-client"></a>Peer-to-Peer-Client

Peer-to-Peer-Kommunikation umfasst Audio, Audio/Video, Anwendungsfreigabe und Dateiübertragung. Nach der erfolgreichen Registrierung beider Clients werden die folgenden Kombinationen unterstützt.


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

Konferenz umfasst Audio/Video, Anwendungsfreigabe und Datenzusammenarbeit (Whiteboards und Dateifreigabe).


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


\*Die primäre Schnittstelle ist die Schnittstelle, die mit den lync Server-Komponenten kommuniziert.

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a>Peer-to-Peer-Kommunikation mit Remotebenutzern

Peer-to-Peer-Kommunikation mit Remotebenutzern umfasst Sofortnachrichten, Audio/Video, Anwendungsfreigabe und Dateiübertragung.


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

Die folgende Tabelle zeigt die Support Matrix zwischen dem Front-End-Serverpool und dem internen Edge-Serverpool.

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
<td><p>Ja </p></td>
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
<td><p><strong>Edgepool (Externer Edge): IPv4</strong></p></td>
<td><p><strong>Edgepool (Externer Edge): Dualer Stapel</strong></p></td>
<td><p><strong>Edgepool (Externer Edge): IPv6</strong></p></td>
</tr>
<tr class="even">
<td><p><strong>Edgepool (Interner Edge): IPv4</strong></p></td>
<td><p>Ja</p></td>
<td><p>Ja</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="odd">
<td><p><strong>Edgepool (Interner Edge): Dualer Stapel</strong></p></td>
<td><p>Nein</p></td>
<td><p>Ja</p></td>
<td><p>Nein</p></td>
</tr>
<tr class="even">
<td><p><strong>Edgepool (Interner Edge): IPv6</strong></p></td>
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

Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E911-Notrufdienste oder Medienumgehung beinhalten, können nur mit IPv4 oder als Implementierung mit dualem Stapel konfiguriert werden.

<div>


> [!NOTE]  
> In einer Dual-Stacked-Bereitstellung, auch wenn ein lync-Client eine Verbindung mit einem lync-Server mithilfe von IPv6 herstellt, bemüht sich lync, eine geeignete IPv4-Adresse zuzuordnen, um E9-1-1 zu unterstützen.



</div>

Der standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.

Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden.

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a>Andere lync Server 2013-Feature-Unterstützung für IPv6

Zusätzlich zu den zuvor erwähnten Features und Komponenten unterstützt lync Server 2013 IPv6 für die folgenden Features:

  - **Beständiger Chat**
    
    Sie konfigurieren IPv6 für beständigen Chat mithilfe des Topologie-Generators. Details zum Konfigurieren des beständigen Chats finden Sie in der Dokumentation zum Bereitstellen des beständigen Chats.

  - **QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen (KDS)**
    
    In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.

</div>

</div>

<span> </span>

</div>

</div>

</div>

