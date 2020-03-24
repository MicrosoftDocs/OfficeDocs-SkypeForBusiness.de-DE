---
title: Installieren von Microsoft Teams mit MSI über Microsoft Endpoint Configuration Manager
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
ms.openlocfilehash: 084f6d4587bc279c4387cf44b8ed29d38d51d4a6
ms.sourcegitcommit: 613665c866f6fd0febfa6e26ad718241cdfbb207
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42937599"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Installieren von Microsoft Teams mit Microsoft Endpoint Configuration Manager

> [!Tip]
> Schauen Sie sich die folgende Sitzung an, um mehr über die Vorteile des Windows-Desktop Clients, die Vorgehensweise für die Planung und die Bereitstellung zu erfahren: [Teams Windows-Desktop Client](https://aka.ms/teams-clients).

Wenn Sie für die allgemeine Bereitstellung Microsoft Endpoint Configuration Manager, Gruppenrichtlinien oder Verteilungsmethoden von Drittanbietern verwenden möchten: Microsoft hat MSI-Dateien (sowohl 32- als auch 64-Bit-Versionen) bereitgestellt, die Administratoren für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden können. Administratoren können Microsoft Teams mit diesen Dateien remote bereitstellen, damit die Benutzer die Teams-App nicht manuell herunterladen müssen. Die bereitgestellte Microsoft Teams-App wird für alle Benutzer, die sich bei dem jeweiligen Computer anmelden, automatisch gestartet. (Sie können das automatische Starten nach der Installation der App deaktivieren. [Siehe unten](#disable-auto-launch-for-the-msi-installer).) Wir empfehlen, das Paket auf dem Computer bereitzustellen, damit alle neuen Benutzer des Computers ebenfalls von dieser Bereitstellung profitieren.

Hier sind die Links zu den MSI-Dateien:


|Entität  |32-Bit      |64-Bit      |
|---------|---------|---------|
|Commercial     | [32-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|Bundesbehörden – GCC     | [32-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|Bundesbehörden – GCC High    | [32-Bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64-Bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|Bundesbehörden – DoD     | [32-Bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-Bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

> [!NOTE]
> Installieren Sie die 64-Bit-Version von Teams unter 64-Bit-Betriebssystemen. Wenn Sie versuchen, die 64-Bit-Version von Teams auf einem 32-Bit-Betriebssystem zu installieren, ist die Installation nicht erfolgreich, und es wird derzeit keine Fehlermeldung angezeigt.

Teams können auch in eine Bereitstellung von Office 365 ProPlus einbezogen werden. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams mit Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).

> [!Note]
> Weitere Informationen zum Microsoft Endpoint Configuration Manager finden Sie unter [Was ist Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>Bereitstellungsverfahren (empfohlen)

1. Rufen Sie das neueste Paket ab.
2. Verwenden Sie die vorausgefüllten Standardeinstellungen.
3. Stellen Sie die Software auf Computern bereit, wenn dies möglich ist.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Funktionsweise des MSI-Pakets für Microsoft Teams

### <a name="pc-installation"></a>PC-Installation

Das MSI-Paket für Microsoft Teams legt ein Installationsprogramm in „Programme“ ab. Wenn sich ein Benutzer bei einem neuen Windows-Benutzerprofil anmeldet, wird das Installationsprogramm gestartet und im `AppData`-Ordner des Benutzers eine Kopie der Microsoft Teams-App installiert. Wenn die Microsoft Teams-App bereits im `AppData`-Ordner des Benutzers installiert ist, überspringt das MSI-Installationsprogramm den Prozess für diesen Benutzer.

Sie sollten das MSI-Paket nicht zum Bereitstellen von Updates verwenden, da der Client automatisch aktualisiert wird, wenn er erkennt, dass über den Dienst eine neue Version verfügbar ist. Verwenden Sie zum erneuten Bereitstellen des neuesten Installationsprogramms das unten beschriebene Verfahren für die erneute Bereitstellung von MSI-Paketen. Wenn Sie eine ältere Version des MSI-Pakets bereitstellen, wird der Client automatisch aktualisiert (außer in VDI-Umgebungen), sofern dies für den Benutzer möglich ist. Falls eine sehr alte Version bereitgestellt wird, löst das MSI-Paket ein App-Update aus, bevor der Benutzer Microsoft Teams verwenden kann.

> [!Important]
> Sie sollten die standardmäßigen Installationsspeicherorte nicht ändern, da dies den Aktualisierungsablauf behindern kann. Eine zu alte Version führt letztlich dazu, dass die Benutzer nicht auf den Dienst zugreifen können.

#### <a name="target-computer-requirements"></a>Anforderungen an die Zielcomputer

- .NET Framework 4.5 oder höher
- Windows 8.1 oder höher
- Windows Server 2012 R2 oder höher
- 3 GB Speicherplatz auf dem Datenträger für jedes Benutzerprofil (empfohlen)

### <a name="vdi-installation"></a>VDI-Installation

Umfassende Anleitungen zum Bereitstellen der Teams-Desktop-App auf VDI finden Sie unter [Teams für virtualisierte Desktopinfrastruktur](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Verfahren für die Bereinigung und erneute Bereitstellung

Wenn ein Benutzer Teams aus seinem Benutzerprofil deinstalliert, wird das MSI-Installationsprogramm nachvollziehen, dass der Benutzer die Teams-APP deinstalliert hat und keine Teams mehr für dieses Benutzerprofil installiert hat. Um Microsoft Teams für diesen Benutzer auf einem bestimmten Computer, auf dem Microsoft Teams deinstalliert wurde, erneut bereitzustellen, gehen Sie so vor:

1. Deinstallieren Sie die für jedes Benutzerprofil installierte Team-app.
2. Löschen Sie nach der Deinstallation das Verzeichnis rekursiv unter `%localappdata%\Microsoft\Teams\`.
3. Stellen Sie das MSI-Paket auf dem entsprechenden Computer erneut bereit.

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Verhindern, dass Microsoft Teams nach der Installation automatisch gestartet wird

Standardmäßig installiert das MSI-Paket die Teams-App, sobald sich ein Benutzer anmeldet, und startet Teams dann automatisch. Wenn Sie nicht möchten, dass Teams nach der Installation für Benutzer automatisch gestartet wird, können Sie mithilfe von Gruppenrichtlinien eine Richtlinieneinstellung festlegen oder den automatischen Start für das MSI-Installationsprogramm deaktivieren.

### <a name="use-group-policy-recommended"></a>Verwenden von Gruppenrichtlinien (empfohlen)

Aktivieren Sie die Gruppenrichtlinie zum **Verhindern, dass Microsoft Teams nach der Installation automatisch gestartet wird**. Sie finden diese Richtlinieneinstellung unter: Computerkonfiguration\Richtlinien\Administrative Vorlagen\Microsoft Teams. Dies ist die empfohlene Methode, da Sie die Richtlinieneinstellung entsprechend den Anforderungen Ihrer Organisation deaktivieren oder aktivieren können.

Aktivieren Sie diese Richtlinieneinstellung vor der Installation von Teams, wird es nicht automatisch gestartet, wenn sich Benutzer bei Windows anmelden. Nachdem sich ein Benutzer zum ersten Mal bei Teams angemeldet hat, wird es bei der nächsten Anmeldung des Benutzers automatisch gestartet.

Lesen Sie [Verwenden der Gruppenrichtlinie zum Verhindern, dass Microsoft Teams nach der Installation automatisch gestartet wird](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation), um mehr zu erfahren.

> [!CAUTION]
> Wenn Sie Teams bereits bereitgestellt haben und diese Richtlinie so einrichten möchten, dass der automatische Start von Teams deaktiviert wird, legen Sie zuerst die Gruppenrichtlinieneinstellung auf den gewünschten Wert fest, und führen Sie dann das [Teams-Autostart-Zurücksetzungsskript](scripts/powershell-script-teams-reset-autostart.md) auf Benutzerbasis aus.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Deaktivieren des automatischen Starts für das MSI-Installationsprogramm

Sie können den automatischen Start für das MSI-Installationsprogramm deaktivieren, indem Sie den Parameter **OPTIONS="noAutoStart=true"** wie folgt verwenden.  

Für die 32-Bit-Version:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Für die 64-Bit-Version:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Wenn sich ein Benutzer bei Windows anmeldet, wird Teams mit dem MSI-Programm installiert und dem Desktop des Benutzers eine Verknüpfung zum Starten hinzugefügt. Teams wird erst gestartet, wenn der Benutzer es manuell startet. Nachdem der Benutzer Teams manuell gestartet hat, wird es immer automatisch gestartet, wenn sich der Benutzer anmeldet.

Beachten Sie, dass diese Beispiele auch den **ALLUSERS = 1** -Parameter verwenden. Wenn Sie diesen Parameter festlegen, wird das computerweite Installationsprogramm von Teams in den Programmen und Funktionen in der Systemsteuerung und in den apps & Features in Windows-Einstellungen für alle Benutzer des Computers angezeigt. Alle Benutzer können dann Teams deinstallieren, wenn Sie über Administratoranmeldeinformationen auf dem Computer verfügen.

> [!Note]
> Wenn Sie das MSI-Paket manuell ausführen, sollten Sie es unbedingt mit erweiterten Berechtigungen ausführen. Auch wenn Sie das Installationsprogramm als Administrator ausführen, kann es die Option zum Deaktivieren des automatischen Starts nicht konfigurieren, wenn es ohne erweiterte Berechtigungen ausgeführt wird.
