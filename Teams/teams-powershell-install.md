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
description: Erfahren Sie, wie Sie die PowerShell-Steuerelemente zum Verwalten von Microsoft Teams verwenden.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58d64a64fd7c9714e84042e4e1aa1be3eb4505db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682006"
---
# <a name="install-microsoft-teams-powershell-module"></a>Installieren Microsoft Teams PowerShell-Moduls

In diesem Artikel wird erläutert, wie Sie das Microsoft Teams PowerShell-Modul mithilfe von PowerShell-Katalog installieren. Das Microsoft Teams PowerShell-Modul wird auf allen Windows Plattformen unterstützt. Mac und Linux werden nicht unterstützt.

## <a name="requirements"></a>Anforderungen

Microsoft Teams PowerShell-Modul erfordert PowerShell 5.1 oder höher auf allen Plattformen. Installieren Sie die [neueste Version von PowerShell](/powershell/scripting/install/installing-powershell) , die für Ihr Betriebssystem verfügbar ist.

Um Ihre PowerShell-Version zu überprüfen, führen Sie den folgenden Befehl in einer PowerShell-Sitzung aus:

```powershell
$PSVersionTable.PSVersion
```

Es wird empfohlen, das Install-Module-Cmdlet zum Installieren des Microsoft Teams PowerShell-Moduls zu verwenden.

Wenn PowerShell-Katalog (PSGallery) nicht als vertrauenswürdiges Repository für **PowerShellGet** konfiguriert ist, wird bei der ersten Verwendung der PSGallery die folgende Meldung angezeigt:

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Antworten Sie auf **"Ja** " oder " **Ja für alle** ", um mit der Installation fortzufahren.

## <a name="installing-using-the-powershellgallery"></a>Installieren mithilfe von PowerShellGallery

Microsoft Teams PowerShell-Modul wird derzeit für die Verwendung mit PowerShell 5.1 auf Windows unterstützt. Führen Sie die folgenden Schritte aus, um das Modul zu installieren:

- Auf [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell) aktualisieren. Wenn Sie mit Windows 10 Version 1607 oder höher arbeiten, ist PowerShell 5.1 bereits installiert.
- Installieren Sie [.NET Framework 4.7.2](/dotnet/framework/install) oder höher.
- Führen Sie den folgenden Befehl aus, um das neueste PowerShellGet zu installieren:

  ```powershell
  Install-Module -Name PowerShellGet -Force -AllowClobber
  ```

- Installieren Sie das Teams PowerShell-Modul.

  ```powershell
  Install-Module -Name MicrosoftTeams -Force -AllowClobber
  ```

## <a name="offline-installation"></a>Offlineinstallation

In einigen Umgebungen ist es nicht möglich, eine Verbindung mit dem PowerShell-Katalog herzustellen. Führen Sie in diesen Situationen die [folgenden manuellen Installationsschritte](https://aka.ms/psgallery-manualdownload) aus.

## <a name="sign-in"></a>Anmelden

Um mit Microsoft Teams PowerShell-Modul zu arbeiten, melden Sie sich mit Ihren Azure-Anmeldeinformationen an.

```PowerShell
Connect-MicrosoftTeams
```

## <a name="update-teams-powershell-module"></a>Aktualisieren Teams PowerShell-Moduls

Zum Aktualisieren eines PowerShell-Moduls sollten Sie dieselbe Methode verwenden, die zum Installieren des Moduls verwendet wird. Wenn Sie z. B. "Install-Module" ursprünglich verwendet haben, sollten Sie [Update-Module](/powershell/module/powershellget/update-module) verwenden, um die neueste Version abzurufen.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Wenn Teams PowerShell bereits in Ihre PowerShell-Sitzung importiert wurde, schlägt das Aktualisieren des Moduls fehl. Schließen Sie PowerShell, und öffnen Sie erneut eine neue PowerShell-Sitzung mit erhöhten Rechten.

## <a name="uninstall-teams-powershell"></a>Deinstallieren Teams PowerShell

Um Microsoft Teams PowerShell zu deinstallieren, öffnen Sie eine neue PowerShell-Eingabeaufforderung, und führen Sie Folgendes aus:

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions
```

## <a name="next-steps"></a>Nächste Schritte

Jetzt können Sie Microsoft Teams mit Microsoft Teams PowerShell verwalten. Weitere Informationen zu den ersten Schritte finden Sie unter [Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md).

## <a name="related-topics"></a>Verwandte Themen

[Verwalten von Teams mit Teams PowerShell](teams-powershell-managing-teams.md)

[versionshinweise zu Teams PowerShell](teams-powershell-release-notes.md)

[Microsoft Teams Cmdlet-Referenz](/powershell/teams/)

[Skype for Business Cmdlet-Referenz](/powershell/skype/intro)
