---
title: Vorbereiten der Bereitstellung des Microsoft Teams-Cloud Voice-Diensts
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Verwenden Sie Onboarding-Checklisten, um Office 365 für Teams vorzubereiten und die Kernfunktionen von Teams, Netzwerke und Cloud-VoIP-Workloads zu konfigurieren.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c2316376bd2dfddce99e63fe4ab66c5e33eb813e
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344829"
---
# <a name="prepare-my-service"></a>Vorbereiten des Diensts

Dieser Artikel enthält eine Übersicht über die Anforderungen für das Vorbereiten von Cloud-VoIP-Diensten für Ihre Organisation. Wenn Sie ordnungsgemäß vorbereitet sind, können Sie sicherstellen, dass Sie bereit sind, Ihrer Organisation Cloud-Sprachfunktionen bereitzustellen.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Onboarding-Checklisten für Microsoft Teams-sprach Auslastungen

Die folgenden Checklisten führen Sie durch die Schritte zum Implementieren von Audiokonferenzen, Telefonsystemen mit Anrufplänen ("Anrufpläne") und von Telefonsystem-direkt Routing ("Direct Routing") in Microsoft Teams.

*  [Vorbereiten von Office 365 für Teams](onboarding-checklist-enable-office-365.md)

*  [Konfigurieren der Kernfunktionen von Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Netzwerk konfigurieren](onboarding-checklist-configure-networking.md)

*  [Konfigurieren von Cloud-sprach Auslastungen in Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Konfigurieren des direkten Routings in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Die Aufgaben und Aktivitäten in diesen Prüflisten sind die Kernaufgaben, die für jede Bereitstellung von Cloud-Sprachfunktionen in Teams gelten. Sie können die Checklisten anpassen, um die Aktivitäten und Aufgaben einzubeziehen, die für Ihre eigene Teams-Reise spezifisch sind.

>[!NOTE]
>Dieser Leitfaden konzentriert sich ausschließlich auf Anrufpläne, Audiokonferenzen und direktes Routing. Wenn Sie neu bei Microsoft Teams sind, überprüfen Sie die [Übersicht über Microsoft Teams](teams-overview.md). Allgemeine Anleitungen zum Planen der Bereitstellung von Teams finden Sie unter [Bereitstellen von Chat, Teams, Kanälen und apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).

Verwenden Sie die bereitgestellten Checklisten, um den Status der einzelnen Aktivitäten und Aufgaben zu überwachen und sicherzustellen, dass Sie keine kritischen Schritte übersprungen haben. Jede Aktivität umfasst eine detaillierte Beschreibung der erforderlichen Aktionen und Verweise auf zusätzliche Informationen, die Sie zum Ausführen dieser Aktivität verwenden können.

Obwohl es empfehlenswert ist, die Checklisten in der richtigen Reihenfolge zu befolgen, hängt die genaue Reihenfolge vom Umfang ihrer Bereitstellung und der Konfiguration und Komplexität Ihrer Umgebung ab. Sie sind so organisiert, dass Sie eine "Greenfield"-Teams-Bereitstellung (eine ohne vorherige Skype for Business Online-Anwesenheit) oder die Migration von Skype for Business Online zu Teams unterstützen. Wenn Sie von Skype for Business Online migrieren, haben Sie möglicherweise bereits einige dieser Aktivitäten abgeschlossen und können diese jetzt ignorieren.

Wenn Sie Benutzer pro Website an Bord haben, wird dringend empfohlen, dass Sie das Textbuch [für die Website Aktivierung](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) als ergänzende Anleitung für diese Checklisten verwenden.

>[!NOTE]
>Die meisten Konfigurationseinstellungen sind zwischen Teams und Skype for Business Online üblich. Sie verwenden das Microsoft 365 Admin Center und das Microsoft Teams Admin Center, um diese Einstellungen zu konfigurieren.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Wer ist für die Überwachung der Fertigstellung der Onboarding-Checklisten zuständig?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Laden Sie die Checklisten für Onboarding herunter.</li><li>Arbeiten Sie schrittweise über die Elemente der Onboarding-Checkliste in Übereinstimmung mit dem Bereitstellungsplan Ihres Unternehmens.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Onboarding fortsetzen

Nachdem Sie diese Checklisten abgeschlossen haben, haben Sie Ihrer Teams-Bereitstellung erfolgreich Sprachfunktionen hinzugefügt.

Verwenden Sie im nächsten Schritt das Textbuch [für die Website Aktivierung (Textbuch für Sprache)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) , damit Sie Ihre Benutzer auf jeder Website an Bord bringen und sicherstellen können, dass Sie wichtige Website spezifische Aktivitäten planen und ausführen.

-   Bereitstellungs Plan für bereite Website nach Website

-   Einrichten des Dienst Verwaltungsprozesses

-   Testen und Behebung durchführen

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testen von Cloud-sprach Auslastungen in Teams

Nachdem Sie Ihre Teams Cloud Voice Business Success-und Technical implementation-Pläne im Rahmen der enVision-Phase definiert und dokumentiert haben und die gewünschte Konfiguration im Admin Center vorgenommen haben, besteht der nächste Schritt darin, zu überprüfen, ob Ihre Organisation Erwartungen und Anforderungen werden durch Funktion, Funktionalität und Benutzerfreundlichkeit erfüllt. Sie sollten diesen Validierungsschritt durchführen, bevor Sie eine Pilot-oder endgültige Bereitstellung in Ihrer Produktionsumgebung bereitstellen.

Sie können den Geschäftserfolgs Plan, den Sie während der enVision-Phase definiert haben, als Grundlage für die Ermittlung der Aktivitäten, Erwartungen, Funktions-/Funktionstest Fälle und des Gesamtumfangs nutzen, der während der Testphase ausgewertet werden soll.

## <a name="define-your-testing-approach"></a>Definieren des testansatzes

In der einfachsten Form basiert Ihr Testansatz auf der Überprüfung der Funktions Funktionen der Audiokonferenzen, der Anrufpläne oder des direkten Routing Diensts sowie der Entwicklung eines Testplans, um zu überprüfen, ob die Funktionsanforderungen für Benutzer im Bereich erfüllt sind. Im folgenden sehen Sie einen Beispiel Testplan für die Onboard-Phase einer Audiokonferenz-Implementierung.


| Zu prüfendes Audiokonferenz-Feature | Ergebnis Zusammenfassung | Zusätzliche Notizen |
|------------|-----------------|------------------|
| Planen einer Ad-hoc-Teams-Besprechung mit Einwahlinformationen zu Audiokonferenzen | Erfolgreich/fehlerhaft   | TBD |
| Verwenden Sie ein Telefon für die Audioübertragung, indem Sie sich über das PSTN mit den eingegebenen Informationen in eine Besprechung einwählen. | Erfolgreich/fehlerhaft | TBD |
| Teilnehmen an einer vorhandenen Besprechung durch Anrufen über das PSTN | Erfolgreich/fehlerhaft | TBD |



| Anrufpläne oder direktes Routing-Feature zum Testen | Ergebnis Zusammenfassung | Zusätzliche Notizen |
|----------------------------------------------------|-----------------|------------------|
| Tätigen eines PSTN-Anrufs durch Wählen einer PSTN-Nummer       | Erfolgreich/fehlerhaft       | TBD |
| Empfangen eines PSTN-Anrufs, indem Sie Ihre PSTN-Nummer von einer externen Leitung anrufen (Mobil, Festnetztelefon) | Erfolgreich/fehlerhaft | TBD|
| Übertragen eines PSTN-Anrufs von einem Teams-Benutzer zu einem anderen | Erfolgreich/fehlerhaft | TBD |


>[!TIP]
>Wenn Sie die Erstellung von Testfällen als Ausgangspunkt unterstützen möchten, lesen Sie die Liste der Benutzerleitfäden, die in den [Teams-Besprechungen und-anrufen](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)zur Verfügung stehen.

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Einrichten von Cloud-sprach Auslastungen für Teams

Nachdem Sie Ihren Testansatz definiert haben, besteht der nächste Schritt darin, ihre Dienstumgebung und die Benutzer im Bereich für die Cloud-Sprachfeatures von Teams zu konfigurieren.

Weitere Informationen finden Sie unter:

- [Technische Planung für Audiokonferenzen](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [Einrichten von Audiokonferenzen für Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Technische Planung für Telefonsysteme mit Anrufplänen](calling-plan-landing-page.md)

- [Einrichten von Anrufplänen für Skype for Business und Microsoft Teams](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planen von direktem Routing](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [Konfigurieren von direktem Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>Ausführen des Testplans

[//]: # (Bearbeiten OK? "Nutzer" schien mir etwas zweideutig zu sein.)
Nach der Konfiguration der Benutzerumgebung und des Diensts umfasst der letzte Test Schritt die Ausführung des Test Plans mit dem Fokus auf Feature-und Funktionsüberprüfung. 

**Testen der Audiokonferenz-Voraussetzungen und Annahmen für Benutzer und Websites im Bereich:**

-   Die Business Use Case-Definition für den Audiokonferenzdienst wurde abgeschlossen.

-   Die für Audiokonferenzen erforderliche Lizenzierung steht zur Verfügung und wurde zugewiesen.

-   Die Liste der Organisations Websites und Benutzergruppen wurde identifiziert.

-   Die Liste der dedizierten und freigegebenen Audiokonferenz-Einwahlnummern mit Spracheinstellungen wurden identifiziert und konfiguriert.

-   [Guthaben](what-are-communications-credits.md) für Kommunikationen (falls erforderlich) wurden für Ihre Organisation eingerichtet.

-   Die Einstellungen für Audiokonferenz-Konferenz Brücken wurden identifiziert und konfiguriert (PIN-Länge, Benachrichtigungen für ein-und Ausstiege, Aktivierung der Benachrichtigungseinstellung).

-   Mandanten Konferenzrichtlinien und Einstellungen für den Wählplan, die Wähl Szenarien für die Audiokonferenz unterstützen, wurden identifiziert, konfiguriert und angewendet.

-   Compliance-Anforderungen an die Audiokonferenz wurden identifiziert und konfiguriert.

**Anrufpläne Testen von Voraussetzungen und Annahmen für Benutzer und Websites im Bereich:**

-   Die Business Use Case-Definition für den Service für Anrufpläne wurde abgeschlossen.

-   Die für Anrufpläne erforderliche Lizenzierung ist verfügbar und wurde zugewiesen.

-   Die Liste der Organisations Websites und Benutzergruppen wurde identifiziert.

-   Telefonnummern, die Benutzern zugewiesen werden sollen, wurden erworben oder an Microsoft portiert und stehen im mandantenportal zur Verfügung.

-   [Guthaben](what-are-communications-credits.md) für Kommunikationen (falls erforderlich) wurden für Ihre Organisation eingerichtet.

-   Mandanten Benutzerrichtlinien und Einstellungen für den Wählplan, die Szenarien für Anrufpläne unterstützen, wurden identifiziert, konfiguriert und angewendet.

-   Die Compliance-Anforderungen für Anrufpläne wurden identifiziert und konfiguriert.

**Direktes Routing Testen von Voraussetzungen und Annahmen für Benutzer und Websites im Bereich:**

-   Die Geschäfts Anwendungsfall Definition für den Direct Routing-Dienst wurde abgeschlossen.

-   Die für das direkte Routing erforderliche Lizenzierung ist verfügbar und wurde zugewiesen.

-   Die Liste der Organisations Websites und Benutzergruppen wurde identifiziert.

-   Ein [Certified Session Border Controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) wurde bereitgestellt, konfiguriert und mit dem Telefon System gekoppelt.

-   Enterprise-VoIP wurde aktiviert, und die Telefonnummern wurden zugewiesen.

-   VoIP-Routing Richtlinien wurden identifiziert, konfiguriert und zugewiesen.

-   Microsoft Teams wurde als bevorzugter Anruf Client für die Benutzer im Bereich eingerichtet.
 
-   Die Compliance-Anforderungen für Direct Routing wurden identifiziert und konfiguriert.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Funktionen für Audiokonferenz Features bereitgestellt werden (Dienst Entscheidung).</li><li>Ermitteln Sie die Anforderungen der Benutzerfunktionalität für Audiokonferenzen.</li><li>Ermitteln der Dienst Konfigurationsanforderungen für Audiokonferenzen</li><br><li>Entscheiden Sie, ob direkte Routing-oder Anrufpläne bereitgestellt und konfiguriert werden.<li>Entscheiden Sie, welche Funktionen für das Telefon System bereitgestellt werden (Dienst Entscheidung).</li><li>Ermitteln der Benutzer Funktionalitätsanforderungen für Anrufpläne oder direktes Routing</li><li>Ermitteln der Dienst Konfigurationsanforderung für Anrufpläne oder direktes Routing</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Entwickeln und dokumentieren Sie Ihren Testplan-Ansatz.</li><li>Bereiten Sie Ihre Dienstumgebung und die Benutzer im Bereich für Audiokonferenzfunktionen vor.</li><li>Bereiten Sie Ihre Dienstumgebung und die Benutzer im Bereich für Anrufpläne oder direkte Routing Features vor.</li><li>Führen Sie die Testüberprüfung für die Audio-Konferenzfeatures aus, die Sie aktivieren möchten.</li><li>Führen Sie die Testüberprüfung für die Anrufpläne oder direkt Routing Features aus, die Sie aktivieren möchten.</li><li>Überprüfen Sie bei Test Fehlern, ob Ihre Konfiguration richtig ist, lesen Sie Community-Artikel, und führen Sie bei Bedarf einen Supportfall aus.</li></ul></td></tr>
</table>


Weitere detaillierte Anleitungen zum Durchführen von Tests für Audiokonferenzen in Teams finden Sie im [ausführlichen Testhandbuch für Audiokonferenzen](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).

Weitere detaillierte Anleitungen zum Durchführen von Tests für Anrufpläne in Teams finden Sie im [ausführlichen Testhandbuch für das Telefon System](onboarding-test-plan-for-enterprises-Phone-System.md).

<!--ENDOFSECTION-->
