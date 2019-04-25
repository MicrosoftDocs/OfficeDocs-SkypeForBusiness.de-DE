---
title: Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Informationen Sie zum Einrichten und Verwalten der app Schichten in Teams für Firstline Mitarbeiter in Ihrer Organisation.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9927da9aea89eeb4d5b1b71eac2818c5deb52925
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32245934"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Verwalten der Schichten-App für Ihre Organisation in Microsoft Teams

> [!IMPORTANT]
> Die Übermittlung wirksamer wird 1 Oktober 2019, Microsoft StaffHub zurückgezogen werden. Wir erstellen StaffHub-Funktionen in Microsoft-Teams. Heute, Teams enthält die Schichten app für zeitplanverwaltung und zusätzliche Funktionen, die über einen Zeitraum einführen werden. StaffHub werden nicht für alle Benutzer auf 1 Oktober 2019 mehr. Jeder Benutzer, der versucht, StaffHub öffnen wird eine Meldung mit der Weiterleitung zum Herunterladen von Teams angezeigt. Weitere Informationen finden Sie unter [Microsoft StaffHub zurückgezogen werden](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Übersicht über die Schichten
Die Schichten-app in Microsoft-Teams, hält Firstline Mitarbeiter verbundenen und synchronisiert. Mobile zunächst für eine schnelle und effektive zeitverwaltung und Kommunikation für Teams basiert. Schichten können Firstline Mitarbeiter und deren Manager ihren mobilen Geräten verwenden, um Zeitpläne verwalten und in Verbindung bleiben. 

- Manager erstellen, aktualisieren und UMSCHALT Zeitpläne für Teams verwalten. Sie können Nachrichten an eine Person senden ("Es ist einem Spill auf der Bodenfläche") oder das gesamte team ("der regionalen konzipiert ist in 20 Minuten eintreffen"). Sie können auch Dokumente zu Richtlinien, amtliche nachrichtenverlautbarungen und Videos senden. 
- Mitarbeiter können ihre bevorstehenden Schichten anzeigen, finden Sie unter, wer außer für den Tag geplant ist, zu vertauschen und bieten eine Schicht Anforderungszeit deaktiviert anfordern. 

Es ist wichtig, zu wissen, dass Schichten unterstützt derzeit keine Gastbenutzer. Dies bedeutet, dass Gäste auf ein Team können nicht hinzugefügt werden, oder UMSCHALT Zeitpläne verwenden, wenn Access Gast in Teams aktiviert ist. 

## <a name="availability-of-shifts"></a>Verfügbarkeit von Schichten

Schichten ist in allen Office 365-Abonnements, die Teams, mit ein paar Ausnahmen enthalten verfügbar. Ausnahmen sind US-Regierung Cloud-Community (GCC) und Teams frei. Schichten nicht in Office-365 US-Regierung oder Teams frei angeboten.

Weitere Informationen zur Lizenzierung für Teams, einschließlich einer Liste der Office 365-Abonnements, die Teams, finden Sie unter [Office 365-Lizenzierung für Teams](../../Office-365-licensing.md).

## <a name="location-of-shifts-data"></a>Speicherort der Schichten Daten

Verschiebt Daten werden derzeit in Azure in Rechenzentren in Nordamerika, Western Europa und Asien-Pazifik gespeichert. Weitere Informationen dazu, wo die Daten gespeichert ist finden Sie unter [Wo sind meine Daten](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Einrichten von Schichten

### <a name="enable-or-disable-shifts-in-your-organization"></a>Aktivieren oder Deaktivieren von Schichten in Ihrer Organisation

Schichten ist standardmäßig für alle Teams Benutzer in Ihrer Organisation aktiviert. Sie können deaktivieren oder Aktivieren der app für Ihre Organisation in der Microsoft-365-Verwaltungskonsole.

1. Melden Sie sich bei Microsoft 365 Administrationscenter mit Ihrem Office 365-Admin-Konto.
2. Wechseln Sie zu **Einstellungen** > **Services &-add-ins** > **Microsoft-Teams**. 
3. Klicken Sie unter **Einstellungen für die gesamte Mandanten** **Apps**, und deaktivieren Sie unter **Default Apps**, ein, oder aktivieren Sie das Kontrollkästchen **Schichten** deaktivieren oder aktivieren Sie die app. 

    ![Screenshot des Abschnitts Standard-Apps] (../../media/firstline-worker-enable-disable-shifts.png "Screenshot des Abschnitts Standard-Apps in der Microsoft-365-Verwaltungskonsole mit der Liste der apps, einschließlich app-Schichten")

### <a name="use-the-firstline-worker-app-setup-policy-to-pin-shifts-to-teams"></a>Verwenden Sie die Firstline Worker app Setup-Richtlinie auf Pin Schichten Teams

Richtlinien für die App Setup können Sie Teams zum Hervorheben von apps, die für Benutzer in Ihrer Organisation am wichtigsten sind anpassen. Die apps in einer Richtlinie festgelegt werden auf der app-Leiste angeheftete&mdash;der Leiste rechts auf dem Desktopclient Teams und am unteren Rand der mobilen Clients Teams&mdash;, in dem Benutzer können schnell und einfach darauf zugreifen. 
 
Teams umfasst eine integrierte Firstline Worker app Setup-Richtlinie, die Sie in Ihrer Organisation Mitarbeiter Firstline zuweisen können. Standardmäßig enthält die Richtlinie die Aktivität, Schichten, Chat und Aufrufen von apps. 

Die Richtlinie Firstline Worker im linken Navigationsbereich von der Verwaltungskonsole von Microsoft-Teams, wechseln Sie zum Anzeigen **Teams**App > **Setup Richtlinien für die App**.

![Screenshot der Firstline Worker app Setup Richtlinie in der Verwaltungskonsole von Microsoft-Teams] (../../media/firstline-worker-app-setup-policy.png "Screenshot der Firstline Worker app Setup Richtlinie in der Verwaltungskonsole von Microsoft-Teams")

#### <a name="assign-the-firstline-worker-policy-to-individual-users"></a>Zuweisen der Richtlinie Firstline Worker für einzelne Benutzer

1. Im linken Navigationsbereich von Microsoft-Teams, Administrationscenter wechseln Sie zu dem **Benutzer**, und klicken Sie dann auf Benutzer.
2. Neben **zugewiesene Richtlinien**wählen Sie **Bearbeiten**aus.
3. Wählen Sie unter **Teams App Setup Richtlinie** **FirstlineWorker**aus, und wählen Sie dann auf **Speichern**.

#### <a name="assign-the-firstline-worker-app-setup-policy-to-users-in-a-group"></a>Weisen Sie den Arbeitsprozess Firstline app Setup-Richtlinie für Benutzer in einer Gruppe

Sie können den Arbeitsprozess Firstline app Setup-Richtlinie für Benutzer in einer Gruppe, wie etwa einer Sicherheitsgruppe zuweisen, indem eine Verbindung mit Azure Active Directory PowerShell Graph-Modul und die Skype für Business PowerShell-Modul. Weitere Informationen zum Verwenden von PowerShell zum Verwalten von Teams finden Sie unter [Übersicht über die PowerShell Teams](../../teams-powershell-overview.md).

In diesem Beispiel weisen wir den Arbeitsprozess Firstline app Setup Richtlinie alle Benutzer in der Gruppe "Contoso" Firstline Team.

> [!NOTE]
> Stellen Sie sicher, dass Sie zuerst die Azure Active Directory-PowerShell-Modul Diagramm und Skype für Business PowerShell-Modul anschließen, durch die Schritte in [Verbindung mit allen Office 365-Diensten in einem einzelnen Windows PowerShell-Fenster](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Rufen Sie die GroupObjectId bestimmten Gruppe.
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
Rufen Sie die Mitglieder der angegebenen Gruppe.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Weisen Sie alle Benutzer in der Gruppe der FirstlineWorker app Setup-Richtlinie.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstlineWorker" -Identity $_.EmailAddress}
``` 
Abhängig von der Anzahl der Elemente in der Gruppe kann dieser Befehl mehrere Minuten dauern.

## <a name="related-topics"></a>Verwandte Themen
- [Verschiebt die Hilfe für Firstline Mitarbeiter](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
