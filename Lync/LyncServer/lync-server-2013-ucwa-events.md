---
title: UCWA-Ereignisse
TOCTitle: UCWA-Ereignisse
ms:assetid: 26cb409d-f4e4-43c7-873f-b694702d491d
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ945621(v=OCS.15)
ms:contentKeyID: 52056315
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# UCWA-Ereignisse

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 verwendet die Unified Communications Web-API (UCWA) für verschiedene Zwecke, vom Zugriff auf Microsoft Exchange für die Suche nach Kontakten bis hin zur Aktualisierung der Anwesenheitsinformationen für Mobilclients.

UCWA zeichnet Einträge zum Betriebsverhalten als die Ereignistypen "Information", "Warnung" und "Fehler" auf. In der folgenden Tabelle sind die Ereignisse beschrieben, die von den UCWA-Komponenten geschrieben werden können.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Ereigniskennung</th>
<th>Ereignistyp</th>
<th>Zusammenfassung</th>
<th>Ursache und Lösung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>20001</p></td>
<td><p>Information</p></td>
<td><p>UCWA initialisiert</p></td>
<td><p>-</p>
<p>-</p></td>
</tr>
<tr class="even">
<td><p>20002</p></td>
<td><p>Fehler</p></td>
<td><p>Unerwartete Ausnahme während der Initialisierung von UCWA</p></td>
<td><p>Während der Initialisierung ist ein unerwarteter Fehler aufgetreten.</p>
<p>Überprüfen Sie die Ausnahmedetails im zugehörigen Ereignisprotokolleintrag, um die mögliche Ursache zu ermitteln.</p></td>
</tr>
<tr class="odd">
<td><p>20003</p></td>
<td><p>Fehler</p></td>
<td><p>In der UCWA ist eine nicht behandelte Ausnahme aufgetreten.</p></td>
<td><p>Eine nicht behandelte Ausnahme ist aufgetreten.</p>
<p>Starten Sie den Server neu. Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</p></td>
</tr>
<tr class="even">
<td><p>20004</p></td>
<td><p>Fehler</p></td>
<td><p>Kein Zugriff auf Exchange zum Abrufen des HD-Fotos</p></td>
<td><p>Keine Verbindung mit Exchange verfügbar</p>
<p>Sicherstellen, dass eine Verbindung mit Exchange verfügbar ist</p></td>
</tr>
<tr class="odd">
<td><p>20005</p></td>
<td><p>Information</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Zugriff auf Exchange zum Abrufen des HD-Fotos ausgeführt</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>20006</p></td>
<td><p>Fehler</p></td>
<td><p>Kein Zugriff auf Exchange zum Suchen von Kontakten</p></td>
<td><p>Keine Verbindung mit Exchange verfügbar</p>
<p>Sicherstellen, dass eine Verbindung mit Exchange verfügbar ist</p></td>
</tr>
<tr class="odd">
<td><p>20007</p></td>
<td><p>Information</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Suchen von Kontakten in Exchange ausgeführt</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>20008</p></td>
<td><p>Warnung</p></td>
<td><p>Versuchen, mehr Anwesenheitsabonemments pro Anwendung als zulässig abzuschließen</p></td>
<td><p>Versuchen, mehr Anwesenheitsabonemments pro Anwendung als zulässig abzuschließen</p>
<p>Clients auf unnötige Abonnements überprüfen</p></td>
</tr>
<tr class="odd">
<td><p>20009</p></td>
<td><p>Warnung</p></td>
<td><p>Versuchen, mehr Anwesenheitsabonemments pro Batch als zulässig abzuschließen</p></td>
<td><p>Versuchen, mehr Anwesenheitsabonemments pro Batch als zulässig abzuschließen</p>
<p>Clients auf unnötige Abonnements überprüfen</p></td>
</tr>
<tr class="even">
<td><p>20010</p></td>
<td><p>Fehler</p></td>
<td><p>In-Band-Daten können nicht abgerufen werden</p></td>
<td><p>In-Band-Daten können nicht abgerufen werden</p>
<p>Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</p></td>
</tr>
<tr class="odd">
<td><p>20011</p></td>
<td><p>Fehler</p></td>
<td><p>Anwesenheit kann nicht abonniert werden</p></td>
<td><p>Anwesenheit kann nicht abonniert werden</p>
<p>Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</p></td>
</tr>
<tr class="even">
<td><p>20012</p></td>
<td><p>Fehler</p></td>
<td><p>Fehler beim Registrieren des Endpunkts</p></td>
<td><p>Fehler beim Registrieren des Endpunkts</p>
<p>Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</p></td>
</tr>
<tr class="odd">
<td><p>20013</p></td>
<td><p>Fehler</p></td>
<td><p>IM MCU ist nicht verfügbar.</p></td>
<td><p>IM MCU ist nicht verfügbar.</p>
<p>Prüfen, ob IM MCU ausgeführt wird.</p></td>
</tr>
<tr class="even">
<td><p>20014</p></td>
<td><p>Information</p></td>
<td><p>Wiederherstellung nach dem Fehler bei der Herstellung der Verbindung mit IM MCU ausgeführt</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>20015</p></td>
<td><p>Fehler</p></td>
<td><p>AV MCU ist nicht verfügbar.</p></td>
<td><p>AV MCU ist nicht verfügbar.</p>
<p>Prüfen, ob AV MCU ausgeführt wird.</p></td>
</tr>
<tr class="even">
<td><p>20016</p></td>
<td><p>Information</p></td>
<td><p>Wiederherstellung nach dem Fehler bei der Herstellung der Verbindung mit AV MCU ausgeführt</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>20017</p></td>
<td><p>Fehler</p></td>
<td><p>AS MCU ist nicht verfügbar.</p></td>
<td><p>AS MCU ist nicht verfügbar.</p>
<p>Prüfen, ob AS MCU ausgeführt wird.</p></td>
</tr>
<tr class="even">
<td><p>20018</p></td>
<td><p>Information</p></td>
<td><p>Wiederherstellung nach dem Fehler bei der Herstellung der Verbindung mit AS MCU ausgeführt</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>20019</p></td>
<td><p>Fehler</p></td>
<td><p>Data MCU ist nicht verfügbar.</p></td>
<td><p>Data MCU ist nicht verfügbar.</p>
<p>Prüfen, ob Data MCU ausgeführt wird.</p></td>
</tr>
<tr class="even">
<td><p>20020</p></td>
<td><p>Information</p></td>
<td><p>Wiederherstellung nach dem Fehler bei der Herstellung der Verbindung mit Date MCU ausgeführt</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>20021</p></td>
<td><p>Fehler</p></td>
<td><p>Teilnahme an IM MCU nicht möglich</p></td>
<td><p>Teilnahme an IM MCU nicht möglich</p>
<p>Prüfen, ob IM MCU ausgeführt wird.</p></td>
</tr>
<tr class="even">
<td><p>20022</p></td>
<td><p>Fehler</p></td>
<td><p>Teilnahme an AV MCU nicht möglich</p></td>
<td><p>Teilnahme an AV MCU nicht möglich</p>
<p>Prüfen, ob AV MCU ausgeführt wird.</p></td>
</tr>
<tr class="odd">
<td><p>20023</p></td>
<td><p>Fehler</p></td>
<td><p>Teilnahme an AS MCU nicht möglich</p></td>
<td><p>Teilnahme an AS MCU nicht möglich</p>
<p>Prüfen, ob AS MCU ausgeführt wird.</p></td>
</tr>
<tr class="even">
<td><p>20024</p></td>
<td><p>Fehler</p></td>
<td><p>Teilnahme an Data MCU nicht möglich</p></td>
<td><p>Teilnahme an Data MCU nicht möglich</p>
<p>Prüfen, ob Data MCU ausgeführt wird.</p></td>
</tr>
<tr class="odd">
<td><p>20025</p></td>
<td><p>Fehler</p></td>
<td><p>Kein Zugriff auf Active Directory zum Abrufen des Fotos</p></td>
<td><p>Die Verbindung mit Active Directory ist nicht verfügbar.</p>
<p>Stellen Sie sicher, dass die Verbindung mit Active Directory verfügbar ist.</p></td>
</tr>
<tr class="even">
<td><p>20026</p></td>
<td><p>Information</p></td>
<td><p>Wiederherstellung nach dem Fehler beim Zugriff auf Active Directory zum Abrufen des Fotos ausgeführt</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>20027</p></td>
<td><p>Warnung</p></td>
<td><p>Deserialisierung nicht möglich</p></td>
<td><p>Deserialisierung nicht möglich</p>
<p>Falls das Problem weiterhin besteht, wenden Sie sich an den Produktsupport.</p></td>
</tr>
</tbody>
</table>

