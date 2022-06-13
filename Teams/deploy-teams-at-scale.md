---
title: Bereitstellen von Teams im großen Maßstab für Mitarbeiter in Service und Produktion in Microsoft Teams
author: LanaChin
ms.author: v-lanachin
ms.reviewer: rahuldey
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Erfahren Sie, wie Sie Teams im großen Maßstab für die Mitarbeiter in Service und Produktion in Ihrer Organisation bereitstellen.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 561eaf310201b99ada9cce4dde49746d58d77088
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/13/2022
ms.locfileid: "66046024"
---
# <a name="deploy-teams-at-scale-for-frontline-workers-in-microsoft-teams"></a>Bereitstellen von Teams im großen Maßstab für Mitarbeiter in Service und Produktion in Microsoft Teams

> [!NOTE]
> Dieses Feature befindet sich derzeit in der privaten Vorschau. Wenn Sie an der privaten Vorschau teilnehmen möchten, wenden Sie sich an uns unter [dscale@microsoft.com](mailto:dscale@microsoft.com).

## <a name="overview"></a>Übersicht
 
Ihre Organisation verfügt möglicherweise über viele Teams, die Sie verwenden, um die Kommunikation und Zusammenarbeit zwischen Ihren Mitarbeitern in Service und Produktion zu fördern, die über verschiedene Geschäfte, Standorte und Rollen verteilt sind. Derzeit gibt es keine einfache Lösung zum Bereitstellen, Einrichten und Verwalten dieser Teams und Benutzer im großen Maßstab.

Wir erstellen eine Lösung, mit der Administratoren Teams im großen Maßstab bereitstellen und verwalten können.

Hier ist eine Übersicht über die Funktionen, die heute verfügbar sind, um eine große Anzahl von Teams gleichzeitig zu erstellen und zu verwalten, und was wir für die nahe Zukunft planen.

||Heute verfügbar |Später im Jahr 2022  |
|---------|---------|---------|
|**Anzahl der Teams, die Sie pro Batch erstellen können**|Bis zu 100 |Bis zu 500|
|**Anzahl der Benutzer, die Sie pro Team hinzufügen können**|Bis zu 25|Bis zu 25|

Die Bereitstellung von Teams im großen Maßstab ermöglicht Folgendes:

- Erstellen Sie Teams mithilfe vordefinierter Vorlagen oder ihrer eigenen benutzerdefinierten Vorlagen.
- Hinzufügen von Benutzern zu Teams als Besitzer oder Mitglieder.
- Verwalten Sie Teams im großen Maßstab, indem Sie Benutzer zu vorhandenen Teams hinzufügen oder daraus entfernen.
- Bleiben Sie per E-Mail benachrichtigt, einschließlich Abschluss, Status und Fehler (falls vorhanden). Sie können bis zu fünf Personen über den Status jeder Gruppe von Teams informieren, die Sie bereitstellen. Teambesitzer und -mitglieder werden automatisch benachrichtigt, wenn sie zu einem Team hinzugefügt werden.

## <a name="how-to-deploy-teams-at-scale"></a>So stellen Sie Teams im großen Maßstab bereit

> [!NOTE]
> Stellen Sie vor der Bereitstellung Ihrer Teams sicher, dass alle Teambesitzer über eine Teams Lizenz verfügen.

Führen Sie die folgenden Schritte aus, um eine große Anzahl von Teams gleichzeitig bereitzustellen.

### <a name="step-1-prepare-your-csv-files"></a>Schritt 1: Vorbereiten Ihrer CSV-Dateien

Sie müssen zwei CSV-Dateien für jeden Batch von Teams erstellen, die Sie bereitstellen:

- **Eine CSV-Datei, die die Teams definiert, die Sie erstellen**. Diese Datei muss diese erforderlichen Spalten in der folgenden Reihenfolge enthalten, beginnend mit der ersten Spalte:

    |Spaltenname  |Beschreibung  |
    |---------|---------|
    |**Teamname**|Der Name des Teams.|
    |**Vorhandene Team-ID**|Wenn Sie Benutzer zu einem vorhandenen Team hinzufügen oder daraus entfernen, geben Sie die Team-ID des Teams an.|
    |**Sichtbarkeit**|Ob das Team öffentlich ist (jeder in Ihrer Organisation kann teilnehmen) oder privat (Benutzer benötigen die Genehmigung der Teambesitzer, um teilzunehmen). Die Optionen sind **öffentlich** und **privat**.|
    |**Teamvorlagen-ID**|Wenn Sie ein Team aus einer vordefinierten oder benutzerdefinierten Vorlage erstellen, geben Sie die Teamvorlagen-ID an. Eine Liste vordefinierter Teamvorlagen und IDs finden Sie [im Erste Schritte mit Teamvorlagen im Teams Admin Center](get-started-with-teams-templates-in-the-admin-console.md). Wenn Sie die standardmäßige Teamvorlage verwenden möchten, lassen Sie diese leer.|

- **Eine CSV-Datei, die die Benutzer, die Sie zu jedem Team hinzufügen, zugeordnet**. Diese Datei muss diese erforderlichen Spalten in der folgenden Reihenfolge enthalten, beginnend mit der ersten Spalte:

    |Spaltenname  |Beschreibung  |
    |---------|---------|
    |**Vollständiger Benutzername**|Der Anzeigename des Benutzers.|
    |**Benutzer-UPN oder -ID**|Der Benutzerprinzipalname (USER Principal Name, UPN) oder die ID des Benutzers. Beispiel: averyh@contoso.com.|
    |**Teamname**|Der Name des Teams.|
    |**Actiontype**|Unabhängig davon, ob Sie den Benutzer zum Team hinzufügen oder daraus entfernen. Die Optionen sind **"AddMember"** und **"RemoveMember"**.|
    |**Besitzer oder Mitglied**|Gibt an, ob der Benutzer Ein Teambesitzer oder Teammitglied ist. Optionen sind **Besitzer** und **Mitglied**.|

#### <a name="examples"></a>Beispiele

Verwenden Sie die folgenden Beispiele, um Ihre CSV-Dateien zu erstellen. Hier haben wir die Dateien, Teams.csv und Users.csv benannt.

**Teams.csv**

|Teamname|Vorhandene Team-ID|Sichtbarkeit|Teamvorlagen-ID|
|---------|---------|---------|---------|
|Contoso Store 1||Öffentlich|com.microsoft.teams.template.retailStore|
|Contoso Store 2||Öffentlich|com.microsoft.teams.template.retailStore|
|Contoso Store 3||Öffentlich|com.microsoft.teams.template.retailStore|
|Contoso Store 4||Öffentlich|com.microsoft.teams.template.retailStore|
|Contoso Store 5||Öffentlich|com.microsoft.teams.template.ManageAProject|
|Contoso Store 6||Öffentlich|com.microsoft.teams.template.ManageAProject|
|Contoso Store 7||Öffentlich||
|Contoso Store 8||Privat|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 9||Privat|com.microsoft.teams.template.OnboardEmployees|
|Contoso Store 10||Privat|com.microsoft.teams.template.OnboardEmployees|

**Users.csv**

|Vollständiger Benutzername |Benutzer-UPN oder -ID|Teamname|Actiontype|Besitzer oder Mitglied|
|---------|---------|---------|---------|---------|
|Avery Howard|averyh@contoso.com|Contoso Store 1|AddMember|Besitzer|
|Casey Jensen|caseyj@contoso.com|Contoso Store 2|AddMember|Besitzer|
|Jessie Irwin|jessiei@contoso.com|Contoso Store 3|AddMember|Besitzer|
|Manjeet Bhatia|manjeetb@contoso.com|Contoso Store 4|AddMember|Besitzer|
|Mikaela Lee|mikaelal@contoso.com|Contoso Store 5|AddMember|Besitzer|
|Morgan Conners|morganc@contoso.com|Contoso Store 6|AddMember|Mitglied|
|Oscar Ward|oscarw@contoso.com|Contoso Store 7|AddMember|Mitglied|
|Rene Pelletier|renep@contoso.com|Contoso Store 8|AddMember|Mitglied|
|Sydney Mattos|sydneym@contoso.com|Contoso Store 9|AddMember|Mitglied|
|Violet Martinez|violetm@contoso.com|Contoso Store 10|AddMember|Mitglied|

### <a name="step-2-deploy-your-teams"></a>Schritt 2: Bereitstellen Ihrer Teams

Nachdem Sie Ihre CSV-Dateien erstellt haben, können Sie Ihre Umgebung einrichten und Ihre Teams bereitstellen.

Sie verwenden das ```New-CsBatchTeamsDeployment``` Cmdlet, um eine Reihe von Teams zum Erstellen zu übermitteln. Für jeden Batch wird eine Orchestrierungs-ID generiert. Anschließend können Sie das ```Get-CsBatchTeamsDeployment``` Cmdlet verwenden, um den Fortschritt und Status jedes Batches nachzuverfolgen.

1. Installieren Sie PowerShell, Version 7 oder höher. Eine schrittweise Anleitung finden Sie unter [Installieren von PowerShell auf Windows](/powershell/scripting/install/installing-powershell-on-windows).
1. Führen Sie PowerShell im Administratormodus aus.
1. Führen Sie die folgenden Schritte aus, um alle zuvor installierten Teams PowerShell-Moduls zu deinstallieren.

    ```powershell
    Uninstall-module -Name MicrosoftTeams -Force -Allversions
    ```

    Wenn eine Fehlermeldung angezeigt wird, sind Sie bereits festgelegt. Fahren Sie mit dem nächsten Schritt fort.
1. Laden Sie die [neueste Version des Teams PowerShell-Moduls](https://www.powershellgallery.com/packages/MicrosoftTeams) herunter, und installieren Sie sie.

1. Führen Sie die folgenden Schritte aus, um eine Verbindung mit Teams herzustellen.

    ```powershell
    Connect-MicrosoftTeams
    ```

    Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihren Administratoranmeldeinformationen an.

1. Führen Sie die folgenden Schritte aus, um eine Liste der Befehle im Teams PowerShell-Modul abzurufen.

    ```powershell
    Get-Command -Module MicrosoftTeams
    ```

    Vergewissern Sie sich, dass ```New-CsBatchTeamsDeployment``` und ```Get-CsBatchTeamsDeployment``` aufgeführt sind.

1. Führen Sie die folgenden Schritte aus, um eine Reihe von Teams bereitzustellen. In diesem Befehl geben Sie den Pfad zu Ihren CSV-Dateien und die E-Mail-Adressen von bis zu fünf Empfängern an, die über diese Bereitstellung benachrichtigt werden sollen.

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "Your CSV file path" -UsersFilePath "Your CSV file path" -UsersToNotify "Email addresses" 
    ```

    Zum Beispiel: 

    ```powershell
    New-CsBatchTeamsDeployment -TeamsFilePath "C:\dscale\Teams.csv" -UsersFilePath "C:\dscale\Users.csv" -UsersToNotify "adminteams@contoso.com,adelev@contoso.com"
    ```

    Die Empfänger erhalten E-Mail-Benachrichtigungen über den Bereitstellungsstatus. Die E-Mail enthält die Orchestrierungs-ID für den von Ihnen übermittelten Batch sowie eventuell aufgetretene Fehler.

1. Führen Sie die folgenden Schritte aus, um den Status des von Ihnen übermittelten Batches zu überprüfen.

    ```powershell
    Get-CsBatchTeamsDeploymentStatus -OrchestrationId "OrchestrationId"
    ```

## <a name="send-us-feedback"></a>Senden Sie uns Feedback.

Wir schätzen Ihr Feedback. Nutzbarkeit, Zuverlässigkeit, Leistung&mdash;wir freuen uns über alles!

[E-Mail-dscale@microsoft.com](mailto:dscale@microsoft.com) und fügen Sie Ihre Orchestrierungs-ID und Fehlerdatei ein, sofern vorhanden.

## <a name="related-articles"></a>Verwandte Artikel

- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
