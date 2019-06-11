---
title: 'Lync Server 2013: gerätebericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e172837622c4ad40a29cca74dcaf42497c4b2bd5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34832448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-report-in-lync-server-2013"></a>Gerätebericht in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-11-12_

Der Gerätebericht wäre mit „Mikrofon- und Lautsprecherbericht“ treffender betitelt, denn er ruft anrufbezogene Metriken ab (z. B. Prozentsatz der Anrufe schlechter Qualität, Echo und Sprachumschaltzeit) und gruppiert sie nach den im Anruf verwendeten Mikrofonen und Lautsprechern. Wenn Sie an IP-Telefonen (auch gemeinhin als "Geräte" bezeichnet) interessiert sind, verwenden Sie stattdessen den [Bericht IP Phone Inventory in lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) .

Der Gerätebericht ist für Administratoren von großem Nutzen, wenn herausgefunden werden soll, ob bei einem bestimmten Gerätetyp mehr Anrufe schlechter Qualität auftreten als bei anderen Typen. Das kann wiederum Kaufentscheidungen beeinflussen, wenn neue Geräte angeschafft oder vorhandene ausgetauscht werden müssen.

Standardmäßig beruhen die Werte im Gerätebericht auch auf dem Mikrofon (dem Aufnahmegerät) und den Lautsprechern bzw. dem Kopfhörer (dem Darstellungsgerät), die bei dem Anruf verwendet werden. Angenommen, Sie haben mehrere Benutzer, die das folgende Aufnahme- bzw. Darstellungsgerät verwenden: Standardmäßig basieren die Informationen im Gerätebericht ebenfalls auf dem Mikrofon (Aufnahmegerät) und den Lautsprechern bzw. dem Kopfhörer (Darstellungsgerät), die für den Anruf verwendet wurden. Nehmen Sie beispielsweise an, dass Sie verschiedene Benutzer haben, die das folgende Aufnahmegerät und das folgende Darstellungsgerät verwenden:

  - Aufnahmegerät -- Mikrofon (SoundMAX Integrated Digital HD Audio)

  - Darstellungsgerät -- Headset-Kopfhörer (Microsoft LifeChat LX-3000)

Wenn diese Benutzer insgesamt 254 Anrufe getätigt haben, enthält der Bericht den folgenden Eintrag:


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
<td><p>Mikrofon (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Headset-Kopfhörer (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


Nehmen wir jetzt an, Sie haben eine Reihe von Benutzern, die das gleiche Aufnahmegerät, aber ein anderes Darstellungsgerät verwenden. In diesem Fall enthält der Bericht eine zweite Zeile, und zwar für diese spezielle Kombination aus Aufnahme- und Darstellungsgerät:


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
<td><p>Mikrofon (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Headset-Kopfhörer (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Mikrofon (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Lautsprecher (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


Wenn Sie lieber die Gesamtsumme für ein bestimmtes Gerät angezeigt bekommen möchten (z. B. für das SoundMAX-Aufnahmegerät, unabhängig vom verwendeten Darstellungsgerät), wählen Sie die entsprechende Option in der Dropdownliste „Gerätetyp“ aus (entweder „Aufnahmegerät“ oder „Darstellungsgerät“). Wenn Sie im aktuellen Beispiel „Aufnahmegerät“ wählen, sieht die Ausgabe etwa so aus:


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
<td><p>Mikrofon (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>Öffnen des Geräteberichts

Auf den Gerätebericht greifen Sie über die Startseite für Überwachungsberichte zu. Wenn Sie jedoch den [Anruf Detail Bericht in lync Server 2013](lync-server-2013-call-detail-report.md) anzeigen, können Sie einen Drilldown zum gerätebericht für ein bestimmtes Gerät durchführen, indem Sie auf eine der folgenden Metriken klicken:

  - Aufnahmegerät

  - Darstellungsgerät

Im gerätebericht können Sie einen Drilldown zum [Anruflistenbericht in lync Server 2013](lync-server-2013-call-list-report.md) durchführen, indem Sie auf eine der folgenden Metriken klicken:

  - Anruflautstärke

  - Prozentsatz der Anrufe schlechter Qualität

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>Optimales Nutzen des Geräteberichts

Im Hinblick auf Gerätenamen ist der Gerätebericht besonders detailliert. Beispielsweise könnten die folgenden Aufnahmegeräte vorhanden sein:

  - Aastra 3002-Mikrofon (2- Aastra 3002)

  - Aastra 3002-Mikrofon (3- Aastra 3002)

  - Aastra 3002-Mikrofon (Aastra 3002)

  - Aastra 6725ip

  - Aastra 6725ip-Mikrofon (10- Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (10- Aastra 6725ip)-V0

  - Aastra 6725ip-Mikrofon (2- Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (3- Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (4- Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (5- Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (6- Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (7- Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (9- Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (9- Aastra 6725ip)-V0

  - Aastra 6725ip-Mikrofon (Aastra 6725ip)

  - Aastra 6725ip-Mikrofon (Aastra 6725ip)-V0

  - Aastra 6725ip-Mikrofon (USB-Audiogerät)

  - Aastra 6725ip-Mikrofon (USB-Audiogerät)-V0

<div>


> [!NOTE]  
> Beachten Sie, dass die Namen von Aufnahmegeräten möglicherweise nicht identisch sind, wenn Sie lokalisierte Versionen von lync Server 2013 ausführen. Ein Gerät namens Aastra 6725ip-Mikrofon (Aastra 6725ip)-V0 hat wahrscheinlich auf Französisch oder Spanisch eine andere Bezeichnung.



</div>

Oft benötigen Sie diese Detailebene; zu anderen Zeiten können Sie jedoch nur daran interessiert sein, wie viele Anrufe ein Aastra-Mikrofon verwenden, unabhängig von der Modellnummer. Eine Möglichkeit zum Abrufen von Informationen wie der besteht darin, die Geräte Berichtsdaten nach Microsoft Excel zu exportieren und diese Daten dann in einer Datei mit durch Kommas getrennten Werten (Beispiels\\Weise\\C\_: Data Devices Report. CSV) zu speichern. Sie können dann eine Reihe ähnlicher Befehle verwenden, um das zu importieren. CSV-Datei in Windows PowerShell und Berichterstattung über die Gesamtzahl der Anrufe, die mit einem Aastra-Aufnahmegerät durchgeführt wurden:

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

Damit wird ein einzelner Wert zurückgegeben, der die Gesamtzahl der Anrufe angibt, die mit einem Aastra-Aufnahmegerät ausgeführt wurden. Beispiel:

    384

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Beispielsweise können Sie im Gerätebericht nach dem Anruftyp filtern (d. h., ob der Anruf ein Clientanruf, eine Telefonkonferenz oder ein PSTN-Anruf ist). Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Geräte nach Stunde, Tag, Woche oder Monat gruppiert.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Gerätebericht verwenden können.

### <a name="device-report-filters"></a>Geräteberichtfilter

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
<td><p><strong>Von</strong></p></td>
<td><p>Anfangsdatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Anfangsdatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 Uhr</p>
<p>Wenn Sie keinen Anfangszeitpunkt eingeben, beginnt der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="even">
<td><p><strong>Bis</strong></p></td>
<td><p>Enddatum und -uhrzeit für den Zeitraum. Wenn die Daten nach Stunden angezeigt werden sollen, geben Sie Enddatum und -uhrzeit wie folgt ein:</p>
<p>7/7/2012 1:00 Uhr</p>
<p>Wenn Sie keinen Endzeitpunkt eingeben, endet der Bericht automatisch am angegebenen Tag um 12:00 Uhr. Zum Anzeigen der Daten nach Tag geben Sie nur das Datum ein:</p>
<p>7/7/2012</p>
<p>Sollen die Daten nach Woche oder Monat angezeigt werden, geben Sie irgendein Datum ein, das in die anzuzeigende Woche oder den anzuzeigenden Monat fällt (Sie müssen nicht den ersten Tag der Woche oder des Monats eingeben):</p>
<p>7/3/2012</p>
<p>Eine Woche läuft immer von Sonntag bis einschließlich Samstag.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ursache für die Sprachumschaltung</strong></p></td>
<td><p>Der Grund, weshalb der Halbduplex-Modus für einen Anruf verwendet werden musste, um Echo zu verhindern. Im Halbduplex-Modus ist die Kommunikation jeweils nur in eine Richtung möglich, ähnlich wie bei Funksprechgeräten, bei denen auch abwechselnd gesprochen wird. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Alle]</p>
</dd>
<dt><span></span></dt>
<dd><p>Keine</p>
</dd>
<dt><span></span></dt>
<dd><p>Ungültiger Zeitstempel</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (Dynamic Nonlinear Processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>Geringe Komplexität</p>
</dd>
<dt><span></span></dt>
<dd><p>Ungültiger Gerätestatus</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo nach AEC (Acoustic Echo Cancellation, Echounterdrückung)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Ursache für Echo</strong></p></td>
<td><p>Der Grund, weshalb bei einem Anruf Echo über dem akzeptablen Niveau festgestellt wurde. (In der Telekommunikation handelt es sich bei Echo um eine Schallreflexion; dasselbe Phänomen tritt auf, wenn Sie in einen Brunnen rufen). Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Alle]</p>
</dd>
<dt><span></span></dt>
<dd><p>Keine</p>
</dd>
<dt><span></span></dt>
<dd><p>Ungültiger Zeitstempel</p>
</dd>
<dt><span></span></dt>
<dd><p>Echo nach AEC (Acoustic Echo Cancellation, Echounterdrückung)</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (Adaptive Nonlinear Processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (Dynamic Nonlinear Processor)</p>
</dd>
<dt><span></span></dt>
<dd><p>Mikrofon übersteuert</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Anruftyp</strong></p></td>
<td><p>Gibt an, welcher Typ von Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Alle]</p>
</dd>
<dt><span></span></dt>
<dd><p>Clientanruf</p>
</dd>
<dt><span></span></dt>
<dd><p>PSTN-Anruf</p>
</dd>
<dt><span></span></dt>
<dd><p>Telefonkonferenz</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Zugriffstyp</strong></p></td>
<td><p>Gibt an, ob der Client am internen oder am externen Netzwerk angemeldet wurde, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Alle]</p>
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
<dd><p>[Alle]</p>
</dd>
<dt><span></span></dt>
<dd><p>Verkabelt</p>
</dd>
<dt><span></span></dt>
<dd><p>Funk</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Gibt an, ob ein externer Client eine VPN-Verbindung (Virtual Private Network) verwendete, als der Anruf getätigt wurde. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>[Alle]</p>
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
<td><p>Gibt den Typ des Geräts an. Wählen Sie eine der folgenden Optionen aus:</p>
<dl>
<dt><span></span></dt>
<dd><p>Aufnahmegerät</p>
</dd>
<dt><span></span></dt>
<dd><p>Darstellungsgerät</p>
</dd>
<dt><span></span></dt>
<dd><p>Aufnahme-/Darstellungsgerätepaar</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Gerätename</strong></p></td>
<td><p>Der Name des Aufnahme- oder Darstellungsgeräts. Sie können den vollständigen Gerätenamen oder einen Teil davon eingeben. Geben Sie beispielsweise wie folgt den vollständigen Gerätenamen ein, um nach dem Gerät „Mikrofon (Microsoft LifeCam VX-1000)“ zu suchen:</p>
<p>Mikrofon (Microsoft LifeCam VX-1000)</p>
<p>Sie können aber auch nur einen Teil des Namens eingeben. Beispiel:</p>
<p>LifeCam</p>
<p>Beachten Sie, dass der vorhergehende Filter jedes Gerät zurück &quot;gibt&quot; , das die Zeichenfolge LifeCam an einer beliebigen Stelle im Namen enthält.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Gerätebericht angegeben werden.

### <a name="device-report-metrics"></a>Geräteberichtmetriken

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
<td><p>Ein Gerät (z. B. ein Mikrofon oder eine Webcam), das für die Übertragung von Audio verwendet wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Darstellungsgerät</strong></p></td>
<td><p>Ja</p></td>
<td><p>Ein Gerät (z. B. ein Headset oder Lautsprecher), das für den Empfang von Audio verwendet wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anruflautstärke</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die Gesamtzahl der getätigten Anrufe.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prozentsatz der Anrufe schlechter Qualität</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz der Anrufe, die als &quot;"schlecht" klassifiziert wurden. &quot; Bei einem schlechten Anruf handelt es sich um einen Anruf, bei dem mindestens eine der gemessenen Metriken den zulässigen Wert überschritten hat (beispielsweise ein Anruf, bei dem übermäßiger Jitter zu sehen ist).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Eindeutige Benutzer</strong></p></td>
<td><p>Ja</p></td>
<td><p>Die eindeutigen Benutzer, die das Gerät verwendet haben. Wenn ein Benutzer das Gerät 13 Mal verwendet hat, zählt er als ein eindeutiger Benutzer. Dasselbe gilt für einen Benutzer, der das Gerät nur ein einziges Mal verwendet hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anteil Sprachumschaltzeit</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der Prozentsatz des Anrufs, der im Halbduplex-Modus getätigt werden musste, um Echo zu verhindern. Im Halbduplex-Modus ist die Kommunikation jeweils nur in eine Richtung möglich, ähnlich wie bei Funksprechgeräten, bei denen auch abwechselnd gesprochen wird.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anteil nicht funktionierendes Mikrofon</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der Prozentsatz des Anrufs, bei dem das Aufnahmegerät nicht ordnungsgemäß funktionierte. Ein hoher Wert ist ein Hinweis, dass Qualitätsprobleme beim Anruf in erster Linie darauf zurückzuführen sind, dass das Aufnahmegerät nicht erwartungsgemäß funktionierte.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anteil nicht funktionierender Lautsprecher</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der Prozentsatz des Anrufs, bei dem das Darstellungsgerät nicht ordnungsgemäß funktionierte. Ein hoher Wert ist ein Hinweis, dass Qualitätsprobleme beim Anruf in erster Linie darauf zurückzuführen sind, dass das Darstellungsgerät nicht erwartungsgemäß funktionierte.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Anrufe mit Sprachumschaltung (%)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der Prozentsatz der Gesamtanrufe, die im Halbduplex-Modus getätigt werden mussten. Im Halbduplex-Modus ist die Kommunikation jeweils nur in eine Richtung möglich, ähnlich wie bei Funksprechgeräten, bei denen auch abwechselnd gesprochen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Echo in Mikrofon (%)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Prozentsatz der Zeit, in der im Mikrofonaufnahme-Datenstrom Echo festgestellt wurde. In der Regel weisen Headsets oder Hörer niedrige Werte und Freisprechvorrichtungen oder eigenständige Lautsprecher höhere Werte auf. Bei Geräten, die eine integrierte akustische Echounterdrückung unterstützen, weisen hohe Werte auf eine Echoausbreitung hin. Für andere Geräte sollte diese Metrik nicht verwendet werden, um die Gerätequalität zu evaluieren.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Echo-Übertragung (%)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der Prozentsatz an Echo, das an andere Benutzer übertragen wird.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anrufe mit Echo (%)</strong></p></td>
<td><p>Ja</p></td>
<td><p>Der Prozentsatz der Gesamtanrufe mit Echo über dem akzeptablen Niveau.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

