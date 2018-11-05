---
title: Konfigurieren eines Watcher-Knotens für die Ausführung von synthetischen Transaktionen
TOCTitle: Konfigurieren eines Watcher-Knotens für die Ausführung von synthetischen Transaktionen
ms:assetid: cedda508-8881-4079-88d5-49798f342ddf
ms:mtpsurl: https://technet.microsoft.com/de-de/library/JJ205314(v=OCS.15)
ms:contentKeyID: 49295454
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Konfigurieren eines Watcher-Knotens für die Ausführung von synthetischen Transaktionen

 

_**Letztes Änderungsdatum des Themas:** 2015-03-09_

Nachdem die System Center-Agentdateien installiert wurden, müssen Sie im nächsten Schritt den Watcher-Knoten selbst konfigurieren. Die Schritte zum Konfigurieren eines Watcher-Knotens hängen davon ab, ob sich der Computer mit dem Watcher-Knoten innerhalb oder außerhalb Ihrs Umkreisnetzwerks befindet.

Beim Konfigurieren eines Watcher-Knotens müssen Sie außerdem die Authentifizierungsmethode auswählen, die von diesem Knoten verwendet werden soll. In Lync Server 2013 stehen zwei Authentifizierungsmethoden zur Auswahl: "Vertrauenswürdiger Server" oder "Authentifizierung mit Anmeldeinformationen". Die Unterschiede zwischen diesen beiden Methoden werden in der folgenden Tabelle erläutert:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Konfiguration</th>
<th>Beschreibung</th>
<th>Unterstützte Standorte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Vertrauenswürdiger Server</p></td>
<td><p>Ein Zertifikat wird verwendet, um die Identität eines internen Servers anzunehmen und die Authentifizierungsaufforderungen zu umgehen.</p>
<p>Diese Methode eignet sich für Administratoren, die es vorziehen, ein einzelnes Zertifikat anstelle vieler Benutzerkennwörter auf jedem Watcher-Knoten zu verwalten.</p></td>
<td><p>Innerhalb des Unternehmens.</p>
<p>Beachten Sie, dass sich bei dieser Methode der Watcher-Knoten in derselben Domäne wie die überwachten Pools befinden muss. Falls sich der Watcher-Knoten und die überwachten Pools in unterschiedlichen Domänen befinden, verwenden Sie stattdessen die Authentifizierung mit Anmeldeinformationen.</p></td>
</tr>
<tr class="even">
<td><p>Authentifizierung mit Anmeldeinformationen</p></td>
<td><p>Benutzernamen und Kennwörter werden auf sichere Weise in der Windows-Anmeldeinformationsverwaltung auf jedem Watcher-Knoten gespeichert.</p>
<p>Dieser Modus erfordert einen höheren Kennwortverwaltungsaufwand, ist aber die einzige Option für Watcher-Knoten außerhalb des Unternehmens. Diese Watcher-Knoten können nicht als Endpunkt, der bezüglich der Authentifizierung vertrauenswürdig ist, betrachtet werden.</p></td>
<td><p>Außerhalb des Unternehmens.</p>
<p>Innerhalb des Unternehmens.</p></td>
</tr>
</tbody>
</table>


Sie sollten außerdem überprüfen, ob Ihre Firewall über eingehende Regeln für MonitoringHost.exe und PowerShell.exe verfügt. Wenn diese Prozesse von der Firewall blockiert werden, schlagen Ihre synthetischen Transaktionen mit Fehler 504 (Server-Timeout) fehl.

