---
title: Audiokonferenzen, Anrufpläne oder direktes Routing
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 06/07/2018
ms.topic: conceptual
audience: admin
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Definieren des Erfolgs für die Bereitstellung von Audiokonferenzen, Telefonsystem mit Anrufplänen oder Telefonsystem direktes Routing für Ihre Organisation.
ms.collection:
- M365-voice
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 4e669e0454f65ef4d3d5ecc0b4832b33201d2703
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011759"
---
# <a name="define-my-success"></a>Definieren der Erfolgskriterien

Dieser Artikel enthält eine Übersicht über die Anforderungen für die Definition des Erfolgs für die Bereitstellung von Audiokonferenzen, Telefonsystem mit Anrufplänen oder Telefonsystem Direct-Routing für Ihre Organisation. Wenn Sie richtig definieren, wie Der Erfolg aussieht, können Sie die Ergebnisse messen, während Sie die Bereitstellungsbereitstellung fortschreitet, und sicherstellen, dass die Ergebnisse, die Sie erzielen, die von Ihnen gesuchten Ergebnisse sind.

<!--ENDOFSECTION-->

**Audiokonferenzen** bieten Organisationen zusätzliche Einstiegspunkte für alle Besprechungen (ad hoc oder geplant), indem Sie es den Besprechungsteilnehmern ermöglichen, über ein festgeschaltetes Telefonnetz (PSTN) durch Einwählen über ein herkömmliches Festnetztelefon, eine Private Branch Exchange (PBX) oder ein Mobiltelefon teilzunehmen. Dies ist nützlich, wenn sich der Organisator oder die Teilnehmer nicht vor einem Computer befinden oder wenn Datenverbindungen nicht verfügbar sind oder zu unzuverlässig sind, um Sprachkommunikation zu unterstützen – z. B. in einem Remotebereich mit geringer Reichweite mobiler Daten, in Verbindung mit einem kostenlosen, öffentlichen Wi-Fi-Dienst mit begrenzter Bandbreite oder wenn sich Besprechungsteilnehmer lieber in die Besprechung einwählen möchten, indem sie einen Telefonieendpunkt verwenden, auf den sie schnell zugreifen können.

Telefonsystem Anrufplänen **("Anrufpläne")** gibt Unternehmen die Möglichkeit, ihren Arbeitsplatz zu modernisieren, indem Benutzer geschäftliche Telefonanrufe von ihren Computern und mobilen Geräten aus anrufen können. Eine arbeitsbasierte Arbeit kann Teil einer Reihe von Szenarien sein – eine aktivitätsbasierte Arbeitsimplementierung, eine größere Büroverzugslösung, eine Office-Fit-out-Aktualisierung, das Ende einer älteren PBX-Lösung, das Ende eines Vertrags für PSTN-Dienstanbieter und so weiter. Mit Anrufplänen erleichtert Microsoft die Verbindung mit dem PSTN.

**Telefonsystem Direct Routing ("Direct Routing")** bietet Organisationen dieselben Vorteile wie oben für Anrufpläne, mit dem Ausnahme, dass die PSTN-Konnektivität durch einen Drittanbieter statt durch Microsoft vereinfacht wird. Dies ermöglicht die Bereitstellung in Ländern, in denen Anrufpläne nicht verfügbar sind, oder in Bereitstellungen, in denen ein vorhandener PSTN-Vertrag für Dienstanbieter beibehalten oder eine Interoperabilität mit bestimmten lokalen Systemen erforderlich ist. Ein weiteres Szenario, das direct Routing berücksichtigen sollte, ist die Interoperabilität des Telefoniesystems. Während Benutzer in Ihrer Telefonanlage zu Anrufen Teams, verbleiben einige Benutzer möglicherweise weiterhin mit älteren PBXs. Das direkte Routing ermöglicht die Koexistenz beider Verwendungsfälle. Der Anrufdatenverkehr zwischen den Benutzern in älteren Systemen und Teams Benutzer bleiben innerhalb der Organisation.

<!--ENDOFSECTION-->

## <a name="define-business-use-cases-for-audio-conferencing-calling-plans-or-direct-routing"></a>Definieren geschäftlicher Nutzungsfälle für Audiokonferenzen, Anrufpläne oder direktes Routing

Zunächst müssen die wichtigsten Projektbeteiligten Geschäftsnutzungsfälle definieren, die die Implementierung von Audiokonferenzen, Anrufplänen oder direktem Routing unterstützen.

Geschäfts-Use-Cases sollen erwartete und messbare Unternehmensergebnisse definieren und dokumentieren sowie die folgenden Punkte umfassen:

-   Beschreibung des aktuellen Geschäftsprozesses

-   Herausforderungen beim vorhandenen Geschäftsprozess

-   Wie diese Herausforderungen mithilfe der Technologie bewältigt werden können

-   Die erwarteten und messbaren Geschäftsergebnisse, die durch die Bewältigung dieser Herausforderungen erzielt werden können

> [!TIP]
> Es folgt ein Beispiel für einen abgeschlossenen Geschäfts-Use-Fall für Audiokonferenzen:
> 
> |         |
> |---------|
> |**Beschreibung des aktuellen Geschäftsprozesses**<br>Für interne Besprechungen und Besprechungen mit Dritten nutzt Contoso derzeit die von etablierten lokalen Telefonanbietern bereitgestellten PSTN-Konferenzdienste, die im Minutentakt abgerechnet werden.|
> |**Herausforderungen mit vorhandenen Geschäftsprozessen**<br>Contoso gibt pro Jahr ca. eine Million USD für den aktuellen PSTN-Konferenzdienst aus, mit 75 % der Kosten für interne Besprechungen. Die Verwendung herkömmlicher Telefonieendpunkte für die Teilnahme an Besprechungen, die vom PSTN-Konferenzdienst gehostet werden, ist nicht mit dem Plan der Organisation abgestimmt, Teams als moderne Kommunikations- und Zusammenarbeitsplattform zu übernehmen.|
> |**Wie diesen Herausforderungen am besten begegnet werden kann**<br>Mit der Einführung von Microsoft Teams als moderne Kommunikations- und Zusammenarbeitsplattform wird erwartet, dass interne Benutzer in erster Linie an Besprechungen teilnehmen, indem sie ihre PCs mit optimierten Headsets und Besprechungsraumgeräten verwenden. Der Audiokonferenzdienst steht für externe Teilnehmer oder für Situationen zur Verfügung, in denen die Verwendung von PC-Audio für die internen Teilnehmer nicht vorteilhaft ist.|
> |**Erwartete, messbare Geschäftsergebnisse**<br>Der Wechsel Teams als moderne Kommunikations- und Zusammenarbeitsplattform in Kombination mit dem Audiokonferenzdienst verringert die Kosten für die Bereitstellung des PSTN-Konferenzdiensts erheblich.|

<br>

> [!TIP]
> Es folgt ein Beispiel für einen abgeschlossenen Geschäfts-Use-Fall für Anrufpläne:
> 
> |         |
> |---------|
> |**Beschreibung des aktuellen Geschäftsprozesses**<br>Die Standardkonfiguration der Büroarbeitsräume von Contoso umfasst ein Desktoptelefon für jeden Schreibtisch. Jeder Mitarbeiter hat eine Direktwahlnummer (DID) erhalten. Die Desktoptelefone sind mit einem PBX-System verbunden und über einen SIP-Trunk (Session Initiation Protocol) mit dem PSTN verbunden. Mitarbeiter können Telefonanrufe nur auf ihren zugewiesenen Festnetztelefonen telefonieren und empfangen.|
> |**Herausforderungen mit vorhandenen Geschäftsprozessen**<br>Die Verwendungsanalyse der Desktoptelefone zeigt, dass nur 10 % der Desktoptelefone aktiv verwendet werden, während die anderen so konfiguriert sind, dass Anrufe an Mobiltelefone weitergeleitet oder gleichzeitig telefoniert wird. Die Pflege des vorhandenen PBX-Systems und der zugehörigen Desktoptelefone trägt zu 20 % der monatlichen Telefoniedienstkosten von Contoso bei.|
> |**Wie diesen Herausforderungen am besten begegnet werden kann**<br>Anrufpläne ermöglichen es dem PC eines Benutzers, Telefonanrufe über das Datennetzwerk zu empfangen und zu platzieren, indem die systemeigene Microsoft Teams-App verwendet wird. Dadurch entferne ich das Rollout und die Wartung von Desktoptelefonen und eröffnet die Möglichkeit, das vorhandene PBX-System außer Betrieb zu nehmen, da der Telefondienst über die Cloud über das Netzwerk ohne Abhängigkeit von einem herkömmlichen Telefonsystem geliefert werden kann.|
> |**Erwartete, messbare Geschäftsergebnisse**<br>Durch das Entfernen von Wartungsanforderungen und die Außerbetriebnahme älterer Festnetztelefone und Desktoptelefone werden die monatlichen Ausgaben für Telefoniedienste um 20 % reduziert. Anrufpläne vereinfachen Office-Arbeitsbereiche und ermöglichen Contoso, den Betrieb zu erweitern, indem neue Niederlassungen mit minimalen Vorab-Telefoniekosten eingerichtet werden.|

<br>

> [!TIP]
> Nachfolgend finden Sie ein Beispiel für einen abgeschlossenen Geschäfts-Use-Fall für Direct-Routing:
> 
> |         |
> |---------|
> |**Beschreibung des aktuellen Geschäftsprozesses**<br>Die Standardkonfiguration der Büroarbeitsräume von Contoso umfasst ein Desktoptelefon für jeden Schreibtisch. Jeder Mitarbeiter hat eine Direktwahlnummer (DID) erhalten. Die Desktoptelefone sind mit einem PBX-System verbunden und über einen SIP-Trunk (Session Initiation Protocol) mit dem PSTN verbunden. Mitarbeiter können Telefonanrufe nur auf ihren zugewiesenen Festnetztelefonen telefonieren und empfangen.|
> |**Herausforderungen mit vorhandenen Geschäftsprozessen**<br>Die Verwendungsanalyse der Desktoptelefone zeigt, dass nur 10 % der Desktoptelefone aktiv verwendet werden, während die anderen so konfiguriert sind, dass Anrufe an Mobiltelefone weitergeleitet oder gleichzeitig telefoniert wird. Die Pflege des vorhandenen PBX-Systems und der zugehörigen Desktoptelefone trägt zu 20 % der monatlichen Telefoniedienstkosten von Contoso bei.|
> |**Wie diesen Herausforderungen am besten begegnet werden kann**<br>Der SIP-Trunkanbieter-Vertrag wurde kürzlich unterzeichnet und wird drei Jahre lang verwendet. Mit Direct Routing kann die PSTN-Verbindung vom SIP-Trunkanbieter bereitgestellt werden, und der PC eines Benutzers kann Telefonanrufe über das Datennetzwerk empfangen und über das Datennetzwerk ab telefonieren, indem die native Microsoft Teams-App verwendet wird. Dadurch entferne ich das Rollout und die Wartung von Desktoptelefonen und eröffnet die Möglichkeit, das vorhandene PBX-System außer Betrieb zu nehmen, während ein begrenzter Speicherbedarf für den lokalen Session Border Controller (SBC) beibehalten wird.|
> |**Erwartete, messbare Geschäftsergebnisse**<br>Durch das Entfernen von Wartungsanforderungen und die Außerbetriebnahme älterer Festnetztelefone und Desktoptelefone werden die monatlichen Ausgaben für Telefoniedienste um 20 % reduziert. Direct Routing vereinfacht Office-Arbeitsbereiche und ermöglicht Contoso, seinen Betrieb zu erweitern, indem neue Niederlassungen mit minimalen Vorab-Telefoniekosten eingerichtet werden.|

Neben der Definition ihrer geschäftlichen Nutzungsfälle sollten Sie zum Festlegen der Projektgrenzen für Klarheit sorgen:

-   **Organisationsumfang:** Die Implementierung von Audiokonferenzen, Anrufplänen oder Direct Routing umfasst möglicherweise die gesamte Organisation oder nur bestimmte Geschäftseinheiten.

-   **Project Zeitachse:** Die zeitspezifische Zeitachse, die das Projekt ausführen wird.

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> |Entscheidungspunkte|<ul><li>Welche geschäftlichen Nutzungsfälle für Audiokonferenzen können Sie in Ihrer Organisation identifizieren?</li><li>Welche geschäftlichen Nutzungsfälle für Anrufpläne können Sie in Ihrer Organisation identifizieren?</li><li>Welche geschäftlichen Einsatzfälle für Direct-Routing können Sie in Ihrer Organisation identifizieren?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Dokumentieren Sie alle geschäftlichen Nutzungsfälle für Audiokonferenzen für Ihre Organisation.</li><li>Dokumentieren Sie alle geschäftlichen Nutzungsfälle für Anrufpläne für Ihre Organisation.</li><li>Dokumentieren Sie alle geschäftlichen Nutzungsfälle für Direct-Routing für Ihre Organisation.</li></ul>|

<!--ENDOFSECTION-->

## <a name="identify-key-stakeholders"></a>Identifizieren der wichtigsten Projektbeteiligten

Die im vorherigen Schritt definierten Geschäftsnutzungsfälle umfassen einen Organisationsumfang für die Implementierung von Audiokonferenzen, Anrufplänen oder Direct Routing. Auf dieser Grundlage können Sie die umfassende Projektbeteiligtenmatrix vervollständigen, um die richtigen Personen zur Einbeziehung in das Projekt mit in das Projekt zu nehmen.

> [!TIP]
> In der folgenden Beispielvorlage für diese Matrix können Sie die Projektbeteiligten dokumentieren.
> 
> |Rolle  |Beschreibung  |Name, Kontaktinformationen, Standort  |
> |---------|---------|---------|
> |Leitender Projektsponsor|<ul><li>Übernehmen Sie letztendlich Autorität und Verantwortlichkeit für das Projekt und die Lieferung von Projektzielen.</li><li>Helfen Sie bei der Lösung von Problemen, die vom Project Lead eskaliert wurden.</li><li>Kommunikation von Sponsoren innerhalb des Unternehmens zu Projektzielen.</li><li>Treffen Sie wichtige strategische Entscheidungen.</li><li>Stellen Sie sicher, dass erforderliche Ressourcen und erforderliche Budgets verfügbar sind.</li><li>Führen Sie vierteljährliche Geschäftsüberprüfungen durch.</li><li>Fördern Sie den Kauf und die Unterstützung von Informationskampagnen.</li><li>Dient als Project Sponsor für das Programmrollout.</li></ul>|TBA|
> |Projektleiter|<ul><li>Verwalten und führen Sie das Projektteam.</li><li>Koordinieren Sie die am Projekt beteiligten Partner und Arbeitsteams.</li><li>Seien Sie für das Erstellen und Verwalten von Projektplänen zur Berücksichtigung der Vierteljährlichen Hauptergebnisse buchbar.</li><li>Lösen sie funktionsübergreifende Probleme.</li><li>Stellen Sie regelmäßig Updates für Projektsponsoren zur Verfügung.</li><li>Integrieren Sie Übernahmeaspekte in den Projektplan.</li><li>Führen Sie monatliche Geschäfts- und Betriebsüberprüfungen durch, und tragen Sie zu QBRs bei.</li></ul>|TBA|
> |Leiter/Architekt für Zusammenarbeit|<ul><li>Ausführung gemäß der von den Unternehmensleitern definierten Zusammenarbeitsstrategie.</li><li>Analysieren und wählen Sie Produkte für die Zusammenarbeit aus, die Geschäftsziele für das Unternehmen erfüllen.</li><li>Designvorgänge für Produkte für die Zusammenarbeit.</li><li>Definieren sie Vorgangs- und Supportmodelle.</li><li>Tragen Sie zu den monatlichen und vierteljährlichen Geschäftsrezensionen bei.</li></ul>|TBA|
> |Berater|<ul><li>Verantwortlich für Konfigurationsdienste</li><li>Tragen Sie zur Gesamtarchitektur der Lösung bei.</li></ul>|TBA|
> |Projektmanager|<ul><li>Entwickeln und pflegen Sie den Projektplan.</li><li>Verwalten Sie Projektlieferablen im Einklang mit dem Projektplan und dem Budget.</li><li>Aufzeichnen und Verwalten von Projektproblemen, einschließlich eskalieren.</li><li>Führen Sie wöchentliche Aufstandsanrufe durch.</li><li>Sorgen Sie für eine Zusammenarbeit mit Projektmanagementsponsoren und stellen Sie Updates für diese zur Verfügung.</li><li>Arbeiten Sie mit der Architektur zusammen, um den Change Management-Ansatz und Kommunikationspläne zu definieren.</li></ul>|TBA|
> |Spezialist für Change Management/Einführung|<ul><li>Geben Sie während der Ermittlungsphase Input in Die Verbreitungs- und Schulungsprozesse ein.</li><li>Nehmen Sie am Workshop zur Einführungsstrategie teil.</li><li>Entwickeln Sie die Übernahmestrategie, und übernehmen Sie deren Verantwortung.</li><li>Entwickeln sie den Kommunikationsplan, und führen Sie den Plan aus.</li><li>Stellen Sie Schulungen für Benutzer vor.</li><li>Sammeln Sie Feedback, und führen Sie Umfragen durch.</li></ul>|TBA|
> |Netzwerkleiter|<ul><li>Geben Sie während der Ermittlungsphase Eingaben in den Netzwerkentwurf ein.</li><li>Nehmen Sie an der Planung während des Envision-Phasenworkshops teil.</li><li>Koordinieren Sie die Arbeit des Netzwerkteams während der Projektausführung.</li></ul>|TBA|
> |Leiter der Sicherheit|<ul><li>Geben Sie während der Ermittlungsphase Informationen zum Sicherheitsentwurf und zu den Prozessen an.</li><li>Nehmen Sie an der Planung während des Envision-Phasenworkshops teil.</li><li>Koordinieren Sie die Arbeit des Sicherheitsteams während der Projektausführung.</li></ul>|TBA|
> |Telefonieleiter|<ul><li>Geben Sie während der Ermittlungsphase Informationen in den Telefonieentwurf ein.</li><li>Nehmen Sie an der Planung während des Envision-Phasenworkshops teil.</li><li>Koordinieren Sie die Arbeit des Telefonieteams während der Projektausführung.</li></ul>|TBA|
> |Desktopleiter|<ul><li>Geben Sie während der Ermittlungsphase Eingaben in die Clients ein, und aktualisieren Sie den Prozess.</li><li>Beteiligen Sie sich an der Planung während des Envision-Workshop.</li><li>Koordinieren Sie die Arbeit des Desktopteams während der Projektausführung.</li></ul>|TBA|
> |Support-/Helpdeskleiter|<ul><li>Geben Sie während der Ermittlungsphase Informationen zu Betriebs- und Supportmodellen an.</li><li>Nehmen Sie an der Planung während des Envision-Phasenworkshops teil.</li><li>Nehmen Sie an der Planung von Supportmodellen teil.</li><li>Koordinieren Sie die Arbeit von Supportteams und Ressourcen während der Projektausführung.</li></ul>|TBA|
> |Vertreter der Betriebseinheiten|<ul><li>Tragen Sie zu benutzerbasierten Einführungshandbüchern und Materialien bei.</li><li>Sie können zu geschäftlichen Nutzungsfällen beitragen und diese überprüfen.</li></ul>|TBA|
> |Bereitstellungsleiter|<ul><li>Stellen Sie sicher, dass die Bereitstellungsvoraussetzungen erfüllt sind.</li><li>Engagieren sie Ressourcen, um an den Aktivitäten in der Onboard-Phase beteiligt zu sein.</li><li>Nehmen Sie an Besprechungen teil, um Berichte zum Bereitstellungsstatus zu überprüfen und vorzubereiten.</li></ul>|TBA|
> |IT-Administratoren|<ul><li>Unterstützen Sie die Testplanung und -ausführung. Diese Rolle ist für IT-Profis.</li></ul>|TBA|
> |Leiter des Kundendiensts|<ul><li>Verantwortlich für den Betrieb der Audiokonferenzen, Anrufpläne oder des Direct Routing-Diensts.</li><li>Besitzen Sie den Audiokonferenz-, Anrufplan- oder Direct-Routingdienst.</li></ul>|TBA|
> |Qualitätspioniere|<ul><li>Laufwerkqualität, Zuverlässigkeit und Benutzerfeedback.</li><li>Identifizieren Sie Qualitätstrends, und verbessern Sie die Wartung mit den jeweiligen Teams.</li><li>Melden Sie den Bericht über das Lenkungsgremium zurück an die Führungskräfte.</li><li>Berichten Sie über Qualität, Zuverlässigkeit und Benutzerstimmung über "Meinen Anruf bewerten" und Net Promoter Score.</li></ul>|TBA|

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Entscheidungspunkte|<ul><li>Wer wird die Rolle der einzelnen Hauptbeteiligten für Ihre Organisation erfüllt?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Dokumentieren Sie alle wichtigen Projektbeteiligten, und teilen Sie den einzelnen zugewiesenen Personen die Verantwortlichkeiten und Erwartungen an die Rolle mit.</li></ul>|

<!--ENDOFSECTION-->

## <a name="define-okrs-ksis-and-risks"></a>Definieren von OKRs, KSIs und Risiken

Wenn die Projektbeteiligten zusammengestellt sind, können Sie Geschäfts-Use-Cases, Organisationsumfang und Projektzeitachsen in Ziele und Wichtige Ergebnisse (OKRs) übersetzen, und die Measures für den Projekterfolg können als eine Liste der wichtigsten Erfolgsindikatoren (Key Success Indicators, KSIs) definiert werden.

Die vollständige Beteiligung der Projektbeteiligten an der Definition von OKRs und KSIs ist von wesentlicher Bedeutung, um sicherzustellen, dass sie das Gefühl der Besitzrechte haben und diese Erfolgsmaßnahmen an die geschäftlichen Anforderungen der Organisation anpassen können.

OKRs enthalten die Ziele, die Sie zu Projektbeginn festgelegt haben, und Sie definieren auf quartalsweise messbare wichtige Ergebnisse. Sie überprüfen die wichtigsten Ergebnisse monatlich, um den Status des Gesamtprojekts nachverfolgt zu werden, und passen die Quartalspläne basierend auf dem Fortschritt nach Bedarf an.

> [!TIP]
> Beispiele für okRs, die für eine Audiokonferenzimplementierung relevant sind, finden Sie unten:
> <br>
> 
> **Vision: Steigerung der Produktivität durch Maximierung Microsoft 365 oder Office 365 Investition**
> 
> |Ziele  |Wichtige Ergebnisse  |Zu tun  |
> |---------|---------|---------|
> |Bereitstellen von Audiokonferenzen in Teams gegen Ende des Geschäftsjahres 2018|1. Quartal des Geschäftsjahres 2018: Globale Bereitstellung von Audiokonferenzen in Teams|Ausblick<ul><li>Erfolgsplan erstellen</li><li>Detaillierten Plan für die technische Implementierung erstellen</li></ul><p>Onboarding<ul><li>Erfolgsplan ausführen</li><li>Plan für die technische Implementierung ausführen</li></ul>|
> |Den Legacy-PSTN-Konferenzdienst zur Mitte des Finanzjahres 2018 deaktivieren|2. Quartal des Finanzjahres 2018: Den Legacy-PSTN-Konferenzdienst deaktivieren|Höhere Wertschöpfung erzielen<ul><li>Benutzerengagement verstärken und Übernahme vorantreiben</li><li>Veränderungen vorbereiten und verwalten</li><li>Erfolg messen und teilen und Durchlauf beschleunigen</li>|

<br>

> [!TIP]
> Beispiele für OKRs, die für eine Anrufplanimplementierung relevant sind, finden Sie unten:
> <br>
> 
> **Vision: Steigerung der Produktivität durch Maximierung Microsoft 365 oder Office 365 Investition**
> 
> |Ziele  |Wichtige Ergebnisse  |Zu tun  |
> |---------|---------|---------|
> |Bereitstellen von Anrufplänen in europäischen Zweigstellen bis Zum Ende des Geschäftsjahrs 2018|FY18Q3: Bereitstellen von Anrufplänen im Büro in London|Ausblick<ul><li>Erfolgsplan erstellen</li><li>Detaillierten Plan für die technische Implementierung erstellen</li></ul><p>Onboarding<ul><li>Erfolgsplan ausführen</li><li>Plan für die technische Implementierung ausführen</li></ul>|
> |Außerbetriebnahme der alten Telefonanlage in London bis Ende des Geschäftsjahrs 2018|FY18Q4: Außerbetriebnahme einer älteren Telefonanlage in London|Höhere Wertschöpfung erzielen<ul><li>Benutzerengagement verstärken und Übernahme vorantreiben</li><li>Veränderungen vorbereiten und verwalten</li><li>Erfolg messen und teilen und Durchlauf beschleunigen</li>|
> 
> [!TIP]
> Beispiele für okRs, die für eine Direct Routing-Implementierung relevant sind, finden Sie unten:
> <br>
> 
> **Vision: Steigerung der Produktivität durch Maximierung Microsoft 365 oder Office 365 Investition**
> 
> |Ziele  |Wichtige Ergebnisse  |Zu tun  |
> |---------|---------|---------|
> |Bereitstellen von Direct Routing in kanadischen Zweigstellen bis zum Ende des Geschäftsjahrs 2018|FY18Q3: Bereitstellen von Direct Routing in Toronto|Ausblick<ul><li>Erfolgsplan erstellen</li><li>Detaillierten Plan für die technische Implementierung erstellen</li></ul><p>Onboarding<ul><li>Erfolgsplan ausführen</li><li>Plan für die technische Implementierung ausführen</li></ul>|
> |Außerbetriebnahme der alten Telefonanlage in Toronto bis Ende des Geschäftsjahrs 2018|FY18Q4: Außerbetriebnahme einer älteren Telefonanlage in Toronto|Höhere Wertschöpfung erzielen<ul><li>Benutzerengagement verstärken und Übernahme vorantreiben</li><li>Veränderungen vorbereiten und verwalten</li><li>Erfolg messen und teilen und Durchlauf beschleunigen</li>|

<br>

KSIs messen die Qualität und den Erfolg der wichtigsten Ergebnisse und ergänzen die binäre Natur von OKRs (erzielt oder nicht erzielt), indem gute und/oder schlechte Ergebnisse detailliert beschrieben werden.

Bei der Definition von KSIs wird empfohlen, "spezifische, messbare, zuzuordnende, realistische, zeitbezogene" (INTELLIGENTE) Kriterien zu verwenden:

-   Speziell: Ziel eines bestimmten Verbesserungsbereichs

-   Messbar: Fortschrittsanzeige quantifizieren oder zumindest vorschlagen

-   Assignable :specify who will do it

-   Realistisch: Unter Schätzer der verfügbaren Ressourcen sollte angegeben werden, welche Ergebnisse realistisch erzielt werden können.

-   Zeitbezogenes: Angeben, wann die Ergebnisse erzielt werden können

> [!TIP]
> Im folgenden Beispiel sehen Sie für dieses Projekt relevante wichtige Erfolgsindikatoren:
> 
> |Typ  |Fragen und Kriterien im Zusammenhang mit den wichtigen Erfolgsindikatoren  |Messmethode  |Erfolgskriterien  |Bemessungszeitpunkt  |Verantwortlich  |
> |---------|---------|---------|---------|---------|---------|
> |Verwendung/Einführung|Anrufqualität entspricht der vorherigen Lösung oder übertrifft diese|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach der Aktivierung und vierteljährlich|IT-Team|
> |Verwendung/Einführung|Microsoft Teams hat den Kommunikationsprozess vereinfacht.|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach der Aktivierung und vierteljährlich|Change Management-Team|
> |Verwendung/Einführung|Aktive Verwendung der Lösung durch die Benutzer|Microsoft 365, Anrufqualitätsdashboard|80 % der Benutzer sind täglich aktiv|Täglich|Change Management-Team|
> |Verwendung/Qualität|Prozentsatz der Anrufe/Konferenzen mit schlechter Qualität sollte verringert werden|Anrufqualitäts-Dashboard|< 5 % Anrufe mit schlechter Qualität pro Monat|Täglich|IT-Team|
> |Verwendung/Support|Ich weiß, wo ich technischen Support erhalte|Umfrage|Zustimmung oder starke Zustimmung bei 90% der Benutzer|Nach der Aktivierung und vierteljährlich|Change Management-Team|
> |Verwendung/Support|Ich bin zufrieden mit der Qualität des technischen Supports|Umfrage|Zustimmung oder starke Zustimmung bei 80 % der Benutzer|Nach jedem Vorfall|IT-Team|
> |Finanzen|Weniger Minuten mit Legacy-Konferenzlösung|Finanzsystem|Definierte Rendite erzielen|Basierend auf Rendite|Change Management-Team|

Sie müssen im Rahmen dieser Übung Geschäftsrisiken identifizieren und einen Entschärfungsplan für jedes identifizierte Risiko definieren. Diese Informationen können in einem Risikoregister erfasst werden.

> [!TIP]
> Ihr Risikoregister kann wie im folgenden Beispiel dokumentiert werden:
> 
> |Risiko  |Wahrscheinlichkeit  |Auswirkungen  |Gesamt  |Risikominderungsplan  |
> |---------|---------|---------|---------|---------|
> |Bei der bevorstehenden Fusion werden bis zu 1.000 Personen dazukommen|Hoch|Hoch|Hoch|<ul><li>Erstellen Sie für zusammengeführte Unternehmen ein separates OKR, das für ihre eigenen Projektphasen gilt (Envision, Onboard, Drive Value)</li><li>Fügen Sie diese OKRs nicht in vorhandene OKRs ein.</li></ul>|
> |Die Portierung von Telefonnummern verzögert den Projektabschluss.|Hoch|Hoch|Hoch|<ul><li>Vorbereiten aller Informationen, die zur Unterstützung der Portierung von Telefonnummern im Voraus erforderlich sind (Kundendienstdatensatz, Abrechnungsdetails, Genehmigungsschreiben)</li><li>Anpassen der Projektzeitachse, um die Bearbeitungszeit der Ausführung der Telefonnummernportierung zu unterstützen</li><li>Teilen Sie den externen Teilnehmern die neuen Einwahlkonferenznummern mit.</li><li>Verwenden temporärer Telefonnummern mit Manipulation der Rufnummernanzeige</li></ul>|
> |Geplante Umgestaltung des Netzwerks|Hoch|Mittel|Mittel|<ul><li>Führen Sie vor Teams einer modernen Kommunikations- und Zusammenarbeitsplattform eine Bewertung der Netzwerkbereitschaft für Websites im Projektumfang durch.</li></ul>|
> |SBC-Konfiguration|Hoch|Hoch|Hoch|<ul><li>Bevor Sie Teams als Ersatz für die vorhandene PbX implementieren, vergewissern Sie sich, dass Sie alle SBC-Konfigurationsanforderungen erfüllen können.</li><li>Stellen Sie sicher, dass SBC-Unterstützungsressourcen über die richtigen Kenntnisse zum Konfigurieren von SBC für Direct-Routing verfügen.</li></ul>|

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Entscheidungspunkte|<ul><li>Welche OKRs und KSIs&#39;Ihre Organisation?</li><li>Welche Risiken sind für die Implementierung von Audiokonferenzen in Ihrer Organisation von Bedeutung? Welche Pläne zur Entschärfung der identifizierten Risiken gibt es?</li><li>Welche Risiken haben Sie für die Implementierung von Anrufplänen in Ihrer Organisation als relevant identifiziert? Welche Pläne zur Entschärfung der identifizierten Risiken gibt es?</li><li>Welche Risiken sind für die Implementierung von Direct Routing in Ihrer Organisation von Bedeutung? Welche Pläne zur Entschärfung der identifizierten Risiken gibt es?</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Dokumentieren Sie die OKRs und KSIs, und legen Sie die Risiken im Register fest.</li></ul>|

<!--ENDOFSECTION-->

## <a name="establish-a-steering-committee"></a>Einrichten eines Lenkungsgremiums

Ein Lenkungskreis ist eine Führungsgruppe wichtiger Projektbeteiligten und Projektleiter, die zusammengebracht wurden, um ein Projekt oder Programm auf dem Weg zu seinen definierten Geschäftsergebnissen zu leiten. Der Lenkungsrat ist nicht  direkt dafür verantwortlich, wie  das Projekt geliefert wird, sondern was das Projekt für das Unternehmen liefert.

Für jedes Projekt ist eine vereinbarte Vision und Einarbeitung erforderlich. Um die Ergebnisse zu erzielen, die Sie aus dem Projekt erzielen möchten, muss die Vision klar definiert und überwacht und verwaltet werden. Dies wird die Aufgabe des Lenkungsgremiums: Entscheidungen zu treffen, zu beraten, strategische Aufsicht zu geben, die Organisation für Die Initiativen des Projekts zu unterstützen und – falls erforderlich – Blockierer zu entfernen.

Ihre Organisation sollte sich einen wichtigen Gedanken über die Mitglieder des Lenkungsgremiums machen. Die Komiteemitglieder müssen sicherstellen, dass das Projekt die Geschäftsziele erreicht, die Sie für die Veränderung innerhalb der Organisation definiert haben, sich regelmäßig treffen, um das aktuelle Pulse des Projekts zu diskutieren und dabei zu helfen, hindernisse zu beseitigen, die auf dem Weg aufgetreten sind.

Der Komitee sollte seinen Charter definieren, um einige Hauptziele zu enthalten:

-   Halten Sie eine starke Ausrichtung zwischen dem Projektteam und dem Executive Sponsor oder der Geschäftsleitung.

-   Geben Sie dem Executive Sponsor oder der Geschäftsleitung Einblicke in den Status des Projekts.

-   Lassen Sie zu, dass der Executive Sponsor oder das Geschäftsleitungsteam anweisungen und Input für das Projekt bereitstellen und sicherstellen, dass es sich an übergeordneten Geschäftszielen richtet, indem Projektpläne, objektiv wichtige Ergebnisse (OKRs) und andere Projektaktivitäten angepasst werden.

Das Lenkungsgremium trifft sich während der gesamten Lebensdauer eines Projekts in regelmäßigen Zeitintervallen, um eine Ausrichtung zwischen der Organisationsführung und dem Projektteam sicherzustellen. Durch diese kritische Besprechung wird sichergestellt, dass die Leitung des Projekts die volle Unterstützung durch die Führungskräfte hat und das von Führungskräften bereitgestellte Feedback in das Projekt ein integrieren, um den Erfolg zu fördern. Das Komitee nutzt diese Besprechungen, um Einblicke in den Projektstatus zu erhalten und um:

-   Stimmen Sie den Unternehmensergebnissen zu, die auf den Geschäftsbereich ausgerichtet sind, und um sicherzustellen, dass das Projekt auf den Weg zu diesen Ergebnissen kommt.

-   Überprüfen und genehmigen Sie das Projekt auf Genauigkeit und Compliance mit dem Geschäftsfall.

-   Überprüfen und überprüfen Sie Änderungen am Geschäftsfall, die sich auf definierte Ergebnisse auswirken können.

-   Treffen Sie strategische Entscheidungen hinsichtlich der Priorisierung von Projektlieferergebnissen, und genehmigen Sie Zwischenergebnisse.

-   Erkennen, verwalten und entschärfen Sie Lücken, Risiken und Probleme, bei denen vom Komitee zusätzlicher Einfluss erforderlich ist.

-   Sammeln Sie Unterstützung vom Executive Sponsor oder dem Executive Leadership-Team für Probleme, die eine Eskalation, Priorisierung und Lösung von Konflikten zwischen den Geschäftseinheiten der Projektbeteiligten erfordern. 

-   Stellen Sie formelles Feedback und Empfehlungen für Führungskräfte, das Change Advisory Board oder ggf. andere Unternehmens- und IT-Projektbeteiligten zur Verfügung.

<br>

|&nbsp;|&nbsp;|&nbsp;|
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/>|Entscheidungspunkte|<ul><li>Entscheiden Sie, ob ein Lenkungsgremium für Ihre Organisation erforderlich ist.</li></ul>|
|<img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/>|Nächste Schritte|<ul><li>Identifizieren Sie die Mitglieder des Lenkungsgremiums.</li><li>Planen Sie Besprechungen von Lenkungsgremiums.</li><li>Bereiten Sie sich auf die Besprechungen des Lenkungsgremiums vor.</li><li>Halten Sie Besprechungen des Lenkungsgremiums ab.</li><li>Ergreifen Sie Maßnahmen basierend auf den Beiträgen in der Besprechung des Lenkungsgremiums.</li></ul>|

Weitere detaillierte Anleitungen zur Leitung eines geeigneten Lenkungsgremiums finden Sie im Handbuch [des Lenkungsgremiums.](envision-steering-committee-complete-guide.md)

<!--ENDOFSECTION-->
