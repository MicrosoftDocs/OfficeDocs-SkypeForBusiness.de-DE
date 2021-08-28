---
title: Durchführen des Rollouts von Microsoft Teams mithilfe von Advisor für Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: pkrebs
manager: serdars
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- remotework
- m365initiative-deployteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.deploymentadvisor.overview
description: Verwenden Sie Advisor für Teams zur Unterstützung der Planung und Durchführung der Bereitstellung von Microsoft Teams
ms.openlocfilehash: 68ac2ec927b1790502a8562c848f1e82f8913668
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58594447"
---
# <a name="use-advisor-for-teams-to-help-you-roll-out-microsoft-teams"></a>Durchführen des Rollouts von Microsoft Teams mithilfe von Advisor für Teams

Advisor für Teams führt Sie durch Ihren Rollout von Microsoft Teams. Die Funktion bewertet Ihre Microsoft 365-Organisationsumgebung und identifiziert die häufigsten Konfigurationen, die Sie möglicherweise aktualisieren oder ändern müssen, bevor Sie den Rollout von Teams erfolgreich durchführen können. Anschließend erstellt Advisor für Teams ein Bereitstellungsteam (in Teams) mit Kanälen für jede Workload, die Sie bereitstellen möchten. Jede Workload im Bereitstellungsteam bietet einen umfassenden Plan im Planner, der alle Rolloutaufgaben für jede Workload umfasst.  Mithilfe dieses Planner-Plans weisen Sie den Personen, die für die einzelnen Phasen des Rollouts verantwortlich sind, Aufgaben zu, beispielsweise Projektmanagern, Teams-Administratoren und Supportmitarbeitern sowie Ihrem Umstiegs- und Benutzerbereitschaftsteam. Jede Rollout-Aufgabe enthält alle Anleitungen und Ressourcen, die Sie benötigen, um die Aufgabe erfolgreich durchführen zu können.

Advisor für Teams ist Teil des [Teams Admin Center](https://admin.teams.microsoft.com). Sie benötigen mindestens eine Microsoft 365 Business Basic-Lizenz, damit Sie die Vorteile der Integration Advisor für Teams mit Forms und Planner nutzen können. Wenn Sie beginnen, Advisor für Teams zu verwenden, klicken Sie auf die Schaltfläche **Start** im dem Widget **Teams-Workload bereitstellen** auf dem Dashboard. Oder wechseln Sie zu **Planung** > **Advisor für Teams**.

> [!IMPORTANT]
> Advisor für Teams ist für Microsoft 365 Government GCC High- oder DoD-Bereitstellungen nicht verfügbar.

Einen geführten Überblick über die Advisor für Teams-Oberfläche erhalten Sie im Microsoft Mechanics-Video [Deploy & Configure Microsoft Teams](https://youtu.be/o2mlsUubIO4?t=50) (Bereitstellen und Konfigurieren von Microsoft Teams).

## <a name="using-advisor-for-teams"></a>Advisor für Teams im Einsatz

**Für die Nutzung von Advisor für Teams sind Teams-, Forms- und Planner-Lizenzen erforderlich.** Sie müssen jedoch kein Teams-Administrator sein, um Advisor für Teams zu verwenden – dazu ist jeder Mitarbeiter in Ihrer Organisation berechtigt. Wir haben spezielle Berechtigungen eingerichtet, damit Benutzer, die keine Administratoren sind, auf Advisor für Teams zugreifen können, obwohl er sich im Admin Center von Teams befindet. Sie müssen Teams-Administrator oder globaler Administrator sein, um die Mandantenbereitschaftsbewertung öffnen zu können. (Dies liegt daran, dass die speziellen Nicht-Administratorrollen keinen Zugriff auf die Microsoft Graph-APIs haben, die den Bewertungen zugrunde liegen.)

> [!IMPORTANT]
> Wenn **Advisor für Teams** unter **Planung** im Team Admin Center nicht angezeigt wird, bedeutet dies, dass der Benutzer nicht für Teams lizenziert ist.

Wenn Sie Advisor für Microsoft Teams zum ersten Mal verwenden, wird ein Bereitstellungsteam für Sie in Microsoft Teams erstellt. Für jede ausgewählte Workload wird ein Kanal hinzugefügt.

> [!IMPORTANT]
> Wenn ein Bereitstellungsteam erstellt wurde und ein anderer Benutzer versucht, es zu erstellen, wird eine Fehlermeldung angezeigt, in der Sie aufgefordert werden, sich an das Supportteam zu wenden. Auf diese Weise wird verhindert, dass Teams versehentlich Informationen zu den vorhandenen Teams und deren Mitgliedern offenlegt. Bitten Sie den Besitzer des Bereitstellungsteams, Sie hinzuzufügen, oder wenden Sie sich an einen Supportmitarbeiter, um Hilfe zu erhalten.

## <a name="available-advisor-for-teams-plans"></a>Verfügbare Pläne für Advisor für Teams

Advisor für Teams bietet zurzeit die folgenden Pläne:

1. Chat, Teams, Kanäle und Apps
    - Mandantenbewertung
    - Planer-Plan, einschließlich Umstiegsaufgaben
    - Forms-Benutzerumfrage
    - Advisor für Teams-Bot
1. Besprechungen und Konferenzen
    - Mandantenbewertung
    - Planer-Plan, einschließlich Umstiegsaufgaben
    - Forms-Benutzerumfrage
    - Advisor für Teams-Bot
1. Skype for Business-Upgrade
    - Mandantenbewertung
    - Planer-Plan, einschließlich Umstiegsaufgaben
    - Forms-Benutzerumfrage
    - Advisor für Teams-Bot
    - Der Skype for Business-Upgradeplan ist für Kunden gedacht, die zurzeit Skype for Business Online oder Skype for Business in lokalen Umgebungen verwenden, und hilft Ihnen, Unsicherheiten bei einem Upgrade zu beseitigen.  Der Plan basiert auf einem bewährten Gerüst für die erfolgreiche Implementierung von Änderungen und führt Sie schrittweise durch den Prozess, ganz gleich, ob Sie gerade erst mit Microsoft Teams beginnen, es bereits zusammen mit Skype for Business nutzen oder ein Upgrade vornehmen möchten. Der Plan bietet außerdem den Zugriff auf [Online-Leitfäden und bewährte Methoden](./upgrade-start-here.md), [herunterladbare Ressourcen](https://aka.ms/UpgradeSuccessKit), [Live 1: viele Planungs-Workshops](./upgrade-workshops-landing-page.yml) und weitere Ressourcen zur Unterstützung Ihres Erfolgs.
1. Education (nur für Bildungseinrichtungen sichtbar)
    - Mandantenbewertung
    - Planer-Plan, einschließlich Umstiegsaufgaben
    - Forms-Benutzerumfrage
    - Advisor für Teams-Bot
    - Der Education-Plan wurde für Bildungseinrichtungen entwickelt und hilft Ihnen bei der Bereitstellung, Einführung und Verwaltung von Microsoft Teams in Ihrer Bildungseinrichtung.

Kommerzielle Organisationen sollten mit dem Plan „Chat, Teams, Kanäle und Apps“ starten. Bildungseinrichtungen sollten mit dem Education-Plan beginnen. Wenn Sie die Bereitstellung dieser Workload abgeschlossen haben, wechseln Sie zurück zu Advisor für Teams, und klicken Sie auf **Kanal hinzufügen**, um die nächste Workload zu starten.



## <a name="tenant-assessment"></a>Mandantenbewertung

Jeder Plan umfasst eine Mandantenbereitschaftsbewertung, mit der Sie Mängel in Ihrer Umgebung erkennen und beheben können, bevor Sie Teams bereitstellen. Die Bewertungen umfassen Voraussetzungen und bewährte Methoden. Bei jedem Bewertungstest wird ein grünes Häkchen oder ein orangefarbenes Warndreieck angezeigt.

- <sub><img src="media/use-advisor-teams-roll-out-image2.png" alt="Green check mark"/></img></sub>Ein grünes Häkchen bedeutet, dass der Mandant den spezifischen Test bestanden hat.
- <sub><img src="media/use-advisor-teams-roll-out-image1.png" alt="Yellow alert mark"/></img></sub>Ein orangefarbenes Warndreieck bedeutet, dass Sie nachforschen müssen, ob eine Maßnahme erforderlich ist (so empfiehlt sich beispielsweise eine Ablaufrichtlinie für Microsoft 365-Gruppen, ist aber nicht erforderlich).

> [!IMPORTANT]
> Sobald ein Benutzer mit einer administrativen Rolle Advisor für Teams gestartet hat, werden alle Bewertungen im Hintergrund ausgeführt. Wenn Sie etwas aktualisieren oder korrigieren, kann es bis zu 24 Stunden dauern, bis es in ihren Bewertungen berücksichtigt wird.

In den nachstehenden Abschnitten werden die einzelnen Bewertungen beschrieben, und es wird erläutert, ob es sich bei den einzelnen Angaben um Voraussetzungen oder bewährte Methoden handelt, was bei den einzelnen Bewertungen überprüft wird und warum die Überprüfung erfolgt. Zudem erhalten Sie bei Bedarf Anleitungen zur Problembehebung.

### <a name="assessment-tests-for-all-workloads"></a>Bewertungstests für alle Workloads

|Bewertungstest  |Was sie erfahren  |
|---------|---------|
|Benutzerdefinierte Domäne konfiguriert     |Ob für Ihren Mandanten eine nicht @onmicrosoft.com-Domäne konfiguriert ist (z. B. @contoso.onmicrosoft.com). Sie können natürlich die "@onmicrosoft.com"-Domäne verwenden oder eine benutzerdefinierte Domäne konfigurieren. Es ist Ihre Entscheidung. Weitere Informationen finden Sie unter [Hinzufügen einer Domäne zu Microsoft 365](/microsoft-365/admin/setup/add-domain). |
|Teams-Lizenzen     |Dies ist eine Voraussetzung – Sie **müssen** Teams-Lizenzen besitzen, um Teams bereitzustellen. Fragt Microsoft Graph ab, um zu ermitteln, ob Sie über Teams-Lizenzen verfügen (mit mindestens einer für die Zuweisung verfügbaren Lizenz). Weitere Informationen finden Sie unter [Microsoft Teams-Dienstbeschreibung](/office365/servicedescriptions/teams-service-description).    |
|Exchange Online-Lizenzen     |Ob Sie über ein aktives Abonnement mit verfügbaren Exchange Online-Lizenzen verfügen. Exchange ist zwar nicht für die grundlegenden Funktionen von Teams erforderlich, doch die Integration mit Exchange bietet eine optimale Teams-Erfahrung. Fragt Microsoft Graph ab, um die mit Ihrem Mandanten verbundenen Abonnements zu analysieren und zu überprüfen, ob Sie über Abonnements mit einer berechtigten Exchange Online-Lizenz verfügen (mit mindestens einer für die Zuweisung verfügbaren Lizenz). Weitere Informationen finden Sie unter [Interaktion von Exchange und Teams](exchange-teams-interact.md).    |
|SharePoint Online-Lizenzen     |Ob Sie über ein aktives Abonnement mit verfügbaren SharePoint Online-Lizenzen verfügen. Wir empfehlen SharePoint Online-Lizenzen auf Benutzerbasis zur Bereitstellung von OneDrive for Business für die Dateispeicherung in Chats. Fragt Microsoft Graph ab, um zu ermitteln, ob Sie über SharePoint Online-Lizenzen verfügen (mit mindestens einer für die Zuweisung verfügbaren Lizenz). Weitere Informationen finden Sie unter [Interaktion von SharePoint Online und OneDrive for Business mit Microsoft Teams](./sharepoint-onedrive-interact.md).    |
|Gastzugriff aktiviert     |Bestimmt, ob der [Gastzugriff](guest-access.md) aktiviert ist. Mit Gastzugriff können Sie externe Benutzer in Ihre Teams einladen. Sehen Sie unter [Zusammenarbeit mit Gästen in einem Team](/microsoft-365/solutions/collaborate-as-team) zur Aktivierung des Gastzugriffs in Teams. Die Checkliste enthält die erforderlichen Azure AD-Konfigurationen. |
|Externer Zugriff konfiguriert     |Bestimmt, ob der [externe Zugriff](manage-external-access.md) aktiviert ist. Standardmäßig ist der externe Zugriff aktiviert, mit offenem Verbund. |

### <a name="assessments-for-chat-teams-channels-and-apps"></a>Bewertungen für Chat, Teams, Kanäle und Apps

Zusätzlich zu den [Bewertungstests für alle Workloads](#assessment-tests-for-all-workloads) werden die folgenden zusätzlichen Bewertungen für die Chat-, Teams-, Kanal- und App-Workloads ausgeführt:

|Bewertungstest  |Was sie erfahren  |
|---------|---------|
|Konfigurierte Benennungsrichtlinien für Microsoft 365-Gruppen     |Ob Benennungsstandards für Microsoft 365-Gruppen konfiguriert wurden. Die Benennungsrichtlinie von Microsoft 365-Gruppen ermöglicht Ihrer Organisation die Anwendung einer konsistenten Benennungsstrategie auf von Benutzern erstellte Teams und gilt auch für andere Gruppenarbeitslasten (einschließlich Outlook, SharePoint, Planner und Yammer). Dieser Test fragt Azure AD über den Microsoft Graph ab, um die Existenz von Benennungsrichtlinien zu prüfen, die für Microsoft 365-Gruppen gelten. Weitere Informationen finden Sie unter [Benennungsrichtlinie für Gruppen](/microsoft-365/admin/create-groups/groups-naming-policy).    |
|Konfigurierte Ablaufrichtlinien für Microsoft 365-Gruppen     |Ob eine Gruppenablaufrichtlinie für Microsoft 365-Gruppen definiert wurde. Auf diese Weise kann Ihr Unternehmen inaktive Teams automatisch entfernen. Diese Option ist standardmäßig deaktiviert. Dieser Test fragt Azure AD über Microsoft Graph ab und meldet, ob der Wert vom Standard abweichend geändert wurde. Weitere Informationen finden Sie unter [Ablaufrichtlinie für Microsoft 365-Gruppen](/microsoft-365/admin/create-groups/office-365-groups-expiration-policy).    |

### <a name="assessments-for-meetings-and-conferencing"></a>Bewertungen für Besprechungen und Konferenzen

Zusätzlich zu den [Bewertungstests für alle Workloads](#assessment-tests-for-all-workloads) werden die folgenden zusätzlichen Bewertungen für die Besprechungs- und Konferenzworkloads ausgeführt:

|Bewertungstest  |Was sie erfahren  |
|---------|---------|
|Audiokonferenz-Lizenzen    |Ob Sie über ein aktives Abonnement mit verfügbaren Audiokonferenz-Lizenzen verfügen. Dies ist eine Voraussetzung für den Einsatz von Audiokonferenzbrücken. Fragt Microsoft Graph ab, um zu ermitteln, ob Sie über Audiokonferenzlizenzen verfügen (mit mindestens einer verfügbaren Lizenz). Weitere Informationen finden Sie unter [Teams Add-On-Lizenzierung](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).    |
|Stream-Lizenzen     |Ob Sie über ein aktives Abonnement mit Microsoft Stream-Lizenzen verfügen. Dies ist eine Voraussetzung, wenn Sie die Besprechungsaufzeichnung aktivieren möchten. Fragt Microsoft Graph ab, um zu ermitteln, ob Sie über Microsoft Stream-Lizenzen verfügen (mit mindestens einer für die Zuweisung verfügbaren Lizenz). Weitere Informationen zu Stream und dessen Aktivierung finden Sie unter [Aufzeichnung einer Teams-Cloudbesprechung](cloud-recording.md).

### <a name="assessments-for-skype-for-business-upgrade"></a>Bewertungen für das Skype for Business-Upgrade

Zusätzlich zu den [Bewertungstests für alle Workloads](#assessment-tests-for-all-workloads) umfasst das Skype for Business Upgrade auch Bewertungen, die im Besprechungs- und Konferenzplan verwendet werden.

### <a name="advisor-for-teams-bot"></a>Advisor für Teams-Bot

Sobald Advisor für Teams Ihr Bereitstellungsteam erstellt hat, schickt der Advisor für Teams-Bot die folgende Nachricht im Kanal "Allgemein".

>**Willkommen bei Ihrem Bereitstellungsteam für Microsoft Teams!**
>  
>Der Zweck dieses Teams besteht darin, Sie durch das Rollout Ihrer Organisation zu führen, indem es Ihnen alle benötigten Ressourcen zur Verfügung stellt und dem Projektteam einen Platz zur Zusammenarbeit bietet. Jeder Kanal, der mit Advisor für Teams erstellt wird, umfasst einen schrittweisen Plan für Planner und andere Ressourcen, z. B. eine Forms-Benutzerumfrage, die während des Rollouts verwendet werden kann. Sie können zu einem beliebigen Zeitpunkt zurückkehren und die Bewertung der Mandantenbereitschaft überprüfen oder zusätzliche Workload-Pläne über das Microsoft Teams Admin Center hinzufügen.
>
>**Handlungsaufforderung**
>
>- Wenn Sie noch nicht mit Teams oder Planner vertraut sind, schauen Sie sich unsere [Teams-Vorgehensweise](https://teamsdemo.office.com/) an und sehen Sie die [Planner-Schnellstartvideos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7).
>- Gehen Sie zu Ihrem Bereitstellungsteam in Teams. Wählen Sie den Workload-Kanal (z. B. Chat, Teams, Kanäle und Apps), und wählen Sie die Registerkarte **Planner** aus, um zu beginnen.
>
>Wenn Sie mehr über Advisor für Teams wissen möchten, lesen Sie [Durchführen des Rollouts von Microsoft Teams mithilfe von Advisor für Teams](use-advisor-teams-roll-out.md).
>

> [!IMPORTANT]
> Der Advisor für Teams-Bot wird nur verwendet, um eine Willkommensnachricht an Ihr Bereitstellungsteam zu schicken. Es werden keine weiteren Daten gesammelt.

> [!IMPORTANT]
> Der Advisor für Teams-Bot ist standardmäßig aktiviert. Deaktivieren Sie ihn nicht, wenn Sie Advisor für Teams verwenden oder vorhaben, Advisor für Teams zu verwenden.

## <a name="advisor-for-teams-and-microsoft-365-learning-pathways"></a>Advisor für Microsoft Teams und Microsoft 365 – Lernpfade

[Microsoft 365-Lernpfade](/office365/customlearning/) ist eine On-Demand-Lernlösung, die Sie anpassen können, um Ihre Benutzer zu schulen und die Nutzung und Annahme von Microsoft Teams in Ihrer Organisation zu verbessern. Verwenden Sie Lernpfade zusammen mit Advisor für Teams, um Ihre Benutzer schnell mit Microsoft Teams vertraut zu machen und die Nutzung zu steigern.

Die Lernpfade-Lösung bietet Ihnen eine SharePoint Online-Websitevorlage und die Möglichkeit, eine Lernwebsite für Ihre Benutzer zu erstellen. Sie können das Schulungsportal für Lernpfade anpassen, um speziell auf die Anforderungen Ihrer Benutzer zugeschnittene Schulungs- und Supportinhalte bereitzustellen. Verwenden Sie die Microsoft Teams-Wiedergabelisten aus dem Microsoft Online-Katalog, und fügen Sie Ihre eigene hinzu.

Sie können in den Lernpfaden eine Schulungssite erstellen und diese dann als Registerkarte zu einem Kanal in Microsoft Teams hinzufügen, um Benutzern schnellen und einfachen Zugriff darauf zu ermöglichen.

Verwenden Sie z. B. Advisor für Teams zusammen mit Lernpfaden, um Ihren Helpdesk und Experten zu schulen, und verwenden Sie dann Lernpfade für die Schulung Ihrer Endbenutzer. Erstellen Sie eine Schulungssite, um das Onboarding Ihres Helpdesks und Ihrer Experten in Microsoft Teams zu erleichtern, und fügen Sie die Site dann als Registerkarte zu jedem Workloadkanal hinzu, den Sie bereitstellen. Ihr Helpdesk und Ihre Experten können dann auf dem Lernpfade-Schulungsportal eine Supportseite mit Links und benutzerdefinierten Wiedergabelisten erstellen, um Ihre Benutzer im Hinblick auf Microsoft Teams zu unterstützen. Diese Supportseite kann zu einem Kanal in jedem beliebigen Team hinzugefügt werden, um die Schulung von Endbenutzern zu erleichtern.

Nachstehend finden Sie eine Übersicht über die Verwendungsmöglichkeiten von Advisor für Microsoft Teams zusammen mit Lernpfaden.

### <a name="get-started-in-learning-pathways"></a>Erste Schritte mit Lernpfaden

Um mit der Nutzung von Lernpfaden loszulegen, sehen Sie sich [Erste Schritte mit Lernpfaden](/office365/customlearning/) an.

Wenn Sie eine neue Lernpfadlösung in Ihrer Umgebung einrichten möchten, finden Sie diesbezügliche Informationen unter [Bereitstellen einer neuen Lernpfadlösung](/office365/customlearning/custom_provision).

### <a name="create-a-learning-plan"></a>Erstellen eines Schulungsplans

#### <a name="plan-your-learning-content"></a>Planen von Schulungsinhalten

Bevor Sie die Website in den Lernpfaden erstellen, nehmen Sie sich etwas Zeit, um sich die Ihnen zur Verfügung stehenden Schulungsressourcen und Features anzusehen und zusammenzuführen. Mit Lernpfaden können Sie Inhalte der Microsoft 365-Schulungsseite verwenden und von Ihnen erstellte Inhalte hinzufügen, um die Website an Ihre individuellen Anforderungen anzupassen.

Weitere Informationen hierzu finden Sie unter [Planen von Lernpfadinhalten](/office365/customlearning/custom_plancontent) und [Ressourcen zur Unterstützung von Remotemitarbeitern](/office365/customlearning/custom_plancontent_remoteresources).

#### <a name="explore-teams-content-in-learning-pathways"></a>Erkunden von Microsoft Teams-Inhalten in Lernpfaden

Lernpfade stellen eine SharePoint-Website mit einem Webpart bereit, das mit einem Online-Katalog verbunden ist. Auf der Microsoft 365-Schulungsseite, die das Webpart hostet, werden alle in Lernpfaden verfügbaren Schulungen aufgeführt. Schauen Sie sich um, um sich mit den verfügbaren Ressourcen und der Strukturierung der Inhalte vertraut zu machen.

[Wechseln Sie zu Ihrer Lernpfade-Website](/office365/customlearning/custom_goto), wählen Sie **Microsoft 365-Schulung** und dann **Microsoft Teams** aus, um alle im Online-Katalog verfügbaren Wiedergabelisten für Microsoft Teams-Schulungen anzuzeigen. Wählen Sie eine Wiedergabeliste aus und klicken Sie dann auf **Nächste** und **Vorherige**, um sie zu durchlaufen. Sie können auch auf den nach unten zeigenden Pfeil klicken, um die Inhalte einer Wiedergabeliste anzuzeigen und zu einem bestimmten Thema zu wechseln.

#### <a name="take-an-inventory-of-teams-learning-resources-in-your-organization"></a>Erstellen eines Inventars an Microsoft Teams-Schulungsressourcen in Ihrer Organisation

Überprüfen Sie die Microsoft Teams-Schulungsinhalte, die in Ihrer Organisation bereits verfügbar sind. Möglicherweise haben Sie zum Beispiel bereits benutzerdefinierte Onboarding-, Schulungs- oder Supportinhalte für Microsoft Teams erstellt. Ihre bestehenden SharePoint-Ressourcen können mit Microsoft-Inhalten in einer Wiedergabeliste zusammengeführt werden, um eine maßgeschneiderte Wiedergabeliste für Ihre Organisation zu erstellen.

#### <a name="build-your-site-in-learning-pathways"></a>Erstellen Ihrer Website in Lernpfaden

Das [Admin Success Center](/office365/customlearning/custom_successcenter) in Lernpfaden stellt Anleitungen und Ressourcen bereit, die Ihnen beim Planen und Anpassen von Lernpfaden in Ihrer Organisation helfen. Erfahren Sie, wie Sie die [Website anpassen](/office365/customlearning/custom_overview) können, Inhalte anzeigen und ausblenden, benutzerdefinierte Wiedergabelisten erstellen und vieles mehr.

Auf das Admin Success Center können Sie über **Admin Success Center** auf der Lernpfade-Homepage zugreifen.

#### <a name="add-your-site-to-teams"></a>Hinzufügen Ihrer Website zu Microsoft Teams

Wenn Ihre Website fertig ist, fügen Sie sie zu einem Kanal in einem beliebigen Team hinzu, damit schnell und einfach darauf zugegriffen werden kann.

1. Wechseln Sie in Microsoft Teams zum gewünschten Team, und wählen Sie dann einen Kanal aus.
2. Wählen Sie oben auf der Kanalseite **+** aus (**Registerkarte hinzufügen**) aus.
3. Wählen Sie **SharePoint-Seiten** und dann **Seite von einer SharePoint-Website hinzufügen** aus.
4. Fügen Sie die URL Ihrer Lernpfade-Website ein, und wählen Sie dann **Speichern** aus.

Weitere Informationen hierzu finden Sie unter [Eine SharePoint-Seite oder -Liste zu einem Kanal in Microsoft Teams hinzufügen](https://support.microsoft.com/office/add-a-sharepoint-page-or-list-to-a-channel-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b).

### <a name="train-your-support-team"></a>Schulung Ihres Supportteams

Verwenden Sie die Ressourcen auf Ihrer Lernpfade-Website, um Ihren Helpdesk und Ihre Experten in Microsoft Teams einzuführen. Statten Sie sie mit den Tools und Informationen aus, die sie benötigen, um Ihre Benutzer in Microsoft Teams zu unterstützen.

Anleitungen und Ressourcen zur Vorbereitung Ihres Helpdesks und Ihrer Experten auf Microsoft Teams finden Sie unter [Schulung Ihrer Organisation](https://adoption.microsoft.com/microsoft-teams/#train-your-org) und [Experten ausbilden](https://adoption.microsoft.com/microsoft-teams/#build-champions).

Als Ansprechpartner für Ihre Benutzer bei Fragen zur Nutzung können Ihr Helpdesk und Ihre Experten die Lernpfade verwenden, um Benutzer zu schulen sowie als Alternative zur Erstellung von Support-Tickets. Ermutigen Sie Ihren Helpdesk und Ihre Experten, [Ihre Lernpfade-Website anzupassen](/office365/customlearning/) durch die Erstellung einer Schulungs- und Supportseite, und sie dann in einem Team [als Registerkarte zu einem Kanal hinzuzufügen](#add-your-site-to-teams), damit die Benutzer selbst nach den erforderlichen Informationen suchen können.

### <a name="drive-adoption"></a>Fördern der Einführung

Nach der Anpassung Ihrer Website und dem Zusammenstellen ihrer Schulungspläne sollten Sie sich Gedanken darüber machen, wie Sie Ihre Benutzer zur Nutzung der Lernpfade für die kontinuierliche Schulung anregen können.

Verwenden Sie Ihre Kommunikationskanäle, um die Website bekannt zu machen und die Aufmerksamkeit der Benutzer auf sie zu lenken. Verwenden Sie beispielsweise in Ihren Mitteilungen einen Standardslogan wie "Erfahren Sie auf unserer Schulungs- und Supportwebsite, wie Sie mit Microsoft Teams noch produktiver werden können".

Wecken Sie das Interesse der Benutzer, indem Sie hervorheben, wie sie in Microsoft Teams zusammenarbeiten können, und leiten Sie sie dann zur Lernpfade-Website weiter, wo sie Genaueres dazu erfahren.

Schauen Sie sich diese Ressourcen an, die Leitfäden, Einführungspakete, bewährte Methoden und mehr umfassen, um Ihnen bei der erfolgreichen Umsetzung eines Rollout- und Einführungsplans zu helfen.  

- [Die Nutzung von Lernpfaden fördern](/office365/customlearning/driveadoption)
- [Microsoft Teams einführen](adopt-microsoft-teams-landing-page.md)
- [Ressourcen für die Einführung von Microsoft Teams](https://adoption.microsoft.com/microsoft-teams/)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="what-are-the-licensing-requirements-for-advisor-for-teams"></a>Welche Lizenzanforderungen gelten für Advisor für Microsoft Teams?

Sie benötigen mindestens Microsoft 365 Business Basic, damit Sie die Vorteile der Integration von Advisor für Teams mit Forms und Planner nutzen können.

### <a name="can-i-delete-the-deployment-team"></a>Kann ich das Bereitstellungsteam löschen?

Nachdem Advisor für Teams Ihr Bereitstellungsteam erstellt hat, können Sie das Team wie jedes andere Team verwalten – einschließlich der Möglichkeit, es zu löschen. Achten Sie darauf, dass das Team im Microsoft Teams Admin Center weiterhin angezeigt wird, wenn es nicht unter Verwendung des Microsoft Teams Admin Center gelöscht wurde.

### <a name="can-i-add-or-remove-channels-in-the-deployment-team"></a>Kann ich im Bereitstellungsteam Kanäle hinzufügen oder entfernen?

Ja, nachdem das Bereitstellungsteam erstellt wurde, können Sie die Kanäle auf die gleiche Weise wie bei jedem anderen Team verwalten.

### <a name="can-i-add-or-remove-project-team-members-in-the-deployment-team"></a>Kann ich im Bereitstellungsteam Projektteammitglieder hinzufügen oder entfernen?

Ja, nachdem das Bereitstellungsteam erstellt wurde, können Sie Projektteammitglieder auf die gleiche Weise wie bei jedem anderen Team verwalten.

### <a name="can-i-modify-the-planner-plans"></a>Kann ich die Planner-Pläne ändern?

Ja, nachdem Advisor für Teams Ihr Bereitstellungsteam erstellt hat, sollten Sie den Planner-Plan so aktualisieren, dass er den Rollout ihrer Teams am besten unterstützt. Sie können alles ändern – Buckets, Aufgaben, Aufgabendetails, – ebenso wie bei jedem anderen Planner-Plan.

### <a name="can-i-modify-the-forms-survey"></a>Kann ich die Forms-Umfrage ändern?

Ja, nachdem Advisor für Teams Ihr Bereitstellungsteam erstellt hat, können Sie die Forms-Umfrage nach Bedarf ändern.

### <a name="are-there-any-differences-between-advisor-for-teams-in-gcc"></a>Gibt es Unterschiede im Hinblick auf Advisor für Teams in GCC?

Ja, Formulare für Benutzerumfragen werden erstellt, aber nicht in Plankanälen angeheftet, da die App Teams Forms in GCC derzeit nicht zur Verfügung steht.

### <a name="what-information-is-advisor-for-teams-collecting-about-my-organization"></a>Welche Daten werden von Advisor für Teams über meine Organisation erfasst?

Advisor für Teams fragt, ob Sie einverstanden sind, dass Daten gesammelt werden, mit denen sich die Identität des Endbenutzers nicht identifizieren lässt. Bei den gesammelten Daten handelt es sich um eine Telemetrie, die Microsoft ein Feedback darüber gibt, wie erfolgreich der Berater für Teams Ergebnisse erzielt und inwieweit er ggf. verbessert werden muss. Diese Daten werden verwendet, um Chancen für Microsoft zu erkennen, sich proaktiv mit Ihrer Organisation zu befassen, um sie bei Ihrer Bereitstellung zu unterstützen.

### <a name="can-i-use-advisor-for-teams-with-fasttrack"></a>Kann ich Advisor für Teams mit FastTrack verwenden?

Ja, FastTrack nutzt Advisor für Teams für alle Kunden, die sich für die Bereitstellung von Teams interessieren. Sie können Ihnen bei der ersten Einrichtung Ihres Bereitstellungsteams über Advisor für Teams (sofern erforderlich) Hilfe anbieten und Sie während des Rollouts von Teams nach Bedarf bei spezifischen Themen unterstützen.

### <a name="can-i-use-advisor-for-teams-with-a-partner"></a>Kann ich Advisor für Teams mit einem Partner verwenden?

Ja, Sie können Advisor für Teams verwenden und gleichzeitig einen Bereitstellungspartner für Ihre Teams-Bereitstellung verwenden. Wenn Ihr Partner ein CSP ist und Ihren Mandanten in Ihrem Auftrag verwaltet, kann er Advisor für Teams verwenden, um Ihr Bereitstellungsteam zu erstellen und Sie bei der Durchführung des Gesamtprojekts zu unterstützen. Darüber hinaus können Sie mit einem beliebigen Partner zusammenarbeiten, indem Sie diese Personen als Gäste Ihrem Bereitstellungsteam hinzufügen, damit sie als Mitglieder des Gesamtprojektteams teilnehmen können.

### <a name="how-do-i-use-planner"></a>Wie verwende ich Planner?

Schauen Sie sich die [Microsoft Planner-Hilfeseite](https://support.office.com/article/Microsoft-Planner-help-4a9a13c6-3adf-4a60-a6fc-15c0b15e16fc) und die [Planner-Schnellstartvideos](https://support.office.com/article/microsoft-planner-video-training-4d71390f-08d8-4db0-84ea-92fb078687c7) an.

### <a name="how-do-i-use-forms"></a>Wie verwende ich Forms?

Wechseln Sie zum [Forms-Hilfecenter](https://support.office.com/forms).

## <a name="related-topics"></a>Verwandte Themen

[Anpassen von Advisor für Teams](/office365/customlearning/custom_teamsadvisor)

[Bereitstellen von Teams](./deploy-overview.md)

[Bewährte Methoden zum Organisieren von Teams in Microsoft Teams](best-practices-organizing.md)

[Produktnamen und Serviceplanbezeichner für die Lizenzierung](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
