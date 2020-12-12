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
description: Hier erfahren Sie, wie Sie die PowerShell-Steuerelemente für die Verwaltung von Microsoft Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662020"
---
# <a name="install-microsoft-teams-powershell"></a>Installieren von Microsoft Teams PowerShell

In diesem Artikel wird erläutert, wie Sie das Microsoft Teams PowerShell-Modul mithilfe von [PowerShellGet](/powershell/scripting/gallery/installing-psget)installieren. Diese Anweisungen funktionieren auf [Azure Cloud Shell](/azure/cloud-shell/overview)-, Linux-, macOS-und Windows-Plattformen.

## <a name="requirements"></a>Voraussetzungen

Für Teams PowerShell ist PowerShell 5,1 oder höher auf allen Plattformen erforderlich. Installieren Sie die [neueste PowerShell-Version](/powershell/scripting/install/installing-powershell) , die für Ihr Betriebssystem verfügbar ist.

> [!WARNING]
> Es gibt bekannte Probleme mit PowerShell 7 und PowerShell von Teams. Für eine optimale Benutzerfreundlichkeit empfehlen wir, PowerShell 5,1 zu verwenden.

## <a name="install-the-teams-powershell-module"></a>Installieren des Teams PowerShell-Moduls

> [!NOTE]
> Für ein optimales Nutzungserlebnis verwenden Sie entweder allgemeine Verfügbarkeit (GA) oder öffentliche Preview-Module – nicht beide. Sie sind nicht für die Zusammenarbeit vorgesehen.


Verwenden Sie die **PowerShellGet** -Cmdlets, um das PowerShell-Modul von Teams zu installieren. Für die Installation des Moduls für alle Benutzer eines Systems sind erhöhte Berechtigungen erforderlich. Starten Sie die PowerShell-Sitzung mit " **als Administrator ausführen** " in Windows, oder verwenden Sie den `sudo` Befehl unter macOS oder Linux:

```powershell
Install-Module MicrosoftTeams
```

Standardmäßig ist der PowerShell-Katalog (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet** konfiguriert. Wenn Sie das PSGallery zum ersten Mal verwenden, wird die folgende Meldung angezeigt:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Beantworten Sie " **Ja** " oder " **Ja",** um mit der Installation fortzufahren.


## <a name="install-teams-powershell-public-preview"></a>Installieren von Teams PowerShell Public Preview

> [!NOTE]
> Wenn Sie die öffentliche Preview-Version von Teams PowerShell verwenden, wird dringend empfohlen, Skype for Business Online Connector zunächst zu deinstallieren.

Das Installieren des Public Preview-Moduls für Teams PowerShell für alle Benutzer in einem System erfordert erhöhte Berechtigungen. Starten Sie die PowerShell-Sitzung mit " **als Administrator ausführen** " in Windows, oder verwenden Sie den `sudo` Befehl unter macOS oder Linux.

Wenn Sie PowerShell 5,1 verwenden, müssen Sie das **PowerShellGet** -Modul vorher aktualisieren. Nachdem Sie **PowerShellGet** aktualisiert haben, schließen Sie eine erhöhte PowerShell-Sitzung, und öffnen Sie Sie erneut, um sicherzustellen, dass die neueste **PowerShellGet** geladen wurde.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Führen Sie den folgenden PowerShell-Befehl aus, um Teams PowerShell Public Preview zu installieren.

> [!NOTE]
> Sie können die aktuelle Preview-Version im [PowerShell-Katalog](https://www.powershellgallery.com/packages/MicrosoftTeams) oder in PowerShell finden, indem Sie "suchen-Modul Microsoft Teams-AllowPrerelease" ausführen.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>Installieren des Skype for Business Online-Connectors

> [!NOTE]
>
> Skype for Business Online Connector ist derzeit Teil des neuesten Teams PowerShell-Moduls.
> Wenn Sie die neueste Version von [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Anmelden

Um mit der Arbeit mit Teams PowerShell zu beginnen, melden Sie sich mit ihren Azure-Anmeldeinformationen an.

> [!NOTE]
> Wenn Sie die neueste Version von [Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Aktualisieren von Teams PowerShell

Um Teams PowerShell zu aktualisieren, öffnen Sie eine neue erweiterte PowerShell-Eingabeaufforderung, und führen Sie die folgenden Aktionen aus:

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, tritt beim Aktualisieren des Moduls ein Fehler auf. Schließen Sie PowerShell, und öffnen Sie eine neue erhöhte PowerShell-Sitzung erneut.


## <a name="uninstall-teams-powershell"></a>Deinstallieren von Teams PowerShell



Um Teams PowerShell zu deinstallieren, öffnen Sie eine neue erweiterte PowerShell-Eingabeaufforderung, und führen Sie die folgenden Aktionen aus:

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, tritt beim Deinstallieren des Moduls ein Fehler auf. Schließen Sie PowerShell, und öffnen Sie eine neue erhöhte PowerShell-Sitzung erneut.

## <a name="next-steps"></a>Nächste Schritte

Jetzt sind Sie bereit, Teams mithilfe von Teams PowerShell zu verwalten. Weitere Informationen finden Sie unter [Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md) für die ersten Schritte.

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Teams mit PowerShell von Teams](teams-powershell-managing-teams.md)

[Teams PowerShell-Anmerkungen zu dieser Version](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
