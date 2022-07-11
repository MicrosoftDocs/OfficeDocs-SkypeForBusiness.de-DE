---
title: Masseninstallation von Teams mithilfe von Windows Installer
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: Verwenden Sie Windows Installer(MSI)-Dateien, um den Teams-Client an mehrere Benutzer und Computer zu verteilen.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b8c8521aa5e19abe59aa9e4c60fcc41eff9b1c7
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713323"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>Masseninstallation von Teams mithilfe von Windows Installer

> [!Tip]
> Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients).

Microsoft stellt 32-Bit-, 64-Bit- und ARM64-MSI-Dateien bereit, die Sie für die Massenbereitstellung von Microsoft Teams für ausgewählte Benutzer und Computer verwenden können. MSI-Dateien können mit dem [Microsoft Endpoint Configuration Manager](/configmgr/core/understand/introduction), der [Gruppenrichtlinie](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) oder der Vertriebssoftware von Drittanbietern verwendet werden, um Teams in Ihrer Organisation bereitzustellen. Massenbereitstellungen sind nützlich, da Benutzer den Teams-Client nicht manuell herunterladen und installieren müssen. Stattdessen wird Teams auf Computern bereitgestellt und dann automatisch gestartet, wenn sich Benutzer zum ersten Mal bei einem Computer anmelden.

Es wird empfohlen, das Paket auf Computern und nicht für einen bestimmten Benutzer bereitzustellen. Durch die Ausrichtung auf Computer profitieren alle neuen Benutzer dieser Computer von dieser Bereitstellung.

>[!NOTE]
> Teams kann auch als Teil von Microsoft 365 Apps for Enterprise an Ihre Organisation verteilt werden. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams mit Microsoft 365 Apps for Enterprise](/deployoffice/teams-install).

## <a name="msi-files"></a>MSI-Dateien

Die folgende Tabelle enthält Links zu 32-Bit-, 64-Bit- und ARM64-MSI-Dateien für Teams. Laden Sie die MSI-Dateien herunter, die Sie auf Computern in Ihrer Organisation installieren möchten. Die von Teams unterstützte x86-Architektur (32-Bit oder 64-Bit) ist unabhängig von anderen Office-Apps, die auf einem Computer installiert sind.

Wenn Sie über 64-Bit-Computer verfügen, empfiehlt es sich, die 64-Bit-Teams-MSI-Dateien auch dann zu installieren, wenn auf dem Computer eine 32-Bit-Version von Office ausgeführt wird. Die ARM64-MSI-Dateien können nur auf Computern installiert werden, die die ARM-Architektur verwenden, z. B. Surface Pro X.

> [!IMPORTANT]
> Installieren Sie die 64-Bit-Version von Teams nur unter 64-Bit-Betriebssystemen. Wenn Sie versuchen, die 64-Bit-Version von Teams unter einem 32-Bit-Betriebssystem zu installieren, ist die Installation nicht erfolgreich, und es wird keine Fehlermeldung angezeigt.

|Entität  |32-Bit      |64-Bit      | ARM64 |
|---------|---------|---------|-----------|
|Commercial     | [32-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|U.S. Government – GCC     | [32-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|U.S. Government – GCC High    | [32-Bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64-Bit](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|U.S. Government – DoD     | [32-Bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64-Bit](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>Funktionsweise der Microsoft Teams-MSI-Datei

### <a name="pc-installation"></a>PC-Installation

Die Teams-MSI-Datei platziert ein Installationsprogramm in `%SystemDrive%\Program Files\Teams Installer` unter 32-Bit-Windows und `%SystemDrive%\Program Files (x86)\Teams Installer` unter 64-Bit-Windows. Wenn sich ein Benutzer bei einem neuen Windows-Benutzerprofil anmeldet, wird das Installationsprogramm gestartet und im Ordner `%LocalAppData%\Microsoft\Teams` des Benutzers eine Kopie der Teams-App installiert. Wenn die Microsoft Teams-App bereits im Ordner`%LocalAppData%\Microsoft\Teams` des Benutzers installiert ist, überspringt das MSI-Installationsprogramm den Prozess für diesen Benutzer.

MSI-Dateien können nicht zum Bereitstellen von Updates verwendet werden. Der Teams-Client wird automatisch aktualisiert, wenn er erkennt, dass eine neue Version über den Dienst verfügbar ist. Verwenden Sie zum erneuten Bereitstellen des neuesten Installationsprogramms das unten beschriebene Verfahren für die erneute Bereitstellung des MSI-Installationsprogramms. Wenn Sie eine ältere Version der MSI-Datei bereitstellen, wird der Client automatisch aktualisiert (außer in VDI-Umgebungen), sofern dies für den Benutzer möglich ist. Falls eine sehr alte Version bereitgestellt wird, löst das MSI-Paket ein App-Update aus, bevor der Benutzer Microsoft Teams verwenden kann.

> [!IMPORTANT]
> Es wird davon abgeraten, die standardmäßigen Installationsspeicherorte zu ändern, da dies den Aktualisierungsablauf unterbrechen könnte. Eine zu alte Version führt letztlich dazu, dass die Benutzer nicht auf den Dienst zugreifen können.

#### <a name="target-computer-requirements"></a>Anforderungen an die Zielcomputer

Stellen Sie sicher, dass die Computer, auf denen Sie Teams installieren, die unter [Hardwareanforderungen für Microsoft Teams](hardware-requirements-for-the-teams-app.md) aufgeführten Anforderungen erfüllen.

### <a name="vdi-installation"></a>VDI-Installation

Umfassende Anleitungen zum Bereitstellen der Teams-Desktop-App auf VDI finden Sie unter [Teams für virtualisierte Desktopinfrastruktur](teams-for-vdi.md).

## <a name="clean-up-and-redeployment-procedure"></a>Verfahren für die Bereinigung und erneute Bereitstellung

Wenn ein Benutzer Microsoft Teams in seinem Benutzerprofil deinstalliert, erkennt das MSI-Installationsprogramm, dass der Benutzer die Microsoft Teams-App deinstalliert hat, und installiert Microsoft Teams für dieses Benutzerprofil nicht mehr. Um Microsoft Teams für diesen Benutzer auf einem bestimmten Computer, auf dem Microsoft Teams deinstalliert wurde, erneut bereitzustellen, gehen Sie so vor:

> [!IMPORTANT]
> Die nächsten Schritte enthalten Informationen zum Ändern der Registrierung. Bevor Sie die Registrierung ändern, sichern Sie die Registrierung, und stellen Sie sicher, dass Sie wissen, wie Sie die Registrierung im Falle ein Problems wiederherstellen. Weitere Informationen dazu, wie Sie die Registrierung sichern, wiederherstellen und ändern, finden Sie unter [Windows-Registrierungsinformationen für fortgeschrittene Benutzer](https://support.microsoft.com/help/256986).

1. Deinstallieren Sie die installierte Microsoft Teams-App für alle Benutzerprofile. Weitere Informationen finden Sie unter [Deinstallieren von Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).
2. Löschen Sie das Verzeichnis rekursiv unter `%LocalAppData%\Microsoft\Teams\` für jedes Benutzerprofil.
3. Löschen Sie den Registrierungswert `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` für jedes Benutzerprofil.
4. Stellen Sie die MSI-Datei auf diesem spezifischen Computer erneut bereit.

> [!TIP]
> Für die Schritte 1 und 2 können Sie auch unser [Skript für die Bereinigung von Teams-Bereitstellungen](scripts/powershell-script-deployment-cleanup.md) verwenden.  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>Verhindern, dass Microsoft Teams nach der Installation automatisch gestartet wird

Standardmäßig installiert das MSI-Paket die Teams-App, sobald sich ein Benutzer anmeldet, und startet Teams dann automatisch. Wenn Sie nicht möchten, dass Teams nach der Installation für Benutzer automatisch gestartet wird, können Sie mithilfe von Gruppenrichtlinien eine Richtlinieneinstellung festlegen oder den automatischen Start für das MSI-Installationsprogramm deaktivieren.

### <a name="use-group-policy-recommended"></a>Verwenden von Gruppenrichtlinien (empfohlen)

Aktivieren Sie die Einstellung der [Gruppenrichtlinie](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) **Verhindern, dass Microsoft Teams nach der Installation automatisch gestartet wird**. Sie finden diese Richtlinieneinstellung unter **Benutzerkonfiguration**\\**Richtlinien**\\**Administrative Vorlagen**\\**Microsoft Teams**. Dies ist die empfohlene Methode, da Sie die Richtlinieneinstellung entsprechend den Anforderungen Ihrer Organisation deaktivieren oder aktivieren können.

Aktivieren Sie diese Richtlinieneinstellung vor der Installation von Teams, wird es nicht automatisch gestartet, wenn sich Benutzer bei Windows anmelden. Nachdem sich ein Benutzer zum ersten Mal bei Teams angemeldet hat, wird es bei der nächsten Anmeldung des Benutzers automatisch gestartet.

Lesen Sie [Verwenden der Gruppenrichtlinie zum Verhindern, dass Microsoft Teams nach der Installation automatisch gestartet wird](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation), um mehr zu erfahren.

> [!CAUTION]
> Wenn Sie Teams bereits bereitgestellt haben und diese Richtlinie so einrichten möchten, dass der automatische Start von Teams deaktiviert wird, legen Sie zuerst die Gruppenrichtlinieneinstellung auf den gewünschten Wert fest, und führen Sie dann das [Teams-Autostart-Zurücksetzungsskript](scripts/powershell-script-teams-reset-autostart.md) auf Benutzerbasis aus.

### <a name="disable-auto-launch-for-the-msi-installer"></a>Deaktivieren des automatischen Starts für das MSI-Installationsprogramm

Sie können den automatischen Start für das MSI-Installationsprogramm deaktivieren, indem Sie den Parameter `OPTIONS="noAutoStart=true"` wie folgt verwenden.  

Für die 32-Bit-Version:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Für die 64-Bit-Version:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

Wenn sich ein Benutzer bei Windows anmeldet, wird Teams mit der MSI installiert. Teams wird erst gestartet, wenn der Benutzer es manuell startet. Nachdem der Benutzer Teams manuell gestartet hat, wird es immer automatisch gestartet, wenn sich der Benutzer anmeldet.

Beachten Sie, dass diese Beispiele auch den Parameter **ALLUSERS=1** verwenden. Wenn Sie diesen Parameter festlegen, wird das Installationsprogramm für die computerweite Installation von Teams unter "Programme und Features" in der Systemsteuerung sowie unter "Apps und Features" in den Windows-Einstellungen für alle Benutzer des Computers angezeigt. Alle Benutzer können Teams dann deinstallieren, wenn Sie über Administratorrechte auf dem Computer verfügen.

> [!Note]
> Wenn Sie das MSI-Paket manuell ausführen, sollten Sie es unbedingt mit erweiterten Berechtigungen ausführen. Auch wenn Sie das Installationsprogramm als Administrator ausführen, kann es die Option zum Deaktivieren des automatischen Starts nicht konfigurieren, wenn es ohne erweiterte Berechtigungen ausgeführt wird.
