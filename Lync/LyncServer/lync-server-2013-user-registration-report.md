---
title: 'Lync Server 2013: Benutzer Registrierungsbericht'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f56ffd05e677d5106552a9ebcf8a0718efbc100
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-registration-report-in-lync-server-2013"></a>Bericht zur Benutzerregistrierung in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2012-10-21_

Der Bericht zur Benutzerregistrierung bietet eine Übersicht über Benutzeranmelde Aktivitäten, insbesondere Informationen zur Anzahl der Benutzer, die sich während eines bestimmten Zeitraums bei Microsoft lync Server 2013 angemeldet haben (stündlich, täglich, wöchentlich, monatlich). Beachten Sie, dass der Bericht nur die Anzahl der angemeldeten Personen enthält. Er enthält keine Informationen dazu, *welche* Personen sich angemeldet haben. Überwachungsberichte liefern keine Informationen darüber, welche bestimmten Benutzer lync Server 2013 verwenden (und welche nicht). Der Bericht über Benutzeraktivität bietet jedoch eine grobe Schätzung in Bezug auf Benutzerinformationen.

Bei der Bereitstellung von Informationen zu Benutzeranmeldungen macht der Bericht über Benutzerregistrierung zwei erhebliche Unterschiede. Zunächst werden die Anmeldungen in zwei Hauptkategorien unterteilt: interne Anmeldungen und externe Anmeldungen. Bei internen Anmeldungen handelt es sich um Benutzer, die sich innerhalb der Firewall Ihres Unternehmens anmelden (d. h. während Sie mit dem Unternehmensnetzwerk verbunden sind). Externe Anmeldungen stellen Benutzer dar, die sich von außerhalb der Firewall über einen Edgeserver angemeldet haben (beispielsweise zählt ein Benutzer, der sich von einem Internet Café anmeldet, als externe Anmeldung). Wenn Sie wissen möchten, wie viele Ihrer Benutzer sich außerhalb der Firewall anmelden, finden Sie diese Information im Bericht über Benutzerregistrierung.

Der Bericht über Benutzerregistrierung enthält zudem Informationen darüber, wie viele *aktive* Benutzer in einem bestimmten Zeitraum anwesend waren. Ein aktiver Benutzer ist ein Benutzer, der an einer Chatsitzung teilgenommen, an einer lync-Besprechung teilgenommen, einen Telefonanruf getätigt oder empfangen oder in diesem Zeitraum anderweitig lync Server verwendet hat. Dadurch unterscheiden sich aktive Benutzer von Benutzern, die sich zwar angemeldet, das System aber nicht genutzt haben.

<div>

## <a name="accessing-the-user-registration-report"></a>Zugreifen auf den Bericht über Benutzerregistrierung

Sie können nur über die Homepage für Überwachungsberichte auf den Bericht über Benutzerregistrierung zugreifen. Der Bericht über Benutzerregistrierung ist nicht mit anderen Berichten verknüpft.

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a>Optimale Nutzung des Berichts über Benutzerregistrierung

Nachdem Sie lync Server bereitgestellt haben, wird häufig eine Frage gestellt: Wie kann ich feststellen, ob meine Benutzer diese neue Technologie tatsächlich verwenden? Der Bericht über Benutzerregistrierung weist in dieser Hinsicht zwar einige Einschränkungen auf, kann Ihnen aber dennoch bei der Beantwortung der Frage helfen. Wenn Sie feststellen möchten, ob Benutzer lync Server verwenden, müssen Sie zwei Schritte ausführen. Rufen Sie zunächst den Wert der Metrik „Eindeutige angemeldete Benutzer“ im Bericht über Benutzerregistrierung ab. Dieser Wert gibt an, wie viele unterschiedliche Personen bei lync Server angemeldet sind.

Im Vergleich dazu zeigt die Metrik Gesamtanzahl der Anmeldungen an, wie viele Gesamtzeiten alle an lync Server angemeldet sind. Angenommen, Ken Myers ist an einem einzigen Tag fünf Mal an lync Server angemeldet. In diesem Fall zählt Jan Sachweh als fünf separate Anmeldesitzungen in der Metrik „Anmeldungen insgesamt“, aber nur als ein angemeldeter Benutzer in der Metrik „Eindeutige angemeldete Benutzer“. Häufig melden sich Benutzer auch auf verschiedenen Geräten oder an verschiedenen Standorten an. Beispielsweise kann sich ein Benutzer mit seinem Desktopcomputer, dem Laptop Computer, anmelden, und er kann ein IP-Telefon haben, das sich automatisch bei lync Server anmeldet. In diesem Beispiel gibt es einen eindeutigen Benutzer mit drei Anmeldungen.

Sehen Sie sich in der folgenden Tabelle mit Anmeldungen in einem bestimmten Zeitraum an, in der der Unterschied zwischen Anmeldungen insgesamt und eindeutigen Anmeldungen näher erklärt ist.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>User</th>
<th>Anmeldezeitpunkt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:45 am</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 8:46 am</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:17 am</p></td>
</tr>
<tr class="even">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 9:22 am</p></td>
</tr>
<tr class="odd">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 9:31 am</p></td>
</tr>
</tbody>
</table>


Insgesamt fanden fünf Anmeldungen statt, es sind jedoch nur zwei eindeutige angemeldete Benutzer vorhanden: Ken Myer (der sich dreimal angemeldet hat) und Pilar Ackerman (die sich zweimal angemeldet hat). Darin besteht der Unterschied zwischen Anmeldungen und eindeutigen angemeldeten Benutzern.

Sie müssen nicht nur die Anzahl der eindeutigen Anmeldungen kennen, sondern auch die Gesamtzahl der Benutzer, die für lync Server aktiviert wurden. Dieser Wert kann abgerufen werden, indem die lync Server 2013-Verwaltungsshell geöffnet und der folgende Windows PowerShell-Befehl ausgeführt wird:

    (Get-CsUser).Count

Wenn der vorhergehende Befehl einen Wert von 1.236 zurückgibt und der Wert der eindeutigen Anmeldebenutzer Metrik einen Mittelwert von 667 zurückgibt, deutet dies darauf hin, dass etwas mehr als die Hälfte der Benutzer für lync aktiviert ist, die sich tatsächlich täglich am System anmelden (d. 667 dividiert durch 1.236 , was etwa 54% beträgt.

<div>


> [!WARNING]  
> Beachten Sie, dass die Metriken die Benutzer aufzeichnen, die sich tatsächlich im angegebenen Zeitraum angemeldet haben. Bereits im System angemeldete Benutzer werden nicht erfasst. Wenn zum Beispiel die Metrik „Eindeutige angemeldete Benutzer“ 667 Anmeldungen anzeigt und insgesamt 1.236 Benutzer vorhanden sind, deutet dies darauf hin, dass sich ca. die Hälfte Ihrer Benutzer im System anmeldet. Nehmen wir jedoch an, 300 Benutzer waren bereits am System angemeldet, als Sie mit der Überprüfung der Anmeldedaten begonnen haben. Das würde bedeuten, dass Sie tatsächlich fast 1.000-Benutzer bei lync Server angemeldet haben, was bedeutet, dass Sie näher an 80% ihrer Benutzer angemeldet waren.



</div>

Vergleichen Sie auch den Wert „Eindeutige angemeldete Benutzer“ mit dem Wert der Metrik „Eindeutige aktive Benutzer“. Die Metrik "eindeutige aktive Benutzer" zeigt an, wie viele eindeutige Benutzer tatsächlich lync Server verwendet haben: Sie haben einen Telefonanruf getätigt, haben sich einer lync-Besprechung angeschlossen, oder Sie haben an einer Chatsitzung teilgenommen. Dies sind nützliche Informationen, da Microsoft lync 2013 so konfiguriert werden kann, dass jedes Mal, wenn ein Benutzer Windows startet, automatisch gestartet wird. Aus diesem Grund haben Sie möglicherweise eine große Anzahl von Benutzern, die sich automatisch bei lync anmelden, wenn Sie sich täglich bei Windows anmelden, in diesem Zeitraum aber niemals lync Server verwenden.

Die Metrik "eindeutige aktive Benutzer" bietet auch aussagekräftigere Daten in einer Organisation, in der Benutzer sich am Ende des Tages in der Regel nicht von Windows abmelden. Stattdessen Sperren Sie einfach Ihre Computer und lassen Windows und lync ausgeführt. In einer solchen Situation erfolgen sehr wenige Anmeldungen pro Tag, da sich die Benutzer vor einigen Tagen angemeldet und seitdem nicht mehr abgemeldet haben. Bei eindeutigen aktiven Benutzern wird jedoch mitgeteilt, ob Benutzer lync oder einen anderen lync Server-Client aktiv verwenden.

</div>

<div>

## <a name="filters"></a>Filter

Mithilfe von Filtern können Sie eine gezieltere Datenauswahl erreichen oder die zurückgegebenen Daten auf unterschiedliche Weise anzeigen. So können Sie beispielsweise mit dem Bericht zur Benutzerregistrierung Daten für alle registrierungspools und-Edgeserver anzeigen oder Daten für einen einzelnen Pool anzeigen. Sie können außerdem festlegen, wie Daten gruppiert werden sollen. In diesem Fall werden die Registrierungen nach Stunde, Tag, Woche oder Monat zusammengefasst.

In der folgenden Tabelle werden die Filter aufgelistet, die Sie im Bericht über Benutzerregistrierung verwenden können.

### <a name="user-registration-report-filters"></a>Filter im Bericht über Benutzerregistrierung

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
<td><p><strong>Intervall</strong></p></td>
<td><p>Zeitintervall. Wählen Sie eine der folgenden Optionen aus:</p>
<ul>
<li><p>Stündlich (maximal 25 Stunden können angezeigt werden)</p></li>
<li><p>Täglich (maximal 31 Tage können angezeigt werden)</p></li>
<li><p>Wöchentlich (maximal 12 Wochen können angezeigt werden)</p></li>
<li><p>Monatlich (maximal 12 Monate können angezeigt werden)</p></li>
</ul>
<p>Wenn mit dem angegebenen Start- und Endzeitpunkt die maximale Anzahl der zulässigen Werte für das ausgewählte Intervall überschritten wird, wird nur die maximale Anzahl an Werten (beginnend mit dem Startzeitpunkt) angezeigt. Wenn Sie beispielsweise das Tagesintervall mit einem Anfangstermin von 7/7/2012 und einem Enddatum von 2/28/2012 auswählen, werden die Daten für die Tage 8/7/2012 12:00 Uhr bis 9/7/2012 12:00 Uhr angezeigt (also insgesamt 31 Tage).</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>Vollqualifizierter Domänenname (FQDN) des Registrierungspools oder Edgeservers. Sie können einen einzelnen Pool oder <strong>[Alle]</strong> auswählen, um die Daten für alle Pools anzuzeigen. Diese Dropdownliste wird basierend auf den Datensätzen in der Datenbank automatisch ausgefüllt.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriken

In der folgenden Tabelle werden die Metriken aufgelistet, die im Bericht über Benutzerregistrierung enthalten sind.

### <a name="user-registration-report-metrics"></a>Metriken im Bericht über Benutzerregistrierung

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
<td><p><strong>Stündlich</strong></p>
<p><strong>Täglich</strong></p>
<p><strong>Wöchentlich</strong></p>
<p><strong>Monatlich</strong></p></td>
<td><p>Nein</p></td>
<td><p>Gibt das auf der Filtersymbolleiste gewählte Zeitintervall an. Sie können gegebenenfalls auf ein bestimmtes Zeitintervall klicken, um ausführliche Informationen zu diesem Intervall anzuzeigen. Wenn Sie beispielsweise das Tagesintervall verwenden und auf 7/7/2012 klicken, wird eine stündliche Aufschlüsselung der Benutzer Registrierungs Aktivität für dieses Datum angezeigt.</p></td>
</tr>
<tr class="even">
<td><p><strong>Anmeldungen insgesamt</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der erfolgreichen Anmeldesitzungen.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interne Anmeldungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anmeldungen im internen Netzwerk.</p></td>
</tr>
<tr class="even">
<td><p><strong>Externe Anmeldungen</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Anmeldungen von außerhalb des internen Netzwerks über den Edgeserver.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Eindeutige angemeldete Benutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Benutzer, die mindestens eine Anmeldesitzung hatten. Ein Benutzer, der mehrere Anmeldesitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Anmeldesitzung ausgeführt hat.</p></td>
</tr>
<tr class="even">
<td><p><strong>Eindeutige aktive Benutzer</strong></p></td>
<td><p>Nein</p></td>
<td><p>Die Gesamtzahl der Benutzer, die an einer Peer-to-Peer- oder Konferenzsitzung teilgenommen haben. Ein Benutzer, der mehrere Sitzungen ausgeführt hat, zählt als ein einziger Benutzer, genauso wie eine Person, die nur eine einzige Sitzung ausgeführt hat.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

