---
title: Vorbereiten der Bereitstellung des Cloud-VoIP-Diensts
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Verwenden Sie Onboarding-Checklisten, um Microsoft 365 oder Office 365 für Teams vorzubereiten und Teams Kernfunktionen, Netzwerk- und Cloud voice-Workloads zu konfigurieren.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a91a57a077db38675a62238289ad2c204040a9cd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675437"
---
# <a name="prepare-my-service"></a>Vorbereiten des Diensts

Dieser Artikel enthält eine Übersicht über die Anforderungen für die Vorbereitung von Cloud-VoIP-Diensten für Ihre Organisation. Durch die ordnungsgemäße Vorbereitung können Sie sicher sein, dass Sie bereit sind, Cloud Voice-Funktionen für Ihre Organisation bereitzustellen.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Onboarding checklists for Microsoft Teams voice workloads

Die folgenden Checklisten führen Sie durch die Schritte zum Implementieren von Audiokonferenz, Telefonsystem mit Anrufplänen ("Anrufpläne") und Telefonsystem Direct Routing("Direct Routing")-Funktionen in Microsoft Teams.

*  [Vorbereiten Microsoft 365 oder Office 365 für Teams](onboarding-checklist-enable-office-365.md)

*  [Konfigurieren Teams Kernfunktionen](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [Vorbereiten des Netzwerks Ihrer Organisation](prepare-network.md)

*  [Konfigurieren von Cloud voice workloads in Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Konfigurieren von Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

Die Aufgaben und Aktivitäten in diesen Checklisten sind die wichtigsten Aufgabenelemente, die für jede Bereitstellung von Cloud-VoIP-Funktionen mit Teams gelten. Sie können die Checklisten so anpassen, dass sie die Aktivitäten und Aufgaben enthalten, die für Ihre eigene Teams Reise spezifisch sind.

>[!NOTE]
>Dieser Leitfaden konzentriert sich ausschließlich auf Anrufpläne, Audiokonferenz und Direct Routing. Wenn Sie mit Teams noch nicht fertig sind, lesen Sie [die Übersicht über Microsoft Teams](teams-overview.md). Für allgemeine Anleitungen zur Planung Ihrer Teams Bereitstellung beginnen [Sie mit "Bereitstellen von Chat", "Teams", "Kanäle" und "Apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md)".

Verwenden Sie die bereitgestellten Checklisten, um den Status jeder einzelnen Aktivität und Aufgabe nachzuverfolgen und sicherzustellen, dass Sie keine kritischen Schritte übersprungen haben. Jede Aktivität enthält eine detaillierte Beschreibung der erforderlichen Aktionen und Verweise auf zusätzliche Informationen, die Sie zum Abschließen dieser Aktivität verwenden können.

Obwohl wir empfehlen, die Prüflisten in der richtigen Reihenfolge zu befolgen, hängt die genaue Reihenfolge vom Umfang Ihrer Bereitstellung und der Konfiguration und Komplexität Ihrer Umgebung ab. Sie sind so organisiert, dass sie entweder eine "grüne Wiese" Teams Bereitstellung (eine ohne vorherige Skype for Business Onlinepräsenz) oder die Migration von Skype for Business Online zu Teams unterstützen. Wenn Sie von Skype for Business Online migrieren, haben Sie möglicherweise bereits einige dieser Aktivitäten abgeschlossen und können sie jetzt ignorieren.

Beim Onboarding von Benutzern pro Website wird dringend empfohlen, das [Playbook für Die Websiteaktivierung für VoIP (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) als zusätzlichen Leitfaden zu diesen Checklisten zu verwenden.

>[!NOTE]
>Die meisten Konfigurationseinstellungen sind zwischen Teams und Skype for Business Online üblich. Sie verwenden das Microsoft 365 Admin Center und Microsoft Teams Admin Center, um diese Einstellungen zu konfigurieren.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Wer ist für die Überwachung des Abschlusses der Onboarding-Checklisten verantwortlich?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Laden Sie die Onboarding-Checklisten herunter.</li><li>Schrittweises Durcharbeiten der Onboarding-Checklistenelemente gemäß dem Bereitstellungsplan Ihrer Organisation.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>Onboarding fortsetzen

Nachdem Sie diese Prüflisten abgeschlossen haben, haben Sie Ihrer Teams Bereitstellung erfolgreich Sprachfunktionen hinzugefügt.

Im nächsten Schritt verwenden Sie das [Playbook für Die Websiteaktivierung für VoIP (Playbook),](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) um Sie beim Onboarding Ihrer Benutzer auf jeder Website zu unterstützen und sicherzustellen, dass Sie wichtige websitespezifische Aktivitäten planen und ausführen.

-   Ready Site by Site Rollout Plan

-   Einrichten des Dienstverwaltungsprozesses

-   Ausführen von Tests und Korrekturen

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Testen von Cloud-VoIP-Workloads in Teams

Nachdem Sie Ihre Teams Cloud Voice Business-Erfolgs- und technische Implementierungspläne im Rahmen der Envision-Phase definiert und dokumentiert haben und die gewünschte Konfiguration im Admin Center durchgeführt haben, besteht der nächste Schritt darin, zu überprüfen, ob die Erwartungen und Anforderungen Ihrer Organisation durch Feature, Funktionalität und Nutzbarkeit erfüllt werden. Führen Sie diesen Überprüfungsschritt aus, bevor Sie ein Pilotprojekt oder eine endgültige Bereitstellung in Ihrer Produktionsumgebung bereitstellen.

Sie können den Geschäftserfolgsplan nutzen, den Sie in der Envisionsphase definiert haben, um als Grundlage für die Bestimmung der Aktivitäten, Erwartungen, Testfälle von Features/Funktionen und des gesamter Umfangs zu dienen, die während der Testphase ausgewertet werden sollen.

## <a name="define-your-testing-approach"></a>Definieren Des Testansatzes

In seiner einfachsten Form basiert Ihr Testansatz darauf, dass Sie die Featurefunktionen der Audiokonferenz, Anrufpläne oder des Direct Routing-Diensts überprüfen und einen Testplan entwickeln, um zu überprüfen, ob Ihre Funktionalitätsanforderungen für Benutzer im Umfang erfüllt sind. Es folgt ein Beispieltestplan für die Onboard-Phase einer Implementierung von Audiokonferenzen.


| Audiokonferenz Zu testungsfeature | Ergebniszusammenfassung | Zusätzliche Hinweise |
|------------|-----------------|------------------|
| Planen einer Ad-hoc-Teams-Besprechung, die Audiokonferenz-Einwahlinformationen enthält | Pass/Fail   | TBD |
| Verwenden eines Telefons für Besprechungsaudio durch Einwählen in eine Besprechung aus dem PSTN mit den bereitgestellten Einwahlinformationen | Pass/Fail | TBD |
| Teilnehmen anderer Personen an einer bestehenden Besprechung durch Ausgehende Anrufe über das PSTN | Pass/Fail | TBD |



| Anrufpläne oder Direct Routing-Feature zum Testen | Ergebniszusammenfassung | Zusätzliche Hinweise |
|----------------------------------------------------|-----------------|------------------|
| Tätigen eines PSTN-Anrufs durch Wählen einer PSTN-Nummer       | Pass/Fail       | TBD |
| Empfangen eines PSTN-Anrufs durch Wählen Ihrer Festnetznummer über eine externe Leitung (Mobil, Festnetz) | Pass/Fail | TBD|
| Übertragen eines PSTN-Anrufs von einem Teams Benutzer zu einem anderen | Pass/Fail | TBD |


>[!TIP]
>Informationen zur Unterstützung bei der Erstellung von Testfällen als Ausgangspunkt finden Sie in der Liste der Benutzerleitfäden, die bei [Teams Besprechungen und Anrufen](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings) zur Verfügung stehen.

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Einrichten von Cloud-VoIP-Workloads für Teams

Nachdem Sie ihren Testansatz definiert haben, besteht der nächste Schritt darin, Ihre Dienstumgebung und Benutzer im Bereich für Teams Cloud Voice-Features zu konfigurieren.

Weitere Informationen finden Sie unter:

- [Technische Planung für Audiokonferenzen](./cloud-voice-landing-page.md)

- [Einrichten von Audiokonferenzen für Microsoft Teams](set-up-audio-conferencing-in-teams.md)

- [Technische Planung für Telefonsystem mit Anrufplänen](calling-plan-landing-page.md)

- [Einrichten von Anrufplänen für Skype for Business und Microsoft Teams](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [Planen von direktem Routing](./direct-routing-plan.md)

- [Konfigurieren von direktem Routing](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>Ausführen des Testplans

[//]: # (Okay bearbeiten? "User" schien mir ein wenig mehrdeutig zu sein.)
Nachdem die Benutzerumgebung und der Dienst konfiguriert wurden, umfasst der letzte Testschritt die Ausführung des Testplans, wobei der Schwerpunkt auf der Überprüfung von Features und Funktionen liegt. 

**Audiokonferenz Testen der Voraussetzungen und Annahmen für Benutzer und Websites im Umfang:**

-   Die Geschäftsanwendungsfalldefinition für den Audiokonferenz Dienst wurde abgeschlossen.

-   Die für Audiokonferenz erforderliche Lizenzierung ist verfügbar und wurde zugewiesen.

-   Die Liste der Organisationswebsites und Benutzergruppen wurde identifiziert.

-   Die Liste der dedizierten und freigegebenen Audiokonferenz-Einwahlnummern mit Spracheinstellungen wurde identifiziert und konfiguriert.

-   [Kommunikationsguthaben](what-are-communications-credits.md) (falls erforderlich) wurde für Ihre Organisation eingerichtet.

-   Audiokonferenz Einstellungen für Konferenzbrücken wurden identifiziert und konfiguriert (PIN-Länge, Ein-/Ausstiegsbenachrichtigungen, Einstellung für Aktivierungsbenachrichtigungen).

-   Mandantenkonferenzrichtlinien und Einstellungen für Wählpläne, die Audiokonferenz Auswahlszenarien unterstützen, wurden identifiziert, konfiguriert und angewendet.

-   Audiokonferenz Complianceanforderungen wurden identifiziert und konfiguriert.

**Anrufpläne testen die Voraussetzungen und Annahmen für Benutzer und Websites im Umfang:**

-   Die Geschäftsanwendungsfalldefinition für den Anrufplandienst wurde abgeschlossen.

-   Die für Anrufpläne erforderliche Lizenzierung ist verfügbar und wurde zugewiesen.

-   Die Liste der Organisationswebsites und Benutzergruppen wurde identifiziert.

-   Telefon Nummern, die Benutzern zugewiesen werden sollen, wurden erworben oder zu Microsoft portiert und sind im Mandantenportal verfügbar.

-   [Kommunikationsguthaben](what-are-communications-credits.md) (falls erforderlich) wurde für Ihre Organisation eingerichtet.

-   Mandantenbenutzerrichtlinien und Wählplaneinstellungen, die Anrufpläne unterstützen, wurden identifiziert, konfiguriert und angewendet.

-   Die Complianceanforderungen für Anrufpläne wurden identifiziert und konfiguriert.

**Voraussetzungen und Annahmen für Direct Routing für Benutzer und Websites im Umfang:**

-   Die Geschäftsanwendungsfalldefinition für den Direct Routing-Dienst wurde abgeschlossen.

-   Die für Direct Routing erforderliche Lizenzierung ist verfügbar und wurde zugewiesen.

-   Die Liste der Organisationswebsites und Benutzergruppen wurde identifiziert.

-   Ein [zertifizierter Session Border Controller (SBC)](./direct-routing-plan.md#supported-session-border-controllers-sbcs) wurde bereitgestellt, konfiguriert und mit Telefonsystem gekoppelt.

-   Enterprise Wurde aktiviert, und die Telefonnummern wurden zugewiesen.

-   VoIP-Routingrichtlinien wurden identifiziert, konfiguriert und zugewiesen.

-   Microsoft Teams wurde als bevorzugter Anrufclient für die Benutzer im Bereich festgelegt.
 
-   Die Complianceanforderungen für direct Routing wurden identifiziert und konfiguriert.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Entscheidungspunkte</td><td><ul><li>Entscheiden Sie, welche Audiokonferenz Featurefunktionen bereitgestellt werden sollen (Dienstentscheidung).</li><li>Identifizieren sie die Anforderungen an die Benutzerfunktionalität für Audiokonferenz.</li><li>Ermitteln der Dienstkonfigurationsanforderungen für Audiokonferenz.</li><br><li>Entscheiden Sie, ob Direct Routing- oder Anrufpläne bereitgestellt und konfiguriert werden.<li>Entscheiden Sie, welche Telefonsystem Featurefunktionen bereitgestellt werden sollen (Dienstentscheidung).</li><li>Identifizieren Sie die Anforderungen an die Benutzerfunktionalität für Anrufpläne oder Direct Routing.</li><li>Ermitteln der Dienstkonfigurationsanforderung für Anrufpläne oder Direct Routing.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Nächste Schritte</td><td><ul><li>Entwickeln und dokumentieren Sie Ihren Testplanansatz.</li><li>Bereiten Sie Ihre Dienstumgebung und Die Benutzer im Bereich für Audiokonferenz Features vor.</li><li>Bereiten Sie Ihre Dienstumgebung und Benutzer im Bereich für Anrufpläne oder Direct Routing-Features vor.</li><li>Führen Sie die Testüberprüfung für die Audiokonferenz Features aus, die Sie aktivieren möchten.</li><li>Führen Sie die Testüberprüfung für die Anrufpläne oder Direct Routing-Features aus, die Sie aktivieren möchten.</li><li>Überprüfen Sie bei Allen Testfehlern, ob Ihre Konfiguration korrekt ist, lesen Sie Communityartikel, und lösen Sie – falls erforderlich – einen Supportfall aus.</li></ul></td></tr>
</table>


Weitere detaillierte Anleitungen zum Durchführen von Tests für Audiokonferenz in Teams finden Sie im [ausführlichen Testhandbuch für Audiokonferenz](./deploy-audio-conferencing-teams-landing-page.md).

Weitere detaillierte Anleitungen zum Durchführen von Tests für Anrufpläne in Teams finden Sie im [detaillierten Testhandbuch für Telefonsystem](./cloud-voice-landing-page.md).

<!--ENDOFSECTION-->