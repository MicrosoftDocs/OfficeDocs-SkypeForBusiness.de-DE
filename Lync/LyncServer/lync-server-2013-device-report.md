---
title: 'Lync Server 2013: gerätebericht'
description: 'Lync Server 2013: gerätebericht.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bff8e973d5c3e2d96c18992a2a2d917d4deb1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575121"
---
# <a name="device-report-in-lync-server-2013"></a>Gerätebericht in lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-11-12_

Der gerätebericht kann besser mit dem Titel Mikrofon und Lautsprecher gemeldet werden. Das liegt daran, dass der gerätebericht anrufbezogene Metriken (wie Prozentsatz für schlechte Anrufe, Echos und Zeit für den Sprachwechsel) abruft, die von den Mikrofonen und Lautsprechern gruppiert werden, die im Anruf verwendet werden. Wenn Sie an IP-Telefonen interessiert sind (auch allgemein als "Geräte" bezeichnet), verwenden Sie stattdessen den Bericht über den [IP-Telefon bestand in lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .

Der gerätebericht ist für Administratoren äußerst nützlich, wenn Sie feststellen, ob ein bestimmter Gerätetyp hohe Mengen schlechter Qualität als andere Anrufe erfährt. Dies kann wiederum alle Entscheidungen beeinflussen, die Sie treffen müssen, wenn es an der Zeit ist, neue Geräte zu kaufen oder vorhandene Geräte zu ersetzen.

Die im gerätebericht angezeigten Informationen basieren standardmäßig auch auf dem Mikrofon (dem Aufnahmegerät) und dem Lautsprecher/Headset (dem Render-Gerät), das im Anruf verwendet wird. Nehmen wir beispielsweise an, Sie haben mehrere Benutzer, die das folgende Aufnahmegerät und das folgende Render-Gerät verwenden: Standardmäßig basieren die im gerätebericht angezeigten Informationen auch auf dem Mikrofon (dem Aufnahmegerät) und dem Lautsprecher/Headset (dem Render-Gerät), das im Anruf verwendet wird. Nehmen wir beispielsweise an, Sie haben mehrere Benutzer, die das folgende Capture-Gerät und das folgende Render-Gerät verwenden:

  - Capture Device--Mikrofon (Soundmax Integrated Digital HD Audio)

  - Render-Gerät--Headset-Ohrhörer (Microsoft LifeChat LX-3000)

Wenn diese Benutzer insgesamt 254 Anrufe getätigt haben, sehen Sie einen Eintrag wie den folgenden im Bericht:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Aufnahmegerät</th>
<th>Darstellungsgerät</th>
<th>Anruflautstärke</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mikrofon (Soundmax Integrated Digital HD Audio)</p></td>
<td><p>Headset-Ohrhörer (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


Angenommen, Sie verfügen über eine Reihe von Benutzern, die dasselbe Aufnahmegerät verwenden, aber ein anderes Render-Gerät. In diesem Fall haben Sie einen zweiten Zeile-Eintrag im Bericht, einen für diese eindeutige Kombination aus Capture Device und Render Device:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Aufnahmegerät</th>
<th>Darstellungsgerät</th>
<th>Anruflautstärke</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mikrofon (Soundmax Integrated Digital HD Audio)</p></td>
<td><p>Headset-Ohrhörer (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Mikrofon (Soundmax Integrated Digital HD Audio)</p></td>
<td><p>Lautsprecher (Soundmax Integrated Digital HD Audio)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


Wenn Sie lieber kombinierte Gesamtsummen für ein bestimmtes Gerät (beispielsweise für das SoundMAX-Aufnahmegerät, unabhängig vom verwendeten Render-Gerät) anzeigen möchten, wählen Sie in der Dropdownliste Gerätetyp die entsprechende Option aus (entweder Capture-Gerät oder Render-Gerät). Wenn Sie in diesem Beispiel Capture Device auswählen, erhalten Sie eine ähnliche Ausgabe wie die folgende:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Aufnahmegerät</th>
<th>Anruflautstärke</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mikrofon (Soundmax Integrated Digital HD Audio)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>Zugreifen auf den gerätebericht

Auf den gerätebericht wird normalerweise über die Startseite für Überwachungsberichte zugegriffen. Wenn Sie jedoch den [Anruf Detail Bericht in lync Server 2013](lync-server-2013-call-detail-report.md) anzeigen, können Sie durch Klicken auf eine der folgenden Metriken einen Drilldown zum gerätebericht für ein bestimmtes Gerät ausführen:

  - Capture-Gerät

  - Render-Gerät

Im gerätebericht können Sie einen Drilldown zum [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:

  - Anrufvolumen

  - Prozentsatz der Anrufe schlechter Qualität

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>Optimale Verwendung des Geräte Berichts

Wenn es um Gerätenamen geht, ist der gerätebericht äußerst detailliert; nehmen wir beispielsweise an, Sie haben die folgenden Capture-Geräte:

  - Aastra 3002-Mikrofon (2-Aastra 3002)

  - Aastra 3002-Mikrofon (3-Aastra 3002)

  - Aastra 3002-Mikrofon (Aastra 3002)

  - Aastra 6725ip

  - Aastra 6725ip-Mikrofon (10-Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (10-Aastra 6725ip)-v0

  - Aastra 6725ip-Mikrofon (2-Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (3-Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (4-Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (5-Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (6-Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (7-Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (9-Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (9-Aastra 6725ip)-v0

  - Aastra 6725ip-Mikrofon (Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (Aastra 6725ip)-v0

  - Aastra 6725ip-Mikrofon (USB-Audiogerät)

  - Aastra 6725ip-Mikrofon (USB-Audiogerät)-v0

<div>


> [!NOTE]  
> Beachten Sie, dass Capture-Gerätenamen möglicherweise nicht identisch sind, wenn Sie lokalisierte Versionen von lync Server 2013 durchführen. Ein Gerät namens Aastra 6725ip Mikrofon (Aastra 6725ip)-v0 in US-Englisch könnte in Französisch oder Spanisch einen anderen Namen haben.



</div>

Oft werden Sie diese Detailgenauigkeit wünschen. zu anderen Zeiten sind Sie jedoch möglicherweise nur daran interessiert, wie viele Anrufe ein Aastra-Mikrofon unabhängig von der Modellnummer verwenden. Eine Möglichkeit zum Abrufen von Informationen wie das ist das Exportieren der Geräte Berichtsdaten in Microsoft Excel und das anschließende Speichern dieser Daten in einer Datei mit Komma getrennten Werten (beispielsweise C: \\ Daten \\ Geräte \_Report.csv). Anschließend können Sie eine Reihe von Befehlen wie diese verwenden, um die zu importieren. CSV-Datei in Windows PowerShell und melden Sie die Gesamtzahl der Anrufe, die mit einem Aastra Capture-Gerät ausgeführt wurden, zurück:

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

Dadurch wird ein einzelner Wert zurückgegeben, der die Gesamtzahl der mit einem Aastra Capture-Gerät getätigten Anrufe darstellt. Zum Beispiel:

    384

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie mit dem gerätebericht nach solchen Dingen wie dem Anruftyp (also dem Anruf eines Client Anrufs), einer Telefonkonferenz oder einem PSTN-Anruf (Public Switched Telephone Network) filtern. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Geräte nach Stunde, Tag, Woche oder Monat gruppiert.

In der folgenden Tabelle sind die Filter aufgeführt, die Sie mit dem gerätebericht verwenden können.

### <a name="device-report-filters"></a>Geräte Berichtsfilter

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Name</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ziel</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>07.07.2012 13:00</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ursache für VoIP-Switch</strong></p></td>
<td><p>Grund, warum ein Anruf in den Halbduplexmodus versetzt werden musste, um Echo zu verhindern. Im Halbduplexmodus kann die Kommunikation gleichzeitig nur in eine Richtung erfolgen, ähnlich wie die Benutzer beim kommunizieren mit einem Walkie-Talkie abwechselnd wechseln. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>Alle</p>
</dd>
<dt><span></span></dt>
<dd><p>Keine</p>
</dd>
<dt><span></span></dt>
<dd><p>Falscher Zeitstempel</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (dynamischer nichtlinearer Prozessor)</p>
</dd>
<dt><span></span></dt>
<dd><p>Geringe Komplexität</p>
</dd>
<dt><span></span></dt>
<dd><p>Ungültiger Gerätestatus</p>
</dd>
<dt><span></span></dt>
<dd><p>Post-AEC-Echo (akustische Echounterdrückung)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Echo Ursache</strong></p></td>
<td><p>Grund, warum Echo oberhalb der akzeptierten Ebene in einem Anruf erkannt wurde. (In der Telekommunikation ist ECHO eine Reflexion des Klangs, das gleiche Phänomen, das Sie hören, wenn Sie auf den Grund eines Brunnens schreien.) Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>Alle</p>
</dd>
<dt><span></span></dt>
<dd><p>Keine</p>
</dd>
<dt><span></span></dt>
<dd><p>Falscher Zeitstempel</p>
</dd>
<dt><span></span></dt>
<dd><p>Post-AEC-Echo (akustische Echounterdrückung)</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (adaptiver nichtlinearer Prozessor)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (dynamischer nichtlinearer Prozessor)</p>
</dd>
<dt><span></span></dt>
<dd><p>Mikrofon Clipping</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Anruftyp</strong></p></td>
<td><p>Gibt den Typ des Anrufs an, der ausgeführt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>Alle</p>
</dd>
<dt><span></span></dt>
<dd><p>Client Anruf</p>
</dd>
<dt><span></span></dt>
<dd><p>PSTN-Anruf</p>
</dd>
<dt><span></span></dt>
<dd><p>Konferenzanruf</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Zugriffstyp</strong></p></td>
<td><p>Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>Alle</p>
</dd>
<dt><span></span></dt>
<dd><p>Intern</p>
</dd>
<dt><span></span></dt>
<dd><p>Extern</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Netzwerktyp</strong></p></td>
<td><p>Gibt den Typ des Netzwerks an, mit dem der Client verbunden wurde, als der Anruf erfolgte. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>Alle</p>
</dd>
<dt><span></span></dt>
<dd><p>Wired</p>
</dd>
<dt><span></span></dt>
<dd><p>Drahtlos</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>Alle</p>
</dd>
<dt><span></span></dt>
<dd><p>VPN</p>
</dd>
<dt><span></span></dt>
<dd><p>Nicht-VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Gerätetyp</strong></p></td>
<td><p>Gibt den Gerätetyp an. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>Aufnahmegerät</p>
</dd>
<dt><span></span></dt>
<dd><p>Darstellungsgerät</p>
</dd>
<dt><span></span></dt>
<dd><p>Paar für Capture/Render-Geräte</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Gerätename</strong></p></td>
<td><p>Name des Capture-oder Render-Geräts. Sie können den vollständigen Gerätenamen oder einen Teil des Gerätenamens eingeben. Um beispielsweise das Gerätemikrofon zu finden (Microsoft LifeCam VX-1000.), können Sie den vollständigen Gerätenamen wie folgt eingeben:</p>
<p>Mikrofon (Microsoft LifeCam VX-1000.)</p>
<p>Sie können auch nur einen Teil des Namens eingeben. Zum Beispiel:</p>
<p>LifeCam</p>
<p>Beachten Sie, dass der obige Filter jedes Gerät zurückgibt, das die Zeichenfolge &quot; LifeCam &quot; Anywhere in seinem Namen enthält.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle sind die Informationen aufgeführt, die im gerätebericht angegeben werden.

### <a name="device-report-metrics"></a>Metriken für den gerätebericht

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
<td><p><strong>Aufnahmegerät</strong></p></td>
<td><p>Ja</p></td>
<td><p>Gerät (zum Beispiel ein Mikrofon oder eine Webcam), das für die Übertragung von Audio verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Darstellungsgerät</strong></p></td>
<td><p>Ja</p></td>
<td><p>Gerät (zum Beispiel ein Headset oder Lautsprecher), das zum Empfangen von Audio verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anruflautstärke</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die Gesamtzahl der getätigten Anrufe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der Anrufe schlechter Qualität</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz der Anrufe, die als unzureichend klassifiziert wurden &quot; . &quot; Bei einem schlechten Anruf handelt es sich um einen Anruf, bei dem mindestens eine der gemessenen Metriken den zulässigen Wert überschritten hat (beispielsweise ein Anruf, bei dem übermäßiger Jitter aufgetreten ist).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Eindeutige Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige Benutzer, die das Gerät verwendet haben. Wenn ein Benutzer das Gerät 13 Mal verwendet hat, würde er als ein eindeutiger Benutzer gezählt, derselbe wie ein Benutzer, der das Gerät nur ein einziges Mal verwendet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Verhältnis der Zeit für die Sprachumstellung</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz des Anrufs, der im Halbduplexmodus durchgeführt werden musste, um Echo zu verhindern. Im Halbduplexmodus kann die Kommunikation gleichzeitig nur in eine Richtung erfolgen, ähnlich wie die Benutzer beim kommunizieren mit einem Walkie-Talkie abwechselnd wechseln.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Verhältnis des nicht funktionierenden Mikrofons</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz des Anrufs, bei dem das Aufnahmegerät nicht ordnungsgemäß funktioniert hat. Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme beim Anruf hauptsächlich darauf zurückzuführen sind, dass das Aufnahmegerät nicht erwartungsgemäß funktioniert.</p></td>
</tr>
<tr class="even">
<td><p><strong>Verhältnis des nicht funktionierenden Lautsprechers</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz des Anrufs, bei dem das Render-Gerät nicht ordnungsgemäß funktioniert hat. Ein hoher Wert deutet darauf hin, dass Qualitätsprobleme beim Anruf hauptsächlich darauf zurückzuführen sind, dass das Render-Gerät nicht erwartungsgemäß funktioniert.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufe mit Sprachumschaltung (%)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz der Gesamt Anrufe, die im Halbduplexmodus getätigt werden mussten. Im Halbduplexmodus kann die Kommunikation gleichzeitig nur in eine Richtung erfolgen, ähnlich wie die Benutzer beim kommunizieren mit einem Walkie-Talkie abwechselnd wechseln.</p></td>
</tr>
<tr class="even">
<td><p><strong>Echo Mikrofon in (%)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz der Zeit, als Echo im Mikrofon Erfassungsdaten Strom erkannt wurde. Normalerweise sind die Werte für Headsets oder Mobiltelefone niedrig und für Lautsprecher Telefone oder eigenständige Lautsprecher höher. Bei Geräten, die die akustische Echounterdrückung auf dem Mainboard unterstützen, deuten hohe Werte auf Echo Lecks hin. Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität auszuwerten.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Echo senden (%)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz des Echos, das an andere Benutzer übermittelt wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anrufe mit Echo (%)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz der Gesamt Anrufe, bei denen Echo den zulässigen Wert überschreitet.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

