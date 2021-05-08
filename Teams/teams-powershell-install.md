---
title: Installieren Microsoft Teams PowerShell
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
description: Erfahren Sie, wie Sie die PowerShell-Steuerelemente zum Verwalten von Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 002f2bc8408536d79274c5e9b001f5e2a5eb55b3
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768339"
---
# <a name="install-microsoft-teams-powershell"></a>Installieren Microsoft Teams PowerShell

In diesem Artikel wird erläutert, wie Sie Microsoft Teams PowerShell-Modul mithilfe von [PowerShellGet installieren.](/powershell/scripting/gallery/installing-psget) Diese Anweisungen funktionieren auf [Azure Cloud Shell-,](/azure/cloud-shell/overview)Linux-, macOS- und Windows Plattformen.

## <a name="requirements"></a>Anforderungen

Teams PowerShell erfordert PowerShell 5.1 oder höher auf allen Plattformen. Installieren Sie [die neueste Version von PowerShell,](/powershell/scripting/install/installing-powershell) die für Ihr Betriebssystem verfügbar ist.

> [!NOTE]
> Für eine optimale Erfahrung empfehlen wir die Verwendung von PowerShell 5.1.

## <a name="install-the-teams-powershell-module"></a>Installieren des Teams PowerShell-Moduls

> [!NOTE]
> Für eine optimale Benutzererfahrung sollten Sie entweder GA-Module (General Availability) oder Public Preview-Module verwenden – nicht beides. Sie sind nicht für die Zusammenarbeit vorgesehen.


Verwenden Sie **die PowerShellGet-Cmdlets** zum Installieren des Teams PowerShell-Moduls. Zum Installieren des Moduls für alle Benutzer auf einem System sind erhöhte Rechte erforderlich. Starten Sie die PowerShell-Sitzung unter Verwendung von Als Administrator **ausführen** in Windows oder verwenden Sie den Befehl `sudo` unter macOS oder Linux:

```powershell
Install-Module MicrosoftTeams
```

Standardmäßig ist der PowerShell-Katalog (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet konfiguriert.** Bei der ersten Verwendung von PSGallery wird die folgende Meldung angezeigt:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Antworten **Sie auf** Ja oder Ja auf **Alle,** um mit der Installation fortzufahren.

## <a name="sign-in"></a>Anmelden

Um mit der Arbeit mit Teams PowerShell zu beginnen, melden Sie sich mit Ihren Azure-Anmeldeinformationen an.

> [!NOTE]
> Wenn Sie die neueste Version Teams [PowerShell Public Preview-Version](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online Connector nicht installieren.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>Anmelden mit MFA und moderner Authentifizierung

 Wenn Ihr Konto die mehrstufige Authentifizierung verwendet, folgen Sie den Schritten in diesem Abschnitt.

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>
```

## <a name="update-teams-powershell"></a>Aktualisieren Teams PowerShell

Zum Aktualisieren Teams PowerShell öffnen Sie eine neue PowerShell-Eingabeaufforderung mit erhöhten Rechten, und führen Sie Folgendes aus:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, kann das Modul nicht aktualisiert werden. Schließen Sie PowerShell, und öffnen Sie eine neue PowerShell-Sitzung mit erhöhten Rechten erneut.


## <a name="uninstall-teams-powershell"></a>Deinstallieren Teams PowerShell

Zum Deinstallieren Teams PowerShell öffnen Sie eine neue PowerShell-Eingabeaufforderung mit erhöhten Rechten, und führen Sie Folgendes aus:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, kann das Modul nicht deinstalliert werden. Schließen Sie PowerShell, und öffnen Sie eine neue PowerShell-Sitzung mit erhöhten Rechten erneut.

## <a name="install-teams-powershell-public-preview"></a>Installieren Teams PowerShell Public Preview

> [!NOTE]
> Wenn Sie die Public Preview-Version von Teams PowerShell verwenden, empfehlen wir dringend, zuerst den Online Connector Skype for Business zu deinstallieren.

Zum Installieren Teams öffentlichen PowerShell-Vorschaumoduls für alle Benutzer in einem System sind erhöhte Rechte erforderlich. Starten Sie die PowerShell-Sitzung unter Verwendung von Als Administrator **ausführen** in Windows oder verwenden Sie den Befehl `sudo` unter macOS oder Linux.

Wenn Sie PowerShell 5.1 verwenden, müssen Sie das **PowerShellGet-Modul** vorab aktualisieren. Schließen Sie nach dem **Aktualisieren von PowerShellGet** eine PowerShell-Sitzung mit erhöhten Rechten, und öffnen Sie sie erneut, um sicherzustellen, dass das neueste **PowerShellGet** geladen wird.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Zum Installieren Teams PowerShell Public Preview führen Sie den folgenden PowerShell-Befehl aus.

> [!NOTE]
> Sie finden die neueste Vorschauversion im [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams) oder in PowerShell, indem Sie "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions" ausführen.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="next-steps"></a>Nächste Schritte

Jetzt können Sie Ihre E-Teams mithilfe Teams PowerShell verwalten. Informationen zu den ersten Teams finden Teams unter Verwalten von Teams mit [PowerShell.](teams-powershell-managing-teams.md)

## <a name="related-topics"></a>Verwandte Themen

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Teams PowerShell-Versionshinweise](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)
