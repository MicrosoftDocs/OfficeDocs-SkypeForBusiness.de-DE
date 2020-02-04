---
title: 'Lync Server 2013: Wöchentliche Aufgaben'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b973d5d69e6e4609a1dff3029b0ad0b05ec3a936
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a>Wöchentliche Aufgaben in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2015-08-17_

Wöchentliche Aufgaben sind im Allgemeinen mit dem sammeln und Analysieren von Protokollen und Berichten verbunden.

<div>

## <a name="archive-event-logs"></a>Archivieren von Ereignisprotokollen

Wenn Ereignisprotokolle nicht so konfiguriert sind, dass Ereignisse nach Bedarf überschrieben werden, müssen Sie regelmäßig archiviert und gelöscht werden. Diese Aktion ist besonders wichtig für Sicherheitsprotokolle, die möglicherweise bei der Untersuchung von Sicherheitsverstößen erforderlich sind.

In Ihrer Organisation müssen Richtlinien und Verfahren für die Protokoll Archivierung definiert werden.

</div>

<div>

## <a name="create-reports"></a>Erstellen von Berichten

Erstellen Sie Statusberichte, die Ihnen bei der Kapazitätsplanung, SLA-Bewertungen und Leistungsanalyse helfen. Verwenden Sie tägliche Daten aus dem Ereignisprotokoll und dem System Monitor, um Berichte auf Datenträger, Arbeitsspeicher und CPU-Auslastung zu erstellen. Verwenden Sie System Center Operations Manager, um Verfügbarkeits-und Verfügbarkeitsberichte zu erstellen.

In Ihrer Organisation müssen Richtlinien und Verfahren für Statusberichte definiert werden.

</div>

<div>

## <a name="incident-reports"></a>Vorfallberichte

Führen Sie eine wöchentliche Überprüfung der vorfallberichte Ihrer Organisation durch, die sich auf lync Server beziehen. Diese Überprüfung sollte Folgendes umfassen:

  - Die am häufigsten generierten, behobenen und ausstehenden Vorfälle.

  - Lösungen für ungelöste Vorfälle.

  - Aktualisieren von Berichten, um neue Trouble-Tickets einzubeziehen.

  - Aktualisieren eines Dokument-Repositorys zur Fehlerbehebung und zur Obduktion über Ausfälle

Da das Vorfall Überwachungssystem Ihrer Organisation eine Wahl ist, die von lync Server unabhängig ist, sind bestimmte Anweisungen oder Zeiger nicht verfügbar. Konsultieren Sie die Dokumentation für das System, das Ihre Organisation ausgewählt hat.

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>Überprüfen von IIS-Protokollen und-Leistung

Führen Sie eine wöchentliche Überprüfung der Internet Informationsdienste (IIS)-Protokolle und-Leistung durch. Weitere Informationen zum Überwachen von IIS-Protokollen und-Leistung finden Sie unter [Übersicht über die Ereignisprotokollierung in Windows Server 2003 (IIS)](http://go.microsoft.com/fwlink/?linkid=36077). Die Überprüfung sollte Folgendes umfassen:

  - Webdienst-Cache-Leistungsindikatoren zum Überwachen des WWW-Dienst Caches.

  - ASP-Leistungsindikatoren (Active Server Pages) zum Überwachen von Anwendungen, die als ASP ausgeführt werden.

</div>

<div>

## <a name="generate-database-reports"></a>Generieren von Datenbankberichten

**So generieren Sie Berichte für die SQL-Datenbank**

1.  Öffnen Sie lync Server 2013.

2.  Erweitern Sie in der Konsolenstruktur den Knoten Gesamtstruktur, erweitern Sie **Enterprise-Pools**, und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.

3.  Klicken Sie im Detailbereich auf die Registerkarte **Datenbank** .

4.  Führen Sie auf der Registerkarte **Datenbank** die folgenden Aktionen aus:
    
    1.  Wenn Sie den Namen der Datenbank anzeigen möchten, erweitern Sie **Allgemeine Einstellungen**, und zeigen Sie den Datenbanknamen an.
    
    2.  Wenn Sie die aktuellen Benutzer Zusammenfassungs Statistiken für den Pool abrufen möchten, erweitern Sie **Benutzer Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.
    
    3.  Wenn Sie aktuelle Daten pro Benutzer für einen einzelnen Benutzer des Pools abrufen möchten, erweitern Sie **Benutzer Berichte**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.

Wenn Sie aktuelle Konferenz Zusammenfassungs Statistiken für den Pool abrufen möchten, erweitern Sie **Konferenz Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>Überprüfen auf Sicherheits-und lync Server-Updates

Identifizieren Sie alle neuen Service Packs, Hotfixes oder Updates. Testen Sie diese gegebenenfalls in einem Testlabor, und verwenden Sie die Änderungskontrollverfahren, um die Bereitstellung auf den Produktionsservern zu arrangieren. Außerdem sind Updates für lync Server-Komponenten jetzt als Teil von Windows Update verfügbar. Alle lync Server-Komponenten Updates müssen gleichzeitig auf allen Servern mit lync Server aktualisiert werden, für die die Updates gelten.

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>Ausführen des lync Server 2013 Best Practice Analyzer

Das lync Server 2013 Best Practices Analyzer-Tool ist ein Diagnosetool, das Konfigurationsinformationen sammelt und bestimmt, ob die Konfiguration gemäß den bewährten Methoden von Microsoft festgelegt ist. Die Dokumentation für dieses Tool finden Sie unter [lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).

Das Tool vergleicht die Konfigurationsdaten Ihrer Bereitstellung mit einer Reihe vordefinierter Regeln für lync Server und meldet potenzielle Probleme. Für jedes gemeldete Problem bietet das Tool die aktuelle Konfiguration in der lync Server-Umgebung und die empfohlene Konfiguration.

Mit dem richtigen Netzwerkzugriff kann das Tool Ihre AD DS und Server untersuchen, auf denen lync Server 2013 ausgeführt wird, um folgende Aktionen auszuführen:

  - Proaktive Durchführung von Integritätsprüfungen und überprüfen, ob die Konfiguration gemäß den empfohlenen bewährten Methoden festzulegen ist

  - Erstellen einer Liste von Problemen, beispielsweise suboptimal-Konfigurationseinstellungen oder nicht unterstützte oder nicht empfohlene Optionen

  - Beurteilen des allgemeinen Zustands eines Systems

  - Hilfe zur Problembehandlung bei bestimmten Problemen

  - Aufforderung zum Herunterladen von Updates, wenn diese verfügbar sind

  - Bereitstellen von Online-und lokalen Dokumentation zu gemeldeten Problemen und einbeziehen von Tipps zur Problembehandlung

  - Generieren von Konfigurationsinformationen, die zur späteren Überprüfung erfasst werden können

Stellen Sie sicher, dass RTCBPA. msi auf allen lync Server 2013-Servern installiert ist, und erstellen Sie einen wöchentlichen Status Prüfbericht. Notieren Sie sich die Ergebnisse, und korrigieren Sie, falls erforderlich.

</div>

<div>

## <a name="review-sla-performance-figures"></a>Überprüfen der SLA-Leistungskennzahlen

Überprüfen Sie die wichtigsten Leistungsdaten für die vorherige Woche. Überprüfen Sie die Leistung mit den Anforderungen der SLA. Erkennen von Trends und Elementen, die ihre Ziele nicht erreicht haben

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>Überprüfen von System Center Operations Manager-Management Pack und Berichte zur Qualität der Erfahrung

Beziehen und überprüfen Sie das lync Server 2013-Management Pack und die Qualität der Erfahrungsberichte.

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>Generieren und Anzeigen von Datenbankberichten für Enterprise-Pools

**So generieren Sie Pool Berichte**

1.  Öffnen Sie lync Server 2013.

2.  Erweitern Sie in der Konsolenstruktur den Knoten Gesamtstruktur, erweitern Sie **Enterprise-Pools**, und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.

3.  Klicken Sie im Detailbereich auf die Registerkarte **Datenbank** .

4.  Führen Sie auf der Registerkarte **Datenbank** die folgenden Aktionen aus:
    
    1.  Wenn Sie den Namen der Datenbank anzeigen möchten, erweitern Sie **Allgemeine Einstellungen**, und zeigen Sie den Datenbanknamen an.
    
    2.  Wenn Sie die aktuellen Benutzer Zusammenfassungs Statistiken für den Pool abrufen möchten, erweitern Sie **Benutzer Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.
    
    3.  Wenn Sie aktuelle Daten pro Benutzer für einen einzelnen Benutzer des Pools abrufen möchten, erweitern Sie **Benutzer Berichte**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.

Wenn Sie aktuelle Konferenz Zusammenfassungs Statistiken für den Pool abrufen möchten, erweitern Sie **Konferenz Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.

Für jeden Enterprise-Pool können Administratoren die Registerkarte **Datenbank** verwenden, um den Datenbanknamen anzuzeigen und Berichte aus der Datenbank abzurufen und anzuzeigen.

### <a name="database-reports-and-descriptions"></a>Datenbankberichte und Beschreibungen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Abschnittsüberschrift</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Benutzer Zusammenfassungsberichte</p></td>
<td><p>Dbanalyze/v/Report: diag [/SQLServer: Wert]</p>
<p>In diesem Abschnitt werden aggregierte Informationen zu Benutzern in einem Pool angezeigt, beispielsweise die Anzahl der aktivierten Benutzer, die durchschnittliche Anzahl der Kontakte pro Benutzer und die Anzahl der Benutzer für bestimmte Features.</p>
<p>Wenn Sie diese Berichte verwenden, können die folgenden Informationen hilfreich sein:</p>
<ul>
<li><p>Ein aktivierter Benutzer ist ein Benutzer, der mit dem Snap-in Active Directory-Benutzer und-Computer für lync Server 2013 aktiviert ist.</p></li>
<li><p>Ein aktiver Benutzer ist ein Benutzer, der sich angemeldet oder registriert hat.</p></li>
<li><p>Die Zusammenfassungsberichte bieten auch eine Reihe von statistischen Informationen zu Kontakten. Diese Statistiken gelten nur für die Bevölkerung von Benutzern, die sich mindestens einmal angemeldet haben und die mindestens einen Kontakt haben. Daher wird normalerweise keine minimale Anzahl von Kontakten von 0 angezeigt. Wenn ein Benutzer über keine Kontakte verfügt (aber aktiv ist, in dem sich der Benutzer registriert hat), wird möglicherweise für einige Statistik &lt;Felder&gt; leer angezeigt:</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Berichte pro Benutzer</p></td>
<td><p>Dbanalyze/v/Report: Datenträger [/SQLServer: Wert]</p>
<p>Im Gegensatz zu den Zusammenfassungsberichten, die über eine Benutzerpopulation berechnet werden, handelt es sich um Berichte über einen bestimmten Benutzer.</p></td>
</tr>
<tr class="odd">
<td><p>Konferenz Zusammenfassungsberichte</p></td>
<td><p>Dbanalyze/v/Report: conf [/SQLServer: Wert]</p>
<p>In diesem Abschnitt werden aggregierte Informationen zu Konferenz Zusammenfassungs Statistiken für den Pool angezeigt, beispielsweise die Anzahl aktiver Konferenzen und die Gesamtzahl der Teilnehmer.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>Ausführen von Bandbreiten Auslastungsanalyse

Bandwidth Utilization Analyzer ist ein Tool, das Berichte über verschiedene Ansichten des Bandbreitenverbrauchs durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Diese Berichte können verwendet werden, um das aktuelle Muster der Bandbreitennutzung zu verstehen und bei der Planung der Bandbreitenkapazität zu helfen. Das Tool durchläuft außerdem die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.

Das Tool bietet folgende Funktionen:

  - Generiert bestimmte Berichte für die audionutzung über das Netzwerk

  - Hilfe bei einer effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist

Der Bandbreiten Auslastungs Analysator kann grafische Plots von Bandbreiten Kapazitäts-und Nutzungsberichten generieren. Sie sind wie folgt:

  - Alle WAN-Verbindungen im Unternehmensnetzwerk

  - Gefiltert nach ausgewählten WAN-Links, die ausgewählt wurden

  - Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben

  - Gefiltert nach WAN-Links, die die bereitgestellte Bandbreite unter Verwenden

  - Filtern nach WAN-Links, die kritische Ebenen erreichen (eine Bandbreitennutzung, die größer als 90 Prozent der Bandbreitenkapazität der WAN-Verbindung ist)

  - Nach WAN-Verknüpfungstyp gefiltert – Netzwerk-Standort-Links, interregionale Links und Links innerhalb einer Website

  - Gefiltert nach Netzwerkregion

Die Dokumentation zu diesem Tool finden Sie in der [Dokumentation zur lync Server 2013 Resource Kit-Tools](http://go.microsoft.com/fwlink/?linkid=623245).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Checkliste für wöchentliche Aufgaben](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

