---
title: Besprechungen und Konferenzen in Microsoft Teams
ms.reviewer: ''
description: Verwenden Sie diese Bereitstellungsressourcen zur Unterstützung Ihrer Bereitstellung von Besprechungen und Audiokonferenzen in Microsoft Teams.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
- m365initiative-meetings
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c6019c72d54ad48406060178389a66f8cdd9cee7
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030801"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a>Besprechungen und Konferenzen in Microsoft Teams

> [!NOTE]
> - Eine Übersicht über den Umstieg auf Remote Learning und Ressourcen für das Fernstudium, die Ihnen bei den ersten Schritten helfen, finden Sie auf der [**Startseite für Remote Learning und Fernunterricht**](https://www.microsoft.com/education/remote-learning).
> - Ressourcen zur Unterstützung von Lehrkräften und Schülern/Studenten beim Remote Learning finden Sie unter [**Fernstudium (Lehren und Lernen) in Office 365 Education**](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4).


Sie haben [Erste Schritte](get-started-with-teams-quick-start.md) abgeschlossen. Sie haben Teams mit [Chat, Teams, Kanälen und Apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in Ihrer Organisation bereitgestellt. Jetzt können Sie die Besprechungsarbeitslast hinzufügen, einschließlich [Audiokonferenzen](deploy-audio-conferencing-teams-landing-page.md), Video und Freigabe. In diesem Artikel werden Sie durch die Einführung von Besprechungen und Audiokonferenzen geführt. Schauen Sie sich als erstes unser Video zu Teams-Besprechungen, -Konferenzen und -Geräten an (3:28 Minuten):

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE46ZdQ]

Wenn Sie mehr über die Besprechungsumgebung für Ihre Benutzer erfahren möchten, lesen Sie [Besprechungen und Anrufe](https://support.office.com/article/meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8). 


*Neu im April 2020*: Besprechungsorganisatoren können eine Besprechung für alle Besprechungsteilnehmer in Teams beenden, indem Sie in der Besprechung in den Besprechungssteuerelementen auf **Besprechung beenden** klicken.  

*Neu im November 2019*: Sie können nun [den Ratgeber für Teams (Vorschau) als Hilfe beim Rollout von Microsoft Teams verwenden](use-advisor-teams-roll-out.md). Der Ratgeber für Teams (Vorschau) führt Sie durch Ihre Einführung von Teams, einschließlich der Besprechungen und Konferenzen. Er analysiert Ihre Office 365-Umgebung und identifiziert die am häufigsten verwendeten Konfigurationen, die Sie möglicherweise aktualisieren oder ändern müssen, bevor Sie den Rollout von Besprechungen und Konferenzen in Teams erfolgreich durchführen können.

 > [!Note]
> Mehr über Teams-Besprechungen und Konferenzen auf verschiedenen Plattformen erfahren Sie unter [Teams-Funktionen nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="meetings-and-conferencing-deployment-decisions"></a>Bereitstellungsentscheidungen für Besprechungen und Konferenzen

Teams bietet ohne weitere Konfiguration eine hervorragende Erfahrung, und die meisten Organisationen stellen fest, dass die Standardeinstellungen für sie sinnvoll sind. Dieser Artikel hilft Ihnen bei der Entscheidung, ob einige der Standardeinstellungen geändert werden sollen, berücksichtigt dazu das Profil und die geschäftlichen Anforderungen Ihrer Organisation und führt Sie dann schrittweise durch die einzelnen Änderungen. Wir haben die Einstellungen in zwei Gruppen aufgeteilt und beginnen mit der Kernmenge der [Änderungen, die Sie mit größerer Wahrscheinlichkeit vornehmen](#core-deployment-decisions) werden. Die zweite Gruppe umfasst die [zusätzlichen Einstellungen](#additional-deployment-decisions), deren Konfiguration, abhängig von den Bedürfnissen Ihrer Organisation, sinnvoll sein kann.

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über Besprechungen zu erfahren: [Einführung in Besprechungen in Microsoft Teams für IT-Experten](https://aka.ms/teams-meetings-intro)


## <a name="meetings-and-conferencing-prerequisites"></a>Voraussetzungen für Besprechungen und Konferenzen 

Bevor Sie Ihre Besprechungsumgebung für Ihre gesamte Organisation skalieren, sollten Sie sich die Zeit nehmen, zu überprüfen und zu bestätigen, dass Ihre Umgebung dafür bereit ist, Benutzern eine bestmögliche Erfahrung zu bieten. Lesen Sie die folgenden Informationen durch, und nehmen Sie alle erforderlichen Änderungen an Ihrer Umgebung vor.

Um das beste Teams-Erlebnis zu bieten, müssen in Ihrer Organisation Exchange Online und SharePoint Online bereitgestellt sein, und Sie müssen über eine bestätigte Domäne für Office 365 verfügen, wie z. B. *contoso.com*.

Zum Skalieren von Besprechungen in Ihrer Organisation sollten Sie sicherstellen, dass alle Benutzerstandorte Zugriff auf das Internet besitzen, damit eine Verbindung zu den Office 365-Diensten hergestellt werden kann. Stellen Sie als Mindestanforderung sicher, dass die folgenden allgemeinen Ports von allen Benutzerstandorten aus zum Internet geöffnet sind:

- TCP-Ports 80 und 443 für ausgehende Verbindungen von Clients, die Teams verwenden sollen
- UDP-Ports 3478 bis 3481 für ausgehende Verbindungen von Clients, die Teams verwenden sollen

| Frage | Aktion |
|--------------|--------|
|Ist mein Netzwerk bereit für eine Teams-Besprechungsumgebung? | Die erforderlichen Schritte, um sicherzustellen, dass Ihr Netzwerk bereit ist, finden Sie unter:<ul><li>[Vorbereiten des Netzwerks Ihrer Organisation für Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</li><li>[URLs und IP-Adressbereiche](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a>Zentrale Entscheidungen bei der Bereitstellung

Dies sind die Einstellungen, deren Änderung in den meisten Organisationen sinnvoll ist (wenn die Standardeinstellungen von Teams sich nicht für die Organisation eignen).

### <a name="teams-administrators"></a>Teamadministratoren

Teams bietet eine Reihe benutzerdefinierter Administratorrollen, die zum Verwalten von Teams für Ihre Organisation verwendet werden können. Die Rollen stellen Administratoren verschiedene Funktionen zur Verfügung. 

| Frage | Aktion |
|--------------|--------|
|Wem wird die Rolle des Teams-Kommunikationsadministrators zugewiesen?|Weitere Informationen zu den Administratorrollen in Teams finden Sie unter [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md).|
|Wem wird die Rolle des Teams-Kommunikationssupporttechnikers zugewiesen?|Informationen zum Zuweisen von Administratorrollen finden Sie unter [Zuweisen von Administrator- und anderen Rollen zu Benutzern mithilfe von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal).|
|Wem wird die Rolle des Teams-Kommunikationssupportexperten zugewiesen?||
|||

### <a name="meetings-settings"></a>Besprechungseinstellungen 

Besprechungseinstellungen werden verwendet, um zu steuern, ob anonyme Benutzer an Teams-Besprechungen teilnehmen und Besprechungsanfragen einrichten können. Wenn Sie Quality of Service (QoS) aktivieren möchten, legen Sie die Ports für den Datenverkehr in Echtzeit fest. Diese Einstellungen werden für alle Teams-Besprechungen verwendet, die Benutzer in Ihrer Organisation planen. 

| Frage | Aktion |
|--------------|--------|
|Kann ich die ursprünglichen Besprechungseinstellungen anpassen? |Im [Lernprogramm Besprechungen in Teams](tutorial-meetings-in-teams.yml) erfahren Sie mehr über Besprechungseinstellungen.|
|Werde ich QoS implementieren?|Unter [Quality of Service in Microsoft Teams](qos-in-teams.md) finden Sie weitere Informationen zu Konzepten, zu Szenarien und zur Implementierung von QoS.|
|||

### <a name="meeting-policies"></a>Besprechungsrichtlinien

Besprechungsrichtlinien werden verwendet, um zu steuern, welche Features für Benutzer verfügbar sind, wenn sie an Teams-Besprechungen teilnehmen. Sie können die Standardrichtlinie verwenden oder eine oder mehrere benutzerdefinierte Besprechungsrichtlinien für Benutzer erstellen, die in Ihrer Organisation Besprechungen hosten. Weitere Informationen hierzu finden Sie im [Lernprogramm Besprechungen in Microsoft Teams](tutorial-meetings-in-teams.yml).

| Frage | Aktion |
|--------------|--------|
|<ul><li>Soll ich die ursprünglichen Besprechungsrichtlinien anpassen?</li><li>Benötige ich mehrere Besprechungsrichtlinien?</li><li>Wie bestimme ich, für welche Benutzergruppen welche Besprechungsrichtlinien gelten?</li></ul>|<br>Lesen Sie [Verwalten von Besprechungsrichtlinien in Teams](meeting-policies-in-teams.md).|
|||

### <a name="audio-conferencing"></a>Audiokonferenzen

Audiokonferenz bietet Organisationen zusätzliche Einstiegspunkte für jede Besprechung (Ad-hoc- oder geplante Besprechungen), indem es Besprechungsteilnehmern gestattet wird, sich über das Telefonfestnetz (PSTN) einzuwählen – über ein herkömmliches Festnetztelefon, eine Nebenstellenanlage (Private Branch Exchange, PBX) oder ein Mobiltelefon. 

Wenn Sie bereit sind, Audiokonferenzen bereitzustellen, sehen Sie sich die Anleitung [Bereitstellen von Audiokonferenzen](deploy-audio-conferencing-teams-landing-page.md) an.

### <a name="meeting-room-and-personal-devices"></a>Besprechungsraum- und private Geräte

Sie sollten die Verwendung von Teams-Geräten wie Raumsystemen, Telefonen, Headsets und Kameras in Betracht ziehen, um ein optimales Besprechungserlebnis zu gewährleisten. Weitere Informationen hierzu finden Sie unter [Teams-Geräte für die intelligente Kommunikation](https://products.office.com/microsoft-teams/across-devices).

| Frage | Aktion |
|--------------|--------|
|Werde ich private Geräte für meine Benutzer erwerben? |Lesen Sie [Verwalten Ihrer Geräte in Teams](devices/device-management.md). |
|Soll ich Raumsystemgeräte für meine Konferenzräume kaufen und bereitstellen?|Lesen Sie [Besprechungsraumgeräte und Lösungen](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).|
|||

### <a name="reporting"></a>Berichterstellung

Verwenden Sie Aktivitätsberichte, um zu erfahren, wie Benutzer in Ihrer Organisation Teams verwenden. Wenn einige beispielsweise Teams noch nicht verwenden, wissen sie vielleicht nicht, wie sie den Einstieg finden sollen oder verstehen nicht, wie sie Teams zur Steigerung ihrer Produktivität und Verbesserung der Zusammenarbeit nutzen können. Ihre Organisation kann mithilfe der Aktivitätsberichte entscheiden, wo Schulungs- und Kommunikationsinitiativen priorisiert ansetzen sollen. 


| Frage | Aktion |
|--------------|--------|
|Wer soll für die Berichterstellung zuständig sein?|Lesen Sie [Verwenden von Aktivitätsberichten für Teams](teams-activity-reports.md).  |
|Wer soll für die Nutzungsüberwachung zuständig sein?|Lesen Sie [Überwachen von Nutzung und Feedback in Teams](get-started-with-teams-monitor-usage-and-feedback.md).|
|||

## <a name="additional-deployment-decisions"></a>Zusätzliche Bereitstellungsentscheidungen

Je nach den Bedürfnissen und der Konfiguration Ihrer Organisation kann es sinnvoll sein, diese Einstellungen zu ändern.

### <a name="bandwidth-planning"></a>Bandbreitenplanung 

Mit der Bandbreitenplanung kann Ihre Organisationen die Bandbreite schätzen, die erforderlich ist, um Besprechungen in Weitverkehrsnetzen und Internetlinks zu unterstützen, damit bestätigt werden kann, dass das Netzwerk ordnungsgemäß bereitgestellt wurde, um einen skalierten Besprechungsdienst zu unterstützen. 

| Frage | Aktion |
|--------------|--------|
| Muss ich die Bandbreitenplanung vor und während der Bereitstellung meiner Besprechungen durchführen? |Weitere Informationen und Links zu Tools, mit denen Sie die Planungsphase vereinfachen können, finden Sie unter [Netzwerkbereitschaft](3-envision-evaluate-my-environment.md#network-readiness).|
|||

### <a name="meeting-recording-and-archiving"></a>Aufzeichnen und Archivieren von Besprechungen

Benutzer können ihre Besprechungen und Gruppenanrufe aufzeichnen, um Aktivitäten der Audio-, Video- und Bildschirmfreigabe festzuhalten. Es gibt auch eine Option für die automatische Transkription von Aufzeichnungen, sodass Benutzer Besprechungsaufzeichnungen mit Untertiteln wiedergeben und nach wichtigen Diskussionsbeiträgen in der Transkription suchen können. Die Aufzeichnung erfolgt in der Cloud und wird im Microsoft Stream gespeichert, sodass Benutzer sie sicher in ihrer Organisation freigeben können. Um die Aufzeichnung für eine Besprechung zu finden, wechseln Sie zur Besprechungsunterhaltung.

>[!Note]
> Der Wechsel von Microsoft Stream zu [OneDrive for Business und SharePoint für Besprechungsaufzeichnungen](tmr-meeting-recording-change.md) erfolgt schrittweise. Beim Start können Sie sich für diese Umgebung entscheiden. Sie müssen sich im November abmelden, wenn Sie Stream weiterhin verwenden möchten. Anfang 2021 müssen alle Kunden OneDrive for Business und SharePoint für neue Besprechungsaufzeichungen verwenden.

Weitere Informationen finden Sie unter [Aufzeichnung einer Teams-Cloudbesprechung](cloud-recording.md).

| Frage | Aktion |
|--------------|--------|
| Soll ich den Transkriptionsdienst für Besprechungen einschalten?|Lesen Sie [Aktivieren oder Deaktivieren der Aufzeichnungstranskription](cloud-recording.md#turn-on-or-turn-off-recording-transcription).|
|||


### <a name="live-events-policies"></a>Richtlinien für Live-Ereignisse

Die Richtlinien für Live-Ereignisse von Teams werden verwendet, um Ereigniseinstellungen für Benutzergruppen zu verwalten. Sie können die Standardrichtlinie verwenden oder weitere Richtlinien erstellen, die Benutzern zugewiesen werden können, die Live-Ereignisse in Ihrer Organisation abhalten. 

| Frage | Aktion |
|--------------|--------|
| Wird meine Organisation Live-Ereignisse von Teams verwenden?| Weitere Informationen über die Planung, Einrichtung und Konfiguration von Live-Ereignissen in Teams finden Sie in den [Artikeln zu Live-Ereignissen](teams-live-events/what-are-teams-live-events.md).|
|||

### <a name="conference-room-systems-rollout"></a>Bereitstellung von Konferenzraumsystemen

Organisationen mit vielen Konferenzräumen sollten einen strukturierten Ansatz für die Bestandsaufnahme Ihrer Räume, Identifizierung der entsprechenden Geräte und deren Bereitstellung in Betracht ziehen. 



| Frage | Aktion |
|--------------|--------|
| Was muss ich tun, um Konferenzraumsysteme bereitzustellen?|Sehen Sie sich die Artikel [Planen von Microsoft Teams-Räumen](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) an.|
|||

### <a name="cloud-video-interop"></a>Cloud-Video-Interoperabilität

Mit der Cloud-Video-Interoperabilität ist es möglich, dass Besprechungsraumgeräte von Drittanbietern an Teams-Besprechungen teilnehmen. 

Video-Telekonferenzen mit einer Zusammenarbeit an Inhalten ermöglichen eine Optimierung von Besprechungen. Aktualisierungen von Konferenzraumsystemen und -geräten sind jedoch teuer. Die Cloud-Video-Interoperabilität für Teams arbeitet mit Drittanbieter-Systemen und bietet eine native Besprechungsfunktion für alle Teilnehmer – in Besprechungsräumen oder innerhalb von Teams-Clients. 

| Frage | Aktion |
|--------------|--------|
| Soll ich eine Cloud-Video-Interoperabilitätslösung innerhalb meiner Raumsystemebereitstellung verwenden? | Lesen Sie [Cloud-Video-Interoperabilität für Teams](cloud-video-interop.md).|
|||


### <a name="personal-device-rollout"></a>Bereitstellen von persönlichen Geräten

Wenn Sie eine umfangreichere Bereitstellung persönlicher Geräte zur Unterstützung von Besprechungen oder Sprachbereitstellungen planen, sollten Sie eine wiederholbare Bereitstellung in Betracht ziehen, die Standort für Standort erfolgt und eine reproduzierbare Qualität ermöglicht.

| Frage | Aktion |
|--------------|--------|
|Soll ich Besprechungen Standort für Standort bereitstellen? |  Das [Playbook für Teams zur Standort-Aktivierung](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads) bietet eine gute Grundlage, die Sie für Ihre eigenen Bereitstellungen verwenden können. Das Handbuch konzentriert sich auf die Sprache, aber die allgemeinen Grundsätze der Gerätelieferung, Kontobereitschaft, Einführung und Schulung gelten auch für eine umfangreiche Besprechungsbereitstellung. |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>Behandeln von Problemen mit der Besprechungs- und Anrufqualität 

Sie haben in Teams zwei Möglichkeiten, Probleme mit der Anrufqualität zu überwachen und zu behandeln: [Anrufanalyse und das Anrufqualitätsdashboard](monitor-call-quality-qos.md). Die Anrufanalyse zeigt detaillierte Informationen zu den Geräten und Netzwerken sowie zur Konnektivität im Zusammenhang mit bestimmten Anrufen und Besprechungen für die einzelnen Benutzer. Die Anrufanalyse ist dazu gedacht, Administratoren und Helpdesk-Agents bei der Behandlung von Problemen mit der Anrufqualität bei bestimmten Anrufen zu unterstützen, während das Anrufqualitätsdashboard Administratoren und Netzwerktechnikern beim Optimieren von Netzwerken hilft. Das Anrufqualitätsdashboard stellt nicht bestimmte Benutzer, sondern aggregierte Informationen für die gesamte Teams-Organisation in den Mittelpunkt. 

|Frage|Aktion |
|------------|-------|
| Wer ist für die Überwachung und Behandlung von Problemen bei Aufrufqualitätsproblemen zuständig? | Weitere Informationen zu den Berechtigungsstufen, die zur Behandlung von Anrufqualitätsproblemen erforderlich sind, finden Sie unter [Verwenden Sie Anrufanalyse, um Probleme mit schlechter Anrufqualität zu behandeln](use-call-analytics-to-troubleshoot-poor-call-quality.md).|
|||

### <a name="operate-your-meetings-service"></a>Betreiben Ihrer Besprechungsdienste

Es ist wichtig, dass Sie den Gesamtzustand Ihres Teams-Dienstes kennen, um andere Personen in Ihrer Organisation proaktiv über alle Ereignisse informieren zu können, die den Service beeinträchtigen. In den Artikeln zum Thema [Verwenden des Dienstes](1-drive-value-operate-my-service.md) finden Sie ausführliche Anleitungen für den Betrieb des Dienstes.

|Frage|Aktion |
|------------|-------|
|Wer wird in meiner Organisation für die Verwaltung des Besprechungsdienstes zuständig sein? | Stellen Sie sicher, dass die Person über die Teams-Administratorberechtigungen verfügt, die benötigt werden, um den Besprechungsdienst zu verwalten. Weitere Informationen zu den Administratorrollen in Teams finden Sie unter [Verwenden der Microsoft Teams-Administratorrollen zum Verwalten von Teams](using-admin-roles.md).|
|||


## <a name="next-steps"></a>Nächste Schritte
- [Fördern der Einführung](adopt-microsoft-teams-landing-page.md) von Besprechungen und Konferenzen innerhalb Ihrer Organisation
- [Hinzufügen von Audiokonferenzen](deploy-audio-conferencing-teams-landing-page.md)
- [Bereitstellen von Cloud Voice](cloud-voice-landing-page.md)
- Nehmen Sie die vorgeschlagenen Apps – wie etwa Planner – in Ihre erstmalige Teams-Bereitstellung auf. Fügen Sie mit fortschreitender Aneignung von Teams weitere [Apps, Bots und Connectors](deploy-apps-microsoft-teams-landing-page.md) hinzu.
