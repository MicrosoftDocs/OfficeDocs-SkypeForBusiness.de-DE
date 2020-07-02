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
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944112"
---
# <a name="install-microsoft-teams-powershell"></a>Installieren von Microsoft Teams PowerShell

In diesem Artikel wird erläutert, wie Sie das Microsoft Teams PowerShell-Modul mithilfe von [PowerShellGet](/powershell/scripting/gallery/installing-psget)installieren. Diese Anweisungen funktionieren auf [Azure Cloud Shell](/azure/cloud-shell/overview)-, Linux-, macOS-und Windows-Plattformen.

## <a name="requirements"></a>Voraussetzungen

Teams PowerShell kann mit PowerShell-6.2.4 und später auf allen Plattformen verwendet werden. Sie wird auch mit PowerShell 5,1 unter Windows unterstützt. Installieren Sie die [neueste PowerShell-Version](/powershell/scripting/install/installing-powershell) , die für Ihr Betriebssystem verfügbar ist. Teams PowerShell hat keine zusätzlichen Anforderungen, wenn Sie auf PowerShell-6.2.4 und höher ausgeführt werden.

> [!WARNING]
> Es gibt bekannte Probleme mit PowerShell 7 und PowerShell von Teams. Für eine optimale Benutzerfreundlichkeit empfehlen wir, PowerShell 5,1 zu verwenden.

## <a name="install-the-teams-powershell-module"></a>Installieren des Teams PowerShell-Moduls

> [!NOTE]
> Für ein optimales Nutzungserlebnis verwenden Sie entweder allgemeine Verfügbarkeit (GA) oder öffentliche Preview-Module – nicht beide. Sie sind nicht für die Zusammenarbeit vorgesehen.


Verwenden Sie die **PowerShellGet** -Cmdlets, um das PowerShell-Modul von Teams zu installieren. Für die Installation des Moduls für alle Benutzer eines Systems sind erhöhte Berechtigungen erforderlich. Starten Sie die PowerShell-Sitzung mit " **als Administrator ausführen** " in Windows, oder verwenden Sie den `sudo` Befehl unter macOS oder Linux:

```powershell
Install-Module MicrosoftTeams
```

Standardmäßig ist der PowerShell-Katalog (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet**konfiguriert. Wenn Sie das PSGallery zum ersten Mal verwenden, wird die folgende Meldung angezeigt:

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Beantworten `Yes` oder `Yes to All` Fortsetzen der Installation


## <a name="install-teams-powershell-public-preview"></a>Installieren von Teams PowerShell Public Preview

> [!NOTE]
> Wenn Sie die öffentliche Preview-Version von Teams PowerShell verwenden, wird dringend empfohlen, Skype for Business Online Connector zunächst zu deinstallieren.

Das Installieren des Public Preview-Moduls für Teams PowerShell für alle Benutzer in einem System erfordert erhöhte Berechtigungen. Starten Sie die PowerShell-Sitzung mit " **als Administrator ausführen** " in Windows, oder verwenden Sie den `sudo` Befehl unter macOS oder Linux.

Wenn Sie PowerShell 5,1 verwenden, müssen Sie das **PowerShellGet** -Modul vorher aktualisieren. Nachdem Sie **PowerShellGet**aktualisiert haben, schließen Sie eine erhöhte PowerShell-Sitzung, und öffnen Sie Sie erneut, um sicherzustellen, dass die neueste **PowerShellGet** geladen wurde.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Führen Sie den folgenden PowerShell-Befehl aus, um Teams PowerShell Public Preview zu installieren.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a>Installieren des Skype for Business Online-Connectors

> [!WARNING]
> Skype for Business Online Connector ist derzeit Teil von Teams PowerShell Public Preview. Nachdem wir dieses Feature in der GA-Version von Teams PowerShell bereitgestellt haben, steht Skype for Business Online Connector nicht mehr zur Verfügung.

Laden Sie das [Skype for Business PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366)herunter, und installieren Sie es, und führen Sie dann die folgenden Schritte in PowerShell aus.

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>Anmelden

Um mit der Arbeit mit Teams PowerShell zu beginnen, melden Sie sich mit ihren Azure-Anmeldeinformationen an.

> [!NOTE]
> Wenn Sie die neueste Version von [Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/)verwenden, müssen Sie den Skype for Business Online-Connector nicht installieren.

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
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
