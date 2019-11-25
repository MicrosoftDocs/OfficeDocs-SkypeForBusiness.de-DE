---
title: Verwenden Sie den Ratgeber für Teams (Vorschau) als Hilfe beim Rollout von Microsoft Teams
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
f1keywords:
- ms.teamsadmincenter.deploymentadvisor.overview
ms.custom: ''
description: Verwenden Sie den Ratgeber für Teams (Preview), um Ihnen bei der Planung und Durchführung ihrer Bereitstellung von Microsoft Teams zu helfen.
ms.openlocfilehash: f7de348c6f8ca60cc1d062fce79725b4b18d0350
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "39209191"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Verwenden Sie den Ratgeber für Teams als Hilfe beim Rollout von Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Ratgeber für Teams (Preview) führt Sie durch Ihren Rollout von Microsoft Teams. Er analysiert Ihre Office 365-Mandantenumgebung und identifiziert die am häufigsten verwendeten Konfigurationen, die Sie möglicherweise aktualisieren oder ändern müssen, bevor Sie den Rollout von Teams erfolgreich durchführen können. Anschließend erstellt der Ratgeber für Teams ein Bereitstellungsteam (in Teams) mit Kanälen für jede Workload, die Sie bereitstellen möchten. Jede Workload im Bereitstellungsteam bietet einen umfassenden Plan im Planner, der alle Rolloutaufgaben für jede Workload umfasst.  Mithilfe dieses Planner-Planes weisen Sie den Personen, die für die einzelnen Phasen des Rollouts verantwortlich sind, Aufgaben zu, einschließlich Projektmanager, Teams und Office 365-Administratoren, Supportmitarbeitern und ihrer Umstiegs- und Benutzerbereitschafts-Teams. Jede Rollout-Aufgabe enthält alle Anleitungen und Ressourcen, die Sie benötigen, um die Aufgabe erfolgreich durchführen zu können.

Der Ratgeber für Teams ist Teil des [Teams Admin Center](https://admin.teams.microsoft.com). Wenn Sie das erste Mal den Ratgeber für Teams verwenden möchten, klicken Sie auf die Schaltfläche **Start** auf dem Widget **Bereitstellen der Teams-Workload** auf dem Dashboard. Oder wechseln Sie zu **Planen** > **Ratgeber**.

> [!IMPORTANT]
> Der Ratgeber für Teams ist für Microsoft 365 Government GCC High- oder DoD-Bereitstellungen nicht verfügbar.

## <a name="using-advisor-for-teams-preview"></a>Den Ratgeber für Teams (Vorschau) verwenden

Sie müssen kein Teams-Administrator sein, um den Ratgeber für Teams zu verwenden – jeder Mitarbeiter in Ihrer Organisation kann ihn verwenden. Wir haben spezielle Berechtigungen eingerichtet, damit Benutzer, die keine Administratoren sind, auf den Ratgeber für Teams zugreifen können, obwohl er sich im Admin Center von Teams befindet. Sie müssen Teams-Administrator, Teams-Dienstadministrator oder globaler Administrator sein, um auf die Bereitschaftsbewertung der Mandanten zugreifen zu können.

Wenn Sie den Ratgeber für Teams zum ersten Mal verwenden, wird ein Bereitstellungsteam für Sie in Teams erstellt. Es fügt Kanäle für jede Workload hinzu, die Sie bereitstellen möchten. 


## <a name="available-advisor-for-teams-plans"></a>Verfügbare Plans für den Ratgeber für Teams

Während der Ratgeber für Teams in der Vorschauversion ist, stellen wir diese beiden Pläne bereit:

1. Chat, Teams, Kanäle und Apps
    - Mandantenbewertung
    - Planer-Plan, einschließlich Umstiegsaufgaben
    - Formulare-Benutzerumfrage
1. Besprechungen und Konferenzen
    - Mandantenbewertung
    - Planer-Plan, einschließlich Umstiegsaufgaben
    - Formulare-Benutzerumfrage

Wir empfehlen, dass Sie mit dem Plan „Chat, Teams, Kanäle und Apps“ starten. Wenn Sie die Bereitstellung dieser Workload abgeschlossen haben, wechseln Sie zurück zum Ratgeber und klicken Sie auf **Kanal hinzufügen**, um die nächste Workload zu starten. 

## <a name="tenant-assessment"></a>Mandantenbewertung
Jeder Plan umfasst eine Mandantenbereitschaftsbewertung, die Sie verwenden können, um Mängel in Ihrer Umgebung zu erkennen und zu beheben, bevor Sie Teams bereitstellen. Hier sehen Sie, was in jeder Bewertung überprüft wird:

### <a name="chat-teams-channels-and-apps"></a>Chat, Teams, Kanäle und Apps


|Bewertung  |Was sie Ihnen sagt  |
|---------|---------|
|Teams-Lizenzen     |Ob Sie über ein aktives Abonnement mit verfügbaren Teams-Lizenzen verfügen |
|Exchange-Lizenzen     |Ob Sie über ein aktives Abonnement mit verfügbaren Exchange Online-Lizenzen verfügen. Exchange ist zwar nicht für die grundlegenden Funktionen von Teams erforderlich, doch die Integration mit Exchange bietet eine optimale Teams-Erfahrung.         |
|SharePoint Online-Lizenzen     | Ob Sie über ein aktives Abonnement mit verfügbaren SharePoint Online-Lizenzen verfügen. Sie benötigen eine SharePoint Online-Lizenz pro Benutzer für die Dateispeicherung, die Kanalzusammenarbeit und den Chat. 
|Gastzugriff aktiviert     |Ob der Gastzugriff auf Teams aktiviert ist. Azure Active Directory-Einstellungen für den Gastzugriff werden nicht überprüft.   |
|Benutzerdefinierte Domäne konfiguriert     |Ob für Ihren Mandanten eine nicht @onmicrosoft.com-Domäne konfiguriert ist  |
|Benennungsstandard für die Office 365-Gruppen konfiguriert     | Ob Benennungsstandards für Office 365-Gruppen konfiguriert wurden        |
|Ablaufrichtlinie für Office 365-Gruppen konfiguriert     |  Ob eine Gruppenablaufrichtlinie für Office 365-Gruppen festgelegt wurde. Wenn nicht, wird der Wert auf "nie" gesetzt.        |
|Externer Zugriff konfiguriert     |Ob der externe Zugriff aktiviert ist, damit Sie mit externen Organisationen in Teams kommunizieren können.          |

### <a name="meetings-and-conferencing"></a>Besprechungen und Konferenzen


|Bewertung  |Was sie Ihnen sagt  |
|---------|---------|
|Teams-Lizenzen     |Ob Sie über ein aktives Abonnement mit verfügbaren Teams-Lizenzen verfügen |
|Exchange-Lizenzen     |Ob Sie über ein aktives Abonnement mit verfügbaren Exchange Online-Lizenzen verfügen. Exchange ist zwar nicht für die grundlegenden Funktionen von Teams erforderlich, doch die Integration mit Exchange bietet eine optimale Teams-Erfahrung. |
|Audiokonferenz-Lizenzen    |Ob Sie über ein aktives Abonnement mit verfügbaren Audiokonferenz-Lizenzen verfügen |
|Stream-Lizenzen     |Ob Sie über ein aktives Abonnement mit Stream-Lizenzen verfügen, das verwendet werden kann, wenn Besprechungssaufzeichnungen erwünscht sind. |
|Gastzugriff     |Ob der Gastzugriff auf Teams aktiviert ist. Azure Active Directory-Einstellungen für den Gastzugriff werden nicht überprüft.|
|Benutzerdefinierte Domäne     |Ob für Ihren Mandanten eine nicht @onmicrosoft.com-Domäne konfiguriert ist.  |
|Externer Zugriff     |Ob der externe Zugriff aktiviert ist, damit Sie mit externen Organisationen in Teams kommunizieren können. |


### <a name="advisor-bot"></a>Ratgeber-Bot
Sobald der Ratgeber Ihr Bereitstellungsteam erstellt hat, schickt der Ratgeber-Bot die folgende Nachricht.

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
> Der Ratgeber für Teams-Bot ist standardmäßig aktiviert. Deaktivieren Sie ihn nicht, wenn Sie den Ratgeber für Teams verwenden oder wenn Sie es vorhaben, ihn zu verwenden.


## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen
### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Welche Lizenzanforderungen gelten für den Ratgeber für Teams?
Es gibt keine zusätzlichen Lizenzanforderungen außer über eine Lizenz für Teams zu verfügen.

### <a name="can-i-delete-the-deployment-team"></a>Kann ich das Bereitstellungsteam löschen?
Nachdem der Ratgeber für Teams Ihr Bereitstellungsteam erstellt hat, können Sie das Team wie jedes andere Team verwalten – einschließlich der Möglichkeit es zu löschen. Achten Sie darauf, dass, wenn Sie das Team nicht mithilfe des Teams Admin Center löschen, berichtet wird, dass das Team vorhanden ist.

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
