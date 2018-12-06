---
title: 'Lync Server 2013: Prüfliste zur Bereitstellung für die Überwachung'
TOCTitle: Prüfliste zur Bereitstellung für die Überwachung
ms:assetid: 4e798370-277c-4391-84b4-13a972b45ca6
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ204874(v=OCS.15)
ms:contentKeyID: 49890743
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prüfliste zur Bereitstellung für die Überwachung in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Auch wenn die Überwachung auf den einzelnen Front-End-Servern bereits installiert und aktiviert wurde, müssen noch einige Schritte ausgeführt werden, bevor tatsächlich Überwachungsdaten für Microsoft Lync Server 2013 erfasst werden können. Diese Schritte werden in der nachstehenden Prüfliste aufgeführt:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Phase</p></td>
<td><p>Schritte</p></td>
<td><p>Rolle und Gruppenmitgliedschaft</p></td>
<td><p>Dokumentation</p></td>
</tr>
<tr class="even">
<td><p><strong>Erforderliche Hardware und Software installieren</strong></p></td>
<td><p>Installieren einer unterstützten Version von Microsoft SQL Server auf dem Computer, der als Back-End-Datenspeicher für die Überwachung fungiert.</p></td>
<td><p>Domänenbenutzer, der auch Mitglied der lokalen Administratorgruppe ist.</p></td>
<td><p><a href="lync-server-2013-supported-hardware.md">Unterstützte Hardware für Lync Server 2013</a> im Unterstützungshandbuch</p>
<p><a href="lync-server-2013-server-software-and-infrastructure-support.md">Serversoftware- und Infrastrukturunterstützung in Lync Server 2013</a> im Unterstützungshandbuch</p></td>
</tr>
<tr class="odd">
<td><p><strong>Erstellen der geeigneten internen Topologie zur Unterstützung der Archivierung</strong></p></td>
<td><p>Fügen Sie der Topologie mit dem Topologie-Generator von Lync Server 2013 Überwachungsdatenbanken hinzu, und veröffentlichen Sie anschließend die aktualisierte Terminologie.</p></td>
<td><p>Definieren einer Topologie, ein Benutzer, der Mitglied der lokalen Benutzergruppe ist.</p>
<p>Veröffentlichen der Topologie, ein Benutzer, der Mitglied der Domänenadministratorgruppe und der RTCUniversalServerAdmins-Gruppe ist.</p></td>
<td><p><a href="lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md">Zuordnen eines Überwachungsspeichers zu einem Front-End-Pool</a> im Bereitstellungshandbuch</p></td>
</tr>
<tr class="even">
<td><p><strong>Aktivieren der entsprechenden Überwachungseinstellungen</strong></p></td>
<td><p>Aktivieren Sie die Aufzeichnung von Kommunikationsdatensätzen und/oder die QoE-Überwachung (Quality of Experience) auf globaler und/oder auf Standortebene.</p></td>
<td><p>Ein Benutzer, der Mitglied der RTCUniversalServerAdmins-Gruppe ist oder dem eine RBAC-Rolle mit Zugriff auf das Cmdlet CsCdrConfiguration und auf das Cmdlet CsQoEConfiguration zugewiesen wurde.</p></td>
<td><p><a href="lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md">Konfigurieren von KDS (Aufzeichnung von Kommunikationsdatensätzen) und QoE-Einstellungen</a> im Betriebshandbuch</p></td>
</tr>
</tbody>
</table>

