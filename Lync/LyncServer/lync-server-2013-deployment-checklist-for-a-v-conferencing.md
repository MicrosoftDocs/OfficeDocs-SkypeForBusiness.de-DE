---
title: Prüfliste zur Bereitstellung für A/V-Konferenzen in Lync Server 2013
TOCTitle: Prüfliste zur Bereitstellung für A/V-Konferenzen in Lync Server 2013
ms:assetid: 6d47426f-6559-407b-9ac1-2453f0b7a2a2
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ619183(v=OCS.15)
ms:contentKeyID: 49294331
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste zur Bereitstellung für A/V-Konferenzen in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Wie bei der Bereitstellung Ihrer anderen Lync Server 2013-Komponenten ist es auch für die Bereitstellung von A/V-Konferenzen erforderlich, dass Sie mit dem Topologie-Generator eine Topologie erstellen und veröffentlichen, die die Konferenzfunktion integriert.

## Bereitstellungsreihenfolge

Sie können die Konferenzfunktion gleichzeitig mit Ihrer anfänglichen Topologie bereitstellen oder nachdem Sie mindestens einen Front-End-Pool oder Standard Edition-Server bereitgestellt haben.

## Bereitstellungsprozess für die Konferenzfunktion

Die folgende Tabelle zeigt eine Übersicht über die für die Bereitstellung der Konferenzfunktion in einer vorhandenen Topologie erforderlichen Schritte.


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
<th>Rollen und Gruppenmitgliedschaften</th>
<th>Dokumentation</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Installieren der vorausgesetzten Hardware und Software</strong></p></td>
<td><p>Konferenzen können auf Front-End-Server auf einem Front-End-Pool und Standard Edition-Server ausgeführt werden. Die Hardware- und Softwarevoraussetzungen für die Installation dieser Server sind ausreichend.</p>
<div>

> [!NOTE]
> Lync Server 2013 verwendet Office Web Apps und den Office Web Apps-Server zum Verarbeiten und Rendern von PowerPoint-Präsentationen. Ausführliche Informationen zur Installation und Konfiguration desOffice Web Apps-Servers erhalten Sie im Abschnitt <A href="lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md">Konfigurieren der Integration mit Office Web Apps Server und Lync Server 2013</A>.


</div></td>
<td><p>Domänenbenutzer, der Mitglied der lokalen Administratorgruppe ist</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für Lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Serversoftware- und Infrastrukturunterstützung in Lync Server 2013</a> in der Unterstützungsdokumentation</p>
<p><a href="lync-server-2013-determining-your-system-requirements.md">Ermitteln Ihrer Systemanforderungen für Lync Server 2013</a> in der Planungsdokumentation.</p>
<p><a href="lync-server-2013-technical-requirements-for-archiving.md">Technische Anforderungen für die Archivierung in Lync Server 2013</a> in der Planungsdokumentation.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung der Konferenzfunktion</strong></p></td>
<td><p>Führen Sie den Topologie-Generator aus, um der Topologie die Konferenzfunktion hinzuzufügen, und veröffentlichen Sie die Topologie anschließend.</p></td>
<td><p>Zum Definieren einer Topologie: Konto, das Mitglied der lokalen Benutzergruppe ist</p>
<p>Zum Veröffentlichen der Topologie: Konto, das Mitglied der Gruppen &quot;Domänen-Admins&quot; und &quot;RTCUniversalServerAdmins&quot; ist und über Vollzugriff (Lesen/Schreiben/Ändern) für die Dateifreigabe verfügt, auf der sich der Lync Server 2013 Dateispeicher befindet (damit der Topologie-Generator die erforderlichen DACLs konfigurieren kann)</p></td>
<td><p><a href="lync-server-2013-define-and-configure-a-topology-in-topology-builder.md">Definieren und Konfigurieren einer Topologie für Lync Server 2013 im Topologie-Generator</a> in der Bereitstellungsdokumentation.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Konfigurieren von Richtlinien und Unterstützung für die Konferenzfunktion</strong></p></td>
<td><p>Verwenden Sie die Systemsteuerung für Lync Server 2013 oder die Lync Server-Verwaltungsshell, um die Einstellungen für die Konferenzfunktion zu konfigurieren.</p></td>
<td><p>Gruppe &quot;RTCUniversalServerAdmins&quot; (nur Windows PowerShell) oder Zuweisung von Benutzern zur Rolle [] oder &quot;CSAdministrator&quot;</p></td>
<td><p><a href="lync-server-2013-conferencing-policies.md">Konferenzrichtlinien in Lync Server 2013</a> in der Betriebsdokumentation.</p></td>
</tr>
</tbody>
</table>


## Siehe auch

#### Weitere Ressourcen

[Übersicht über Konferenzen in Lync Server 2013](lync-server-2013-overview-of-conferencing.md)  
[Definieren der Anforderungen für Konferenzen in Lync Server 2013](lync-server-2013-defining-your-requirements-for-conferencing.md)

