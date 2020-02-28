---
title: Installieren von Microsoft Teams mithilfe von MSI über den Microsoft Endpoint Configuration Manager
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Administratoren können das Microsoft Teams-MSI-Paket für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c048e321241f4403fbb69f71e56b3fc179346951
ms.sourcegitcommit: c16451519e05b47bbb77e09dacd13ff212617e91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "42327827"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Installieren von Microsoft Teams mit Microsoft Endpoint Configuration Manager

> [!Tip]
> Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)

Zur Verwendung von Microsoft Endpoint Configuration Manager oder von Gruppenrichtlinien oder von Drittanbieter-Verteilungsmechanismen für eine breite Bereitstellung hat Microsoft MSI-Dateien bereitgestellt (sowohl 32-Bit als auch 64-Bit), die Administratoren für die Massenbereitstellung von Teams zur Auswahl von Benutzern verwenden können, oder Computer. Administratoren können Microsoft Teams mit diesen Dateien remote bereitstellen, damit die Benutzer die Teams-App nicht manuell herunterladen müssen. Die bereitgestellte Microsoft Teams-App wird für alle Benutzer, die sich bei dem jeweiligen Computer anmelden, automatisch gestartet. (Sie können das automatische Starten nach der Installation der App deaktivieren. [Siehe unten](#disable-auto-launch-for-the-msi-installer).) Wir empfehlen, das Paket auf dem Computer bereitzustellen, damit alle neuen Benutzer des Computers ebenfalls von dieser Bereitstellung profitieren.

Hierbei handelt es sich um die Links zu den MSI-Dateien:


|Entität  |32-Bit      |64-Bit      |
|---------|---------|---------|
|Handels     | [32-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Bundesregierung-gcc     | [32-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Bundesregierung-gcc-Höchststand    | [32-Bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64-Bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Bundesregierung-DoD     | [32-Bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-Bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

Teams können auch in eine Bereitstellung von Office 365 ProPlus einbezogen werden. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams mit Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Weitere Informationen zum Microsoft Endpoint Configuration Manager finden Sie unter [Was ist Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Bereitstellungsverfahren (empfohlen)

1. Rufen Sie das neueste Paket ab.
2. Verwenden Sie die vorausgefüllten Standardeinstellungen.
3. Stellen Sie die Software auf Computern bereit, wenn dies möglich ist.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Funktionsweise des MSI-Pakets für Microsoft Teams

### <a name="pc-installation"></a>PC-Installation

Das MSI-Paket für Microsoft Teams legt ein Installationsprogramm in „Programme“ ab. Wenn sich ein Benutzer in einem neuen Windows-Benutzerprofil anmeldet, wird das Installationsprogramm gestartet, und eine Kopie der Teams-APP wird im `AppData` Ordner dieses Benutzers installiert. Wenn ein Benutzer bereits die Teams-App im `AppData` Ordner installiert hat, überspringt das MSI-Installationsprogramm den Prozess für diesen Benutzer.

Sie sollten das MSI-Paket nicht zum Bereitstellen von Updates verwenden, da der Client automatisch aktualisiert wird, wenn er erkennt, dass über den Dienst eine neue Version verfügbar ist. Verwenden Sie zum erneuten Bereitstellen des neuesten Installationsprogramms das unten beschriebene Verfahren für die erneute Bereitstellung von MSI-Paketen. Wenn Sie eine ältere Version des MSI-Pakets bereitstellen, wird der Client automatisch aktualisiert (außer in VDI-Umgebungen), sofern dies für den Benutzer möglich ist. Falls eine sehr alte Version bereitgestellt wird, löst das MSI-Paket ein App-Update aus, bevor der Benutzer Microsoft Teams verwenden kann.

> [!Important]
> Sie sollten die standardmäßigen Installationsspeicherorte nicht ändern, da dies den Aktualisierungsablauf behindern kann. Eine zu alte Version führt letztlich dazu, dass die Benutzer nicht auf den Dienst zugreifen können.

#### <a name="target-computer-requirements"></a>Anforderungen an die Zielcomputer

- .NET Framework 4.5 oder höher
- Windows 8,1 oder höher
- Windows Server 2012 R2 oder höher
- 3 GB Speicherplatz auf dem Datenträger für jedes Benutzerprofil (empfohlen)

### <a name="vdi-installation"></a>VDI-Installation

Eine vollständige Anleitung zum Bereitstellen der Desktop-App "Teams" auf VDI finden Sie unter [Teams für virtualisierte Desktopinfrastruktur](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Verfahren für die Bereinigung und erneute Bereitstellung

Wenn ein Benutzer Microsoft Teams in seinem Benutzerprofil deinstalliert, erkennt das MSI-Installationsprogramm, dass der Benutzer die Microsoft Teams-App deinstalliert hat, und installiert Microsoft Teams für dieses Benutzerprofil nicht mehr. Um Microsoft Teams für diesen Benutzer auf einem bestimmten Computer, auf dem Microsoft Teams deinstalliert wurde, erneut bereitzustellen, gehen Sie so vor:

1. Deinstallieren Sie die installierte Microsoft Teams-App für alle Benutzerprofile.
2. Löschen Sie nach der Deinstallation das Verzeichnis rekursiv `%localappdata%\Microsoft\Teams\`unter.
3. Stellen Sie das MSI-Paket auf dem entsprechenden Computer erneut bereit.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Verhindern, dass Teams nach der Installation automatisch gestartet werden

Das Standardverhalten der MSI-Anwendung besteht darin, die Teams-APP zu installieren, sobald sich ein Benutzer anmeldet und dann Teams automatisch startet. Wenn Sie nicht möchten, dass Teams nach der Installation automatisch für Benutzer gestartet werden, können Sie mithilfe von Gruppenrichtlinien eine Richtlinieneinstellung festlegen oder den automatischen Start für das MSI-Installationsprogramm deaktivieren.

#### <a name="use-group-policy-recommended"></a>Verwenden von Gruppenrichtlinien (empfohlen)

Aktivieren Sie das **automatische Starten von Microsoft Teams nach der Installations** Gruppenrichtlinieneinstellung verhindern. Diese Richtlinieneinstellung finden Sie unter Benutzer sich Computerkonfiguration\Richtlinien\Administrative Vorlagen\Microsoft Teams. Dies ist die empfohlene Methode, da Sie die Richtlinieneinstellung entsprechend den Anforderungen Ihrer Organisation deaktivieren oder aktivieren können.

Wenn Sie diese Richtlinieneinstellung vor der Installation von Teams aktivieren, werden die Teams nicht automatisch gestartet, wenn sich Benutzer bei Windows anmelden. Nachdem sich ein Benutzer zum ersten Mal bei Teams angemeldet hat, wird das Team automatisch gestartet, wenn sich der Benutzer das nächste Mal anmeldet.

Weitere Informationen finden Sie unter [Verwenden von Gruppenrichtlinien, um zu verhindern, dass Teams nach der Installation automatisch gestartet](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)werden.

> [!CAUTION]
> Wenn Sie bereits Teams bereitgestellt haben und diese Richtlinie für die Deaktivierung von "Teams Autostart" festlegen möchten, legen Sie zunächst die Gruppenrichtlinieneinstellung auf den gewünschten Wert fest, und führen Sie dann das [Skript "Teams Autostart-Reset](scripts/powershell-script-teams-reset-autostart.md) " für einzelne Benutzer aus.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Deaktivieren des automatischen Starts für das MSI-Installationsprogramm

Sie können den automatischen Start für das MSI-Installationsprogramm deaktivieren, indem Sie den Parameter **Options = "noAutoStart = true"** wie folgt verwenden.  

Für die 32-Bit-Version

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```

Für die 64-Bit-Version

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

Wenn sich ein Benutzer bei Windows anmeldet, wird Teams mit dem MSI installiert, und eine Verknüpfung zum Starten von Teams wird dem Desktop des Benutzers hinzugefügt. Teams werden erst gestartet, wenn der Benutzer Teams manuell startet. Nachdem der Benutzer Teams manuell gestartet hat, werden die Teams automatisch gestartet, wenn sich der Benutzer anmeldet.

> [!Note]
> Wenn Sie das MSI-Paket manuell ausführen, sollten Sie es unbedingt mit erweiterten Berechtigungen ausführen. Auch wenn Sie es als Administrator ausführen, ohne es mit erhöhten Berechtigungen auszuführen, kann das Installationsprogramm die Option zum Deaktivieren des automatischen Starts nicht konfigurieren.
