---
title: Deaktivieren Teams Richtlinie für die Hochladen nativen Datei
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Erfahren Sie, wie Sie die Teams Dateirichtlinie mithilfe von PowerShell erstellen, festlegen, zuweisen und anpassen.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b6089e93b4754fa35edaa9befb5cfa6bb176238
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681906"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Deaktivieren Teams Richtlinie für die Hochladen nativen Datei

Microsoft Teams verwendet OneDrive und SharePoint zum Speichern und Freigeben von Inhalten, aber einige Organisationen und Benutzer bevorzugen möglicherweise Speicheranbieter von Drittanbietern.  

Wenn Ihre Organisation einen Drittanbieter für die Inhaltsspeicherung wählt, müssen Sie den `NativeFileEntryPoints` Parameter in der Richtlinie Teams Dateien deaktivieren. Dieser Parameter ist standardmäßig aktiviert, wodurch die Option zum Hochladen von Inhalten aus OneDrive oder SharePoint in Teams Chats oder Kanäle angezeigt wird.

Dieser Artikel hilft Ihnen beim Erstellen, Festlegen, Zuweisen und Entfernen des `NativeFileEntryPoints` Parameters mithilfe von PowerShell.

>[!NOTE]
>Wenn die Richtlinie Teams Dateien deaktiviert ist, werden Benutzern in Teams keine Zugriffspunkte für OneDrive und SharePoint angezeigt, aber die Erstellung neuer Teams und Kanäle löst weiterhin die Generierung übereinstimmenden SharePoint Bibliotheken aus.

## <a name="prepare-to-update-the-teams-files-policy"></a>Vorbereiten der Teams Dateirichtlinie

### <a name="set-up-microsoft-powershell"></a>Einrichten von Microsoft PowerShell

Derzeit kann diese Richtlinie im Teams Admin Center nicht geändert werden. Der Microsoft 365 Mandantenadministrator Ihrer Organisation muss die Änderungen mithilfe der PowerShell-Cmdlets vornehmen, die weiter unten in diesem Artikel beschrieben werden.

Erfahren Sie, wie Sie das PowerShell-Teams-Modul mithilfe von PowerShell-Katalog installieren, indem [Sie "Microsoft Teams PowerShell-Modul installieren" lesen](teams-powershell-install.md).

Informationen zum Installieren oder Herunterladen des Teams PowerShell-Moduls finden Sie [unter PowerShell-Katalog für Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Weitere Informationen zum Einrichten von PowerShell für Teams-Verwaltung finden [Sie unter Verwalten von Teams mit Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Zulassen von Drittanbieter-Apps im Teams Admin Center

Dieser Schritt ist nicht erforderlich, um die Teams Dateirichtlinie zu ändern, aber er ist erforderlich, wenn Sie bereit sind, Ihren Drittanbieter-Speicheranbieter in die Teams Erfahrung Ihrer Benutzer zu integrieren.

Ihr Microsoft 365 Mandantenadministrator muss die Richtlinie "Apps von Drittanbietern zulassen" im Teams Admin Center aktivieren.

Informationen zum Zulassen von Drittanbieter- oder benutzerdefinierten Apps finden Sie unter Verwalten organisationsweiter Apps-Einstellungen unter ["Verwalten Ihrer Apps" im Microsoft Teams Admin Center](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Deaktivieren von NativeFileEntryPoints für den gesamten Mandanten

Durch Festlegen des `-Identity` Parameters werden `Global` die Richtlinieneinstellungen auf alle Benutzer in Ihrer Organisation angewendet.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Beispiel-PowerShell-Richtlinien-Cmdlet für den gesamten Mandanten

Mit diesem PowerShell-Beispielbefehl wird der`NativeFileEntryPoints` Parameter `Disabled` für den gesamten Mandanten festgelegt.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Überprüfen des Status Ihres Mandanten  

Verwenden Sie `Get-CsTeamsFilesPolicy` das Cmdlet, um den aktuellen Status der Richtlinie für Teams Dateien Ihres Mandanten anzuzeigen.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Aktivieren oder Deaktivieren des nativen Dateiuploadpunkts

Um den systemeigenen Dateiuploadpunkt für Den gesamten Mandanten zu aktivieren oder zu deaktivieren, legen Sie den `NativeFileEntryPoints` Parameter entweder oder `Enabled` `Disabled`fest.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Entfernen der Richtlinie für Ihre Benutzer

Verwenden Sie das Cmdlet, `Remove-CsTeamsFilesPolicy` um die Richtlinie Teams Dateien für Ihre Benutzer zu entfernen.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Deaktivieren von NativeFileEntryPoints für bestimmte Benutzer

Sie können auch die Richtlinie Teams Dateien für bestimmte Benutzer aktualisieren, indem Sie eine neue Teams Dateirichtlinienzeichenfolge `-Identity` erstellen und benutzern die neu erstellte Richtlinie zuweisen.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Beispiel-PowerShell-Richtlinien-Cmdlet für bestimmte Benutzer

Mit diesem PowerShell-Beispielbefehl wird ein neues `CsTeamsFilesPolicy` Element mit dem `-Identity` Namen "as `UserPolicy` " und dem `NativeFileEntryPoints` auf `Disabled`" festgelegten Parameter " erstellt.

Wenn einem Benutzer die "with`-Identity UserPolicy`" zugewiesen wird, werden die `CsTeamsFilesPolicy` systemeigenen Dateieinstiegspunkte deaktiviert.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Zuweisen einer Richtlinie zum Benutzer

Nachdem Sie die neue Richtlinie erstellt haben, können Sie diese Richtlinie Benutzern mithilfe des `Grant-CsTeamsFilesPolicy` Cmdlets zuweisen.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Aktualisieren der Richtlinie

Wenn Sie die Einstellung der neuen Teams Dateirichtlinie `UserPolicy`ändern müssen, verwenden Sie das `Set-CsTeamsFilePolicy` Cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Entfernen der Richtlinie für die vollständige Liste der Benutzer

Verwenden Sie `Remove-CsTeamsFilesPolicy` das Cmdlet, um die Richtlinie von allen Benutzern zu entfernen, die der Richtlinie `UserPolicy`Teams Dateien zugewiesen sind.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Nachdem Sie Änderungen an der Richtlinie vorgenommen haben, lassen Sie bis zu 12 Stunden zu, bis die Änderungen in den Teams Clients der Benutzer angezeigt werden.
