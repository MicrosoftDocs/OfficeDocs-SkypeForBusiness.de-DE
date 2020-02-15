---
title: 'Lync Server 2013: wöchentliche Aufgaben'
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
ms.openlocfilehash: 87d3f87b37b8c0fe29c4dee76467a9e07931551a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a>Wöchentliche Aufgaben in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2015-08-17_

Wöchentliche Aufgaben beziehen sich im Allgemeinen auf das Sammeln und Analysieren von Protokollen und Berichten.

<div>

## <a name="archive-event-logs"></a>Archiv Ereignisprotokolle

Wenn Ereignisprotokolle nicht so konfiguriert sind, dass Ereignisse nach Bedarf überschrieben werden, müssen Sie regelmäßig archiviert und gelöscht werden. Diese Aktion ist besonders wichtig für Sicherheitsprotokolle, die bei der Untersuchung versuchter Sicherheitsverletzungen möglicherweise erforderlich sind.

In Ihrer Organisation müssen Richtlinien und Verfahren für die Protokoll Archivierung definiert werden.

</div>

<div>

## <a name="create-reports"></a>Erstellen von Berichten

Erstellen von Statusberichten zur Unterstützung bei der Kapazitätsplanung, SLA-Überprüfungen und Leistungsanalyse. Verwenden Sie tägliche Daten aus dem Ereignisprotokoll und dem System Monitor, um Berichte zu Datenträgern, Arbeitsspeicher und CPU-Auslastung zu erstellen. Verwenden Sie System Center Operations Manager zum Generieren von Verfügbarkeits-und Verfügbarkeitsberichten.

In Ihrer Organisation müssen Richtlinien und Verfahren für Statusberichte definiert werden.

</div>

<div>

## <a name="incident-reports"></a>Schadensberichte

Führen Sie eine wöchentliche Überprüfung der vorfallberichte Ihrer Organisation durch, die sich auf lync Server beziehen. Diese Überwachung sollte Folgendes umfassen:

  - Die am häufigsten generierten, aufgelösten und ausstehenden Vorfälle.

  - Lösungen für ungelöste Vorfälle.

  - Aktualisieren von Berichten, um neue Trouble Tickets einzuschließen.

  - Aktualisieren eines Dokument-Repositorys für die Problem Behandlungs Anleitungen und Post mortem über Ausfälle.

Da das Vorfall Verfolgungssystem Ihrer Organisation unabhängig von lync Server ausgewählt werden kann, sind bestimmte Anweisungen oder Zeiger nicht verfügbar. Lesen Sie in der Dokumentation zu dem System, das Ihre Organisation ausgewählt hat.

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>Überprüfen der IIS-Protokolle und-Leistung

Führen Sie eine wöchentliche Überprüfung der Internet Information Services (IIS) Protokolle und der Leistung durch. Weitere Informationen zum Überwachen von IIS-Protokollen und-Leistung finden Sie unter [Windows Server 2003 Internet Information Services (IIS) Ereignisprotokollierung (Übersicht](http://go.microsoft.com/fwlink/?linkid=36077)). Die Überprüfung sollte Folgendes umfassen:

  - Webdienst-Cache Indikatoren zum Überwachen des WWW-Dienst Caches.

  - ASP-Indikatoren (Active Server Pages) zum Überwachen von Anwendungen, die als ASP ausgeführt werden.

</div>

<div>

## <a name="generate-database-reports"></a>Generieren von Datenbankberichten

**So generieren Sie Berichte für die SQL-Datenbank**

1.  Öffnen Sie lync Server 2013.

2.  Erweitern Sie in der Konsolenstruktur den Knoten Gesamtstruktur, erweitern Sie **Enterprise-Pools**, und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.

3.  Klicken Sie im Detailbereich auf die Registerkarte **Datenbank** .

4.  Führen Sie auf der Registerkarte **Datenbank** die folgenden Aktionen aus:
    
    1.  Um den Namen der Datenbank anzuzeigen, erweitern Sie **Allgemeine Einstellungen**, und zeigen Sie den Datenbanknamen an.
    
    2.  Um aktuelle Benutzer Zusammenfassungs Statistiken für den Pool abzurufen, erweitern Sie **Benutzer Zusammenfassungsberichte**, klicken Sie auf **wechseln**, und zeigen Sie die Ergebnisse an.
    
    3.  Zum Abrufen aktueller benutzerbezogener Daten für einen einzelnen Benutzer des Pools erweitern Sie **Berichte pro Benutzer**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.

Um aktuelle Konferenz Zusammenfassungs Statistiken für den Pool abzurufen, erweitern Sie **Konferenz Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>Überprüfen der Sicherheit und lync Server Updates

Identifizieren Sie neue Service Packs, Hotfixes oder Updates. Testen Sie diese gegebenenfalls in einem Test Labor, und ordnen Sie die Bereitstellung auf den Produktionsservern mithilfe der Änderungskontrollverfahren an. Außerdem sind lync Server Komponenten Aktualisierungen jetzt im Rahmen von Windows Update verfügbar. Alle lync Server-Komponenten Updates müssen gleichzeitig auf allen Servern mit lync Server aktualisiert werden, für die die Updates gelten.

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>Ausführen des lync Server 2013 Best Practice Analyzer

Das lync Server 2013 Best Practices Analyzer ist ein Diagnosetool, das Konfigurationsinformationen sammelt und ermittelt, ob die Konfiguration gemäß den bewährten Methoden von Microsoft festgelegt wurde. Dokumentation zu diesem Tool finden Sie unter [lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).

Das Tool vergleicht die Konfigurationsdaten Ihrer Bereitstellung mit einer Reihe vordefinierter Regeln für lync Server und meldet potenzielle Probleme. Für jedes gemeldete Problem stellt das Tool die aktuelle Konfiguration in der lync Server Umgebung und die empfohlene Konfiguration bereit.

Mit dem richtigen Netzwerkzugriff kann das Tool Ihre AD DS und Server untersuchen, auf denen lync Server 2013 ausführen, um folgende Aktionen auszuführen:

  - Proaktives durchführen von Integritätsprüfungen, überprüfen, ob die Konfiguration gemäß den empfohlenen bewährten Methoden festgelegt wurde

  - Erstellen einer Liste von Problemen, beispielsweise suboptimale Konfigurationseinstellungen oder nicht unterstützte oder nicht empfohlene Optionen

  - Beurteilen der allgemeinen Integrität eines Systems

  - Hilfe bei der Behandlung bestimmter Probleme

  - Aufforderung zum Herunterladen von Updates, sofern diese verfügbar sind

  - Bereitstellen von Online-und lokalen Dokumentationen zu gemeldeten Problemen und einschließen von Tipps zur Problembehandlung

  - Generieren von Konfigurationsinformationen, die für eine spätere Überprüfung erfasst werden können

Stellen Sie sicher, dass die RTCBPA. msi auf allen lync Server 2013 Servern installiert ist, und generieren Sie einen wöchentlichen Integritäts Prüfungsbericht. Notieren Sie sich die Ergebnisse und korrigieren Sie, falls erforderlich.

</div>

<div>

## <a name="review-sla-performance-figures"></a>Überprüfen der SLA-Leistungszahlen

Überprüfen Sie die wichtigsten Leistungsdaten für die vorherige Woche. Überprüfen der Leistung anhand der Anforderungen der SLA. Identifizieren von Trends und Elementen, die ihre Ziele nicht erreicht haben.

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>Überprüfen von System Center Operations Manager Management Pack und Quality of Experience-Berichten

Abrufen und überprüfen lync Server 2013 Management Packs und Quality of Experience-Berichte.

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>Generieren und Anzeigen von Datenbankberichten für Enterprise-Pools

**So generieren Sie Pool Berichte**

1.  Öffnen Sie lync Server 2013.

2.  Erweitern Sie in der Konsolenstruktur den Knoten Gesamtstruktur, erweitern Sie **Enterprise-Pools**, und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.

3.  Klicken Sie im Detailbereich auf die Registerkarte **Datenbank** .

4.  Führen Sie auf der Registerkarte **Datenbank** die folgenden Aktionen aus:
    
    1.  Um den Namen der Datenbank anzuzeigen, erweitern Sie **Allgemeine Einstellungen**, und zeigen Sie den Datenbanknamen an.
    
    2.  Um aktuelle Benutzer Zusammenfassungs Statistiken für den Pool abzurufen, erweitern Sie **Benutzer Zusammenfassungsberichte**, klicken Sie auf **wechseln**, und zeigen Sie die Ergebnisse an.
    
    3.  Zum Abrufen aktueller benutzerbezogener Daten für einen einzelnen Benutzer des Pools erweitern Sie **Berichte pro Benutzer**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.

Um aktuelle Konferenz Zusammenfassungs Statistiken für den Pool abzurufen, erweitern Sie **Konferenz Zusammenfassungsberichte**, klicken Sie auf **Gehe**zu, und zeigen Sie die Ergebnisse an.

Für jeden Enterprise-Pool können Administratoren die Registerkarte **Datenbank** verwenden, um den Datenbanknamen anzuzeigen und Berichte aus der Datenbank abzurufen und anzuzeigen.

### <a name="database-reports-and-descriptions"></a>Datenbankberichte und-Beschreibungen

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Abschnitt</th>
<th>Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Benutzer Zusammenfassungsberichte</p></td>
<td><p>Dbanalyze/v/Report: diag [/SQLServer: Wert]</p>
<p>In diesem Abschnitt werden aggregierte Informationen zu Benutzern in einem Pool angezeigt, beispielsweise die Anzahl der aktivierten Benutzer, die durchschnittliche Anzahl der Kontakte pro Benutzer und die Anzahl der Benutzer für bestimmte Features.</p>
<p>Wenn Sie diese Berichte verwenden, sind die folgenden Informationen möglicherweise hilfreich:</p>
<ul>
<li><p>Ein aktivierter Benutzer ist ein Benutzer, der mithilfe des Snap-Ins Active Directory Benutzer und Computer für lync Server 2013 aktiviert ist.</p></li>
<li><p>Ein aktiver Benutzer ist ein Benutzer, der sich angemeldet oder registriert hat.</p></li>
<li><p>Die zusammenfassenden Berichte bieten auch eine Reihe von statistischen Informationen über Kontakte. Diese Statistiken sind nur für die Auffüllung von Benutzern gültig, die sich mindestens einmal angemeldet haben und die mindestens einen Kontakt haben. Folglich wird normalerweise keine Mindestanzahl von Kontakten von 0 angezeigt. Wenn ein Benutzer über keine Kontakte verfügt (aber aktiv ist, in dem der Benutzer registriert ist), wird aufgrund dieses Verhaltens möglicherweise Folgendes &lt;angezeigt&gt; : Empty für einige Statistikfelder.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Berichte pro Benutzer</p></td>
<td><p>Dbanalyze/v/Report: Datenträger [/SQLServer: Wert]</p>
<p>Im Gegensatz zu den Zusammenfassungsberichten, die für eine Benutzer Auffüllung berechnet werden, handelt es sich um Berichte über einen bestimmten Benutzer.</p></td>
</tr>
<tr class="odd">
<td><p>Konferenz Zusammenfassungsberichte</p></td>
<td><p>Dbanalyze/v/Report: conf [/SQLServer: Wert]</p>
<p>In diesem Abschnitt werden aggregierte Informationen zu Konferenz Zusammenfassungs Statistiken für den Pool angezeigt, beispielsweise die Anzahl der aktiven Konferenzen und die Gesamtzahl der Teilnehmer.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>Ausführung des Bandbreiten Auslastungsanalyse Programms

Bandwidth Auslastung Analyzer ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Diese Berichte können verwendet werden, um das aktuelle Muster der Bandbreitennutzung zu verstehen und die Planung der Bandbreitenkapazität zu unterstützen. Außerdem wird die Bandbreitenkapazität durchlaufen, die verschiedenen Links zugewiesen ist.

Dieses Tool führt folgende Schritte aus:

  - Generiert spezifische Berichte für die audionutzung über das Netzwerk.

  - Hilft bei der effektiveren Kapazitätsplanung und Iteration der Bandbreitenkapazität, die verschiedenen Links zugeordnet ist.

Bandbreiten Auslastungsanalyse kann grafische Plots von Bandbreitenkapazität und Nutzungsberichten generieren. Sie sind wie folgt:

  - Alle WAN-Verbindungen im Unternehmensnetzwerk

  - Gefiltert nach ausgewählten WAN-Verbindungen, die ausgewählt wurden

  - Gefiltert nach WAN-Verbindungen, die die Link Kapazität überschritten haben

  - Gefiltert nach WAN-Verbindungen, die die bereitgestellte Bandbreite unter Verwenden

  - Filtern nach WAN-Verbindungen, die kritische Ebenen erreicht haben (Bandbreitenauslastung von mehr als 90% der Bandbreitenkapazität der WAN-Verbindung)

  - Gefiltert nach WAN-Linktyp – Netzwerkstandort Verknüpfungen, interregionale Links und Links innerhalb eines Standorts

  - Gefiltert nach netzwerkregion

Dokumentation zu diesem Tool finden Sie in der [Dokumentation zum lync Server 2013 Resource Kit-Tools](http://go.microsoft.com/fwlink/?linkid=623245).

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Prüfliste für wöchentliche Aufgaben](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

