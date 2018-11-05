---
title: 'Lync Server 2013: PSTN-Verwendungsdatensätze'
TOCTitle: PSTN-Verwendungsdatensätze
ms:assetid: b5f624aa-abe8-455b-a8e3-c228be230463
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg412878(v=OCS.15)
ms:contentKeyID: 49295161
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# PSTN-Verwendungsdatensätze in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Die Planung von PSTN-Verwendungsdatensätzen besteht hauptsächlich darin, alle Anrufberechtigungen aufzulisten, die aktuell in Ihrer Organisation vorhanden sind, vom Firmenchef bis hin zu Personen mit befristeten Arbeitsverträgen, Beratern und Zeitarbeitern. Dieses Verfahren bietet außerdem die Gelegenheit, vorhandene Berechtigungen neu zu überprüfen und sie zu überarbeiten. Sie können PSTN-Verwendungsdatensätze ausschließlich für Berechtigungen erstellen, die sich auf Ihre vorgesehenen Enterprise-VoIP-Benutzer beziehen. Langfristig besteht eine bessere Lösung möglicherweise darin, PSTN-Verwendungsdatensätze einfach für alle Berechtigungen zu erstellen, und zwar unabhängig davon, ob einige davon derzeit nicht für die Gruppe der Benutzer gelten, für die Enterprise-VoIP aktiviert werden soll. Wenn Anrufberechtigungen geändert oder neue Benutzer mit abweichenden Abrufberechtigungen hinzugefügt werden, haben Sie die erforderlichen PSTN-Verwendungsdatensätze bereits erstellt.

Die folgende Tabelle stellt eine typische PSTN-Verwendungstabelle dar.

### PSTN-Verwendungsdatensätze

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Telefonattribut</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Local</p></td>
<td><p>Ortsgespräche</p></td>
</tr>
<tr class="even">
<td><p>Long-Distance</p></td>
<td><p>Ferngespräche</p></td>
</tr>
<tr class="odd">
<td><p>International</p></td>
<td><p>Auslandsgespräche</p></td>
</tr>
<tr class="even">
<td><p>Delhi</p></td>
<td><p>Vollzeitmitarbeiter in Delhi</p></td>
</tr>
<tr class="odd">
<td><p>Redmond</p></td>
<td><p>Vollzeitmitarbeiter in Redmond</p></td>
</tr>
<tr class="even">
<td><p>RedmondTemps</p></td>
<td><p>Zeitarbeiter in Redmond</p></td>
</tr>
<tr class="odd">
<td><p>Zurich</p></td>
<td><p>Vollzeitmitarbeiter in Zürich</p></td>
</tr>
</tbody>
</table>


PSTN-Verwendungsdatensätze alleine führen keine Aktionen aus. Um sie verwenden zu können, müssen Sie sie mit Folgendem verknüpfen:

  - VoIP-Richtlinien, die Benutzern zugewiesen sind

  - Routen, die Rufnummern zugewiesen sind

Genauere Informationen zu VoIP-Richtlinien und -Routen finden Sie unter [VoIP-Richtlinien in Lync Server 2013](lync-server-2013-voice-policies.md) und [VoIP-Routen in Lync Server 2013](lync-server-2013-voice-routes.md). Genauere Informationen zum Erstellen und Konfigurieren von VoIP-Richtlinien und -Routen finden Sie unter [Konfigurieren von VoIP-Routen für ausgehende Anrufe in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).

