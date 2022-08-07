---
title: Deaktivieren der Richtlinie für das systemeigene Hochladen von Teams-Dateien
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Erfahren Sie, wie Sie die Teams-Dateirichtlinie mithilfe von PowerShell erstellen, festlegen, zuweisen und anpassen.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1993371099d0712d21106987f21575e85e181ad7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268927"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Deaktivieren der Richtlinie für das systemeigene Hochladen von Teams-Dateien

Microsoft Teams verwendet OneDrive und SharePoint zum Speichern und Freigeben von Inhalten, aber einige Organisationen und Benutzer bevorzugen möglicherweise Speicheranbieter von Drittanbietern.  

Wenn Ihre Organisation einen Drittanbieter für die Inhaltsspeicherung wählt, müssen Sie den `NativeFileEntryPoints` Parameter in der Microsoft Teams-Dateirichtlinie deaktivieren. Dieser Parameter ist standardmäßig aktiviert, wodurch die Option zum Hochladen von Inhalten aus OneDrive oder SharePoint in Teams-Chats oder -Kanäle angezeigt wird.

Dieser Artikel hilft Ihnen beim Erstellen, Festlegen, Zuweisen und Entfernen des `NativeFileEntryPoints` Parameters mithilfe von PowerShell.

>[!NOTE]
>Wenn die Richtlinie "Teams-Dateien" deaktiviert ist, werden Benutzern keine Zugriffspunkte für OneDrive und SharePoint in Teams angezeigt, aber die Erstellung neuer Teams und Kanäle löst weiterhin die Generierung übereinstimmener SharePoint-Bibliotheken aus.

## <a name="prepare-to-update-the-teams-files-policy"></a>Vorbereiten der Aktualisierung der Teams-Dateirichtlinie

### <a name="set-up-microsoft-powershell"></a>Einrichten von Microsoft PowerShell

Derzeit kann diese Richtlinie im Teams Admin Center nicht geändert werden. Der Microsoft 365-Mandantenadministrator Ihrer Organisation muss die Änderungen mithilfe der PowerShell-Cmdlets vornehmen, die weiter unten in diesem Artikel beschrieben werden.

Erfahren Sie, wie Sie das PowerShell Teams-Modul mithilfe von PowerShell-Katalog installieren, indem [Sie "Microsoft Teams PowerShell-Modul installieren"](teams-powershell-install.md) lesen.

Informationen zum Installieren oder Herunterladen des Teams PowerShell-Moduls finden Sie [unter PowerShell-Katalog für Microsoft Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Weitere Informationen zum Einrichten von PowerShell für die Teams-Verwaltung finden Sie unter [Verwalten von Teams mit Microsoft Teams PowerShell](teams-powershell-managing-teams.md).

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Zulassen von Drittanbieter-Apps in Teams Admin Center

Dieser Schritt ist nicht erforderlich, um die Teams-Dateirichtlinie zu ändern, aber er ist erforderlich, wenn Sie bereit sind, Ihren Drittanbieter-Speicheranbieter in die Teams-Umgebung Ihrer Benutzer zu integrieren.

Ihr Microsoft 365-Mandantenadministrator muss die Richtlinie "Apps von Drittanbietern zulassen" im Teams Admin Center aktivieren.

Informationen zum Zulassen von Drittanbieter- oder benutzerdefinierten Apps finden Sie unter Verwalten organisationsweiter Apps-Einstellungen unter ["Verwalten Ihrer Apps" im Microsoft Teams Admin Center](/microsoftteams/manage-apps#manage-org-wide-app-settings).

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Deaktivieren von NativeFileEntryPoints für den gesamten Mandanten

Durch Festlegen des `-Identity` Parameters werden `Global` die Richtlinieneinstellungen auf alle Benutzer in Ihrer Organisation angewendet.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Beispiel-PowerShell-Richtlinien-Cmdlet für den gesamten Mandanten

Mit diesem PowerShell-Beispielbefehl wird der`NativeFileEntryPoints` Parameter `Disabled` für den gesamten Mandanten festgelegt.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Überprüfen des Status Ihres Mandanten  

Verwenden Sie `Get-CsTeamsFilesPolicy` das Cmdlet, um den aktuellen Status der Teams-Dateirichtlinie Ihres Mandanten anzuzeigen.

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

Verwenden Sie `Remove-CsTeamsFilesPolicy` das Cmdlet, um die Teams-Dateirichtlinie für Ihre Benutzer zu entfernen.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Deaktivieren von NativeFileEntryPoints für bestimmte Benutzer

Sie können auch die Teams-Dateirichtlinie für bestimmte Benutzer aktualisieren, indem Sie eine neue Richtlinienzeichenfolge `-Identity` für Teams-Dateien erstellen und benutzern die neu erstellte Richtlinie zuweisen.

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

Wenn Sie die Einstellung der neuen Teams-Dateirichtlinie `UserPolicy`ändern müssen, verwenden Sie das `Set-CsTeamsFilePolicy` Cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Entfernen der Richtlinie für die vollständige Liste der Benutzer

Verwenden Sie das Cmdlet, um die Richtlinie von allen Benutzern zu entfernen, die `Remove-CsTeamsFilesPolicy` der Teams-Dateirichtlinie `UserPolicy`zugewiesen sind.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Nachdem Sie Änderungen an der Richtlinie vorgenommen haben, lassen Sie bis zu 12 Stunden zeit, bis die Änderungen in den Teams-Clients der Benutzer angezeigt werden.
