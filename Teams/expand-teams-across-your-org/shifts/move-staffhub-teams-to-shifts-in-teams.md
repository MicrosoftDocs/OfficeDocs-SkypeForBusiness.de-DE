---
title: Verschieben Ihrer StaffHub-Teams in Schichten in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 3/29/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre Microsoft StaffHub-Teams verschieben und Daten in Microsoft Teams in Schichten planen können.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b6354c2edd4d8504aeb2c84715b982f6bf793d33
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548294"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Verschieben Ihrer Microsoft StaffHub-Teams in die Schichten in Microsoft Teams

> [!IMPORTANT]
> Ab dem 1. Oktober 2019 wird Microsoft StaffHub eingestellt. Wir erstellen StaffHub-Funktionen in Microsoft Teams. Heute umfasst Teams die Schicht-App für die Terminplanung, und zusätzliche Funktionen werden im Laufe der Zeit bereitgestellt. StaffHub wird für alle Benutzer am 1. Oktober 2019 nicht mehr funktionieren. Jede Person, die versucht, StaffHub zu öffnen, wird eine Meldung angezeigt, die Sie zum Herunterladen von Teams anweist. Weitere Informationen finden Sie unter [Microsoft StaffHub](microsoft-staffhub-to-be-retired.md).

> Die in diesem Artikel beschriebene Funktion wurde noch nicht veröffentlicht. Es wurde angekündigt, und wird in Kürze, Anfang Juni 2019. Wenn Sie ein Administrator sind, können Sie herausfinden, wann dies im Nachrichtencenter (im [Microsoft 365 Admin Center](https://portal.office.com/adminportal/home)) verfügbar ist.

Die Schicht-app in Teams bietet einen einfachen Ansatz für die Verwaltung von Zeitplänen und den konstanten Fluss von Schicht-Swaps und-Abbrüchen, die täglich auftreten. Team Mitglieder können auf Ihre Plan-und Schicht Informationen direkt in der APP und auf Ihren Geräten zugreifen, um Ihre Einstellungen festzulegen, ihre Zeitpläne zu verwalten und die Freizeit zu beantragen.

In diesem Artikel erfahren Sie, wie Sie die StaffHub-Teams Ihrer Organisation verschieben und Daten in Teams verschieben können. Ganz gleich, ob Sie ein kleines Unternehmen mit einem oder zwei StaffHub-Teams oder einem Großunternehmen mit Hunderten von StaffHub-Teams sind, hier finden Sie die Administratoranleitung, die Sie benötigen, um den Übergang zu Teams erfolgreich zu gestalten.

Sie müssen ein globaler Administrator sein, um die in diesem Artikel beschriebenen Schritte ausführen zu können. Wenn Sie dies noch nicht getan haben, schauen Sie sich die [FAQ zu StaffHub Retirement](microsoft-staffhub-to-be-retired.md) an, um Antworten auf Ihre Fragen zu erhalten. 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Was Sie über den Umzug in Teams wissen müssen

### <a name="when-to-move-to-teams"></a>Zeitpunkt für den Wechsel zu Teams

Ab dem 1. Oktober 2019 wird StaffHub eingestellt. Wir empfehlen Ihnen, die Verwendung von Teams noch heute zu verwenden und zu beginnen, die Teams und Benutzer Ihrer Organisation aus StaffHub zu wechseln. Da die Zeitplanverwaltung das am häufigsten verwendete Feature in StaffHub ist, empfehlen wir, dass Sie die app "Schichten" in Teams verwenden, die sich weiter bewegen.

### <a name="what-is-moved-to-teams"></a>Was wird in Teams verschoben?

Benutzer Details, Zeitplaninformationen sowie Chat-und Dateidaten werden in Teams umgestellt. Dazu gehören Teammitgliedschaft, Team Zeitpläne sowie Chats und Dateien aus den letzten 90 Tagen.

Jedes StaffHub-Team benötigt eine entsprechende Office 365-Gruppe. Wenn einem StaffHub-Team keine Office 365-Gruppe zugeordnet ist, wird automatisch ein für Sie erstellt, um den Übergang zu unterstützen. Angesichts der Unterschiede bei der Team-und Gruppenbenennung zwischen Teams und StaffHub wird möglicherweise in Teams ein anderer Teamname angezeigt.

Wenn Sie Teams von StaffHub in Teams umstellen, haben die Benutzer keinen Zugriff mehr auf ihre Zeitpläne in StaffHub und werden an Schichten in Teams umgeleitet. Wir empfehlen, dass Sie diese Änderung in Ihrer Organisation übermitteln, um Unterbrechungen zu minimieren und Benutzer zu ermutigen, Teams zu übernehmen und zu erkunden. Wenn Sie über Azure AD Premium verfügen, können Sie [einen Bericht ausführen](run-report-to-show-staffhub-usage.md) , um eine Liste der StaffHub-Benutzer in Ihrer Organisation abzurufen, die über diese Änderung Bescheid wissen müssen.  

Nachdem Sie ein StaffHub-Team in Teams verschoben haben, gibt es keine Rollback-Option.

### <a name="user-experience-when-you-move-a-team"></a>Benutzererfahrung beim Verschieben eines Teams

Es gibt minimale Ausfallzeiten (wenn überhaupt keine Sekunde) für Benutzer, wenn Ihr Team von StaffHub zu Schichten in Teams gewechselt hat. Benutzer können StaffHub weiterhin verwenden, bis der Wechsel zu Teams abgeschlossen ist. Nach Abschluss des Umzugs wird den Teammitgliedern eine Meldung angezeigt, in der Sie darüber informiert werden, dass Sie die Verwendung von Schichten in Teams für den Zugriff auf Ihren Team Zeitplan benötigen. Nachfolgend finden Sie ein Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Teams verschoben wurde.

![Beispiel für die Meldung, die Benutzern angezeigt wird.] (../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Teams verschoben wurde")

## <a name="prepare"></a>Vorbereiten

Hier erfahren Sie, wie Sie sich auf den Umzug in Teams vorbereiten.

### <a name="assign-teams-licenses"></a>Zuweisen von Teams-Lizenzen

Jeder Benutzer muss über eine aktive Microsoft 365-oder Office 365-Lizenz für [einen berechtigten Plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) verfügen und muss eine Teams-Lizenz zugewiesen werden. Wenn Sie Benutzern eine Teams-Lizenz zuweisen, erhalten Sie Zugriff auf Teams.

Sie verwalten die Lizenzen für Teams im Microsoft 365 Admin Center. Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs auf Teams](../../user-access.md).

> [!NOTE]
> Wenn Ihre Organisation Skype for Business verwendet und Sie nicht bereit sind, alle Ihre Benutzer in Teams zu verschieben, können Sie Teams für Ihre Mitarbeiter in der First-work-Abteilung aktivieren, die dann Teams neben Skype for Business ausführen können. In diesem Koexistenzmodus, dem sogenannten " *Inseln*", fungiert jede Client-App als separate Lösung. Weitere Informationen finden Sie Untergrund Legendes zu [Teams und zur Koexistenz und Interoperabilität von Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Bereitstellen von Konten für StaffHub-Benutzer, die keine Identität in Azure AD besitzen

Jeder Manager und jedes Teammitglied muss über eine Identität in Azure Active Directory (Azure AD) verfügen. Wenn ein Benutzer noch keine Identität in Azure AD hat, stellen Sie ihm ein Konto bereit. Vorgehensweise:

- StaffHub-Teambesitzer und-Manager können ein Dummy-oder Inaktives Konto konvertieren und mit einem bereitgestellten Konto in StaffHub verknüpfen, indem Sie die e-Mail-Adresse des Benutzers in einen gültigen UPN auf der Seite "StaffHub-Team Einstellungen" ändern.

- Administratoren können die Cmdlets [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) und [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) ausführen, um ein nicht bereitgestelltes Konto aus einem StaffHub-Team zu entfernen und das Konto mithilfe des UPN wieder hinzuzufügen.

### <a name="install-the-staffhub-powershell-module"></a>Installieren des StaffHub PowerShell-Moduls

Wenn Sie dies noch nicht getan haben, [Installieren Sie das StaffHub PowerShell-Modul](install-the-staffhub-powershell-module.md).

Wenn Sie ein StaffHub-Team verschieben, überprüft die Verschiebungsanforderung die Voraussetzungen. Hier sind die Gründe, warum eine Verschiebungsanforderung fehlschlagen kann:

- Der angemeldete Benutzer ist kein globaler Administrator.
- Teams ist für alle Benutzer im Mandanten deaktiviert
- Die Erstellung von Office 365-Gruppen ist im Mandanten deaktiviert
- Die teamStaffHub ist ungültig oder hat keine Mitglieder.
- Das StaffHub-Team enthält Mitglieder, die nicht mit einem Azure AD-Konto verknüpft sind.  

## <a name="run-a-pilot"></a>Führen eines Pilotprojekts

Wir empfehlen, dass Sie zunächst zwei oder drei StaffHub-Teams für eine ausgewählte Gruppe von Early Adopters verschieben. Durch das Ausführen eines Pilotprojekts können Sie Ihren Übergangsplan verfeinern und sicherstellen, dass Sie bereit sind, alle StaffHub-Teams Ihrer Organisation in Teams zu verschieben. Es werden auch Champions identifiziert, die Ihnen bei der Einführung in Ihrer Organisation behilflich sein können. Wenn Sie ein kleines Unternehmen sind, das keinen Phasen orientierten Ansatz benötigt, sind die Schritte in diesem Abschnitt möglicherweise alles, was Sie benötigen, um von StaffHub zu Teams zu wechseln.

### <a name="identify-pilot-teams"></a>Ermitteln von Pilot Teams

Erreichen Sie zwei oder drei Pilot Teams. Alle Teammitglieder sollten sich verpflichten, mithilfe von Schichten in Teams ihre Zeitpläne zu verwalten und miteinander zu kommunizieren und zusammenzuarbeiten.

### <a name="identify-team-champions"></a>Identifizieren von Team Champions

Ermitteln Sie Champions in Pilot Teams, und geben Sie Sie zur Evangelisierung von Schichten ein. Team-Champions sind leidenschaftlich über das, was Sie tun, indem Sie Ihre eigenen Erfahrungen austauschen, um den Teammitgliedern Support und Hilfestellung zu bieten. Team Champions können Teambesitzer oder Manager sein.

Team-Champions sollten sicherstellen, dass die Teammitglieder eingerichtet werden, indem Sie Zeit für jeden einrichten, um [Teams-Clients zu erhalten](../../get-clients.md), sich bei Teams anzumelden und deren Zeitpläne in Schichten zu überprüfen und mit anderen zu chatten. Benutzer, die bereits mit StaffHub vertraut sind, werden in Schichten schnell in Betrieb sein. Sie können auch auf die [Schalt Schicht Hilfe](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) verweisen, um weitere Hilfe zu erhalten.

### <a name="move-a-staffhub-team-coming-soon"></a>Verschieben eines StaffHub-Teams (in Kürze verfügbar)

Führen Sie die folgenden Schritte aus, um ein StaffHub-Team gleichzeitig zu verschieben. Wir empfehlen diesen Ansatz für Ihre Pilot Teams. Wenn Sie zu einem späteren Zeitpunkt alle StaffHub-Teams Ihrer Organisation verschieben möchten, lesen Sie [Verschieben von StaffHub Teams](#move-your-staffhub-teams-coming-soon) nach Schritten zum Verschieben mehrerer Teams.

Führen Sie die folgenden Schritte aus, um ein StaffHub-Team zu verschieben.

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Im folgenden finden Sie ein Beispiel für die Antwort, die Sie erhalten, wenn Sie eine Anfrage einreichen, um ein StaffHub-Team in Teams zu verschieben.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Führen Sie die folgenden Schritte aus, um den Status einer Verschiebungsanforderung zu überprüfen.

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

Im folgenden finden Sie ein Beispiel für die Antwort, die Sie erhalten, wenn ein Schritt ausgeführt wird.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>Durchführen des Übergangs von StaffHub zu Teams

### <a name="raise-awareness"></a>Sensibilisieren

Wenn Sie bereit sind, über Ihre Pilot Teams hinauszugehen und die StaffHub-Teams Ihrer Organisation in Teams zu verschieben, ist es wichtig, zunächst die Änderung in Ihrer Organisation zu kommunizieren. Informieren Sie sich über Schichten und den Übergang zu Teams, um das Bewusstsein zu schärfen, Spannung zu wecken und die Akzeptanz zu steigern.

### <a name="move-your-staffhub-teams-coming-soon"></a>Verschieben Ihrer StaffHub-Teams (in Kürze verfügbar)

Führen Sie die folgenden Schritte aus, um StaffHub Teams massenhaft zu verschieben. Sie können auswählen, ob Sie alle StaffHub-Teams Ihrer Organisation verschieben oder bestimmte StaffHub-Teams verschieben möchten. Wenn Sie StaffHub Teams einzeln verschieben möchten, lesen Sie [Verschieben eines StaffHub](#move-a-staffhub-team-coming-soon)-Teams.

#### <a name="move-all-staffhub-teams-coming-soon"></a>Verschieben aller StaffHub-Teams (in Kürze verfügbar)

Führen Sie die folgenden Schritte aus, um eine Liste aller StaffHub-Teams in Ihrer Organisation abzurufen.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Führen Sie dann die folgenden Schritte aus, um alle Teams zu verschieben.

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

Hier ist ein Beispiel für die Antwort.

Für alle Teams, die bereits in Teams verschoben oder bereits in Teams vorhanden sind, ist die JobID "Null", da ein Auftrag nicht gesendet werden muss, um das Team zu verschieben.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>Verschieben spezifischer StaffHub-Teams (in Kürze verfügbar)

Führen Sie die folgenden Schritte aus, um eine Liste aller StaffHub-Team-IDs in Ihrer Organisation abzurufen.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Wählen Sie in den Ergebnissen, `Get-StaffHubteamsForTenant` die von dem zuvor ausgeführten Cmdlet zurückgegeben wurden, die Team-IDs aus, die Sie verschieben möchten, und fügen Sie Sie dann einer CSV-Datei (Comma-Separated Values, CSV) hinzu.

Im folgenden finden Sie ein Beispiel dafür, wie die CSV-Datei formatiert werden soll.

|ID  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Nachdem Sie die CSV-Datei erstellt haben, führen Sie die folgenden Schritte aus, um die in der CSV-Datei angegebenen Teams zu verschieben.

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>Vergewissern Sie sich, dass Ihre StaffHub-Teams in die Teams umgezogen sind (in Kürze verfügbar)

Führen Sie die folgenden Schritte aus, um eine Liste aller Teams in Schichten in Ihrer Organisation abzurufen. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>Überwachen der Verwendung von Teams

Verwendungsberichte können Ihnen dabei helfen, Nutzungsmuster besser zu verstehen und Ihnen Einblicke zu geben, wo Sie die Schulungs-und Kommunikationsaktivitäten in Ihrer Organisation priorisieren können. Da es sich bei Schichten um eine app in Teams handelt, können Sie die Verwendung über Teams-Berichte anzeigen. Weitere Informationen finden Sie unter [Teams-Berichterstattung im Microsoft Teams Admin Center](../../teams-analytics-and-reports/teams-reporting-reference.md) und [Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../../teams-activity-reports.md).

## <a name="related-topics"></a>Verwandte Themen
- [Microsoft StaffHub soll eingestellt werden](microsoft-staffhub-to-be-retired.md)
- [Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell-Referenz](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
