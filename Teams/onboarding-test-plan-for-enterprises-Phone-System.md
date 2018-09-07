---
title: Enterprise Testplan für Telefonsystem mit Aufrufen plant in Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Überprüfen, ob die Erwartungen hinsichtlich Ihrer Organisation erfüllt sind, über das Telefonsystem in Teams Features, Funktionen und Verwendbarkeit testen.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fffb52988da639f21246b0c5d27f2c8554b459ac
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23855425"
---
<a name="define-and-document-your-phone-system-with-calling-plans-in-teams-test-plan-for-enterprises"></a>Definieren Sie und Dokumentieren Sie Ihr Telefonsystem mit Aufrufen plant in Plan zum Testen von Teams für Unternehmen 
============================================================================================

Nachdem Sie Ihr Telefonsystem mit Aufrufen von Plänen in Teams geschäftlichen Erfolg und technische Pläne als Teil der Phase Ermitteln übergeordneter Faktoren dokumentiert und definiert haben, wird im nächste Schritt überprüfen, dass über die Erwartungen und die Anforderungen Ihres Unternehmens erfüllt sind Features, Funktionen und Verwendbarkeit. Sie sollten diese Validierungsschritt führen Sie vor der Bereitstellung einer pilot oder final-bereitstellungs in Ihrer produktionsumgebung.

Sie können Business Erfolg planen nutzen, die Sie während der Phase der Ermitteln übergeordneter Faktoren dienen als Grundlage für die Bestimmung der Aktivitäten, erwartet, die Funktionalität der Testfälle und allgemeine Bereich während der Testphase ausgewertet werden definiert haben.

<a name="identify-testing-support-stakeholders"></a>Bestimmen der beteiligten Personen testing support
-------------------------------------

Sie bei der Vorbereitung für die Auswertung Telefonsystem Funktionen aufrufen plant, erstellen Sie eine testing Matrix der unterstützten beteiligten zum Identifizieren der Rollen, die zur Unterstützung der Testphase erforderlich sind.

> [!TIP]
> Wie Sie die Tests Matrix der beteiligten Teams auffüllen, wird möglicherweise angezeigt, dass einige Rollen identisch mit den während der Phase der Ermitteln übergeordneter Faktoren, wobei jedoch rollenbeschreibung schräg sind zu testen. Sie müssen möglicherweise zusätzliche Rollen, je nach den Anforderungen Ihrer Testszenarios eindeutigen identifizieren.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Testen der Matrix der beteiligten Teams

> [!TIP]

> Im folgenden ist ein Beispiel einer testing Support beteiligten Vorlage, die Sie verwenden können, um die Beteiligten zu dokumentieren Sie zur Unterstützung der Testphase erfordern.

| Rolle                          | Rollenbeschreibung                                                                                                                                                                          | Zugeordneten Ressource, Kontaktinformationen und Ort |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Executive Sponsor(s) testen  | <ul><li>Stellen Sie sicher, dass Teams Features unternehmensanforderungen erfüllen; die executive Sponsor sind wichtige Geschäftsergebnisse und priorisiert Groß-/Kleinschreibung Nutzungsszenarien fließend.</li><li>Dienen Sie als ultimate Zertifizierungsstelle, und davon ausgehen Sie Accountability, für Teams Feature Ziele zu testen.</li><li>Hilfe von Tests führen eskaliert Probleme zu beheben.</li><li>Sponsor Kommunikation innerhalb des Unternehmens zum Testen der Ziele.</li><li>Wichtige strategische Entscheidung zuständig sein.</li><li>Zur Sicherstellung der Verfügbarkeit von erforderlichen Ressourcen und Budget für die Unterstützung von Testverfahren zuständig sein.</li><li>Laufwerk zur Förderung des Bekanntheitsgrads und Unterstützung für die Tests Kampagne mit anderen der Verantwortlichen.</li><li>Dienen Sie als der testing Sponsor während der Auswertungsphase Test.</li></ul>                                                 | TBD                                                  |
| Lenkungsausschuss Mitglieder    | <ul><li>Verwalten von Interesse, sowie Anleitungen für die allgemeine Richtung des das Telefonsystem mit der Bereitstellung des Plans aufrufen.<li>Kennsätzen strategischen Erkenntnisse über gesteuerter Führungsriege in der gesamten Organisation unterstützen.</li></ul>                                                                        | TBD                                                  |
| Projektleiter                  |<ul><li> Verwalten Sie, und führen Sie das Projektteam.</li><li>Partner und Teams an das Projekt anderweitig zu koordinieren.</li><li>Verantwortlich für das Erstellen und Verwalten von Project-Pläne wichtige Quartale erfüllen.</li><li>Beheben Sie funktionsübergreifenden Probleme.</li><li>Stellen Sie regelmäßige Updates für Project Sponsor.</li><li>Integrieren Sie wichtige Benutzer wünschen Befunde in Testergebnissen in der gesamten Benutzer Anpassungsplan identifiziert.</li><li>Führen Sie monatliche Geschäfts- und betriebsbereit Reviews (engl.), Beitrag zu vierteljährlich Business Reviews (engl.).</li></ul>                                                                                                                                                         | TBD                                                  |
| Leiter/Architekt für Zusammenarbeit  | <ul><li>Werden Sie verantwortlich für die Ausführung auf der Strategie für die Zusammenarbeit durch die Unternehmensführung definiert.</li><li>Analysieren und Auswählen von Produkten für die Zusammenarbeit für das Unternehmen, die Unternehmensziele.</li><li>Für den Entwurf für den Betrieb von Produkten für die Zusammenarbeit zuständig sein.</li><li>Definieren Sie die Modelle Betrieb und Support.</li><li>Beitrag zu monatlich oder vierteljährlich Business Reviews (engl.).</li></ul>                                                                                                 | TBD                                                  |
| Projektmanager               | <ul><li>Entwickeln Sie und verwalten Sie den Projektplan.</li><li>Verwalten Sie Projektlieferumfang in einer Reihe mit dem Projektplan und Ihrem Budget.</li><li>Aufzeichnen und Projektprobleme, einschließlich der Benutzerberechtigungen verwalten.</li><li>Durchführen Sie wöchentliche kurze Anrufe.</li><li>Verbindung mit und beinhalten Updates für Project executive Sponsor.</li><li>Arbeiten mit internen ändern, Verwaltung und Kommunikation Teams so aktualisieren Sie die Änderung Ansatz und Kommunikation Verwaltungspläne je nach Bedarf.</li></ul>                                                                                                                                                   | TBD                                                  |
| Netzwerkleiter                  | <ul><li>Enthalten Sie Eingabe während der Phase der Ermittlung Netzwerkdesign.</li><li>Bei der Planung während Ermitteln übergeordneter Faktoren Phase Workshops teilnehmen.</li><li>Koordinieren Sie die Arbeit der networking-Team während der Ausführung des Projekts.</li></ul>                                                                                                                               | TBD                                                  |
| Leiter der Sicherheit                 | <ul><li>Mitteilen Sie, Sicherheitsentwurf und Prozesse während der Phase der Suche.</li><li>Bei der Planung während Ermitteln übergeordneter Faktoren Phase Workshops teilnehmen.</li><li>Koordinieren Sie die Arbeit vom Security Team während der Ausführung des Projekts.</li></ul>                                                                                                                | TBD                                                  |
| Telefonieleiter                | <ul><li>Enthalten Sie Eingabe während der Phase der Ermittlung Telefonie Design.</li><li>Bei der Planung während Ermitteln übergeordneter Faktoren Phase Workshops teilnehmen.</li><li>Koordinieren Sie die Arbeit des Teams Telefonie während der Ausführung des Projekts.</li></ul>                                                                                                                           | TBD                                                  |
| Desktopleiter                  | <ul><li>Mitteilen Sie, Clients und des Aktualisierungsvorgangs während der Phase der Suche.</li><li>Bei der Planung während Ermitteln übergeordneter Faktoren Phase Workshops teilnehmen.</li><li>Koordinieren Sie die Arbeit des Teams desktop während der Ausführung des Projekts.</li></ul>                                                                                                              | TBD                                                  |
| Vertreter der Betriebseinheiten | <ul><li>Beitrag zu benutzerbasierte Annahme Handbücher und Materialien (engl.).</li><li>Beitrag zu, und überprüfen Sie, Geschäftsfälle verwenden.</li></ul>                                                                                                                                   | TBD                                                  |
| IT-Administratoren                     | <ul><li>Unterstützung bei der Planung von Test und Ausführung (diese Rolle ist für IT-Experten).                                                                                                                       | TBD                                                  |
| Leiter des Kundendiensts                 | <ul><li>Werden Sie alle für den Betrieb von das Telefonsystem mit Dienst aufrufen Plans zuständig.</li><li>Fungieren Sie als Besitzer der das Telefonsystem mit Dienst plant aufrufen.</li></ul>                                                                                                               | TBD                                                  |
| Test Lead-Manager             | <ul><li>Definieren des Testplans, einschließlich Aktivitäten, Abhängigkeiten, Umgebung, Ziele, Strategie, Durchführung der Migration erforderlich (Umwelt- und human) und den Zeitplan für die Unterstützung der Testphase erforderlich.</li><li>Bereitstellung und Bereitschaft für Test Plan Abhängigkeiten zu koordinieren.</li><li>Mit der rechten Priorität für Fehler Lösung ausrichten.</li><li>Dienen Sie als Eskalationspfad auf testing Probleme, die auftreten.</li><li>Kommunizieren Sie und Berichten Sie Test Planstatus mit internen Teams und der festgelegten Beteiligten.</li><li>Dokumentieren Sie und präsentieren Sie der abschließenden Testergebnisse.</li></ul> | TBD                                                  |
| Telefonsystem mit dem Aufrufen der Pläne Tester     | <ul><li>Überprüfen Sie den Testplan zu verstehen, testing Anforderungen, Ziele, Zeitplan, Problembehebung und Testfälle ausgeführt werden.</li><li>Überprüfen und Entwickeln von Testfällen für das Telefonsystem aufrufen plant Annahme und Funktionalität Vorschriften unterstützen.</li><li>Führen Sie Testfälle und Testergebnisse Dokument.</li><li>Fehler beim auftreten und sie an der Test Lead für die Priorisierung und Auflösung eskalieren des Dokuments.</li><li>Testen Sie Regressionen um Fehler zu schließen, nachdem defekt Lösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |
| Netzwerk-Tester                | <ul><li>Überprüfen Sie den Testplan zu verstehen, testing Anforderungen, Ziele, Zeitplan, Problembehebung und Testfälle ausgeführt werden.</li><li>Überprüfen Sie Testfälle Bereitschaft Annahme und Leistung netzwerkanforderungen unterstützen.</li><li>Führen Sie Tests im Zusammenhang mit der Bereitschaft des Netzwerks, einschließlich Netzwerkkonnektivität und Leistung Überprüfung, QoS-Validierung und Überprüfung der Split-Tunnel-Konfiguration.</li><li>Führen Sie mithilfe von Netzwerk-Planner über MyAdvisor Bandbreite Validierung Websites im Bereich.</li><li>Bereitschaft des Netzwerks Testergebnisse des Dokuments.</li><li>Fehler beim auftreten und sie an der Test Lead für die Priorisierung und Auflösung eskalieren des Dokuments.</li><li>Testen Sie Regressionen um Fehler zu schließen, nachdem defekt Lösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |
| Sicherheitstester               | <ul><li>Überprüfen Sie den Testplan zu verstehen, testing Anforderungen, Ziele, Zeitplan, Problembehebung und Testfälle ausgeführt werden.</li><li>Überprüfen und Testfälle unterstützende Annahme sicherheitsanforderungen entwickeln.</li><li>Führen Sie Tests im Zusammenhang mit Sicherheit Annahme für Testfälle.</li><li>Dokument Sicherheit Akzeptanztests Ergebnisse.</li><li>Fehler beim auftreten und sie an der Test Lead für die Priorisierung und Auflösung eskalieren des Dokuments.</li><li>Testen Sie Regressionen um Fehler zu schließen, nachdem defekt Lösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |
| Telefonie Tester              | <ul><li>Überprüfen Sie den Testplan zu verstehen, testing Anforderungen, Ziele, Zeitplan, Problembehebung und Testfälle ausgeführt werden.</li><li>Überprüfen Sie Testfälle Zahl Portieren Annahme und Funktionalität dienstanforderungen unterstützen.</li><li>Führen Sie Tests im Zusammenhang mit der Nummer portieren, einschließlich Service Zahl Port zu Office 365-service.</li><li>Führen Sie Testfälle und Dokument Testfallergebnisse.</li><li>Fehler beim auftreten und sie an der Test Lead für die Priorisierung und Auflösung eskalieren des Dokuments.</li><li>Testen Sie Regressionen um Fehler zu schließen, nachdem defekt Lösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |
| Telefonsystem per plant Admin-Test | <ul><li>Überprüfen Sie den Testplan zu verstehen, testing Anforderungen, Ziele, Zeitplan, Problembehebung und Testfälle ausgeführt werden.</li><li>Überprüfen und Entwickeln von Testfällen für das Telefonsystem aufrufen plant Administration Annahme und Funktionalität Vorschriften unterstützen.</li> <li>Führen Sie Testfälle und Dokument Testfallergebnisse.</li><li>Fehler beim auftreten und sie an der Test Lead für die Priorisierung und Auflösung eskalieren des Dokuments.</li><li>Testen Sie Regressionen um Fehler zu schließen, nachdem defekt Lösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche testing Support- und Beteiligten Rollen, Sie benötigen für die Tests Telefonsystem mit Features in der Umgebung plant aufrufen.</li><li>Entscheiden Sie, welche Ressourcen, die Sie für die testen Support- und Beteiligten Rollen zuweisen müssen, den Sie angegeben haben.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Die Testen in der Tests unterstützen beteiligten Matrix erforderlichen Support- und Beteiligten Rollen des Dokuments.</li><li>Dokumentieren Sie Kontaktinformationen sowie Details zum Besprechungsort für jede Ressource, die Sie in den Tests beteiligten Matrix der unterstützten anbieten.
</table>


<a name="define-phone-system-with-calling-plans-feature-requirements"></a>Definieren von Telefonsystem mit Aufrufen plant Feature Anforderungen 
------------------------------------------------------------

Als Teil der Definition von Telefonsystem mit Aufrufen plant Feature Anforderungen für Benutzer im Gültigkeitsbereich wurde eine erste Schritte, die Sie während der Phase der Ermitteln übergeordneter Faktoren abgeschlossen haben, sollte der [Rolle Analyse](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans#assess-environment-and-evaluate-adoption-readiness), in dem Sie Ihr Telefonsystem mit Aufrufen plant definiert Rolle und Szenarios.
Im nächste Schritt werden mit dieser Baseline identifiziert bewerten die neueste Teams öffentliche Roadmap, um zu bestimmen:

-   Welche Telefonsystem mit Aufrufen plant Features, die Sie für Benutzer im Gültigkeitsbereich bereitstellen können.

-   Erwartete Benutzer Telefonsystem mit Aufrufen plant Funktionalität Anforderungen für den angegebenen Ihrer aktuellen Skype für Business, Exchange und SharePoint-Bereitstellung im Querformat.

-   Erfüllen Sie Ihre Benutzer, Funktionen und bereichsanforderungen in die Zeitachse Ihrer Bereitstellung, ob Sie bestätigen können, dass die neuesten öffentlichen Roadmap Telefonsystem mit Aufrufen plant Features beschrieben

> [!TIP]
> Die neueste Teams-Roadmap für die Identifizierung von Telefonsystem mit Aufrufen plant Features im Bereich für die Bereitstellung Sie unter finden <https://aka.ms/skype2teamsroadmap>.

Nun, da das Telefonsystem mit Persona plant aufrufen und Features definiert wurden, werden die nächsten Kriterien für die Auswertung der Interoperabilität Erfahrung mit Teams. Weitere Informationen über die Interoperabilität-Erfahrung zusammen mit verfügbaren Konfigurationsoptionen finden Sie unter [Microsoft-Teams und Skype für die Business-Interoperabilität](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability).

#### <a name="phone-system-with-calling-plans-feature-definition"></a>Telefonsystem mit Featuredefinition plant aufrufen

> [!TIP]
> Es folgt ein Beispiel für eine Telefonsystem aufrufen plant Definition Vorlage, die Sie verwenden können, um dokumentieren das Telefonsystem mit Aufrufen plant Verwaltungs- und Benutzer Gruppenfunktionen ausgewertet werden soll.


| Höchste Ansprüche   | Besprechungen    | Plattformen und Geräte   | Für IT-Experten  | Zusätzliche Unternehmensgruppe, standortspezifische  | Anforderungen erfüllt neueste Teams-roadmap |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Telefonsystem Anruffunktionen:<ul><li>Blind Übertragung</li><li>Blockieren von Anrufen</li><li>Die Anrufweiterleitung</li><li>Anrufer-ID Maskierung</li><li>E911-Unterstützung</li><li>Erweiterung Wählvorgang</li><li>Anruf halten</li><li>Mit mehreren Anrufbehandlung</li><li>Gleichzeitiges Klingeln</li><li>Azure-Voicemail</li></ul></li><li>Unterstützung von Aufrufen von Plänen</li></ul> |<ul><li>Skype für Business-an-Aufruf von Teams</li></ul> |<ul><li> Windows, Mac Teams Client Besprechungen bieten Unterstützung</li><li>Browser Teams Besprechungen Clientfunktion Unterstützung für:<ul><li>Chrome</li><li>Microsoft Edge</li></ul></li><li>iOS und Android Teams Clientfunktion Besprechungen unterstützen</li><li>TTY-support</li></ul> | <ul><li>Rufen Sie diagnoseportal Qualität</li><li>Mandanten-Wählplan</li><li>Mandanten Anrufer-ID-Richtlinien</li><li>Aktivieren der Anrufqualität Analytics (CQD)</li></ul> | <ul><li>Überprüfen von Teams meeting-Features basierend auf unternehmenseigenen Laptop-Bild</li><li>Unterstützung für bestimmte Sprachen</li><li>GPO-Einstellungen für einen bestimmten Benutzerszenario oder bestimmte Website angewendet</li></ul> | Ja  |




#### <a name="phone-system-with-calling-plans-user-functionality-definition"></a>Telefonsystem mit Aufrufen plant Benutzer Funktionalität definition

> [!TIP]
> Im folgenden ein Beispiel für eine Vorlage für Funktionen, die Sie verwenden können, um die Benutzeroberfläche erforderlich zu dokumentieren basieren auf das Telefonsystem mit den Funktionen aufrufen plant ausgewertet werden soll.


| Exchange-Erfahrung                          | SharePoint-Umgebung                            | Teams Interoperabilität Richtlinie Erfahrung |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Erstellen von Teams (Office-Gruppe Erstellung aktiviert)</li><li>An Teams teilnehmen</li><li>Kanäle erstellen</li><li>Besprechungen erstellen und anzeigen</li><li>Benutzerprofilbild bearbeiten</li><li>Connectors hinzufügen und konfigurieren</li><li>Registerkarten hinzufügen und konfigurieren</li><li>Bots hinzufügen und konfigurieren</li></ul> | <ul><li>Speichern und Freigeben von Dateien in Teams Unterhaltungen</li><li>Speichern und freigeben und Dateien in privaten Chats (basierend auf OneDrive)</li></ul> | <ul><li>ChatDefaultClient: Default</li><li>CallingDefaultClient: Default</li></ul>      |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li> Entscheiden Sie, welche Telefonsystem mit Aufrufen plant Kategorie Features, die Sie in Ihrer Umgebung bereitstellen können.</li><li>Identifizieren Sie Ihre Benutzer Telefonsystem mit Aufrufen plant Funktionalität Anforderungen angegebenen Ihrer aktuellen Skype für Business, Exchange und SharePoint-Bereitstellung im Querformat.</li><li>Entscheiden Sie, welche Teams Interoperabilität wünschen Sie bereitstellen müssen.</li><li>Überprüfen Sie die neuesten öffentliche Roadmap für Teams und entscheiden Sie, ob der aktuelle arbeitsauslastungsfunktionen Ihrer Bereitstellung Zeitachse erfüllen.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokument das Telefonsystem mit Aufrufen plant Kategorie Features zur Unterstützung von Ihr Telefonsystem mit Aufrufen plant Bereitstellung erforderlich.</li><li>Dokumentieren Sie Benutzer Telefonsystem mit Funktionen aufrufen plant und Interoperabilität-Anforderungen erhält Ihre aktuellen Skype für Business, Exchange und SharePoint-Bereitstellung im Querformat.</li><li>Dokumentieren Sie, ob die neueste öffentliche Roadmap von Teams, Telefonsystem Funktionen aufrufen plant darstellt, die geschäftlichen Anforderungen und Timing-Anforderungen Ihrer Bereitstellung erfüllt.</li></ul></td></tr>
</table>

<a name="define-and-document-your-phone-system-with-calling-plans-test-plan"></a>Definieren Sie und Dokumentieren Sie Ihr Telefonsystem Testplan plant aufrufen
------------------------------------------------------------------

Nachdem Sie das Telefonsystem mit Aufrufen plant Features im Bereich definiert haben, besteht der nächste Schritt den Testplan erstellen. Auf allgemeiner Ebene umfasst der Plan zum Testen der allgemeine Teststrategie und Methoden, mit denen Sie die Überprüfung von Feature in der Testprozesse unterstützt werden.

Auf allgemeiner Ebene sollte der Testplan umfassen:

-   **Bereich testen:** Enthält eine Zusammenfassung der Schwerpunkte (Ziele, Szenarien und Ziele) ausgewertet werden soll, im Rahmen der Testphase

-   **Testfälle:** Der Satz von Testfällen für Telefonsystem mit Aufrufen plant-im Bereich Features überprüft werden soll

-   **Testressourcen:** Eine Matrix von Ressourcen zur Unterstützung von Tests aus einer Sicht Umwelt, technische und Personal erforderlich

-   **– Handbuch zu Tests Zeitplan (Zeitskala):** Darstellt, wenn der Test beginnt, wenn Sie für das Ende die Testphase erwarten und wie lange es wahrscheinlich letzten ist

-   **Verfolgung, berichterstellung und Korrektur:** Richtlinien für wie Probleme mit testen gemeldet werden sollen, nachverfolgt und selektiert

-   **Verfolgung Ursachenanalyse und Ausweitung:** Gliederung für einen Fehler Ausweitung wie und wann gestartet werden sollen

-   **Beenden und Aussetzung Kriterien testen:** Gliederung Kriterien zur Einhaltung der entweder Abnahme zum Beenden der Testphase oder Anhalten des Tests bis mit Prioritätsstufe defekte aufgelöst werden

-   **Testen Lieferumfang:** Zusammenfassung der Ergebnisse entwickelt und zur Unterstützung der Abnahme Annahme und Beenden der Tests übermittelt werden

> [!TIP]
>   Eine-Tests ist möglicherweise bereits in Ihrer Organisation vorhanden, aber die folgenden Anleitung widerspiegelt bewährte Methoden, die eingebunden oder separat für Teams Testfeatures in Ihrer Umgebung genutzt werden können.

In die Abschnitten, die Sie folgen finden weitere vorgeschriebenen Anleitungen, die in bestimmten Entscheidungen und Vorlagen und Themen wie Ihre testing Planung berücksichtigen unterstützen.

### <a name="define-and-document-testing-scope"></a>Definieren Sie und Dokumentieren Sie Testumfang

Während der Arbeit um Testplan zu entwickeln, müssen Sie definieren Testumfang voraus, Hervorheben der Arbeitslast und die Liste der Features, die Sie eine Auswertung erstellen möchten.

Der Bereich für die Auswertung ordnungsgemäß Telefonsystem in der Regel mit Aufrufen plant Features umfasst:

-   Telefonsystem mit Aufrufen plant Website Bereitschaft

-   Telefonsystem mit Aufrufen plant Benutzererlebnis

-   Telefonsystem mit Aufrufen plant administration

#### <a name="phone-system-with-calling-plans-testing-scope"></a>Telefonsystem mit Aufrufen plant Bereich testen

> [!TIP]
>   Es folgt ein Beispiel Test Bereich Vorlage, die Sie verwenden können, um dokumentieren das Telefonsystem mit Aufrufen plant Verwaltungs- und Benutzer Gruppenfunktionen ausgewertet werden soll.

| Telefonsystem mit Aufrufen plant Website Bereitschaft                                                                                                                                                                                    | Telefonsystem mit Aufrufen plant Benutzererlebnis                                                                                                                                                                                         | Telefonsystem mit Erfahrung in der Verwaltung plant aufrufen                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>Der Netzwerkbandbreite Planner planning (über MyAdvisor)<li></li>Netzwerk-Konnektivität und die Leistung Validierung (über die Skype für Tool zur Bewertung der Business-Netzwerk)<li></li>Die Qualität der Überprüfung Service (QoS)<li></li>Remotezugriff Split-Tunnel Validierung</li></ul>|<ul><li>PBX-features<li></li>Telefonnetz (nationalen und internationalen)<li></li> Tätigen und Empfangen von PSTN-Anrufe<li></li>Azure-Voicemail<li></li>E911<li></li>Mandanten-Wählplan<li></li>Mandanten Anrufer-ID-Maskierung <li></li>Erweiterte remoteanrufsteuerungsfunktionen (beispielsweise die anrufweiterleitung, Gleichzeitiges Klingeln)</li></ul> |<ul><li>Lizenzierung der Zuordnung</li><li>Teilnehmernummer Portieren zu Office 365</li><li>Telefonsystem mit reporting plant aufrufen</li><li>Die Anrufqualität reporting (CQD)</li></ul> |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie das Telefonsystem mit Aufrufen plant testen Bereich durch das Identifizieren von Features durch den Fokusbereich ausgewertet werden soll.</li><li>Entscheiden Sie zusätzliche Ziele und Zielsetzungen für die Auswertung.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie das Telefonsystem mit Aufrufen plant Features nach den Fokusbereich ausgewertet werden soll.</li><li>Zusätzliche Ziele und Zielsetzungen für die Auswertung des Dokuments.</li></ul></td></tr>
</table>

### <a name="define-and-document-phone-system-with-calling-plans-test-cases"></a>Definieren Sie und Dokumentieren Sie Telefonsystem plant Aufrufen von Testfällen

Nachdem Sie das Telefonsystem mit Funktionen aufrufen plant, Clientbereitstellung und Side-by-Side-Szenarien mit Skype für Unternehmen (falls zutreffend) definiert haben, besteht der nächste Schritt erforderlich für die Auswertung Telefonsystem plant Aufrufen von Features in Testfälle zu formulieren Bereich. Auf allgemeiner Ebene Testfälle in der Regel werden nach den Fokusbereich gruppiert und umfassen:

-   **Testfall Titel:** Auswerten von Fokusbereich des Features für den Test mit den (beispielsweise Telefonsystem mit plant aufrufen)

-   **Testfall Beschreibung:** Zusammenfassung der Ziele des Tests Gliederung features ausgewertet wird

-   **Testfall Anweisungen:** Schritte für den Testfall ausgeführten richtig ausgeführt

-   **Umgebung erforderlich (Voraussetzungen):** Setupanweisungen erforderlich, um die ordnungsgemäße Ausführung des Tests

-   **Ressource erforderlich:** Personelle Ressourcen für die ordnungsgemäße Auswertung und Ausführung des Tests erforderlichen

-   **Erwartete Ergebnisse:** Das Ergebnis, das Sie erwarten, nachdem der Test erfolgreich abgeschlossen wurde

> [!NOTE]
>   Da die Ansatz und die Detailebene für das Erstellen von Testfall erforderlichen innerhalb Ihrer Organisation unterschiedlich sein können, ist es ratsam, einen Ansatz zu befolgen, der für einen angemessenen Detailebene ermöglicht noch ausgeglichen Gründlichkeit mit Möglichkeit, der zur Unterstützung von allgemeinen testen Verwaltbarkeit.

> [!TIP]
>   Zur Erleichterung der Testfall Erstellung als Ausgangspunkt finden Sie in der Liste der Phone System Benutzer Anleitungen verfügbar unter [Teams Besprechungen und Telefonkonferenzen](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8).

#### <a name="phone-system-with-calling-plans-test-case"></a>Telefonsystem Testfall plant aufrufen

> [!TIP]
>   Im folgenden finden Sie ein Beispiel Testfall-Vorlage, die Sie verwenden können, um dokumentieren das Telefonsystem mit Aufrufen plant Verwaltungs- und Benutzer Gruppenfunktionen ausgewertet werden soll.

Telefonsystem mit dem Aufrufen der Pläne Validierung

| Testfall-ID | Testfall Titel               | Testfall Beschreibung                                                  | Umgebung für die Ausführung des Testfalls erforderlich                                               | Für die Ausführung des Testfalls erforderlichen Schritte                                                                                                                                                          | Testen der Ressource benötigt              |
|--------------|-------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| 1            | Tätigen eines ausgehenden Anrufs PSTN | Stellen Sie sicher, dass Sie einen externen Anruf auf eine Zahl 10 Ziffern einfügen können. |<ul><li>Teams-Client installiert.</li><li>Benutzer mit den folgenden Office 365-Lizenzen zugewiesen aktiviert:<ul><li>Office Enterprise E5 mit Telefonsystem, Microsoft-Teams und nationalen und internationalen Aufruf von Plänen</li><li>Office Enterprise E3 mit Telefonsystem, Microsoft-Teams und nationalen und internationalen Aufruf von Plänen</li></ul></li></ul> | <ol><li>Melden Sie sich an den Client Teams.</li><li>Wählen Sie das Wähltastenfeld, und geben Sie eine Nummer 10 Ziffern zu wählende.</li><li>Stellen Sie sicher, dass die Zahl Einwahl ordnungsgemäß normalisiert und externe PSTN-Anruf wird eingerichtet.</li></ol>    | Telefonsystem mit dem Aufrufen der Pläne Tester |


> [!TIP]
>   Überprüfen Sie zusätzliche Anleitung bei der Erleichterung der allgemeine Plan Erstellung für die Auswertung Telefonsystem mit Features in Ihrer Organisation plant aufrufen und einzelne Testfall [Phone System Test Plan](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) von [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/)bereitgestellt.


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden, welche Telefonsystem mit Aufrufen plant Verwaltung und Features der ausgewertet werden.</li><li>Entscheiden Sie, welche testumgebung zur Ausführung des Testfalls Unterstützung erforderlich ist.</li><li>Entscheiden Sie, die bei der Evaluierung Testfall erforderlichen Schritte.</li><li>Entscheiden Sie, die für die ordnungsgemäße Ausführung des Tests erforderlichen Ressourcen.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die Testfälle ausgewertet werden soll, basierend auf der bereitgestellten Testfall-Vorlage.</li><li>Enthalten Sie die abgeschlossene Vorlage als Teil des gesamten Testplans.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Definieren Sie und Dokumentieren Sie Testressourcen

Zur Unterstützung der Testphase ist es wichtig, dass Sie entwickeln ein Ressourcenplans mit ausführlichen Informationen zu den Personen, Unterstützung und Technologie Ressourcen, die Sie benötigen, werden. Einen wichtigen Bestandteil der allgemeine Plan zum Testen von möglicherweise die Ressource Plan können, die Sie bestimmen, dass Abhängigkeiten, die möglicherweise vorhanden ist, und erhalten Sie einen allgemeinen Überblick der Ressource, die Sie unterstützen, müssen.

Auf allgemeiner Ebene bestehen diese Ressourcen in der Regel aus:

-   **Personen**: beteiligten

-   **Technologie**: Mandanten, Lizenzierung, Geräte

-   **Unterstützt**: Schulung (Karten, Videos), Unterstützung der Verwaltung mit definierten Eskalationspfad

#### <a name="testing-resource-requirements"></a>Testen des Ressourcenbedarfs

> [!TIP]
>   Es folgt ein Beispiel testing Ressource Anforderung Vorlage, die Sie verwenden können, um die verschiedenen Arten von Ressourcen zur Unterstützung Ihrer Testphase erforderlich zu dokumentieren.


| Ressourcentyp | Erforderlichen Ressourcen                                           | Beschreibung der Ressource |
|---------------|--------------------------------------------------------------|----------------------|
| Personen        | Beteiligten Test Lead Tester                               | TBD                  |
| Technologie    | Zugriff auf Office 365 mit die folgenden Dienste aktiviert:<ul><li>Lizenzierung der Office 365-E5 zugewiesen</li><li>Aufrufen von nationalen und internationalen Plan zugewiesen</li></ul>    | TBD                  |
| Support       | Testen der Administrator Unterstützung Testleiter Supporttechniker Test | TBD                  |

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie Ressourcentypen (Personen, Technologie und Unterstützung), die Sie zur Unterstützung der Testphase benötigen.</li><li>Entscheiden Sie, die bestimmten Ressourcen erforderlich für die Ressourcentypen, den, die Sie angegeben haben.</li><li>Entscheiden Sie, ob die Details zum Beschreiben der Arten von Ressourcen, die Sie benötigen weitere bereitgestellt werden sollen.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die Ressourcentypen (Personen, Technologie und Unterstützung), die Sie zur Unterstützung der Testphase benötigen.</li><li>Dokumentieren Sie die entsprechenden Ressourcen für die Ressourcentypen, die Sie identifiziert erforderlich.</li><li>Wenn Sie sich, dass es erforderlich ist entscheiden, dokumentieren Sie alle Weitere Einzelheiten zu den Arten von Ressourcen, die Sie die Testphase unterstützen müssen.</li></ul></td></tr>
</table>


### <a name="define-and-document-a-testing-timeline"></a>Definieren Sie und Dokumentieren Sie eine testing Zeitachse

Erstellen Sie im Rahmen der Test Plan Definition eine Zeitskala an, die den Zeitplan für die wann voraussichtlich auf Testaktivitäten abzuschließen und zu allgemeinen Meilensteine erzielen erläutert.

Auf allgemeiner Ebene besteht in der Regel aus:

-   **Aufgabe:** Allgemeine Aktivität ausgeführt werden

-   **Meilenstein:** Allgemeine Ziel oder Fortschritt, der beendet wurde

-   **Ressource erforderlich:** Testen von Ressourcen zur Unterstützung der Bereitstellung von den Meilenstein oder den angegebenen Vorgang erforderlich

-   **Startdatum:** Das Datum, an dem die Aktivität, Meilenstein oder Aufgabe auf gestartet wurde

-   **Fertigstellungstermin:** Das Datum der Aktivität, den Meilenstein oder die Aufgabe abgeschlossen wird erwartet

-   **Besitzer:** Zugeordneten Ressource, dafür verantwortlich ist, sicherzustellen, dass die Aktivität, den Meilenstein oder die Aufgabe, auf, die gemäß der Fertigstellungstermin abgeschlossen ist

-   **Schätzung:** Anzahl der Stunden, dass die zugeordneten Ressourcen es erwarteten dauert, stellen Sie sicher, dass die Aktivität, Meilenstein oder Vorgang termingerecht abgeschlossen ist

#### <a name="testing-scheduling-and-timeline-requirements"></a>Testen der Planung und Zeitachsen-Anforderungen

> [!TIP]
>   Es folgt ein Beispiel für eine Vorlage testing Zeitplan Anforderung, die Sie verwenden können, um die erwarteten Datumsangaben für zu dokumentieren, wenn bestimmte Testaktivitäten abgeschlossen werden oder Meilensteine durch bereitgestellt werden.

| Aufgabe                                                 | Meilenstein       | Startdatum                                                             | Abschlussdatum | Besitzer | Zugeordneten Ressourcen | Schätzung |
|------------------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Testbericht                                          | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | TBD Stunden  |
| Ausführung des Testfalls: Telefonsystem mit dem Aufrufen der Pläne | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | TBD Stunden  |
| Ausführung des Testfalls: Bereitschaft des Netzwerks               | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | TBD Stunden  |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie Zeitachse Aktivität und Meilenstein Aufgaben, bei denen Sie überwachen möchten.</li><li>Entscheiden Sie, welche Ressourcen Sie benötigen zuweisen.</li><li>Entscheiden Sie das Datum, an das Sie erwarten, die ausgeführt werden.</li><li>Identifizieren Sie die Übermittlung Besitzer.</li><li>Entscheiden Sie, wie lange es dauert, führen Sie die Aktivität, den Meilenstein oder die Aufgabe.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie Ihre testing Zeitachse mithilfe der Vorlage bereitgestellt und umfassen:<ul><li>Timeline-Aktivität, Meilenstein und Aufgaben, die überwacht werden müssen.</li><li>Ressourcen, die zugewiesen werden müssen.</li><li>Voraussichtliche Abschlussdatum.</li><li>Übermittlung Besitzer.</li><li>Für die Durchführung der Aktivität, den Meilenstein oder die Aufgabe erforderliche Zeit.</li></ul></li><li>Enthalten Sie die abgeschlossene Vorlage als Teil des gesamten Testplans.</li></ul></td></tr>
</table>


### <a name="define-and-document-test-defect-report-criteria"></a>Definieren Sie und Dokumentieren Sie der Test defekt Berichtskriterien

Wie Testfälle in einer bestimmten Phase oder einem Stream ausgeführt werden, können Probleme auftreten, in dem das Ergebnis der ausgeführten Testfall wird nicht erwartet.

Beim Auftreten dieser Arten von Ergebnissen, sollten sie in einem Bericht und-Wartung Plan für Fehler erfasst werden, die an den angegebenen Test Lead für überprüfen, reporting und Fehler Lösung ausgeweitet.

In der Regel enthält ein Fehler Bericht und-Wartung Plan Folgendes:

-   **Verfolgung-ID:** Die Nummer, das Problem zugewiesen ist

-   **Betroffene Testfall-ID**: die Nummer des Testfalls die zum Zeitpunkt der Fehler identifiziert wurde auszuwertende wurde

-   **Verfolgung Beschreibung:** Zusammenfassung des Problems

-   **Umgebung/Schritte zum Reproduzieren:** Zusammenfassung der testing Umgebungssetup zusammen mit dem genauen Schritte erforderlich, um das Problem zu reproduzieren

-   **Fehler Schweregrad**: die Auswirkung des Problems, angefangen verhindert, dass der Testfall seiner Annahme mit minimalem Risiko genehmigt werden. Einige Beispiele möglicherweise:

-   **Niedrig:** Das Problem wirkt sich nur geringfügig und wird nicht verhindern, dass der Testfall Annahme erreichen, wenn das Problem später aufgelöst werden kann.

-   **Mittel:** Das Problem erhebliche Auswirkungen hat, aber Sie werden nicht verhindern, dass der Testfall Annahme erreichen, wenn das Problem behoben werden, bevor die Testphase abgeschlossen ist.

-   **Hohe:** -das Problem hat wichtige Auswirkung auf den Testfall. Das Problem muss behoben werden, bevor der Testfall akzeptiert werden kann.

-   **Status:** Wurde das Problem behoben wurde, ist es geöffnet ist, oder noch in der Untersuchung

-   **Übermittelt von:** Der Tester das Problem gemeldet

-   **Besitzer zugewiesen:** Die Ressource aus, die zur Lösung dieses Problems zuständig ist, Testteam zugeordnet.

-   **Ergänzende Details:** Dazu gehören kann – anderem – mithilfe der clientseitigen Protokolle, Screenshots oder Video des Problems.

Wie Tester im Testplan beschriebenen Testfälle ausführen, sollten sie unbedingt für die Durchführung ein defekt Bericht und-Wartung Plans für Probleme, die auftreten.
Dadurch werden potenzielle Auswirkungen hervorheben, die beeinträchtigen oder sogar Anhalten der Bewertung Testvorgang konnte.

#### <a name="testing-defect-report-and-remediation-plan"></a>Planen von Tests Fehlerbericht und-Wartung

> [!TIP]
>   Es folgt ein Beispiel-Fehlerbericht und Planen der Wartung Vorlage, die Sie zum dokumentprobleme während der Testphase verwenden können.

| Fehler-ID                                | Betroffene Testfall-ID | Beschreibung des Fehlers                                                                                 | Umgebung /steps zu reproduzieren                                                                                                | Schweregrad | Status | Übermittelten | Zugewiesene Besitzer | Unterstützung von Details (Protokolle, Screenshots usw.) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Wenn der Benutzer eine vierstellige Erweiterung eingibt, schlägt fehl, versucht, einen ausgehenden Anruf, setzen Sie der Anruf. | Klicken Sie im Client Teams aktivieren Sie das Wähltastenfeld, geben Sie eine vierstellige-Erweiterung, und wählen Sie das Telefonsymbol so versuchen Sie, den Anruf zu tätigen. | Mittel   | Geschlossen | Louis Lahr   | Lisa grau      | Teams mithilfe der clientseitigen Protokoll<br/> Screenshot der Teams-client     |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie Sie zur Unterstützung der Testaktivitäten ordnen defekt Kriterien Schweregrade.</li><li>Entscheiden Sie, welche Kriterien, die Sie dokumentieren werden, treten Probleme während der Tests reporting testing defekt.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren des testen Fehlers reporting Kriterien, die in der bereitgestellten Vorlage erforderlich.</li><li>Enthalten Sie die abgeschlossene Vorlage als Teil des gesamten Testplans.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Definieren Sie und Dokumentieren Sie beenden und Aussetzung Kriterien

Im Rahmen der gesamten Test Plan ausführen müssen Sie Kriterien an, um den Punkt angeben, an dem Sie Testverfahren im Vergleich zu Anforderungen unterbrechen soll, die erfüllt sein müssen, damit Abnahme abrufen und Beenden der Testphase, definieren.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Test Plan beenden und Aussetzung Kriterien

> [!TIP]
>   Im folgenden ist ein Beispiel für beenden und Aussetzung Kriterien-Vorlage, die Sie in Ihrem Dokument Kriterien Testplan verwenden können Abnahme zu erzielen, Testphase beenden oder unterbrechen Testaktivitäten erforderlich.

| Testen der abschlusskriterien                            | Testen der Aussetzung Kriterien                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Alle Testfälle muss eine Pass-Rate der TBD % erzielen.</li><li>Alle Testfälle muss vollständig ausgeführt wurden</li><li>Aus allen Testfällen ausgewertet müssen alle hoher Schweregrad Mängel geschlossen werden</li></ul> | <ul><li>Alle Testfälle muss eine TBD % Fehlerrate erzielen.</li><li>Alle Fehler, die als hoher Schweregrad müssen behoben werden, bevor Tests fortgesetzt werden kann.</li></ul> |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Treffen einer Entscheidung bezüglich Aussetzung Kriterien, die erfüllt sein müssen, wenn Probleme mit testen identifiziert werden.</li><li>Treffen einer Entscheidung bezüglich abschlusskriterien die Genehmigung durch testing Akzeptanz und Unterstützung die Testphase erst, nachdem alle Tests beenden erfüllt sein müssen, dass Aktivitäten abgeschlossen sind.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie testing beenden und Aussetzung Kriterien in den Test- und Exit-Vorlagen zur Verfügung gestellt.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Definieren und Dokumentieren des Fehler Ausweitung-Prozess

Im Verlauf der Test Plan Ausführung können Sie ermitteln ein Problem oder identifizieren einen Fehler, der Weiterleitung zu den rechten Ressource benötigt für die Umsetzung und bestimmen die erforderliche Auflösung zu testen, um den Vorgang fortzusetzen.

Fehler mit dem entsprechenden Schweregrad und Priorität identifiziert werden, erstellen Sie eine Matrix Ausweitung und Ursachenanalyse Prozess für die Zuordnung, bei eine Ausweitung ausgelöst wird und wie, wann und, die der Fehler für die zugewiesen werden weitere überprüfen Überprüfen und Auflösung.

In der Regel enthält ein Fehler Bericht und-Wartung Plan Folgendes:

-   **Verfolgung-ID:** Die Nummer, die Ihnen für das Problem zugewiesen haben

-   **Verfolgung Beschreibung:** Zusammenfassung des Problems

-   **Priorität Assessment Verfolgung:** Die Ebene der Priorität einen Fehler für die Auflösung basierend auf geschäftlichen und defekt Schweregrad. Einige Beispiele:

-   **Niedrig:** Das Problem hat geringe Auswirkung auf verhindert, dass der Testphase Abnahme erreichen, wenn das Problem später aufgelöst werden kann.

-   **Mittel:** Das Problem hat beträchtliche Auswirkung auf verhindert, dass der Testphase Abnahme erreichen, wenn das Problem nicht aufgelöst werden kann.

-   **Hohe:** Das Problem wirkt sich wichtige auf verhindert, dass der Testphase Abnahme erreichen, wenn das Problem nicht aufgelöst werden kann.

-   **Zugewiesene defekt Besitzer:** Die Ressource aus, die zur Lösung dieses Problems zuständig ist, Testteam zugeordnet.

-   **Defekt Ausweitung Punkt zugewiesen:** Die Ressource zugewiesen, die auf Punkt für eskalieren das Problem in der Organisation (falls erforderlich) für die Lösung gesteuert wird. basierend auf Fehler Schweregrad

-   **Verfolgung Status:** Wurde das Problem behoben wurde, ist es geöffnet ist, oder noch in der Untersuchung

-   **Lösung nach Datum erforderlich:** Das Datum, die durch das Problem behoben werden muss

-   **Statusdatum:** Das Datum den letzten Zeitstatus spiegeln wurde als Ergebnis einer defekt Ursachenanalyse Überprüfung aktualisiert.

#### <a name="test-plan-defect-escalation"></a>Test Plan defekt Ausweitung

> [!TIP]
>   Es folgt ein Beispiel für einen Fehler Ausweitung Vorlage, die Sie Teil des Testplans verwenden können, um die Ausweitung-Prozess für die Priorisierung und Beheben von Fehlern testing erforderliche zu dokumentieren.

| Fehler-ID                                | Beschreibung des Fehlers                                                                                 | Fehler Priorität Bewertung                                           | Zugewiesene defekt Besitzer | Zugewiesene defekt Ausweitung Punkt | Fehler Ausweitung-Methode                                          | Fehler-status | Erforderliche Auflösung nach Datum | Statusdatum |
|------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1                                        | Wenn der Benutzer eine vierstellige Erweiterung eingibt, schlägt fehl, versucht, einen ausgehenden Anruf, setzen Sie der Anruf. | Mittel                                                               | Lisa grau             | Louis Lahr                       | Wöchentliche Ursachenanalyse überprüfen hoher Priorität e-Mails an betroffene beteiligten | Öffnen Sie die .          | ASAP                        | 1/12/2018   |



<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden, und der Fehler Prioritäten zur Unterstützung von Testplan vereinbaren.</li><li>Entscheiden Sie den Ausweitung Punkt für jeden Bereich Fehler.</li><li>Entscheiden Sie, die Fehler Eskalation und Ursachenanalyse Plan, denen Sie folgen, basierend auf Priorität.</li><li>Entscheiden Sie, die Fehler reporting und selektieren Sie Kommunikationsplans für Eskalation.</li><li>Entscheiden Sie der Fehler Ursachenanalyse Besprechung Trittfrequenz.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die Prioritäten vereinbart auf Fehler.</li><li>Den Ausweitung Punkt für jeden möglichen Fokusbereich des Dokuments.</li><li>Dokumentieren Sie den Fehler Eskalation und Ursachenanalyse Plan vereinbart auf Kriterien erfüllen.</li><li>Dokumentieren Sie Ihre reporting Richtlinien defekt.</li><li>Planen der Reihe von defekt Ursachenanalyse Besprechungen.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-deliverables"></a>Definieren Sie und Dokumentieren Sie testing Lieferumfang

Die letzte Komponente bei der Erstellung eines Testplans ist, die Ergebnisse im Hinblick auf bestimmte Lieferumfang zu identifizieren, die der allgemeine Plan zum Testen von zustellt.

Auf allgemeiner Ebene diese in der Regel umfassen, aber nicht beschränkt auf:

-   Plan zum Testen von

-   Testfälle

-   Fehler-Berichte

-   Ergebnisse der Zusammenfassung

-   Testen der Akzeptanz und Freigabe

#### <a name="test-plan-deliverables"></a>Test Plan Lieferumfang

> [!TIP]
>   Es folgt ein Beispiel für einen Test Plan Lieferumfang Matrix, die Sie verwenden können, um den Lieferumfang erstellt werden, sowie zur Prüfung, Genehmigung und Abnahme erforderlichen Ressourcen zu dokumentieren.

| Plan zum Testen des Lieferumfangs                    | Test Plan Lieferumfang format | Test Plan Lieferumfang Besitzer                                                                                                      | Test Plan Lieferumfang reviewer | Test Plan Lieferumfang genehmigende Person | Test Plan Lieferumfang Abnahme Datum |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Plan zum Testen von                                | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Fehler-Management-Berichte                | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Testen von Statusberichten                   | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Ergebnisse der Zusammenfassung                     | Word PPTX                    | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Lieferumfang erstellt und als Ausgabe aus jeder Testphase erfasst werden sollen. Für jede Lieferumfang, entscheiden Sie sich für die:<ul><li>Format</li><li>Besitzer</li><li>Prüfer</li><li>Eine genehmigende Person</li></ul></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Test Plan Lieferumfang Erstellung und Bereitstellung Matrix des Dokuments.</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Bewerten der Bereitschaft des Netzwerks
----------------------------

Als kritisch Element Unterstützung Ihrer Bereitstellung Teams ist die Bereitschaft des Netzwerks wichtiger Bestandteil der testen, um sicherzustellen, dass das Netzwerk ordnungsgemäß für die Unterstützung von Teams Communications optimiert ist. Um sicherzustellen, dass Ihr Netzwerk für die Websites im Bereich bereit ist, umfassen Sie die Schwerpunkte in Ihrer gesamten Teststrategie unten aufgeführten:

-   Bandbreitenschätzung und Planung mit Netzwerk Planner (über MyAdvisor)

-   Qualität der Überprüfung der Service (QoS)-Konfiguration

-   Überprüfen Sie Netzwerkkonnektivität und Leistung über Datenverkehr simulation

-   Validierung Split-tunneling

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Führen Sie für Websites und Rollen im Bereich Netzwerk Planner (über MyAdvisor)

Vor der Einführung in die Kommunikation in Echtzeit-Dienste wie Teams in Ihrer Umgebung, ist es wichtig, um sicherzustellen, dass das Netzwerk ordnungsgemäß optimiert und aus einer Azure ExpressRoute (falls zutreffend), Internet und WAN-Bandbreite Perspektive angepasst wurde.

Bei der Bestimmung des Bandbreite und Ebene der Netzwerk-Optimierung für Websites im Bereich Unterstützung Ihrer Bereitstellung erforderlich sind, führen Sie das Tool [Netzwerk Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) (über MyAdvisor) zum Überprüfen des Netzwerks Ihrer Organisation benötigt. Weitere Anleitungen zum Ermitteln der netzwerkanforderungen für Teams über das Netzwerk Planner, finden Sie unter MyAdvisor: Planner Netzwerk.

> [!TIP]
>   Weitere Informationen zu den **Empfehlungen** -Registerkarte Beispiele zum Konfigurieren und die Ergebnisse interpretieren finden Sie unter Network Planner [Recommendations Overview](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp).



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Netzwerkstandorten für die Bereitstellung von Teams im Bereich Dienste sind.</li><li>Entscheiden Sie die Rollen für Teams Modalitäten im Bereich erforderlich.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Führen Sie die Netzwerk-Planner (über MyAdvisor) für die Liste der Websites, die im Gültigkeitsbereich befinden.</li><li>Dokumentüberprüfung Netzwerk Planner führt der bereitgestellten Test Plan Ergebnisse Vorlage.</li><li>Überprüfen Sie, ob die ExpressRoute (falls zutreffend), Internet und WAN-Bandbreite, die für Websites in Bereich berechnet wurde Ausrichtung Bandbreitenwerte, die derzeit zugeordnet sind.</li><li>Führen Sie für Websites, die nicht über eine ausreichende Bandbreite verfügen die Ausweitung und-Wartung Pläne und Bandbreitenprobleme zu beheben.</li><li>Richten Sie ein Netzwerk-Lösung für Websites im Bereich zur Auslastung der Bandbreite überwachen und QoS für ExpressRoute (falls zutreffend), Internet und WAN-Segmenten monitoring.</li><li>Planen einer Besprechung Lenkungsausschuss Netzwerk Planner Ergebnisse zu überprüfen.</li><li>Präsentieren Sie Bandbreite, die Planung der Ergebnisse des Verwaltungshaushaltsplans, Bereiche zu identifizieren, die Behebung erforderlich machen.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Bewerten der QoS-Konfiguration für Websites im Bereich
---------------------------------------------

Im Rahmen der Auswertung Bereitschaft des Netzwerks für die Unterstützung von Teams Real-Time Communications, es ist gleichermaßen wichtig, um sicherzustellen, dass das Netzwerk ordnungsgemäß konfiguriert und aus Sicht der QoS optimiert wurde.

Zusätzliche Anleitung zum Konfigurieren, bereitstellen und Überprüfen von QoS-Netzwerks für Teams mithilfe von Gruppenrichtlinien finden Sie unter [Aktivieren von QoS für Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Legen Sie die QoS-Konfiguration implementiert werden.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Konfigurieren von QoS.</li><li>QoS-Überprüfung ausführen, wie von über die "Überprüfen über GPO" beschriebenen Schritte beschrieben und "Überprüfen über Nachricht Analyzer" Abschnitte oben.</li></ul></td></tr>
</table>


### <a name="document-qos-configuration-validation-test-results"></a>Dokumentieren Sie QoS-Konfiguration Validierung Testergebnisse

Nach Abschluss QoS Validierungstests mithilfe von Gruppenrichtlinien für Websites in Bereich erstellen Sie einen Bericht, der während der letzten Lenkungsausschuss Überprüfung durchzuführen Testergebnisse zusammengefasst.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>A: Website QoS-Konfiguration Validierungstests Zusammenfassungsbericht

> [!TIP]
>   Es folgt ein Beispiel testen Zusammenfassungsbericht-Vorlage, die Sie während der nächsten Besprechung Lenkungsausschuss überprüfen können, wenn Sie in der Pilotphase zur integrierten Telefonsystem mit Aufrufen plant Services entscheiden.


**Überprüfung der QoS-Konfiguration über GPO und Nachricht Analyzer**

**Zusammenfassung**:&nbsp;&nbsp;&nbsp;& #9744; Übergeben Sie&nbsp; &nbsp; &nbsp; & #9744; Teilweise&nbsp; &nbsp; &nbsp; & #9744; Ein Fehler auftritt

<table>
<tr><th colspan="2">Testen der highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen der Schwachstellen  </th></tr>  
<tr><td>**Problem**: TBD</td><td>**Remediation:** TBD</td></tr>
<tr><th colspan="2">Identifiziert Popupblockern </td></tr>
<tr><td>**Blockierenden Person**: TBD</td><td>**Remediation**: TBD</td></tr>
</table>


> [!TIP]
> Um weitere Erörterung während der letzten Lenkungsausschuss Überprüfung zu erleichtern, können Sie die aktualisierte [Testergebnisse Matrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) von [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) zu dokumentieren und markieren Sie weitere Bereiche, die Wartung erfordern.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Bewerten der Testergebnisse QoS, um sicherzustellen, dass in Echtzeit Mediendatenverkehr ordnungsgemäß wird Teams markiert und priorisiert.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokument QoS Testergebnisse in der Test Plan Ergebnis Vorlage zur Verfügung gestellt.</li><li>Ausweitung und-Wartung Pläne und Probleme zu beheben, wobei QoS möglicherweise nicht ordnungsgemäß konfiguriert oder ist nicht zur Unterstützung von Teams Mediendatenverkehr arbeiten wie erwartet, ausgeführt werden.</li></ul></td></tr><li>Planen einer Besprechung Lenkungsausschuss Zusammenfassung Testergebnisse überprüfen.</li><li>Vorhanden Zusammenfassung Testergebnissen Lenkungsausschusses, Bereiche zu identifizieren, die Behebung erforderlich machen.</li>
</table>


<a name="execute-split-tunnel-enablement-validation"></a>Split-Tunnel-Aktivierung-Überprüfung ausführen
------------------------------------------

Es ist üblich für Unternehmen heute eine einen oder mehrere Lösungen für die Bereitstellung von Remotezugriff, ein virtuelles privates Netzwerk oder VPN. Diese Lösungen ermöglichen die Konnektivität mit internen Line-of-Business-Ressourcen und Anwendungen, sicher und zuverlässig.

Obwohl RAS-Lösungen sehr gut für den Zugriff auf einige Anwendungen erhält, wenn es darum geht, tunneling in Echtzeit Mediendatenverkehr Teams arbeiten können, bewirken diese Lösungen häufig ein kleiner als optimale Benutzererlebnis für alle Teilnehmer an einer Audio Teams Konferenzen oder aufrufende Szenario.

Um sicherzustellen, dass Teams Mediendatenverkehr *nicht* durchsuchenden RAS-Lösungen in der Umgebung ist, wird eine Split-Tunnel-Konfiguration erforderlich sein.

Weitere Anleitungen zum Konfigurieren und Überprüfen der Bereitschaft des Netzwerks der Split-Tunnel Konfiguration für Teams finden Sie unter Bereitschaft des [Netzwerks](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!NOTE]
>   Aufgrund des Volumens der RAS-Lösungen im Marketplace zur Verfügung dieses Dokument nicht herstellerspezifischen Details bereitstellen, RAS-Lösungen sollte nur allgemeine Richtlinien zur was konfiguriert werden.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, die Split-Tunnel Konfiguration zu implementieren.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Split-Tunnel Konfiguration zu implementieren.</li><li>Testen und Überprüfen der Konfiguration des Split-Tunnel.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Dokument Split-Tunnel Konfiguration Validierung Testergebnisse

Nach Abschluss Split-Tunnel Testkonfiguration für Websites in Bereich erstellen Sie einen Bericht, der Testergebnisse zusammengefasst und bei der nächsten Lenkungsausschuss Überprüfung.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>A: Website Split-Tunnel Konfiguration Validierungstests Zusammenfassungsbericht

> [!TIP]
>   Es folgt ein Beispiel testen Zusammenfassungsbericht-Vorlage, die Sie während der nächsten Besprechung Lenkungsausschuss überprüfen können, wenn Sie in der Pilotphase zur integrierten Telefonsystem mit Aufrufen plant Services entscheiden.

**Überprüfung der Split-Tunnel-Konfiguration**

**Zusammenfassung**:&nbsp;&nbsp;&nbsp;& #9744; Übergeben Sie&nbsp; &nbsp; &nbsp; & #9744; Teilweise&nbsp; &nbsp; &nbsp; & #9744; Ein Fehler auftritt

<table>
<tr><th colspan="2">Testen der highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen der Schwachstellen  </th></tr>  
<tr><td>**Problem**: TBD</td><td>**Remediation:** TBD</td></tr>
<tr><th colspan="2">Identifiziert Popupblockern </td></tr>
<tr><td>**Blockierenden Person**: TBD</td><td>**Remediation**: TBD</td></tr>
</table>


> [!TIP]
> Um weitere Erörterung während der letzten Lenkungsausschuss Überprüfung zu erleichtern, können Sie die aktualisierte [Testergebnisse Matrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) von [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) zu dokumentieren und markieren Sie weitere Bereiche, die Wartung erfordern.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Bewerten der Testergebnisse Split-Tunnel, um sicherzustellen, dass Teams in Echtzeit-Datenverkehr vom RAS-Lösung ausgeschlossen wird.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Split-Tunnel Connectivity Testergebnisse in der bereitgestellten Test Plan Ergebnis Vorlage des Dokuments.</li><li>Führen Sie Eskalation und-Wartung Pläne und Probleme zu beheben, auf dem ordnungsgemäßes routing existiert nicht für die Unterstützung von Teams Medien in einer geteilten Tunnel-Konfiguration.</li><li>Planen einer Besprechung Lenkungsausschuss Zusammenfassung Testergebnisse überprüfen.</li><li>Vorhanden Zusammenfassung Testergebnissen Lenkungsausschusses, Bereiche zu identifizieren, die Behebung erforderlich machen.</li></ul></td></tr>
</table>


<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Führen Sie Netzwerk und die Leistung Validierung mithilfe des Tools zur Bewertung Netzwerk von Microsoft
-----------------------------------------------------------------------------------------------------------

Das Netzwerk-Assessment-Tool von Microsoft führt Datenverkehr Simulation und Konnektivität Tests durch streaming simulierten audiopakete, für einen vordefinierten Zeitraum und die Anzahl von Iterationen, auf die nächste Edge-Website, die Konnektivität mit dem Dienst Teams bereitstellt. Ein Ziel dieses Tests ist für Netzwerk Leistungsmetriken für Paketverlust, Jitter, die Roundtrip-Wartezeit und Paket neu anordnen Prozent für jeden Anruf simulierten ausgewertet werden soll. Darüber hinaus der Test überprüft, dass ordnungsgemäße Konnektivität zwischen internen zulässig ist und edge-Netzwerkelementen zu alle Edge eingehende Punkte, die Verbindung mit Teams Dienste unterstützen.

Zusätzliche Hinweise zum Bestätigen und Auswerten von Teams Bereitschaft des Netzwerks für festgelegte Websites im Gültigkeitsbereich finden Sie unter Bereitschaft des [Netzwerks](https://docs.microsoft.com/MicrosoftTeams/prepare-network) .

> [!TIP]
>   Zum Ausführen von Netzwerk-Bereitschaft Analyse und Bereitschaft für Websites im Bereich bestimmen Sie ein potenziellen Kunden für jeden Standort, die mit Ihrer Netzwerk Bereitschaft Evaluation sind hilfreich sein kann.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie dem Netzwerk Assessment and Connectivity testing Profil für Websites in Bereich.</li><li>Entscheiden Sie Netzwerk Assessment Datei konfigurationsanforderungen für Websites im Bereich.</li></ol></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Konfigurieren Sie im Bereich Assessment Konfiguration Datei netzwerkanforderungen für die Websites.</li><li>Führen Sie im Bereich Netzwerk Leistung und Konnektivität Überprüfung für Websites.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Dokument-Netzwerk und die Leistung Validierung Testergebnisse

Nachdem Sie alle Netzwerkkonnektivität und Testen der Leistung für die Websites im Bereich abgeschlossen haben, Erstellen eines Berichts, das Testergebnisse zusammengefasst und bei der nächsten Lenkungsausschuss Überprüfung.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>A: Netzwerk und die Leistung Websiteübersichtsbericht

> [!TIP]
> Im folgenden ist eine Beispiel-Netzwerk und die Leistung Zusammenfassung Vorlage, die Sie bei der nächsten Lenkungsausschuss Überprüfung verwenden können, bei der Entscheidung sind allgemeine Bereitschaft des Netzwerks für Websites im Bereich.

**Standort: Seattle [inneren verkabelt] Client für Office 365-Ergebnisse**

**Zusammenfassung**:&nbsp;&nbsp;&nbsp;& #9744; Übergeben Sie&nbsp; &nbsp; &nbsp; & #9744; Teilweise&nbsp; &nbsp; &nbsp; & #9744; Ein Fehler auftritt 



| Metrik                                                        |  Target                                                                                                            | Weekday: Geschäftszeiten 9:30 Uhr bis 11:00                                                                                                                                                                                                                                                                                                 | Weekday: Geschäftszeiten 14:30 Uhr bis 4:30 Uhr | Weekday: nach Stunden 10:30 Uhr auf 12:30 Uhr ausgeführt. | Wochenende: nach Stunden 9:30 Uhr um 11:30 Uhr ausgeführt. | Wochenende: nach Stunden 14:30 Uhr bis 4:30 Uhr |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latenz (ein Weg)                                             | \<50 ms                                                                                                           | 40 ms                                                                                                                                                                                                                                                                                                                                     | 38 ms                                    | 41 ms                                     | 35 ms                                    | 36 ms                                   |
| Wartezeit (Roundtripzeit oder Zeit)                             | \<100 ms                                                                                                          | 81 ms                                                                                                                                                                                                                                                                                                                                     | 77 ms                                    | 80 ms                                     | 72 ms                                    | 70 ms                                   |
| Burstverlust von Paketen                                             | \<10 % Intervall 200 ms                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | 2 %                                       | 2 %                                        | 0.2 %                                     | 0,1 %                                    |
| Paketverlust                                                   | \<1 % Intervall 15 s                                                                                   | 0,4 %                                                                                                                                                                                                                                                                                                                                      | 0,3 %                                     | 0,3 %                                      | 0,1 %                                     | 0 %                                      |
| Die Kommunikation zwischen hinzukommen Jitter Paket                                   | \<während ein Intervall von 15 s 30 ms                                                                                | 12 ms                                                                                                                                                                                                                                                                                                                                     | 11 ms                                    | 13 ms                                     | 5 ms                                     | 5 ms                                    |
| Neuanordnung von Paketen                                                | \<0,05 % außerhalb der Reihenfolge Pakete                                                                                      | 0 %                                                                                                                                                                                                                                                                                                                                        | 0 %                                       | 0 %                                        | 0 %                                       | 0 %                                      |



<table>
<tr><th colspan="2">Testen der highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen der Schwachstellen  </th></tr> 
<tr><td>**Problem**: hoher Wartezeit</td><td>**Remediation:** Untersuchen Sie die Paket-routing, und implementieren Sie die optimale Route.</td></tr>
<tr><td>**Problem**: Roundtripzeit ist nicht doppelt die Wartezeit</td><td>**Remediation:** Überprüfen Sie eine mögliche Firewall oder dem Router Konfigurationsproblem. Untersuchen Sie Datenverkehr Pfade.</td></tr>
<tr><td>**Problem**: hohe Paketverluste </td><td>**Remediation:** Überprüfen Sie, ob über das Netzwerk Planner genügend Bandbreite zugewiesen wurde. </td></tr>
<tr><td>**Problem**: hohe Jitter </td><td> **Remediation:** Überprüfen Sie, ob die richtigen differentiated Services Code Point (DSCP)-Werte verwendet werden. </td></tr>
<tr><td>**Problem**: hohe Paketverluste </td><td>**Remediation:** Untersuchen von Paketverlusten. </td></tr>
<tr><td>**Problem**: hohe Paket neu anordnen </td><td>**Remediation:** Untersuchen Sie Router Berichterstellungsdienst und Bandbreite. </td></tr>
<tr><th colspan="2">Identifiziert Popupblockern </td></tr>
<tr><td>**Blockierenden Person**: TBD</td><td>**Remediation**: TBD</td></tr>
</table>

 


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Bewerten der Netzwerk-Bewertung und Konnektivität testen Ergebnisse, um sicherzustellen, dass Sie die in [der Leistung für die Qualität und Netzwerk Konnektivität Medien](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) für die Edge-Segment und den Client Segmente beschriebenen Anforderungen erfüllen.</li><li>Haben Sie Netzwerkfunktionen zur Unterstützung von Real-Time Media für alle Websites in Bereich ausgewertet?</li><li> Wenn Ihr Netzwerk ordnungsgemäß bewertet wurde noch nicht oder wissen Sie, dass in Echtzeit Medien wird nicht unterstützt, wird Video deaktivieren und Bildschirmfreigabe-Funktionen zur Reduzierung von Netzwerk auswirken und Verbessern der benutzerfreundlichkeit von Teams für Benutzer?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Leistung des Netzwerks und Konnektivität Testergebnisse des Dokuments.</li><li>Ausweitung und-Wartung Pläne und Behandeln von Problemen mit Websites, in dem es steht nicht genügend Bandbreite oder Leistung und Konnektivität netzwerkanforderungen erfüllt werden nicht, ausgeführt.</li><li>Planen einer Besprechung Lenkungsausschuss Zusammenfassung Testergebnisse überprüfen.</li><li>Vorhanden Zusammenfassung Testergebnissen Lenkungsausschusses, Bereiche zu identifizieren, die Behebung erforderlich machen.</li></ul></td></tr>
</table>


<a name="execute-subscriber-number-port-validation"></a>Führen Sie den Teilnehmerzugriff Port Prüfung
-----------------------------------------

Wenn Sie zum Übertragen von Zahlen im Rahmen der Bereitstellung von eingehenden und ausgehenden aufrufende Funktionen in Telefonsystem mit Aufrufen plant Services unterstützt von Teams benötigen, sollten Sie einen partiellen Port für eine Zahl Service durchführen. Dies hilft Ihnen die erwartete sowie Anforderungen und angemessene Zeitachse zu überprüfen, wie Sie die Vorbereitung der bereitstellungs von Telefonsystem mit Aufrufen plant Services in Ihrer produktionsumgebung abgeschlossen.

Um eine partielle Port eine Teilnehmernummer aus Ihrer aktuellen PSTN-Dienstanbieter Teams abgeschlossen haben, durchlaufen Sie die unten beschriebenen Schritte aus.

#### <a name="step-1"></a>Schritt 1

Identifizieren Sie die Test-Nummer, die an den port zu Office 365 als Zahl (Teilnehmernummer) zugeordnet werden Benutzer, die über das Telefonsystem mit Aufrufen plant Service in Teams gewartet werden soll.

> [!IMPORTANT]
>Bei der Planung Ihrer Nummern Portieren Test werden Sie die neuesten Richtlinien für Nummern Portieren Anforderungen in [Anzahl Port häufig gestellte Fragen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)zu überprüfen.

#### <a name="step-2"></a>Schritt 2

Identifizieren Sie und Dokumentieren Sie alle Kontoinformationen (einschließlich des Namens, der für das jeweilige Konto verwendet) für die aktuelle Netzbetreiber der Testzahl, die Sie benötigen Portieren werden.
In der Regel finden Sie die Informationen in der neuesten Bill oder Rechnung müssen vom aktuellen Dienstanbieter.

> [!TIP]
>   Sie können portieren oder Übertragung von Telefonnummern in allen derzeit Länder/Regionen unterstützt; möglicherweise die Möglichkeit, die Sie eine Port Reihenfolge Anforderung übermitteln, je nach Land/Region unterscheiden sich jedoch, in dem die Telefonnummern aus Quelle werden. Die aktuelle Liste der derzeit unterstützte Länder/Regionen finden Sie unter [Ländern und Region Verfügbarkeit für Audiokonferenzen und plant aufrufen](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).

>   Weitere Informationen zum Übertragen von Telefonnummern an Telefonsystem mit Aufrufen plant – zusammen mit potenziellen Einschränkungen – finden Sie unter [Weiterleiten von Telefonnummern zu Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) und [gebührenfreie kostenlose einwählen Einschränkungen in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Schritt 3

Herunterladen Sie und erstellen Sie einen Buchstaben der Autorisierung (Geladene) für Ihr Land/Region, die als Zahl Portieren Typ auf "Service Anzahl" basiert.

>[!NOTE]
>   Da Geladene Formate nach Land, Region oder Datentyp Zahl unterscheiden können (, ist im Vergleich zu nicht geografische geografische oder Benutzer im Vergleich zu Dienst oder gebührenfreie Nummer), stellen Sie sicher, dass Sie die richtige Geladene Dokumentvorlage für den bestimmten Szenarios Typ verwenden. Finden Sie weitere Informationen zur Auswahl der Geladene [Buchstaben der Autorisierung (Geladene) herunterladen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) , oder rufen Sie direkt die [Downloadseite](https://www.microsoft.com/download/details.aspx?id=49167).

>[!NOTE]
> **Nur USA**<br/>
>   Da wir eine Service-Nummer für diesen Test nur Portieren sind, müssen Sie die entsprechenden Felder in das Geladene wie folgt aus:

![Wie viele Rufnummern sollen Sie übertragen werden? Antwort: Ich bin nur übertragen einiger Meine Zahlen aus der aktuellen meines.] (media/onboarding-test-plan-image1.png "Wie viele Rufnummern sollen Sie übertragen werden? Antwort: Ich bin nur übertragen einiger Meine Zahlen aus der aktuellen meines.")

![Welche Art von Rufnummern sollen Sie übertragen werden? Antwort: Ich bin VoIP-Dienst Rufnummern wie für automatische Telefonzentralen oder Konferenzbrücken übertragen.] (media/onboarding-test-plan-image2.png "Welche Art von Rufnummern sollen Sie übertragen werden? Antwort: Ich bin VoIP-Dienst Rufnummern wie für automatische Telefonzentralen oder Konferenzbrücken übertragen.")

>[!IMPORTANT]
>   Wenn Sie Rufnummern manuell mithilfe eines Geladene port, stellen Sie sicher, dass Sie den korrekten Typ der Telefonnummer auswählen. Sie müssen für jede zur Übertragung vorgesehene Art von Telefonnummer einen separaten Portierungsauftrag einreichen.<br/><br/>
>   Da wir die Anzahl Portieren Prozess mithilfe einer dieselbe Art der Rechnungslegung Telefonnummer (BTN) zugeordneten Telefonnummer testen möchten, müssen Sie sicherstellen, dass die Art der Rechnungslegung Telefonnummer ist *nicht* enthalten, mit der bestimmte Telefonnummer übertragen wird.

#### <a name="step-4"></a>Schritt 4

Wechseln zur Registerkarte **Unterstützung** dem Mandanten-Verwaltungsportal erstellen und Übermitteln einer Anforderung. Fügen Sie der abgeschlossenen Geladene Datei so planen Sie die Telefonnummer für die Migration Ihrer aktuellen Dienstanbieter zugeordnet. Die Service-Anforderung-Methode für die Größe Ihres Mandanten am besten geeigneten finden Sie unter [einer benutzerdefinierten Anforderung manuell zu senden](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Nachdem die Support-Anforderung empfangen wurde, wird Microsoft Support nachverfolgung basierend auf der Kommunikationsmethode ausgewählt haben und empfehlen Ihnen der Status und weitere Schritte für Nummern Portieren Vorgang wird beendet.

#### <a name="step-5"></a>Schritt 5

Nachdem die Anzahl als müssen über übertragen wurde, als eine neue Teilnehmernummer in Office 365 bestätigt wurde, weisen Sie die Anzahl das Telefonsystem mit Dienst aufrufen plant durch das Aufrufen der Mandanten-Verwaltungsportal \> **Skype für Business Admin Center** \> ** VoIP**. Klicken Sie auf der Registerkarte **Rufnummern** weisen Sie die neue Servicenummer das Telefonsystem mit Dienst plant aufrufen.

> [!TIP]
>   Obwohl diese Aufgabe eine neue Servicenummer Telefonsystem mit Aufrufen plant, zum Zeitpunkt der Erstellung dieses Dokuments zugewiesen wird, wird die Verwaltung für diese Aufgabe abgeschlossen, mithilfe der Skype für Business Administrationscenter.

#### <a name="step-6"></a>Schritt 6

Nun, dass Sie die Port aus Teilnehmernummer zugewiesen haben, melden Sie sich an einen Client Teams, wie der Benutzer und wählen Sie eine externe Nummer 10 Ziffern über das PSTN ein. Nachdem Sie den Anruf zu tätigen, vergewissern Sie sich, dass der Anruf verbunden wurde und dass die angezeigten Anrufer-ID die Teilnehmernummer entspricht, die Sie übertragen.

#### <a name="step-7"></a>Schritt 7

Eine externe PSTN-Nummer einen Anruf an die Rufnummer des Teilnehmers, dass Sie in Office 365 übertragen, und stellen Sie sicher, dass den Anruf empfangen hat eingehenden und über die Teams Client verbunden ist.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche nationalen Abonnenten Nummern, die Sie nach Land/Region auf Port, benötigen.</li><li>Entscheiden Sie, welche Geladene Vorlage, die Sie verwenden möchten.</li><li>Bestimmen, ob Ihre aktuellen Netzbetreiber (riskieren Netzbetreiber) Phone Number Fragmentierung zulässt (d. h., Partial-Port Orders erlaubt).</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Sammeln Sie die erforderliche Informationen und Vorbereiten Sie die Koordinations.</li><li>Herunterladen Sie, und schließen Sie die Geladene Vorlagen, die Sie benötigen.</li><li>Fordern Sie ein Abonnenten Zahl portieren.</li><li>Führen Sie Test Validierung Port aus Zahlen, indem Sie das Telefonsystem mit Aufrufen plant Service für DFÜ-Zugriff zuweisen, und vergewissern Sie sich, dass sie funktionieren, wie in Schritt 6 und 7 weiter oben in diesem Abschnitt beschrieben.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Dokumentieren Sie Testergebnisse Portieren Service-Nummer

Nachdem Sie alle Abonnenten Zahl Tests abgeschlossen haben, erstellen Sie einen Bericht, der eine Zusammenfassung Testergebnisse während der nächsten Lenkungsausschuß Überprüfung durchzuführen.

#### <a name="site-a-number-porting-test-summary-report"></a>A: Nummer Test Zusammenfassungsbericht Portieren

> [!TIP]
>   Es folgt ein Beispiel Test Berichtsvorlage summary, mit denen Sie zur Überprüfung während der nächsten Besprechung Lenkungsausschuss Wenn Sie in der Pilotphase zur integrierten Telefonsystem mit Aufrufen plant Services entscheiden.

**Portieren Service-Nummer**

**Zusammenfassung**:&nbsp;&nbsp;&nbsp;& #9744; Übergeben Sie&nbsp; &nbsp; &nbsp; & #9744; Teilweise&nbsp; &nbsp; &nbsp; & #9744; Ein Fehler auftritt 

<table>
<tr><th colspan="2">Testen der highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen der Schwachstellen  </th></tr>  
<tr><td>**Problem**: TBD</td><td>**Remediation:** TBD</td></tr>
<tr><th colspan="2">Identifiziert Popupblockern </td></tr>
<tr><td>**Blockierenden Person**: TBD</td><td>**Remediation**: TBD</td></tr>
</table>


> [!TIP]
>   Um weitere Erörterung während der letzten Lenkungsausschuss Überprüfung zu erleichtern, können Sie die aktualisierte [Testergebnisse Matrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) bereitgestellt von [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) zu dokumentieren und markieren Sie zusätzliche Test Bereiche, die Behebung erforderlich machen.


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Überprüfen Sie, ob Abonnenten Zahlen übermittelt für die Migration erfolgreich in das Telefonsystem mit Aufrufen plant Dienst übertragen wurden.</li><li>Überprüfen Sie, ob Sie das Telefonsystem mit Dienst aufrufen plant übertragen Service Number zuweisen konnten.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Die Nummer Ihres Portieren Testergebnisse des Dokuments.</li><li>Führen Sie die Ausweitung und-Wartung Pläne und zu beheben, mit denen, die Sie die Nummer Portieren Prozess vertraut, sofern vorhanden.</li><li>Planen einer Besprechung Lenkungsausschuss Zusammenfassung Testergebnisse überprüfen.</li><li>Stellen Sie die Zusammenfassung Testergebnisse des Verwaltungshaushaltsplans, Bereiche zu identifizieren, die Behebung erforderlich machen.</li></ul></td></tr>
</table>


<a name="execute-your-test-plan-for-phone-system-with-calling-plans"></a>Testplan für Telefonsystem mit Aufrufen plant ausführen
----------------------------------------------------------

Nun, da Sie Testplan definiert haben, im nächsten Schritt wird die Testfälle durchlaufen, Konzentration auf die Auswertung der Telefonsystem mit Aufrufen plant Verwaltungs- und Benutzer erleben Sie die Funktionen im Bereich. Vor dem Testen tatsächlich begonnen hat, stellen Sie sicher, dass die unten aufgeführten testing erforderlichen Komponenten vorhanden sind.

### <a name="phone-system-with-calling-plans-testing-prerequisites"></a>Telefonsystem mit Aufrufen plant testen erforderliche Komponenten

-   Anwendungsbeispiele wurden für das Telefonsystem mit Dienst aufrufen plant definiert.

-   Der verantwortlichen wurden identifiziert.

-   Die Lizenzierung für Telefonsystem mit Services aufrufen Pläne erforderlich ist und für die Gruppe von Benutzern im Bereich zugewiesen wurde.

-   Die Liste der Organisationseinheit Websites und Benutzergruppen in den Bereich ermittelt wurden.

-   [Communications haben](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (falls erforderlich) Ihrer Organisation eingerichtet wurden.

-   Telefonsystem mit Einstellungen aufrufen plant identifiziert und konfiguriert wurden.

-   Mandanten-Wählplan Einstellungen, die mit Aufrufen plant Telefonsystem unterstützen identifiziert, konfiguriert und für die Gruppe von Benutzern im Bereich angewendet wurde.

-   Telefonsystem mit Richtlinien plant aufrufen identifiziert und für die Gruppe von Benutzern im Bereich konfiguriert wurden.

-   Telefonsystem mit Aufrufen plant, Compliance-Bestimmungen identifiziert und für die Gruppe von Benutzern im Bereich konfiguriert wurden.

### <a name="document-phone-system-with-calling-plans-test-case-passfail-status"></a>Dokument Telefonsystem mit Aufrufen plant Testfall bestanden wurden oder status

Testfälle für die administrative Teams und Benutzer System Telefonfunktionen im Bereich ausgewertet werden, verfolgen Sie die Ergebnisse der einzelnen Testfälle gemäß Durchlauf/Partial/Fail-Status, zusammen mit der zugewiesenen ID für die Fehler, für den Fall, dass unvorhergesehene Probleme auftreten.

#### <a name="phone-system-with-calling-plans-test-case-status"></a>Telefonsystem mit Aufrufen plant Testfallstatus

> [!TIP]
>   Es folgt eine Testfall Status Beispielvorlage, mit denen Sie können Testergebnisse Dokument zur Überprüfung während der nächsten Besprechung Lenkungsausschuss Wenn Sie in der Pilotphase zur integrierten Telefonsystem mit Aufrufen plant Services entscheiden.

| Telefonsystem mit Anrufplänen          |                              |                                                                                            |                           |                                                                            |
|------------------------------------------|------------------------------|--------------------------------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------|
| Testfall-ID                             | Testfall Titel              | Testfall Beschreibung                                                                      | Ergebnisse des Testfalls Zusammenfassung | Zugewiesene Fehler-ID (falls zutreffend)                                         |
| 1                                        | Das ausgehende PSTN-Anrufe tätigen. | Tätigen eines ausgehenden Anrufs durch Wählen einer Rufnummer für nationalen 10 Ziffern.                              |    & #9744; Übergeben Sie<br/>& #9744; Teilweise<br/> & #9744; Ein Fehler auftritt                   | Wenn ein Benutzer eine vierstellige Zahl eingibt, schlägt fehl, der Anruf an das Telefonfestnetz platziert. |



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Evaluieren Sie allgemeine Testfall bestanden wurden oder Status nach Standort für Telefonsystem mit Aufrufen plant Features im Bereich.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die Testfall Statusergebnisse für alle Testfälle im Bereich abgeschlossen wurde.</li><li>Planen einer Besprechung Lenkungsausschuss Zusammenfassung Testergebnisse überprüfen.</li><li>Darstellen Sie Ergebnisse des Testfalls Status des Verwaltungshaushaltsplans alle Bereiche identifiziert, die erfordern Remediation.</li></ul></td></tr>
</table>


### <a name="document-phone-system-with-calling-plans-testing-result-summary"></a>Dokument Telefonsystem mit Aufrufen plant Ergebnis Zusammenfassung testen

Nachdem alle Testfälle Telefonsystem mit Aufrufen plant Features im Bereich Unterstützung von Website abgeschlossen Sie wurden, dokumentieren Sie die Ergebnisse während einer Besprechung Lenkungsausschuss zu überprüfen, wenn Sie mit plant Aufrufen von Webdiensten in der Pilotphase Telefonsystem aktiviert entscheiden Phase.

#### <a name="site-a-phone-system-with-calling-plans-test-case-summary-report"></a>A: Website Phone System aufrufen plant Testfall zusammenfassenden Bericht über:

> [!TIP]
>   Es folgt ein Beispiel Test Berichtsvorlage summary, die Sie während der nächsten Besprechung Lenkungsausschuss überprüfen können, wenn Sie in der Pilotphase zur integrierten Telefonsystem mit Aufrufen plant Services entscheiden.


**Teams Telefonsystem mit dem Aufrufen der Pläne**

**Zusammenfassung**:&nbsp;&nbsp;&nbsp;& #9744; Übergeben Sie&nbsp; &nbsp; &nbsp; & #9744; Teilweise&nbsp; &nbsp; &nbsp; & #9744; Ein Fehler auftritt 

<table>
<tr><th colspan="2">Testen der highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen der Schwachstellen  </th></tr>  
<tr><td>**Problem**: TBD</td><td>**Remediation:** TBD</td></tr>
<tr><th colspan="2">Identifiziert Popupblockern </td></tr>
<tr><td>**Blockierenden Person**: TBD</td><td>**Remediation**: TBD</td></tr>
</table>


> [!TIP]
>   Um weitere Erörterung während der letzten Lenkungsausschuss Überprüfung zu erleichtern, können Sie die aktualisierte [Testergebnisse Matrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) von [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) bereitgestellten zu dokumentieren und markieren Sie weitere Bereiche, die Remediation erfordern.



<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Bewerten der allgemeine Zusammenfassung-Testergebnisse nach Standort für Telefonsystem mit Aufrufen plant Features im Bereich.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie Testfall Zusammenfassungsbericht, nachdem alle Ergebnisse des Testfalls abgeschlossen wurden.</li><li>Planen einer Besprechung Lenkungsausschuss Zusammenfassung Testergebnisse überprüfen.</li><li>Vorhanden Zusammenfassung Testergebnissen Lenkungsausschusses, Bereiche zu identifizieren, die Behebung erforderlich machen.</li></ul></td></tr>
</table>



<a name="present-and-report-phone-system-with-calling-plans-test-findings"></a>Präsentieren und Bericht Telefonsystem mit Testergebnisse plant aufrufen
----------------------------------------------------------------

Nachdem alle Testaktivitäten abgeschlossen wurden und Mängel mit niedrig wirkt sich behoben wurden, Planen einer Besprechung endgültigen ist abgeschlossen, mit festgelegten testing Beteiligten. In der Besprechung zu beheben:

-   Status überprüfen

-   Hervorheben/Schwachstellen

-   Gelernte Lektionen

-   Allgemeine Empfehlung – fahren Sie mit der Pilotphase oder neu auswerten Testergebnisse?

-   Matrix Testergebnisse (diese sollte vollständig in einem Anhang dokumentiert werden)

#### <a name="test-plan-deliverables"></a>Test Plan Lieferumfang:

> [!TIP]
>   Es folgt ein Beispiel für einen Plan zum Testen des Lieferumfangs Vorlage, die Sie verwenden können, um die Kriterien zu dokumentieren erforderlich, um Abnahme zu erzielen und Beenden der Testphase oder angehalten werden soll, bis alle identifizierte Problemen vollständig aufgelöster sind testen.

| Status überprüfen               | Highlights/Schwachstellen | Gelernte Lektionen | Schließen die Empfehlung |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Testfall Durchlauf Satz von TBD %</li><li>Alle Tests übergeben</li></ul> | TBD                  | TBD             | Fahren Sie mit der Pilotphase       |

-   Alle Tests übergeben


<table>
<tr><td>![](media/audio_conferencing_image7.png)<br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie den Zusammenfassung Teststatus.</li><li>Testen von Highlights und Schwachstellen zu identifizieren.</li><li>Gelernte Lektionen zu identifizieren.</li><li>Entscheiden Sie, welche Remediation Aktionen bleiben, falls vorhanden.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Dokument Zusammenfassung Testergebnisse enthalten:<ul><li>Status überprüfen</li><li>Highlights/Schwachstellen</li><li>Gelernte Lektionen</li></ul></li><li>Planen einer Besprechung endgültigen Lenkungsausschuss Testergebnisse überprüfen.</li><li>Vorhanden Zusammenfassung Testergebnisse während einer Lenkungsausschuss überprüfen endgültigen Genehmigung für das Beenden der Testphase abrufen.</li></ul></td></tr>
</table>