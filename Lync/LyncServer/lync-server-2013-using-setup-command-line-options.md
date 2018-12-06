---
title: Verwenden von Setup-Befehlszeilenoptionen
TOCTitle: Verwenden von Setup-Befehlszeilenoptionen
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205129(v=OCS.15)
ms:contentKeyID: 49294854
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Verwenden von Setup-Befehlszeilenoptionen

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Die Befehlszeile von "Setup.exe" wird nur für wenige Vorgänge des Office-Setups verwendet. Anstelle der Setup-Befehlszeilenoptionen benutzen Sie in der Regel das Office-Anpassungstool und die Datei "Config.xml", um Produkte einzurichten und Funktionen anzupassen.

Die Befehlszeile der Office "Setup.exe" erkennt die in der folgenden Tabelle beschriebenen Befehlzeilenoptionen.

### Optionen der Office Setup-Befehlszeile

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Option der Office Setup-Befehlszeile</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Führt das Office-Anpassungstool aus, um eine Setupanpassungsdatei (.msp-Datei) zu erstellen.</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [Pfad]</p></td>
<td><p>Wendet die angegebene Setupanpassungsdatei auf die Installation an. Sie können einen Pfad zu einer bestimmten Anpassungsdatei (.msp-Datei) oder zu dem Ordner angeben, in dem Sie Anpassungsdateien speichern.</p></td>
</tr>
<tr class="odd">
<td><p>/config [Pfad]</p></td>
<td><p>Gibt die Config.xml-Datei an, die Setup während der Installation verwendet. Benutzen Sie die Option &quot;/config&quot;, um die Config.xml-Datei anzugeben, die Sie für Lync 2013-Installationen angepasst haben. Beispiel: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>Wird mit einer geänderten Config.xml-Datei verwendet, um das Setup im Wartungsmodus auszuführen und Änderungen an einer vorhandenen Office-Installation durchzuführen. Sie können die Option &quot;/modify&quot; z. B. nutzen, um Lync-Funktionen hinzuzufügen oder zu entfernen.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>Führt Setup auf dem Computer des Benutzers aus, um Lync zu reparieren.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>Führt Setup aus, um Lync vom Computer des Benutzers zu entfernen.</p></td>
</tr>
</tbody>
</table>


Ausführliche Informationen zu den Befehlzeilenoptionen finden Sie unter [http://go.microsoft.com/fwlink/?linkid=267515\&clcid=0x407](http://go.microsoft.com/fwlink/?linkid=267515%26clcid=0x407).

