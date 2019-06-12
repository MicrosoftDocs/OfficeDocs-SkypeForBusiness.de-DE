---
title: Enterprise-Testplan für Telefonsysteme mit Anrufplänen in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Überprüfen Sie, ob die Erwartungen Ihrer Organisation erfüllt sind, indem Sie das Telefon System in den Funktionen, Funktionen und der Benutzerfreundlichkeit von Teams testen.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1534c1b327e7fda146894430ca750f01c53e8fa4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898754"
---
<a name="define-and-document-your-phone-system-with-calling-plans-in-teams-test-plan-for-enterprises"></a>Definieren und dokumentieren Ihres Telefonsystems mit Anrufplänen in Teams Testplan für Unternehmen 
============================================================================================

Nachdem Sie Ihr Telefon System mit Anrufplänen in den Plänen für Geschäftserfolg und technische Implementierung von Teams im Rahmen der enVision-Phase definiert und dokumentiert haben, besteht der nächste Schritt darin, zu überprüfen, ob die Erwartungen und Anforderungen Ihrer Organisation erfüllt werden. Feature, Funktionalität und Benutzerfreundlichkeit. Sie sollten diesen Validierungsschritt durchführen, bevor Sie eine Pilot-oder endgültige Bereitstellung in Ihrer Produktionsumgebung bereitstellen.

Sie können den Geschäftserfolgs Plan, den Sie während der enVision-Phase definiert haben, als Grundlage für die Ermittlung der Aktivitäten, Erwartungen, Funktions-/Funktionstest Fälle und des Gesamtumfangs nutzen, der während der Testphase ausgewertet werden soll.

<a name="identify-testing-support-stakeholders"></a>Ermitteln der Beteiligten des Test Supports
-------------------------------------

Wenn Sie sich vorbereiten, das Telefon System mit den Funktionen für Anrufpläne zu evaluieren, erstellen Sie eine Stakeholder-Matrix für Test Support, um die zur Unterstützung der Testphase erforderlichen Rollen zu identifizieren.

> [!TIP]
> Wenn Sie die Stakeholder-Matrix für Team testing-Unterstützung füllen, sehen Sie möglicherweise, dass einige Rollen mit denen in der enVision-Phase identisch sind, jedoch mit Rollenbeschreibungen, die in Richtung testing geneigt sind. Je nach den eindeutigen Anforderungen Ihrer Testszenarien müssen Sie möglicherweise zusätzliche Rollen ermitteln.

#### <a name="teams-testing-support-stakeholder-matrix"></a>Team Prüfung unterstützt Stakeholder-Matrix

> [!TIP]
> 
> Nachfolgend finden Sie ein Beispiel für eine Stakeholder-Vorlage für Test Support, mit der Sie dokumentieren können, welche Stakeholder Sie zur Unterstützung der Testphase benötigen.

| Rolle                          | Rollenbeschreibung                                                                                                                                                                          | Zugeordnete Ressource, Kontaktinformationen und Standort |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Testing Executive Sponsor (s)  | <ul><li>Sicherstellen, dass die Teamfunktionen die geschäftlichen Anforderungen erfüllen die Executive-Sponsoren sind an wichtigen geschäftlichen Ergebnissen und priorisierter Anwendungsfall Szenarien fließend.</li><li>Als ultimative Autorität fungieren und die Verantwortung für die Test Ziele von Teams übernehmen.</li><li>Helfen Sie bei der Lösung von Problemen, die vom Testleiter eskaliert werden.</li><li>Sponsern Sie die Kommunikation innerhalb des Unternehmens, um Ziele zu testen.</li><li>Für wichtige strategische Entscheidungen verantwortlich sein.</li><li>Sie müssen dafür sorgen, dass die verfügbaren Ressourcen und das Budget für die Unterstützung von Testaktivitäten zur Verfügung stehen.</li><li>Sensibilisierung und Buy-in für die Testkampagne mit anderen wichtigen Stakeholdern</li><li>Während der Test Evaluierungsphase als Testsponsor fungieren.</li></ul>                                                 | TBD                                                  |
| Mitglieder des Lenkungsausschusses    | <ul><li>Halten Sie Interesse an und geben Sie Anleitungen für die Gesamtrichtung des Telefonsystems bei der Bereitstellung von Anrufplänen.<li>Unterstützen Sie bei der Evangelisierung strategischer Einblicke, indem Sie das Buy-in in der gesamten Organisation steuern.</li></ul>                                                                        | TBD                                                  |
| Projektleiter                  |<ul><li> Verwalten und leiten des Projektteams</li><li>Koordinieren von Partnern und Arbeitsteams, die am Projekt beteiligt sind</li><li>Sie müssen für die Erstellung und Verwaltung von Projektplänen verantwortlich sein, um quartalsweise Ergebnisse zu erreichen.</li><li>Lösen Sie funktionsübergreifende Probleme.</li><li>Bereitstellen von regelmäßigen Updates für Projektsponsoren</li><li>Integrieren Sie die in Testergebnissen identifizierten Kenntnisse der Benutzererfahrung in den allgemeinen Plan zur Benutzereinführung.</li><li>Führen Sie monatliche Geschäfts-und operative Bewertungen durch, und tragen Sie zu Quartals Überprüfungen bei.</li></ul>                                                                                                                                                         | TBD                                                  |
| Leiter/Architekt für Zusammenarbeit  | <ul><li>Verantwortlich für die Ausführung der von Unternehmensleitern definierten Zusammenarbeitsstrategie.</li><li>Analysieren und Auswählen von Zusammenarbeits Produkten für das Unternehmen, das Unternehmensziele erfüllt.</li><li>Für den Entwurf der Vorgänge für Collaboration-Produkte verantwortlich sein.</li><li>Definieren Sie die Betriebs-und Support Modelle.</li><li>Beiträge zu monatlichen und Quartals Überprüfungen für Unternehmen.</li></ul>                                                                                                 | TBD                                                  |
| Projektmanager               | <ul><li>Entwickeln und Verwalten des Projektplans</li><li>Verwalten Sie Projektergebnisse entsprechend dem Projektplan und dem Budget.</li><li>Aufzeichnen und Verwalten von Projektproblemen, einschließlich Eskalationen</li><li>Führen Sie wöchentliche aufstehende Anrufe durch.</li><li>Sie können mit den Project Executive-Sponsoren Kontakt aufnehmen und Updates für Sie bereitstellen.</li><li>Arbeiten Sie mit internen Change Management-und Kommunikationsteams zusammen, um den Änderungs Verwaltungsansatz und die Kommunikationspläne nach Bedarf zu aktualisieren.</li></ul>                                                                                                                                                   | TBD                                                  |
| Netzwerkleiter                  | <ul><li>Bereitstellen von Eingaben für das Netzwerk Design während der Erkennungsphase</li><li>Teilnehmen an der Planung in Workshops zur Envisions Phase.</li><li>Koordinieren der Arbeit des Netzwerkteams während der Projektausführung</li></ul>                                                                                                                               | TBD                                                  |
| Leiter der Sicherheit                 | <ul><li>Bereitstellen von Eingaben in Sicherheitsdesign und-Prozesse während der Erkennungsphase</li><li>Teilnehmen an der Planung in Workshops zur Envisions Phase.</li><li>Koordinieren der Arbeit des Sicherheitsteams während der Projektausführung</li></ul>                                                                                                                | TBD                                                  |
| Telefonieleiter                | <ul><li>Bereitstellen von Eingaben für das Telefonie-Design während der Erkennungsphase.</li><li>Teilnehmen an der Planung in Workshops zur Envisions Phase.</li><li>Koordinieren der Arbeit des Telefonie-Teams während der Projektdurchführung</li></ul>                                                                                                                           | TBD                                                  |
| Desktopleiter                  | <ul><li>Bereitstellen von Eingaben für Clients und des Aktualisierungsprozesses während der Erkennungsphase</li><li>Teilnehmen an der Planung in Workshops zur Envisions Phase.</li><li>Koordinieren der Arbeit des Desktop Teams während der Projektausführung</li></ul>                                                                                                              | TBD                                                  |
| Vertreter der Betriebseinheiten | <ul><li>Tragen Sie zu benutzerbasierten Einführungsleitfäden und Materialien bei.</li><li>Tragen Sie dazu bei, und überprüfen Sie Geschäfts Anwendungsfälle.</li></ul>                                                                                                                                   | TBD                                                  |
| IT-Administratoren                     | <ul><li>Unterstützen Sie die Testplanung und-Ausführung (diese Rolle richtet sich an IT-Experten).                                                                                                                       | TBD                                                  |
| Leiter des Kundendiensts                 | <ul><li>Seien Sie für den Betrieb des Telefonsystems mit Anrufplan-Service verantwortlich.</li><li>Als Besitzer des Telefonsystems mit Anruf Plan Service fungieren.</li></ul>                                                                                                               | TBD                                                  |
| Test Leiter/-Manager             | <ul><li>Definieren Sie den Testplan, einschließlich Aktivitäten, Abhängigkeiten, Umgebung, Ziele, Strategie, Resourcing (Umwelt und menschlich) sowie die Zeitachse, die für die Unterstützung der Testphase erforderlich ist.</li><li>Koordinieren der Zustellung und Bereitschaft für Test Plan Abhängigkeiten</li><li>Richten Sie die richtige Priorität für die Fehlerauflösung aus.</li><li>Dient als Eskalationspfad für alle auftretenden Test Probleme.</li><li>Kommunizieren und melden des Test Plan Status mit internen Teams und benannten Stakeholdern</li><li>Dokumentieren und präsentieren der endgültigen Testergebnisse</li></ul> | TBD                                                  |
| Telefon System mit Anruf Plan Tester     | <ul><li>Überprüfen Sie den Testplan, um die Testanforderungen, Ziele, Zeitachse, Problembehebung und Testfälle zu verstehen, die ausgeführt werden sollen.</li><li>Überprüfen und entwickeln Sie Test Cases, die das Telefon System mit Akzeptanz-und Funktionsanforderungen für Anrufpläne unterstützen.</li><li>Führen Sie Testfälle aus, und dokumentieren Sie Testergebnisse.</li><li>Dokumentieren Sie Fehler, während diese auftreten, und Eskalieren Sie Sie zur Priorisierung und Lösung an den Test Leiter.</li><li>Testen Sie Regressionen, um Fehler zu schließen, nachdem die Fehlerauflösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |
| Netzwerk Tester                | <ul><li>Überprüfen Sie den Testplan, um die Testanforderungen, Ziele, Zeitachse, Problembehebung und Testfälle zu verstehen, die ausgeführt werden sollen.</li><li>Überprüfen Sie Testfälle, die die Akzeptanz von Netzwerk Bereitschaft und die Leistungsanforderungen unterstützen.</li><li>Führen Sie Tests im Zusammenhang mit der Netzwerk Bereitschaft durch, einschließlich Netzwerkkonnektivität und Leistungsüberprüfung, QoS-Validierung und Überprüfung des Split-Tunnel-Konfiguration.</li><li>Vollständige Bandbreiten Überprüfung für Websites im Umfang mithilfe von Network Planner über myadvisor.</li><li>Ergebnisse der Netzwerk Bereitschafts Tests für Dokumente.</li><li>Dokumentieren Sie Fehler, während diese auftreten, und Eskalieren Sie Sie zur Priorisierung und Lösung an den Test Leiter.</li><li>Testen Sie Regressionen, um Fehler zu schließen, nachdem die Fehlerauflösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |
| Sicherheits Tester               | <ul><li>Überprüfen Sie den Testplan, um die Testanforderungen, Ziele, Zeitachse, Problembehebung und Testfälle zu verstehen, die ausgeführt werden sollen.</li><li>Überprüfen und entwickeln Sie Testfälle, die die Anforderungen an die Sicherheits Akzeptanz unterstützen.</li><li>Führen Sie Tests im Zusammenhang mit der Sicherheits Akzeptanz für Testfälle aus.</li><li>Ergebnisse der Dokumentsicherheit Akzeptanztests.</li><li>Dokumentieren Sie Fehler, während diese auftreten, und Eskalieren Sie Sie zur Priorisierung und Lösung an den Test Leiter.</li><li>Testen Sie Regressionen, um Fehler zu schließen, nachdem die Fehlerauflösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |
| Telefon Tester              | <ul><li>Überprüfen Sie den Testplan, um die Testanforderungen, Ziele, Zeitachse, Problembehebung und Testfälle zu verstehen, die ausgeführt werden sollen.</li><li>Überprüfen Sie die Test Cases, die die Akzeptanz und Funktionalität der Dienstnummern Portierung unterstützen.</li><li>Führen Sie Tests in Bezug auf die Portierung von Dienstnummern aus, einschließlich Port für Dienstnummern zu Office 365.</li><li>Führen Sie Testfälle aus, und dokumentieren Sie Testfallergebnisse.</li><li>Dokumentieren Sie Fehler, während diese auftreten, und Eskalieren Sie Sie zur Priorisierung und Lösung an den Test Leiter.</li><li>Testen Sie Regressionen, um Fehler zu schließen, nachdem die Fehlerauflösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |
| Telefon System mit Anruf Plan-Administrator Test | <ul><li>Überprüfen Sie den Testplan, um die Testanforderungen, Ziele, Zeitachse, Problembehebung und Testfälle zu verstehen, die ausgeführt werden sollen.</li><li>Überprüfen und entwickeln Sie Test Cases, die das Telefon System unterstützen und die Anforderungen für die Verwaltung der Anrufpläne erfüllen.</li> <li>Führen Sie Testfälle aus, und dokumentieren Sie Testfallergebnisse.</li><li>Dokumentieren Sie Fehler, während diese auftreten, und Eskalieren Sie Sie zur Priorisierung und Lösung an den Test Leiter.</li><li>Testen Sie Regressionen, um Fehler zu schließen, nachdem die Fehlerauflösung bestätigt wurde.</li></ul>                                                                | TBD                                                  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Test Support-und Stakeholder-Rollen Sie für das Testen von Telefonsystemen mit Anruf Planfunktionen in Ihrer Umgebung benötigen.</li><li>Entscheiden Sie, welche Ressourcen Sie für die von Ihnen identifizierten Test Support-und Stakeholder-Rollen zuweisen.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die Rollen für Test Support und Stakeholder, die für die Stakeholder-Matrix des Test Supports erforderlich sind.</li><li>Dokumentieren Sie Kontaktinformationen und Standortdetails für jede Ressource, die Sie in der Stakeholder-Matrix des Test Supports auflisten.
</table>


<a name="define-phone-system-with-calling-plans-feature-requirements"></a>Telefon System mit Anforderungen für Anrufpläne definieren 
------------------------------------------------------------

Im Rahmen des Definierens von Telefonsystemen mit Anruf Plan-Funktionsanforderungen für Benutzer im Umfang finden Sie unter [Telefonsystem mit Anrufplänen](calling-plan-landing-page.md).
Bewerten Sie als nächstes die aktuelle Roadmap für öffentliche Teams, um Folgendes zu ermitteln:

-   Das Telefon System mit den Funktionen für Anrufpläne, die Sie für Benutzer im Bereich bereitstellen.

-   Erwartetes Nutzer-Telefon System mit Funktionsanforderungen für Anrufpläne, vorausgesetzt, Ihre aktuelle Skype for Business-, Exchange-und SharePoint-Bereitstellungs Landschaft.

-   Ob Sie bestätigen können, dass das Telefon System mit den in der neuesten öffentlichen Roadmap beschriebenen Funktionen für Anrufpläne Ihre Benutzer-, Funktionalitäts-und Bereichsanforderungen in der Zeitachse Ihrer Bereitstellung erfüllt

> [!TIP]
> Die aktuelle Roadmap für Teams zur Identifizierung von Telefonsystemen mit Anruf Planfunktionen im Bereich für Ihre Bereitstellung finden <https://aka.ms/O365Roadmap>Sie unter.

Nachdem nun das Telefon System mit den Funktionen "Anrufpläne" und "Features" definiert wurde, werden die Interoperabilitäts Erfahrungen mit Teams als nächstes bewertet. Weitere Informationen zur Interoperabilitäts Erfahrung sowie zu den verfügbaren Konfigurationsoptionen finden Sie unter [Interoperabilität von Microsoft Teams und Skype for Business](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability).

#### <a name="phone-system-with-calling-plans-feature-definition"></a>Telefon System mit Funktionsdefinition für Anrufpläne

> [!TIP]
> Nachfolgend finden Sie ein Beispiel für eine Telefonanlage mit einer Definitions Vorlage für Anrufpläne, die Sie verwenden können, um das Telefonsystem mit Anruf Planverwaltung und benutzergruppenfeatures zu dokumentieren, die ausgewertet werden sollen.


| Unternehmensklasse   | Kollaborative Besprechungen    | Plattform und Geräte   | IT-Experten  | Zusätzliche Unternehmensgruppe, Website spezifisch  | Anforderungen der neuesten Teams-Roadmap |
|-------------------------------------------|----------------------------|------------------|------------------------|-------------------|-------------------|
| <ul><li>Telefon System-Anruffunktionen:<ul><li>Blind Übertragung</li><li>Anruf Blockierung</li><li>Anrufweiterleitung</li><li>Rufnummernanzeige-Maskierung</li><li>E911-Support</li><li>Durchwahl Wahl</li><li>Anruf halten</li><li>Multi-Call-Behandlung</li><li>Simultaner Ring</li><li>Azure Voicemail</li></ul></li><li>Unterstützung des Anruf Plans</li></ul> |<ul><li>Anrufe zwischen Skype for Business-to-Teams</li></ul> |<ul><li> Unterstützung für Windows-, Mac Teams-Client Besprechungen</li><li>Browser Teams-Client Besprechungen unterstützen die folgenden Funktionen:<ul><li>Chrome</li><li>Microsoft Edge</li></ul></li><li>Support für IOS-und Android-Teams-Client Besprechungen</li><li>TTY-Unterstützung</li></ul> | <ul><li>Diagnose Portal für Anrufqualität</li><li>Mandanten Wähl Plan</li><li>Richtlinien für Mandanten Anrufer-ID</li><li>Aktivieren der Anruf Qualitätsanalyse (CQD)</li></ul> | <ul><li>Überprüfen von Teams-besprechungsfeatures basierend auf einem Firmen-Laptop Bild</li><li>Spezifische Sprachunterstützung</li><li>Für ein bestimmtes Benutzerszenario oder eine bestimmte Website angewendete GPO-Einstellungen</li></ul> | Ja  |




#### <a name="phone-system-with-calling-plans-user-functionality-definition"></a>Telefon System mit Anrufplänen Benutzer Funktionalitäts Definition

> [!TIP]
> Nachfolgend finden Sie ein Beispiel für eine Benutzer Funktionsvorlage, die Sie verwenden können, um die Benutzeroberfläche zu dokumentieren, die basierend auf dem Telefon System erforderlich ist, damit die zu prüfenden Funktionen für Anrufpläne ausgewertet werden.


| Exchange-Benutzeroberfläche                          | SharePoint-Benutzeroberfläche                            | Teams-Interoperabilitätsrichtlinien Erfahrung |
|----------------------------------------------|--------------------------------------------------|------------------------------------------|
| <ul><li>Erstellen von Teams (aktivierte Office-Gruppenerstellung)</li><li>An Teams teilnehmen</li><li>Kanäle erstellen</li><li>Besprechungen erstellen und anzeigen</li><li>Benutzerprofilbild bearbeiten</li><li>Connectors hinzufügen und konfigurieren</li><li>Registerkarten hinzufügen und konfigurieren</li><li>Bots hinzufügen und konfigurieren</li></ul> | <ul><li>Speichern und Freigeben von Dateien in Teams-Unterhaltungen</li><li>Speichern und Freigeben von Dateien in privaten Chats (basierend auf OneDrive)</li></ul> | <ul><li>ChatDefaultClient: Standard</li><li>CallingDefaultClient: Standard</li></ul>      |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li> Entscheiden Sie, welches Telefon System mit den Kategorien Funktionen für Anrufpläne in Ihrer Umgebung bereitgestellt werden soll.</li><li>Ermitteln Sie Ihr Benutzer Telefon System mit den Funktionsanforderungen für Anrufpläne, wenn Sie Ihre aktuelle Skype for Business-, Exchange-und SharePoint-Bereitstellungs Landschaft verwenden.</li><li>Entscheiden Sie, welche Teams Interoperabilitäts Erfahrung bereitgestellt werden soll.</li><li>Überprüfen Sie die aktuelle Roadmap für öffentliche Teams, und entscheiden Sie, ob die aktuellen Arbeits Auslastungs Funktionen Ihrer Bereitstellungs Zeitachse entsprechen.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie das Telefonsystem mit den Kategorien Funktionen für Anrufpläne, die zur Unterstützung Ihres Telefonsystems mit der Bereitstellung von Anrufplänen erforderlich sind.</li><li>Dokumenten-Nutzer Telefon System mit Anruf Planfunktionen und Interoperabilitätsanforderungen in Bezug auf Ihre aktuelle Skype for Business-, Exchange-und SharePoint-Bereitstellungs Landschaft.</li><li>Dokumentieren Sie, ob die aktuelle Public-Roadmap für Teams, die das Telefon System mit Anruf Planfunktionen darstellt, die geschäftlichen Anforderungen und die Zeitvorgaben Ihrer Bereitstellung erfüllt.</li></ul></td></tr>
</table>

<a name="define-and-document-your-phone-system-with-calling-plans-test-plan"></a>Definieren und dokumentieren Ihres Telefonsystems mit dem Testplan für Anrufpläne
------------------------------------------------------------------

Nachdem Sie das Telefon System mit den Funktionen für Anrufpläne im Bereich definiert haben, besteht der nächste Schritt darin, den Testplan zu erstellen. Der Testplan umfasst auf hoher Ebene die Gesamttest Strategie und-Methodik, mit der die Funktionsüberprüfung im Testprozess unterstützt wird.

Auf hoher Ebene sollte der Testplan Folgendes umfassen:

-   **Testbereich:** Fasst die Schwerpunkte (Ziele, Szenarien und Zielsetzungen) zusammen, die als Teil der Testphase ausgewertet werden sollen.

-   **Test Cases:** Die Gruppe von Testfälle, die für das Telefon System überprüft werden sollen, mit Features für Anrufpläne im Bereich

-   **Testressourcen:** Eine Matrix der Ressourcen, die zur Unterstützung des Testversuchs aus einer umwelttechnischen, technischen und personellen Sicht erforderlich sind

-   **Testzeitplan (Zeitachse):** Stellt dar, wann die Tests beginnen, wie lange Sie wahrscheinlich dauern wird, und wann die Testphase beendet werden soll.

-   **Fehlerberichterstattung und-Behebung:** Richtlinien für das melden, nachverfolgen und untersuchen von Problemen mit Tests

-   **Fehler Triage und-Eskalation:** Übersicht darüber, wie und wann eine Fehler Eskalation initiiert werden soll

-   **Testen von Exit-und Suspensions Kriterien:** Leitfaden zur Gliederung von Kriterien für die Erreichung einer Abmeldung, um die Testphase zu beenden oder das Testen zu unterbrechen, bis priorisierte Fehler behoben wurden

-   **Test Ergebnisse:** Zusammenfassung der Ergebnisse, die entwickelt und bereitgestellt werden, um die Abmelde Akzeptanz zu unterstützen und den Testvorgang zu beenden

> [!TIP]
>   Möglicherweise ist in Ihrer Organisation bereits eine Testmethodik vorhanden, doch in der folgenden Anleitung sind bewährte Methoden aufgeführt, die für das Testen von Teams-Features in Ihrer Umgebung separat integriert oder separat genutzt werden können.

In den folgenden Abschnitten finden Sie weitere vorgeschriebene Anleitungen, die Ihnen bei bestimmten Entscheidungen helfen, sowie Vorlagen und Themen, die Sie bei der Fertigstellung Ihres Test Plans beachten sollten.

### <a name="define-and-document-testing-scope"></a>Definieren und Dokumentieren des Testbereichs

Während Sie an der Entwicklung Ihres Testplans arbeiten, müssen Sie den Testbereich im Vordergrund definieren, um die Arbeitsauslastung und die Liste der Features hervorzuheben, die Sie auswerten.

Der Bereich für die ordnungsgemäße Auswertung des Telefonsystems mit Funktionen für Anrufpläne umfasst in der Regel:

-   Telefon System mit Website Bereitschaft für Anrufpläne

-   Telefon System mit Anrufplänen Benutzererfahrung

-   Telefon System mit Anruf Planverwaltung

#### <a name="phone-system-with-calling-plans-testing-scope"></a>Telefon System mit Testbereich für Anrufpläne

> [!TIP]
>   Nachfolgend finden Sie ein Beispiel für eine Testbereichs Vorlage, die Sie verwenden können, um das Telefon System mit Anruf Plan Verwaltungen und benutzergruppenfeatures zu dokumentieren, die ausgewertet werden sollen.

| Telefon System mit Website Bereitschaft für Anrufpläne                                                                                                                                                                                    | Telefon System mit Anrufplänen Benutzererfahrung                                                                                                                                                                                         | Telefon System mit Verwaltungserfahrung bei Anrufplänen                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------|
| <ul><li>Netzwerk Planner-Bandbreitenplanung (über myadvisor)<li></li>Netzwerkkonnektivität und Leistungsüberprüfung (über das Skype for Business-Netzwerk Bewertungstool)<li></li>QoS-Validierung (Quality of Service)<li></li>Remote Zugriff-Split-Tunnel-Validierung</li></ul>|<ul><li>PBX-Funktionen<li></li>PSTN-Anrufe (Inlands-und Auslandsgespräche)<li></li> Platzieren und empfangen von PSTN-anrufen<li></li>Azure Voicemail<li></li>E911<li></li>Mandanten Wähl Plan<li></li>Mandanten-ID-Maskierung <li></li>Erweiterte Funktionen zur Anrufsteuerung (beispielsweise Anrufweiterleitung, gleichzeitiges Klingeln)</li></ul> |<ul><li>Lizenzierungs Aufgabe</li><li>Portierung von Abonnenten Nummern auf Office 365</li><li>Telefon System mit Berichterstattung über Anrufpläne</li><li>Bericht zur Anrufqualität (CQD)</li></ul> |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie sich für das Telefon System mit dem Testbereich für Anrufpläne, indem Sie die Features identifizieren, die vom Fokusbereich ausgewertet werden sollen.</li><li>Entscheiden Sie sich für weitere Ziele und Zielsetzungen für die Bewertung.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie das Telefon System mit den Funktionen für Anrufpläne, die nach Fokusbereich ausgewertet werden sollen.</li><li>Dokumentieren Sie weitere Ziele und Ziele für die Bewertung.</li></ul></td></tr>
</table>

### <a name="define-and-document-phone-system-with-calling-plans-test-cases"></a>Definieren und Dokumentieren von Telefonsystemen mit Testfällen für Anrufpläne

Nachdem Sie das Telefonsystem mit Funktionen für Anrufpläne, Clientbereitstellung und parallele Szenarien mit Skype for Business (falls zutreffend) definiert haben, besteht der nächste Schritt darin, die Testfälle zu formulieren, die erforderlich sind, um das Telefonsystem mit Anruf Planfunktionen in zu bewerten. Bereich. Auf einer hohen Ebene sind Testfälle in der Regel nach Fokusbereich gruppiert und umfassen:

-   **Test Case-Titel:** Fokusbereich der Funktion, die vom Test ausgewertet wird (beispielsweise Telefon System mit Anrufplänen)

-   **Test Fallbeschreibung:** Zusammenfassung der Ziele der Testfeatures, die ausgewertet werden

-   **Test Case-Anweisungen:** Schritte zum ordnungsgemäßen Ausführen des Testfalls, der ausgeführt wird

-   **Umgebung erforderlich (Voraussetzungen):** Setup Anweisungen, die für eine ordnungsgemäße Ausführung des Tests erforderlich sind

-   **Benötigte Ressource:** Für die ordnungsgemäße Bewertung und Durchführung des Tests erforderliche Personalressourcen

-   **Erwartete Ergebnisse:** Das Ergebnis, das Sie erwarten, nachdem der Test erfolgreich abgeschlossen wurde

> [!NOTE]
>   Da der Ansatz und die Detailebene, die für die Erstellung von Testfällen erforderlich sind, in Ihrer Organisation unterschiedlich sein können, empfiehlt es sich, einem Ansatz zu folgen, der ein angemessenes Maß an Details zulässt, doch die Gründlichkeit mit der Praktikabilität in Einklang zu bringen, um die Gesamtprüfung zu unterstützen. Verwaltbarkeit.

> [!TIP]
>   Wenn Sie die Erstellung von Testfällen als Ausgangspunkt unterstützen möchten, lesen Sie die Liste der Benutzerleitfaden für Telefonsysteme, die in den [Teams-Besprechungen und-anrufen](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)zur Verfügung stehen.

#### <a name="phone-system-with-calling-plans-test-case"></a>Telefon System mit Test Case für Anrufpläne

> [!TIP]
>   Nachfolgend finden Sie ein Beispiel für eine Testfall-Vorlage, mit der Sie das Telefon System mit den Anrufplänen verwalten und die zu prüfenden benutzergruppenfeatures dokumentieren können.

Telefon System mit Überprüfung der Anrufpläne

| Test Case-ID | Test Case-Titel               | Test Fallbeschreibung                                                  | Umgebung, die für die Test Fall Ausführung erforderlich ist                                               | Erforderliche Schritte für die Test Case-Ausführung                                                                                                                                                          | Erforderliche Testressource              |
|--------------|-------------------------------|------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------|
| 1            | Einfügen eines ausgehenden PSTN-Anrufs | Stellen Sie sicher, dass Sie einen externen Sprachanruf an eine 10-stellige Nummer durch stellen können. |<ul><li>Der Client für Teams ist installiert.</li><li>Der Benutzer ist aktiviert, wenn die folgenden Office 365-Lizenzen zugewiesen sind:<ul><li>Office Enterprise E5 mit Telefon System, Microsoft Teams und nationalen und internationalen Anrufplänen</li><li>Office Enterprise E3 mit Telefon System, Microsoft Teams und nationalen und internationalen Anrufplänen</li></ul></li></ul> | <ol><li>Anmelden beim Team-Client.</li><li>Wählen Sie die Wähltastatur aus, und geben Sie eine 10-stellige Nummer ein, die Sie wählen möchten.</li><li>Stellen Sie sicher, dass die Rufnummernanzeige ordnungsgemäß normalisiert wurde und der externe PSTN-Anruf eingerichtet ist.</li></ol>    | Telefon System mit Anruf Plan Tester |


> [!TIP]
>   Weitere Anleitungen zur Vereinfachung des individuellen Testfalls und zur allgemeinen Planerstellung für die Bewertung des Telefonsystems mit Funktionen für Anrufpläne in Ihrer Organisation finden Sie unter dem Testplan für [Telefonsysteme](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) , der von myadvisor bereitgestellt wird. [](https://myadvisor.fasttrack.microsoft.com/)


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welches Telefon System mit Anruf Planverwaltung und Benutzer Features ausgewertet werden soll.</li><li>Entscheiden Sie, welche Testumgebung zur Unterstützung der Test Case-Ausführung erforderlich ist.</li><li>Entscheiden Sie, welche Schritte für die Test fallauswertung erforderlich sind.</li><li>Entscheiden Sie, welche Ressourcen für die ordnungsgemäße Ausführung des Tests erforderlich sind.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die Test Cases, die ausgewertet werden sollen, basierend auf der bereitgestellten Test Fall Vorlage.</li><li>Schließen Sie die fertige Vorlage als Teil des gesamten Testplans ein.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-resources"></a>Definieren und Dokumentieren von Testressourcen

Um die Testphase zu unterstützen, ist es wichtig, dass Sie einen Ressourcenplan entwickeln, in dem die erforderlichen Personen-, Support-und Technologieressourcen erläutert werden. Als wichtige Komponente des Gesamt Testplans hilft Ihnen der Ressourcenplan dabei, eventuell vorhandene Abhängigkeiten zu ermitteln, und vermittelt Ihnen einen allgemeinen Überblick über die Ressourcen, die Sie möglicherweise benötigen.

Auf einem hohen Niveau bestehen diese Ressourcen in der Regel aus:

-   **Personen**: Stakeholder

-   **Technologie**: Mandant, Lizenzierung, Geräte

-   **Support**: Schulung (Karten, Videos), Verwaltungsunterstützung mit definiertem Eskalationspfad

#### <a name="testing-resource-requirements"></a>Testen der Ressourcenanforderungen

> [!TIP]
>   Nachfolgend finden Sie ein Beispiel für das Testen von Ressourcen Anforderungsvorlagen, mit denen Sie die verschiedenen Arten von Ressourcen dokumentieren können, die zur Unterstützung Ihrer Testphase erforderlich sind.


| Ressourcentyp | Erforderliche Ressourcen                                           | Ressourcenbeschreibung |
|---------------|--------------------------------------------------------------|----------------------|
| Kontakte        | Testleiter testen                               | TBD                  |
| Technologie    | Zugriff auf Office 365, wobei die folgenden Dienste aktiviert sind:<ul><li>Office 365 E5-Lizenzierung zugewiesen</li><li>Zugeordneter Plan für Inlands-und Auslandsanrufe</li></ul>    | TBD                  |
| Support       | Test Supporttechniker testen | TBD                  |

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie über die Ressourcentypen (Personen, Technologie und Support), die Sie zur Unterstützung der Testphase benötigen.</li><li>Entscheiden Sie, welche Ressourcen für die angegebenen Ressourcentypen erforderlich sind.</li><li>Entscheiden Sie, ob Sie weitere Einzelheiten angeben sollten, um die Ressourcentypen zu beschreiben, die Sie benötigen.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die Ressourcentypen (Personen, Technologie und Support), die Sie zur Unterstützung der Testphase benötigen.</li><li>Dokumentieren Sie die spezifischen Ressourcen, die für die von Ihnen identifizierten Ressourcentypen erforderlich sind.</li><li>Wenn Sie sich entscheiden, dass dies erforderlich ist, dokumentieren Sie alle weiteren Details zu den Ressourcentypen, die Sie zur Unterstützung der Testphase benötigen.</li></ul></td></tr>
</table>


### <a name="define-and-document-a-testing-timeline"></a>Definieren und dokumentieren einer Test Zeitachse

Erstellen Sie im Rahmen der Testplan-Definition eine Zeitachse, in der der Zeitplan für die Ausführung von Testaktivitäten und das erreichen von Meilensteinen auf höherer Ebene erläutert wird.

Auf einem hohen Niveau besteht dies in der Regel aus:

-   **Aufgabe:** Aktivitäten auf höherer Ebene, die ausgeführt werden sollen

-   **Meilenstein:** Ziel auf oberster Ebene oder abgeschlossener Status

-   **Benötigte Ressource:** Testen der Ressourcen, die zur Unterstützung der Zustellung des Meilensteins oder der Aufgabe erforderlich sind

-   **Anfangstermin:** Das Datum, an dem die Aktivität, der Meilenstein oder die Aufgabe initiiert wurde

-   **Fertigstellungsdatum:** Das Datum, an dem die Aktivität, der Meilenstein oder die Aufgabe ausgeführt werden soll

-   **Besitzer:** Zugeordnete Ressource, die dafür verantwortlich ist, dass die Aktivität, der Meilenstein oder die Aufgabe nach dem Fertigstellungstermin rechtzeitig abgeschlossen wird

-   **Einschätzung:** Die Anzahl der Stunden, die für die zugeordneten Ressourcen erwartet werden, um sicherzustellen, dass die Aktivität, der Meilenstein oder die Aufgabe rechtzeitig abgeschlossen wird

#### <a name="testing-scheduling-and-timeline-requirements"></a>Voraussetzungen für Testplanung und Zeitachse

> [!TIP]
>   Nachfolgend finden Sie ein Beispiel für eine Anforderungs Vorlage für Test Zeitachsen, mit der Sie die voraussichtlichen Daten für den Abschluss bestimmter Testaktivitäten oder von Meilensteinen dokumentieren können.

| Aufgabe                                                 | Meilenstein       | Anfangstermin                                                             | Fertigstellungsdatum | Besitzer | Zugewiesene Ressourcen | Schätzung |
|------------------------------------------------------|-----------------|------------------------------------------------------------------------|-----------------|-------|--------------------|------------|
| Test Bericht                                          | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Stunden festzulegen  |
| Test Case-Ausführung: Telefon System mit Anrufplänen | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Stunden festzulegen  |
| Test Case-Ausführung: Netzwerk Bereitschaft               | TBD             | TBD                                                                    | TBD             | TBD   | TBD                | Stunden festzulegen  |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Zeitachsen Aktivitäten, Meilensteine und Aufgaben Sie nachvollziehen müssen.</li><li>Entscheiden Sie, welche Ressourcen Sie zuweisen müssen.</li><li>Entscheiden Sie, welches Datum Sie erwarten.</li><li>Identifizieren des Zustellungs Besitzers</li><li>Entscheiden Sie, wie viel Zeit für die Ausführung der Aktivität, des Meilensteins oder der Aufgabe beansprucht werden soll.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie Ihre Test Zeitachse mit der bereitgestellten Vorlage, und fügen Sie Folgendes hinzu:<ul><li>Zeitachsen Aktivität, Meilenstein und Aufgaben, die nachverfolgt werden müssen.</li><li>Ressourcen, die zugewiesen werden müssen.</li><li>Voraussichtlicher Fertigstellungstermin.</li><li>Zustellungs Besitzer.</li><li>Die Zeit, die zum Abschließen der Aktivität, des Meilensteins oder der Aufgabe erforderlich ist.</li></ul></li><li>Schließen Sie die fertige Vorlage als Teil des gesamten Testplans ein.</li></ul></td></tr>
</table>


### <a name="define-and-document-test-defect-report-criteria"></a>Definieren und Dokumentieren von Kriterien für Testfehler Berichte

Da Testfälle innerhalb einer bestimmten Phase oder eines Datenstroms ausgeführt werden, können Probleme auftreten, wenn das Ergebnis des ausgeführten Testfalls nicht das ist, was Sie erwartet haben.

Wenn diese Arten von Ergebnissen auftreten, sollten Sie in einem Fehlerbericht und Behebungs Plan erfasst werden, der zur Überprüfung, Berichterstellung und Fehlerauflösung an den angegebenen Testleiter weitergeleitet wird.

In der Regel umfasst ein Fehlerbericht und ein Sanierungsplan Folgendes:

-   **Fehler-ID:** Die dem Problem zugewiesene Nummer

-   **Test Case-ID beeinträchtigt**: die Nummer, die dem Testfall zugewiesen wurde, der zum Zeitpunkt der Fehlerermittlung ausgewertet wurde.

-   **Fehlerbeschreibung:** Zusammenfassung des Problems

-   **Zu reproduzierende Umgebung/Schritte:** Zusammenfassung des Setups der Testumgebung zusammen mit den genauen Schritten, die erforderlich sind, um das Problem zu reproduzieren

-   **Fehlerschweregrad**: die Auswirkungen des Problems, von der Annahme, dass der Test Case nicht genehmigt wird, mit minimalem Risiko akzeptiert zu werden. Einige Beispiele können Folgendes enthalten:

-   **Gering:** Das Problem hat kaum Auswirkungen und verhindert nicht, dass der Testfall akzeptiert wird, wenn das Problem später behoben werden kann.

-   **Mittel:** Das Problem hat erhebliche Auswirkungen, wird jedoch nicht verhindern, dass der Testfall akzeptiert wird, wenn das Problem gelöst werden kann, bevor die Testphase abgeschlossen ist.

-   **Höchstwert:** – das Problem hat eine kritische Auswirkung auf den Testfall. Das Problem muss aufgelöst werden, bevor der Testfall akzeptiert werden kann.

-   **Status:** Wurde das Problem gelöst, ist es geöffnet oder wird noch untersucht

-   **Eingereicht von:** Der Tester, der das Problem gemeldet hat

-   **Zugewiesener Besitzer:** Die Ressource, die dem Test Team zugewiesen ist, das für die Lösung des Problems verantwortlich ist

-   **Unterstützende Details:** Dies kann – aber nicht nur – auf clientseitige Protokolle, Screenshots oder Videos des Problems zählen.

Wenn Tester die in Ihrem Testplan skizzierten Testfälle ausführen, sollten Sie sicherstellen, dass Sie einen Fehlerbericht und einen Sanierungsplan für alle auftretenden Probleme durchführen.
Dadurch werden potenzielle Auswirkungen aufgezeigt, die das Testen des Evaluierungsprozesses behindern oder sogar verhindern könnten.

#### <a name="testing-defect-report-and-remediation-plan"></a>Testfehler Bericht und Sanierungsplan

> [!TIP]
>   Nachfolgend finden Sie ein Beispiel für eine Vorlage für Fehlerberichte und korrekturpläne, die Sie zum Dokumentieren von Problemen verwenden können, die während der Testphase entdeckt wurden.

| Fehler-ID                                | Test Case-ID beeinträchtigt | Fehlerbeschreibung                                                                                 | Zu reproduzierender Umgebungs/Steps                                                                                                | Schweregrad | Status | Eingereicht von | Zugewiesener Besitzer | Unterstützende Details (Protokolle, Screenshots usw.) |
|------------------------------------------|-----------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------|--------|--------------|----------------|---------------------------------------------------|
| 1                                        | 1                     | Wenn der Benutzer eine vierstellige Durchwahl eingibt und versucht, einen ausgehenden Anruf zu tätigen, schlägt der Anruf fehl. | Wählen Sie im Team-Client die Wähltastatur aus, geben Sie eine vierstellige Durchwahl ein, und wählen Sie das Telefonsymbol aus, um den Anruf zu tätigen. | Mittel   | Geschlossen | Louis Lahr   | Lisa Gray      | Clientseitige Teams-Protokoll<br/> Screenshot des Teams-Clients     |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Fehlerkriterien Schweregrade zugewiesen werden, um den Prüfungsaufwand zu unterstützen.</li><li>Entscheiden Sie, welche Prüfkriterien für die Fehlerberichterstattung Sie dokumentieren, wenn während der Tests Probleme auftreten.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die Kriterien für die Prüfung der Fehlerberichterstattung, die in der Vorlage bereitgestellt werden.</li><li>Schließen Sie die fertige Vorlage als Teil des gesamten Testplans ein.</li></ul></td></tr>
</table>


### <a name="define-and-document-exit-and-suspension-criteria"></a>Definieren und Dokumentieren von Exit-und Suspensions Kriterien

Im Rahmen des gesamten Test Plan Ausführungsprozesses müssen Sie Kriterien definieren, um den Punkt anzugeben, an dem Sie die Testaktivitäten und die Anforderungen, die für die Abmeldung und Beendigung der Testphase erfüllt sein müssen, auszusetzen.

#### <a name="test-plan-exit-and-suspension-criteria"></a>Test Plan-Exit-und Suspensions Kriterien

> [!TIP]
>   Nachfolgend finden Sie ein Beispiel für eine Vorlage für Exit-und Suspensions Kriterien, die Sie in Ihrem Testplan verwenden können, um Kriterien zu dokumentieren, die erforderlich sind, um die Abmeldung zu erreichen, die Testphase zu beenden oder Testaktivitäten auszusetzen.

| Testen von Exit-Kriterien                            | Testen von Aussetzungs Kriterien                      |
|--------------------------------------------------|--------------------------------------------------|
|<ul><li>Alle Testfälle müssen eine Durchlauf Rate von%% erreichen.</li><li>Alle Testfälle müssen vollständig ausgeführt worden sein.</li><li>In allen bewerteten Testfällen müssen alle Fehler mit dem höchsten Schweregrad geschlossen werden.</li></ul> | <ul><li>Alle Testfälle müssen eine% ige Fehlerrate erreichen.</li><li>Alle als "schwerwiegend" gekennzeichneten Fehler müssen aufgelöst werden, bevor der Test fortgesetzt werden kann.</li></ul> |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Aussetzungs Kriterien erfüllt sein müssen, wenn Probleme mit der Prüfung identifiziert werden.</li><li>Entscheiden Sie sich für Exit-Kriterien, die erfüllt sein müssen, um die Abnahme der Prüfung zu erhalten und die Testphase zu beenden, nachdem alle Testaktivitäten abgeschlossen sind.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die für die Test-und Exit-Vorlagen erforderlichen Test-Exit-und Suspension-Kriterien.</li></ul></td></tr>
</table>


### <a name="define-and-document-the-defect-escalation-process"></a>Definieren und Dokumentieren des Fehler Eskalationsprozesses

Während der Ausführung des Test Plans können Sie möglicherweise ein Problem entdecken oder einen Fehler ermitteln, bei dem eine Eskalation der richtigen Ressource für das fahren und ermitteln der erforderlichen Auflösung erforderlich ist, damit Tests fortgesetzt werden können.

Da Fehler mit dem entsprechenden Schweregrad und der zugewiesenen Priorität identifiziert werden, erstellen Sie eine Eskalations Matrix und eine Triage-Überprüfungsprozess für die Zuordnung, wenn eine Eskalation ausgelöst wird und wie, wann und wem der Fehler zur weiteren Überprüfung zugeordnet wird, und Auflösung.

In der Regel umfasst ein Fehlerbericht und ein Sanierungsplan Folgendes:

-   **Fehler-ID:** Die Nummer, die Sie dem Problem zugewiesen haben.

-   **Fehlerbeschreibung:** Zusammenfassung des Problems

-   **Beurteilung der Fehler Priorität:** Die Prioritätsstufe, die einem Fehler für die Auflösung auf der Grundlage der geschäftlichen Auswirkungen und des Fehlerschwere Grads zugewiesen wurde. Einige Beispiele könnten Folgendes umfassen:

-   **Gering:** Das Problem hat kaum Auswirkungen darauf, dass die Testphase nicht abgemeldet wird, wenn das Problem später behoben werden kann.

-   **Mittel:** Das Problem hat erhebliche Auswirkungen darauf, dass die Testphase nicht abgemeldet wird, wenn das Problem nicht behoben werden kann.

-   **Höchst:** Das Problem hat kritische Auswirkungen darauf, dass die Testphase nicht abgemeldet wird, wenn das Problem nicht behoben werden kann.

-   **Zugeordneter Fehler Besitzer:** Die Ressource, die dem Test Team zugewiesen ist, das für die Lösung des Problems verantwortlich ist

-   **Zugewiesene Fehler Eskalationspunkt:** Die zugeordnete Ressource, die für die Eskalation des Problems in der Organisation (falls erforderlich) für die Fahr Auflösung steht. basierend auf dem Fehlerschweregrad

-   **Fehlerstatus:** Wurde das Problem gelöst, ist es geöffnet oder wird noch untersucht

-   **Erforderliche Auflösung nach Datum:** Das Datum, an dem das Problem aufgelöst werden muss

-   **Status Datum:** Das Datum, das den letzten Zeitstatus widerspiegelt, wurde als Ergebnis einer Fehler Triage-Überprüfung aktualisiert.

#### <a name="test-plan-defect-escalation"></a>Fehler Eskalation des Test Plans

> [!TIP]
>   Nachfolgend finden Sie ein Beispiel für eine Fehler Eskalations Vorlage, die Sie in einem Teil Ihres Testplans verwenden können, um den Eskalationsprozess zu dokumentieren, der für die Priorisierung und Behebung von Test Fehlern erforderlich ist.

| Fehler-ID                                | Fehlerbeschreibung                                                                                 | Bewertung der Fehler Priorität                                           | Zugeordneter Fehler Besitzer | Zugewiesene Fehler Eskalationspunkt | Fehler Eskalations Methode                                          | Fehlerstatus | Erforderliche Auflösung nach Datum | Status Datum |
|------------------------------------------|----------------------------------------------------------------------------------------------------|----------------------------------------------------------------------|-----------------------|----------------------------------|-------------------------------------------------------------------|---------------|-----------------------------|-------------|
| 1                                        | Wenn der Benutzer eine vierstellige Durchwahl eingibt und versucht, einen ausgehenden Anruf zu tätigen, schlägt der Anruf fehl. | Mittel                                                               | Lisa Gray             | Louis Lahr                       | Wöchentliche Triage Überprüfen der e-Mail mit hoher Priorität an betroffene Stakeholder | Öffnen          | SFWM                        | 1/12/2018   |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie sich für die Fehler Prioritäten, um Ihren Testplan zu unterstützen.</li><li>Entscheiden Sie den Eskalationspunkt für jeden Fehlerbereich.</li><li>Entscheiden Sie, ob der Fehler Eskalations-und Triage-Plan basierend auf der Priorität befolgt werden soll.</li><li>Entscheiden Sie sich für die Fehlerberichterstattung und den Plan zur Triage für die Eskalation.</li><li>Entscheiden Sie sich für den Fehler Triage Überprüfen des Besprechungs Rhythmus.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren der vereinbarten Fehler Prioritäten</li><li>Dokumentieren Sie den Eskalationspunkt für jeden potenziellen Fokusbereich.</li><li>Dokumentieren Sie den Plan für Fehler Eskalation und-Triage auf der Grundlage vereinbarter Kriterien.</li><li>Dokumentieren Sie Ihre Fehlerberichterstattungsrichtlinien.</li><li>Planen Sie die Serie der Fehler Triage-Besprechungen.</li></ul></td></tr>
</table>


### <a name="define-and-document-testing-deliverables"></a>Definieren und Dokumentieren der Testergebnisse

Die letzte und letzte Komponente beim Erstellen eines Testplans besteht darin, die Ergebnisse im Hinblick auf bestimmte Ergebnisse zu identifizieren, die der Gesamt Testplan übermitteln wird.

Auf einem hohen Niveau gehören diese in der Regel zu den folgenden:

-   Testplan

-   Test Cases

-   Fehlerberichte

-   Zusammenfassung der Test Ergebnisse

-   Testen der Akzeptanz und Abmeldung

#### <a name="test-plan-deliverables"></a>Ergebnisse des Test Plans

> [!TIP]
>   Nachfolgend finden Sie ein Beispiel für eine Testplan-Matrix, die Sie verwenden können, um die zu erstellenden Lieferbestandteile zusammen mit Ressourcen zu dokumentieren, die für die Überprüfung, Genehmigung und Freigabe erforderlich sind.

| Testplan-Lieferung                    | Testplan-Lieferumfang Format | Testplan-Lieferbestandteil-Besitzer                                                                                                      | Testplan-Lieferbestandteil-Bearbeiter | Test Plan Lieferung Genehmiger | Testplan-Liefertermin für die Abmeldung |
|------------------------------------------|------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------|-------------------------------------|
| Testplan                                | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Fehler Verwaltungsberichte                | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Testen von Statusberichten                   | Word                         | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |
| Zusammenfassung der Test Ergebnisse                     | Word-PPTX                    | TBD                                                                                                                              | TBD                            | TBD                            | TBD                                 |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Lieferbestandteile in den einzelnen Testphasen als Ausgabe erstellt und erfasst werden sollen. Entscheiden Sie für jede Lieferung:<ul><li>Format</li><li>Besitzer</li><li>Prüfer</li><li>Genehmiger</li></ul></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren einer Test Plan Bereitstellungs Matrix für die Erstellung und Zustellung</li></ul></td></tr>
</table>


<a name="evaluate-network-readiness"></a>Auswerten der Netzwerk Bereitschaft
----------------------------

Als wichtiges Element zur Unterstützung der Bereitstellung von Teams ist die Netzwerk Bereitschaft ein entscheidender Bestandteil des Tests, um sicherzustellen, dass das Netzwerk für die Unterstützung von Teams-Kommunikation richtig optimiert ist. Wenn Sie sicherstellen möchten, dass Ihr Netzwerk für die Websites im Umfang bereit ist, schließen Sie die nachstehend aufgeführten Fokusbereiche in Ihre allgemeine Teststrategie ein:

-   Bandbreiten Abschätzung und-Planung mit Network Planner (über myadvisor)

-   QoS-Konfigurationsüberprüfung (Quality of Service)

-   Netzwerkkonnektivität und Leistungsüberprüfung durch Verkehrssimulation

-   Überprüfung für Split-Tunneling

### <a name="execute-network-planner-through-myadvisor-for-sites-and-personas-in-scope"></a>Ausführen von Network Planner (über myadvisor) für Websites und Personas im Bereich

Vor der Einführung von Echt Zeit Kommunikationsdiensten wie Teams in Ihrer Umgebung ist es wichtig, sicherzustellen, dass das Netzwerk ordnungsgemäß optimiert und von einem Azure Express Route (falls zutreffend), Internet und WAN-Bandbreiten Perspektive angepasst wurde.

Wenn Sie bei der Ermittlung der Bandbreite und des Grads der Netzwerkoptimierung unterstützen möchten, die für Websites im Umfang erforderlich ist, die Ihre Bereitstellung unterstützen, füllen Sie das [Network Planner](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=DashboardHelp) -Tool (über myadvisor) aus, um die Netzwerk Bereitschaft Ihrer Organisation zu überprüfen. Weitere Informationen dazu, wie Sie Netzwerkanforderungen für Teams über den Netzwerk Planner ermitteln können, finden Sie unter myadvisor: Network Planner.

> [!TIP]
>   Weitere Informationen zur Registerkarte **Empfehlungen** sowie Beispiele für das Konfigurieren und Interpretieren der Ergebnisse finden Sie unter [Übersicht über](https://myadvisor.fasttrack.microsoft.com/CloudVoice/NetworkPlanner/Help?sectionName=RecommendationHelp)die Netzwerk Planner-Empfehlungen.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Netzwerk Websites im Bereich für die Bereitstellung von Teams-Diensten sind.</li><li>Entscheiden Sie, welche Personen für die Modalitäten für Teams im Bereich erforderlich sind.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Vervollständigen Sie den Netzwerk Planner (über myadvisor) für die Liste der Websites, die sich im Bereich befinden.</li><li>Dokumentieren von Netzwerk Planner-Validierungsergebnissen in der Vorlage Testplan-Ergebnisse bereitgestellt.</li><li>Überprüfen Sie, ob die Express Route (falls zutreffend), Internet und WAN-Bandbreite, die für Websites im Bereich berechnet wurde, an Bandbreiten Werten ausgerichtet sind, die derzeit zugewiesen sind.</li><li>Führen Sie für Websites, die nicht über eine ausreichende Bandbreite verfügen, Eskalations-und Sanierungspläne aus, um Bandbreitenprobleme zu beheben.</li><li>Einrichten einer Netzwerküberwachungslösung für Websites im Bereich zum Überwachen der Bandbreitennutzung und QoS für Express Route (falls zutreffend), Internet und WAN-Segmente.</li><li>Planen einer Sitzung des Lenkungsausschusses zur Überprüfung der Ergebnisse des Netzwerk Planers</li><li>Präsentieren Sie dem Lenkungsausschuss die Ergebnisse der Bandbreitenplanung, um alle Bereiche zu identifizieren, die Behebung erfordern.</li></ul></td></tr>
</table>


<a name="evaluate-qos-configuration-for-sites-in-scope"></a>Auswerten der QoS-Konfiguration für Websites im Bereich
---------------------------------------------

Im Rahmen der Überprüfung der Netzwerk Bereitschaft zur Unterstützung der Echtzeitkommunikation von Teams ist es ebenso wichtig, sicherzustellen, dass das Netzwerk ordnungsgemäß konfiguriert und aus einer QoS-Perspektive optimiert wurde.

Weitere Anleitungen zum Konfigurieren, bereitstellen und Überprüfen der QoS-Netzwerk Bereitschaft für Teams mithilfe von Gruppenrichtlinien finden Sie unter [Aktivieren von QoS für Teams](https://docs.microsoft.com/MicrosoftTeams/qos-in-teams).


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche QoS-Konfiguration implementiert werden soll.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Konfigurieren von QoS</li><li>Führen Sie eine QoS-Validierung aus, wie Sie in den Abschnitten über die Abschnitte "überprüfen über GPO" und "überprüfen per Nachrichten Analyse" beschrieben sind.</li></ul></td></tr>
</table>


### <a name="document-qos-configuration-validation-test-results"></a>Dokument QoS-Konfigurations Prüfungsergebnisse

Nachdem Sie die QoS-Gültigkeitsprüfung mithilfe von Gruppenrichtlinien für Websites im Bereich abgeschlossen haben, erstellen Sie einen Bericht, der die Testergebnisse zusammenfasst, die während der letzten Überprüfung des Lenkungsausschusses zu präsentieren sind.

#### <a name="site-a-qos-configuration-validation-testing-summary-report"></a>Website A: Zusammenfassungsbericht zur QoS-Konfigurationsprüfung

> [!TIP]
>   Nachfolgend finden Sie eine Beispielvorlage für den Test Zusammenfassungsbericht, die Sie während der nächsten Sitzung des Lenkungsausschusses überprüfen können, wenn Sie entscheiden, wann das Telefon System mit den Anruf Plan Diensten in der Pilot Phase eingebunden werden soll.


**QoS-Konfigurationsüberprüfung über GPO und Nachrichten Analyse**

**Zusammenfassung**der&nbsp; &nbsp; &nbsp; Ergebnisse:&nbsp; &nbsp; &nbsp;&#9744;Durchlauf&nbsp; &nbsp; &nbsp; &#9744;partiellen &#9744;Fehler

<table>
<tr><th colspan="2">Test Highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen von Lowlights  </th></tr><br/><tr><td><strong>Problem</strong>: festgelegt</td><td><strong>Behebung:</strong> TBD</td></tr>
<tr><th colspan="2">Identifizierte Blocker </td></tr>
<tr><td><strong>Blocker</strong>: festgelegt</td><td><strong>Behebung</strong>: festgelegt</td></tr>
</table>


> [!TIP]
> Um weitere Diskussionen während der letzten Überprüfung des Lenkungsausschusses zu ermöglichen, können Sie die aktualisierte [Test Ergebnismatrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) von myadvisor verwenden, um weitere Bereiche zu dokumentieren und hervorzuheben, für die eine Korrektur erforderlich ist. [](https://myadvisor.fasttrack.microsoft.com/)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Bewerten Sie die QoS-Testergebnisse, um sicherzustellen, dass der Echt Zeit Mediendatenverkehr von Teams ordnungsgemäß markiert und priorisiert wird.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die QoS-Testergebnisse in der Vorlage Test Plan Ergebnis.</li><li>Führen Sie Eskalations-und Sanierungspläne aus, um Probleme zu beheben, bei denen QoS möglicherweise nicht ordnungsgemäß konfiguriert ist oder nicht wie erwartet funktioniert, um den Mediendatenverkehr von Teams zu unterstützen</li></ul></td></tr><li>Planen Sie eine Sitzung des Lenkungsausschusses, um die Ergebnisse der Test Zusammenfassung zu überprüfen.</li><li>Präsentieren Sie dem Lenkungsausschuss Test Zusammenfassungsergebnisse, um alle Bereiche zu identifizieren, für die eine Sanierung erforderlich ist.</li>
</table>


<a name="execute-split-tunnel-enablement-validation"></a>Ausführen der Validierung von Split-Tunnel-Aktivierung
------------------------------------------

Für Unternehmen ist es heute üblich, eine oder mehrere Lösungen für die Bereitstellung von Remotezugriff zu haben, beispielsweise ein virtuelles privates Netzwerk oder ein VPN. Diese Lösungen ermöglichen eine sichere und zuverlässige Konnektivität mit internen Unternehmensressourcen und-Anwendungen.

Obwohl Remote Access-Lösungen sehr gut für den Zugriff auf einige Anwendungen geeignet sind, wenn es um Tunneling-Teams in Echtzeit-Mediendatenverkehr geht, führen diese Lösungen häufig zu einer weniger optimalen Benutzererfahrung für alle Teilnehmer in einem Teams-Audio. Konferenz-oder Anruf Szenario

Um sicherzustellen, dass der Mediendatenverkehr von Teams *keine* Remotezugriffslösungen in Ihrer Umgebung durchläuft, ist eine Split-Tunnel-Konfiguration erforderlich.

Weitere Anleitungen zum Konfigurieren und Überprüfen der Netzwerk Bereitschaft von Split-Tunnel-Konfigurationen für Teams finden Sie unter [Netzwerk](https://docs.microsoft.com/MicrosoftTeams/prepare-network) Bereitschaft.

> [!NOTE]
>   Aufgrund der großen Anzahl von Remotezugriffslösungen, die auf dem Marktplatz zur Verfügung stehen, können in diesem Dokument keine herstellerspezifischen Details bereitgestellt werden, sondern nur allgemeine Richtlinien für das, was für Remotezugriffslösungen konfiguriert werden sollte.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, ob die Split-Tunnel-Konfiguration implementiert werden soll.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Implementieren Sie die Split-Tunnel-Konfiguration.</li><li>Testen und überprüfen Sie die Split-Tunnel-Konfiguration.</li></ul></td></tr>
</table>


### <a name="document-split-tunnel-configuration-validation-test-results"></a>Testergebnisse für Dokument Split-Tunnel-Konfigurationsüberprüfung

Nachdem Sie das Testen der Split-Tunnel-Konfiguration für Websites im Bereich abgeschlossen haben, erstellen Sie einen Bericht, der die Testergebnisse zusammenfasst und während der nächsten Überprüfung des Lenkungsausschusses präsentiert.

#### <a name="site-a-split-tunnel-configuration-validation-testing-summary-report"></a>Website A: Zusammenfassungsbericht zur Überprüfung der geteilten Tunnelkonfiguration

> [!TIP]
>   Nachfolgend finden Sie eine Beispielvorlage für den Test Zusammenfassungsbericht, die Sie während der nächsten Sitzung des Lenkungsausschusses überprüfen können, wenn Sie entscheiden, wann das Telefon System mit den Anruf Plan Diensten in der Pilot Phase eingebunden werden soll.

**Überprüfung der Split-Tunnel-Konfiguration**

**Zusammenfassung**der&nbsp; &nbsp; &nbsp; Ergebnisse:&nbsp; &nbsp; &nbsp;&#9744;Durchlauf&nbsp; &nbsp; &nbsp; &#9744;partiellen &#9744;Fehler

<table>
<tr><th colspan="2">Test Highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen von Lowlights  </th></tr><br/><tr><td><strong>Problem</strong>: festgelegt</td><td><strong>Behebung:</strong> TBD</td></tr>
<tr><th colspan="2">Identifizierte Blocker </td></tr>
<tr><td><strong>Blocker</strong>: festgelegt</td><td><strong>Behebung</strong>: festgelegt</td></tr>
</table>


> [!TIP]
> Um weitere Diskussionen während der letzten Überprüfung des Lenkungsausschusses zu ermöglichen, können Sie die aktualisierte [Test Ergebnismatrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) von myadvisor verwenden, um weitere Bereiche zu dokumentieren und hervorzuheben, für die eine Korrektur erforderlich ist. [](https://myadvisor.fasttrack.microsoft.com/)


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Bewerten Sie die Ergebnisse des Split-Tunnel-Tests, um sicherzustellen, dass der Echtzeitverkehr von Teams aus der RAS-Lösung ausgeschlossen wird.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Testergebnisse des Dokuments Split-Tunnel-Konnektivität in der Test Plan Ergebnis-Vorlage bereitgestellt.</li><li>Führen Sie Eskalations-und Sanierungspläne aus, um Probleme zu beheben, bei denen ein geeignetes Routing für die Unterstützung von Teams-Medien innerhalb einer Split-Tunnel-Konfiguration nicht möglich ist.</li><li>Planen Sie eine Sitzung des Lenkungsausschusses, um die Ergebnisse der Test Zusammenfassung zu überprüfen.</li><li>Präsentieren Sie dem Lenkungsausschuss Test Zusammenfassungsergebnisse, um alle Bereiche zu identifizieren, für die eine Sanierung erforderlich ist.</li></ul></td></tr>
</table>


<a name="execute-network-connectivity-and-performance-validation-by-using-the-network-assessment-tool-from-microsoft"></a>Ausführen von Netzwerkkonnektivität und Leistungsüberprüfung mithilfe des Tools für die Netzwerkbewertung von Microsoft
-----------------------------------------------------------------------------------------------------------

Das Netzwerk Bewertungstool von Microsoft führt Datenverkehrs Simulationen und Verbindungstests durch, indem simulierte Audiopakete für einen vordefinierten Zeitraum und die Anzahl der Iterationen an die nächstgelegene Edge-Website weitergeleitet werden, die eine Verbindung mit dem Teams-Dienst bereitstellt. Ein Ziel dieses Tests ist das Auswerten von Netzwerk Leistungsmetriken für Paketverluste, Jitter, Roundtrip-Latenz und den Prozentsatz der Paket Neuanordnung für jeden simulierten Anruf. Darüber hinaus überprüft der Test, ob die richtige Konnektivität zwischen internen und Edge-Netzwerkelementen für alle Edge-Ingress-Punkte zulässig ist, die die Konnektivität zu den Teams-Diensten unterstützen.

Weitere Informationen dazu, wie Sie die Netzwerk Bereitschaft von Teams für bestimmte Websites im Umfang bestätigen und bewerten können, finden Sie unter [Netzwerk](https://docs.microsoft.com/MicrosoftTeams/prepare-network) Bereitschaft.

> [!TIP]
>   Um die Netzwerkbereitschaftsanalyse und die Bereitschaft für Websites im Bereich abzuschließen, weisen Sie einen Lead für jede Website zu, die bei der Evaluierung Ihrer Netzwerk Bereitschaft behilflich sein kann.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie sich für das Netzwerk Beurteilungs-und Verbindungstest Profil für Websites im Bereich.</li><li>Entscheiden Sie sich für die Konfigurationsdatei Anforderungen für die Netzwerkbewertung für Websites im Bereich.</li></ol></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Konfigurieren Sie die Konfigurationsdatei Anforderungen für die Netzwerkbewertung für Websites im Bereich.</li><li>Führen Sie Netzwerkleistung und Verbindungsüberprüfung für Websites im Bereich aus.</li></ul></td></tr>
</table>



### <a name="document-network-connectivity-and-performance-validation-test-results"></a>Testergebnisse für die Dokument Netzwerkkonnektivität und Leistungsüberprüfung

Nachdem Sie alle Netzwerk Konnektivitäts-und Leistungstests für die Websites im Bereich abgeschlossen haben, erstellen Sie einen Bericht, der die Testergebnisse zusammenfasst und während der nächsten Überprüfung des Lenkungsausschusses präsentiert.

#### <a name="site-a-network-connectivity-and-performance-summary-report"></a>Website A: Bericht zu Netzwerkkonnektivität und Leistungszusammenfassung

> [!TIP]
> Nachfolgend finden Sie ein Beispiel für eine Netzwerkkonnektivität und eine Leistungs Zusammenfassungs Vorlage, die Sie während der nächsten Überprüfung des Lenkungsausschusses verwenden können, wenn Sie die Gesamtnetzwerk Bereitschaft für Websites im Bereich ermitteln.

**Ort: Seattle [in Wired] Client zu Office 365 Ergebnisse**

**Zusammenfassung**der&nbsp; &nbsp; &nbsp; Ergebnisse:&nbsp; &nbsp; &nbsp;&#9744;Durchlauf&nbsp; &nbsp; &nbsp; &#9744;partiellen &#9744;Fehler 



| Metrik                                                        |  Target                                                                                                            | Wochentag: Bürozeiten 9:30 Uhr bis 11:00 Uhr                                                                                                                                                                                                                                                                                                 | Wochentag: Office Hours 2:30 pm to 4:30 pm | Wochentag: nach Stunden 10:30 Uhr bis 12:30 Uhr | Wochenende: nach Stunden 9:30 Uhr bis 11:30 Uhr | Wochenende: nach Stunden 2:30 Uhr bis 4:30 Uhr |
|---------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------|-------------------------------------------|------------------------------------------|-----------------------------------------
| Latenz (eine Möglichkeit)                                             | \<50 ms                                                                                                           | 40 ms                                                                                                                                                                                                                                                                                                                                     | 38 MS                                    | 41 MS                                     | 35 MS                                    | 36 MS                                   |
| Latenz (Roundtrip-Zeit oder RTT)                             | \<100 MS                                                                                                          | 81 MS                                                                                                                                                                                                                                                                                                                                     | 77 MS                                    | 80 ms                                     | 72 MS                                    | 70 MS                                   |
| Burst-Paketverlust                                             | \<10% während eines beliebigen 200-MS-Intervalls                                                                                  | 3%                                                                                                                                                                                                                                                                                                                                        | 2                                       | 2                                        | 0,2%                                     | 0,1%                                    |
| Paketverlust                                                   | \<1% während eines 15-Sekunden-Intervalls                                                                                   | 0,4%                                                                                                                                                                                                                                                                                                                                      | 0,3%                                     | 0,3%                                      | 0,1%                                     | 0%                                      |
| Paket Inter-arrival Jitter                                   | \<30 ms während eines 15-Sekunden-Intervalls                                                                                | 12 ms                                                                                                                                                                                                                                                                                                                                     | 11 ms                                    | 13 ms                                     | 5 ms                                     | 5 ms                                    |
| Paket Reihenfolge                                                | \<0,05% Pakete außerhalb der Reihenfolge                                                                                      | 0 %                                                                                                                                                                                                                                                                                                                                        | 0 %                                       | 0 %                                        | 0 %                                       | 0 %                                      |



<table>
<tr><th colspan="2">Test Highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen von Lowlights  </th></tr> 
<tr><td><strong>Problem</strong>: große Latenz</td><td><strong>Behebung:</strong> Untersuchen Sie die Paketweiterleitung, und implementieren Sie die ideale Route.</td></tr>
<tr><td><strong>Problem</strong>: Roundtrip-Zeit&#39;t die Wartezeit verdoppeln</td><td><strong>Behebung:</strong> Untersuchen Sie eine mögliche Firewall oder Router-Konfigurationsproblem. Untersuchen von Verkehrswegen</td></tr>
<tr><td><strong>Problem</strong>: großer Paketverlust </td><td><strong>Behebung:</strong> Überprüfen Sie im Netzwerk Planner, ob genügend Bandbreite zugeteilt wurde. </td></tr>
<tr><td><strong>Problem</strong>: starker Jitter </td><td> <strong>Behebung:</strong> Überprüfen Sie, ob die richtigen DSCP-Werte (differenzierte Services Code Point) verwendet werden. </td></tr>
<tr><td><strong>Problem</strong>: großer Paketverlust </td><td><strong>Behebung:</strong> Untersuchen Sie den Paketverlust. </td></tr>
<tr><td><strong>Problem</strong>: höhere Paket Reihenfolge </td><td><strong>Behebung:</strong> Untersuchen Sie die Router-Warteschlange und die Bandbreite. </td></tr>
<tr><th colspan="2">Identifizierte Blocker </td></tr>
<tr><td><strong>Blocker</strong>: festgelegt</td><td><strong>Behebung</strong>: festgelegt</td></tr>
</table>




<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Bewerten Sie die Ergebnisse der Netzwerkbewertung und-Konnektivität, um sicherzustellen, dass Sie die Anforderungen unter <a href="https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance" data-raw-source="[Media quality and network connectivity performance](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)">Medienqualität und Netzwerkkonnektivität</a> für die Segmente Edge-Segment und Client erfüllen.</li><li>Haben Sie Netzwerkfunktionen zur Unterstützung von Echt Zeit Medien für alle Websites im Umfang ausgewertet?</li><li> Wenn Ihr Netzwerk nicht richtig bewertet wurde oder Sie wissen, dass es keine Echt Zeit Medien unterstützt, können Sie die Video-und Bildschirmfreigabe Funktionen deaktivieren, um die Auswirkungen auf das Netzwerk zu verringern und die Team Erfahrung für Benutzer zu verbessern?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren von Netzwerkleistung und Verbindungstest Ergebnissen</li><li>Führen Sie Eskalations-und Sanierungspläne aus, um Probleme mit Websites zu beheben, bei denen nicht genügend Bandbreite vorhanden ist, oder die Anforderungen an die Netzwerkleistung und Konnektivität nicht erfüllt werden.</li><li>Planen Sie eine Sitzung des Lenkungsausschusses, um die Ergebnisse der Test Zusammenfassung zu überprüfen.</li><li>Präsentieren Sie dem Lenkungsausschuss Test Zusammenfassungsergebnisse, um alle Bereiche zu identifizieren, für die eine Sanierung erforderlich ist.</li></ul></td></tr>
</table>


<a name="execute-subscriber-number-port-validation"></a>Portüberprüfung für Abonnenten Nummern ausführen
-----------------------------------------

Wenn Sie im Rahmen der Bereitstellung von Rufnummern für eingehende und ausgehende Anrufe im Telefon System mit Anruf Plan Diensten, die von Teams unterstützt werden, übertragen müssen, sollten Sie einen teilweisen Port für eine Dienstnummer ausführen. Auf diese Weise können Sie die Erwartungen, Anforderungen und die angemessene Zeitachse überprüfen, wenn Sie mit der Vorbereitung Ihrer Bereitstellung des Telefonsystems mit Anruf Plan Diensten in Ihrer Produktionsumgebung fertig sind.

Führen Sie die nachstehenden Schritte aus, um eine Teil Portierung einer Teilnehmernummer von Ihrem aktuellen PSTN-Dienstanbieter zu Teams abzuschließen.

#### <a name="step-1"></a>Schritt 1

Ermitteln Sie die Testnummer, die Sie an Office 365 portieren möchten, als eine übertragbare Benutzernummer (Teilnehmernummer), die über das Telefon System mit Anruf Plan Service in Teams gewartet werden soll.

> [!IMPORTANT]
>Achten Sie bei der Planung Ihres Nummern Portierungs Tests darauf, dass Sie die neuesten Richtlinien für die Nummern Portierungs Anforderungen in den [häufig gestellten Fragen](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)zu Number Port überprüfen.

#### <a name="step-2"></a>Schritt 2

Identifizieren und dokumentieren Sie alle Kontoinformationen (einschließlich des für das jeweilige Konto verwendeten namens) für den aktuellen Netzbetreiber der Testnummer, die Sie portieren werden.
In der Regel können Sie die benötigten Informationen in der letzten Rechnung oder Rechnung Ihres aktuellen Dienstanbieters finden.

> [!TIP]
>   Sie können Telefonnummern in allen derzeit unterstützten Ländern/Regionen portieren oder übertragen; die Art und Weise, wie Sie eine Portierungs Auftragsanforderung übermitteln, kann je nach Land/Region unterschiedlich sein, aus dem die Telefonnummern stammen. Die aktuelle Liste der derzeit unterstützten Länder/Regionen finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenz-und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).
> 
>   Weitere Informationen zum Übertragen von Telefonnummern in das Telefon System mit Anrufplänen sowie potenzielle Einschränkungen finden Sie unter [übertragen von Telefonnummern an Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365) und [gebührenfreie Wähleinschränkungen in Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/toll-free-dialing-limitations-and-restrictions.).

#### <a name="step-3"></a>Schritt 3

Laden Sie einen Letter of Authorization (LoA) für Ihr Land/Ihre Region, der auf "Service Number" basiert, als Nummernportierung herunter.

>[!NOTE]
>   Da sich die Formate für Loa nach Land, Region oder Zahlentyp unterscheiden können (geografischer Vergleich, nicht geografischer oder Nutzerzahl versus Dienst oder gebührenfreie Nummer), stellen Sie sicher, dass Sie die richtige Loa-Vorlage für Ihren bestimmten szenariotyp verwenden. Weitere Informationen zum Auswählen des Loa oder direkt zur [Download Seite](https://www.microsoft.com/download/details.aspx?id=49167)finden Sie unter [Herunterladen eines Genehmigungsschreibens (LoA)](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/download-a-letter-of-authorization-loa) .

>[!NOTE]
> **Nur Vereinigte Staaten**<br/>
>   Da wir nur eine Dienstnummer für diesen Test portieren, stellen Sie sicher, dass Sie die entsprechenden Felder in der Loa auswählen, wie unten dargestellt:

![Wie viele Telefonnummern werden übertragen? Antwort: Ich übertrage nur einige meiner Nummern von meinem derzeitigen Netzbetreiber.] (media/onboarding-test-plan-image1.png "Wie viele Telefonnummern werden übertragen? Antwort: Ich übertrage nur einige meiner Nummern von meinem derzeitigen Netzbetreiber.")

![Welche Art von Telefonnummern werden Sie übertragen? Antwort: Ich übertrage Telefonnummern für Sprachdienste wie für automatische Telefonzentralen oder Konferenz Brücken.] (media/onboarding-test-plan-image2.png "Welche Art von Telefonnummern werden Sie übertragen? Antwort: Ich übertrage Telefonnummern für Sprachdienste wie für automatische Telefonzentralen oder Konferenz Brücken.")

>[!IMPORTANT]
>   Wenn Sie Telefonnummern manuell mithilfe eines Loa portieren, stellen Sie sicher, dass Sie die richtige Art von Telefonnummer auswählen. Sie müssen für jede zur Übertragung vorgesehene Art von Telefonnummer einen separaten Portierungsauftrag einreichen.<br/><br/>
>   Da wir den Nummern Portierungsprozess mithilfe einer Telefonnummer testen möchten, die mit der gleichen Abrechnungs Telefonnummer (BTN) verbunden ist, müssen Sie sicherstellen, dass die Abrechnungs Telefonnummer *nicht* in der angegebenen Telefonnummer enthalten ist, die portiert werden soll.

#### <a name="step-4"></a>Schritt 4

Wechseln Sie im Mandanten-Admin-Portal zur Registerkarte **Support** , und erstellen und senden Sie eine Serviceanfrage. Fügen Sie die fertige Loa-Datei an, um die Telefonnummer zu planen, die Ihrem aktuellen Dienstanbieter für die Migration zugeordnet ist. Informationen zum Auswählen der Dienst Anforderungsmethode, die für Ihre Mandanten Größe am besten geeignet ist, finden Sie unter Manuelles über [Mitteln einer benutzerdefinierten Serviceanfrage](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/manually-submit-a-custom-service-request).

Nachdem die Support-Anfrage eingegangen ist, wird der Microsoft-Support nach der von Ihnen ausgewählten Kommunikationsmethode nachverfolgen und Sie über den Status und die nächsten Schritte zum Abschließen des Nummern Portierungs Prozesses informieren.

#### <a name="step-5"></a>Schritt 5

Nachdem die Nummer bestätigt wurde, dass Sie als neue Rufnummer in Office 365 portiert wurde, weisen Sie die Nummer dem Telefon System mit Anruf Plandienst zu, indem Sie zum mandantenadministrator-Portal \> **Skype for Business Admin Center** \> **wechseln. Sprachausgabe**. Weisen Sie auf der Registerkarte **Telefonnummern** die neue Dienstnummer dem Telefon System mit Anruf Plandienst zu.

> [!TIP]
>   Obwohl diese Aufgabe dem Telefon System eine neue Dienstnummer mit Anrufplänen zuweist, wird zum Zeitpunkt der Erstellung dieses Artikels die Verwaltung für diese Aufgabe mithilfe des Skype for Business admin Centers abgeschlossen.

#### <a name="step-6"></a>Schritt 6

Nachdem Sie die portierte Teilnehmernummer zugewiesen haben, müssen Sie sich als Benutzer bei einem Team-Client anmelden und über das PSTN eine externe 10-stellige Nummer wählen. Nachdem Sie den Anruf tätigen, stellen Sie sicher, dass der Anruf verbunden wurde und dass die angezeigte Rufnummernanzeige mit der von Ihnen portierten Abonnentennummer übereinstimmt.

#### <a name="step-7"></a>Schritt 7

Führen Sie von einer externen PSTN-Nummer einen Anruf an die Abonnentennummer, die Sie nach Office 365 portiert haben, und überprüfen Sie, ob der Anruf eingehende und über den Team-Client verbundene Anrufe empfangen wird.



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche inländischen Teilnehmer Nummern Sie nach Land/Region portieren müssen.</li><li>Entscheiden Sie, welche Loa-Vorlage Sie verwenden möchten.</li><li>Ermitteln Sie, ob Ihr derzeitiger Netzbetreiber (Unternehmens-Carrier) die Fragmentierung von Telefonnummern zulässt (also teilweise Port Bestellungen zulässt).</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Sammeln Sie die erforderlichen Informationen, und bereiten Sie die LOAs vor.</li><li>Laden Sie die benötigten Loa-Vorlagen herunter, und füllen Sie Sie aus.</li><li>Übermitteln Sie eine Portierungs Anfrage für eine Teilnehmernummer.</li><li>Führen Sie die Testüberprüfung für portierte Nummern durch, indem Sie diese dem Telefon System mit dem Anruf Plandienst für Einwahlzugriff zuweisen und bestätigen, dass Sie funktionieren, wie in den Schritten 6 und 7 weiter oben in diesem Abschnitt beschrieben.</li></ul></td></tr>
</table>


### <a name="document-service-number-porting-test-results"></a>Portieren von Testergebnissen für die Dokumentdienst Nummer

Nachdem Sie alle Teilnehmer Nummern Tests abgeschlossen haben, erstellen Sie einen Bericht, der die Testergebnisse zusammenfasst, die während der nächsten Überprüfung des Lenkungsausschusses zu präsentieren sind.

#### <a name="site-a-number-porting-test-summary-report"></a>Bericht "Website A: Nummern Portierungs Test"

> [!TIP]
>   Nachfolgend finden Sie eine Beispielvorlage für Test Zusammenfassungsberichte, die Sie während der nächsten Sitzung des Lenkungsausschusses zur Überprüfung verwenden können, wenn Sie entscheiden, wann das Telefon System mit Anruf Plan Diensten in der Pilot Phase integriert werden soll.

**Dienstnummern Portierung**

**Zusammenfassung**der&nbsp; &nbsp; &nbsp; Ergebnisse:&nbsp; &nbsp; &nbsp;&#9744;Durchlauf&nbsp; &nbsp; &nbsp; &#9744;partiellen &#9744;Fehler 

<table>
<tr><th colspan="2">Test Highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen von Lowlights  </th></tr><br/><tr><td><strong>Problem</strong>: festgelegt</td><td><strong>Behebung:</strong> TBD</td></tr>
<tr><th colspan="2">Identifizierte Blocker </td></tr>
<tr><td><strong>Blocker</strong>: festgelegt</td><td><strong>Behebung</strong>: festgelegt</td></tr>
</table>


> [!TIP]
>   Zur Erleichterung weiterer Diskussionen während der letzten Überprüfung des Lenkungsausschusses können Sie die aktualisierte [Testergebnis Matrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) verwenden, [](https://myadvisor.fasttrack.microsoft.com/) die von myadvisor zur Verfügung gestellt wird, um weitere Testbereiche zu dokumentieren und hervorzuheben, die eine Korrektur erfordern.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Überprüfen Sie, ob die für die Migration übermittelten Abonnenten Nummern erfolgreich mit dem Anruf Plandienst auf das Telefon System portiert wurden.</li><li>Überprüfen Sie, ob Sie dem Telefon System die portierte Dienstnummer mit Anruf Plandienst zuweisen konnten.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie Ihre Nummer, um die Testergebnisse zu portieren.</li><li>Führen Sie Eskalations-und Sanierungspläne aus, um Probleme zu beheben, die Sie mit dem Nummern Portierungsprozess (falls vorhanden) hatten.</li><li>Planen Sie eine Sitzung des Lenkungsausschusses, um die Ergebnisse der Test Zusammenfassung zu überprüfen.</li><li>Präsentieren Sie die Test Zusammenfassungsergebnisse dem Lenkungsausschuss, um alle Bereiche zu identifizieren, die eine Sanierung erfordern.</li></ul></td></tr>
</table>


<a name="execute-your-test-plan-for-phone-system-with-calling-plans"></a>Ausführen Ihres Testplans für das Telefon System mit Anrufplänen
----------------------------------------------------------

Nachdem Sie Ihren Testplan definiert haben, besteht der nächste Schritt darin, die Testfälle zu durchlaufen, wobei der Schwerpunkt auf der Bewertung des Telefonsystems mit der Verwaltung von Anrufplänen und den Features der Benutzeroberfläche im Bereich liegt. Überprüfen Sie vor dem eigentlichen testen, ob die unten aufgeführten testvoraussetzungen vorhanden sind.

### <a name="phone-system-with-calling-plans-testing-prerequisites"></a>Telefon System mit Voraussetzungen für das Testen von Anrufplänen

-   Für das Telefon System wurden Unternehmens-Anwendungsfälle mit Anruf Plan Service definiert.

-   Wichtige Stakeholder wurden identifiziert.

-   Die für das Telefon System erforderliche Lizenzierung mit Anruf Plan Diensten steht zur Verfügung und wurde der Gruppe der Benutzer im Bereich zugewiesen.

-   Die Liste der Organisations Websites und Benutzergruppen im Bereich wurde identifiziert.

-   [Guthaben](what-are-communications-credits.md) für Kommunikationen (falls erforderlich) wurden für Ihre Organisation eingerichtet.

-   Telefon System mit Einstellungen für Anrufpläne wurden identifiziert und konfiguriert.

-   Einstellungen für den Mandanten Wähl Plan, die das Telefon System mit Anrufplänen unterstützen, wurden für die Gruppe der Benutzer im Bereich identifiziert, konfiguriert und angewendet.

-   Das Telefon System mit den Richtlinien für Anrufpläne wurde für die Gruppe der Benutzer im Bereich identifiziert und konfiguriert.

-   Telefon System mit Anrufplänen Compliance-Anforderungen wurden für die Gruppe der Benutzer im Bereich identifiziert und konfiguriert.

### <a name="document-phone-system-with-calling-plans-test-case-passfail-status"></a>Dokument-Telefon System mit Anrufplänen Test Case Pass/Fail-Status

Wenn Testfälle für die Features für die Verwaltungs-und Benutzer Telefonsystem Funktionen in Scope ausgewertet werden, überwachen Sie die Ergebnisse jedes Testfalls, um den Status "Pass/Partial/Fail" zusammen mit der zugewiesenen ID des Fehlers anzuzeigen, falls unvorhergesehene Probleme auftreten.

#### <a name="phone-system-with-calling-plans-test-case-status"></a>Telefon System mit Anrufplänen Test Case-Status

> [!TIP]
>   Nachfolgend finden Sie eine Beispiel-Testfallstatus Vorlage, mit der Sie Testergebnisse zur Überprüfung während der nächsten Sitzung des Lenkungsausschusses dokumentieren können, wenn Sie entscheiden, wann das Telefon System mit Anruf Plan Diensten in der Pilot Phase verwendet werden soll.

| Telefon System mit Anrufplänen          |                              |                                                                                            |                           |                                                                            |
|------------------------------------------|------------------------------|--------------------------------------------------------------------------------------------|---------------------------|----------------------------------------------------------------------------|
| Test Case-ID                             | Test Case-Titel              | Test Fallbeschreibung                                                                      | Zusammenfassung des Test Fall Ergebnisses | Zugewiesene Fehler-ID (falls zutreffend)                                         |
| 1                                        | Ausgehende PSTN-Anrufe. | Einen ausgehenden Anruf tätigen, indem Sie eine inländische 10-stellige Nummer wählen.                              |    &#9744;Pass<br/>&#9744;teilweise<br/> &#9744;Fehler                   | Wenn ein Benutzer eine vierstellige Zahl eingibt, schlägt der für das PSTN festgelegte Anruf fehl. |



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Auswerten des Status "Test Case Pass/Fehler" auf hoher Ebene nach Standort für Telefon System mit Funktionen für Anrufpläne im Umfang.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie die Ergebnisse des Testfallstatus für alle im Bereich abgeschlossenen Testfälle.</li><li>Planen Sie eine Sitzung des Lenkungsausschusses, um die Ergebnisse der Test Zusammenfassung zu überprüfen.</li><li>Präsentieren Sie dem Lenkungsausschuss Test Case-Status Ergebnisse, um alle Bereiche zu identifizieren, für die eine Sanierung erforderlich ist.</li></ul></td></tr>
</table>


### <a name="document-phone-system-with-calling-plans-testing-result-summary"></a>Dokument-Telefon System mit Testergebnis Zusammenfassung für Anrufpläne

Nachdem alle Test Cases, die das Telefonsystem mit den Funktionen für Anrufpläne im Bereich unterstützen, von der Website ausgefüllt wurden, dokumentieren Sie die Ergebnisse während einer Sitzung des Lenkungsausschusses, wenn Sie entscheiden, wann das Telefonsystem mit Anruf Plan Diensten im Pilot Modus aktiviert werden soll. Phase.

#### <a name="site-a-phone-system-with-calling-plans-test-case-summary-report"></a>Website A: Telefon System mit einem Anruf Plan Test Fall Zusammenfassungsbericht:

> [!TIP]
>   Nachfolgend finden Sie eine Beispielvorlage für Test Zusammenfassungsberichte, die Sie während der nächsten Sitzung des Lenkungsausschusses überprüfen können, wenn Sie entscheiden, wann das Telefon System mit Anruf Plan Diensten in der Pilot Phase integriert werden soll.


**Teams-Telefon System mit Anrufplänen**

**Zusammenfassung**der&nbsp; &nbsp; &nbsp; Ergebnisse:&nbsp; &nbsp; &nbsp;&#9744;Durchlauf&nbsp; &nbsp; &nbsp; &#9744;partiellen &#9744;Fehler 

<table>
<tr><th colspan="2">Test Highlights </th></tr>
<tr><td>TBD</td><td>TBD</td></tr>
<tr><th colspan="2">Testen von Lowlights  </th></tr><br/><tr><td><strong>Problem</strong>: festgelegt</td><td><strong>Behebung:</strong> TBD</td></tr>
<tr><th colspan="2">Identifizierte Blocker </td></tr>
<tr><td><strong>Blocker</strong>: festgelegt</td><td><strong>Behebung</strong>: festgelegt</td></tr>
</table>


> [!TIP]
>   Um weitere Diskussionen während der letzten Überprüfung des Lenkungsausschusses zu erleichtern, können Sie die aktualisierte [Test Ergebnismatrix](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=5_1_0_21) verwenden, die von myadvisor zur Verfügung gestellt wird, um zusätzliche Bereiche zu dokumentieren und hervorzuheben, für die eine Korrektur erforderlich ist. [](https://myadvisor.fasttrack.microsoft.com/)



<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Auswerten von Zusammenfassungs Ergebnissen für Testergebnisse nach Standort für Telefon System mit Funktionen für Anrufpläne im Umfang.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokumentieren Sie den Test Fall Zusammenfassungsbericht, nachdem alle Testfallergebnisse abgeschlossen wurden.</li><li>Planen Sie eine Sitzung des Lenkungsausschusses, um die Ergebnisse der Test Zusammenfassung zu überprüfen.</li><li>Präsentieren Sie dem Lenkungsausschuss Test Zusammenfassungsergebnisse, um alle Bereiche zu identifizieren, für die eine Sanierung erforderlich ist.</li></ul></td></tr>
</table>



<a name="present-and-report-phone-system-with-calling-plans-test-findings"></a>Präsentieren und melden von Telefonsystemen mit Anrufplänen Testergebnisse
----------------------------------------------------------------

Nachdem alle Testaktivitäten abgeschlossen sind und etwaige Fehler mit einer Auswirkung von "gering" behoben wurden, planen Sie eine abschließende Besprechung mit den festgelegten Test beteiligten. In der Besprechung:

-   Status Zusammenfassung

-   Hervorhebungs-Lowlights

-   Gelernte Lektionen

-   Allgemeine Empfehlung: fahren Sie mit der Pilot Phase fort, oder überprüfen Sie die Testergebnisse erneut.

-   Test Matrix Ergebnisse (diese sollten vollständig in einem Anhang dokumentiert sein)

#### <a name="test-plan-deliverables"></a>Ergebnisse des Test Plans:

> [!TIP]
>   Nachfolgend finden Sie ein Beispiel für eine Vorlage für den Testplan, die Sie verwenden können, um die Kriterien zu dokumentieren, die erforderlich sind, um die Abmeldung zu erreichen und die Testphase zu beenden, oder das Testen auszusetzen, bis alle identifizierten Probleme vollständig aufgelöst sind.

| Status Zusammenfassung               | Highlights/Lowlights | Gelernte Lektionen | Schluss Empfehlung |
|------------------------------|----------------------|-----------------|------------------------|
| <ul><li>Test Case-Durchlauf Rate von "%"</li><li>Alle Tests wurden erfolgreich durchgeführt</li></ul> | TBD                  | TBD             | Weiter zu Pilot       |

-   Alle Tests wurden erfolgreich durchgeführt


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/><br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie sich für die Statuszusammenfassung des Tests.</li><li>Ermitteln von Test Highlights und Lowlights</li><li>Ermitteln der gelernten Lektionen</li><li>Entscheiden Sie, welche Behebungsaktionen ggf. verbleiben.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Nächste Schritte</td><td><ul><li>Dokument Test Zusammenfassungsergebnisse enthalten:<ul><li>Status Zusammenfassung</li><li>Highlights/Lowlights</li><li>Gelernte Lektionen</li></ul></li><li>Planen Sie eine endgültige Sitzung des Lenkungsausschusses, um die Testergebnisse zu überprüfen.</li><li>Präsentieren Sie Test Zusammenfassungsergebnisse während einer Überprüfung des Lenkungsausschusses, um eine endgültige Abmeldung für das Beenden der Testphase zu erhalten.</li></ul></td></tr>
</table>
