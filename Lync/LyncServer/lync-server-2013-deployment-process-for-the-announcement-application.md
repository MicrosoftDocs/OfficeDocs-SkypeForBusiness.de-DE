---
title: 'Lync Server 2013: Bereitstellungsprozess für die Ankündigungsanwendung'
TOCTitle: Bereitstellungsprozess für die Ankündigungsanwendung
ms:assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Gg398545(v=OCS.15)
ms:contentKeyID: 49294382
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Bereitstellungsprozess für die Ankündigungsanwendung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Dieser Abschnitt enthält eine Übersicht über die Schritte zum Bereitstellen der Ansageanwendung. Sie müssen Enterprise-VoIP bereitstellen, bevor Sie Ansagen konfigurieren. Die für die Ansageanwendung erforderlichen Komponenten werden bei der Bereitstellung von Enterprise-VoIP installiert und aktiviert.

### Bereitstellungsprozess für Ansagen

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Schritte</th>
<th>Rollen</th>
<th>Bereitstellungsdokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Konfigurieren von Ansageeinstellungen</p></td>
<td><ul>
<li><p>Erstellen Sie die Ansage durch Aufzeichnen und Hochladen von Audiodateien oder unter Verwendung der Text-zu-Sprache-Funktion (TTS)</p></li>
<li><p>Konfigurieren Sie die Bereiche nicht zugewiesener Nummern in der Tabelle nicht zugewiesener Nummern und ordnen Sie diese Bereiche der geeigneten Ansage zu.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>CsViewOnlyAdministrator</p></td>
<td><p><a href="lync-server-2013-create-an-announcement.md">Erstellen einer Ansage in Lync Server 2013</a></p>
<p><a href="lync-server-2013-configure-the-unassigned-number-table.md">Konfigurieren der Tabelle nicht zugewiesener Nummern in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Überprüfen Ihrer Bereitstellung von Ansagen</p></td>
<td><p>Testen Sie die Wiedergabe von Ansagen, um zu überprüfen, ob Ihre Konfiguration das erwartete Verhalten aufweist.</p></td>
<td><p>-</p></td>
<td><p><a href="lync-server-2013-optional-verify-announcement-deployment.md">(Optional) Überprüfen der Ansagebereitstellung in Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

