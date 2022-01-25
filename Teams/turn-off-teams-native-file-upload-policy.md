---
title: Deaktivieren der Teams Systemeigene Hochladen"-Richtlinie
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: Erfahren Sie, wie Sie die Datenschutzrichtlinie mithilfe von PowerShell Teams, festlegen, zuweisen und anpassen.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192494"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Deaktivieren der Teams Systemeigene Hochladen"-Richtlinie

Microsoft Teams verwendet OneDrive und SharePoint (ODSP) zum Speichern und Freigeben von Inhalten, aber einige Organisationen und Benutzer bevorzugen möglicherweise Speicheranbieter von Drittanbietern.  

Wenn Sich Ihre Organisation für einen Drittanbieter für die Speicherung von Inhalten entscheidet, müssen Sie den Parameter in der Richtlinie Teams ``NativeFileEntryPoints`` deaktivieren. Dieser Parameter ist standardmäßig aktiviert, wodurch die Option zum Hochladen von Inhalten aus ODSP in Teams oder Kanälen angezeigt wird.

Dieser Artikel hilft Ihnen beim Erstellen, Festlegen, Zuweisen und Entfernen des ``NativeFileEntryPoints`` Parameters mithilfe von PowerShell.

>[!NOTE]
>Wenn die richtlinie "Teams-Dateien" deaktiviert ist, können Benutzer in Teams keine Zugriffspunkte für OneDrive und SharePoint (ODSP) sehen, aber die Erstellung neuer Teams und Kanäle löst weiterhin die Generation übereinstimmender SharePoint-Bibliotheken aus.

## <a name="prepare-to-update-the-teams-files-policy"></a>Vorbereiten der Updaterichtlinie für Teams Dateien

### <a name="set-up-microsoft-powershell"></a>Einrichten von Microsoft PowerShell

Derzeit kann diese Richtlinie im Admin Center Teams geändert werden. Der Mandantenadministrator Microsoft 365 Ihrer Organisation muss die Änderungen mithilfe der PowerShell-Cmdlets vornehmen, die weiter später in diesem Artikel erläutert werden.

Informationen zum Installieren des PowerShell Teams Moduls mithilfe des PowerShell-Katalogs finden Sie unter [Installieren Microsoft Teams PowerShell-Moduls.](teams-powershell-install.md)

Informationen zum Installieren oder Herunterladen des Teams PowerShell-Moduls finden Sie im [PowerShell-Katalog für Microsoft Teams.](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)

Weitere Informationen zum Einrichten von PowerShell für die Teams finden Sie unter Verwalten von Teams [mit Microsoft Teams PowerShell.](teams-powershell-managing-teams.md)

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Drittanbieter-Apps im Teams Admin Center zulassen

Dieser Schritt ist nicht erforderlich, um die Teams-Dateirichtlinie zu ändern, aber er ist erforderlich, wenn Sie bereit sind, Ihren Drittanbieterspeicheranbieter in die Benutzererfahrung Teams integrieren.

Ihr Microsoft 365 muss die Richtlinie "Drittanbieter-Apps zulassen" im Teams Admin Center aktivieren.

Informationen zum Zulassen von Drittanbieter- oder benutzerdefinierten Apps finden Sie unter Verwalten von organisationsweiten Apps-Einstellungen unter Verwalten Ihrer Apps [im Microsoft Teams Admin Center.](/microsoftteams/manage-apps#manage-org-wide-app-settings)

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>Deaktivieren von NativeFileEntryPoints für den gesamten Mandanten

Wenn Sie ``-Identity`` den Parameter auf ``Global`` festlegen, werden die Richtlinieneinstellungen auf alle Benutzer in Ihrer Organisation angewendet.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>Beispiel für ein PowerShell-Richtlinien-Cmdlet für den gesamten Mandanten

Mit diesem PowerShell-Beispielbefehl wird der ``NativeFileEntryPoints`` -Parameter für ``Disabled`` den gesamten Mandanten auf festgelegt.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>Überprüfen des Status Ihres Mandanten  

Verwenden Sie das Cmdlet, um den aktuellen Status der Richtlinie Teams Dateien Ihres Mandanten ``Get-CsTeamsFilesPolicy`` anzeigen.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>Aktivieren oder Deaktivieren des systemeigenen Dateiuploadpunkts

Um den systemeigenen Dateiuploadpunkt für Ihren gesamten Mandanten zu aktivieren oder zu deaktivieren, legen Sie den -Parameter ``NativeFileEntryPoints`` auf oder ``Enabled`` ``Disabled`` vor.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>Entfernen der Richtlinie für Ihre Benutzer

Zum Entfernen der Teams"-Richtlinie für Ihre Benutzer verwenden Sie das ``Remove-CsTeamsFilesPolicy`` Cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>Deaktivieren von NativeFileEntryPoints für bestimmte Benutzer

Sie können auch die Richtlinie Teams Dateien für bestimmte Benutzer aktualisieren, indem Sie eine neue Teams-Richtlinienzeichenfolge erstellen und die neu erstellte Richtlinie ``-Identity`` Benutzern zuweisen.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>Beispiel für ein PowerShell-Richtlinien-Cmdlet für bestimmte Benutzer

Dieser PowerShell-Beispielbefehl erstellt einen neuen mit dem Namen ``CsTeamsFilesPolicy`` als und dem auf ``-Identity`` ``UserPolicy`` ``NativeFileEntryPoints`` festgelegten ``Disabled`` Parameter.

Wenn einem Benutzer mit zugewiesen ``CsTeamsFilesPolicy`` ``-Identity UserPolicy`` wird, werden die systemeigenen Dateieinstiegspunkte deaktiviert.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>Zuweisen einer Richtlinie zu einem Benutzer

Nachdem Sie die neue Richtlinie erstellt haben, können Sie diese Richtlinie mithilfe des ``Grant-CsTeamsFilesPolicy`` Cmdlets Benutzern zuweisen.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>Aktualisieren der Richtlinie

Wenn Sie die Einstellung der neuen Dateirichtlinie Teams ``UserPolicy`` müssen, verwenden Sie das ``Set-CsTeamsFilePolicy`` Cmdlet.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>Entfernen der Richtlinie für die vollständige Liste der Benutzer

Wenn Sie die Richtlinie von allen Benutzern entfernen möchten, die der Richtlinie Teams Dateien zugewiesen ``UserPolicy`` sind, verwenden Sie das ``Remove-CsTeamsFilesPolicy`` Cmdlet.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> Nachdem Sie Änderungen an der Richtlinie vorgenommen haben, kann es bis zu 12 Stunden dauern, bis die Änderungen in den Benutzerclients Teams werden.
