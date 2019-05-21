---
title: Installieren von Microsoft Teams mithilfe eines MSI-Pakets mit SCCM
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Administratoren können das Microsoft Teams-MSI-Paket für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c009433696ac554114a2a06955b4f33beb6543f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281617"
---
<a name="install-microsoft-teams-using-msi"></a>Installieren von Microsoft Teams mithilfe eines MSI-Pakets
=================================

> [!Tip]
> Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)

Wenn Sie für die allgemeine Bereitstellung System Center Configuration Manager (SCCM), Gruppenrichtlinien oder Verteilungsmethoden von Drittanbietern verwenden möchten: Microsoft hat MSI-Dateien (als [32-Bit](https://aka.ms/teams32bitmsi)- und [64-Bit](https://aka.ms/teams64bitmsi)-Versionen) bereitgestellt, die Administratoren für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer oder Computer verwenden können. Administratoren können Microsoft Teams mit diesen Dateien remote bereitstellen, damit die Benutzer die Teams-App nicht manuell herunterladen müssen. Die bereitgestellte Microsoft Teams-App wird für alle Benutzer, die sich bei dem jeweiligen Computer anmelden, automatisch gestartet. (Sie können das automatische Starten nach der Installation der App deaktivieren. [Siehe unten](#disable-auto-launch-for-the-msi-installer).) Wir empfehlen, das Paket auf dem Computer bereitzustellen, damit alle neuen Benutzer des Computers ebenfalls von dieser Bereitstellung profitieren. 
 
> [!Note] 
> Weitere Informationen zu SCCM finden Sie unter [Einführung in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).

## <a name="deployment-procedure-recommended"></a>Bereitstellungsverfahren (empfohlen)
1. Rufen Sie das neueste Paket ab.
2. Verwenden Sie die vorausgefüllten Standardeinstellungen.
3. Stellen Sie die Software auf Computern bereit, wenn dies möglich ist.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Funktionsweise des MSI-Pakets für Microsoft Teams

### <a name="pc-installation"></a>PC-Installation

> [!Note] 
> Anleitungen zum Bereitstellen von Teams in einer virtuellen DesktopInfrastructure (VDI)-Umgebung finden Sie unter [VDI-Installation](#vdi-installation) .

Das MSI-Paket für Microsoft Teams legt ein Installationsprogramm in „Programme“ ab. Wenn sich ein Benutzer in einem neuen Windows-Benutzerprofil anmeldet, wird das Installationsprogramm gestartet, und eine Kopie der Teams-APP wird im AppData-Ordner des Benutzers installiert. Wenn die Microsoft Teams-App bereits im Ordner „AppData“ des Benutzers installiert ist, überspringt das MSI-Installationsprogramm den Prozess für diesen Benutzer.

Sie sollten das MSI-Paket nicht zum Bereitstellen von Updates verwenden, da der Client automatisch aktualisiert wird, wenn er erkennt, dass über den Dienst eine neue Version verfügbar ist. Verwenden Sie zum erneuten Bereitstellen des neuesten Installationsprogramms das unten beschriebene Verfahren für die erneute Bereitstellung von MSI-Paketen.Wenn Sie eine ältere Version des MSI-Pakets bereitstellen, wird der Client automatisch aktualisiert, sofern dies für den Benutzer möglich ist. Wenn eine sehr alte Version bereitgestellt wird, löst die MSI-App ein App-Update aus, bevor der Benutzer in der Lage ist, Teams zu verwenden. 

> [!Important] 
> Sie sollten die standardmäßigen Installationsspeicherorte nicht ändern, da dies den Aktualisierungsablauf behindern kann. Eine zu alte Version führt letztlich dazu, dass die Benutzer nicht auf den Dienst zugreifen können. 

#### <a name="target-computer-requirements"></a>Anforderungen an die Zielcomputer

- .NET Framework 4.5 oder höher
- Windows 7 oder höher
- 3 GB Speicherplatz auf dem Datenträger für jedes Benutzerprofil (empfohlen)

### <a name="vdi-installation"></a>VDI-Installation

Hier ist der Vorgang zum Bereitstellen der Desktop-App für Teams. Umfassende Anleitungen finden Sie unter [Teams für virtualisierte Desktop Infrastruktur](teams-for-vdi.md).

1. Laden Sie das MSI-Paket für Teams mit einem der folgenden Links in Abhängigkeit von der Umgebung herunter. Wir empfehlen die 64-Bit-Version für eine VDI-VM mit einem 64-Bit-Betriebssystem.

    - [32-Bit-Version](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64-Bit-Version](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. Führen Sie den folgenden Befehl aus, um die MSI-Datei auf der VDI-VM zu installieren (oder vollständig zu aktualisieren).

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1

    Dadurch werden Teams in Programmdateien installiert. An diesem Punkt ist die Einrichtung des goldenen Bilds abgeschlossen.

    In der nächsten interaktiven Anmeldesitzung werden Teams gestartet, und es werden Anmeldeinformationen angefordert. Beachten Sie, dass es nicht möglich ist, den automatischen Start von Teams bei der Installation von Teams auf VDI mithilfe der ALLUSERS-Eigenschaft zu deaktivieren.

3. Führen Sie den folgenden Befehl aus, um die MSI-Datei von der VDI-VM zu deinstallieren (oder die Aktualisierung vorzubereiten).

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    Dadurch wird Microsoft Teams aus Programmdateien deinstalliert.

## <a name="clean-up-and-redeployment-procedure"></a>Verfahren für die Bereinigung und erneute Bereitstellung

Wenn ein Benutzer Microsoft Teams in seinem Benutzerprofil deinstalliert, erkennt das MSI-Installationsprogramm, dass der Benutzer die Microsoft Teams-App deinstalliert hat, und installiert Microsoft Teams für dieses Benutzerprofil nicht mehr. Um Microsoft Teams für diesen Benutzer auf einem bestimmten Computer, auf dem Microsoft Teams deinstalliert wurde, erneut bereitzustellen, gehen Sie so vor:

1. Deinstallieren Sie die installierte Microsoft Teams-App für alle Benutzerprofile. 
2. Löschen Sie nach der Deinstallation rekursiv das Verzeichnis „%localappdata%\Microsoft\Teams\“.
3. Stellen Sie das MSI-Paket auf dem entsprechenden Computer erneut bereit.

> [!TIP] 
> Für die Schritte 1 und 2 können Sie unser Skript für die [Bereinigung von Microsoft Teams-Bereitstellungen](scripts/Powershell-script-teams-deployment-clean-up.md) über SCCM verwenden.

## <a name="disable-auto-launch-for-the-msi-installer"></a>Deaktivieren des automatischen Starts für das MSI-Installationsprogramm

Standardmäßig installiert das MSI-Paket den Teams-Client, sobald sich ein Benutzer anmeldet, und startet dann automatisch Teams. Sie können dieses Verhalten mit folgenden Parametern wie folgt ändern:

- Wenn sich ein Benutzer bei Windows anmeldet, wird Teams mit dem MSI-Paket installiert.
- Jedoch wird der Teams-Client nicht gestartet, bis der Benutzer Teams manuell startet.
- Auf dem Desktop des Benutzers wird eine Verknüpfung zum Starten von Teams hinzugefügt.
- Nach dem erstmaligen manuellen Start wird Teams automatisch gestartet, wenn sich der Benutzer anmeldet.

Für die 32-Bit-Version
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
Für die 64-Bit-Version
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  Wenn Sie das MSI-Paket manuell ausführen, sollten Sie es unbedingt mit erweiterten Berechtigungen ausführen. Auch wenn Sie es als Administrator ausführen, kann das Installationsprogramm die Option zum Deaktivieren des automatischen Starts nicht deaktivieren, wenn keine erweiterten Berechtigungen vorhanden sind.
