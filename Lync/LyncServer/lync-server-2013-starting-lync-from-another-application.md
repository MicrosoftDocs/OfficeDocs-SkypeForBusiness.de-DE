---
title: Starten von Lync aus einer anderen Anwendung
TOCTitle: Starten von Lync aus einer anderen Anwendung
ms:assetid: 573b30b1-6590-4b24-8e96-a41be57cb0ef
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398376(v=OCS.15)
ms:contentKeyID: 52056337
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Starten von Lync aus einer anderen Anwendung

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Sie können Befehlszeilenparameter für den Schnellstart von Lync 2013 verwenden. Wenn ein Benutzer z. B. in einer anderen Anwendung auf eine Rufnummer klickt, kann die Anwendung eine Instanz von Lync 2013 starten und einen Anruf an die ausgewählte Nummer initiieren.

Lync 2013 kann zudem eine durch Semikolons getrennte Liste mit Kontaktnamen für Konferenzen mit mehreren Teilnehmern erkennen.

Wenn Lync 2013 für die automatische Anmeldung beim Starten der Anwendung konfiguriert ist, wird beim Starten von Lync 2013 über Befehlszeilenparameter das Lync-Hauptfenster geöffnet. Wenn Lync nicht für die automatische Anmeldung beim Starten konfiguriert ist, wird das Anmeldefenster geöffnet.

Die folgende Tabelle zeigt die verfügbaren Parameter.

### Lync 2013-Befehlszeilenparameter

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Erweiterung</th>
<th>Datenformat</th>
<th>Aktion</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>tel:</p></td>
<td><p>Tel-URI</p></td>
<td><p>Öffnet das Fenster &quot;Unterhaltung&quot; für einen Audioanruf, die angegebene Nummer wird jedoch nicht gewählt.</p></td>
</tr>
<tr class="even">
<td><p>callto:</p></td>
<td><p>&quot;tel:&quot;, &quot;sip:&quot; oder Telefon-URI, der eingegeben werden kann</p></td>
<td><p>Öffnet das Fenster &quot;Unterhaltung&quot; für einen Audioanruf, die angegebene Nummer wird jedoch nicht gewählt.</p></td>
</tr>
<tr class="odd">
<td><p>sip:</p></td>
<td><p>SIP-URI</p></td>
<td><p>Öffnet das Fenster &quot;Unterhaltung&quot; mit dem angegebenen SIP-URI (Uniform Resource Identifier) in der Teilnehmerliste.</p></td>
</tr>
<tr class="even">
<td><p>Sips:</p></td>
<td><p>SIP-URI</p></td>
<td><p>Wenn Lync 2013 für die Verwendung des TLS-Protokolls (Transport Layer Security) konfiguriert ist, ist die Funktionsweise mit &quot;sip:&quot; identisch. Wenn TLS nicht verwendet wird, wird der Benutzer in einem Dialogfeld informiert, dass eine höhere Sicherheitsstufe erforderlich ist.</p></td>
</tr>
<tr class="odd">
<td><p>conf:</p></td>
<td><p>SIP-URI der Konferenz, an welcher der Benutzer teilnehmen möchte</p></td>
<td><p>Bei Verwendung des URI-Werts &quot;self&quot; wird das Konferenzzustandsobjekt instanziiert, und es wird ausschließlich die Konferenzliste angezeigt. Andernfalls wird die Listenansicht geöffnet, eine INVITE-Anforderung wird jedoch nicht gesendet.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>im:</p></td>
<td><p>SIP-URI</p></td>
<td><p>Zeigt ein Fenster &quot;Unterhaltung&quot; mit dem SIP-URI an, in dem ausschließlich Sofortnachrichten gesendet werden können. Akzeptiert mehrere SIP-URIs, die in spitzen Klammern (&lt;&gt;) und ohne Trennzeichen angegeben werden.</p>
<pre><code>im:&lt;sip:user1@host&gt;&lt;sip:user2@host&gt;</code></pre></td>
</tr>
</tbody>
</table>


In der folgenden Tabelle sind Beispiele für diese Befehlszeilenparameter aufgeführt.

### Beispiele für Befehlszeilenparameter

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Instanz</th>
<th>Ergebnisse</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tel:+14255550101</p></td>
<td><p>Öffnet eine Nur-Telefon-Ansicht mit +14255550101.</p></td>
</tr>
<tr class="even">
<td><p>Callto:tel:+ 14255550101</p></td>
<td><p>Öffnet eine Nur-Telefon-Ansicht mit +14255550101.</p></td>
</tr>
<tr class="odd">
<td><p>Callto:sip:kazuto@litwareinc.com</p></td>
<td><p>Öffnet eine Nur-Telefon-Ansicht mit kazuto@litwareinc.com.</p></td>
</tr>
<tr class="even">
<td><p>sip:kazuto@litwareinc.com</p></td>
<td><p>Öffnet ein Fenster &quot;Unterhaltung&quot; mit kazuto@litwareinc.com.</p></td>
</tr>
<tr class="odd">
<td><p>conf:sip:https://meet.contoso.com/kazuto/7322994</p></td>
<td><p>Öffnet das Fenster &quot;Unterhaltung&quot; und zeigt Optionen für die Verbindung mit Besprechungsaudiodaten an.</p></td>
</tr>
</tbody>
</table>

