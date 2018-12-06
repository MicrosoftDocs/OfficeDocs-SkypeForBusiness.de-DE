---
title: 'Lync Server 2013: Übersicht über IP-Adresstypen'
TOCTitle: Übersicht über IP-Adresstypen für Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205363(v=OCS.15)
ms:contentKeyID: 49295824
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Übersicht über IP-Adresstypen für Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Beim Konfigurieren von IP-Adressen in Lync Server 2013 haben Sie drei Optionen. Sie können Lync Server 2013 so konfigurieren, dass es nur IP Version 4 (IPv4), nur IP Version 6 (IPv6) oder aber eine Kombindation aus beiden (auch *dualer Stapel* genannt) unterstützt. Bei jedem Konfigurationstyp sind bestimmte Punkte zu beachten:

  - **Nur IPv4**   IPv6 wurde entwickelt, weil es auf der Welt immer weniger IPv4-Adressen gibt. IPv6 wird sich letztendlich weltweit durchsetzen, aber viele Unternehmen und Geräte, mit denen Ihr Unternehmen kommunizieren muss, unterstützen vielleicht derzeit noch nicht IPv6, und möglicherweise bleibt das auch noch eine ganze Weile so. Mit einer Nur-IPv4-Konfiguration können Sie sicherstellen, dass Ihre Lync Server-Implementierung mit den meisten vorhandenen Geräten kommunizieren kann.

  - **Nur IPv6**   Andersherum wird eine reine IPv6-Implementierung die Kommunikation mit vielen vorhandenen Geräten derzeit noch ausschließen.

  - **Dualer Stapel**   Beim dualen Stapel werden sowohl IPv4- als auch IPv6-Adressen unterstützt. Diese Konfiguration wird in Lync Server 2013 unterstützt, weil die Umstellung von reinem IPv4 auf reines IPv6 meist mehrere Jahre dauert.

In den folgenden Abschnitten wird die Kompatibilität zwischen diesen drei Konfigurationen in Bezug auf verschiedene Features von Lync Server beschrieben.


> [!NOTE]
> Client- oder Serverkonfiguration mit reinem IPv6 wird nur zu Labor- oder Validierungszwecken unterstützt. Eine reine IPv6-Konfiguration wird in der Produktionsbereitstellung nicht unterstützt.



## Clientregistrierung


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


## Peer-zu-Peer-Client

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


## Konferenzen

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


## Vermittlungsserver/PSTN

Lync Server 2013 unterstützt keine Medienumgehung für PSTN-Anrufe (Public Switched Telephone Network, Festnetz), wenn der Datenverkehr über eine IPv6-Schnittstelle abgewickelt wird. Wenn Medienumgehung erforderlich ist, sollten Sie das PSTN-Gateway mit IPv4 konfigurieren.


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


\* Die primäre Schnittstelle ist die Schnittstelle, die mit den Lync Server-Komponenten kommuniziert.

## Peer-zu-Peer-Kommunikation mit Remotebenutzern

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


## Konfiguration mit Front-End-Pool und Edgepool

Die folgende Tabelle zeigt, welche Kombinationen zwischen dem Front-End-Server-Pool und dem internen Edgeserver-Pool unterstützt werden.

### Schema der unterstützten Kombinationen zwischen Front-End-Pool und Edgepool (interner Edge)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
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


\* Verwenden Sie diese Kombination nur in einer Laborumgebung.

Die folgende Tabelle zeigt, welche Kombinationen zwischen den internen und externen Edge-Schnittstellen unterstützt werden.

### Schema der unterstützten Kombinationen zwischen Edgepool (interner Edge) und Edgepool (externer Edge)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p></p></td>
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


\* Verwenden Sie diese Kombination nur in einer Laborumgebung.

## Erweiterte Unterstützung für Enterprise-VoIP für IPv6

Bereitstellungen, die Anrufsteuerung (Call Admission Control, CAC), E9-1-1-Notrufdienste oder Medienumgehung beinhalten, müssen als Implementierung nur mit IPv4 oder als Dualer-Stapel-Implementierung konfiguriert werden.


> [!NOTE]
> In einer Implementierung mit dualem Stapel versucht Lync selbst dann, wenn ein Lync-Client über IPv6 eine Verbindung mit einem Lync Server herstellt, eine geeignete IPv4-Adresse zur Unterstützung von E9-1-1-Notrufdiensten zuzuordnen.



Standortinformationsdienst mit IPv6-Adressen wird nicht unterstützt.

Exchange Unified Messaging (UM) unterstützt IPv6 nicht. Stellen Sie sicher, dass die DNS-Auflösung für Exchange UM keine IPv6-Adresse zurückgibt. Die Verwendung von IPv6 kann Fehler verursachen, wenn Anrufe an Voicemail gesendet werden.

## Unterstützung von IPv6 für andere Lync Server 2013-Features

Zusätzlich zu den oben erwähnten Features und Komponenten wird IPv6 in Lync Server 2013 für die folgenden Features unterstützt:

  - **Beständiger Chat**
    
    Sie verwenden den Topologie-Generator, um IPv6 für Beständiger Chat zu konfigurieren. Ausführliche Informationen zum Konfigurieren von Beständiger Chat finden Sie in der Dokumentation "Bereitstellen von Persistent Chat Server".

  - **QoE-Berichte und Berichte über die Aufzeichnung von Kommunikationsdatensätzen**
    
    In Monitoring-Berichten wird die IP-Adresse so angegeben, wie sie in der Monitoring Server-Datenbank gespeichert ist, unabhängig davon, ob der Adresstyp IPv4 oder IPv6 ist.

