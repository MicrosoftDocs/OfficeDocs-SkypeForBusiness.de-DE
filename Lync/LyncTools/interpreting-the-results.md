---
title: Interpretieren der Ergebnisse
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0a3dc473765a67db2e09f5a56db14b1ea8a41a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>Interpretieren der Ergebnisse

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2013-02-24_

Das lync Server 2013-Stress-und-Leistungs Tool (LyncPerfTool. exe) bietet zahlreiche Leistungsindikatoren, mit denen Sie verstehen können, was der Client tut und ob Probleme auftreten.

<div>

## <a name="client-counters"></a>Client-Leistungsindikatoren

Jede Instanz von LyncPerfTool. exe, die ausgeführt wird, verfügt über eine separate Instanz der Leistungsindikatoren. Jede Instanz wird durch ihre Prozess-ID benannt.

Wenn die Clients überladen sind, können Probleme auftreten. Gehen Sie wie folgt vor, um diese Probleme zu vermeiden:

1.  Überwachen Sie die CPU und die Speicherauslastung auf den Clientcomputern. Wenn die CPU konstant über 90 Prozent liegt, verringern Sie die Anzahl der Benutzer.

2.  Bei einem hohen Speicherbedarf können Probleme auftreten, wenn die Auslagerungsdatei nicht groß genug ist. Überprüfen Sie, ob die Commit-Belastung auf dem Computer nicht auf das Limit trifft. Wenn Sie Speichergrenzwerte verwenden, können Sie die Größe der Auslagerungsdatei erhöhen oder die Anzahl der Benutzer reduzieren.

In den folgenden Tabellen sind die wichtigsten LyncPerfTool-Leistungsindikatoren aufgeführt.

**Allgemeine Informationen**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>In Minuten verbrachte Zeit</p></td>
<td><p>Die Zeit, die seit dem Start des Prozesses aufgewendet wurde.</p></td>
</tr>
<tr class="even">
<td><p>Aktive Endpunkte</p></td>
<td><p>Die Anzahl der Endpunkte, die derzeit mit dem Server verbunden sind.</p></td>
</tr>
<tr class="odd">
<td><p>Fehlgeschlagene Anmeldungen</p></td>
<td><p>Die Gesamtzahl der Endpunkt Anmeldungsfehler.</p></td>
</tr>
<tr class="even">
<td><p>Anmeldeversuche</p></td>
<td><p>Die Gesamtzahl der Endpunkt Anmeldeversuche.</p></td>
</tr>
<tr class="odd">
<td><p>Endpunkte getrennt</p></td>
<td><p>Die Gesamtzahl der Endpunkte, die getrennt wurden.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Anwesenheitsinformationen**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SetPresence-Anrufe</p></td>
<td><p>Die Gesamtzahl der Anwesenheits Änderungsversuche. Informationen zu unterschiedlichen Arten von Anwesenheitsänderungen finden Sie im Leistungsindikator SetPresence (Presence Type) Calls.</p></td>
</tr>
<tr class="even">
<td><p>NNN-Antworten für SetPresence</p></td>
<td><p>Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence-Anrufe</p></td>
<td><p>Die Gesamtzahl der Versuche, Anwesenheits Anfragen abzurufen.</p></td>
</tr>
<tr class="even">
<td><p>NNN-Antworten für GetPresence</p></td>
<td><p>Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</p></td>
</tr>
</tbody>
</table>


**Informationen zum Adressbuchdienst**

Diese Kategorie enthält Leistungsindikatoren, die zum Überwachen von Dateidownloads für den Adressbuchdienst (ABS) und für Adressbuch-Webabfrage Dienstanforderungen verwendet werden.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vollständige/Delta-Datei Downloads versucht</p></td>
<td><p>Die Gesamtzahl der vollständigen oder Deltadatei Downloadanforderungen wurde versucht.</p></td>
</tr>
<tr class="even">
<td><p>Vollständige/Delta-Datei Downloads erfolgreich</p></td>
<td><p>Die Gesamtzahl der vollständigen oder Deltadatei Downloadanforderungen wurde versucht.</p></td>
</tr>
<tr class="odd">
<td><p>Verwandte Leistungsindikatoren des Adressbuch-Webabfrage Diensts</p></td>
<td><p>Verwandte Leistungsindikatoren für Adressbuchdateien herunterladen.</p></td>
</tr>
<tr class="even">
<td><p>Versuchter ABS WS-Anruf</p></td>
<td><p>Die Gesamtzahl der versuchten Adressbuch-Webabfrage Dienstanforderungen.</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS-Aufrufe erfolgreich</p></td>
<td><p>Die Gesamtzahl der Adressbuch-Webabfrage Dienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</p></td>
</tr>
<tr class="even">
<td><p>ABS WS-Anrufe nicht möglich</p></td>
<td><p>Die Gesamtzahl der Adressbuch-Webabfrage Dienstanforderungen, die einen Fehlerantwort Code zurückgegeben haben.</p></td>
</tr>
</tbody>
</table>


**Informationen zur Verteilerliste (DL)**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Anrufversuche</p></td>
<td><p>Gesamtzahl der versuchten Webdienstanforderungen für die Verteilerlistenerweiterung (dlx).</p></td>
</tr>
<tr class="even">
<td><p>Anrufe erfolgreich</p></td>
<td><p>Die Gesamtzahl der dlx-Webdienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</p></td>
</tr>
<tr class="odd">
<td><p>Anruf fehlgeschlagen</p></td>
<td><p>Die Gesamtzahl der dlx-Webdienstanforderungen, die einen Fehlerantwort Code zurückgegeben haben.</p></td>
</tr>
</tbody>
</table>


**VoIP-Grundinformationen**

Die nachstehend aufgeführten Leistungsindikatoren melden Nummern für alle VoIP-Anrufe (Voice over IP), einschließlich Anrufe an den Vermittlungsserver, A/V-Konferenzserver, den Edgeserver, die Antwortgruppen Anwendung und die automatische Konferenzzentrale, wenn diese Szenarien aktiviert sind.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Aktive Anrufe</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe, die derzeit ausgeführt werden.</p></td>
</tr>
<tr class="even">
<td><p>Anrufe beendet</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe wurde bereits beendet.</p></td>
</tr>
<tr class="odd">
<td><p>Anrufe abgelehnt</p></td>
<td><p>Die Gesamtzahl der eingehenden Sprachanrufe wurde abgelehnt.</p></td>
</tr>
<tr class="even">
<td><p>Ein-und ausgehende Anrufe wurden versucht</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe wurde versucht.</p></td>
</tr>
<tr class="odd">
<td><p>Eingehende/ausgehende Anrufe eingerichtet</p></td>
<td><p>Gesamtzahl der festgelegten eingehenden/ausgehenden Sprachanrufe.</p></td>
</tr>
<tr class="even">
<td><p>Empfangene Anrufe nnn</p></td>
<td><p>Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</p></td>
</tr>
<tr class="odd">
<td><p>VoIP-Durchlauf Rate (%)</p></td>
<td><p>Gesamtzahl der eingestellten Anrufe/Gesamtzahl der Anrufe.</p></td>
</tr>
</tbody>
</table>


**Informationen zum Reaktionsgruppendienst**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Aktive Anrufe</p></td>
<td><p>Die Gesamtzahl aktiver Anrufe an die reaktionsgruppenanwendung.</p></td>
</tr>
<tr class="even">
<td><p>Anrufversuche</p></td>
<td><p>Gesamtzahl der versuchten Anrufe.</p></td>
</tr>
</tbody>
</table>


**Sofortnachrichten (im)-Anrufinformationen**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Aktive Anrufe</p></td>
<td><p>Gesamtzahl der laufenden eingehenden/ausgehenden Sofortnachrichten.</p></td>
</tr>
<tr class="even">
<td><p>Anrufe beendet</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Instant Messaging-Anrufe wurde bereits beendet.</p></td>
</tr>
<tr class="odd">
<td><p>Empfangene Anrufe nnn</p></td>
<td><p>Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</p></td>
</tr>
<tr class="even">
<td><p>Empfangene/Gesendete Chatnachrichten</p></td>
<td><p>Die Gesamtzahl der Nachrichten, die für alle Sitzungen empfangen oder gesendet wurden.</p></td>
</tr>
<tr class="odd">
<td><p>Ein-und ausgehende Anrufe wurden versucht</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe wurde versucht.</p></td>
</tr>
<tr class="even">
<td><p>Eingehende/ausgehende Anrufe eingerichtet</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe wurde eingerichtet.</p></td>
</tr>
</tbody>
</table>


**App-Freigabe-Anrufinformationen**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Aktive Anrufe</p></td>
<td><p>Gesamtzahl der laufenden eingehenden/ausgehenden Anwendungsfreigabe Anrufe.</p></td>
</tr>
<tr class="even">
<td><p>Anrufe beendet</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe wurde bereits beendet.</p></td>
</tr>
<tr class="odd">
<td><p>Empfangene Anrufe nnn</p></td>
<td><p>Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</p></td>
</tr>
<tr class="even">
<td><p>Ein-und ausgehende Anrufe wurden versucht</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Aufrufe wurde versucht.</p></td>
</tr>
<tr class="odd">
<td><p>Eingehende/ausgehende Anrufe eingerichtet</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe wurde eingerichtet.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**CAA-Anrufinformationen**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Aktive Anrufe</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe (Public Switched Telephone Network), die derzeit ausgeführt werden.</p></td>
</tr>
<tr class="even">
<td><p>Anrufe beendet</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe wurde bereits beendet.</p></td>
</tr>
<tr class="odd">
<td><p>Ein-und ausgehende Anrufe wurden versucht</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe wurde versucht.</p></td>
</tr>
<tr class="even">
<td><p>Eingehende/ausgehende Anrufe eingerichtet</p></td>
<td><p>Gesamtzahl der festgelegten eingehenden/ausgehenden PSTN-Anrufe.</p></td>
</tr>
</tbody>
</table>


**Konferenz Informationen**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Aktive Instant Messaging-Konferenzen</p></td>
<td><p>Gesamtzahl der laufenden Instant Messaging-Konferenzen.</p></td>
</tr>
<tr class="even">
<td><p>Aktive Audio/Video Konferenzen</p></td>
<td><p>Gesamtzahl der laufenden Audio/Video-Konferenzen (A/V).</p></td>
</tr>
<tr class="odd">
<td><p>Aktive Anwendungsfreigabe Konferenzen</p></td>
<td><p>Gesamtzahl der laufenden Konferenz zur Anwendungsfreigabe.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der Teilnehmer</p></td>
<td><p>Die Gesamtzahl der Teilnehmer, die derzeit mit Konferenzen verbunden sind.</p></td>
</tr>
<tr class="odd">
<td><p>Konferenzplan Fehler</p></td>
<td><p>Die Gesamtzahl der Fehler bei dem Versuch, eine Konferenz zu planen.</p></td>
</tr>
<tr class="even">
<td><p>Konferenz Fehler teilnehmen</p></td>
<td><p>Die Gesamtzahl der Fehler bei dem Versuch, eine Verbindung mit einer Konferenz herzustellen.</p></td>
</tr>
</tbody>
</table>


**UCWA-Client-Leistungsindikatoren**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Leistungsindikator</strong></th>
<th><strong>Beschreibung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Gesamtzahl der IMMCU-Joins erfolgreich</p></td>
<td><p>Die Gesamtzahl der Teilnahmen an Instant Messaging-Konferenzen.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtzahl der DMCU-Joins erfolgreich</p></td>
<td><p>Die Gesamtzahl der A/V-Konferenzen, die beigetreten sind.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

