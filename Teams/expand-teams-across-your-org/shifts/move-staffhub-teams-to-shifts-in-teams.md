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
description: Informationen Sie zum Verschieben von Ihren Teams bei Microsoft StaffHub und Daten im Microsoft-Teams Schichten planen.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 14f94428ddeba7b5a648b4b8dbd7bd5ef8fae0e4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32246100"
---
# <a name="move-your-microsoft-staffhub-teams-to-shifts-in-microsoft-teams"></a>Verschieben Sie Ihren Teams bei Microsoft StaffHub in Schichten in der Microsoft-Teams

> [!IMPORTANT]
> Die Übermittlung wirksamer wird 1 Oktober 2019, Microsoft StaffHub zurückgezogen werden. Wir erstellen StaffHub-Funktionen in Microsoft-Teams. Heute, Teams enthält die Schichten app für zeitplanverwaltung und zusätzliche Funktionen, die über einen Zeitraum einführen werden. StaffHub werden nicht für alle Benutzer auf 1 Oktober 2019 mehr. Jeder Benutzer, der versucht, StaffHub öffnen wird eine Meldung mit der Weiterleitung zum Herunterladen von Teams angezeigt. Weitere Informationen finden Sie unter [Microsoft StaffHub zurückgezogen werden](microsoft-staffhub-to-be-retired.md).

> Die Möglichkeit, die in diesem Artikel erläuterten noch nicht noch zur Verfügung gestellt. Es ist bekannt gegeben und wird in Kürze verfügbar, am Ende April 2019. Wenn Sie ein Administrator sind, können Sie feststellen, wenn dies in der Mitte der Nachricht (in der [Microsoft-365-Verwaltungskonsole](https://portal.office.com/adminportal/home)) zur Verfügung steht.

Die Schichten-app in Teams bietet einen einfachen Ansatz für die Verwaltung von Zeitplänen und der Konstante Ablauf UMSCHALT vertauscht und absagen, die täglich auftreten. Teammitglieder können seinen Zeitplan zugreifen und UMSCHALT Informationen direkt in der app über ihren Geräten ihren Vorlieben festgelegt, deren Zeitpläne verwalten und Anforderungszeit deaktiviert.

Dieser Artikel führt Sie durch das Verschieben Ihrer Organisation StaffHub Teams und Daten im Teams Schichten planen. Ganz gleich, ob Sie ein kleines Unternehmen mit einem oder zwei StaffHub Teams oder große Unternehmen mit Hunderten von StaffHub Teams, finden hier die Admin-Anleitung Sie, die Sie benötigen, um des Übergangs Teams Erfolg zu machen.

Sie müssen ein globaler Administrator zum Ausführen der Schritte in diesem Artikel werden. Wenn Sie dies noch nicht getan haben, haben Sie einen Überblick über die [StaffHub Stilllegung – häufig gestellte Fragen](microsoft-staffhub-to-be-retired.md) , Antworten auf Fragen zu erhalten, die Sie möglicherweise. 

## <a name="what-you-need-to-know-about-the-move-to-teams"></a>Sie müssen über die Verschiebung Teams wissen sollten

### <a name="when-to-move-to-teams"></a>Beim Verschieben von Teams

Die Übermittlung wirksamer wird 1 Oktober 2019, StaffHub zurückgezogen werden. Wir empfehlen Ihnen, starten Sie heute mithilfe von Teams und für den Übergang von Teams und Benutzer aus StaffHub Ihres Unternehmens beginnen. Mit zeitplanverwaltung wird das Feature am häufigsten verwendeten in StaffHub wird empfohlen, dass Sie die app Schichten in Teams verwenden vorwärts verschoben werden.

### <a name="what-is-moved-to-teams"></a>Was ist in Teams verschoben.

Teams sind Benutzerdetails Zeitplaninformationen und Chat und Dateidaten gewechselt. Dazu gehören Teammitgliedschaft, Team Zeitpläne, und Chats und Dateien von der letzten 90 Tage.

Jedes Team StaffHub benötigt eine entsprechende Office 365-Gruppe. Wenn ein Team StaffHub ein mit ihm verbundenes Office 365-Gruppe vorhanden ist, wird eine automatisch für Sie zur Unterstützung des Übergangs erstellt. In Anbetracht der unterschiedlichen in Teams und der Gruppe Namenskonflikt zwischen Teams und StaffHub, sehen Sie möglicherweise einen anderen Teamnamen in Teams.

Wie Sie Teams aus StaffHub Teams Übergang, Benutzer haben Zugriff auf ihre Zeitpläne nicht mehr in StaffHub und zu Schichten in Teams weitergeleitet werden. Es wird empfohlen, dass Sie diese Änderung in Ihrer Organisation, um Unterbrechung zu minimieren und fordern Sie die Benutzer zu übernehmen und Erforschen von Teams kommunizieren.

## <a name="prepare"></a>Zubereiten

Hier ist wie für das Verschieben der Teams vorbereiten.

### <a name="assign-teams-licenses"></a>Zuweisen von Teams-Lizenzen

Jeder Benutzer benötigen eine aktive Microsoft 365 oder Office 365-Lizenz aus [einem Anspruch Plan](microsoft-staffhub-to-be-retired.md#which-plans-is-shifts-available-in) und Teams Lizenz zugewiesen sein. Zuweisen einer Lizenz Teams für Benutzer erhalten sie Zugriff auf Teams.

Sie können Teams-Lizenzen in der Microsoft-365-Verwaltungskonsole verwalten. Weitere Informationen finden Sie unter [Verwalten des Benutzerzugriffs für Teams](../../user-access.md).

> [!NOTE]
> Wenn Ihre Organisation Skype für Unternehmen verwendet, und Sie sind nicht alle Benutzer in Teams zu verschieben, können Sie Teams für Ihre Mitarbeiter Firstline aktivieren, die dann Teams zusammen mit Skype für Unternehmen ausgeführt werden können. In diesem Koexistenzmodus *Inseln*aufgerufen, wird jede Clientanwendung als eine separate Lösung ausgeführt. Weitere Informationen finden Sie finden Sie unter [Grundlegendes zu Teams und Skype für Interoperabilität und Koexistenz von Business](../../teams-and-skypeforbusiness-coexistence-and-interoperability.md).

### <a name="provision-accounts-for-staffhub-users-who-dont-have-an-identity-in-azure-ad"></a>Bereitstellung von Konten für StaffHub-Benutzer, die nicht über eine Identität in Azure AD verfügen

Jeden Manager und Teammitglied benötigen eine Identität in Azure Active Directory (AD Azure). Wenn ein Benutzer eine Identität in Azure AD bereits vorhanden ist, stellen Sie ein Konto für diese bereit. Vorgehensweise:

- StaffHub Team Eigentümer und Manager können eine simulierte Kontostatus konvertieren und Verknüpfen des Arbeitsbereichs mit einem bereitgestellten Konto in StaffHub durch Ändern der e-Mail-Adresse des Benutzers für einen gültigen UPN auf der Seite StaffHub Team Settings.

- Administratoren können die [Hinzufügen-StaffHubMember](https://docs.microsoft.com/powershell/module/staffhub/add-staffhubmember?view=staffhub-ps) ausführen und [Remove-StaffHubUser](https://docs.microsoft.com/powershell/module/staffhub/Remove-StaffHubUser?view=staffhub-ps) -Cmdlets zum Entfernen eines Kontos nicht bereitgestellte aus einem Team StaffHub, und fügen Sie das Konto mithilfe des UPN sichern.

### <a name="install-the-staffhub-powershell-module"></a>Installieren des StaffHub PowerShell-Moduls

Wenn Sie nicht bereits geschehen, [Installieren Sie das Modul StaffHub PowerShell](install-the-staffhub-powershell-module.md).

Wenn Sie ein Team StaffHub verschieben, wird die verschiebungsanforderung für erforderliche Komponenten überprüft. Nachfolgend finden Sie Gründe, warum eine verschiebungsanforderung fehlschlagen kann:

- Der Benutzer angemeldet ist kein globaler Administrator
- Teams ist für alle Benutzer in den Mandanten deaktiviert.
- Office 365 Gruppen erstellen ist in den Mandanten deaktiviert.
- Das Team StaffHub ist ungültig oder enthält keine Mitglieder
- Das StaffHub Team enthält Elemente, die mit einem Azure AD-Konto verknüpft sind  

## <a name="run-a-pilot"></a>Ausführen eines Pilotprojekts

Es wird empfohlen, dass Sie starten, indem Sie zwei oder drei StaffHub Teams für eine ausgewählte Gruppe von frühe Übernahmen verschieben. Ausführen eines Pilotprojekts Dank Optimieren des Plans für den Umstieg von, und stellen Sie sicher, dass Sie Ihrer Organisation StaffHub Teams Teams verschieben möchten. Er gibt außerdem Champions, die Akzeptanz in Ihrem Unternehmen helfen können. Wenn Sie ein kleines Unternehmen, das phasenweise nicht erforderlich ist sind, können die Schritte in diesem Abschnitt alle können, Sie die Option von StaffHub Teams müssen.

### <a name="identify-pilot-teams"></a>Identifizieren von pilot-teams

Erreichen von zwei oder drei pilot Teams zu identifizieren. Alle Teammitglieder sollten mithilfe von Schichten Teams ihre Zeitpläne verwalten und Kommunikation und Zusammenarbeit miteinander in commit.

### <a name="identify-team-champions"></a>Identifizieren von Champions team

Identifizieren von Champions über pilot Teams und registrieren, mit denen Schichten Wechsels bekannt. Team Champions am Herzen was sie tun, werden ihre eigenen Befunde um bieten Unterstützung und an die Teammitglieder freigeben. Team Champions kann Team Besitzer oder -Manager.

Team Champions sollten sicherstellen, Teammitglieder eingesetzten Hörers Zeit für alle Benutzer, [Teams Clients erhalten möchten](../../get-clients.md), melden Sie sich bei Teams sind und ihre Zeitpläne in Schichten Auschecken und miteinander chatten. Benutzer, die bereits mit StaffHub vertraut sind werden betriebsbereit schnell Schichten in. Sie können Sie auch zur [Schichten](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b) zusätzliche Hilfe verweisen.

### <a name="move-a-staffhub-team-coming-soon"></a>Verschieben eines StaffHub-Teams (bald verfügbar)

Verwenden Sie folgende Schritte aus, um ein StaffHub Team gleichzeitig zu verschieben. Es wird empfohlen, diese Herangehensweise an die die pilot-Teams. Später, wenn Sie zum Verschieben von Ihrer Organisation StaffHub Teams bereit sind, finden Sie unter Schritte zum Verschieben Sie mehrere Teams zu einem Zeitpunkt [Verschieben Ihrer StaffHub Teams](#move-your-staffhub-teams-coming-soon) .

Führen Sie Folgendes ein, um ein Team StaffHub verschieben.

```
Move-StaffHubTeam -TeamId <String>

Sample:

Move-StaffHubTeam -TeamId "TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f"
```

Es folgt ein Beispiel der Antwort, die Sie erhalten, wenn Sie die Anforderung einer Verschiebung einer Team StaffHub Teams übermitteln.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ---------------------------------------    ----------------------------------------    ---------------------------          
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   false
```

Führen Sie folgenden Befehl zum Überprüfen des Status einer Anforderung verschieben.

```
Get-TeamMigrationJobStatus <String>

Sample:
Get-TeamMigrationJobStatus -JobId "JOB_81b1f191-3e19-45ce-ab32-3ef51f100000"

```

Es folgt ein Beispiel der Antwort, die Sie erhalten, wenn eine Verschiebung ausgeführt wird.

```
    jobId                                     status       teamId                                     isO365GroupCreated  Error
    ----------------------------------------  ----------   ----------------------------------------   ------------------  -----    
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000  inProgress   TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f  true                none
```

## <a name="make-the-transition-from-staffhub-to-teams"></a>Nehmen Sie den Übergang von StaffHub Teams

### <a name="raise-awareness"></a>Bewusstsein

Wenn können Sie jetzt Ihre pilot Teams hinausgehen, und Verschieben von Ihrer Organisation StaffHub Teams Teams, es ist wichtig, zuerst die Änderung in Ihrer Organisation kommunizieren. Das Wort zu Schichten und den Übergang zu Teams Bewusstsein, Interesse generieren und bessere Akzeptanz verteilt.

### <a name="move-your-staffhub-teams-coming-soon"></a>Verschieben Sie die StaffHub-Teams (bald verfügbar)

Verwenden Sie folgende Schritte aus, um StaffHub Teams in einer Sammeloperation verschieben. Sie können auswählen, verschieben Sie alle Ihrer Organisation StaffHub Teams oder bestimmte StaffHub Teams. Wenn Sie, dass StaffHub teams, die jeweils einzeln verschieben möchten, finden Sie unter [Verschieben Sie ein Team StaffHub](#move-a-staffhub-team-coming-soon).

#### <a name="move-all-staffhub-teams-coming-soon"></a>Verschieben Sie alle StaffHub-Teams (bald verfügbar)

Führen Sie Folgendes ein, um eine Liste aller StaffHub Teams in Ihrer Organisation abzurufen.

```
$StaffHubTeams = Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

Führen Sie dann Folgendes ein, um alle Teams verschieben.

```
$StaffHubTeams | foreach {Move-StaffHubTeam -TeamId {$_.Id}}
```

Es folgt ein Beispiel der Antwort.

Für alle Teams, die bereits für Teams verschoben wurde oder bereits im Teams, wird die JobId "null" während ein Auftrags muss nicht zum Verschieben von diesem Teams übermittelt werden.

```
    jobId                                      teamId                                      teamAlreadyInMicrosofteams  
    ----------------------------------------   -----------------------------------------   --------------------------         
    null                                       TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f   true
    JOB_81b1f191-3e19-45ce-ab32-3ef51f100000   TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000   false
```

#### <a name="move-specific-staffhub-teams-coming-soon"></a>Verschieben Sie bestimmte StaffHub-Teams (bald verfügbar)

Führen Sie Folgendes ein, um eine Liste aller StaffHub Team Ids in Ihrer Organisation abzurufen.

```
Get-StaffHubTeamsForTenant -ManagedBy "Staffhub"
```

In den zurückgegebenen Ergebnissen der `Get-StaffHubteamsForTenant` Cmdlet ausgeführt Sie zuvor, wählen Sie die Team-Ids, die Sie verschieben möchten, und klicken Sie dann eine durch Trennzeichen getrennten Werten (CSV)-Datei hinzugefügt werden.

Hier ist ein Beispiel, wie die CSV-Datei formatiert werden soll.

|ID  |
|---------|
|TEAM_4bbc03af-c764-497f-a8a5-1c0708475e5f<br>TEAM_81b1f191-3e19-45ce-ab32-3ef51f100000<br>TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000<br>TEAM_b42d0fa2 - 0fc 9-408b-85ff-c14a26700000|

Nachdem Sie die CSV-Datei erstellt haben, führen Sie Folgendes ein, um die Teams verschieben, den, die Sie in der CSV-Datei angegeben.

```
Import-Csv .\teams.txt | foreach {Move-StaffHubTeam -TeamdId {$_.Id}}
```
### <a name="confirm-that-your-staffhub-teams-have-moved-to-teams-coming-soon"></a>Vergewissern Sie sich, dass Ihre StaffHub Teams Teams (bald verfügbar) verschoben wurden

Führen Sie Folgendes ein, um eine Liste aller Teams in Schichten in Ihrer Organisation abzurufen. 

```
Get-StaffHubTeamsForTenant -ManagedBy "Teams"
```

## <a name="monitor-teams-usage"></a>Überwachen der Verwendung von Teams

Verwendungsberichte können Ihnen besser verstehen Verwendungsmuster und bieten Ihnen Insights an, wo Sie in Ihrer Organisation Schulung und Kommunikation Maßnahmen priorisieren. Da Schichten ist eine app in Teams, können Sie die Verwendung durch Teams Berichte anzeigen. Weitere Informationen finden Sie unter [Teams Berichte in der Verwaltungskonsole von Microsoft-Teams](../../teams-analytics-and-reports/teams-reporting-reference.md) und [Teams Berichte in der Microsoft-365-Verwaltungskonsole](../../teams-activity-reports.md).

## <a name="related-topics"></a>Verwandte Themen
- [Microsoft StaffHub soll eingestellt werden](microsoft-staffhub-to-be-retired.md)
- [Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Referenz zu den StaffHub PowerShell](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
