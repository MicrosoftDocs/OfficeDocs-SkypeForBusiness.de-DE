---
title: Lync Call Quality Methodology
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/de-de/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084825
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Call Quality Methodology

 

_**Letztes Änderungsdatum des Themas:** 2016-12-08_

Dieser Artikel begleitet das Poster [Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841), das Sie aus dem Download Center herunterladen können.

![Poster mit Beschreibung des CQM-Prozesses](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster mit Beschreibung des CQM-Prozesses")

Auf diesem Poster erfahren Sie mehr über CQM, der Call Quality Methodology für Lync 2013 und 2010, mit der Sie Probleme finden und beheben können, die sich auf die Anrufqualität und die Benutzerfreundlichkeit für Lync-Implementierungen auswirken, die Enterprise-VoIP-Funktionen enthalten. Call Quality Methodology ist ein neues Fehlerbehandlungs- und Dienstverwaltungsframework, mit dem Sie Ihre Bemühungen zur Verbesserung von Enterprise-VoIP-Diensten in Lync besser fokussieren können. In diesem Artikel erfahren Sie mehr über CQM, die Arten der überwachten Server und Lösungen und was Sie mit den gesammelten Telemetriedaten tun können.

Fragen zur Verwendung von CQM können Sie an cqmfeedback@microsoft.com senden.

Auf dem Poster werden die folgenden Bereiche erklärt:

  - Was ist Lync CQM?

  - Priorisierung: Ausführen von Trendabfragen

  - PCD

  - Verwaltet/Nicht verwaltet

  - Die Straße der Servereinrichtung

  - Die Straße der letzten Meile

  - Die Straße der Endpunkte

  - Dienstverwaltung

  - Spielregeln

## Was ist Lync CQM?

Call Quality Methodology ist ein neues Fehlerbehandlungs- und Dienstverwaltungsframework, mit dem Sie Ihre Bemühungen zur Verbesserung von Enterprise-VoIP-Diensten in Lync besser fokussieren können. Wenn Sie CQM verwenden, können Sie die Anrufqualität und Benutzerzufriedenheit für Enterprise-VoIP-Anrufe einfacher sicherstellen. CQM wird ausführlicher im [Lync Server-Netzwerkhandbuch](http://go.microsoft.com/fwlink/p/?linkid=390677) beschrieben. In diesem Artikel und auf dem Poster werden diese Inhalte zusammengefasst.

CQM teilt die Systemfehlerbehandlung in die folgenden drei Wege oder “Straßen” auf: die Straße der Servereinrichtung, bei der die Server und die dazwischen bestehenden Verbindungen angesehen werden, die Straße der Endpunkte, bei der Benutzergeräte und Medien für die Übertragung von Anrufen betrachtet werden, und die Straße der letzten Meile, bei der die Integration herkömmlicher PSTN-Anrufe behandelt wird.

Jede Straße ist je nach bestimmtem Bereich oder Thema in mehrere Segmente aufgeteilt. In jedem Segment wird definiert, was ein akzeptabler Qualitätslevel ist und mit welchen Aktionen dieser Qualitätslevel erreicht werden kann. Zudem wird ein Dienstverwaltungsplan festgelegt, um diesen Qualitätslevel aufrechtzuerhalten, bevor zum nächsten Thema übergegangen wird.

Auf dem Poster ist Lync CQM als Brettspiel für drei Spieler dargestellt, die jeweils eine der Straßen nehmen. Im Download enthaltene Karten werden verwendet, um Hindernisse für die Anrufqualität darzustellen, die überwunden werden müssen. Hinweise und Vorschläge zu Zielen und wie diese erreicht werden können, sind in allen drei Straßen vorhanden, ebenso Richtlinien zur Priosierung, welche Straße in tatsächlichen Anwendungen zuerst verfolgt werden sollte (im Spiel werden alle drei Straßen parallel genommen).

Wie funktioniert CQM in früheren Versionen von Lync? CQM ist neu in Lync 2013, aber der größte Teil kann auch für die Verwendung mit Lync 2010 angepasst werden. CQM funktioniert möglicherweise zu einem gewissen Grad mit Microsoft Office Communicator, aber dies ist nicht getestet und es gibt keinen Support dafür.

Fragen zur Verwendung von CQM können Sie an cqmfeedback@microsoft.com senden.

## Priorisierung: Ausführen von Trendabfragen

Der erste Schritt von CQM besteht darin, zwei Wochen lang jede der Trendabfragen auszuführen und die Ergebnisse zu analysieren. Priorisieren Sie korrigierende Aktionen nach dem größten Datenstrombeitrager, dem höchsten Datenstromverhältnis und den verwalteten Bereichen (die Sie kontrollieren). Wenn die Audio/Video Multipoint Control Unit (AV MCU) oder Vermittlungsabfragen schlechte Ergebnisse zeigen, beginnen Sie auf der roten Straße (Servereinrichtung). Wenn die Verkabelungs- oder Drahtlosabfragen schlechte Ergebnisse zeigen, beginnen Sie auf der blauen Straße (letzte Meile). Wenn die VPN- oder externen Abfragen schlechte Ergebnisse zeigen, beginnen Sie auf der grünen Straße (Endpunkte).

Nachdem Sie sich für eine Straße entschieden haben, mit der Sie beginnen möchten, definieren Sie ein Ziel für jeden Bereich (Bestätigen), arbeiten Sie daran, das Ziel zu erreichen (Erreichen), und implementieren Sie dann Verfahren, um den Kurs zu halten (Warten). Sie können dieses Poster auch als Spiel verwenden, um die Prinzipien hinter CQM zu verstehen.

## PCD

Das PreCall-Diagnosetool (PCD) hilft Ihnen, Probleme in Ihrem Umkreisnetzwerk zu erkennen und zu diagnostizieren (die QoE-Datenbank sammelt keine Informationen in Ihrem Edge- oder Umkreisnetzwerk) sowie Probleme mit der Verbindung in der letzten Meile zu beheben. Das Tool steht sowohl als Windows 8 Modern-App als auch als Windows Desktop-App unter http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88 zur Verfügung.

## Verwaltet/Nicht verwaltet

Die Lync Server-Bereitstellung und -Infrastruktur kann normalerweise in verwaltete und nicht verwaltete Bereiche aufgeteilt werden. Der verwaltete Bereich beinhaltet Ihre gesamte interne verkabelte Netzwerk- und Serverinfrastruktur. Der nicht verwaltete Bereich ist die Drahtlosinfrastruktur und die externe Netzwerkinfrastruktur.

Wenn Sie diese Unterscheidung machen, werden Ihre Daten klarer. Es hilft Ihrem Unternehmen zudem, sich auf Arbeitsauslastungen zu konzentrieren, die eine messbare Wirkung auf die Sprach- und Videoqualität für Ihre Benutzer haben. Benutzer haben unterschiedliche Erwartungen an die Qualität, wenn der Anruf in einer Infrastruktur erfolgt, die Sie besitzen (verwaltet), oder in einer Infrastruktur, die teilweise von einer anderen Entität kontrolliert wird (nicht verwaltet). Das bedeutet nicht, dass Drahtlosbenutzer mit ihren eigenen Geräten allein dastehen, um hervorragende Lync Server-Erfahrungen zu machen.

Für eine Verbesserung der Sprachqualität im nicht verwalteten Bereich benötigen Sie eine hohe Qualität im verwalteten Bereich. Ob der Drahtlosbereich (WLAN) als verwalteter oder nicht verwalteter Bereich betrachtet wird, hängt von Ihrem Unternehmen ab. Die Techniken zum Erzielen einer fehlerfreien Umgebung sind in beiden Bereichen unterschiedlich, ebenso die Lösungen.

## Die Straße der Servereinrichtung

Segment 1 der Straße der Servereinrichtung zielt auf die tatsächlichen Server in der Lync-Implementierung ab. Sammeln Sie KHI-Daten zum Server selbst und zu seiner Rolle in der Implementierung und analysieren Sie die Ergebnisse. Wenn eine Aktion notweding ist, korrigieren Sie die gefundenen Probleme. Ausführlichere Informationen zu diesem Thema finden Sie in dem Artikel zu [Key Health Indicators](lync-server-2013-poster-key-health-indicators.md), der das KHI-Poster begleitet.

Das nächste Segment betrifft den Mediendatenstrom zwischen dem AV MCU-Server und dem Vermittlungsserver. Bestimmen Sie zunächst Ihre Ziele für schlechte Datenstromschwellenwerte. Schlechte Datenströme sind normalerweise "PacketLossRate \> .01" oder "PacketLossRateMax \> .05". Ein weiteres wünschenswertes Ziel ist "PoorStreamsRatio \< 2%". Verwenden Sie danach detaillierte Abfragen, um AV MCU- und Vermittlungsserver mit schlechten Datenströmen zu finden, untersuchen Sie deren Ursache, sehen Sie sich die Netzwerkkomponenten in den schlechten Datenstrompfaden an, warten Sie schlechte Datenströme und definieren Sie die optimale oder "goldene" Konfiguration für die Netzwerkkomponenten. Um Ihren Erfolg beizubehalten, implementieren Sie Prozesse und Tools zum Verwalten von Konfigurationsabweichungen und Melden neuer Problembereiche.

Untersuchen Sie danach den Mediendatenstrom zwischen dem Vermittlungsserver und dem PSTN-Gateway. Bestimmen Sie zunächst Ihre Ziele für schlechte Datenstromschwellenwerte. Schlechte Datenströme sind normalerweise "PacketLossRate \> .01" oder "PacketLossRateMax \> .05". Ein weiteres wünschenswertes Ziel ist "PoorStreamsRatio \< 2%". Verwenden Sie danach detaillierte Abfragen, um Vermittlungsserver- und Gatewaypaare mit schlechten Datenströmen zu finden, untersuchen Sie deren Ursache, sehen Sie sich die Netzwerkkomponenten in den schlechten Datenstrompfaden an, warten Sie schlechte Datenströme und definieren Sie die optimale oder "goldene" Konfiguration für die Netzwerkkomponenten. Um Ihren Erfolg beizubehalten, implementieren Sie Prozesse und Tools zum Verwalten von Konfigurationsabweichungen und Melden neuer Problembereiche.

Schließlich können Sie die Integritätskennzahlen für Ihr PSTN-Gateway untersuchen. Ermitteln Sie die Statistiken, die die Integrität zeigen, und definieren Sie Ziele anhand dieser Statistiken. Hier wird keine spezielle Anleitung bereitgestellt, da viele mögliche Gateways verwendet werden können. Wenn die Ziele festgelegt sind, warten Sie nach Bedarf, um das Ziel zu erreichen. Während dieses Vorgangs werden Sie wahrscheinlich eine optimale oder "goldene" Konfiguration für das Gateway festlegen. Um Ihren Erfolg beizubehalten, implementieren Sie Prozesse und Tools zum Verwalten von Konfigurationsabweichungen und Melden neuer Problembereiche. Achten Sie darauf, dass Firmware- und Softwareupdates möglicherweise Ihre Konfiguration ändern oder dazu führen, dass Sie die Definition der "goldenen" Konfiguration ändern. Gehen Sie diese Aktivitäten deshalb mit Vorsicht an.

## Die Straße der letzten Meile

Von den zwei Möglichkeiten, mit denen Clients eine Verbindung zum Netzwerk herstellen können, wird bei einer verkabelten Verbindung erwartet, dass sie die höchste Qualität bietet. Entsprechend muss das Ihr anfänglicher Schwerpunkt für Probleme der letzten Meile sein. Verwenden Sie die CQM-Verkabelungsabfrage (LastMile\_0\_Wired) und die Verhältnisdaten für schlechte Datenströme, die diese bereitstellt. Es wird empfohlen, ein Ziel für PoorStreamsRatio \< 5% für Standorte mit \> 300 Datenströmen festzulegen. Zum Erreichen Ihrer Ziele warten Sie Subnetze in der Reihenfolge vom schlechtesten zum besten und implementieren Sie QoS.

Nachdem Sie die Qualität Ihrer verkabelten Verbindungen optimiert haben, wird das Verbessern der Qualität von Drahtlosverbindungen einfacher, da die Drahtlosinfrastruktur über dem verkabelten Kern an jedem Standort sitzt. Schlechte Drahtlosdatenströme an einem Standort mit guter verkabelter Qualität muss den speziellen Drahtloskomponenten zugeschrieben werden. Die CQM-Drahtlosabfrage (LastMile\_1\_Wireless) funktioniert in einem Datumsbereich und gibt alle internen Drahtlosdatenströme in Ihrer Umgebung zurück, die Lync-Clients an oder von Konferenz- oder Vermittlungsservern übertragen. Es wird empfohlen, ein Ziel für PoorStreamsRatio \< 5% für Standorte mit \> 300 Datenströmen zu definieren. Zum Erreichen Ihrer Ziele warten Sie Subnetze in der Reihenfolge vom schlechtesten zum besten und implementieren Sie QoS.

## Die Straße der Endpunkte

Beginnen Sie Abfragen in der Straße der Endpunkte mit den Kopfhörern und anderen Geräten, die bekanntermaßen bei der Verwendung mit Lync eine annehmbare Qualität bieten. Es wird empfohlen, ein Ziel von AvgSendListen MOS \> 3.6 für Implementierungen mit mehr als 100 Datenströmen zu setzen. Verfolgen Sie Ihr Ziel, indem Sie problematische Geräte ermitteln und reparieren oder ersetzen.

Untersuchen Sie danach das Gerät oder den PC, das bzw. der die Audiosignale für Endbenutzeranrufe verarbeitet. Eine vorgeschlagene Zielqualitätskennzahl ist AudioMic GlitchRate \> 1. Wenn Sie optimale Systemkonfigurationen für die Benutzersysteme ermitteln, definieren Sie eine "goldene" PC-Konfiguration einschließlich Treiberversionen.

Untersuchen Sie jetzt den Netzwerkpfad, den ein Audiodatenstrom von einem Lync-Endpunktsystem nimmt, der zu schlechter Audioqualität führen kann. Wenn Audio über eine VPN-Verbindung übertragen wird, beobachten Sie möglicherweise Latenzprobleme. Wenn ein interner Lync-Client bei einem Anruf mit zwei Parteien oder einem Peer-zu-Peer-Anruf keinen direkten Mediendatenstrom zu einem anderen internen Lync-Client einrichten kann, fällt er auf einen Pfad zurück, der über einen Lync-Edgeserver vermittelt wird, was wiederum zu Latenzproblemen sowie einem höheren Verlust- und Jitterrisiko führen kann. Es wird empfohlen, eine Qualitätskennzahl von 0 % Medien über VPN zu definieren. Wenn Sie warten, um das festgelegte Ziel zu erreichen, ermitteln Sie Problemsubnetze und untersuchen Sie Firewallregeln, Packet Shaper und andere relevante Netzwerkgerätekonfigurationen.

IP-Pakete können TCP (Transmission Control Protocol) oder UDP (User Datagram Protocol) verwenden. TCP ist optimal für Datendatenströme geeignet. UDP ist verbindungslos und effizienter für Medien, da TCP-Wiederherstellungsmechanismen nicht auf Verluste in Echtzeitmedien reagieren können. Lync bevorzugt immer UDP, wird aber auf TCP zurückgesetzt, wenn keine UDP-Sitzung eingerichtet werden kann. Mediensitzungen über TCP haben eine schlechtere Qualität als über UDP. Es wird empfohlen, eine Qualitätsdefinition von 0 % Verbindungen über TCP festzulegen. Wenn Sie warten, um das festgelegte Ziel zu erreichen, ermitteln Sie Problemsubnetze und untersuchen Sie Firewallregeln, Packet Shaper und andere relevante Netzwerkgerätekonfigurationen.

## Dienstverwaltung

Die Dienstverwaltung ist der Endzustand von CQM und das Ziel aller drei Straßen. Zur Aufrechterhaltung einer hohen Anrufqualität überwachen Sie die folgenden Bereiche:

1.  **Benutzer:** Wartungsaktivitäten sollten eine messbare Steigerung der Benutzerzufriedenheit zeigen. Sie können dies mit Problemtickets oder anderen Feedbackmechanismen messen. Sie können außerdem Qualitätskennzahlen veröffentlichen.

2.  **Prozess:** Definieren Sie tägliche, wöchentliche und monatliche Prozesse, um CQM zu operationalisieren. Der Überwachungsrhythmus beginnt mit einer größeren Häufigkeit, während Sie warten (täglich), und geht zu einer geringeren Häufigkeit (monatlich) über, wenn Sie stabilisieren.

3.  **Tools:** Ermitteln Sie Tools sowohl für das Messen als auch das Warten. Möglicherweise ist es nützlich, die Ausführung von CQM-Abfragen zu automatisieren, um Ihre Prozesse zu unterstützen. Für die Wartung sind möglicherweise zusätzliche Tools erforderlich, zum Beispiel um standardisierte Konfigurationen für Netzwerkelemente zu erzwingen oder Verlustprobleme in schlechen Datenströmen zu behandeln.

## Spielregeln

Sie können dieses Poster entweder als Referenz für eine CQM-Implementierung oder als Spiel verwenden, um sich mit den Konzepten vertraut zu machen. Zum Spielen benötigen Sie einen sechsseitigen Würfel und die bereitgestellten Karten. Eine Version der Karten zum Herunterladen steht zur Verfügung und kann auf Avery 5871-Standardvisitenkarten gedruckt werden.

Das Spiel ist für drei Spieler vorgesehen. Es gibt drei Straßen, die die Spieler nehmen können, um die gewünschte Qualität zu erzielen und den zentralen Dienstverwaltungsstatus zu erreichen: die Straße der Servereinrichtung, die Straße der Endpunkte und die Straße der letzten Meile. Auf jeder Straße gibt es Haltepunkte, an denen Sie Qualitätsziele bestätigen, Ziele erreichen und einen Aspekt Ihres Systems warten. Legen Sie die Karten auf dem gekennzeichneten Bereich oben ab und ziehen Sie fünf Karten. Sehen Sie sich die gezogenen Karten an und legen Sie sie im vorgesehenen Spielsegment ab. Jeder Spieler arbeitet sich auf seiner Straße Schritt für Schritt durch die Karten, bestätigt die Qualitätsziele, erreicht diese Ziele und hält die Servicelevel aufrecht. Das Spiel ist abgeschlossen, wenn alle Spieler den zentralen Dienstverwaltungszustand erreicht haben. Ausführlichere Regeln werden mit dem Download der Spielkarten bereitgestellt.

Zum **Bestätigen** eines Qualitätsziels sehen Sie sich die für dieses Ziel geltenden Parameter an und sprechen Sie laut aus, was Sie akzeptieren und was nicht. Wir haben empfohlene Startpunkte, aber Sie müssen die letzte Entscheidung treffen. Die Ausnahme sind KHI-Daten, bei denen die von Microsoft festgelegten Standards verwendet werden sollten. Weitere Informationen finden Sie auf dem begleitenden KHI-Poster.

Zum **Erreichen** eines Ziels im Spiel verwenden Sie die Karten, die anstelle von KHI-Daten und Systemabfragen bereitgestellt sind. Wenn Sie zu Beginn des Spiels keine Karte gezogen haben, die einem bestimmten Aspekt entspricht, können Sie darüber hinweggehen. Wenn eine entsprechende Karte vorhanden ist, würfeln Sie. Liegt die gewürfelte Zahl unter der auf der Karte angegebenen Zahl, haben Sie gewonnen. Entspricht die gewürfelte Zahl der Zahl auf der Karte oder liegt sie darüber, müssen Sie eine weitere Karte vom Stapel ziehen. Wenn auf der Karte angegeben ist, dass zwei oder mehr Spieler würfeln sollen, müssen alle erfolgreich würfeln.

Zum **Warten** im Spiel sprechen Sie laut den Dienstmanagementplan für diesen Aspekt der Lync-Umgebung aus.

## Siehe auch

#### Weitere Ressourcen

[Lync Server-Netzwerkhandbuch](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Key Health Indicators: die Grundlage für die Aufrechterhaltung fehlerfreier Lync-Server](http://go.microsoft.com/fwlink/?linkid=391838)  
[Lync Call Quality Methodology](http://go.microsoft.com/fwlink/?linkid=391841)

