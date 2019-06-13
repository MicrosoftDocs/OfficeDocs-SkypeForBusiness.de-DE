---
title: Verschieben Ihrer StaffHub-Teams in Shifts in Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Hier erfahren Sie, wie Sie Ihre Microsoft StaffHub-Teams verschieben und in Microsoft Teams Daten in Shifts planen.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: e2e8b0ac4f1c4eb0cce2cae97481fc428f588ec5
ms.sourcegitcommit: 8f9bf1acdcdc2104fa8c343c030d64838e2c31eb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "34780809"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Verschieben Ihrer Microsoft StaffHub-Teams in Shifts in Microsoft Teams

> [!IMPORTANT]
> Am 1. Oktober 2019 wird Microsoft StaffHub eingestellt. Wir bauen StaffHub-Funktionen in Microsoft Teams ein. Heute umfasst Microsoft Teams die App "Shifts" für die Zeitplanverwaltung, und im Laufe der Zeit werden zusätzliche Funktionen bereit stehen. StaffHub wird am 1. Oktober 2019 für alle Benutzer eingestellt. Jedem Benutzer, der StaffHub zu öffnen versucht, wird eine Meldung angezeigt, die ihn zum Microsoft Teams-Download leitet. Weitere Informationen finden Sie unter [Microsoft StaffHub soll eingestellt werden](microsoft-staffhub-to-be-retired.md).

Die Shifts-App in Microsoft Teams bietet einen einfachen Ansatz für die Verwaltung von Zeitplänen und sämtlichen von Schichttauschaktivitäten und -ausfällen auf täglicher Basis. Teammitglieder können direkt in der App und von allen ihren Geräten aus auf Ihren Zeitplan und die Schichtinformationen zugreifen, um Einstellungen festzulegen, ihre Zeitpläne zu verwalten und arbeitsfreie Zeit zu beantragen.

Dieser Artikel beschreibt, wie Sie die StaffHub-Teams Ihrer Organisation verschieben und Daten für Shifts in Microsoft Teams planen können. Inhalt:

- [Was Sie über den Wechsel zu Microsoft Teams wissen müssen](#what-you-need-to-know-about-the-move-to-teams)
- [Vorbereiten](#prepare)
- [Durchführen eines Pilotversuches](#conduct-a-pilot) 
- [Gehen Sie über Ihren Pilotversuch hinaus und verschieben Sie alle StaffHub-Teams.](#go-beyond-your-pilot-and-move-all-staffhub-teams) 
- [Überwachung der Team-Nutzung](#monitor-teams-usage)
- [Problembehandlung](#troubleshooting)

Ob Sie ein kleines Unternehmen mit einem oder zwei StaffHub-Teams oder ein großes Unternehmen mit Hunderten von StaffHub-Teams sind, hier finden Sie den Administratoren-Leitfaden, den Sie benötigen, um Ihren Wechsel zu Microsoft Teams erfolgreich zu gestalten.

Sie müssen ein globaler Administrator sein, um die Schritte in diesem Artikel auszuführen. Wenn Sie dies noch nicht getan haben, schauen Sie sich die [StaffHub Deaktivierung häufig gestellte Fragen](microsoft-staffhub-to-be-retired.md) an, um Antworten auf Ihre Fragen zu erhalten.

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Was Sie über den Wechsel zu Microsoft Teams wissen müssen

### <a name="when-to-move-to-teams"></a>Zeitpunkt für den Wechsel zu Microsoft Teams

Am 1. Oktober 2019 wird Microsoft StaffHub eingestellt. Wir empfehlen Ihnen, mit der Verwendung von Microsoft Teams noch heute zu beginnen und mit der Migration der Microsoft Teams und Benutzer Ihrer Organisation von StaffHub zu beginnen. Da die Zeitplanverwaltung die am häufigsten verwendete Funktion in StaffHub ist, empfehlen wir Ihnen, die Shifts-App in Microsoft Teams zu verwenden.

### <a name="what-is-moved-to-teams"></a>Was zu Microsoft Teams transferiert wird

Benutzerdetails, Zeitplaninformationen sowie Chat- und Dateidaten werden zu Microsoft Teams übertragen. Dazu gehören Teammitgliedschaft, Teampläne sowie Chats und Dateien der letzten 90 Tage.

Jedes StaffHub-Team benötigt eine entsprechende Office 365 Gruppe. Wenn einem StaffHub-Team keine Office 365-Gruppe zugeordnet ist, wird automatisch eine erstellt, damit die Umstellung unterstützt wird. Aufgrund des Unterschieds in der Team- und Gruppennamensvergabe zwischen Microsoft Teams und StaffHub wird in Microsoft Teams möglicherweise ein anderer Teamname angezeigt.

Während Sie Microsoft Teams von StaffHub zu Microsoft Teams migrieren, haben die Benutzer keinen Zugriff mehr auf ihre Zeitpläne in StaffHub und werden zu Shifts in Microsoft Teams weitergeleitet. Wir empfehlen Ihnen, diese Änderung in Ihrer Organisation zu kommunizieren, um Störungen zu minimieren und die Benutzer zu ermutigen, Microsoft Teams zu implementieren und zu testen. Wenn Sie Azure AD Premium haben, können Sie [einen Bericht ausführen](run-report-to-show-staffhub-usage.md), um eine Liste der StaffHub-Benutzer in Ihrer Organisation zu erhalten, die über diese Änderung informiert werden müssen.  

Es gibt keine Rollback-Option, nachdem Sie ein StaffHub-Team in Microsoft Teams verschoben haben.

### <a name="user-experience-when-you-move-a-team"></a>Benutzererfahrung beim Wechsel eines Microsoft Teams

Es gibt minimale Ausfallzeiten (weniger als eine Sekunde, wenn überhaupt) für Benutzer, wenn ihr Team von StaffHub auf Shifts in Microsoft Teams umgestellt wird. Benutzer können StaffHub weiterhin verwenden, bis der Wechsel zu Microsoft Teams abgeschlossen ist. Wenn der Wechsel abgeschlossen ist, sehen die Teammitglieder eine Meldung, die sie darüber informiert, dass sie damit beginnen müssen, Shifts in Microsoft Teams zu verwenden, um auf ihren Teamplan zuzugreifen. Hier ist ein Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Microsoft Teams verschoben wurde.

![Beispiel für die Nachricht, die Benutzer sehen.](../../media/move-staffhub-teams-to-shifts-in-teams-message-to-users.png "Beispiel für die Meldung, die Benutzer in StaffHub sehen, nachdem das StaffHub-Team in Microsoft Teams verschoben wurde")

## <a name="prepare"></a>Vorbereitung

Hier erfahren Sie, wie Sie sich auf den Wechsel zu Microsoft Teams vorbereiten können.

### <a name="check-that-prerequisites-are-met"></a>Überprüfen Sie, ob die erforderlichen Komponenten erfüllt sind

Bevor Sie ein StaffHub-Team in Microsoft Teams verschieben, müssen Sie auf Folgendes achten:

- Der angemeldete Benutzer ist ein globaler Administrator.
- Microsoft Teams ist für alle Benutzer im Mandanten aktiviert.
- Die Erstellung von Office 365-Gruppen ist im Mandanten aktiviert.
- Die StaffHub TeamID ist gültig.
- Das StaffHub-Team setzt sich aus Mitgliedern zusammen. 
- Alle StaffHub-Teammitglieder sind mit einem Azure AD-Konto verknüpft. 

Wenn diese Voraussetzungen nicht erfüllt sind, schlägt der Umstellungsauftrag fehl. 

### <a name="assign-teams-licenses"></a>Zuweisen von Microsoft Teams-Lizenzen

Jeder Benutzer muss über eine aktive Microsoft 365- oder Office 365-Lizenz aus [einem berechtigten Plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) verfügen und eine Teamlizenz zugewiesen bekommen. Die Zuweisung einer Teams-Lizenz an Benutzer ermöglicht ihnen den Zugriff auf Microsoft Teams.

Sie verwalten Microsoft Teams-Lizenzen im Microsoft 365 Admin Center. Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs auf Microsoft Teams](../../user-access.md).

> [!NOTE]
> Wenn Ihre Organisation Skype for Business verwendet und Sie nicht bereit sind, alle Ihre Benutzer in Microsoft Teams zu verschieben, können Sie Microsoft Teams für Ihre Mitarbeiter in Service und Produktion aktivieren, die dann Microsoft Teams neben Skype for Business ausführen können. In diesem Koexistenzmodus, der als *Inseln* genannt wird, arbeitet jede Client-App als separate Lösung. Weitere Informationen finden Sie unter [Grundlegendes zur Koexistenz und Interoperabilität von Skype for Business und Microsoft Teams](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="install-the-staffhub-powershell-module"></a>Installieren des StaffHub PowerShell-Moduls

Falls noch nicht installiert, [installieren Sie das StaffHub PowerShell-Modul](install-the-staffhub-powershell-module.md). 

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Bereitstellung von Konten für StaffHub-Benutzer, die keine Identität in Azure AD haben.

Jeder Manager und jedes Teammitglied muss über eine Identität im Azure Active Directory Domain Services (Azure AD) verfügen. Wenn ein Benutzer noch nicht über eine Identität in Azure AD verfügt, richten Sie ein Konto für ihn ein. Vorgehensweise. 

#### <a name="get-a-list-of-all-users-on-staffhub-teams-that-have-team-members-that-arent-provisioned-with-an-azure-ad-account"></a>Erhalten Sie eine Liste aller Benutzer in StaffHub-Teams, die Teammitglieder haben, die nicht über ein Azure AD-Konto verfügen.

Führen Sie den folgenden Befehl aus:
```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
foreach($team in $StaffHubTeams[0]) {Get-StaffHubMember -TeamId $team.Id | where {$_.Email -eq $null -or $_.State -eq "Invited"}}
```

#### <a name="provision-the-account"></a>Bereitstellen des Kontos

Führen Sie einen der folgenden Schritte aus:

- Konvertieren und verknüpfen Sie das Konto mit einem bereitgestellten Konto.

  StaffHub Teambesitzer und Manager können einen Dummy oder inaktives Konto konvertieren und mit einem bereitgestellten Konto in StaffHub verknüpfen, indem sie die E-Mail-Adresse des Benutzers auf der StaffHub Team-Einstellungen-Seite in einen gültigen UPN ändern.

- Entfernen Sie das nicht bereitgestellte Konto und fügen Sie es dann mit Hilfe des UPN erneut hinzu.
    1. Führen Sie den Cmdlet[Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) aus, um das nicht bereitgestellte Konto aus dem StaffHub-Team zu entfernen.
    2. Führen Sie den Cmdlet [Add-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) aus, um das Konto zurück zum StaffHub-Team hinzuzufügen, indem Sie den UPN verwenden. 

### <a name="assign-the-firstlineworker-app-setup-policy-to-users"></a>Weisen Sie den Benutzern die FirstlineWorker App-Setup-Richtlinie zu.

Teams enthält eine eingebaute FirstlineWorker-App-Setup-Richtlinie, mit der Sie Microsoft Teams anpassen können, um die Anwendungen hervorzuheben, die für die Mitarbeiter in Service und Produktion in Ihrer Organisation am wichtigsten sind. Wenn Sie diese Richtlinie Benutzern zuweisen, werden die Anwendungen in der Richtlinie an die App-Leiste in Microsoft Teams angeheftet, um einen schnellen und einfachen Zugriff zu ermöglichen. Weitere Apps, die in Microsoft Teams hinzugefügt wurden, finden Sie in der App-Leiste, indem Sie auf **...Weitere Apps** in den Teams Desktop- und Webclients klicken und durch das Wischen nach oben im Microsoft Teams Mobile Client. Standardmäßig beinhaltet die FirstlineWorker App-Setup-Richtlinie die Apps für Aktivität, Shifts, Chat und Anrufe.

Weitere Informationen zum Zuweisen der FirstlineWorker-App-Setup-Richtlinie an Benutzer finden Sie unter [Verwenden der FirstlineWorker-App-Setup-Richtlinie zum Anhäften von Shifts an Teams](manage-the-shifts-app-for-your-organization-in-teams.md#use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams). Nachdem Sie eine Richtlinie zugewiesen haben, kann es bis zu 24 Stunden dauern, bis sie wirksam wird.

Wir empfehlen Ihnen, diesen Schritt mindestens eine Woche vor dem Wechsel Ihrer StaffHub-Teams und Benutzer in Teams durchzuführen. Wenn Benutzer in Teams sind, bestätigen Sie, dass sie die Shifts-App sehen und darauf zugreifen können.

Sie können auch benutzerdefinierte App-Setup-Richtlinien erstellen und die Einstellungen in der globalen App-Setup-Richtlinie bearbeiten. Weitere Informationen finden Sie unter [Verwalten von App-Setup-Richtlinien in Teams](../../teams-app-setup-policies.md).

### <a name="onboard-users-to-teams"></a>Benutzer in Teams einbinden

Als Teil Ihrer Onboarding-Strategie bieten Sie Schulungen und Anleitungen für Benutzer an, die diesen helfen, sich mit Teams vertraut zu machen. Geben Sie die folgenden Ressourcen an Benutzer weiter, damit sie wissen, wo sie Team-Clients, Schulungen und Support erhalten:

- [Teams-Webclient](https://teams.microsoft.com)
- [Downloadlinks für Desktop- und mobile Clients](https://teams.microsoft.com/downloads)
- [Teams-Schulungsvideos](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)
- [Teams-Hilfedokumentation](https://support.office.com/teams)

Anleitungen zur Bereitstellung von Teams und zur Förderung der Teams-Akzeptanz finden Sie unter [Wie Sie Teams einführen](../../How-to-roll-out-teams.md) und [Teams übernehmen können](../../adopt-microsoft-teams-landing-page.md).

## <a name="conduct-a-pilot"></a>Durchführen eines Pilotversuches

Wir empfehlen Ihnen, zunächst zwei oder drei StaffHub-Teams für eine ausgewählte Gruppe von Erstanwendern zu migrieren. Die Durchführung eines Pilotversuchs hilft Ihnen, Ihren Migrationsplan zu verfeinern und sicherzustellen, dass Sie bereit sind, alle StaffHub-Teams Ihrer Organisation in Teams zu übertragen. Es werden auch Experten identifiziert, die dazu beitragen können, die Akzeptanz in Ihrer Organisation zu steigern. Wenn Sie ein kleines Unternehmen sind, das keinen mehrstufigen Ansatz benötigt, reichen die Schritte in diesem Abschnitt aus, um den Wechsel von StaffHub zu Teams zu realisieren.

### <a name="identify-pilot-teams"></a>Auswählen der Pilotteams

Identifizieren Sie zwei oder drei Pilotteams. Alle Teammitglieder sollten sich verpflichten, Shifts in Teams zu verwenden, um ihre Zeitpläne zu verwalten und miteinander zu kommunizieren und zusammenzuarbeiten.

### <a name="identify-team-champions"></a>Auswählen der Teamexperten

Suchen Sie über Pilotteams hinweg Experten aus, und fordern Sie diese auf, sich für die Akzeptanz von Shifts einzusetzen. Teamexperten sind von ihrer Arbeit begeistert und teilen ihre eigenen Erfahrungen, um den Teammitgliedern Unterstützung und Beratung zu bieten. Teamexperten können Teambesitzer oder Manager sein.

Teamexperten sollten sicherstellen, dass die Teammitglieder so eingerichtet werden, dass jeder Zeit hat, um [Team-Clients zu erhalten](../../get-clients.md), sich bei Teams anzumelden und ihre Zeitpläne in Shifts zu überprüfen und mit einander zu chatten. Benutzer, die bereits mit StaffHub vertraut sind, werden in Shifts schnell produktiv sein. Sie können sie auch auf die [Shifts Hilfe](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) verweisen, um zusätzliche Hilfe zu erhalten.

### <a name="move-a-staffhub-team"></a>Verschieben eines StaffHub-Teams

Führen Sie diese Schritte aus, um ein StaffHub-Team nach dem anderen zu verschieben. Wir empfehlen diesen Ansatz für Ihre Pilotteams. Wenn Sie später bereit sind, alle StaffHub-Teams Ihrer Organisation zu verschieben, finden Sie unter [Verschieben Sie Ihre StaffHub-Teams](#move-your-staffhub-teams) Informationen, wie Sie mehrere Teams auf einmal verschieben können.

Führen Sie die folgenden Schritte aus, um ein StaffHub-Team zu verschieben.

```
Move-StaffHubTeam -TeamId <String>
```
Beispiel:

```
Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Hier ist ein Beispiel für die Antwort, die Sie erhalten, wenn Sie eine Anfrage senden, ein StaffHub-Team an Teams zu verschieben.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Um den Status einer Migration zu überprüfen, führen Sie Folgendes aus.

```
Get-TeamMigrationJobStatus <String>
```
Beispiel:

```
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"
```

Hier ist ein Beispiel für die Antwort, die Sie erhalten, wenn eine Migration ausgeführt wird.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

### <a name="move-files-from-a-staffhub-team-to-teams"></a>Dateien von einem StaffHub-Team in Teams verschieben

Dieser Schritt gilt nur, wenn das StaffHub-Team, das Sie in Teams verschoben haben, Dateien enthält, die Sie auch in Teams verschieben möchten. Sie können Dateien direkt in SharePoint Online oder mit PowerShell verschieben. 

#### <a name="in-sharepoint-online"></a>In SharePoint Online

Hier finden Sie Informationen zum[Verschieben von Dateien in SharePoint Online](https://support.office.com/article/how-to-move-files-in-sharepoint-online-8c86f6c3-9612-4031-95b2-3d9d5c6e5a30).

#### <a name="using-powershell"></a>Verwendung von PowerShell

Laden Sie [SharePoint Online Verwaltungsshell](https://www.microsoft.com/download/details.aspx?id=35588) herunter und installieren Sie es, falls noch nicht installiert. Es enthält die Cmdlets, die Sie zum Verschieben von Dateien benötigen.  

Verwenden Sie das Cmdlet [Connect-PnPOnline,](https://docs.microsoft.com/powershell/module/sharepoint-pnp/connect-pnponline?view=sharepoint-ps) um eine Verbindung mit der SharePoint Online-Teamwebsite herzustellen.

```
Connect-PnPOnline -Url https://<sharepoint URL>/sites/<Group Name>  
```

Verwenden Sie für jede Datei, die Sie von StaffHub in Teams verschieben möchten, das Cmdlet [Move-PnPFile](https://docs.microsoft.com/powershell/module/sharepoint-pnp/move-pnpfile), um die Datei zu verschieben.

```
Move-PnPFile -ServerRelativeUrl "/sites/<Group Name>/Shared Documents/<File Name>" -TargetUrl "/sites/<Group Name>/Shared Documents/General/<File Name>" 
```

Um mehrere Dateien zu verschieben, führen Sie eine Schleife über die Dateien und führen Sie den zweiten Befehl auf der Schleife aus. Sie müssen den ersten Befehl nicht wiederholen, wenn die Sitzung aktiv bleibt.

## <a name="go-beyond-your-pilot-and-move-all-staffhub-teams"></a>Gehen Sie über Ihren Piloteversuch hinaus und verschieben Sie alle StaffHub-Teams.

### <a name="raise-awareness"></a>Bewusstsein schaffen

Wenn Sie bereit sind, über Ihre Pilotteams hinauszugehen und die StaffHub-Teams Ihrer Organisation in Teams zu verschieben, ist es wichtig, die Veränderung zunächst in Ihrer Organisation zu kommunizieren. Verbreiten Sie Informationen über Shifts und den Wechsel zu Teams, um das Bewusstsein zu erhöhen, Begeisterung zu erzeugen und die Akzeptanz zu steigern.

### <a name="move-your-staffhub-teams"></a>Verschieben Sie Ihre StaffHub-Teams

Verwenden Sie diese Schritte, um StaffHub-Teams massenhaft zu verschieben. Sie können wählen, ob Sie alle StaffHub-Teams Ihrer Organisation oder einzelne StaffHub-Teams verschieben möchten. Wenn Sie StaffHub-Teams einzeln verschieben möchten, lesen Sie bitte den Abschnitt [Ein StaffHub-Teams verschieben](#move-a-staffhub-team).

#### <a name="move-all-staffhub-teams"></a>Alle StaffHub-Teams verschieben

Führen Sie den folgenden Befehl aus, um eine Liste aller StaffHub-Teams in Ihrer Organisation zu erhalten.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Führen Sie die folgenden Schritte aus, um alle Teams zu verschieben.

```
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```

Hier ist ein Beispiel für die Antwort.

Für jedes Team, das bereits in Teams verlegt wurde oder bereits in Teams existiert, ist die jobId "null", da kein Auftrag eingereicht werden muss, um dieses Team zu verschieben.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams"></a>Verschieben von bestimmten StaffHub-Teams

Führen Sie den folgenden Befehl aus, um eine Liste aller StaffHub-Team-IDs in Ihrer Organisation zu erhalten.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Wählen Sie in den Ergebnissen, die von dem zuvor ausgeführten `Get-StaffHubteamsForTenant`Cmdlet-Befehl angezeigt werden, die Team-IDs aus, die Sie verschieben möchten, und fügen Sie sie dann einer CSV-Datei (comma-separated values) hinzu.

Hier ist ein Beispiel, wie die CSV-Datei formatiert werden sollte.

|Id  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2-0fc9-408b-85ff-c14a26700000|

Nachdem Sie die CSV-Datei erstellt haben, führen Sie Folgendes aus, um die Teams zu verschieben, die Sie in der CSV-Datei angegeben haben.

```
$StaffHubTeams = Import-Csv .\teams.csv
foreach ($team in $StaffHubTeams[0]) {Move-StaffHubTeam -TeamId $team.Id}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams"></a>Bestätigen Sie, dass Ihre StaffHub-Teams in die Teams migriert wurden.

Führen Sie die folgenden Befehl aus, um eine Liste aller Teams in Shifts in Ihrer Organisation zu erhalten. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

### <a name="move-files-from-your-staffhub-teams-to-teams"></a>Dateien von Ihren StaffHub-Teams in Microsoft Teams verschieben

Wenn die StaffHub-Teams, die Sie verschoben haben, Dateien enthalten, die Sie auch in Microsoft Teams verschieben möchten, lesen Sie den Abschnitt [Dateien von einem StaffHub-Team in Microsoft Teams verschieben](#move-files-from-a-staffhub-team-to-teams).

## <a name="monitor-teams-usage"></a>Überwachung der Teams-Nutzung

Mithilfe von Nutzungsberichten können Sie Nutzungsmuster besser verstehen und Sie gelangen so zu Einsichten, die Sie zur Priorisierung von Schulungs- und Kommunikationsinitiativen verwenden können. Da Shifts eine App in Microsoft Teams ist, können Sie die Nutzung über Teams-Berichte einsehen. Weitere Informationen finden Sie unter [Teams-Berichte im Microsoft Teams Admincenter](../../teams-analytics-and-reports/teams-reporting-reference.md)und[Teams-Aktivitätsberichte im Microsoft 365 Admin Center](../../teams-activity-reports.md).

## <a name="troubleshooting"></a>Problembehandlung 

**Wenn Sie versuchen, Dateien von StaffHub in Microsoft Teams zu verschieben, erhalten Sie die Fehlermeldung "Berechtigung verweigert".**

Dies kann vorkommen, wenn Sie versuchen, Dateien in einer privaten Office 365-Gruppe zu verschieben, der Sie nicht angehören. Wenn dies der Fall ist, verwenden Sie das Cmdlet [AddStaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember), um sich zum StaffHub-Team hinzuzufügen, und verschieben Sie dann die Dateien. Nachdem Sie die Dateien verschoben haben, verwenden Sie das Cmdlet [Remove-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/remove-staffhubmember), um sich aus dem Team zu entfernen. 

**Wenn Sie versuchen, Dateien von StaffHub in Microsoft Teams zu verschieben, erhalten Sie eine Fehlermeldung, dass der Ordner „Allgemein“ nicht existiert.**

Führen Sie den folgenden Befehl aus, um den Ordner „Allgemein“ zu Microsoft Office SharePoint Online hinzuzufügen, und versuchen Sie es dann erneut:

  ```
  Add-PnPFolder -Name General -Folder 'Shared Documents'
  ```  

## <a name="related-topics"></a>Verwandte Themen
- [Bereitstellen von Microsoft Teams](../../How-to-roll-out-teams.md)
- [Microsoft StaffHub soll eingestellt werden](microsoft-staffhub-to-be-retired.md)
- [Verwalten der Shifts-App für Ihre Organisation in Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [StaffHub-PowerShell-Referenz](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
