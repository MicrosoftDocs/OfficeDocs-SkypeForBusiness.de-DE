---
title: Definieren von Erfolg in Audiokonferenzen, Telefonsystem mit Anrufplänen oder Telefonsystem mit direktem Routing – Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Messen Sie die Ergebnisse ihrer Audiokonferenzen, Ihres Telefonsystems mit Anrufplänen oder einer direkten Routing Bereitstellung für das Telefonsystem, und überprüfen Sie, ob Sie die gewünschten Ergebnisse erzielt haben.
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 96fb3a0031b27b331dbc6424650f101b0f0a34f3
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433096"
---
# <a name="define-my-success"></a>Definieren der Erfolgskriterien

In diesem Artikel finden Sie eine Übersicht über die Anforderungen zum Definieren von Erfolg für die Bereitstellung von Audiokonferenzen, Telefonsystemen mit Anrufplänen oder direktes Routing für Telefonsysteme für Ihre Organisation. Wenn Sie den Erfolg richtig definieren, können Sie die Ergebnisse während der Bereitstellung Messen und sicherstellen, dass die von Ihnen gesuchten Ergebnisse die gewünschten Ergebnisse aufweisen.

<!--ENDOFSECTION-->

**Audiokonferenz** bietet Organisationen zusätzliche Einstiegspunkte für alle Besprechungen (Ad-hoc-oder geplant), indem Besprechungsteilnehmer über ein öffentliches Telefonnetz (PSTN) teilnehmen können, indem Sie sich über herkömmliche Festnetznummern, private Branch Exchange (PBX) oder Mobiltelefone. Dies ist hilfreich, wenn sich der Organisator oder die Teilnehmer nicht vor einem Computer befinden oder wenn Datenverbindungen nicht verfügbar oder zu unzuverlässig sind, um die Sprachkommunikation zu unterstützen, beispielsweise in einem Remotebereich mit fleckiger mobiler Datenversorgung oder verbunden mit einem kostenlosen öffentlichen WLAN-Zugang. Dienst mit begrenzter Bandbreite oder wenn Besprechungsteilnehmer sich lieber mit einem Telefon Endpunkt in die Besprechung einwählen, der für Sie leicht zugänglich ist.

Das **Telefon System mit Anrufplänen ("Anrufpläne")** bietet Organisationen eine Möglichkeit, ihren Arbeitsplatz zu modernisieren, indem Benutzer in die Lage versetzt werden, geschäftliche Telefonanrufe von ihren Computern und mobilen Geräten aus zu führen. Die Modernisierung des Arbeitsplatzes kann Teil einer beliebigen Anzahl von Szenarien sein – einer aktivitätsbasierten Implementierung, einer wichtigen Office Move-Funktion, einer Office fit-out-Aktualisierung, dem Ruhestand einer Legacy-PBX-Lösung, dem Abschluss eines PSTN-Dienstanbieter Vertrags usw. Mit Anrufplänen erleichtert Microsoft die Konnektivität mit dem PSTN.

Das **direkte Routing des Telefonsystems ("Direktes Routing")** bietet Organisationen dieselben oben aufgeführten Vorteile für Anrufpläne, mit der Ausnahme, dass die PSTN-Konnektivität von einem Drittanbieter und nicht von Microsoft unterstützt wird. Dies ermöglicht die Bereitstellung in Ländern, in denen keine Anrufpläne verfügbar sind, oder in Bereitstellungen, bei denen ein vorhandener PSTN-Dienstanbieter Vertrag gewartet werden muss oder die Interoperabilität mit bestimmten lokalen Systemen erforderlich ist. Ein weiteres Szenario zur Berücksichtigung des direkten Routings ist die Interoperabilität des Telefonie-Systems. Während Benutzer in Teams zu anrufen gewechselt werden, verbleiben einige Benutzer möglicherweise auf Legacy-PBX-Anlagen. Durch das direkte Routing können beide Anwendungsfälle koexistieren. Der Anrufverkehr zwischen den Benutzern auf Legacysystemen und Teammitgliedern bleibt innerhalb des Unternehmens.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definieren von Geschäfts Anwendungsfällen für Audiokonferenzen, Anrufpläne oder direktes Routing

Zunächst müssen Hauptprojekt beteiligte Geschäfts Anwendungsfälle definieren, die die Implementierung von Audiokonferenzen, Anrufplänen oder direktem Routing unterstützen.

Unternehmens-Anwendungsfälle sollen erwartete und messbare Geschäftsergebnisse definieren und dokumentieren und Folgendes umfassen:

-   Beschreibung des aktuellen Geschäftsprozesses

-   Herausforderungen beim vorhandenen Geschäftsprozess

-   Wie diese Herausforderungen mithilfe der Technologie bewältigt werden können

-   Die erwarteten und messbaren Geschäftsergebnisse, die durch die Bewältigung dieser Herausforderungen erzielt werden können

> [!TIP]
> Der folgende Code ist ein Beispiel für einen abgeschlossenen Geschäfts Anwendungsfall für Audiokonferenzen:
> 
> |         |
> |---------|
> |**Beschreibung des aktuellen Geschäftsprozesses**<br>Für interne Besprechungen und Besprechungen mit Dritten nutzt Contoso derzeit die von etablierten lokalen Telefonanbietern bereitgestellten PSTN-Konferenzdienste, die im Minutentakt abgerechnet werden.|
> |**Herausforderungen mit vorhandenen Geschäftsprozessen**<br>Contoso verbringt rund USD1 Millionen pro Jahr für den aktuellen PSTN-Konferenzdienst, wobei 75% der Kosten für interne Besprechungen entstehen. Die Verwendung herkömmlicher Telefonie-Endpunkte für die Teilnahme an den vom PSTN-Konferenzdienst gehosteten Besprechungen ist nicht an dem Plan ausgerichtet, in dem die Organisation Teams als moderne Kommunikations-und Zusammenarbeitsplattform übernehmen soll.|
> |**Wie diesen Herausforderungen am besten begegnet werden kann**<br>Mit der Einführung von Microsoft Teams als moderne Kommunikations-und Zusammenarbeitsplattform wird erwartet, dass interne Benutzer in erster Linie an Besprechungen teilnehmen, indem Sie Ihre PCs verwenden, die mit optimierten Headsets und Besprechungsraum Geräten ausgestattet sind. Der Audiokonferenzdienst steht zur Unterstützung externer Teilnehmer zur Verfügung oder unterstützt Situationen, in denen die Verwendung von PC-Audio für die internen Teilnehmer nicht vorteilhaft ist.|
> |**Erwartete, messbare Geschäftsergebnisse**<br>Der Wechsel zu Teams als moderne Kommunikations-und Zusammenarbeitsplattform, kombiniert mit dem Audiokonferenzdienst, wird die Kosten für die Bereitstellung des PSTN-Konferenz Diensts erheblich reduzieren.|

<br>

> [!TIP]
> Der folgende Code ist ein Beispiel für einen abgeschlossenen Geschäfts Anwendungsfall für Anrufpläne:
> 
> |         |
> |---------|
> |**Beschreibung des aktuellen Geschäftsprozesses**<br>Die Standard Konfiguration der Office-Arbeitsbereiche von Contoso umfasst ein Desktoptelefon für jeden Schreibtisch. Jedem Mitarbeiter wurde eine direkte Durchwahl (DID)-Telefonnummer zugewiesen. Die Desktoptelefone sind mit einem PBX-System verbunden und über einen SIP-Trunk (Session Initiation Protocol) mit PSTN verbunden. Mitarbeiter können nur Telefonanrufe über ihre zugewiesenen Desktoptelefone tätigen und empfangen.|
> |**Herausforderungen mit vorhandenen Geschäftsprozessen**<br>Die Nutzungsanalyse der Desktoptelefone zeigt, dass nur 10% der Desktoptelefone aktiv verwendet werden, wobei der andere so konfiguriert ist, dass Sie Anrufe an Mobiltelefone weiterleiten oder gleichzeitig an Handys anrufen können. Die Verwaltung des vorhandenen PBX-Systems und zugehöriger Desktoptelefone trägt zu 20% der monatlichen Telefondienst Kosten von Contoso bei.|
> |**Wie diesen Herausforderungen am besten begegnet werden kann**<br>Mit Anrufplänen kann der Personal Computer eines Benutzers Anrufe über das Datennetzwerk empfangen und tätigen, indem er die native Microsoft Teams-App nutzt. Dadurch ist es nicht mehr notwendig, Desktop-Smartphones einzuführen und zu warten, und es wird die Möglichkeit eröffnet, das vorhandene PBX-System zu stillen, da der Telefondienst über die Cloud über das Netzwerk bereitgestellt werden kann, ohne dass dies von einem herkömmlichen Telefonsystem abhängig ist.|
> |**Erwartete, messbare Geschäftsergebnisse**<br>Durch das Entfernen von Wartungsanforderungen und die Außerbetriebnahme von Legacy-PBX-und-Desktop-Smartphones werden die monatlichen Telefondienst Kosten um 20% reduziert. Mit Anrufplänen werden die Office-Arbeitsbereiche vereinfacht, wodurch Contoso seine Aktivitäten erweitern kann, indem neue Offices mit minimalen Telefonkosten im Voraus festgelegt werden.|

<br>

> [!TIP]
> Der folgende Code ist ein Beispiel für einen abgeschlossenen Geschäfts Anwendungsfall für das direkte Routing:
> 
> |         |
> |---------|
> |**Beschreibung des aktuellen Geschäftsprozesses**<br>Die Standard Konfiguration der Office-Arbeitsbereiche von Contoso umfasst ein Desktoptelefon für jeden Schreibtisch. Jedem Mitarbeiter wurde eine direkte Durchwahl (DID)-Telefonnummer zugewiesen. Die Desktoptelefone sind mit einem PBX-System verbunden und über einen SIP-Trunk (Session Initiation Protocol) mit PSTN verbunden. Mitarbeiter können nur Telefonanrufe über ihre zugewiesenen Desktoptelefone tätigen und empfangen.|
> |**Herausforderungen mit vorhandenen Geschäftsprozessen**<br>Die Nutzungsanalyse der Desktoptelefone zeigt, dass nur 10% der Desktoptelefone aktiv verwendet werden, wobei der andere so konfiguriert ist, dass Sie Anrufe an Mobiltelefone weiterleiten oder gleichzeitig an Handys anrufen können. Die Verwaltung des vorhandenen PBX-Systems und zugehöriger Desktoptelefone trägt zu 20% der monatlichen Telefondienst Kosten von Contoso bei.|
> |**Wie diesen Herausforderungen am besten begegnet werden kann**<br>Der SIP Trunk-Anbieter Vertrag wurde kürzlich unterschrieben und wird drei Jahre lang in Kraft sein. Das direkte Routing ermöglicht die Bereitstellung von PSTN-Konnektivität durch den SIP-Trunk-Anbieter und ermöglicht es dem Personal Computer des Benutzers auch, Telefonanrufe über das Datennetzwerk zu empfangen und zu tätigen, indem die native Microsoft Teams-App genutzt wird. Auf diese Weise ist es nicht mehr notwendig, Desktop-Smartphones einzuführen und zu warten, und es wird die Möglichkeit eröffnet, das vorhandene PBX-System abzusetzen, während ein begrenzter SBC-Footprint (Session Border Controller) beibehalten wird.|
> |**Erwartete, messbare Geschäftsergebnisse**<br>Durch das Entfernen von Wartungsanforderungen und die Außerbetriebnahme von Legacy-PBX-und-Desktop-Smartphones werden die monatlichen Telefondienst Kosten um 20% reduziert. Das direkte Routing vereinfacht die Office-Arbeitsbereiche, wodurch Contoso seine Aktivitäten erweitern kann, indem neue Offices mit minimalen Telefonkosten im Voraus eingerichtet werden.|

Um die Projektgrenzen festzulegen, sollten Sie nicht nur Ihre geschäftlichen Anwendungsfälle definieren, sondern auch die Klarheit in den folgenden Fällen unterteilen:

-   **Organisatorischer Bereich:** Die Implementierung von Audiokonferenzen, Anrufplänen oder direktem Routing kann die gesamte Organisation oder nur bestimmte Unternehmenseinheiten umfassen.

-   **Projektzeitachse:** Die bestimmte Zeitachse, die das Projekt ausführen soll.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Entscheidungspunkte|<ul><li>Was sind die Unternehmens-Anwendungsfälle für Audiokonferenzen, die Sie in Ihrer Organisation identifizieren können?</li><li>Was sind alle Geschäfts Anwendungsfälle für Anrufpläne, die Sie in Ihrer Organisation identifizieren können?</li><li>Was sind alle Geschäfts Anwendungsfälle für das direkte Routing, das Sie in Ihrer Organisation identifizieren können?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Dokumentieren Sie alle Business Use Cases für Audiokonferenzen für Ihre Organisation.</li><li>Dokumentieren Sie alle Geschäfts Anwendungsfälle für Anrufpläne für Ihre Organisation.</li><li>Dokumentieren Sie alle Geschäfts Anwendungsfälle für das direkte Routing für Ihre Organisation.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identifizieren der wichtigsten Projektbeteiligten

Zu den im vorherigen Schritt definierten Geschäfts Anwendungsfällen gehören ein organisatorischer Bereich für Audiokonferenzen, Anrufpläne oder die Implementierung des direkten Routings. Auf dieser Grundlage können Sie die umfassende Stakeholder-Matrix ausfüllen, um die richtigen Personen in das Projekt einzubeziehen.

> [!TIP]
> In der folgenden Beispielvorlage für diese Matrix können Sie die Projektbeteiligten dokumentieren.
> 
> |Rolle  |Beschreibung  |Name, Kontaktinformationen, Standort  |
> |---------|---------|---------|
> |Leitender Projektsponsor|<ul><li>Übernehmen Sie die ultimative Autorität und Verantwortlichkeit für das Projekt und die Bereitstellung von Projektzielen.</li><li>Helfen Sie bei der Lösung von Problemen, die vom Projektleiter eskaliert werden.</li><li>Sponsoren Kommunikation innerhalb des Unternehmens über Projektziele.</li><li>Wichtige strategische Entscheidungen treffen.</li><li>Stellen Sie sicher, dass die erforderlichen Ressourcen und das Budget verfügbar sind.</li><li>Lead Quarterly Business Reviews (QBRs)</li><li>Drive Buy-in und Support für Kampagnen zur Sensibilisierungskampagne.</li><li>Als Projekt Sponsor für den Programm Rollout fungieren.</li></ul>|TBA|
> |Projektleiter|<ul><li>Verwalten und leiten des Projektteams</li><li>Koordinieren von Partnern und Arbeitsteams, die am Projekt beteiligt sind</li><li>Sie müssen für die Erstellung und Verwaltung von Projektplänen verantwortlich sein, um quartalsweise Ergebnisse zu erreichen.</li><li>Lösen Sie funktionsübergreifende Probleme.</li><li>Bereitstellen von regelmäßigen Updates für Projektsponsoren</li><li>Integrieren Sie Adoptions Aspekte in den vollständigen Projektplan.</li><li>Führen Sie monatliche Geschäfts-und Betriebs Bewertungen (MBRs), die zu QBRs beitragen.</li></ul>|TBA|
> |Leiter/Architekt für Zusammenarbeit|<ul><li>Führen Sie die von Unternehmensleitern definierte Zusammenarbeitsstrategie aus.</li><li>Analysieren und Auswählen von Zusammenarbeits Produkten, die die Unternehmensziele für das Unternehmen erfüllen</li><li>Design Vorgänge für Collaboration-Produkte.</li><li>Definieren von Betriebs-und Support Modellen</li><li>Beiträge zu monatlichen und Quartals Überprüfungen für Unternehmen.</li></ul>|TBA|
> |Berater|<ul><li>Für Konfigurationsdienste verantwortlich sein</li><li>Tragen Sie zur Gesamt Lösungsarchitektur bei.</li></ul>|TBA|
> |Projektmanager|<ul><li>Entwickeln und Verwalten des Projektplans</li><li>Verwalten Sie Projektergebnisse entsprechend dem Projektplan und dem Budget.</li><li>Aufzeichnen und Verwalten von Projektproblemen, einschließlich Eskalationen</li><li>Führen Sie wöchentliche aufstehende Anrufe durch.</li><li>Sie können mit den Project Executive-Sponsoren Kontakt aufnehmen und Updates für Sie bereitstellen.</li><li>Arbeiten Sie mit dem Architekten zusammen, um den Ansatz der Änderungsverwaltung und Kommunikationspläne zu definieren.</li></ul>|TBA|
> |Spezialist für Change Management/Einführung|<ul><li>Bereitstellen von Eingaben während der Ermittlungsphase in Adoptions-und Schulungsprozesse.</li><li>Nehmen Sie am Einführungsstrategie-Workshop Teil.</li><li>Entwickeln Sie die Strategie für die Einführung, und übernehmen Sie die Verantwortung.</li><li>Entwickeln Sie den Kommunikationsplan, und führen Sie ihn aus.</li><li>Bereitstellen von Schulungen für Benutzer</li><li>Sammeln von Feedback und Durchführen von Umfragen</li></ul>|TBA|
> |Netzwerkleiter|<ul><li>Bereitstellen von Eingaben während der Erkennungsphase im Netzwerkentwurf.</li><li>Teilnehmen an der Planung während des Workshops enVision Phase.</li><li>Koordinieren der Arbeit des Netzwerkteams während der Projektausführung</li></ul>|TBA|
> |Leiter der Sicherheit|<ul><li>Bereitstellen von Eingaben während der Ermittlungsphase in Sicherheitsdesign und-Prozesse.</li><li>Teilnehmen an der Planung während des Workshops enVision Phase.</li><li>Koordinieren der Arbeit des Sicherheitsteams während der Projektausführung</li></ul>|TBA|
> |Telefonieleiter|<ul><li>Bereitstellen von Eingaben während der Erkennungsphase in den Telefonie-Entwurf</li><li>Teilnehmen an der Planung während des Workshops enVision Phase.</li><li>Koordinieren der Arbeit des Telefonie-Teams während der Projektdurchführung</li></ul>|TBA|
> |Desktopleiter|<ul><li>Bereitstellen von Eingaben während der Ermittlungsphase in den Clients und Updateprozess.</li><li>Teilnehmen an der Planung während des enVision-Workshops.</li><li>Koordinieren der Arbeit des Desktop Teams während der Projektausführung</li></ul>|TBA|
> |Support-/Helpdeskleiter|<ul><li>Bereitstellen von Eingaben während der Ermittlungsphase in Betriebs-und Support Modelle</li><li>Teilnehmen an der Planung während des Workshops enVision Phase.</li><li>Teilnehmen an der Planung des Supportmodells</li><li>Koordinieren der Arbeit von Support Teams und Ressourcen während der Projektausführung</li></ul>|TBA|
> |Vertreter der Betriebseinheiten|<ul><li>Tragen Sie zu benutzerbasierten Einführungsleitfäden und Materialien bei.</li><li>Tragen Sie dazu bei, Geschäfts Anwendungsfälle zu überprüfen.</li></ul>|TBA|
> |Bereitstellungsleiter|<ul><li>Sicherstellen, dass die Voraussetzungen für die Bereitstellung erfüllt sind</li><li>Ressourcen für die Teilnahme an den Phasen Aktivitäten an Bord einbinden.</li><li>An Besprechungen teilnehmen, um Berichte über den Bereitstellungsstatus zu überprüfen und vorzubereiten.</li></ul>|TBA|
> |IT-Administratoren|<ul><li>Unterstützen Sie die Testplanung und-Ausführung. Diese Rolle richtet sich an IT-Experten.</li></ul>|TBA|
> |Leiter des Kundendiensts|<ul><li>Seien Sie für den Betrieb der Audiokonferenz-, Anrufpläne oder des Direct Routing-Diensts verantwortlich.</li><li>Besitzen Sie die Audiokonferenzen, Anrufpläne oder Direct Routing-Dienste.</li></ul>|TBA|
> |Qualitätspioniere|<ul><li>Qualität, Zuverlässigkeit und Benutzer Feedback für das Laufwerk.</li><li>Identifizieren Sie qualitätstrends, und führen Sie eine Problembehebung mit den jeweiligen Teams durch.</li><li>Melden Sie sich über das Lenkungskomitee zurück zu Leadership.</li><li>Berichten Sie über Qualität, Zuverlässigkeit und Benutzer Gefühle durch bewerten meines Anrufs und des Netto-Promoters.</li></ul>|TBA|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Entscheidungspunkte|<ul><li>Wer füllt die einzelnen wichtigen Stakeholder-Rollen für Ihre Organisation aus?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Dokumentieren Sie alle wichtigen Stakeholder, und kommunizieren Sie die Zuständigkeiten und Erwartungen der Rolle an jede zugewiesene Person.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definieren von OKRs, KSIs und Risiken

Mit den zusammengestellten Projekt Beteiligten können Sie Geschäfts Anwendungsfälle, den organisatorischen Umfang und Projektzeitpläne in Zielsetzungen und wichtige Ergebnisse (OKRs) übersetzen, und die Measures des Projekterfolgs können als eine Liste der wichtigsten Erfolgsindikatoren (KSIs) definiert werden.

Die vollständige Teilnahme von Projekt Beteiligten an der Definition von OKRs und KSIs ist unerlässlich, um sicherzustellen, dass Sie ein Gefühl des Eigentums empfinden und diese Erfolgskennzahlen den Anforderungen des Unternehmens anpassen.

OKRs enthalten die Ziele, die Sie am Anfang des Projekts festgelegt haben, und Sie definieren messbare Schlüsselergebnisse vierteljährlich. Sie überprüfen die wichtigsten Ergebnisse monatlich, um den Status des Gesamtprojekts zu überwachen und – basierend auf dem Status – die Quartals Pläne nach Bedarf anzupassen.

> [!TIP]
> Im folgenden finden Sie Beispiele für OKRs, die für eine Audiokonferenz-Implementierung relevant sind:
> <br>
> 
> **Vision: Steigern der Produktivität durch Maximierung der Investition in Office 365**
> 
> |Ziele  |Wichtigste Ergebnisse  |zu tun  |
> |---------|---------|---------|
> |Bereitstellen von Audiokonferenzen in Teams gegen Ende des Geschäftsjahres 2018|1. Quartal des Geschäftsjahres 2018: Globale Bereitstellung von Audiokonferenzen in Teams|Ausblick<ul><li>Erfolgsplan erstellen</li><li>Detaillierten Plan für die technische Implementierung erstellen</li></ul><p>Onboarding<ul><li>Erfolgsplan ausführen</li><li>Plan für die technische Implementierung ausführen</li></ul>|
> |Den Legacy-PSTN-Konferenzdienst zur Mitte des Finanzjahres 2018 deaktivieren|2. Quartal des Finanzjahres 2018: Den Legacy-PSTN-Konferenzdienst deaktivieren|Höhere Wertschöpfung erzielen<ul><li>Benutzerengagement verstärken und Übernahme vorantreiben</li><li>Veränderungen vorbereiten und verwalten</li><li>Erfolg messen und teilen und Durchlauf beschleunigen</li>|

<br>

> [!TIP]
> Nachfolgend finden Sie Beispiele für OKRs, die für eine Anruf Plan Implementierung relevant sind:
> <br>
> 
> **Vision: Steigern der Produktivität durch Maximierung der Investition in Office 365**
> 
> |Ziele  |Wichtigste Ergebnisse  |zu tun  |
> |---------|---------|---------|
> |Bereitstellen von Anrufplänen in europäischen Niederlassungen am Ende des Geschäftsjahres 2018|FY18Q3: Bereitstellen von Anrufplänen in London Office|Ausblick<ul><li>Erfolgsplan erstellen</li><li>Detaillierten Plan für die technische Implementierung erstellen</li></ul><p>Onboarding<ul><li>Erfolgsplan ausführen</li><li>Plan für die technische Implementierung ausführen</li></ul>|
> |Decommission Legacy PBX in London Office Ende des Geschäftsjahres 2018|FY18Q4: decommission Legacy PBX in London Office|Höhere Wertschöpfung erzielen<ul><li>Benutzerengagement verstärken und Übernahme vorantreiben</li><li>Veränderungen vorbereiten und verwalten</li><li>Erfolg messen und teilen und Durchlauf beschleunigen</li>|
> 
> [!TIP]
> Nachfolgend finden Sie Beispiele für OKRs, die für eine direkte Routing Implementierung relevant sind:
> <br>
> 
> **Vision: Steigern der Produktivität durch Maximierung der Investition in Office 365**
> 
> |Ziele  |Wichtigste Ergebnisse  |zu tun  |
> |---------|---------|---------|
> |Bereitstellen des direkten Routings in kanadischen Niederlassungen am Ende des Geschäftsjahres 2018|FY18Q3: Bereitstellen des direkten Routings in Toronto Office|Ausblick<ul><li>Erfolgsplan erstellen</li><li>Detaillierten Plan für die technische Implementierung erstellen</li></ul><p>Onboarding<ul><li>Erfolgsplan ausführen</li><li>Plan für die technische Implementierung ausführen</li></ul>|
> |Decommission Legacy PBX in Toronto Office bis Ende des Geschäftsjahres 2018|FY18Q4: decommission Legacy PBX in Toronto Office|Höhere Wertschöpfung erzielen<ul><li>Benutzerengagement verstärken und Übernahme vorantreiben</li><li>Veränderungen vorbereiten und verwalten</li><li>Erfolg messen und teilen und Durchlauf beschleunigen</li>|

<br>

KSIs misst die Qualität und den Erfolg der wichtigsten Ergebnisse und ergänzt den binären Charakter von OKRs (erreicht oder nicht erreicht), indem er gute und/oder schlechte Ergebnisse beschreibt.

Wenn Sie KSIs definieren, empfehlen wir, dass Sie "spezifische, messbare, beschreibbare, realistische, zeitbezogene" (Smart-) Kriterien verwenden:

-   Spezifisch: Ziel eines bestimmten Bereichs zur Verbesserung

-   Messbar: quantifizieren oder zumindest einen Indikator für Fortschritt vorschlagen

-   Zugeordnet: Geben Sie an, wer dies tun soll

-   Realistisch: Geben Sie an, welche Ergebnisse realistischerweise erreicht werden können, wenn verfügbare Ressourcen vorhanden sind.

-   Zeit bezogen: Geben Sie an, wann die Ergebnisse erreicht werden können.

> [!TIP]
> Im folgenden Beispiel sehen Sie für dieses Projekt relevante wichtige Erfolgsindikatoren:
> 
> |Typ  |Fragen und Kriterien im Zusammenhang mit den wichtigen Erfolgsindikatoren  |Messmethode  |Erfolgskriterien  |Bemessungszeitpunkt  |Verantwortlich  |
> |---------|---------|---------|---------|---------|---------|
> |Verwendung/Einführung|Anrufqualität entspricht der vorherigen Lösung oder übertrifft diese|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach der Aktivierung und vierteljährlich|IT-Team|
> |Verwendung/Einführung|Microsoft Teams hat den Kommunikationsprozess vereinfacht.|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach der Aktivierung und vierteljährlich|Change Management-Team|
> |Verwendung/Einführung|Aktive Verwendung der Lösung durch die Benutzer|Office 365-Berichte, Anrufqualitäts-Dashboard|80 % der Benutzer sind täglich aktiv|Täglich|Change Management-Team|
> |Verwendung/Qualität|Prozentsatz der Anrufe/Konferenzen mit schlechter Qualität sollte verringert werden|Anrufqualitäts-Dashboard|< 5 % Anrufe mit schlechter Qualität pro Monat|Täglich|IT-Team|
> |Verwendung/Support|Ich weiß, wo ich technischen Support erhalte|Umfrage|Zustimmung oder starke Zustimmung bei 90% der Benutzer|Nach der Aktivierung und vierteljährlich|Change Management-Team|
> |Verwendung/Support|Ich bin zufrieden mit der Qualität des technischen Supports|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach jedem Vorfall|IT-Team|
> |Finanzen|Weniger Minuten mit Legacy-Konferenzlösung|Finanzsystem|Definierte Rendite erzielen|Basierend auf Rendite|Change Management-Team|

Sie müssen Geschäftsrisiken im Rahmen dieser Übung ermitteln und einen Minderungsplan für jedes erkannte Risiko definieren. Diese Informationen können in ein risikoregister aufgenommen werden.

> [!TIP]
> Ihr risikoregister kann im folgenden Beispiel dokumentiert werden:
> 
> |Risiko  |Wahrscheinlichkeit  |Auswirkungen  |Gesamt  |Risikominderungsplan  |
> |---------|---------|---------|---------|---------|
> |Bei der bevorstehenden Fusion werden bis zu 1.000 Personen dazukommen|Hoch|Hoch|Hoch|<ul><li>Erstellen Sie für verbundene Unternehmen ein separates okr, das für eigene Projektphasen gilt (enVision, Onboard, Drive Value).</li><li>Diese OKRs nicht in vorhandene OKRs einbeziehen</li></ul>|
> |Die Portierung von Telefonnummern verzögert den Projektabschluss.|Hoch|Hoch|Hoch|<ul><li>Alle Informationen vorbereiten, die erforderlich sind, um die Portierung von Telefonnummern vorzeitig zu unterstützen (Kundendienst Aufzeichnung, Abrechnungsdetails, Autorisierungs Bescheid)</li><li>Anpassen der projektzeitachse an die Bearbeitungszeit der Port Ausführung für Telefonnummern</li><li>Teilen Sie den externen Teilnehmern die neuen Einwahlkonferenznummern mit.</li><li>Verwenden temporärer Telefonnummern mit Manipulation der Rufnummernanzeige</li></ul>|
> |Geplante Umgestaltung des Netzwerks|Hoch|Mittel|Mittel|<ul><li>Bevor Sie Teams als moderne Kommunikations-und Zusammenarbeitsplattform implementieren, führen Sie eine Netzwerk Bereitschaftsbewertung für Websites im Projektumfang durch.</li></ul>|
> |SBC-Konfiguration|Hoch|Hoch|Hoch|<ul><li>Bevor Sie Teams als Ersatz für die vorhandene Telefonanlage implementieren, stellen Sie sicher, dass Sie alle SBC-Konfigurationsanforderungen erfüllen können.</li><li>Stellen Sie sicher, dass die SBC-Supportressourcen über die richtige Fertigkeit verfügen, um SBC für das direkte Routing zu konfigurieren.</li></ul>|

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Entscheidungspunkte|<ul><li>Was sind ihre Organisationen&#39;s OKRs und KSIs?</li><li>Welche Risiken sind für die Implementierung von Audiokonferenzen in Ihrer Organisation relevant? Was sind die Abschwächungs Pläne für die identifizierten Risiken?</li><li>Welche Risiken haben Sie für die Implementierung von Anrufplänen in Ihrer Organisation als relevant identifiziert? Was sind die Abschwächungs Pläne für die identifizierten Risiken?</li><li>Welche Risiken sind für die Implementierung des direkten Routings in Ihrer Organisation relevant? Was sind die Abschwächungs Pläne für die identifizierten Risiken?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Dokumentieren Sie die OKRs und KSIs, und legen Sie das risikoregister fest.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Einrichten eines Lenkungsausschusses

Ein Lenkungsausschuss ist eine übergeordnete Gruppe von wichtigen Stakeholdern und Projektleitern, die zusammengebracht wurden, um ein Projekt oder Programm zu den definierten geschäftlichen Ergebnissen zu führen. Das Lenkungskomitee ist nicht direkt für ** die Bereitstellung des Projekts verantwortlich, sondern vielmehr, *was* das Projekt dem Unternehmen liefert.

Für jedes Projekt ist eine vereinbarte Vision und Charta erforderlich. Um die gewünschten Ergebnisse aus dem Projekt zu liefern, muss die Vision klar definiert sein, und Sie muss überwacht und gewartet werden. Dieser wird in die Zuständigkeit des Lenkungsausschusses gestellt: um Entscheidungen zu treffen, Ratschläge zu erteilen, strategisches beaufsichtigen zu führen, als Fürsprecher für die Organisation für die Initiativen des Projekts zu fungieren und – falls erforderlich – Blocker zu entfernen.

Ihre Organisation sollte die Bildung des Lenkungsausschusses erheblich überdenken. Der Ausschuss muss sicherstellen, dass das Projekt die von Ihnen festgelegten geschäftlichen Ziele für das Vorantreiben von Änderungen in der gesamten Organisation erreicht, sich regelmäßig trifft, um den aktuellen Puls des Projekts zu besprechen, und die Blockierung von Hindernissen, die auf der Möglichkeit.

Der Ausschuss sollte seine Charta definieren, um einige der wichtigsten Ziele einzubeziehen:

-   Halten Sie eine starke Abstimmung zwischen dem Projektteam und dem Executive-Sponsor oder der Führungskraft.

-   Geben Sie dem Executive-Sponsor oder der Führungskraft einen Einblick in den Projektstatus.

-   Ermöglichen Sie es dem Executive-Sponsor oder dem Executive Leadership-Team, Richtung und Eingabe für das Projekt bereitzustellen, und stellen Sie sicher, dass es den übergeordneten Geschäftszielen entspricht, indem Sie Projektpläne, objektive Schlüsselergebnisse (OKRs) und andere Projektaktivitäten anpassen.

Das Lenkungskomitee tagt zu einem wiederkehrenden Intervall während der gesamten Laufzeit eines Projekts, um die Ausrichtung zwischen organisatorischer Führung und Projektteam zu gewährleisten. Diese kritische Besprechung stellt sicher, dass die Richtung des Projekts die vollständige Unterstützung durch Leadership hat, und es werden alle von der Führungskraft bereitgestellten Feedbacks in das Projekt integriert, um den Erfolg zu steigern. Der Ausschuss verwendet diese Besprechungen, um Einblicke in den Projektstatus zu erhalten und:

-   Vereinbaren Sie Geschäftsergebnisse, die sich an den Fall des Unternehmens orientieren, und stellen Sie sicher, dass das Projekt auf die bereitstellungdieser Ergebnisse ausgerichtet ist.

-   Überprüfen und genehmigen Sie das Projekt für die Genauigkeit und Einhaltung des Geschäftsfalls.

-   Überprüfen und überprüfen Sie die am Geschäftsfall vorgenommenen Änderungen, die sich auf definierte Ergebnisse auswirken können.

-   Treffen Sie strategische Entscheidungen bezüglich der Priorisierung von Projektergebnissen, und genehmigen Sie Zwischenergebnisse.

-   Ermitteln, managen und verringern Sie Lücken, Risiken und Probleme, bei denen zusätzlicher Einfluss des Ausschusses erforderlich ist.

-   Sammeln Sie Unterstützung des Executive-Sponsors oder des Executive Leadership Teams für Probleme, die Eskalation erfordern, priorisieren und Konflikte zwischen Stakeholder-Geschäftseinheiten beheben. 

-   Bereitstellen von formellem Feedback und Empfehlungen für Führungskräfte, das Change Advisory Board oder andere Geschäfts-und IT-Stakeholder, sofern zutreffend.

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob ein Lenkungsausschuss für Ihre Organisation erforderlich ist.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Mitglieder des Lenkungsausschusses ermitteln.</li><li>Planen von Sitzungen des Lenkungsausschusses</li><li>Vorbereiten der Sitzungen des Lenkungsausschusses</li><li>Sitzungen des Lenkungsausschusses abhalten.</li><li>Ergreifen von Maßnahmen auf der Grundlage des Inputs der Sitzung des Lenkungsausschusses</li></ul>|

Weitere detaillierte Anleitungen zum Betrieb eines ordnungsgemäßen Lenkungsausschusses finden Sie im Leitfaden für das [Lenkungskomitee](envision-steering-committee-complete-guide.md).

<!--ENDOFSECTION-->