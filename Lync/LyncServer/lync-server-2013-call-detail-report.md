---
title: 'Lync Server 2013: Anruf Detail Bericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call Detail Report
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558637(v=OCS.15)
ms:contentKeyID: 48183843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a258a5c228cfe96218c9c694b05055cc5ebd7eb6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34839712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-detail-report-in-lync-server-2013"></a>Anruf Detail Bericht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2014-02-05_

Der Anruf Detailbericht bietet einen detaillierten Überblick über einen einzelnen Anruf. der Bericht enthält nahezu alle von lync Server gesammelten Metriken für die Qualität der Benutzerfreundlichkeit und die in Berichtsabschnitte unterteilten Statistiken, wie beispielsweise:

  - Anrufinformationen

  - Gerät und Signalmetrik des Anrufers

  - Gerät und Signalmetrik des Angerufenen

  - Clientereignis des Anrufers

  - Clientereignis des Angerufenen

  - Audiodatenstrom (Anrufer zum Angerufenen)

  - Videodatenstrom (Anrufer zum Angerufenen)

  - Audiodatenstrom (Angerufener zum Anrufer)

  - Videodatenstrom (Angerufener zum Anrufer)

Beachten Sie, dass die Kategorien und Metriken in einem bestimmten Bericht zum einen vom Typ der Sitzung und zum anderen vom Typ der Endpunkte abhängen, die in der Sitzung verwendet werden. Bei einem reinen Audioanruf werden keine Metriken für Videodatenströme gemeldet, da der Anruf keinen Videodatenstrom beinhaltete. Entsprechend werden in einem Bericht ggf. zwar Anruferstatistiken, aber keine Statistiken zum Angerufen angezeigt. Dies liegt normalerweise daran, dass der Angerufene kein SIP-kompatibles Gerät verwendet. Endpunkte sind für das Melden von Statistiken am Ende des Anrufs verantwortlich. Ein Mobiltelefon (das SIP oder SIP-Statistiken nicht unterstützt) kann diese Informationen jedoch nicht melden. Wenn Sie jemanden anrufen und diese Person den Anruf auf einem Mobiltelefon entgegennimmt, erhalten Sie keinen Bericht von diesem Mobiltelefon, wenn der Anruf beendet wird.

Der Anrufdetailbericht ist sehr nützlich, wenn Sie genau feststellen möchten, warum bei einem bestimmten Anruf Probleme in Bezug auf die Medienqualität aufgetreten sind.

<div>

## <a name="accessing-the-call-detail-report"></a>Zugreifen auf den Anrufdetailbericht

Auf den Anrufdetailbericht kann von einem der folgenden Berichte aus zugegriffen werden:

  - Der [Standortbericht in lync Server 2013](lync-server-2013-location-report.md) (durch Klicken auf das Anrufvolumen oder den Prozentsatz für den schlechten Anruf)

  - Der [Bericht zur Zusammenfassung der Medienqualität in lync Server 2013](lync-server-2013-media-quality-summary-report.md) (durch Klicken auf den Prozentsatz der Anruflautstärke oder die schlechte Anruf Rate)

  - Der [Bericht zum Vergleich der Medienqualität in lync Server 2013](lync-server-2013-media-quality-comparison-report.md) (durch Klicken auf den [Bericht Anrufliste in lync Server 2013](lync-server-2013-call-list-report.md) und anschließendes Klicken auf die Detail Metrik).

  - Der [Bericht zur Serverleistung in lync Server 2013](lync-server-2013-server-performance-report.md) (durch Klicken auf den Prozentsatz der Anruflautstärke oder des schlechten Anrufs)

  - Der [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) (durch Klicken auf die Detail Metrik)

Innerhalb des Anruf Detail Berichts können Sie auf den [gerätebericht in lync Server 2013](lync-server-2013-device-report.md) zugreifen, indem Sie auf eine der folgenden Metriken klicken:

  - Aufnahmegerät

  - Darstellungsgerät

Sie können auch auf den Trendbericht über Medienqualität des Servers zugreifen, indem Sie auf die Metrik „A/V-Edgeserver“ klicken.

</div>

<div>

## <a name="making-the-best-use-of-the-call-detail-report"></a>Optimale Verwendung des Anrufdetailberichts

Der Anrufdetailbericht umfasst normalerweise 250 verschiedene Metriken. Hierzu gehören „Zeitstempelabweichung des Mikrofons“, „Geringer Rauschabstand, Zeit“ und „Nahes Ende zu Echo, Zeit“. Wenn Sie nicht genau wissen, was mit diesen Metriken gemessen wird, können Sie mit der Maus auf die Bezeichnung der Metrik zeigen. In den meisten Fällen erscheint dann eine QuickInfo mit einer Metrikbeschreibung.

Wenn Sie Probleme beim Auffinden einer Metrik haben, geben Sie einen Teil der metrischen Beschriftung im Suchfeld ein, und klicken Sie dann auf suchen. Wenn Sie beispielsweise die niedrige SNR-Zeit Metrik nicht finden können, geben Sie im Suchfeld SNR ein, und klicken Sie dann auf suchen.

Beachten Sie, dass im Bericht nur Informationen zu einem Anruf verfolgt werden. Der Anruf selbst wird nicht aufgezeichnet.

</div>

<div>

## <a name="filters"></a>Filter

Keine. Der Anrufdetailbericht lässt sich nicht filtern.

</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Anrufdetailbericht für jeden Anruf angegeben werden.

### <a name="call-detail-report-metrics"></a>Metriken im Anrufdetailbericht

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Kann nach dieser Metrik sortiert werden?</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PAI des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der den Anruf initiiert hat. Diese dient zur Übermittlung der nachgewiesenen Identität eines Benutzers innerhalb eines vertrauenswürdigen Netzwerks.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die SIP-Adresse des Benutzers, der den Anruf initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endpunkt des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das Gerät, mit dem der Anruf ausgeführt wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Benutzer-Agent des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Software, die auf dem Gerät verwendet wird, mit dem der Anruf ausgeführt wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Startzeit des Anrufs</strong></p></td>
<td><p>Nein</p></td>
<td><p>Der Zeitpunkt (Datum und Uhrzeit), zu dem der Anruf ursprünglich getätigt wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Vermittlungsserver-Umgehungsanruf</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt an, ob der Anruf mit einem PSTN-VoIP-Gateway oder einer qualifizierten IP-Nebenstellenanlage verbunden wurde, ohne dass er über den Vermittlungsserver geleitet wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Betriebssystem des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das Betriebssystem auf dem Computer des Anrufers.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPU des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die CPU, die im Computer des Benutzers installiert ist, der den Anruf initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPU-Kernnummer des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Nummer des Prozessors in dem Computer des Benutzers, der den Anruf initiiert hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPU-Geschwindigkeit des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Taktfrequenz der CPU des Computers des Benutzers, der den Anruf initiiert hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPU-Virtualisierung des Anrufers</strong></p></td>
<td><p>Nein</p></td>
<td><p>Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der den Anruf initiiert hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>PAI des Angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die P-Asserted-Identity (P-Asserted-ID) des Benutzers, der zur Teilnahme an dem Anruf eingeladen wurde. Diese dient zur Übermittlung der nachgewiesenen Identität eines Benutzers innerhalb eines vertrauenswürdigen Netzwerks.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI des Angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die SIP-Adresse des Benutzers, der angerufen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endpunkt des Angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das Gerät, mit dem der Anruf angenommen wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Benutzer-Agent des Angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Software, die auf dem Gerät verwendet wird, mit dem der Anruf angenommen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dauer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Dauer des Anrufs.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Vermittlungsserver-Umgehungswarnung</strong></p></td>
<td><p>Nein</p></td>
<td><p>Eine Warnung, die ausgegeben wird, wenn der Vermittlungsserver umgangen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Betriebssystem des Angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Das Betriebssystem auf dem Computer des Benutzers, der angerufen wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPU des Angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die CPU, die im Computer des Benutzers installiert ist, der angerufen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPU-Kernnummer des Angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Nummer des Prozessors in dem Computer des Benutzers, der angerufen wurde.</p></td>
</tr>
<tr class="odd">
<td><p><strong>CPU-Geschwindigkeit des Angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Taktfrequenz der CPU des Computers des Benutzers, der angerufen wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>CPU-Virtualisierung des Angerufenen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Ggf. die Virtualisierung, die auf dem Computer des Benutzers implementiert ist, der angerufen wurde.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

