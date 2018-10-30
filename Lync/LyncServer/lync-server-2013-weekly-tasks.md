---
title: 'Lync Server 2013: Wöchentliche Aufgaben'
TOCTitle: Wöchentliche Aufgaben
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn722432(v=OCS.15)
ms:contentKeyID: 62281955
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Wöchentliche Aufgaben in Lync Server 2013

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Wöchentliche Aufgaben hängen in der Regel mit dem Erfassen und Analysieren von Protokollen und Berichten zusammen.

## Archivieren von Ereignisprotokollen

Wenn Ereignisprotokolle nicht, wie erforderlich, zum Überschreiben von Ereignissen konfiguriert sind, müssen sie regelmäßig archiviert und gelöscht werden. Diese Aktion ist besonders wichtig für Sicherheitsprotokolle, die möglicherweise erforderlich sind, wenn Sie versuchte Sicherheitsverletzungen untersuchen.

Ihre Organisation muss Richtlinien und Verfahren für die Archivierung von Protokollen definieren.

## Erstellen von Berichten

Erstellen Sie Statusberichte, um die Kapazitätsplanung, SLA-Überprüfungen und Leistungsanalyse zu unterstützen. Verwenden Sie tägliche Daten aus dem Ereignisprotokoll und dem Systemmonitor, um Berichte zur Datenträger-, Arbeitsspeicher- und CPU-Auslastung zu erstellen. Verwenden Sie System Center Operations Manager, um Betriebszeit- und Verfügbarkeitsberichte zu generieren.

Ihre Organisation muss Richtlinien und Verfahren für Statusberichte definieren.

## Schadensberichte

Führen Sie eine wöchentliche Überprüfung der Schadensberichte Ihrer Organisation durch, die mit Lync Server zusammenhängen. Diese Überprüfung sollte Folgendes umfassen:

  - Die wichtigsten generierten, gelösten und ausstehenden Vorfälle

  - Lösungen für ungelöste Vorfälle

  - Aktualisieren von Berichten zum Einschließen eines Trouble-Tickets

  - Aktualisieren eines Dokumentrepositorys für Problembehandlungsleitfäden und Abschlussberichte zu Ausfällen

Da das Vorfallverfolgungssystem Ihrer Organisation eine von Lync Server unabhängige Wahl ist, sind keine spezifischen Anweisungen oder Hinweise verfügbar. Entsprechende Informationen finden Sie in der Dokumentation für das System, das Ihre Organisation ausgewählt hat.

## Überprüfen der IIS-Protokolle und -Leistung

Führen Sie eine wöchentliche Überprüfung der Internetinformationsdienste (Internet Information Services, IIS)-Protokolle und -Leistung durch. Weitere Informationen zum Überwachen der IIS-Protokolle und -Leistung finden Sie unter [Übersicht über die Ereignisprotokollierung der Windows Server 2003-Internetinformationsdienste (IIS)](http://go.microsoft.com/fwlink/?linkid=36077). Die Überprüfung sollte Folgendes umfassen:

  - Leistungsindikatoren für den Webdienstcache zum Überwachen des WWW-Dienstcaches

  - Leistungsindikatoren für Active Server Pages (ASPs) zum Überwachen von Anwendungen, die als ASPs ausgeführt werden

Weitere Informationen zum Überwachen der IIS-Protokolle und -Leistung finden Sie unter [Übersicht über die Ereignisprotokollierung der Windows Server 2003-Internetinformationsdienste (IIS)](http://go.microsoft.com/fwlink/?linkid=36077).

## Generieren von Datenbankberichten

**So generieren Sie Berichte der SQL-Datenbank**

1.  Öffnen Sie die Lync Server 2013.

2.  Erweitern Sie in der Konsolenstruktur den Gesamtstrukturknoten, erweitern Sie **Enterprise-Pools** und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.

3.  Klicken Sie im Bereich mit den Details auf die Registerkarte **Datenbank**.

4.  Führen Sie auf der Registerkarte **Datenbank** die folgenden Schritte aus:
    
    1.  Erweitern Sie zum Anzeigen des Namens der Datenbank **Allgemeine Einstellungen** und zeigen Sie den Datenbanknamen an.
    
    2.  Erweitern Sie zum Abrufen der aktuellen Benutzerzusammenfassungsstatistiken für den Pool **Benutzerzusammenfassungsberichte**, klicken Sie auf **Los** und sehen Sie sich die Ergebnisse an.
    
    3.  Erweitern Sie zum Abrufen aktueller benutzerbasierter Daten für einen einzigen Benutzer des Pools **Benutzerbasierte Berichte**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Los** und sehen Sie sich die Ergebnisse an.

Erweitern Sie zum Abrufen der aktuellen Konferenzzusammenfassungsstatistiken für den Pool **Konferenzzusammenfassungsberichte**, klicken Sie auf **Los** und sehen Sie sich die Ergebnisse an.

## Suchen nach Sicherheits- und Lync Server-Updates

Ermitteln Sie, ob neue Service Packs, Hotfixes oder Updates verfügbar sind. Testen Sie diese gegebenenfalls in einem Testlabor und verwenden Sie die Änderungssteuerungsverfahren, um die Bereitstellung an die Produktionsserver vorzubereiten. Außerdem sind jetzt Lync Server-Komponentenupdates als Teil von Windows Update verfügbar. Alle Lync Server-Komponentenupdates müssen gleichzeitig auf Servern mit Lync Server aktualisiert werden, für die Updates gelten.

## Ausführen von Lync Server 2013 Best Practices Analyzer

Lync Server 2013 Best Practices Analyzer ist ein Diagnosetool, das Konfigurationsinformationen sammelt und bestimmt, ob die Konfiguration gemäß den bewährten Methoden von Microsoft festgelegt ist. Die Dokumentation zu diesem Tool finden Sie unter [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md) und [Ausführen von Best Practices Analyzer](https://technet.microsoft.com/de-de/library/gg398652\(v=ocs.15\)).

Das Tool vergleicht die Konfigurationsdaten Ihrer Bereitstellung mit einem Satz vordefinierter Regeln für Lync Server und meldet potenzielle Probleme. Das Tool stellt für jedes gemeldete Problem die aktuelle Konfiguration in der Lync Server-Umgebung sowie die empfohlene Konfiguration bereit.

Mit dem korrekten Netzwerkzugriff kann das Tool Ihre AD DS und Server untersuchen, auf denen Lync Server 2013 ausgeführt wird, um Folgendes durchzuführen:

  - Ausführen proaktiver Integritätsprüfungen, ob die Konfiguration entsprechend der empfohlenen bewährten Methoden eingerichtet ist

  - Generieren einer Liste von Problemen wie suboptimale Konfigurationseinstellungen oder nicht unterstützte bzw. nicht empfohlene Optionen

  - Beurteilen der allgemeinen Integrität eines Systems

  - Unterstützen der Problembehandlung bestimmter Probleme

  - Auffordern zum Herunterladen von Updates, wenn diese verfügbar sind

  - Bereitstellen einer Online- und lokalen Dokumentation zu gemeldeten Problemen, einschließlich Tipps zur Problembehandlung

  - Generieren von Konfigurationsinformationen, die zur späteren Überprüfung erfasst werden können

Stellen Sie sicher, dass RTCBPA.msi auf allen Lync Server 2013-Servern installiert ist und generieren Sie einen wöchentlichen Integritätsprüfungsbericht. Überprüfen Sie die Ergebnisse und korrigieren Sie diese bei Bedarf.

## Überprüfen der SLA-Leistungszahlen

Überprüfen Sie die Daten wichtiger Leistungsaspekte der vorherigen Woche. Prüfen Sie die Leistung im Vergleich zu den SLA-Anforderungen. Ermitteln Sie Trends und Elemente, deren Ziele nicht erreicht wurden.

## Überprüfen von System Center Operations Manager Management Pack- und Quality of Experience-Berichten

Rufen Sie Lync Server 2013 Management Pack- und Quality of Experience-Berichte ab und überprüfen Sie diese.

## Generieren und Überprüfen von Datenbankberichten für Enterprise-Pools

**So generieren Sie Poolberichte**

1.  Öffnen Sie die Lync Server 2013.

2.  Erweitern Sie in der Konsolenstruktur den Gesamtstrukturknoten, erweitern Sie **Enterprise-Pools** und klicken Sie dann auf den Pool, für den Sie einen Datenbankbericht generieren möchten.

3.  Klicken Sie im Bereich mit den Details auf die Registerkarte **Datenbank**.

4.  Führen Sie auf der Registerkarte **Datenbank** die folgenden Schritte aus:
    
    1.  Erweitern Sie zum Anzeigen des Namens der Datenbank **Allgemeine Einstellungen** und zeigen Sie den Datenbanknamen an.
    
    2.  Erweitern Sie zum Abrufen der aktuellen Benutzerzusammenfassungsstatistiken für den Pool **Benutzerzusammenfassungsberichte**, klicken Sie auf **Los** und sehen Sie sich die Ergebnisse an.
    
    3.  Erweitern Sie zum Abrufen aktueller benutzerbasierter Daten für einen einzigen Benutzer des Pools **Benutzerbasierte Berichte**, geben Sie den SIP-URI des Benutzers ein, klicken Sie auf **Los** und sehen Sie sich die Ergebnisse an.

Erweitern Sie zum Abrufen der aktuellen zusammenfassenden Konferenzstatistiken für den Pool **Zusammenfassende Konferenzberichte**, klicken Sie auf **Los** und sehen Sie sich die Ergebnisse an.

Administratoren können für jeden Enterprise-Pool die Registerkarte **Datenbank** verwenden, um den Datenbanknamen anzuzeigen und Berichte aus der Datenbank abzurufen und zu überprüfen.

### Datenberichte und -beschreibungen

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
<td><p>Benutzerzusammenfassungsberichte</p></td>
<td><p>Dbanalyze /v /report:diag [/sqlserver:value]</p>
<p>In diesem Abschnitt werden zusammengefasste Informationen zu den Benutzern in einem Pool angezeigt, beispielsweise die Anzahl aktivierter Benutzer, die durchschnittliche Anzahl von Kontakten pro Benutzer und die Anzahl von Benutzern für bestimmte Features.</p>
<p>Bei der Verwendung dieser Berichte sind möglicherweise die folgenden Informationen hilfreich:</p>
<ul>
<li><p>Ein aktivierter Benutzer ist ein Benutzer, der für Lync Server 2013 über das Snap-In Active Directory-Benutzer und -Computer aktiviert ist.</p></li>
<li><p>Ein aktiver Benutzer ist ein Benutzer, der sich angemeldet oder registriert hat.</p></li>
<li><p>Der Zusammenfassungsbericht enthält auch einen Satz statistischer Informationen zu Kontakten. Diese Statistiken gelten nur für die Benutzer, die sich mindestens einmal angemeldet haben und über mindestens einen Kontakt verfügen. Deshalb wird normalerweise keine Mindestanzahl von Kontakten von 0 angezeigt. Aufgrund dieses Verhaltens wird, wenn ein Benutzer keine Kontakte hat (aber aktiv ist, d. h. sich registriert hat) in einigen Statistikfeldern möglicherweise &lt;empty&gt; angezeigt.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Benutzerbasierte Berichte</p></td>
<td><p>Dbanalyze /v /report:disk [/sqlserver:value]</p>
<p>Im Gegensatz zu den Zusammenfassungsberichten, die für eine Benutzergesamtheit berechnet werden, werden diese Berichte für einen bestimmten Benutzer erstellt.</p></td>
</tr>
<tr class="odd">
<td><p>Zusammenfassende Konferenzberichte</p></td>
<td><p>Dbanalyze /v /report:conf [/sqlserver:value]</p>
<p>In diesem Abschnitt werden zusammengefasste Informationen zu Konferenzstatistiken für den Pool angezeigt, beispielsweise die Anzahl der aktiven Konferenzen und die Gesamtzahl der Teilnehmer.</p></td>
</tr>
<tr class="even">
<td><p>Benutzerzusammenfassungsberichte</p></td>
<td><p>Dbanalyze /v /report:diag [/sqlserver:value]</p>
<p>In diesem Abschnitt werden zusammengefasste Informationen zu den Benutzern in einem Pool angezeigt, beispielsweise die Anzahl aktivierter Benutzer, die durchschnittliche Anzahl von Kontakten pro Benutzer und die Anzahl von Benutzern für bestimmte Features.</p>
<p>Bei der Verwendung dieser Berichte sind möglicherweise die folgenden Informationen hilfreich:</p>
<ul>
<li><p>Ein aktivierter Benutzer ist ein Benutzer, der für Lync Server 2013 über das Snap-In Active Directory-Benutzer und -Computer aktiviert ist.</p></li>
<li><p>Ein aktiver Benutzer ist ein Benutzer, der sich angemeldet oder registriert hat.</p></li>
<li><p>Der Zusammenfassungsbericht enthält auch einen Satz statistischer Informationen zu Kontakten. Diese Statistiken gelten nur für die Benutzer, die sich mindestens einmal angemeldet haben und über mindestens einen Kontakt verfügen. Deshalb wird normalerweise keine Mindestanzahl von Kontakten von 0 angezeigt. Aufgrund dieses Verhaltens wird, wenn ein Benutzer keine Kontakte hat (aber aktiv ist, d. h. sich registriert hat) in einigen Statistikfeldern möglicherweise &lt;empty&gt; angezeigt.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Benutzerbasierte Berichte</p></td>
<td><p>Dbanalyze /v /report:disk [/sqlserver:value]</p>
<p>Im Gegensatz zu den Zusammenfassungsberichten, die für eine Benutzergesamtheit berechnet werden, werden diese Berichte für einen bestimmten Benutzer erstellt.</p></td>
</tr>
<tr class="even">
<td><p>Zusammenfassende Konferenzberichte</p></td>
<td><p>Dbanalyze /v /report:conf [/sqlserver:value]</p>
<p>In diesem Abschnitt werden zusammengefasste Informationen zu Konferenzstatistiken für den Pool angezeigt, beispielsweise die Anzahl der aktiven Konferenzen und die Gesamtzahl der Teilnehmer.</p></td>
</tr>
</tbody>
</table>


## Ausführen der Bandbreitennutzungsanalyse

Die Bandbreitennutzungsanalyse ist ein Tool, das Berichte über verschiedene Ansichten der Bandbreitennutzung durch die UC-Endpunkte über WAN-Verbindungen im Unternehmensnetzwerk erstellt. Mithilfe dieser Berichte kann das aktuelle Bandbreitennutzungsmuster analysiert werden, um die Planung der Bandbreitenkapazität zu unterstützen. Außerdem durchläuft das Tool die Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.

Das Tool bietet folgende Funktionen:

  - Erzeugung spezifischer Berichte für die Audionutzung über das Netzwerk

  - Hilfe bei einer effektiveren Kapazitätsplanung und iterativer Durchlauf der Bandbreitenkapazität, die verschiedenen Verbindungen zugewiesen ist.

Die Bandbreitennutzungsanalyse kann grafische Diagramme aus Bandbreitenkapazitäts- und -nutzungsberichten generieren, nämlich folgende:

  - Alle WAN-Verbindungen im Unternehmensnetzwerk

  - Gefiltert nach ausgewählten WAN-Verbindungen

  - Gefiltert nach WAN-Verbindungen, die die Verbindungskapazität überschritten haben.

  - Gefiltert nach WAN-Verbindungen, die die bereitgestellte Bandbreite unterschritten haben

  - Gefiltert nach WAN-Verbindungen, die kritische Grenzwerte erreicht haben (eine Bandbreitennutzung die größer als 90 % der Bandbreitenkapazität der WAN-Verbindung ist)

  - Gefiltert nach WAN-Verbindungstyp: Netzwerkstandortverbindungen, interregionale Verbindungen und Verbindungen innerhalb eines Standorts

  - Gefiltert nach Netzwerkregion

Die Dokumentation zu diesem Tool finden Sie unter [Lync Server 2013 Resource Kit-Tools – Dokumentation](https://technet.microsoft.com/de-de/library/jj945604\(v=ocs.15\)).

## Siehe auch

#### Weitere Ressourcen

[Wöchentliche Aufgabenprüfliste](lync-server-2013-operations-checklists.md)

