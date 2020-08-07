---
title: Konfigurieren von Audiokonferenzeinstellungen – Microsoft Teams
ms.reviewer: ''
description: Verwenden Sie diese Bereitstellungsressourcen zur Unterstützung bei der Bereitstellung von Audiokonferenzen als Bestandteil der Besprechungsarbeitslast in Microsoft Teams.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom: seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c8a23faff819f24330b6ab70716dad2afc4cbbd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583994"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>Erfahren Sie, wie Sie Audiokonferenzen in Microsoft Teams bereitstellen

Durch Audiokonferenz ist es möglich, mit einem normalen Telefon an einer Teams-Besprechung teilzunehmen und in einer Besprechung eine Telefonnummer anzurufen. Lesen Sie [Bereitstellen von Besprechungen](deploy-meetings-microsoft-teams-landing-page.md), wenn Sie Audiokonferenzen in Ihrer Organisation bereitstellen möchten.

## <a name="audio-conferencing-deployment-decisions"></a>Bereitstellungsentscheidungen für Audiokonferenzen

Dieser Artikel hilft Ihnen bei der Entscheidung, ob einige der Standardeinstellungen für Audiokonferenzen geändert werden sollen, berücksichtigt dazu das Profil und die geschäftlichen Anforderungen Ihrer Organisation und führt Sie dann schrittweise durch die einzelnen Änderungen. Wir haben die Einstellungen in zwei Gruppen aufgeteilt und beginnen mit der Kernmenge der [Änderungen, die Sie mit größerer Wahrscheinlichkeit vornehmen](#core-deployment-decisions) werden. Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), deren Konfiguration, abhängig von den Bedürfnissen Ihrer Organisation, sinnvoll sein kann.

Sie müssen Audiokonferenzen nur für Personen einrichten, die Besprechungen planen oder leiten möchten. Besprechungsteilnehmer, die sich einwählen, benötigen keine ihnen zugewiesenen Lizenzen oder andere Einstellungen. Die telefonische Einwahl in Besprechungen ist sehr praktisch für Benutzer, die unterwegs sind und nicht über die Skype for Business- oder Teams-App auf ihrem Laptop oder auf Mobilgeräten an einer Besprechung teilnehmen können. 


## <a name="audio-conferencing-prerequisites"></a>Voraussetzungen für Audiokonferenzen 

Bevor Sie Audiokonferenzen für Teams bereitstellen können, beachten Sie Folgendes:

|Frage|Aktion |
|------------|-------|
|Sind Audiokonferenzen für mein Land/meine Region verfügbar?|Informationen darüber, ob Audiokonferenzen für Ihr Land/Ihre Region verfügbar sind, finden Sie unter [Verfügbarkeit von Ländern und Regionen für Audiokonferenzen und Anrufpläne](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).|
|Besitzen meine Benutzer die entsprechenden Lizenzen für Teams-Audiokonferenzen?|Die Audiokonferenzlizenzen sind im Rahmen eines Microsoft 365- oder Office 365 E5-Abonnements oder als Add-On-Service für ein Office 365 Business Premium-, E1- oder E3-Abonnement verfügbar. <ul><li>Informationen zum Abrufen und Zuweisen von Lizenzen finden Sie unter [Testen oder Kaufen von Audiokonferenz in Microsoft 365 oder Office 365](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) und [Zuweisen oder Entfernen von Lizenzen für Microsoft 365 Apps for Business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</li><li> Weitere Informationen finden Sie unter [Lizenzierung für Microsoft Teams-Add-On](teams-add-on-licensing/microsoft-teams-add-on-licensing.md). </li><li>Welche Cloudfeatures in den einzelnen Plänen enthalten sind, erfahren Sie in den Artikeln [Lizenzoptionen auf Grundlage Ihres Plans](teams-add-on-licensing/office-365-business-premium.md).</li></ul>|
|Muss ich Guthaben für Kommunikationen für Benutzer erwerben, denen eine Lizenz für Audiokonferenzen zugewiesen wurde?|Lesen Sie weiter unter [Was ist Guthaben für Kommunikationen?](what-are-communications-credits.md), und sehen Sie sich anschließend den Abschnitt [Guthaben für Kommunikationen](#communications-credits) weiter unten an.|
|||


## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Nachdem Sie die Voraussetzungen für Audiokonferenzen erfüllt haben, führen Sie die folgenden Schritte aus, um Audiokonferenzen für Ihre Benutzer zu konfigurieren.


### <a name="teams-administrators"></a>Teamadministratoren

Teams bietet eine Reihe benutzerdefinierter Administratorrollen, die zum Verwalten von Teams für Ihre Organisation verwendet werden können. Die Rollen stellen Administratoren verschiedene Funktionen zur Verfügung. 

| Frage | Aktion |
|--------------|--------|
|Wem wird die Rolle des Teams-Kommunikationsadministrators zugewiesen?|Weitere Informationen zu den Administratorrollen in Teams finden Sie unter [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md).|
|Wem wird die Rolle des Teams-Kommunikationssupporttechnikers zugewiesen?|Informationen zum Zuweisen von Administratorrollen finden Sie unter [Zuweisen von Administrator- und anderen Rollen zu Benutzern mithilfe von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|Wem wird die Rolle des Teams-Kommunikationssupportexperten zugewiesen?||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>Konferenzbrücken und Telefonnummern

Über Konferenzbrücken können sich Benutzer per Telefon in Besprechungen einwählen. Sie können die Standardeinstellungen für eine Konferenzbrücke verwenden oder die Telefonnummern (gebührenpflichtig und gebührenfrei) und andere Einstellungen ändern, z. B. die PIN oder die verwendeten Sprachen.

Weitere Informationen finden Sie unter [Audiokonferenzen](audio-conferencing-in-office-365.md).

|Frage|Aktion |
|------------|-------|
|Muss ich neue Konferenzbrückennummern hinzufügen?| Informationen zum Hinzufügen neuer Nummern finden Sie unter [Abrufen von Service-Telefonnummern](/microsoftteams/getting-service-phone-numbers).|
|Muss ich die Brückeneinstellungen ändern?|Informationen zum Ändern der Brückeneinstellungen finden Sie unter [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).|
|Muss ich Nummern für den Gebrauch mit Audiokonferenzen übertragen?|Weitere Informationen zum Übertragen von Telefonnummern finden Sie unter [Übertragen von Telefonnummern zu Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).|
|||


### <a name="default-and-alternate-languages"></a>Standard- und alternative Sprachen

In Teams-Audiokonferenzen können Sie standardmäßige und alternative Sprachen für eine Konferenzbrücke einrichten.

|Frage|Aktion |
|------------|-------|
| Welche Sprachen sollte ich für die Begrüßung der automatischen Telefonzentrale auswählen? | Informationen zur Auswahl von Sprachen finden Sie unter [Festlegen der Sprachen für die automatische Telefonzentrale für Audiokonferenzen](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="conferencing-bridge-settings"></a>Einstellungen für die Konferenzbrücke 

Nachdem Sie Ihre Konferenzbrücke einschließlich der Standard- und alternativen Sprachen eingerichtet haben, sollten Sie sich vergewissern, dass die Standardeinstellungen, wie z. B. Ein-/Ausgangsbenachrichtigungen und PIN-Länge, die sind, die Sie verwenden möchten. Wenn dies nicht zutrifft, können Sie sie ändern. 

|Frage|Aktion |
|------------|-------|
| Hören Teilnehmer eine Benachrichtigung, wenn ein Benutzer einer Besprechung beitritt oder diese verlässt? | Informationen zum Ändern dieser Einstellungen finden Sie unter [Ändern der Einstellungen für eine Audiokonferenzbrücke](change-the-settings-for-an-audio-conferencing-bridge.md).|
|Was ist die erforderliche Länge der PIN, die ein Besprechungsorganisator verwendet, um die Besprechung zu beginnen?||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>Einwahlnummerneinstellungen für Benutzer, die Besprechungen leiten

Nachdem Sie Ihre Audiokonferenzbrücke erstellt haben, müssen Sie die gebührenpflichtigen und/oder gebührenfreien Nummern festlegen, die Benutzer, die Besprechungen leiten, verwenden.

|Frage|Aktion |
|------------|-------|
| Welche Konferenzbrückennummern weise ich den jeweiligen Benutzern zu, die Besprechungen leiten? | Weitere Informationen zum Zuweisen einer Einwahltelefonnummer zu einem Benutzer finden Sie unter [Schritt 7: Zuweisen von Einwahlnummern zu Benutzern, die Besprechungen leiten](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings). |
|||

### <a name="communications-credits"></a>Guthaben für Kommunikationen

Um gebührenfreie Telefonnummern für Konferenzbrücken zur Verfügung zu stellen und ausgehende Konferenzanrufe für internationale Telefonnummern zu unterstützen, müssen Sie Kommunikationsguthaben für Ihre Organisation einrichten. Weitere Informationen zu Guthaben für Kommunikationen finden Sie unter [Was ist Guthaben für Kommunikationen?](what-are-communications-credits.md).

|Frage|Aktion |
|------------|-------|
|Ist Guthaben für Kommunikationen für meine Audiokonferenz-Implementierung erforderlich? |Um zu erfahren, ob Sie Guthaben für Kommunikationen einrichten müssen, lesen Sie [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](set-up-communications-credits-for-your-organization.md).|
|Wenn Guthaben erforderlich ist, wie viel soll ich erwerben?|Wenn Sie bestimmen möchten, wie viel Guthaben für Kommunikationen Sie benötigen, lesen Sie [Empfohlene Einzahlungsbeträge](what-are-communications-credits.md#recommended-funding-amounts).|
|Soll ich einen Betrag für das automatische Aufladen konfigurieren?|Informationen zum Konfigurieren eines Betrags für das automatische Aufladen finden Sie unter [Einrichten von Guthaben für Kommunikationen für Ihr Unternehmen](set-up-communications-credits-for-your-organization.md).|
|||



## <a name="additional-deployment-decisions"></a>Zusätzliche Bereitstellungsentscheidungen

Je nach den Bedürfnissen und der Konfiguration Ihrer Organisation kann es sinnvoll sein, diese Einstellungen zu ändern.

### <a name="outbound-calling-restriction-policies"></a>Einschränkungsrichtlinien für ausgehende Anrufe 

Als Administrator können Sie die Steuerelemente für ausgehende Anrufe verwenden, um den Typ der Audiokonferenzen und Endbenutzer-PSTN-Anrufe einzuschränken, die von Benutzern in Ihrer Organisation verwendet werden können.

|Frage|Aktion |
|------------|-------|
| Soll ich den Typ der erlaubten ausgehenden Anrufe einschränken? | Informationen zum Einschränken ausgehender Anrufe finden Sie unter [Einschränkungsrichtlinien für ausgehende Anrufe für Audiokonferenzen und PSTN-Anrufe](outbound-calling-restriction-policies.md).|
|||


### <a name="dial-plans"></a>Wählpläne

Ein Wählplan (ein Bestandteil des Telefonsystems von Microsoft 365 oder Office 365) ist eine Gruppe von Normalisierungsregeln, die gewählte Telefonnummern in ein alternatives Format (normalerweise das Format E.164) übersetzt, um Anrufe zu autorisieren und weiterzuleiten.

Weitere Informationen zu Wählplänen finden Sie unter [Was sind Wählpläne?](what-are-dial-plans.md).

|Frage|Aktion |
|------------|-------|
|Benötigt meine Organisation einen angepassten Wählplan?|Um zu ermitteln, ob Sie einen angepassten Wählplan benötigen, sehen Sie sich den Abschnitt [Planen eines Mandantenwählplans](what-are-dial-plans.md#planning-for-tenant-dial-plans) an. |
|Welche Benutzer benötigen einen angepassten Wählplan und welcher Mandantenwählplan sollte jedem Benutzer zugewiesen werden?|Wenn Sie Benutzer mithilfe von PowerShell zu einem benutzerdefinierten Wählplan hinzufügen möchten, lesen Sie den Abschnitt [Erstellen und Verwalten von Wahlplänen](create-and-manage-dial-plans.md).|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Behandeln von Problemen mit der Besprechungs- und Anrufqualität 

Sie haben in Teams zwei Möglichkeiten, Probleme mit der Anrufqualität zu überwachen und zu behandeln: [Anrufanalyse und das Anrufqualitätsdashboard](monitor-call-quality-qos.md). Die Anrufanalyse zeigt detaillierte Informationen zu den Geräten und Netzwerken sowie zur Konnektivität im Zusammenhang mit bestimmten Anrufen und Besprechungen für die einzelnen Benutzer. Die Anrufanalyse ist dazu gedacht, Administratoren und Helpdesk-Agents bei der Behandlung von Problemen mit der Anrufqualität bei bestimmten Anrufen zu unterstützen, während das Anrufqualitätsdashboard Administratoren und Netzwerktechnikern beim Optimieren von Netzwerken hilft. Das Anrufqualitätsdashboard stellt nicht bestimmte Benutzer, sondern aggregierte Informationen für die gesamte Teams-Organisation in den Mittelpunkt. 

|Frage|Aktion |
|------------|-------|
| Wer ist für die Überwachung und Behandlung von Problemen bei Aufrufqualitätsproblemen zuständig? | Weitere Informationen zu den Berechtigungsstufen, die zur Behandlung von Anrufqualitätsproblemen erforderlich sind, finden Sie unter [Verwenden Sie Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md).|
|||


## <a name="next-steps"></a>Nächste Schritte
- [Fördern der Einführung](adopt-microsoft-teams-landing-page.md) der Audiokonferenz in Ihrer Organisation
- [Bereitstellen von Cloud Voice](cloud-voice-landing-page.md)
- Nehmen Sie die vorgeschlagenen Apps – wie etwa Planner – in Ihre erstmalige Teams-Bereitstellung auf. Fügen Sie mit fortschreitender Aneignung von Teams weitere [Apps, Bots und Connectors](deploy-apps-microsoft-teams-landing-page.md) hinzu.
