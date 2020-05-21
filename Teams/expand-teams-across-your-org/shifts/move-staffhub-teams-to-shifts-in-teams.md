---
title: Verschieben der StaffHub-Teams in Schichten
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu, gumariam
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Ihre Microsoft StaffHub-Teams verschieben und Daten in Microsoft Teams in Schichten planen können.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- SPO_Content
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e0bf24c32854ddf2498b8a00874ad1d358c8fb8a
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326792"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Verschieben Ihrer Microsoft StaffHub-Teams in die Schichten in Microsoft Teams

> [!IMPORTANT]
> Am 31. Dezember 2019 wird Microsoft StaffHub eingestellt. Wir erstellen StaffHub-Funktionen in Microsoft Teams. Heute umfasst Microsoft Teams die App "Schichten" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub wird am 31. Dezember 2019 für alle Benutzer eingestellt. Jedem Benutzer, der StaffHub zu öffnen versucht, wird eine Meldung angezeigt, die ihn zum Microsoft Teams-Download leitet. Weitere Informationen finden Sie unter [Microsoft StaffHub wird eingestellt](microsoft-staffhub-to-be-retired.md).

Die Schicht-app in Teams bietet einen einfachen Ansatz für die Verwaltung von Zeitplänen und den konstanten Fluss von Schicht-Swaps und-Abbrüchen, die täglich auftreten. Team Mitglieder können auf Ihre Plan-und Schicht Informationen direkt in der APP und auf Ihren Geräten zugreifen, um Ihre Einstellungen festzulegen, ihre Zeitpläne zu verwalten und die Freizeit zu beantragen.

In diesem Artikel erfahren Sie, wie Sie die StaffHub-Teams Ihrer Organisation verschieben und Daten in Teams verschieben können. Sie umfasst:

- [Was Sie über den Umzug in Teams wissen müssen](#what-you-need-to-know-about-the-move-to-teams)
- [Vorbereiten](#prepare)
- [Durchführen eines Pilotprojekts](#conduct-a-pilot) 
- [Gehen Sie über ihr Pilotprojekt hinaus und verschieben Sie alle StaffHub-Teams.](#go-beyond-your-pilot-and-move-all-staffhub-teams)
- [Überwachen der Verwendung von Teams](#monitor-teams-usage)
- [Problembehandlung](#troubleshooting)

Ganz gleich, ob Sie ein kleines Unternehmen mit einem oder zwei StaffHub-Teams oder einem Großunternehmen mit Hunderten von StaffHub-Teams sind, hier finden Sie die Administratoranleitung, die Sie benötigen, um den Übergang zu Teams erfolgreich zu gestalten.

Sie müssen ein globaler Administrator sein, um die in diesem Artikel beschriebenen Schritte ausführen zu können. Wenn Sie dies noch nicht getan haben, schauen Sie sich die [FAQ zu StaffHub Retirement](microsoft-staffhub-to-be-retired.md) an, um Antworten auf Ihre Fragen zu erhalten.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Was Sie über den Umzug in Teams wissen müssen

### <a name="when-to-move-to-teams"></a>Zeitpunkt für den Wechsel zu Teams

StaffHub wird im Dezember 31, 2019, eingestellt. Wir empfehlen Ihnen, die Verwendung von Teams noch heute zu verwenden und zu beginnen, die Teams und Benutzer Ihrer Organisation aus StaffHub zu wechseln. Da die Zeitplanverwaltung das am häufigsten verwendete Feature in StaffHub ist, empfehlen wir, dass Sie die app "Schichten" in Teams verwenden, die sich weiter bewegen.

### <a name="what-is-moved-to-teams"></a>Was wird in Teams verschoben?

Wenn Sie ein StaffHub-Team verschieben, werden Teammitgliedschaft, Benutzer Details, Team Zeitpläne und Chatdaten in Teams verschoben. Dateien werden nicht verschoben, wenn Sie ein StaffHub-Team verschieben. Wenn ein StaffHub-Team Dateien enthält, die Sie auch in Teams verschieben möchten, verschieben Sie die Dateien in einem separaten Schritt.

Jedes StaffHub-Team benötigt eine entsprechende Office 365-Gruppe. Wenn ein StaffHub-Team einer Office 365-Gruppe zugeordnet ist, bleibt die Datenschutzeinstellung der Gruppe erhalten, wenn Sie das Team verschieben. Wenn einem StaffHub-Team keine Office 365-Gruppe zugeordnet ist, wird automatisch eine Gruppe mit privater Privatsphäre-Einstellung erstellt, um den Übergang zu unterstützen.  Angesichts der Unterschiede bei der Team-und Gruppenbenennung zwischen Teams und StaffHub wird möglicherweise in Teams ein anderer Teamname angezeigt. 

Wenn Sie Teams von StaffHub in Teams umstellen, haben die Benutzer keinen Zugriff mehr auf ihre Zeitpläne in StaffHub und werden an Schichten in Teams umgeleitet. Wir empfehlen, dass Sie diese Änderung in Ihrer Organisation übermitteln, um Unterbrechungen zu minimieren und Benutzer zu ermutigen, Teams zu übernehmen und zu erkunden. Wenn Sie über Azure AD Premium verfügen, können Sie [einen Bericht ausführen](run-report-to-show-staffhub-usage.md) , um eine Liste der StaffHub-Benutzer in Ihrer Organisation abzurufen, die über diese Änderung Bescheid wissen müssen.  

Nachdem Sie ein StaffHub-Team in Teams verschoben haben, gibt es keine Rollback-Option.

### <a name="user-experience-when-you-move-a-team"></a>Benutzererfahrung beim Verschieben eines Teams

Es gibt minimale Ausfallzeiten (wenn überhaupt keine Sekunde) für Benutzer, wenn Ihr Team von StaffHub zu Schichten in Teams gewechselt hat. Benutzer können StaffHub weiterhin verwenden, bis der Wechsel zu Teams abgeschlossen ist. Nach Abschluss des Umzugs wird den Teammitgliedern eine Meldung angezeigt, in der Sie darüber informiert werden, dass Sie die Verwendung von Schichten in Teams für den Zugriff auf Ihren Team Zeitplan benötigen. Nachfolgend finden Sie ein Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Teams verschoben wurde.

![Beispiel für die Meldung, die Benutzern angezeigt wird.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Teams verschoben wurde")

## <a name="prepare"></a>Vorbereiten

Hier erfahren Sie, wie Sie sich auf den Umzug in Teams vorbereiten.

### <a name="check-that-prerequisites-are-met"></a>Überprüfen, ob Voraussetzungen erfüllt sind

Bevor Sie ein StaffHub-Team in Teams verschieben, stellen Sie Folgendes sicher:

- Der angemeldete Benutzer ist ein globaler Administrator.
- Teams ist für alle Benutzer im Mandanten aktiviert.
- Die Erstellung von Microsoft 365-Gruppen ist im Mandanten aktiviert.
- Die teamStaffHub ist gültig.
- Das StaffHub-Team verfügt über mindestens einen Teambesitzer.
- Das StaffHub-Team enthält Mitglieder.
- Alle StaffHub-Teammitglieder sind mit einem Azure AD-Konto verknüpft.
- Allen Mitgliedern des StaffHub-Teams wird eine Teams-Lizenz zugewiesen.  

Wenn diese Voraussetzungen nicht erfüllt werden, schlägt die Verschiebungsanforderung fehl.

### <a name="assign-teams-licenses"></a>Zuweisen von Teams-Lizenzen

Jeder Benutzer muss über eine aktive Microsoft 365-oder Office 365-Lizenz für [einen berechtigten Plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) verfügen und muss eine Teams-Lizenz zugewiesen werden. Wenn Sie Benutzern eine Teams-Lizenz zuweisen, erhalten Sie Zugriff auf Teams.

Sie verwalten die Lizenzen für Teams im Microsoft 365 Admin Center. Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft Teams](../../user-access.md).

> [!NOTE]
> Wenn Ihre Organisation Skype for Business verwendet und Sie nicht bereit sind, alle Ihre Benutzer in Teams zu verschieben, können Sie Teams für Ihre Mitarbeiter in der First-work-Abteilung aktivieren, die dann Teams neben Skype for Business ausführen können. In diesem Koexistenzmodus, dem sogenannten " *Inseln*", fungiert jede Client-App als separate Lösung. Weitere Informationen finden Sie Untergrund [Legendes zu Teams und zur Koexistenz und Interoperabilität von Skype for Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="install-the-prerelease-version-of-the-staffhub-powershell-module"></a>Installieren der Vorabversion des StaffHub PowerShell-Moduls

Wenn Sie dies noch nicht getan haben, [Installieren Sie die Vorabversion des StaffHub PowerShell-Moduls](install-the-staffhub-powershell-module.md).

Sie müssen die Vorabversion des Moduls installiert haben, um Ihre StaffHub-Teams in Teams zu verschieben.

### <a name="link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one"></a>Verknüpfen eines Azure AD-Kontos für StaffHub-Teammitglieder, die nicht über ein Konto verfügen

Jedes StaffHub-Teammitglied muss mit einem Azure Active Directory-Konto (Azure AD) verknüpft sein. Benutzer in Ihrer Organisation werden nicht mit einem Azure AD-Konto verknüpft, wenn eines der folgenden Szenarien zutrifft:

- Ein Teambesitzer hat einen Benutzer hinzugefügt, der kein Azure AD-Konto hat.
- Ein Teambesitzer hat einen Benutzer zu einem StaffHub-Team eingeladen, und dieser Benutzer hat die Einladung nicht akzeptiert.

Diese Benutzer haben inaktive Konten und zeigen den Benutzerstatus unbekannt, eingeladen oder InviteRejected. Sie können ein Azure AD-Konto für diese Benutzer verknüpfen.  Vorgehensweise.

#### <a name="get-a-list-of-all-inactive-accounts-on-staffhub-teams"></a>Abrufen einer Liste aller inaktiven Konten in StaffHub-Teams

Führen Sie die folgende Reihe von Befehlen aus, um eine Liste aller inaktiven Konten in StaffHub Teams abzurufen und die Liste in eine CSV-Datei zu exportieren. Jeder Befehl sollte separat ausgeführt werden.

```PowerShell
$InvitedUsersObject = @()

$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] = $StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }

foreach($team in $StaffHubTeams[0])
{ 
    Write-host $team.name
    $StaffHubUsers = Get-StaffHubMember -TeamId $team.Id | where {$_.State -eq "Invited"}
    foreach($StaffHubUser in $StaffHubUsers) {
        $InvitedUsersObject  += New-Object PsObject -Property @{
          "TeamID"="$($team.Id)"
          "TeamName"="$($team.name)"
          "MemberID"="$($StaffHubUser.Id)"
            }
    }
}

$InvitedUsersObject | SELECT * | export-csv InvitedUsers.csv -NoTypeInformation  
```

#### <a name="link-the-account"></a>Verknüpfen des Kontos

Führen Sie einen der folgenden Schritte aus:

- Konvertieren und Verknüpfen des Kontos

  StaffHub-Teambesitzer und-Manager können ein inaktives Konto konvertieren und es mit einem Azure AD-Konto in StaffHub verknüpfen, indem Sie die e-Mail-Adresse des Benutzers in einen gültigen UPN auf der Seite "StaffHub-Team Einstellungen" ändern.

- Entfernen Sie das Konto, das nicht verknüpft ist, und fügen Sie es dann mithilfe des UPN erneut hinzu.
    1. Führen Sie das Cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubMember?view=staffhub-ps) aus, um das nicht bereitgestellte Konto aus dem StaffHub-Team zu entfernen.
    2. Führen Sie das [Add-StaffHubMember-](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) Cmdlet aus, um das Konto mithilfe des UPN dem StaffHub-Team wieder hinzuzufügen.

- Entfernen des inaktiven Kontos Verwenden Sie diese Option, wenn das Benutzerkonto nicht mehr benötigt wird.

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Zuweisen der FirstlineWorker-App-Setup Richtlinie zu Benutzern

Teams umfasst eine integrierte Richtlinie für die FirstlineWorker-APP, die Sie zum Anpassen von Teams verwenden können, um die apps hervorzuheben, die für die ersten Mitarbeiter in Ihrer Organisation am wichtigsten sind. Wenn Sie diese Richtlinie Benutzern zuweisen, werden die apps in der Richtlinie in Teams an die APP-Leiste angeheftet, damit Sie schnell und einfach darauf zugreifen können. Andere apps, die zu Teams hinzugefügt wurden, finden Sie in der APP-Leiste, indem Sie auf **... Weitere apps** in den Teams-Desktop-und Webclients und durch wischen im mobilen Team-Client. Standardmäßig umfasst die FirstlineWorker-App-Setup Richtlinie die Aktivitäten, Schichten, Chats und Anruf-apps.

Eine schrittweise Anleitung zum Zuweisen der FirstlineWorker-App-Setup Richtlinie für Benutzer finden Sie unter [Verwenden der FirstlineWorker-App-Setup Richtlinie zum Anheften von Schichten an Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams). Nachdem Sie eine Richtlinie zugewiesen haben, kann es einige Stunden dauern, bis Sie wirksam wird.

Wir empfehlen, diesen Schritt mindestens eine Woche abzuschließen, bevor Sie Ihre StaffHub-Teams und-Benutzer in Teams verschieben. Wenn Benutzer in Teams angemeldet sind, vergewissern Sie sich, dass Sie die Schicht-App anzeigen und darauf zugreifen können.

Sie können auch benutzerdefinierte App-Setup Richtlinien erstellen und die Einstellungen in der globalen App-Setup Richtlinie bearbeiten. Weitere Informationen finden Sie unter [Verwalten von App-Setup Richtlinien in Teams](../../teams-app-setup-policies.md).

### <a name="onboard-users-to-teams"></a>Onboard-Benutzer für Teams

Stellen Sie im Rahmen ihrer Onboarding-Strategie Schulungen und Anleitungen für Benutzer bereit, die Ihnen helfen, sich mit Teams vertraut zu machen. Geben Sie die folgenden Ressourcen für die Benutzer frei, damit Sie wissen, wo Sie Teams-Clients, Schulungen und Support erhalten:

- [Teams-Webclient](https://teams.microsoft.com)
- [Downloadlinks für Desktop- und mobile Clients](https://teams.microsoft.com/downloads)
- [Teams-Schulungsvideos](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Teams-Hilfedokumentation](https://support.office.com/teams)

Anleitungen zum Bereitstellen von Teams und zur Einführung von Teams finden Sie unter so wird es [gemacht: Rollout von Teams](../../How-to-roll-out-teams.md) und über [nehmen von Teams](../../adopt-microsoft-teams-landing-page.md).

## <a name="conduct-a-pilot"></a>Durchführen eines Pilotprojekts

Wir empfehlen, dass Sie zunächst zwei oder drei StaffHub-Teams für eine ausgewählte Gruppe von Early Adopters verschieben. Durch das Ausführen eines Pilotprojekts können Sie Ihren Übergangsplan verfeinern und sicherstellen, dass Sie bereit sind, alle StaffHub-Teams Ihrer Organisation in Teams zu verschieben. Es werden auch Champions identifiziert, die Ihnen bei der Einführung in Ihrer Organisation behilflich sein können. Wenn Sie ein kleines Unternehmen sind, das keinen Phasen orientierten Ansatz benötigt, sind die Schritte in diesem Abschnitt möglicherweise alles, was Sie benötigen, um von StaffHub zu Teams zu wechseln.

### <a name="identify-pilot-teams"></a>Ermitteln von Pilot Teams

Erreichen Sie zwei oder drei Pilot Teams. Alle Teammitglieder sollten sich verpflichten, mithilfe von Schichten in Teams ihre Zeitpläne zu verwalten und miteinander zu kommunizieren und zusammenzuarbeiten.

### <a name="identify-team-champions"></a>Identifizieren von Team Champions

Ermitteln Sie Champions in Pilot Teams, und geben Sie Sie zur Evangelisierung von Schichten ein. Team-Champions sind leidenschaftlich über das, was Sie tun, indem Sie Ihre eigenen Erfahrungen austauschen, um den Teammitgliedern Support und Hilfestellung zu bieten. Team Champions können Teambesitzer oder Manager sein.

Team-Champions sollten sicherstellen, dass die Teammitglieder eingerichtet werden, indem Sie Zeit für jeden einrichten, um [Teams-Clients zu erhalten](../../get-clients.md), sich bei Teams anzumelden und deren Zeitpläne in Schichten zu überprüfen und mit anderen zu chatten. Benutzer, die bereits mit StaffHub vertraut sind, werden in Schichten schnell in Betrieb sein. Sie können auch auf die [Schalt Schicht Hilfe](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) verweisen, um weitere Hilfe zu erhalten.

### <a name="move-a-staffhub-team"></a>Verschieben eines StaffHub-Teams

Führen Sie die folgenden Schritte aus, um ein StaffHub-Team gleichzeitig zu verschieben. Wir empfehlen diesen Ansatz für Ihre Pilot Teams. Wenn Sie zu einem späteren Zeitpunkt alle StaffHub-Teams Ihrer Organisation verschieben möchten, lesen Sie [Verschieben von StaffHub Teams](#move-your-staffhub-teams) nach Schritten zum Verschieben mehrerer Teams.

Führen Sie die folgenden Schritte aus, um ein StaffHub-Team zu verschieben.

```PowerShell
Move-StaffHubTeam -TeamId <String>
```
Beispiel:

```PowerShell
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Im folgenden finden Sie ein Beispiel für die Antwort, die Sie erhalten, wenn Sie eine Anfrage einreichen, um ein StaffHub-Team in Teams zu verschieben.

```console
 jobId                                      teamId                                      teamAlreadyInMicrosofteams  
---------------------------------------    ----------------------------------------    ---------------------------          
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Führen Sie die folgenden Schritte aus, um den Status einer Verschiebungsanforderung zu überprüfen.

```PowerShell
Get-TeamMigrationJobStatus <String>
```
Beispiel:

```PowerShell
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

Im folgenden finden Sie ein Beispiel für die Antwort, die Sie erhalten, wenn ein Schritt ausgeführt wird.

```console
jobId                                     status       teamId                                     isO365GroupCreated  Error
----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>Verschieben von Dateien aus einem StaffHub-Team in Teams

Dieser Schritt gilt nur, wenn das StaffHub-Team, das Sie in Teams verschoben haben, Dateien enthält, die Sie auch in Teams verschieben möchten. Sie können Dateien direkt in SharePoint Online oder mithilfe von PowerShell verschieben.

#### <a name="in-sharepoint-online"></a>In SharePoint Online

Informationen finden Sie unter [Verschieben von Dateien in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).

#### <a name="using-powershell"></a>Verwendung von PowerShell

Laden Sie die [SharePoint Online-Verwaltungsshell](https://www.microsoft.com/download/details.aspx?id=35588)herunter, und installieren Sie Sie, falls noch nicht geschehen. Sie enthält die Cmdlets, die Sie zum Verschieben von Dateien benötigen.  

Verwenden Sie das Cmdlet [Connect-PnPOnline](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) zum Herstellen einer Verbindung mit der SharePoint Online-Teamwebsite.

```PowerShell
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

Verwenden Sie für jede Datei, die Sie von StaffHub in Teams verschieben möchten, das Cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile) , um die Datei zu verschieben.

```PowerShell
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

Wenn Sie mehrere Dateien verschieben möchten, durchlaufen Sie die Dateien, und führen Sie den zweiten Befehl auf der Schleife aus. Sie müssen den ersten Befehl nicht wiederholen, wenn die Sitzung aktiv bleibt.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>Gehen Sie über ihr Pilotprojekt hinaus und verschieben Sie alle StaffHub-Teams.

### <a name="raise-awareness"></a>Sensibilisieren

Wenn Sie bereit sind, über Ihre Pilot Teams hinauszugehen und die StaffHub-Teams Ihrer Organisation in Teams zu verschieben, ist es wichtig, zunächst die Änderung in Ihrer Organisation zu kommunizieren. Informieren Sie sich über Schichten und den Übergang zu Teams, um das Bewusstsein zu schärfen, Spannung zu wecken und die Akzeptanz zu steigern.

### <a name="move-your-staffhub-teams"></a>Verschieben Ihrer StaffHub-Teams

Führen Sie die folgenden Schritte aus, um StaffHub Teams massenhaft zu verschieben. Sie können auswählen, ob Sie alle StaffHub-Teams Ihrer Organisation verschieben oder bestimmte StaffHub-Teams verschieben möchten. Wenn Sie StaffHub Teams einzeln verschieben möchten, lesen Sie [Verschieben eines StaffHub](#move-a-staffhub-team)-Teams.

#### <a name="move-all-staffhub-teams"></a>Verschieben aller StaffHub-Teams

Führen Sie die folgenden Schritte aus, um eine Liste aller StaffHub-Teams in Ihrer Organisation abzurufen.

```PowerShell
$StaffHubTeams = Get-StaffHubTeamsForTenant

$StaffHubTeams[0] | Where-Object { $_.ManagedBy -eq 'StaffHub' }
```

Führen Sie dann die folgenden Schritte aus, um alle Teams zu verschieben.

```PowerShell
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

Hier ist ein Beispiel für die Antwort.

Für alle Teams, die bereits in Teams verschoben oder bereits in Teams vorhanden sind, ist die JobID "Null", da ein Auftrag nicht gesendet werden muss, um das Team zu verschieben.

```console
jobId                                      teamId                                      teamAlreadyInMicrosofteams  
----------------------------------------   -----------------------------------------   --------------------------         
null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>Verschieben spezifischer StaffHub Teams

Führen Sie die folgenden Schritte aus, um eine Liste aller StaffHub-Team-IDs in Ihrer Organisation abzurufen.

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Wählen Sie in den Ergebnissen, die von dem `Get-StaffHubteamsForTenant` zuvor ausgeführten Cmdlet zurückgegeben wurden, die Team-IDs aus, die Sie verschieben möchten, und fügen Sie Sie dann einer CSV-Datei (Comma-Separated Values, CSV) hinzu.

Im folgenden finden Sie ein Beispiel dafür, wie die CSV-Datei formatiert werden soll.

|ID  |
|---------|
|TEAM_4bbc03af-c764-497f-A8A5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Nachdem Sie die CSV-Datei erstellt haben, führen Sie die folgenden Schritte aus, um die in der CSV-Datei angegebenen Teams zu verschieben.

```PowerShell
$StaffHubTeams = Import-Csv .\teams.csv

foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>Überprüfen, ob Ihre StaffHub-Teams in Teams umgezogen sind

Führen Sie die folgenden Schritte aus, um eine Liste aller Teams in Schichten in Ihrer Organisation abzurufen. 

```PowerShell
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>Verschieben von Dateien aus ihren StaffHub-Teams in Teams

Wenn die von Ihnen verschobenen StaffHub-Teams Dateien enthalten, die Sie auch in Teams verschieben möchten, lesen Sie [Verschieben von Dateien aus einem StaffHub-Team in Teams](#move-files-from-a-staffhub-team-to-teams).

## <a name="monitor-teams-usage"></a>Überwachen der Verwendung von Teams

Verwendungsberichte können Ihnen dabei helfen, Nutzungsmuster besser zu verstehen und Ihnen Einblicke zu geben, wo Sie die Schulungs-und Kommunikationsaktivitäten in Ihrer Organisation priorisieren können. Sie können Berichte ausführen, die Ihnen die Verwendung der allgemeinen Teams, die Art der Aktivitäten, die Benutzer in Teams ausführen, die Art und Weise, wie Benutzer eine Verbindung mit Teams herstellen, und vieles mehr. Weitere Informationen finden Sie unter [Teams-Berichterstattung im Microsoft Teams Admin Center](../../teams-analytics-and-reports/teams-reporting-reference.md) und [Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../../teams-activity-reports.md).

## <a name="troubleshooting"></a>Problembehandlung

**So erhalten Sie weitere Informationen zu Fehler Fehlern**

Führen Sie die folgenden Schritte aus, um weitere Informationen zu Fehler Fehlern zu erhalten, die auftreten, wenn Sie versuchen, ein Team zu verschieben:

```PowerShell
Move-StaffHubTeam -TeamId <TeamId>

$res = Get-TeamMigrationJobStatus -JobId <JobId>

$res.Status
```

Es wird einer der folgenden Status angezeigt: Erfolg, Fehler, InProgress, in der Warteschlange.

Wenn "Fehler" zurückgegeben wird, führen Sie die folgenden Schritte aus, um weitere Informationen zum Fehler zu erhalten:

```PowerShell
$res.Result.Error.Innererror
```

**Wenn Sie versuchen, ein StaffHub-Team zu verschieben, wird der Status als "Fehler" angezeigt, und Sie erhalten die Fehlermeldung "Fehler beim Abrufen anwendbarer SKU-Kategorien für den Benutzer".**

Dies kann auftreten, wenn mindestens ein Teammitglied keine Teams-Lizenz besitzt. Wechseln Sie zu Portal.Office.com, suchen Sie die Gruppe, und bestätigen Sie, dass Gruppenmitgliedern eine Teams-Lizenz zugewiesen wurde.

**Wenn Sie versuchen, ein StaffHub-Team zu verschieben, wird der Status als "Fehler" angezeigt, und Sie erhalten die Fehlermeldung "Teambesitzer nicht gefunden".**

Dies kann auftreten, wenn die Gruppe, die dem StaffHub-Team zugeordnet ist, keinen Teambesitzer hat. Wechseln Sie zu Portal.Office.com, suchen Sie die Gruppe, und fügen Sie dann einen oder mehrere Besitzer zur Gruppe hinzu.

**Wenn Sie versuchen, Dateien von StaffHub in Teams zu verschieben, erhalten Sie die Fehlermeldung "Berechtigung verweigert".**

Dies kann auftreten, wenn Sie versuchen, Dateien in einer privaten Office 365-Gruppe zu verschieben, in der Sie nicht Mitglied sind. Wenn dies der Fall ist, verwenden Sie das [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember) -Cmdlet, um sich selbst dem StaffHub-Team hinzuzufügen, und verschieben Sie dann die Dateien. Nachdem Sie die Dateien verschoben haben, verwenden Sie das Cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember) , um sich selbst aus dem Team zu entfernen. 

**Wenn Sie versuchen, Dateien aus StaffHub in Teams zu verschieben, erhalten Sie eine Fehlermeldung, die besagt, dass der Ordner "Allgemein" nicht vorhanden ist.**

Führen Sie den folgenden Befehl aus, um den Ordner "Allgemein" zu SharePoint hinzuzufügen, und versuchen Sie es dann erneut:

  ```PowerShell
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>Verwandte Themen
- [Bereitstellen von Microsoft Teams](../../How-to-roll-out-teams.md)
- [Microsoft StaffHub soll eingestellt werden](microsoft-staffhub-to-be-retired.md)
- [Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub PowerShell-Referenz](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
