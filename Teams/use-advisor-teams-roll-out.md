---
title: Verwenden des Ratgebers für Teams (Advisor für Teams, öffentliche Vorschau) als Hilfe beim Rollout von Microsoft Teams
author: lolajacobsen
ms.author: lolaj
ms.reviewer: brandber
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ''
description: Verwenden Sie den Ratgeber für Teams (öffentliche Vorschau) als Hilfe bei der Planung und Durchführung Ihrer Bereitstellung von Microsoft Teams.
ms.openlocfilehash: 17fac0b4f4c974f72eccc7d0c11ae6b27337afef
ms.sourcegitcommit: 92a278c0145798266ecbe052e645b2259bcbd62d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42892285"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Verwenden Sie den Ratgeber für Teams als Hilfe beim Rollout von Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Der Ratgeber für Teams (Advisor für Teams, öffentliche Vorschau) führt Sie durch Ihren Rollout von Microsoft Teams. Er analysiert Ihre Office 365-Mandantenumgebung und identifiziert die am häufigsten verwendeten Konfigurationen, die Sie möglicherweise aktualisieren oder ändern müssen, bevor Sie den Rollout von Teams erfolgreich durchführen können. Anschließend erstellt der Ratgeber für Teams ein Bereitstellungsteam (in Teams) mit Kanälen für jede Workload, die Sie bereitstellen möchten. Jede Workload im Bereitstellungsteam bietet einen umfassenden Plan im Planner, der alle Rolloutaufgaben für jede Workload umfasst.  Mithilfe dieses Planner-Planes weisen Sie den Personen, die für die einzelnen Phasen des Rollouts verantwortlich sind, Aufgaben zu, einschließlich Projektmanager, Teams und Office 365-Administratoren, Supportmitarbeitern und ihrer Umstiegs- und Benutzerbereitschafts-Teams. Jede Rollout-Aufgabe enthält alle Anleitungen und Ressourcen, die Sie benötigen, um die Aufgabe erfolgreich durchführen zu können.

Der Ratgeber für Teams ist Teil des [Teams Admin Center](https://admin.teams.microsoft.com). Sie benötigen mindestens eine Office 365 Business Essentials-Lizenz, um in den Genuss der Integration von Advisor für Teams in Forms und Planner zu kommen. Wenn Sie beginnen, Advisor für Teams zu verwenden, klicken Sie auf die Schaltfläche **Start** im dem Widget **Teams-Workload bereitstellen** auf dem Dashboard. Oder wechseln Sie zu **Planung** > **Advisor für Teams**.

> [!IMPORTANT]
> Der Ratgeber für Teams ist für Microsoft 365 Government GCC High- oder DoD-Bereitstellungen nicht verfügbar.

Einen geführten Überblick über die Advisor für Teams-Oberfläche erhalten Sie im Microsoft Mechanics-Video [Deploy & Configure Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50) (Bereitstellen und Konfigurieren von Microsoft Teams).

## <a name="using-advisor-for-teams-public-preview"></a>Verwenden des Ratgebers für Teams (Advisor für Teams, öffentliche Vorschau)

**Für die Nutzung von Advisor für Teams sind Teams-, Forms- und Planner-Lizenzen erforderlich.** Sie müssen jedoch kein Teams-Administrator sein, um den Ratgeber für Teams zu verwenden – jeder Mitarbeiter in Ihrer Organisation kann ihn verwenden. Wir haben spezielle Berechtigungen eingerichtet, damit Benutzer, die keine Administratoren sind, auf den Ratgeber für Teams zugreifen können, obwohl er sich im Admin Center von Teams befindet. Sie müssen Teams-Administrator, Teams-Dienstadministrator oder globaler Administrator sein, um die Mandantenbereitschaftsbewertung öffnen zu können. (Dies liegt daran, dass die speziellen Nicht-Administratorrollen keinen Zugriff auf die Microsoft Graph-APIs haben, die den Bewertungen zugrunde liegen.)

> [!IMPORTANT]
> Wenn **Advisor für Teams** unter **Planung** im Team Admin Center nicht angezeigt wird, bedeutet dies, dass der Benutzer nicht für Teams lizenziert ist. Dieses Verhalten wird künftig geändert.

Wenn Sie Advisor für Teams zum ersten Mal verwenden, wird ein Bereitstellungsteam für Sie in Teams erstellt. Für jede ausgewählte Workload wird ein Kanal hinzugefügt.

> [!IMPORTANT]
> Wenn bereits ein Bereitstellungsteam erstellt wurde und ein anderer Benutzer versucht, es zu erstellen, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, sich an das Supportteam zu wenden. Auf diese Weise wird verhindert, dass Teams versehentlich Informationen zu den vorhandenen Teams und deren Mitgliedern offenlegt. Bitten Sie den Besitzer des Bereitstellungsteams, Sie hinzuzufügen, oder wenden Sie sich an einen Supportmitarbeiter, um Hilfe zu erhalten.

## <a name="available-advisor-for-teams-plans"></a>Verfügbare Pläne für Advisor für Teams

Während Advisor für Teams in öffentlicher Vorschau vorliegt, stellen wir diese beiden Pläne bereit:

1. Chat, Teams, Kanäle und Apps
    - Mandantenbewertung
    - Planer-Plan, einschließlich Umstiegsaufgaben
    - Formulare-Benutzerumfrage
    - Advisor für Teams – Bot
1. Besprechungen und Konferenzen
    - Mandantenbewertung
    - Planer-Plan, einschließlich Umstiegsaufgaben
    - Formulare-Benutzerumfrage
    - Advisor für Teams – Bot

Wir empfehlen, dass Sie mit dem Plan "Chat, Teams, Kanäle und Apps" starten. Wenn Sie die Bereitstellung dieser Workload abgeschlossen haben, wechseln Sie zurück zu Advisor für Teams, und klicken Sie auf **Kanal hinzufügen**, um die nächste Workload zu starten.

## <a name="tenant-assessment"></a>Mandantenbewertung
Jeder Plan umfasst eine Mandantenbereitschaftsbewertung, mit der Sie Mängel in Ihrer Umgebung erkennen und beheben können, bevor Sie Teams bereitstellen. Die Bewertungen umfassen Voraussetzungen und bewährte Methoden. Bei jedem Bewertungstest wird ein grünes Häkchen oder ein orangefarbenes Warndreieck angezeigt. 

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>Ein grünes Häkchen bedeutet, dass der Mandant den spezifischen Test bestanden hat. 
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>Ein orangefarbenes Warndreieck bedeutet, dass Sie nachforschen müssen, ob eine Maßnahme erforderlich ist (so empfiehlt sich beispielsweise eine Ablaufrichtlinie für Office 365-Gruppen, ist aber nicht erforderlich).

> [!IMPORTANT]
> Sobald ein Benutzer mit einer administrativen Rolle Advisor für Teams gestartet hat, werden alle Bewertungen im Hintergrund ausgeführt. Wenn Sie etwas aktualisieren oder korrigieren, kann es bis zu 24 Stunden dauern, bis es in ihren Bewertungen berücksichtigt wird. Dieser Zustand ist temporär – sobald Advisor für Teams den Status der öffentlichen Vorschau verlassen hat und allgemein verfügbar ist, werden die Bewertungen nahezu in Echtzeit aktualisiert.

In den nachstehenden Abschnitten werden die einzelnen Bewertungen beschrieben, und es wird erläutert, ob es sich bei den einzelnen Angaben um Voraussetzungen oder bewährte Methoden handelt, was bei den einzelnen Bewertungen überprüft wird und warum die Überprüfung erfolgt. Zudem erhalten Sie bei Bedarf Anleitungen zur Problembehebung.

### <a name="assessment-tests-for-all-workloads"></a>Bewertungstests für alle Workloads

|Bewertungstest  |Was sie erfahren  |
|---------|---------|
|Benutzerdefinierte Domäne konfiguriert     |Ob für Ihren Mandanten eine nicht @onmicrosoft.com-Domäne konfiguriert ist (z. B. @contoso.onmicrosoft.com). Sie können natürlich die "@onmicrosoft.com"-Domäne verwenden oder eine benutzerdefinierte Domäne konfigurieren. Es ist Ihre Entscheidung. Weitere Informationen finden Sie unter [Hinzufügen einer Domäne zu Office 365](https://docs.microsoft.com/office365/admin/setup/add-domain). |
|Teams-Lizenzen     |Dies ist eine Voraussetzung – Sie **müssen ** Teams-Lizenzen besitzen, um Teams bereitzustellen. Fragt Microsoft Graph ab, um zu ermitteln, ob Sie über Teams-Lizenzen verfügen (mit mindestens einer für die Zuweisung verfügbaren Lizenz). Weitere Informationen finden Sie unter [Office 365-Lizenzierung für Teams](https://docs.microsoft.com/microsoftteams/office-365-licensing).    |
|Exchange Online-Lizenzen     |Ob Sie über ein aktives Abonnement mit verfügbaren Exchange Online-Lizenzen verfügen. Exchange ist zwar nicht für die grundlegenden Funktionen von Teams erforderlich, doch die Integration mit Exchange bietet eine optimale Teams-Erfahrung. Fragt Microsoft Graph ab, um die mit Ihrem Mandanten verbundenen Abonnements zu analysieren und zu überprüfen, ob Sie über Abonnements mit einer berechtigten Exchange Online-Lizenz verfügen (mit mindestens einer für die Zuweisung verfügbaren Lizenz). Weitere Informationen finden Sie unter [Interaktion von Exchange und Teams](exchange-teams-interact.md).    |
|SharePoint Online-Lizenzen     |Ob Sie über ein aktives Abonnement mit verfügbaren SharePoint Online-Lizenzen verfügen. Wir empfehlen SharePoint Online-Lizenzen auf Benutzerbasis zur Bereitstellung von OneDrive for Business für die Dateispeicherung in Chats. Fragt Microsoft Graph ab, um zu ermitteln, ob Sie über SharePoint Online-Lizenzen verfügen (mit mindestens einer für die Zuweisung verfügbaren Lizenz). Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](https://docs.microsoft.com/microsoftteams/sharepoint-onedrive-interact).    |
|Gastzugriff aktiviert     |Bestimmt, ob der [Gastzugriff](guest-access.md) aktiviert ist. Mit Gastzugriff können Sie externe Benutzer in Ihre Teams einladen. Verwenden Sie die [Checkliste für den Teams-Gastzugriff](guest-access-checklist.md) zur Aktivierung des Gastzugriffs in Teams. Die Checkliste enthält die erforderlichen Azure AD-Konfigurationen. |
|Externer Zugriff konfiguriert     |Bestimmt, ob der [externe Zugriff](manage-external-access.md) aktiviert ist. Standardmäßig ist der externe Zugriff aktiviert, mit offenem Verbund. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>Bewertungen für Chat, Teams, Kanäle und Apps

Zusätzlich zu den [Bewertungstests für alle Workloads](#assessment-tests-for-all-workloads) werden die folgenden zusätzlichen Bewertungen für die Chat-, Teams-, Kanal- und App-Workloads ausgeführt:

|Bewertungstest  |Was sie erfahren  |
|---------|---------|
|Konfigurierte Benennungsrichtlinien für Office 365-Gruppen     |Ob Benennungsstandards für Office 365-Gruppen konfiguriert wurden. Die Benennungsrichtlinie für Office 365-Gruppen ermöglicht es Ihrer Organisation, eine einheitliche Benennungsstrategie auf vom Benutzer erstellte Teams anzuwenden und gilt auch für andere Gruppenworkloads (einschließlich Outlook, SharePoint, Planner und Yammer). Dieser Test fragt Azure AD über Microsoft Graph nach der Existenz von Benennungsrichtlinien ab, die für Office 365-Gruppen gelten. Weitere Informationen finden Sie unter [Benennungsrichtlinie für Office 365-Gruppen](https://docs.microsoft.com/office365/admin/create-groups/groups-naming-policy).    |
|Konfigurierte Ablaufrichtlinien für Office 365-Gruppen     |Ob eine Gruppenablaufrichtlinie für Office 365-Gruppen festgelegt wurde. Auf diese Weise kann Ihr Unternehmen inaktive Teams automatisch entfernen. Diese Option ist standardmäßig deaktiviert. Dieser Test fragt Azure AD über Microsoft Graph ab und meldet, ob der Wert vom Standard abweichend geändert wurde. Weitere Informationen finden Sie unter [Ablaufrichtlinie für Office 365-Gruppen](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups-expiration-policy).    |

### <a name="assessments-for-meetings-and-conferencing"></a>Bewertungen für Besprechungen und Konferenzen

Zusätzlich zu den [Bewertungstests für alle Workloads](#assessment-tests-for-all-workloads) werden die folgenden zusätzlichen Bewertungen für die Besprechungs- und Konferenzworkloads ausgeführt:

|Bewertungstest  |Was sie erfahren  |
|---------|---------|
|Audiokonferenz-Lizenzen    |Ob Sie über ein aktives Abonnement mit verfügbaren Audiokonferenz-Lizenzen verfügen. Dies ist eine Voraussetzung für den Einsatz von Audiokonferenzbrücken. Fragt Microsoft Graph ab, um zu ermitteln, ob Sie über Audiokonferenzlizenzen verfügen (mit mindestens einer verfügbaren Lizenz). Weitere Informationen finden Sie unter [Teams Add-On-Lizenzierung](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).    |
|Stream-Lizenzen     |Ob Sie über ein aktives Abonnement mit Microsoft Stream-Lizenzen verfügen. Dies ist eine Voraussetzung, wenn Sie die Besprechungsaufzeichnung aktivieren möchten. Fragt Microsoft Graph ab, um zu ermitteln, ob Sie über Microsoft Stream-Lizenzen verfügen (mit mindestens einer für die Zuweisung verfügbaren Lizenz). Weitere Informationen zu Stream und dessen Aktivierung finden Sie unter [Aufzeichnung einer Teams-Cloudbesprechung](cloud-recording.md).

### <a name="advisor-for-teams-bot"></a>Advisor für Teams – Bot

Sobald Advisor für Teams Ihr Bereitstellungsteam erstellt hat, schickt der Advisor für Teams-Bot die folgende Nachricht im Kanal "Allgemein".

>**Willkommen bei Ihrem Bereitstellungsteam für Microsoft Teams!**
>  
>Der Zweck dieses Teams besteht darin, Sie durch das Rollout Ihrer Organisation zu führen, indem es Ihnen alle benötigten Ressourcen zur Verfügung stellt und dem Projektteam einen Platz zur Zusammenarbeit bietet. Jeder Kanal, der mit dem Ratgeber für Teams erstellt wird, umfasst einen schrittweisen Plan für Planner und andere Ressourcen, z. B. eine Formular-Benutzerumfrage, die während des Rollouts verwendet werden kann. Sie können zu einem beliebigen Zeitpunkt zurückkehren und die Bewertung der Mandantenbereitschaft überprüfen oder zusätzliche Workloads-Pläne über das Teams Admin Center hinzufügen.
> 
>**Handlungsaufforderung** 
>- Wenn Sie noch nicht mit Teams oder Planner vertraut sind, schauen Sie sich unsere [Teams-Vorgehensweise](https://teamsdemo.office.com/) an und sehen Sie die [Planner-Schnellstartvideos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7). 
>- Gehen Sie zu Ihrem Bereitstellungsteam in Teams. Wählen Sie den Workload-Kanal (z. B. Chat, Teams, Kanäle und Apps), und wählen Sie die Registerkarte **Planner** aus, um zu beginnen.
> 
>Wenn Sie mehr über den Ratgeber für Teams wissen möchten, lesen Sie [Verwenden des Ratgebers für Teams, um Microsoft Teams bereitzustellen](use-advisor-teams-roll-out.md).
>

> [!IMPORTANT]
> Der Ratgeber für Teams-Bot wird nur verwendet, um eine Willkommensnachricht an Ihr Bereitstellungsteam zu schicken. Es werden keine weiteren Daten gesammelt.

> [!IMPORTANT]
> Der Advisor für Teams-Bot ist standardmäßig aktiviert. Deaktivieren Sie ihn nicht, wenn Sie Advisor für Teams verwenden oder vorhaben, Advisor für Teams zu verwenden.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Welche Lizenzanforderungen gelten für den Ratgeber für Teams?
Sie benötigen mindestens Office 365 Business Essentials, um in den Genuss der Integration von Advisor für Teams in Forms und Planner zu kommen.

### <a name="can-i-delete-the-deployment-team"></a>Kann ich das Bereitstellungsteam löschen?
Nachdem der Ratgeber für Teams Ihr Bereitstellungsteam erstellt hat, können Sie das Team wie jedes andere Team verwalten – einschließlich der Möglichkeit es zu löschen. Achten Sie darauf, dass das Team im Microsoft Teams Admin Center weiterhin angezeigt wird, wenn es nicht unter Verwendung des Microsoft Teams Admin Center gelöscht wurde. Dieser Zustand ist temporär – sobald Advisor für Teams den Zeitraum der öffentlichen Vorschau verlassen hat und allgemein verfügbar ist, wird dies korrigiert.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>Kann ich im Bereitstellungsteam Kanäle hinzufügen oder entfernen?
Ja, nachdem das Bereitstellungsteam erstellt wurde, können Sie die Kanäle auf die gleiche Weise wie bei jedem anderen Team verwalten.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>Kann ich im Bereitstellungsteam Projektteammitglieder hinzufügen oder entfernen?
Ja, nachdem das Bereitstellungsteam erstellt wurde, können Sie Projektteammitglieder auf die gleiche Weise wie bei jedem anderen Team verwalten.

### <a name="can-i-modify-the-planner-plans"></a>Kann ich die Planner-Pläne ändern?
Ja, nachdem der Ratgeber für Teams Ihr Bereitstellungsteam erstellt hat, sollten Sie den Planner-Plan so aktualisieren, dass er den Rollout ihrer Teams am besten unterstützt. Sie können alles ändern – Buckets, Aufgaben, Aufgabendetails, – ebenso wie bei jedem anderen Planner-Plan.

### <a name="can-i-modify-the-forms-survey"></a>Kann ich die Formulare-Umfrage ändern?
Ja, nachdem der Ratgeber für Teams Ihr Bereitstellungsteam erstellt hat, können Sie die Formulare-Umfrage nach Bedarf ändern.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Welche Daten werden von dem Ratgeber für Teams über meine Organisation gesammelt?
Der Ratgeber für Teams fragt, ob Sie einverstanden sind, das nicht-EUII (endbenutzeridentifizierende Daten) gesammelt werden. Bei den gesammelten Daten handelt es sich um eine Telemetrie, die Microsoft ein Feedback darüber gibt, wie erfolgreich der Berater für Teams Ergebnisse erzielt und inwieweit er ggf. verbessert werden muss. Diese Daten werden verwendet, um Chancen für Microsoft zu erkennen, sich proaktiv mit Ihrer Organisation zu befassen, um sie bei Ihrer Bereitstellung zu unterstützen.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>Kann ich den Ratgeber für Teams mit FastTrack verwenden?
Ja, FastTrack nutzt den Ratgeber für Teams für alle Kunden, die sich für die Bereitstellung von Teams interessieren. Sie können Ihnen bei der ersten Einrichtung Ihres Bereitstellungsteams über den Ratgeber für Teams (sofern erforderlich) Hilfe anbieten und Sie während des Rollouts von Teams nach Bedarf bei spezifischen Themen unterstützen.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>Kann ich den Ratgeber für Teams mit einem Partner verwenden?
Ja, Sie können den Ratgeber für Teams verwenden und gleichzeitig einen Bereitstellungspartner für Ihre Teams-Bereitstellung verwenden. Wenn Ihr Partner ein CSP ist und Ihre Mandanten auf Ihren Auftrag verwaltet, kann er den Ratgeber für Teams verwenden, um Ihr Bereitstellungsteam zu erstellen und Sie bei der Durchführung des Gesamtprojekts zu unterstützen. Darüber hinaus können Sie mit einem beliebigen Partner zusammenarbeiten, indem Sie diese Personen als Gäste Ihrem Bereitstellungsteam hinzufügen, damit sie als Mitglieder des Gesamtprojektteams teilnehmen können.

### <a name="how-do-i-use-planner"></a>Wie verwende ich Planner?
Schauen Sie sich [Microsoft Planner-Hilfe](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) und die [Planner-Schnellstartvideos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7)an. 

### <a name="how-do-i-use-forms"></a>Wie verwende ich Formulare?
Wechseln Sie zum [Formulare-Hilfecenter](https://support.office.com/forms).

## <a name="related-topics"></a>Verwandte Themen

[Bereitstellen von Teams](How-to-roll-out-teams.md)

[Bewährte Methoden zum Organisieren von Teams in Microsoft Teams](best-practices-organizing.md)

[Produktnamen und Serviceplanbezeichner für die Lizenzierung](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference
) 
