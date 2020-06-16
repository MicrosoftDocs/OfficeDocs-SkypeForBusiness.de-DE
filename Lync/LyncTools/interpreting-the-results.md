---
title: Interpretieren der Ergebnisse
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Interpreting the Results
ms:assetid: dd7f199f-7075-4d88-bb84-49a7e05eb593
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945608(v=OCS.15)
ms:contentKeyID: 51541433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d02f69f8ea1c8eb7df004e063dba39f03bbe8b7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="interpreting-the-results"></a>Interpretieren der Ergebnisse

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2013-02-24_

Das lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe) verfügt über zahlreiche Leistungsindikatoren, die Sie verwenden können, um zu verstehen, was der Client ausführt und ob Probleme auftreten.

<div>

## <a name="client-counters"></a>Client Indikatoren

Jede Instanz von LyncPerfTool.exe, die ausgeführt wird, verfügt über eine separate Instanz der Leistungsindikatoren. Jede Instanz hat ihren Namen durch die Prozess-ID.

Wenn die Clients überladen sind, können Probleme auftreten. Um diese Probleme zu vermeiden, gehen Sie wie folgt vor:

1.  Überwachen Sie die CPU und die Arbeitsspeicherauslastung auf den Clientcomputern. Wenn die CPU konstant über 90 Prozent liegt, verringern Sie die Anzahl der Benutzer.

2.  Wenn der Speicherplatzbedarf hoch ist, können Probleme auftreten, wenn die Auslagerungsdatei nicht groß genug ist. Stellen Sie sicher, dass die Commit-Gebühr nicht auf den Computer beschränkt ist. Wenn Sie Arbeitsspeichergrenzwerte verwenden, sollten Sie die Größe der Auslagerungsdatei erhöhen oder die Anzahl der Benutzer reduzieren.

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
<td><p>Zeitaufwand seit Beginn des Prozesses.</p></td>
</tr>
<tr class="even">
<td><p>Aktive Endpunkte</p></td>
<td><p>Die Anzahl der Endpunkte, die derzeit mit dem Server verbunden sind.</p></td>
</tr>
<tr class="odd">
<td><p>Fehlgeschlagene Anmeldungen</p></td>
<td><p>Gesamtzahl der Endpunkt Anmeldungsfehler.</p></td>
</tr>
<tr class="even">
<td><p>Anmeldeversuche</p></td>
<td><p>Gesamtzahl der Endpunkt Anmeldeversuche.</p></td>
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
<td><p>SetPresence-Aufrufe</p></td>
<td><p>Die Gesamtzahl der Anwesenheits Änderungsversuche. Informationen zu verschiedenen Arten von Anwesenheitsänderungen finden Sie unter SetPresence (Anwesenheits) Aufrufe Leistungsindikator.</p></td>
</tr>
<tr class="even">
<td><p>NNN-Antworten für SetPresence</p></td>
<td><p>Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</p></td>
</tr>
<tr class="odd">
<td><p>GetPresence-Aufrufe</p></td>
<td><p>Die Gesamtzahl der Versuche zum Abrufen von Anwesenheits Anfragen.</p></td>
</tr>
<tr class="even">
<td><p>NNN-Antworten für GetPresence</p></td>
<td><p>Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</p></td>
</tr>
</tbody>
</table>


**Informationen zum Adressbuchdienst**

Diese Kategorie enthält Leistungsindikatoren, die zum Überwachen von Dateidownloads für den Adressbuchdienst (ABS) und Adressbuch-Webabfragedienst Anforderungen verwendet werden.


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
<td><p>Versuchtes ABS Full/Delta file Downloads</p></td>
<td><p>Die Gesamtzahl der versuchten Downloadanforderungen für vollständige oder Deltadateien.</p></td>
</tr>
<tr class="even">
<td><p>ABS Full/Delta Datei Downloads erfolgreich</p></td>
<td><p>Die Gesamtzahl der versuchten Downloadanforderungen für vollständige oder Deltadateien.</p></td>
</tr>
<tr class="odd">
<td><p>Adressbuch-Webabfragedienst zugehörige Indikatoren</p></td>
<td><p>Adressbuchdatei-Download bezogene Indikatoren.</p></td>
</tr>
<tr class="even">
<td><p>Versuchtes ABS WS-Aufrufe</p></td>
<td><p>Die Gesamtzahl der versuchten Adressbuch-Webabfragedienst Anforderungen.</p></td>
</tr>
<tr class="odd">
<td><p>ABS WS-Aufrufe erfolgreich</p></td>
<td><p>Die Gesamtzahl der Adressbuch-Webabfragedienst Anforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</p></td>
</tr>
<tr class="even">
<td><p>ABS WS-Aufrufe fehlgeschlagen</p></td>
<td><p>Die Gesamtzahl der Adressbuch-Webabfragedienst Anforderungen, die einen Fehlerantwort Code zurückgegeben haben.</p></td>
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
<td><p>Anrufe versucht</p></td>
<td><p>Die Gesamtzahl der versuchten Webdienstanforderungen für die Verteilerlistenerweiterung (dlx).</p></td>
</tr>
<tr class="even">
<td><p>Erfolgreiche Aufrufe</p></td>
<td><p>Die Gesamtzahl der dlx-Webdienstanforderungen, die einen erfolgreichen Antwortcode zurückgegeben haben.</p></td>
</tr>
<tr class="odd">
<td><p>Anrufe sind fehlgeschlagen</p></td>
<td><p>Die Gesamtzahl der dlx-Webdienstanforderungen, die einen Fehlerantwort Code zurückgegeben haben.</p></td>
</tr>
</tbody>
</table>


**VoIP-Basisinformationen**

Die unten aufgeführten Leistungsindikatoren melden Nummern für alle VoIP-Anrufe (Voice over IP), einschließlich Aufrufen von Vermittlungsserver, A/V-Konferenzserver, Edgeserver, Reaktionsgruppenanwendung und der automatischen Telefonzentrale für Konferenzen, wenn diese Szenarien aktiviert sind.


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
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe, die derzeit fortgesetzt werden.</p></td>
</tr>
<tr class="even">
<td><p>Anrufe beendet</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Sprachanrufe, die bereits beendet wurden.</p></td>
</tr>
<tr class="odd">
<td><p>Anrufe abgelehnt</p></td>
<td><p>Die Gesamtzahl der abgelehnten eingehenden Sprachanrufe.</p></td>
</tr>
<tr class="even">
<td><p>Versuchten eingehenden/ausgehenden Anrufe</p></td>
<td><p>Die Gesamtzahl der versuchten eingehenden/ausgehenden Sprachanrufe.</p></td>
</tr>
<tr class="odd">
<td><p>Eingehende/ausgehende Anrufe wurden hergestellt</p></td>
<td><p>Gesamtzahl der eingerichteten eingehenden/ausgehenden Sprachanrufe.</p></td>
</tr>
<tr class="even">
<td><p>Empfangene Anrufe nnn</p></td>
<td><p>Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</p></td>
</tr>
<tr class="odd">
<td><p>VoIP-Durchlauf Rate (%)</p></td>
<td><p>Gesamtzahl der eingestellten Anrufe/Gesamtzahl der Anrufe wurde versucht.</p></td>
</tr>
</tbody>
</table>


**Anrufinformationen für den Reaktionsgruppendienst**


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
<td><p>Die Gesamtzahl der aktiven Anrufe an die Reaktionsgruppenanwendung.</p></td>
</tr>
<tr class="even">
<td><p>Anrufe versucht</p></td>
<td><p>Die Gesamtzahl der versuchten Anrufe.</p></td>
</tr>
</tbody>
</table>


**Anrufinformationen für Chatnachrichten**


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
<td><p>Gesamtzahl der laufenden eingehenden/ausgehenden Sofortnachrichten Anrufe.</p></td>
</tr>
<tr class="even">
<td><p>Anrufe beendet</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe, die bereits beendet wurden.</p></td>
</tr>
<tr class="odd">
<td><p>Empfangene Anrufe nnn</p></td>
<td><p>Die Gesamtzahl der vom Server empfangenen nnn-Antwortcodes.</p></td>
</tr>
<tr class="even">
<td><p>Empfangene/Gesendete Chatnachrichten</p></td>
<td><p>Die Gesamtzahl der empfangenen oder gesendeten Nachrichten für alle Sitzungen.</p></td>
</tr>
<tr class="odd">
<td><p>Versuchten eingehenden/ausgehenden Anrufe</p></td>
<td><p>Die Gesamtzahl der versuchten eingehenden/ausgehenden Sofortnachrichten Anrufe.</p></td>
</tr>
<tr class="even">
<td><p>Eingehende/ausgehende Anrufe wurden hergestellt</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Sofortnachrichten Anrufe, die eingerichtet wurden.</p></td>
</tr>
</tbody>
</table>


**Informationen zum App-Freigabe Anruf**


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
<td><p>Die Gesamtzahl der laufenden eingehenden/ausgehenden Anwendungsfreigabe Anrufe.</p></td>
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
<td><p>Versuchten eingehenden/ausgehenden Anrufe</p></td>
<td><p>Die Gesamtzahl der versuchten eingehenden/ausgehenden Anwendungsfreigabe Anrufe.</p></td>
</tr>
<tr class="odd">
<td><p>Eingehende/ausgehende Anrufe wurden hergestellt</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden Anwendungsfreigabe Anrufe, die eingerichtet wurden.</p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
</tbody>
</table>


**Informationen zu CAA-anrufen**


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
<td><p>Die Gesamtzahl der eingehenden und ausgehenden PSTN-Anrufe (Public Switched Telephone Network), die derzeit fortgesetzt werden.</p></td>
</tr>
<tr class="even">
<td><p>Anrufe beendet</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe, die bereits beendet wurden.</p></td>
</tr>
<tr class="odd">
<td><p>Versuchten eingehenden/ausgehenden Anrufe</p></td>
<td><p>Die Gesamtzahl der versuchten eingehenden/ausgehenden PSTN-Anrufe.</p></td>
</tr>
<tr class="even">
<td><p>Eingehende/ausgehende Anrufe wurden hergestellt</p></td>
<td><p>Die Gesamtzahl der eingehenden/ausgehenden PSTN-Anrufe, die eingerichtet wurden.</p></td>
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
<td><p>Aktive Sofortnachrichtenkonferenzen</p></td>
<td><p>Gesamtzahl der laufenden Sofortnachrichtenkonferenzen.</p></td>
</tr>
<tr class="even">
<td><p>Aktive Audio/Video Konferenzen</p></td>
<td><p>Gesamtzahl der laufenden Audio/Video-Konferenzen (A/V).</p></td>
</tr>
<tr class="odd">
<td><p>Aktive Anwendungsfreigabe Konferenzen</p></td>
<td><p>Die Gesamtzahl der laufenden Konferenzen für die Anwendungsfreigabe.</p></td>
</tr>
<tr class="even">
<td><p>Anzahl der Teilnehmer</p></td>
<td><p>Die Gesamtzahl der Teilnehmer, die derzeit mit Konferenzen verbunden sind.</p></td>
</tr>
<tr class="odd">
<td><p>Ausfall des Konferenz Zeitplans</p></td>
<td><p>Die Gesamtzahl der Fehler beim Planen einer Konferenz.</p></td>
</tr>
<tr class="even">
<td><p>Konferenz Fehler beitreten</p></td>
<td><p>Die Gesamtzahl der Fehler beim Versuch, eine Verbindung mit einer Konferenz herzustellen.</p></td>
</tr>
</tbody>
</table>


**UCWA-Client Indikatoren**


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
<td><p>Gesamtanzahl der erfolgreichen IMMCU-Joins</p></td>
<td><p>Die Gesamtzahl der beigetretenen Sofortnachrichtenkonferenzen.</p></td>
</tr>
<tr class="even">
<td><p>Gesamtanzahl der erfolgreichen DMCU-Joins</p></td>
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

