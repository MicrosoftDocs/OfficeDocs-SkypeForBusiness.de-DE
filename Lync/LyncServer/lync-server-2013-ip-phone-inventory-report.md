---
title: 'Lync Server 2013: Inventurbericht über IP-Telefone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5566f5e38608d2802c8ad699e3599f70c87be4e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Inventurbericht über IP-Telefone in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2012-11-12_

Der Bericht für den IP-Telefonbestand enthält Informationen zu den IP-Telefonen, die derzeit in der Organisation verwendet werden. Er umfasst eine detaillierte Liste der IP-Telefone, die während des angegebenen Berichtszeitraums tatsächlich verwendet wurden. Mithilfe dieses Berichts können Administratoren unter anderem Informationen dazu erhalten, ob alte oder veraltete Telefone vorhanden sind, die ausgetauscht werden sollten. Zudem können Administratoren darauf hingewiesen werden, dass in der Organisation teure Telefone existieren, die kaum verwendet werden. Solche Informationen können außerordentlich wertvoll sein, wenn es darum geht, neue Telefone zu kaufen oder vorhandene Telefone neu zu verteilen. (Ein Benutzer, der sein teures Telefon selten nutzt, kann beispielsweise gebeten werden, sein Telefon mit einem Benutzer zu tauschen, der sein Telefon häufiger verwendet.)

Es sollte darauf hingewiesen werden, dass dieser Bericht einige Einschränkungen hat, wenn es darum geht, als echter Inventarbericht verwendet zu werden. Für eine Sache listet der IP-Telefon Bericht einfach alle Telefone auf, die sich bei lync Server während des angegebenen Zeitraums angemeldet haben, sortiert nach der letzten Anmeldezeit. Wenn sich ein Telefon während des angegebenen Zeitraums nicht angemeldet hat, wird es nicht im Inventurbericht aufgeführt. Dies umfasst Telefone, die vor dem Start des Zeitraums angemeldet waren und noch während des angegebenen Zeitintervalls angemeldet waren. Nehmen wir beispielsweise an, Sie möchten sich den gesamten Telefon bestand für Juli 2012. Nehmen wir an, dass mehrere Telefone, die am 30. Juni lync Server angemeldet sind, am 2012 und noch am 1. Juli angemeldet waren. Diese Telefone werden nicht im Inventurbericht für den 1. Juli angezeigt.

Weiterhin muss beachtet werden, dass der Bestandsbericht Telefone einschließen kann, die in Ihrer Organisation nicht mehr verwendet werden. Angenommen, eine bestimmte Anzahl Telefone von Fabrikam wurde am 1. Juli 2012 beim System angemeldet. Fünf Tage später hat sich Ihre Organisation dazu entschlossen, diese Fabrikam-Telefone durch ein neueres Modell von Contoso auszutauschen. Die Fabrikam-Telefone werden jedoch weiterhin im "Bestandsbericht" aufgeführt, weil sie im Juli beim System angemeldet wurden.

Darüber hinaus werden im Bericht für den IP-Telefonbestand keine zusammenfassenden Gesamtzahlen für die verschiedenen Telefontypen angegeben. Nehmen wir beispielsweise an, Sie besitzen 105 Telefone vom Typ Polycom CX600. Aus dem Bericht wird nicht ersichtlich, dass Sie 105 solcher Telefone haben. Stattdessen sehen Sie lediglich 105 separate Einträge für das Modell Polycom Cx600. Die einzige Möglichkeit, um herauszufinden, dass für das Modell Polycom Cx600 105 Einträge vorliegen, besteht darin, diese Einträge manuell zu zählen.

<div>


> [!WARNING]  
> Alternativ dazu können Sie die Daten exportieren und die Zählung in Microsoft Excel oder Windows PowerShell vornehmen.



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>Zugreifen auf den Bericht für den IP-Telefonbestand

Der Zugriff auf den Bericht für den IP-Telefonbestand erfolgt über die Startseite der Überwachungsberichte. Wenn Sie auf die Metrik "Benutzer-URI" klicken, können Sie auf den Benutzeraktivitätsbericht für den jeweiligen Benutzer zugreifen. Wenn Sie für einen Peer-zu-Peer-Anruf auf die Metrik "Letzte Aktivität" klicken, gelangen Sie zum Detailbericht über Peer-zu-Peer-Sitzungen. Wenn Sie für eine Konferenz auf dieselbe Metrik klicken, gelangen Sie zum detaillierten Konferenzbericht.

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Optimale Nutzung des Berichts für den IP-Telefonbestand

Wenn Sie nur an Verwendungsinformationen für eine bestimmte Art von Telefon interessiert sind (beispielsweise "wie oft verwenden Benutzer ein Polycom CX600-Telefon?"), können Sie diese Informationen direkt aus dem IP-Telefon Inventurbericht abrufen, indem Sie nach dieser bestimmten Art von Telefon filtern. Wenn Sie jedoch zusammenfassende Informationen für alle Telefone wünschen (wie viele Benutzer eine Polycom CX600 verwenden, wie viele eine LG-Nortel-IP8540 verwenden, usw.), müssen Sie die Daten exportieren und eine andere Anwendung (wie Windows PowerShell) für diesen Typ von verwenden. Analyse. Nehmen Sie beispielsweise an, dass Sie die Daten in eine Datei mit Komma getrennten Werten exportieren\\(\\C\_:\_Data\_IP Phone Inventory Report. CSV). In diesem Fall können Sie diese beiden Befehle verwenden, um zusammenfassende Daten für alle Telefone bereitzustellen:

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

Dadurch werden Daten zurückgegeben, die den Folgenden ähneln:

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

Gleichermaßen erhalten Sie mithilfe dieser beiden Befehle Informationen dazu, welche Telefone zwar beim System angemeldet, aber tatsächlich nie zum Telefonieren genutzt wurden (der Wert der Metrik "Letzte Aktivität" ist leer und gibt somit an, dass es keine letzte Aktivität gab):

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

Dabei werden für alle nicht verwendeten Telefone Daten zurückgegeben, die den Folgenden ähneln:

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

Eine weitere interessante Möglichkeit, den Bericht über den IP-Telefon bestand zu verwenden, ist Folgendes: Wenn Sie über die Mac-Adresse eines IP-Telefons verfügen, können Sie den Benutzer, der dieses Telefon zuletzt verwendet hat, einfach über die Adresse in das Textfeld Mac-Adresse eingeben. Der Bericht über den IP-Telefon bestand meldet dann (unter anderem) die SIP-Adresse des Benutzers, der sich zuletzt mit dem Telefon angemeldet hat. Alternativ können Sie eine SIP-Adresse des Benutzers eingeben (im Feld Benutzer-URI-Präfix), um alle Telefone zu ermitteln, die von diesem Benutzer verwendet wurden.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl zurückgeben oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. Der IP-Telefonbestand ermöglicht Ihnen beispielsweise das Anzeigen von Telefonen eines bestimmten Herstellers oder sogar einer bestimmten Version dieser Telefone. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht für den IP-Telefonbestand verwenden können.

### <a name="ip-phone-inventory-report-filters"></a>Bericht für den IP-Telefonbestand – Filter

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
<td><p><strong>Hersteller</strong></p></td>
<td><p>Name des Herstellers des IP-Telefons. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hardwareversion</strong></p></td>
<td><p>Versionsnummer des IP-Telefons; mit den Filtern für den Hersteller und die Hardwareversion können Sie einen bestimmten Telefontyp eindeutig identifizieren. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Benutzer-Agent</strong></p></td>
<td><p>ID für die vom IP-Telefon verwendete Software. Die Werte für diesen Filter werden basierend auf den in der Datenbank vorhandenen IP-Telefonen automatisch ausgefüllt.</p></td>
</tr>
<tr class="even">
<td><p><strong>MAC-Adresse</strong></p></td>
<td><p>Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse (Media Access Control) wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.</p>
<p>Zum Suchen nach Datensätzen mit einer bestimmten MAC-Adresse geben Sie einfach diese Adresse ein, z. B.:</p>
<p>00-08-5D-16-16-48</p>
<p>Die Adresse muss vollständig eingegeben werden. Ein Teil einer Adresse (z. B. 00-08-5D) gibt keine Daten zurück.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Letzte Aktivität vor (Tage)</strong></p></td>
<td><p>Wählen Sie einen der folgenden Werte:</p>
<ul>
<li><p>Alle</p></li>
<li><p>10 </p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Zuletzt abgemeldet vor (Tage)</strong></p></td>
<td><p>Wählen Sie einen der folgenden Werte:</p>
<ul>
<li><p>Alle</p></li>
<li><p>10 </p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Präfix des Benutzer-URI</strong></p></td>
<td><p>SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden Metriken aufgelistet, die im Bericht für den IP-Telefonbestand angegeben werden.

### <a name="ip-phone-inventory-report-metrics"></a>Bericht für den IP-Telefonbestand – Metriken

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
<td><p><strong>Hersteller</strong></p></td>
<td><p>Ja</p></td>
<td><p>Name des Herstellers des IP-Telefons.</p></td>
</tr>
<tr class="even">
<td><p><strong>Hardwareversion</strong></p></td>
<td><p>Ja</p></td>
<td><p>Versionsnummer des IP-Telefons.</p></td>
</tr>
<tr class="odd">
<td><p><strong>MAC-Adresse</strong></p></td>
<td><p>Ja</p></td>
<td><p>Eindeutige ID für die Netzwerkschnittstelle auf dem IP-Telefon. Die MAC-Adresse wird in der Regel bei der Herstellung des Telefons zugewiesen und fest in der Gerätehardware verdrahtet.</p></td>
</tr>
<tr class="even">
<td><p><strong>Benutzer-URI</strong></p></td>
<td><p>Ja</p></td>
<td><p>SIP-Adresse des Benutzers, der das IP-Telefon verwendet hat.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Benutzer-Agent</strong></p></td>
<td><p>Ja</p></td>
<td><p>ID für die vom IP-Telefon verwendete Software.</p></td>
</tr>
<tr class="even">
<td><p><strong>Zuletzt angemeldet um:</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit der letzten Anmeldung des IP-Telefons bei lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Zuletzt abgemeldet um:</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit, zu denen das IP-Telefon zuletzt von lync Server abgemeldet wurde.</p></td>
</tr>
<tr class="even">
<td><p><strong>Letzte Aktivität</strong></p></td>
<td><p>Ja</p></td>
<td><p>Datum und Uhrzeit der letzten Verwendung des IP-Telefons.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

