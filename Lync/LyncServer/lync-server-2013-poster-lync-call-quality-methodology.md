---
title: 'Lync Server 2013: Poster: lync Call Quality Method'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Lync Call Quality Methodology'
ms:assetid: a069f4e5-4f80-4f0f-8657-2e07276b6b41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593600(v=OCS.15)
ms:contentKeyID: 61084874
ms.date: 06/24/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 849e74fb4857dd7b3ab98b8a8efd9c3ce3781e35
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043037"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Methode für die lync-Anrufqualität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsstand des Themas:** 2016-06-24_

Dieser Artikel ist ein Begleiter zum [lync Call Quality Method](http://go.microsoft.com/fwlink/?linkid=391841) -Poster, das Sie im Download Center herunterladen können.

![Poster mit Beschreibung des CQM-Prozesses](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster mit Beschreibung des CQM-Prozesses")

Sie können dieses Poster verwenden, um mehr über CQM, die Methode für die Anrufqualität für lync 2013 und 2010 zu erfahren, mit deren Hilfe Sie Probleme bei der Anrufqualität und der Benutzerfreundlichkeit für lync-Implementierungen, die Enterprise-VoIP-Funktionen umfassen, finden und beseitigen. Die Methode für die Anrufqualität ist ein neues Framework zur Problembehandlung und Dienstverwaltung, mit dem die Bemühungen zur Verbesserung der Enterprise-VoIP-Dienste in lync verbessert werden können. In diesem Artikel erfahren Sie mehr über CQM, die Arten von Servern und Lösungen, die überwacht werden, und wie Sie mit den erfassten Telemetrie-Daten vorgehen müssen.

Wenn Sie Fragen zur Verwendung von CQM haben, können Sie Ihre Fragen an cqmfeedback@Microsoft.com übermitteln.

Das Poster erläutert die folgenden Bereiche:

  - Was ist lync CQM?

  - Priorisieren: Ausführen von Trend Abfragen

  - PCD

  - Verwaltet/nicht verwaltet

  - Die Server-Werks Straße

  - Die letzte Meile Straße

  - Die End Points Road

  - Dienstverwaltung

  - Regeln für das Brettspiel

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>Was ist lync CQM?

Die Methode für die Anrufqualität ist ein neues Framework zur Problembehandlung und Dienstverwaltung, mit dem die Bemühungen zur Verbesserung der Enterprise-VoIP-Dienste in lync verbessert werden können. Wenn Sie CQM verwenden, sind geringere Anstrengungen erforderlich, um die Anrufqualität und die Benutzerzufriedenheit für Enterprise-VoIP-Dienste zu gewährleisten. CQM wird in der Methode für die [Anrufqualität](http://go.microsoft.com/fwlink/p/?linkid=615208)ausführlicher erläutert. Dieser Artikel und das Poster sind Zusammenfassungen dieser Inhalte.

CQM bricht die System Problembehandlung in drei Pfade oder "Straßen" ab. Dabei handelt es sich um die Server-Werks Straße, die die Server und die Verbindungen zwischen Ihnen, die Endpunkte-Straße, die auf Benutzergeräten und Medien, die für die Durchführung von Anrufen verwendet werden, und die letzte Meile, die die Integration von herkömmlichen Telefonnetz anrufen adressiert, betrachtet.

Jede Straße ist in mehrere Abschnitte unterteilt, die sich auf einen bestimmten Bereich oder ein bestimmtes Thema beziehen, und bei jedem Segment werden Definitionen darüber erstellt, was eine akzeptable Qualitätsstufe ist, es werden Maßnahmen ergriffen, um diese Qualitätsstufe zu erreichen, und es wird ein Service Management Plan bereitgestellt, um zu warten. Diese Qualitätsstufe, bevor Sie mit dem nächsten Thema fortfahren.

Das Poster stellt lync CQM als Brettspiel für drei Spieler vor, von denen jeder eine der Straßen durchläuft. Im Download enthaltene Karten werden verwendet, um Beeinträchtigungen der Anrufqualität zu simulieren, die überwunden werden müssen. Hinweise und Vorschläge zu Zielen und deren Erreichung finden Sie in den drei Pfaden sowie in den Richtlinien für die Priorisierung, für welche Straße zunächst in den tatsächlichen Anwendungen vorgegangen werden soll (im Spiel werden alle drei Straßen parallel adressiert).

Wie funktioniert CQM in früheren Versionen von lync? CQM ist neu für lync 2013, aber das meiste kann für die Verwendung mit lync 2010 angepasst werden. CQM kann mit Microsoft Office Communicator ein gewisses Maß an Arbeit haben, dies ist jedoch nicht getestet und wird nicht unterstützt.

Wenn Sie Fragen zur Verwendung von CQM haben, können Sie Ihre Fragen an cqmfeedback@Microsoft.com übermitteln.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Priorisieren: Ausführen von Trend Abfragen

Der erste Schritt in CQM besteht darin, alle Trend Abfragen zwei Wochen lang auszuführen und dann die Ergebnisse zu analysieren. Priorisieren Sie Korrekturmaßnahmen durch den größten Stream Mitwirkenden, das höchste schlechte Datenstrom Verhältnis und verwaltete Bereiche (die Sie steuern).Wenn die Audio/Video-Mehrpunkt-Steuereinheit (AV MCU) oder Vermittlungs Abfragen schlechte Ergebnisse aufweisen, starten Sie auf der roten oder der Server-Werks Straße.Wenn die kabelgebundene oder drahtlose Abfragen schlechte Ergebnisse anzeigen, beginnen Sie auf der blauen oder letzten Meile Straße.Wenn die VPN-oder externen Abfragen schlechte Ergebnisse aufweisen, beginnen Sie mit der grünen oder Endpunkt Straße.

Nachdem Sie eine Straße für den Anfang ausgewählt haben, definieren Sie ein Ziel für jeden Bereich (Assert), arbeiten Sie an der Erfüllung dieses Ziels (erreichen), und implementieren Sie dann Verfahren, um das Ziel beizubehalten. Sie können dieses Poster auch als ein Spiel verwenden, um die Prinzipien hinter CQM zu verstehen.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

Das precall Diagnostics Tool (PCD) hilft Ihnen bei der Identifizierung und Diagnose von Problemen in Ihrem Umkreisnetzwerk (die QoE-Datenbank sammelt keine Informationen im Edge-oder Umkreisnetzwerk) und auch zur Problembehandlung von Verbindungen in der letzten Meile. Das Tool ist sowohl als Windows 8 moderne App als auch als Windows http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88-Desktop-App verfügbar.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Verwaltet/nicht verwaltet

Die lync Server-Bereitstellung und die Netzwerkinfrastruktur können in der Regel in verwaltete und nicht verwaltete Leerzeichen unterteilt werden. Der verwaltete Speicherplatz umfasst das gesamte interne kabelgebundene Netzwerk und die Serverinfrastruktur. Der nicht verwaltete Speicherplatz ist die drahtlose Infrastruktur und die externe Netzwerkinfrastruktur.

Diese Unterscheidung erhöht die Übersichtlichkeit Ihrer Daten und hilft Ihrer Organisation bei der Fokussierung auf Arbeitslasten, die sich messbar auf die Sprach-und Videoqualität Ihrer Benutzer auswirken. Benutzer haben eine andere Erwartung an die Qualität, wenn der Anruf in einer Infrastruktur getätigt wird, die Sie besitzen (verwaltet) und Infrastruktur, die teilweise der Steuerung einer anderen Entität (nicht verwaltet) unterliegt. Dies bedeutet nicht, dass drahtlose Benutzer auf Ihre eigenen Geräte überlassen werden, um hervorragende lync Server-Erlebnisse zu haben.

Die Verbesserung der Sprachqualität auf dem nicht verwalteten Speicherplatz erfordert eine hohe Qualität im verwalteten Bereich. Ob Wireless (Wi-Fi) als verwaltet oder nicht verwalteter Speicherplatz gilt, liegt bei Ihrer Organisation. Die Techniken zum Erreichen einer gesunden Umgebung unterscheiden sich in den beiden Bereichen, ebenso wie die Lösungen.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>Die Server-Werks Straße

In Segment 1 der Server-Werks Straße werden die tatsächlichen Server in der lync-Implementierung behandelt. Sammeln Sie KHI-Daten bezüglich des Servers selbst und seiner Rolle in der Implementierung, und analysieren Sie das Ergebnis. Wenn die Aktion gerechtfertigt ist, beheben Sie die gefundenen Probleme. Ausführlichere Informationen zu diesem Thema finden Sie im Artikel über [wichtige Gesundheitsindikatoren in lync Server 2013](lync-server-2013-poster-key-health-indicators.md) , die dem KHI-Poster beigefügt sind.

Das nächste Segment behandelt Mediendatenströme zwischen dem AV MCU-Server und dem Vermittlungsserver. Beginnen Sie mit der Bestimmung der Ziele für schlechte Datenstrom Schwellenwerte. Schlechte Streams sind in der \> Regel PacketLossRate .01 \> oder PacketLossRateMax. 05. Ein weiteres erstrebenswertes \< Ziel ist PoorStreamsRatio 2%. Verwenden Sie anschließend detaillierte Abfragen, um AVMCU-und Vermittlungsserver Paare mit schlechten Streams zu finden, die Ursache für schwache Streams zu untersuchen, Netzwerkgeräte in den schlechten Strompfaden zu suchen, schwache Datenströme zu beheben und die optimale oder "Goldene" Konfiguration für das Netzwerk zu definieren. Ausrüstung. Um Ihre Leistung aufrechtzuerhalten, implementieren Sie Prozesse und Tools, um die Konfigurations Verschiebung zu verwalten und neue Problembereiche zu melden.

Überprüfen Sie als nächstes die Mediendatenströme zwischen dem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network). Beginnen Sie mit der Bestimmung der Ziele für schlechte Datenstrom Schwellenwerte. Schlechte Streams sind in der \> Regel PacketLossRate .01 \> oder PacketLossRateMax. 05. Ein weiteres erstrebenswertes \< Ziel ist PoorStreamsRatio 2%. Verwenden Sie anschließend detaillierte Abfragen, um Vermittlungsserver-und Gateway-Paare mit schlechten Streams zu finden, die Ursache für schwache Streams zu untersuchen, Netzwerkgeräte in den schlechten Strompfaden zu suchen, schwache Datenströme zu beheben und die optimale oder "Goldene" Konfiguration für das Netzwerk zu definieren. Ausrüstung. Um Ihre Leistung aufrechtzuerhalten, implementieren Sie Prozesse und Tools, um die Konfigurations Verschiebung zu verwalten und neue Problembereiche zu melden.

Untersuchen Sie schließlich die Integritäts Metrik für Ihr PSTN-Gateway. Identifizieren der Statistiken, die die Integrität anzeigen, und Definieren von Zielen für diese. Hier werden keine spezifischen Anleitungen bereitgestellt, da viele mögliche Gateways verwendet werden können. Sobald die Ziele festgelegt wurden, können Sie bei Bedarf korrigieren, um das Ziel zu erreichen. in diesem Prozess werden Sie wahrscheinlich eine "Gold"-oder eine optimale Konfiguration für das Gateway definieren. Um Ihre Leistung aufrechtzuerhalten, implementieren Sie Prozesse und Tools, um die Konfigurations Verschiebung zu verwalten und neue Problembereiche zu melden. Beachten Sie, dass Firmware-und Softwareupdates möglicherweise Ihre Konfiguration ändern oder die Definition der "Gold"-Konfiguration ändern, um diese Aktivitäten daher mit Bedacht anzugehen.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>Die letzte Meile Straße

Von den beiden Möglichkeiten, mit denen Clients eine Verbindung mit dem Netzwerk herstellen, wird von Wired erwartet, dass Sie die höchste Qualität liefern, und dementsprechend muss Ihr anfänglicher Schwerpunkt für die letzten Meile-Probleme sein. Verwenden Sie die CQM-verkabelte Abfrage (LastMile\_0\_Wired) und die von ihr bereitgestellten Datenstrom Verhältnisdaten. Wir empfehlen, ein Ziel PoorStreamsRatio \< von 5% für Websites \> mit 300-Streams festzulegen. Um Ihre Ziele zu erreichen, müssen Sie die Subnetze, die von der schlechtesten bis zum besten sortiert sind, korrigieren und QoS implementieren.

Nachdem Sie die Qualität ihrer kabelgebundenen Verbindungen optimiert haben, wird die Verbesserung der drahtlosen Qualität vereinfacht, da sich die drahtlose Infrastruktur an jedem Standort oben auf dem drahtgebundenen Kern befindet. Schlechte drahtlose Datenströme an einem Standort mit guter Kabelqualität müssen den spezifischen drahtlosen Komponenten zugeschrieben werden. Die drahtlose CQM-Abfrage (\_LastMile\_1 Wireless) arbeitet in einem Datumsbereich und gibt alle internen drahtlosen Datenströme in Ihrer Umgebung von lync-Clients zu oder von Konferenzservern oder Vermittlungsservern zurück. Wir empfehlen, ein Ziel PoorStreamsRatio \< von 5% für Websites \> mit 300-Streams festzulegen. Um Ihre Ziele zu erreichen, müssen Sie die Subnetze, die von der schlechtesten bis zum besten sortiert sind, korrigieren und QoS implementieren.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>Die End Points Road

Beginnen Sie mit Anfragen an der End Points Road, wobei die Headsets und andere Geräte bekanntermaßen eine akzeptable Qualität bei Verwendung mit lync erzeugen. Wir schlagen ein Ziel AvgSendListen Mos \> 3,6 für Implementierungen mit über 100 Streams vor.) Erreichen Sie das Ziel, indem Sie problematische Geräte identifizieren und diese reparieren oder ersetzen.

Überprüfen Sie als nächstes das Gerät oder den PC, in dem die Audiodaten für Endbenutzer Anrufe verarbeitet werden. Eine vorgeschlagene Ziel Qualitätsmetrik ist eine AudioMicGlitchRate \<= 1. Definieren Sie bei der Ermittlung optimaler Systemkonfigurationen für die Benutzersysteme eine "Goldene" PC-Konfiguration mit Treiberversionen.

Untersuchen Sie nun den Netzwerkpfad, den ein Audiostream von einem lync-Endpunkt System benötigt, was zu einer schlechten Audioqualität führen kann. Wenn die Audiodaten über eine VPN-Verbindung transportiert werden, werden möglicherweise Latenzprobleme angezeigt. Wenn ein interner lync-Client keinen direkten Mediendatenstrom zu einem anderen internen lync-Client für einen zwei-oder einen Peer-zu-Peer-Anruf einrichten kann, greift er auf einen Pfad zurück, der über einen lync-Edgeserver weitergeleitet wird, was wiederum zu Wartezeiten und einem erhöhten Potenzial für Verlust und Jitter. Es wird empfohlen, eine Qualitätsmetrik von 0% Medien über VPN zu definieren. Wenn Sie die Lösung zur Erreichung des von Ihnen festgelegten Ziels korrigieren, identifizieren Sie Problem Subnetze und untersuchen Sie Firewallregeln, Paket Formteile und andere relevante Netzwerkgeräte Konfigurationen.

IP-Pakete können entweder TCP (Transmission Control Protocol) oder UDP (User Datagram Protocol) verwenden. TCP eignet sich optimal für Datenströme. UDP ist verbindungslos und ist für Medien effizienter, da die TCP-Wiederherstellungsmechanismen keinen Verlust in Echt Zeit Medien adressieren können. Lync bevorzugt UDP immer, wird jedoch auf TCP zurückgesetzt, wenn keine UDP-Sitzung hergestellt werden kann. Mediensitzungen über TCP weisen eine schlechtere Qualität als über UDP auf. Wir empfehlen eine Qualitätsdefinition von 0% Verbindungen über TCP. Wenn Sie die Lösung zur Erreichung des von Ihnen festgelegten Ziels korrigieren, identifizieren Sie Problem Subnetze und untersuchen Sie Firewallregeln, Paket Formteile und andere relevante Netzwerkgeräte Konfigurationen.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Dienstverwaltung

Dienstverwaltung ist der Endzustand von CQM und das Ziel für alle drei Straßen. Um eine hohe Anrufqualität aufrechtzuerhalten, überwachen Sie die folgenden Bereiche:

1.  **Benutzer** – Korrekturaktivitäten sollten eine messbare höhere Benutzerzufriedenheit aufweisen. Sie können dies durch Problemtickets oder andere Feedbackmechanismen messen. Sie können auch Qualitäts Metriken veröffentlichen.

2.  **Process** -define tägliche, wöchentliche und monatliche Prozesse zur operativen CQM. Der Rhythmus der Überwachung beginnt bei einer höheren Frequenz, während Sie (täglich) umstellen und während der Stabilisierung zu einer niedrigeren Frequenz (monatlich) wechselt.

3.  **Tools** – Identifizieren von Tools, die sowohl messen als auch korrigieren. Möglicherweise ist es hilfreich, die Ausführung der CQM-Abfragen zur Unterstützung ihrer Prozesse zu automatisieren. Für die Wiederherstellung sind möglicherweise zusätzliche Tools erforderlich, beispielsweise zum Erzwingen standardisierter Konfigurationen auf Netzwerkelementen oder zur Problembehandlung bei Verlusten in schlechten Datenströmen.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Regeln für das Brettspiel

Sie können dieses Poster entweder als Verweis auf eine CQM-Implementierung oder als ein Spiel verwenden, um die Konzepte zu üben. Um zu spielen, benötigen Sie 1 6-seitige Matrizen und die Karten werden bereitgestellt. Eine herunterladbare Version der Karten ist verfügbar, um auf Standard-Avery 5871-Visitenkarten zu drucken.

Das Spiel ist für 3 Spieler. Es gibt drei Pfade, die die Spieler verwenden können, um die gewünschte Qualität zu erreichen und den Center Service Management-Status zu erreichen: Server Pflanze, Endpunkt und letzte Meile. Jeder Pfad verfügt über Stopps auf dem Weg, an dem Sie Qualitätsziele durchsetzen, Ziele erreichen und einen Aspekt Ihres Systems aufrecht erhalten. Legen Sie die Karten in den oben angegebenen Bereich, und ziehen Sie dann 5 Karten. Überprüfen Sie die Karten, die Sie gezeichnet haben, und platzieren Sie Sie im entsprechenden Board-Segment. Jeder Spieler bewegt sich Schritt für Schritt durch die Karten, indem er Qualitätsziele, die Erreichung dieser Ziele und die Wartung der Service Levels bestätigt. Das Spiel ist abgeschlossen, wenn alle Spieler den Center Service Management State erreichen. Ausführlichere Regeln werden mit dem Spielkarten Download bereitgestellt.

Um ein Qualitätsziel zu **bestätigen** , überprüfen Sie die für dieses Ziel geltenden Parameter, und geben Sie laut an, was Sie akzeptieren möchten und welche nicht. Wir haben Anfangspunkte empfohlen, aber Sie müssen den letzten Aufruf vornehmen. Die Ausnahme sind KHI-Daten, bei denen die von Microsoft festgelegten Standards verwendet werden sollten. Siehe das zugehörige KHI-Poster.

Um im Spiel zu **erreichen** , verwenden Sie die Karten, die anstelle von KHI-Daten und System Abfragen bereitgestellt werden. Wenn Sie zu Beginn des Spiels keine Karte im Zusammenhang mit einem bestimmten Aspekt gezeichnet haben, können Sie Sie weiter daran vorbeiführen. Wenn eine entsprechende Karte vorhanden ist, Rollen Sie den Würfel. Wenn Sie unter der auf der Karte aufgeführten Nummer gerollt haben, ist es Ihnen gelungen. Wenn Sie die angegebene Zahl bei oder über Rollen, müssen Sie eine weitere Karte aus dem Stapel ziehen. Wenn die Karte angibt, dass zwei oder mehr Spieler Rollen müssen, müssen Sie alle erfolgreich ausgeführt werden.

Um im Spiel **beizubehalten** , geben Sie den Dienst Verwaltungsplan zu diesem Aspekt der lync-Umgebung laut an.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Leitfaden für lync Server Netzwerke](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Wichtige Integritätsindikatoren: die Grundlage für die Verwaltung gesunder lync-Server](http://go.microsoft.com/fwlink/?linkid=391838)  
[Methode für die lync-Anrufqualität](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

