---
title: 'Lync Server 2013: Poster: Methode der lync-Anrufqualität'
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
ms.openlocfilehash: 95105501d0403600e88d01ad5fa84363c1e81785
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724975"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-call-quality-methodology-in-lync-server-2013"></a>Methodik der lync-Anrufqualität in lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Letztes Änderungsdatum des Themas:** 2016-06-24_

Dieser Artikel ist ein Begleiter des lync-Methoden-Plakats für die [Anrufqualität](http://go.microsoft.com/fwlink/?linkid=391841) , das Sie aus dem Download Center herunterladen können.

![Poster mit Beschreibung des CQM-Prozesses](images/Dn594589.d239e04a-1c3b-4f0e-93af-88b85198615a(OCS.15).jpg "Poster mit Beschreibung des CQM-Prozesses")

Sie können dieses Poster verwenden, um mehr über CQM zu erfahren, die Methoden zur Anrufqualität für lync 2013 und 2010, die Ihnen helfen, Probleme zu finden und zu eliminieren, die sich auf die Anrufqualität und die Benutzererfahrung für lync-Implementierungen beziehen, die Enterprise-VoIP Die Methode der Anrufqualität ist ein neues Problem Behandlungs-und Dienst Verwaltungs Framework, mit dem sich die Bemühungen zur Verbesserung der Enterprise-VoIP-Dienste in lync besser konzentrieren können. In diesem Artikel finden Sie weitere Informationen zu CQM, den Arten von Servern und Lösungen, die überwacht werden, und was mit den erfassten Telemetrie-Daten zu tun ist.

Wenn Sie Fragen zur Verwendung von CQM haben, können Sie Ihre Fragen an cqmfeedback@Microsoft.com senden.

Das Poster erläutert die folgenden Bereiche:

  - Was ist lync CQM?

  - Priorisieren: Ausführen von Trend Abfragen

  - PCD

  - Verwaltet/nicht verwaltet

  - Der Server plant Road

  - Die letzte Meile Straße

  - Die Endpunkte-Straße

  - Dienstverwaltung

  - Regeln für das Brettspiel

<span id="WhatIs"></span>

<div>

## <a name="what-is-lync-cqm"></a>Was ist lync CQM?

Die Methode der Anrufqualität ist ein neues Problem Behandlungs-und Dienst Verwaltungs Framework, mit dem sich die Bemühungen zur Verbesserung der Enterprise-VoIP-Dienste in lync besser konzentrieren können. Wenn Sie CQM verwenden, sind geringere Anstrengungen erforderlich, um die Anrufqualität und die Benutzerzufriedenheit für Enterprise-VoIP-Dienste zu gewährleisten. CQM wird in der [Methode zur Anrufqualität](http://go.microsoft.com/fwlink/p/?linkid=615208)umfassender erläutert. Dieser Artikel und das Plakat sind Zusammenfassungen dieser Inhalte.

CQM gliedert die System Problembehandlung in drei Pfade oder "Straßen" auf. Diese sind: die Server plant Road, die die Server und die Verknüpfungen zwischen Ihnen, die Endpunkte Road, untersucht, die Benutzer Geräte und Medien verwendet, um Anrufe zu führen, und die letzte Meile Road, die die Integration von herkömmlichen Telefonnetz anrufen anspricht.

Jede Straße ist in mehrere Abschnitte unterteilt, die sich auf einen bestimmten Bereich oder ein bestimmtes Thema beziehen, und bei jedem Segment werden Definitionen zu einer akzeptablen Qualitätsstufe, Maßnahmen zur Erreichung dieser Qualitätsstufe und ein Service Management Plan eingerichtet, in dem die Verwaltung erfolgen kann. Diese Qualitätsstufe, bevor Sie mit dem nächsten Thema fortfahren.

Das Poster stellt lync CQM als Brettspiel für drei Spieler dar, die jeweils eine der Straßen durchlaufen werden. Karten, die im Download enthalten sind, werden verwendet, um Hindernisse für die Anrufqualität zu simulieren, die überwunden werden müssen. Hinweise und Vorschläge zu Zielen und deren Erreichung sind in den drei Pfaden sowie in den Richtlinien für die Priorisierung enthalten, die zuerst in tatsächlichen Anwendungen verfolgt werden sollen (im Spiel werden alle drei Straßen parallel adressiert).

Wie funktioniert CQM in früheren Versionen von lync? CQM ist neu für lync 2013, aber die meisten davon können an die Verwendung mit lync 2010 angepasst werden. CQM kann mit Microsoft Office Communicator zu einem gewissen Grad arbeiten, dies ist jedoch nicht getestet und wird nicht unterstützt.

Wenn Sie Fragen zur Verwendung von CQM haben, können Sie Ihre Fragen an cqmfeedback@Microsoft.com senden.

</div>

<span id="Trending"></span>

<div>

## <a name="prioritize-run-trending-queries"></a>Priorisieren: Ausführen von Trend Abfragen

Der erste Schritt in CQM besteht darin, die einzelnen Trend Abfragen für zwei Wochen auszuführen und dann die Ergebnisse zu analysieren. Priorisieren von Korrekturmaßnahmen durch den größten Datenstrom Mitwirkenden, das höchste schlechte Datenstrom Verhältnis und verwaltete Bereiche (die Sie steuern).Wenn die Audio/Video-Multi-Point-Steuereinheit (AV MCU) oder Mediations Abfragen schlechte Ergebnisse aufweisen, beginnen Sie auf der roten oder Server-Anlagen Straße.Wenn die verkabelten oder drahtlos Abfragen schlechte Ergebnisse aufweisen, beginnen Sie mit der blauen oder letzten Meile.Wenn die VPN-oder externen Abfragen schlechte Ergebnisse aufweisen, beginnen Sie mit der grünen oder Endpunkte-Straße.

Nachdem Sie eine Straße ausgewählt haben, mit der Sie beginnen möchten, definieren Sie ein Ziel für jeden Bereich (Assert), arbeiten Sie, um dieses Ziel zu erfüllen (erreichen), und implementieren Sie dann Verfahren, um im Ziel (beibehalten) zu bleiben. Sie können dieses Poster auch als Spiel verwenden, um die Prinzipien hinter CQM zu verstehen.

</div>

<span id="PCD"></span>

<div>

## <a name="pcd"></a>PCD

Das precall Diagnostics Tool (PCD) hilft Ihnen, Probleme in Ihrem Umkreisnetzwerk zu erkennen und zu diagnostizieren (die QoE-Datenbank sammelt keine Informationen über Ihr Edge-oder Umkreisnetzwerk) und auch, um Verbindungen in der letzten Meile zu beheben. Das Tool ist sowohl in einer modernen Windows 8-App als auch in http://apps.microsoft.com/windows/en-us/app/lync-2013-precall-diagnostics/9607fe33-2b51-403d-9615-c23f248e7c88einer Windows-Desktop-App verfügbar.

</div>

<span id="ManagedUn"></span>

<div>

## <a name="managedunmanaged"></a>Verwaltet/nicht verwaltet

Die lync Server-Bereitstellung und die Netzwerkinfrastruktur können in der Regel in verwaltete und nicht verwaltete Leerzeichen unterteilt werden. Der verwaltete Speicherplatz umfasst Ihr gesamtes internes Kabelnetzwerk und die Serverinfrastruktur. Der nicht verwaltete Speicherplatz ist die drahtlose Infrastruktur und die externe Netzwerkinfrastruktur.

Durch diese Unterscheidung wird die Übersichtlichkeit Ihrer Daten erhöht, und Ihre Organisation kann sich auf Arbeitslasten konzentrieren, die messbare Auswirkungen auf die Sprach-und Videoqualität Ihrer Benutzer haben. Die Erwartungen der Benutzer an die Qualität sind unterschiedlich, wenn der Anruf in einer Infrastruktur erfolgt, die Sie besitzen (verwaltet), und die Infrastruktur teilweise unter der Kontrolle einer anderen Entität (nicht verwaltet) liegt. Dies soll nicht heißen, dass drahtlose Benutzer auf Ihren eigenen Geräten überlassen werden, um hervorragende lync Server-Erfahrungen zu haben.

Um die Sprachqualität im nicht verwalteten Speicherbereich zu verbessern, müssen Sie in verwaltetem Raum eine hohe Qualität aufweisen. Ob drahtlos (Wi-Fi) als verwalteter oder nicht verwalteter Speicherplatz gilt, liegt in Ihrer Organisation. Die Techniken zum Erreichen einer gesunden Umgebung unterscheiden sich in den beiden Räumen ebenso wie die Lösungen.

</div>

<span id="ServRd"></span>

<div>

## <a name="the-server-plant-road"></a>Der Server plant Road

Segment 1 des Server plant Road-Adressen der tatsächlichen Server in der lync-Implementierung. Sammeln Sie KHI-Daten bezüglich des Servers selbst und seiner Rolle in der Implementierung, und analysieren Sie das Ergebnis. Wenn die Aktion gerechtfertigt ist, beheben Sie alle gefundenen Probleme. Weitere Informationen zu diesem Thema finden Sie im Artikel zu den [wichtigsten Integritätsindikatoren in lync Server 2013](lync-server-2013-poster-key-health-indicators.md) , der dem KHI-Poster beigefügt ist.

Das nächste Segment adressiert Mediendatenströme zwischen dem AV MCU-Server und dem Vermittlungsserver. Ermitteln Sie zunächst Ihre Ziele für schlechte Datenstrom Schwellenwerte. Schlechte Datenströme sind in \> der Regel PacketLossRate \> .01 oder PacketLossRateMax. 05. Ein weiteres erstrebenswertes \< Ziel ist PoorStreamsRatio 2%. Verwenden Sie als nächstes detaillierte Abfragen, um AVMCU-und Vermittlungsserver Paare mit schlechten Datenströmen zu finden, die Ursache schlechter Datenströme zu untersuchen, Netzwerkgeräte in den schlechten Datenstrom Pfaden zu suchen, schlechte Streams zu beheben und die optimale oder "Gold"-Konfiguration für das Netzwerk zu definieren. Geräte. Um Ihre Leistung beizubehalten, implementieren Sie Prozesse und Tools, um die Konfigurations Drift zu verwalten und neue Problembereiche zu melden.

Überprüfen Sie als nächstes die Mediendatenströme zwischen dem Vermittlungsserver und dem PSTN-Gateway (Public Switched Telephone Network). Ermitteln Sie zunächst Ihre Ziele für schlechte Datenstrom Schwellenwerte. Schlechte Datenströme sind in \> der Regel PacketLossRate \> .01 oder PacketLossRateMax. 05. Ein weiteres erstrebenswertes \< Ziel ist PoorStreamsRatio 2%. Verwenden Sie als nächstes detaillierte Abfragen, um Vermittlungsserver-und Gateway-Paare mit schlechten Datenströmen zu finden, die Ursache schlechter Datenströme zu untersuchen, Netzwerkgeräte in den schlechten Datenstrom Pfaden zu ermitteln, schlechte Streams zu beheben und die optimale oder "Gold"-Konfiguration für das Netzwerk zu definieren. Geräte. Um Ihre Leistung beizubehalten, implementieren Sie Prozesse und Tools, um die Konfigurations Drift zu verwalten und neue Problembereiche zu melden.

Überprüfen Sie abschließend die Integritäts Metrik für Ihr PSTN-Gateway. Ermitteln Sie die Statistiken, die den Status anzeigen, und definieren Sie Ziele für Sie. Hier werden keine spezifischen Anleitungen bereitgestellt, da viele mögliche Gateways verwendet werden können. Sobald Ziele festgelegt sind, können Sie bei Bedarf wiederhergestellt werden, um das Ziel zu erreichen. im Prozess definieren Sie wahrscheinlich eine "Gold"-oder optimale Konfiguration für das Gateway. Um Ihre Leistung beizubehalten, implementieren Sie Prozesse und Tools, um die Konfigurations Drift zu verwalten und neue Problembereiche zu melden. Beachten Sie, dass Firmware-und Softwareupdates Ihre Konfiguration ändern oder Sie dazu bringen können, die Definition der "Gold"-Konfiguration zu ändern, damit Sie sich mit Bedacht an diese Aktivitäten wenden können.

</div>

<span id="LastMi"></span>

<div>

## <a name="the-last-mile-road"></a>Die letzte Meile Straße

Von den zwei Möglichkeiten, wie Clients eine Verbindung mit dem Netzwerk herstellen, wird von Wired erwartet, dass Sie die höchste Qualität liefern, und dementsprechend muss dies Ihr erster Schwerpunkt für die letzten Meilen sein. Verwenden Sie die CQM-Kabel Abfrage\_(\_LastMile 0 Wired) und die von ihr bereitgestellten Datenströme. Wir empfehlen, eine Ziel PoorStreamsRatio \< von 5% für Websites \> mit 300-Streams zu definieren. Um Ihre Ziele zu erreichen, beheben Sie Subnetze, die von Worst to Best bestellt wurden, und implementieren Sie QoS.

Nachdem Sie die Qualität ihrer kabelgebundenen Verbindungen optimiert haben, wird die Verbesserung der WLAN-Qualität vereinfacht, da sich die drahtlose Infrastruktur an jedem Standort auf dem kabelgebundenen Kern befindet. Schlechte drahtlose Datenströme auf einer Website mit guter Kabelqualität müssen den jeweiligen Drahtloskomponenten zugeschrieben werden. Die CQM Wireless Query (LastMile\_1\_Wireless) funktioniert in einem Datumsbereich und gibt alle internen drahtlos Datenströme in Ihrer Umgebung von lync-Clients zu oder von Konferenzservern oder Vermittlungsservern zurück. Wir empfehlen, eine Ziel PoorStreamsRatio \< von 5% für Websites \> mit 300-Streams zu definieren. Um Ihre Ziele zu erreichen, beheben Sie Subnetze, die von Worst to Best bestellt wurden, und implementieren Sie QoS.

</div>

<span id="EndPt"></span>

<div>

## <a name="the-end-points-road"></a>Die Endpunkte-Straße

Beginnen Sie Anfragen in die Endpunkte der Straße, wobei die Headsets und andere Geräte bekanntermaßen in Verbindung mit lync akzeptable Qualität produzieren. Wir empfehlen eine Ziel AvgSendListen Mos \> 3,6 für Implementierungen mit mehr als 100 Streams.) Erreichen Sie das Ziel, indem Sie problematische Geräte identifizieren und beheben oder ersetzen.

Überprüfen Sie als nächstes das Gerät oder den PC, in dem die Audiodaten für Endbenutzer Anrufe verarbeitet werden. Eine vorgeschlagene Ziel Qualitätsmetrik ist eine AudioMicGlitchRate \<= 1. Wenn Sie optimale Systemkonfigurationen für die Benutzersysteme erkennen, definieren Sie eine "Goldene" PC-Konfiguration mit Treiberversionen.

Untersuchen Sie nun den Netzwerkpfad, den ein Audiostream von einem lync-Endpunkt System benötigt, was zu schlechter Audioqualität führen kann. Wenn Audio über eine VPN-Verbindung reist, werden möglicherweise Latenzprobleme angezeigt. Wenn ein interner lync-Client keinen direkten Mediendatenstrom zu einem anderen internen lync-Client für einen zweiseitigen oder Peer-zu-Peer-Anruf einrichten kann, wird er auf einen Pfad zurückgegriffen, der über einen lync-Edgeserver weitergeleitet wird, was wiederum zu Latenzproblemen führt, sowie zu einem erhöhten Potenzial für Verlust und Jitter. Wir empfehlen, dass Sie eine Qualitätsmetrik von 0% Medien über VPN definieren. Bei der Problembehebung, um das von Ihnen festgelegte Ziel zu erreichen, identifizieren Sie Problem-Subnetze und untersuchen Firewall-Regeln, Paket-shaper und andere relevante Netzwerkgeräte-Konfiguration.

IP-Pakete können entweder TCP (Transmission Control Protocol) oder UDP (User Datagram Protocol) verwenden. TCP eignet sich optimal für Datenströme. UDP ist verbindungslos und effizienter für Medien, da TCP-Wiederherstellungsmechanismen den Verlust in Echtzeit-Medien nicht beheben können. Lync bevorzugt UDP immer, wird aber auf TCP zurückgesetzt, wenn keine UDP-Sitzung hergestellt werden kann. Mediensitzungen über TCP weisen eine schlechtere Qualität als über UDP auf. Wir empfehlen eine Qualitätsdefinition von 0% Verbindungen über TCP. Bei der Problembehebung, um das von Ihnen festgelegte Ziel zu erreichen, identifizieren Sie Problem-Subnetze und untersuchen Firewall-Regeln, Paket-shaper und andere relevante Netzwerkgeräte-Konfiguration.

</div>

<span id="ServMgt"></span>

<div>

## <a name="service-management"></a>Dienstverwaltung

Dienstverwaltung ist der Endstatus von CQM und das Ziel für alle drei Straßen. Um eine hohe Anrufqualität zu gewährleisten, sollten Sie die folgenden Bereiche überwachen:

1.  **Benutzer** -Behebungs Aktivitäten sollten eine messbare Steigerung der Benutzerzufriedenheit aufweisen. Sie können dies anhand von Problemtickets oder anderen Feedbackmechanismen messen. Sie können auch Qualitäts Metriken veröffentlichen.

2.  **Prozess** – definieren Sie tägliche, wöchentliche und monatliche Prozesse für die operative CQM. Die Überwachung des Rhythmus beginnt mit einer höheren Häufigkeit, während Sie (täglich) eine erneute Vermittlung durchführen und auf eine niedrigere Häufigkeit (monatlich) umstellen, während Sie sich stabilisieren.

3.  **Tools** – identifizieren Sie Tools, um beide zu messen und zu beheben. Möglicherweise ist es hilfreich, die Ausführung der CQM-Abfragen zu automatisieren, um Ihre Prozesse zu unterstützen. Für die Behebung sind möglicherweise zusätzliche Tools erforderlich, um beispielsweise standardisierte Konfigurationen für Netzwerkelemente durchzusetzen oder Verlust in schlechten Datenströmen zu beheben.

</div>

<span id="BoardGm"></span>

<div>

## <a name="board-game-rules"></a>Regeln für das Brettspiel

Sie können dieses Poster entweder als Verweis auf eine CQM-Implementierung oder als Spiel verwenden, um die Konzepte zu üben. Damit Sie spielen können, benötigen Sie einen 1 6-seitigen Würfel, und die Karten werden bereitgestellt. Eine herunterladbare Version der Karten steht zum Drucken auf Standard-Avery 5871-Visitenkarten zur Verfügung.

Das Spiel ist für 3 Spieler. Es gibt drei Pfade, die die Spieler verwenden können, um die gewünschte Qualität zu erreichen und den Center-Service Verwaltungsstatus zu erreichen: Server Anlage, Endpunkt und letzte Meile. Jeder Pfad hat Stopps auf dem Weg, in dem Sie Qualitätsziele behaupten, Ziele erreichen und einen Aspekt Ihres Systems verwalten. Legen Sie die Karten in dem oben angegebenen Bereich ab, und ziehen Sie dann fünf Karten. Überprüfen Sie die Karten, die Sie gezeichnet haben, und legen Sie Sie auf das entsprechende Board-Segment. Jeder Spieler bewegt sich Schritt für Schritt durch die Karten auf seinem Weg, indem er Qualitätsziele, die Erreichung dieser Ziele und die Beibehaltung der Service Levels behauptet. Das Spiel ist abgeschlossen, wenn alle Spieler den Center Service Management-Zustand erreichen. Detailliertere Regeln finden Sie im Spielkarten Download.

Wenn Sie ein Qualitätsziel **bestätigen** möchten, überprüfen Sie die auf dieses Ziel anwendbaren Parameter, und geben Sie laut an, was Sie akzeptieren und welche nicht. Wir haben Anfangspunkte empfohlen, aber Sie müssen den letzten Anruf führen. Die Ausnahme sind KHI-Daten, bei denen die von Microsoft festgelegten Standards verwendet werden sollten. Sehen Sie sich das dazugehörige KHI-Poster an.

Um im Spiel zu **erreichen** , verwenden Sie die Karten, die anstelle von KHI-Daten und System Abfragen zur Verfügung gestellt werden. Wenn Sie zu Beginn des Spiels keine Karte in Bezug auf einen bestimmten Aspekt gezeichnet haben, können Sie sie weiterführen. Wenn eine entsprechende Karte vorhanden ist, drehen Sie den Würfel. Wenn Sie unter der auf der Karte angegebenen Nummer gerollt haben, ist es Ihnen gelungen. Wenn Sie bei oder über die angegebene Zahl Rollen, müssen Sie eine weitere Karte vom Stapel ziehen. Wenn die Karte angibt, dass zwei oder mehr Spieler Rollen müssen, müssen Sie alle erfolgreich Rollen.

Wenn Sie im Spiel **warten** möchten, geben Sie den Service Management Plan für diesen Aspekt der lync-Umgebung laut an.

</div>

<div>

## <a name="see-also"></a>Siehe auch


[Lync Server-Netzwerkhandbuch](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[Wichtige Integritätsindikatoren: die Grundlage für die Verwaltung von fehlerfreien lync-Servern](http://go.microsoft.com/fwlink/?linkid=391838)  
[Methodik der lync-Anrufqualität](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

