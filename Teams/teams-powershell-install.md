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
ms.openlocfilehash: 3a1e969a1310a64a281434a630f4fb608b8cfb30
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947566"
---
# <a name="install-microsoft-teams-powershell-module"></a>Installieren Microsoft Teams PowerShell-Moduls

In diesem Artikel wird erläutert, wie Sie Microsoft Teams PowerShell-Modul mithilfe von PowerShell Gallery installieren. Das Microsoft Teams PowerShell-Modul wird auf allen Windows unterstützt. 

## <a name="requirements"></a>Anforderungen

Microsoft Teams Für das PowerShell-Modul ist PowerShell 5.1 oder höher auf allen Plattformen erforderlich. Installieren Sie [die neueste Version von PowerShell,](/powershell/scripting/install/installing-powershell)die für Ihr Betriebssystem verfügbar   ist. 

Um Ihre PowerShell-Version zu überprüfen, führen Sie in einer PowerShell-Sitzung den folgenden Befehl aus: 

```powershell
$PSVersionTable.PSVersion 
```
Wir empfehlen, das Install-Module-Cmdlet zum Installieren des Microsoft Teams PowerShell-Moduls zu verwenden. 
 
Wenn der PowerShell-Katalog (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet** konfiguriert ist, wird bei der ersten Verwendung des PSGallery die folgende Meldung angezeigt:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Antworten **Sie auf** Ja oder Ja auf **Alle,** um mit der Installation fortzufahren.

## <a name="installing-using-the-powershellgallery"></a>Installieren mit PowerShellGallery

Microsoft Teams Das PowerShell-Modul wird derzeit für die Verwendung mit PowerShell 5.1 auf Windows. Führen Sie die folgenden Schritte aus, um das Modul zu installieren: 

- Aktualisieren Sie [auf Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). Wenn Sie Version Windows 10 1607 oder höher verwenden, ist PowerShell 5.1 bereits installiert. 
- Installieren [.NET Framework Version 4.7.2](/dotnet/framework/install) oder höher. 
- Führen Sie den folgenden Befehl aus, um das neueste PowerShellGet zu installieren:
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- Installieren Sie Teams PowerShell-Modul.

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a>Offlineinstallation 

In einigen Umgebungen ist es nicht möglich, eine Verbindung mit dem PowerShell-Katalog herzustellen. Führen Sie in diesen Fällen die folgenden [manuellen Installationsschritte aus.](https://aka.ms/psgallery-manualdownload)  

## <a name="sign-in"></a>Anmelden

Um mit der Arbeit mit Microsoft Teams PowerShell-Modul zu beginnen, melden Sie sich mit Ihren Azure-Anmeldeinformationen an.

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a>Aktualisieren Teams PowerShell-Moduls

Zum Aktualisieren eines beliebigen PowerShell-Moduls sollten Sie die gleiche Methode zum Installieren des Moduls verwenden. Wenn Sie z. B. "Install-Module" ursprünglich verwendet haben, sollten Sie [Update-Module](/powershell/module/powershellget/update-module) verwenden, um die neueste Version zu erhalten.  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, kann das Modul nicht aktualisiert werden. Schließen Sie PowerShell, und öffnen Sie eine neue PowerShell-Sitzung mit erhöhten Rechten erneut.


## <a name="uninstall-teams-powershell"></a>Deinstallieren Teams PowerShell

Zum Deinstallieren Microsoft Teams PowerShell öffnen Sie eine neue PowerShell-Eingabeaufforderung, und führen Sie die folgenden Schritte aus: 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a>Nächste Schritte 

Jetzt können Sie Ihre E-Microsoft Teams mithilfe Microsoft Teams PowerShell verwalten. Informationen zu den ersten Teams finden Teams unter Verwalten von Teams mit [PowerShell.](teams-powershell-managing-teams.md) 

## <a name="related-topics"></a>Verwandte Themen

[Verwalten Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[Teams PowerShell-Versionshinweise](teams-powershell-release-notes.md)

[Microsoft Teams-Cmdlet-Referenz](/powershell/teams/?view=teams-ps)

[Skype for Business-Cmdlet-Referenz](/powershell/skype/intro?view=skype-ps)
