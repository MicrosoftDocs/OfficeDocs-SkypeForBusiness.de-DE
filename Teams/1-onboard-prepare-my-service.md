---
title: Vorbereiten der Bereitstellung von VoIP-Clouddienst Microsoft-Teams
author: rmw2890
ms.author: MyAdvisor
manager: serdars
ms.date: 06/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Verwenden Sie Onboarding Prüflisten zum Vorbereiten von Office 365 für Teams und Konfigurieren von Teams Kernfunktionen, Netzwerk, und cloud-VoIP-Arbeitslasten.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e115ac93a63fb007787a4324c56793c996723c64
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850205"
---
# <a name="prepare-my-service"></a>Meine Service vorbereiten

Dieser Artikel bietet eine Übersicht über die Anforderungen bei der Vorbereitung von Cloud-VoIP-Dienste für Ihre Organisation. Vorbereiten der ordnungsgemäß, können Sie sein sicher, dass Sie Cloud Voice-Funktionen in Ihrer Organisation bereitstellen möchten.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Onboarding Checklisten für die Microsoft-Teams, VoIP-Arbeitslasten

Die folgenden Prüflisten führen Sie durch die Schritte für die Implementierung von Audiokonferenzen, Telefonsystem mit Aufrufen plant ("aufrufen plant") und Funktionen Phone System direkten Routing ("Direktes Routing") im Microsoft-Teams.

*  [Vorbereiten der Office 365 für Teams](onboarding-checklist-enable-office-365.md)

*  [Konfigurieren von Teams Kernfunktionen](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Netzwerk konfigurieren](onboarding-checklist-configure-networking.md)

*  [Konfigurieren von VoIP-Arbeitslasten Cloud in Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Konfigurieren der direkten Weiterleitung von Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Die Aufgaben und Aktivitäten in dieser Prüflisten sind die Core "Aufgabe" Elemente, die in jeder Bereitstellung von Cloud-Sprachfunktionen mit Teams liegen. Sie können die Prüflisten zum Einschließen von Aktivitäten und Aufgaben, die speziell für Ihre eigenen Teams Reise anpassen.

>[!NOTE]
>Diese Anleitung konzentriert sich ausschließlich auf aufrufen plant, Audiokonferenzen und direkte Routing. Wenn Sie neue Teams sind, überprüfen Sie die [Übersicht der Microsoft-Teams](teams-overview.md). Allgemeine Richtlinien zum Planen der Bereitstellung von Teams finden Sie im [Planungshandbuch für Microsoft Teams](quick-start-enable-teams.md).

Verwenden Sie die bereitgestellten Prüflisten zum Nachverfolgen des Status der jede einzelne Aktivität und jede Aufgabe, und um sicherzustellen, dass Sie alle wichtigen Schritte übersprungen noch nicht. Jede Aktivität enthält eine ausführliche Beschreibung der erforderlichen Aktionen und Verweise auf zusätzliche Informationen, die Sie verwenden können, um diese Aktivität abgeschlossen haben.

Obwohl es wird empfohlen, dass Sie die Prüflisten in Reihenfolge ausführen, wird der Umfang der Bereitstellung und Konfiguration und Komplexität der Umgebung die genauen Reihenfolge abhängen. Sie sind so angeordnet, dass entweder ein "ohne bestehende Infrastruktur" unterstützt Teams Bereitstellung (eine mit keine vorherigen Skype für Business Onlineanwesenheit) oder die Migration von Skype für Business Online zu Teams. Wenn Sie von Skype für Business Online migrieren, möglicherweise haben bereits abgeschlossen einige dieser Aktivitäten und jetzt ignorieren können.

Wenn Sie Onboarding-Benutzer auf eine Websitebasis sind, empfehlen wir nachdrücklich für die Verwendung der [Website Aktivierung Playbook für VoIP (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) als zusätzliche Anleitung zu dieser Prüflisten.

>[!NOTE]
>Die meisten Konfigurationseinstellungen gelten sowohl für Teams und Skype für Business Online. Verwenden Sie Office 365 Skype für Business-Verwaltungskonsole, um diese Einstellungen zu konfigurieren.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Wer wird für die Aufsicht über den Abschluss der Onboarding Prüflisten zuständig sein?</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Laden Sie die Prüflisten Onboarding.</li><li>Durch die Onboarding Prüfliste Elemente schrittweise nach Plan für die Bereitstellung Ihrer Organisation arbeiten.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Onboarding fortsetzen

Nach Abschluss dieser Prüflisten benötigen Sie erfolgreich Voice-Funktionen für Ihre Bereitstellung Teams hinzugefügt haben.

Als Nächstes verwenden Sie die [Website Aktivierung Playbook für VoIP (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) Einstieg erleichtern die Benutzer auf jeder Website durch, und dazu beitragen Sie, dass Sie beim Planen und Ausführen von wichtigen standortspezifische Aktivitäten.

-   Plan für die Einführung der bereit von Standorten

-   Service-Management Prozess herstellen

-   Ausführen von Tests und-Wartung

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Test Cloud VoIP Arbeitslasten in Teams

Nachdem Sie definiert und die Teams Cloud VoIP geschäftlichen Erfolg und technische Pläne als Teil der Phase Ermitteln übergeordneter Faktoren dokumentiert und in der Verwaltungskonsole gewünschte Konfiguration vorgenommen, wird im nächste Schritt zu überprüfen, die Ihre Organisation die Erwartungen und Anforderungen erfüllt sind über Features, Funktionen und Verwendbarkeit. Sie sollten diese Validierungsschritt führen Sie vor der Bereitstellung einer pilot oder final-bereitstellungs in Ihrer produktionsumgebung.

Sie können Business Erfolg planen nutzen, die Sie während der Phase der Ermitteln übergeordneter Faktoren dienen als Grundlage für die Bestimmung der Aktivitäten, erwartet, die Funktionalität der Testfälle und allgemeine Bereich während der Testphase ausgewertet werden definiert haben.

## <a name="define-your-testing-approach"></a>Definieren Sie Ihren testing Ansatz

In der einfachsten Form Ihre testing Ansatz basiert auf Ihre Funktion Funktionen von Audiokonferenzen, aufrufen plant, überprüfen oder direkte Routingdienst und Entwickeln von einen Test planen, um sicherzustellen, dass Ihre Funktionalität für Benutzer im Gültigkeitsbereich erfüllt sind. Es folgt ein Beispiel Testplan für die integrierte Phase einer Audiokonferenz Implementierung.


| So testen Sie Audio Feature für Einwahlkonferenzen | Zusammenfassung der Ergebnisse | Zusätzliche Hinweise |
|------------|-----------------|------------------|
| Planen Sie eine Ad-hoc-Teams Besprechung, die Einwahlinformationen Audiokonferenzen enthält | Bestanden wurden oder   | TBD |
| Verwenden Sie ein Telefon zur Erfüllung von Audio in einer Besprechung über das Telefonfestnetz erreichen, indem er mit den bereitgestellten Informationen Zugriffsnummer für Einwahl | Bestanden wurden oder | TBD |
| Teilnehmen an andere Personen zu einer vorhandenen Besprechung durch Telefonverbindung über das Telefonfestnetz | Bestanden wurden oder | TBD |



| Aufrufen von Plänen oder direkten Routing feature zum Testen | Zusammenfassung der Ergebnisse | Zusätzliche Hinweise |
|----------------------------------------------------|-----------------|------------------|
| Stellen Sie einen PSTN-Anruf durch wählen eine PSTN-Nummer       | Bestanden wurden oder       | TBD |
| Erhalten Sie einen PSTN-Anruf durch Wählen der PSTN-Nummer aus einer externen Zeile (mobile, Festnetz) | Bestanden wurden oder | TBD|
| Übertragen Sie einen PSTN-Anruf von einem Benutzer von Teams auf einen anderen | Bestanden wurden oder | TBD |


>[!TIP]
>Zur Erleichterung der Testfall Erstellung als Ausgangspunkt finden Sie in der Liste der Benutzer Anleitungen verfügbar unter [Teams Besprechungen und Telefonkonferenzen](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Einrichten von Cloud-VoIP-Arbeitslasten für Teams

Nun, da Sie Ihren testing Ansatz definiert haben, wird im nächste Schritt der Service-Umgebung und den Benutzer im Gültigkeitsbereich für Teams Cloud VoIP-Funktionen konfigurieren.

Weitere Informationen finden Sie unter:

- [Technische Planung für Audiokonferenzen](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [Einrichten von Audiokonferenzen für Skype for Business und Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)

- [Technische Telefonsystem mit dem Aufrufen der Pläne planen](phone-system-with-calling-plans.md#technical-planning-for-phone-system-with-calling-plans)

- [Einrichten von Aufrufen Pläne für Skype für Unternehmen und die Microsoft-Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planen der direkten Routing](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Konfigurieren der Weiterleitung von direkten](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Führen Sie den Testplan

[//]: # (Okay bearbeiten? "User" erschien mir etwas nicht eindeutig.)
Nachdem die Umgebung des Benutzers und der Dienst konfiguriert haben, enthält der letzte Schritt testen Test Plan Ausführung mit Fokus auf Features und Funktionen Überprüfung. 

**Audiokonferenzen Voraussetzungen und Annahmen für Benutzer und Standorte im Bereich testen:**

-   Business verwenden Sie Groß-/Kleinschreibung Definition für die Audiokonferenz Service abgeschlossen wurde.

-   Lizenzierung für Audiokonferenzen erforderlich ist verfügbar und zugewiesen wurde.

-   Die Liste der Organisationseinheit Standorte und Benutzergruppen ermittelt wurden.

-   Die Liste der dedizierten und freigegebene Audiokonferenz einwählen und Nummern mit bevorzugte Sprache identifiziert und konfiguriert wurden.

-   [Communications haben](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (falls erforderlich) Ihrer Organisation eingerichtet wurden.

-   Live Meeting-Konferenz Bridge audioeinstellungen wurden identifiziert und konfiguriert (PIN-Mindestlänge, Eintrag/Exit Benachrichtigungen, Aktivierung Benachrichtigung Option Sie bevorzugen).

-   Mandanten Sie konferenzrichtlinien, und wählen Sie planen von Einstellungen, die Audiokonferenz unterstützen Dial-Out-Szenarien identifiziert, angewendet und konfiguriert wurden.

-   Audio Conferencing Compliance-Bestimmungen haben identifiziert und konfiguriert wurden.

**Aufrufen von Pläne Voraussetzungen und Annahmen für Benutzer und Standorte im Bereich testen:**

-   Business verwenden Sie Groß-/Kleinschreibung Definition für den Aufruf von plant Service abgeschlossen wurde.

-   Lizenzierung für aufrufen Pläne erforderlich ist verfügbar und zugewiesen wurde.

-   Die Liste der Organisationseinheit Standorte und Benutzergruppen ermittelt wurden.

-   Rufnummern, die Benutzern zugewiesen werden wurden erworben oder Microsoft und sind in den Mandanten Portal übertragen.

-   [Communications haben](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/what-are-communications-credits) (falls erforderlich) Ihrer Organisation eingerichtet wurden.

-   Mandanten Benutzerrichtlinien und Wähleinstellungen, die Pläne aufrufen Szenarios unterstützen haben identifiziert, angewendet und konfiguriert wurden.

-   Aufrufen von Plänen Compliance-Bestimmungen identifiziert und konfiguriert wurden.

**Direkte Routing Voraussetzungen und Annahmen für Benutzer und Standorte im Bereich testen:**

-   Business verwenden Sie Groß-/Kleinschreibung Definition für das direkte Routing Service abgeschlossen wurde.

-   Lizenzierung für das direkte Routing erforderlich ist verfügbar und zugewiesen wurde.

-   Die Liste der Organisationseinheit Standorte und Benutzergruppen ermittelt wurden.

-   Eine [zertifizierte Session Border Controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) wurde bereitgestellt, konfiguriert und gepaart mit einer Telefonsystem.

-   Enterprise-VoIP aktiviert wurde, und die Rufnummern zugewiesen wurden.

-   VoIP-Routingrichtlinien zurückgegeben haben identifiziert, konfiguriert und zugewiesen.

-   Microsoft-Teams wurde als bevorzugter Client aufrufende für die Benutzer im Bereich festgelegt.
 
-   Direktes Routing Compliance Anforderungen identifiziert und konfiguriert wurden.

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden, welche Funktionen der Audiokonferenz Feature bereitgestellt werden soll (service Entscheidung).</li><li>Identifizieren der Anforderungen an den Funktionen für Audiokonferenzen.</li><li>Identifizieren Sie die Konfiguration der dienstanforderungen für Audiokonferenzen.</li><br><li>Entscheiden Sie, ob direkten Routing oder aufrufen plant bereitgestellt und konfiguriert wird.<li>Entscheiden, welche Telefonsystem Feature Funktionen bereitgestellt werden soll (service Entscheidung).</li><li>Identifizieren der Anforderungen für Benutzer-Funktionalität für direkte Routing oder plant aufrufen.</li><li>Identifizieren Sie Service Konfigurationsaufwand für direkte Routing oder plant aufrufen.</li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Nächste Schritte</td><td><ul><li>Entwickeln Sie und Dokumentieren Sie Ihren Test Plan Ansatz.</li><li>Vorbereiten der Service-Umgebung und Benutzer für Audiokonferenzen Features im Bereich.</li><li>Vorbereiten der Service-Umgebung und Benutzer für den Aufruf von Plänen oder direkten Routing Features im Bereich.</li><li>Führen Sie Test-Überprüfung für die Audiokonferenz-Features, die Sie aktivieren möchten.</li><li>Führen Sie Test-Überprüfung für die direkte Routing oder plant aufrufen Features, die Sie aktivieren möchten.</li><li>Testen Sie für alle Fehler, bestätigen Sie, dass Ihre Konfiguration korrekt ist, Community-Artikel zu lesen und – falls erforderlich – auslösen eine Supportanfrage.</li></ul></td></tr>
</table>


Weitere ausführliche Anleitungen zur Durchführung von Tests für Audiokonferenzen in Teams finden Sie unter der- [ausführliche Anleitung für Audiokonferenzen testen](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).

Weitere ausführliche Anleitungen zur Durchführung von Tests für Aufrufen in Teams plant finden Sie unter der- [ausführliche Anleitung für Telefonsystem testen](onboarding-test-plan-for-enterprises-Phone-System.md).

<!--ENDOFSECTION-->
