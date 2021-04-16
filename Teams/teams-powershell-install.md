---
title: Installieren von Microsoft Teams PowerShell
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie Sie die PowerShell-Steuerelemente zum Verwalten von Microsoft Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768339"
---
# <a name="install-microsoft-teams-powershell"></a>Installieren von Microsoft Teams PowerShell

In diesem Artikel wird erläutert, wie Sie das Microsoft Teams PowerShell-Modul mit [PowerShellGet installieren.](/powershell/scripting/gallery/installing-psget) Diese Anweisungen funktionieren auf [Azure Cloud Shell-,](/azure/cloud-shell/overview)Linux-, macOS- und Windows-Plattformen.

## <a name="requirements"></a>Anforderungen

Teams PowerShell erfordert PowerShell 5.1 oder höher auf allen Plattformen. Installieren Sie [die neueste Version von PowerShell,](/powershell/scripting/install/installing-powershell) die für Ihr Betriebssystem verfügbar ist.

> [!NOTE]
> Für optimale Benutzererfahrung empfehlen wir, PowerShell 5.1 zu verwenden.

## <a name="install-the-teams-powershell-module"></a>Installieren des Teams PowerShell-Moduls

> [!NOTE]
> Verwenden Sie zur bestmöglichen Benutzererfahrung entweder die Module Allgemeine Verfügbarkeit (GA) oder Public Preview – nicht beide. Sie sollen nicht zusammenarbeiten.


Verwenden Sie **die PowerShellGet-Cmdlets,** um das Teams PowerShell-Modul zu installieren. Für die Installation des Moduls für alle Benutzer auf einem System sind erhöhte Berechtigungen erforderlich. Starten Sie die PowerShell-Sitzung mithilfe **von Als** Administrator ausführen unter Windows, oder verwenden Sie den `sudo` Befehl unter macOS oder Linux:

```powershell
Install-Module MicrosoftTeams
```

Standardmäßig ist der PowerShell Gallery (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet konfiguriert.** Wenn Sie die PSGallery zum ersten Mal verwenden, wird die folgende Meldung angezeigt:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Antworten **Sie auf** Ja oder Ja zu **Allen,** um mit der Installation fortzufahren.

## <a name="sign-in"></a>Anmelden

Um mit der Arbeit mit Teams PowerShell zu beginnen, melden Sie sich mit Ihren Azure-Anmeldeinformationen an.

> [!NOTE]
> Wenn Sie die neueste version der öffentlichen [Vorschauversion von Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>Anmelden mit MFA und moderner Authentifizierung

 Wenn Ihr Konto die mehrstufige Authentifizierung verwendet, verwenden Sie die Schritte in diesem Abschnitt.

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a>Aktualisieren von Teams PowerShell

Zum Aktualisieren von Teams PowerShell öffnen Sie eine neue Eingabeaufforderung für erhöhte PowerShell, und führen Sie folgendes aus:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, kann das Modul nicht aktualisiert werden. Schließen Sie PowerShell, und öffnen Sie erneut eine neue PowerShell-Sitzung mit erhöhten Rechten.


## <a name="uninstall-teams-powershell"></a>Deinstallieren von Teams PowerShell

Um Teams PowerShell zu deinstallieren, öffnen Sie eine neue Eingabeaufforderung für erhöhte PowerShell, und führen Sie folgendes aus:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, wird das Modul nicht deinstalliert. Schließen Sie PowerShell, und öffnen Sie erneut eine neue PowerShell-Sitzung mit erhöhten Rechten.

## <a name="install-teams-powershell-public-preview"></a>Installieren der öffentlichen Vorschau von Teams PowerShell

> [!NOTE]
> Wenn Sie die Public Preview-Version von Teams PowerShell verwenden, wird dringend empfohlen, zuerst Skype for Business Online Connector zu deinstallieren.

Für die Installation des öffentlichen Teams PowerShell-Vorschaumoduls für alle Benutzer auf einem System sind erhöhte Berechtigungen erforderlich. Starten Sie die PowerShell-Sitzung mit **Ausführen als Administrator** unter Windows, oder verwenden Sie den Befehl unter `sudo` macOS oder Linux.

Wenn Sie PowerShell 5.1 verwenden, müssen Sie das **PowerShellGet-Modul** vorab aktualisieren. Nachdem Sie **PowerShellGet aktualisiert** haben, schließen Sie eine höher gehobene PowerShell-Sitzung, und öffnen Sie sie erneut, um sicherzustellen, dass das neueste **PowerShellGet** geladen wird.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Führen Sie zum Installieren der öffentlichen Vorschau von Teams PowerShell den folgenden PowerShell-Befehl aus.

> [!NOTE]
> Sie finden die neueste Vorschauversion im [PowerShell Gallery](https://www.powershellgallery.com/packages/MicrosoftTeams) oder in PowerShell, indem Sie "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions" ausführen.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a>Nächste Schritte

Jetzt können Sie Teams mit Teams PowerShell verwalten. Erste Schritte finden Sie unter Verwalten von Teams mit [Teams PowerShell.](teams-powershell-managing-teams.md)

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Versionshinweise zu Teams PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdletreferenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdletreferenz](/powershell/skype/intro?view=skype-ps)
