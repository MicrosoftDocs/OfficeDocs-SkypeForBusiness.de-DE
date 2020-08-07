---
title: Beziehen von Clients für Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Hier erfahren Sie, wie Sie die verschiedenen verfügbaren Microsoft Teams-Clients für Web, Desktop (Windows und Mac) und mobile Betriebssysteme (Android und iOS) verwenden.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: c1db2aa6eae0dadbd2043198a167daa5cc6fe098
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581676"
---
# <a name="get-clients-for-microsoft-teams"></a>Beziehen von Clients für Microsoft Teams 


Microsoft Teams-Clients sind für Desktop (Windows, Mac und Linux), Web und mobile Betriebssysteme (Android und iOS) verfügbar. Alle diese Clients erfordern eine aktive Internetverbindung und unterstützen den Offlinemodus nicht.

> [!NOTE]
> Ab dem 29. November 2018 können Sie die Microsoft Teams for Windows 10 S-App (Vorschau), die im Microsoft Store verfügbar ist, nicht mehr verwenden. Stattdessen können Sie nun den Teams-Desktopclient auf Geräte herunterladen und installieren, die mit Windows 10 S-Modus betrieben werden. Den Desktopclient zum Herunterladen finden Sie unter [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754). MSI-Builds des Teams-Desktopclients stehen für Geräte, die mit Windows 10 S-Modus betrieben werden, derzeit noch nicht zur Verfügung.
>
> Weitere Informationen zum Windows 10 S-Modus finden Sie unter [Einführung in den Windows 10-Modus](https://www.microsoft.com/windows/s-mode). 

## <a name="desktop-client"></a>Desktopclient

> [!TIP]
> Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)

Der Microsoft Teams-Desktop Client ist eine eigenständige Anwendung und steht auch [in Microsoft 365-Apps für Unternehmen zur Verfügung](https://docs.microsoft.com/deployoffice/teams-install). Teams steht für 32-Bit-und 64-Bit-Versionen von Windows (8,1 oder höher) und Windows Server (2012 R2 oder höher) sowie für macOS und Linux (in `.deb` und Formate) zur Verfügung `.rpm` . Unter Windows erfordert Teams .NET Framework 4.5 oder höher. Das Installationsprogramm für Teams bietet die Installation an, wenn Sie nicht darüber verfügen. Unter Linux versuchen Paketmanager wie `apt` und `yum` alle Anforderungen für Sie zu installieren. Wenn dies nicht gelingt, müssen Sie die bekannten Anforderungen installieren, bevor Sie Teams unter Linux installieren.

Die Desktopclients bieten Unterstützung für Echtzeitkommunikation (Audio, Video und Inhaltsfreigabe) für Teambesprechungen, Gruppenanrufe und private Einzelanrufe.

Desktopclients können unter [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) von Endbenutzern direkt heruntergeladen und installiert werden, sofern sie über die entsprechenden lokalen Berechtigungen verfügen (Administratorrechte sind zum Installieren des Teams-Clients auf einem PC nicht erforderlich, auf einem Mac jedoch sind sie erforderlich).

> [!NOTE]
> Weitere Informationen zum Installieren von Teams auf einem chromebook finden Sie unter [so wird es gemacht: Installieren und Ausführen von Microsoft Office auf einem chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).

IT-Administratoren können ihre bevorzugte Methode für die Verteilung der Installationsdateien an die Computer in ihrer Organisation auswählen. Einige Beispiele hierfür sind Microsoft Endpoint Configuration Manager (Windows) oder Jamf Pro (macOS). Informationen dazu, wie Sie das MSI-Paket für die Verteilung von Windows erhalten, finden Sie unter [Installieren von Microsoft Teams mithilfe eines MSI-Pakets](msi-deployment.md).  

> [!NOTE]
> Die Verteilung des Clients über diese Mechanismen ist nur für die anfängliche Installation von Microsoft Team-Clients gedacht, nicht für zukünftige Updates.

### <a name="windows"></a>Windows

Die Installation von Microsoft Teams für Windows bietet herunterladbare Installationsprogramme in der 32-Bit- und 64-Bit-Architektur.

> [!NOTE]
> Die Architektur (32 Bit oder 64 Bit) von Microsoft Teams ist unabhängig von der Architektur der installierten Windows- und Office-Version.

Der Windows-Client wird im Ordner „AppData“ im Profil des Benutzers bereitgestellt. Durch das Bereitstellen im lokalen Profil des Benutzers kann der Client ohne erweiterte Berechtigungen installiert werden. Der Windows-Client nutzt die folgenden Speicherorte:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Wenn Benutzer erstmals mit dem Microsoft Teams-Client einen Anruf einleiten, sehen sie möglicherweise eine Warnung mit den Einstellungen der Windows-Firewall, in der sie aufgefordert werden, die Kommunikation zuzulassen. Die Benutzer können angewiesen werden, diese Meldung zu ignorieren, da der Anruf auch dann funktioniert, wenn die Warnung geschlossen wird.

![Screenshot des Dialogfelds „Windows-Sicherheitshinweis“](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Die Konfiguration der Windows-Firewall wird auch dann geändert, wenn die Eingabeaufforderung durch Auswählen von „Abbrechen“ geschlossen wird. Zwei eingehende Regeln für „teams.exe“ werden mit der Aktion „Blockieren“ für die Protokolle TCP und UDP erstellt.

Wenn Sie verhindern möchten, dass die Benutzer von Teams aufgefordert werden, Firewallregeln zu erstellen, wenn die Benutzer ihren ersten Anruf von Teams aus führen, verwenden Sie die folgende [Beispiel-PowerShell-Skript-eingehende Firewall-Regel](#sample-powershell-script---inbound-firewall-rule) . 

### <a name="mac"></a>Mac

Mac-Benutzer können Teams mit einer PKG-Installationsdatei für macOS-Computer installieren. Administratorzugriff ist erforderlich, um den Mac-Client zu installieren. Der macOS-Client wird im Ordner „/Programme“ installiert.

#### <a name="install-teams-by-using-the-pkg-file"></a>Installieren von Teams mithilfe der PKG-Datei

1. Klicken Sie auf der [Teams-Downloadseite](https://teams.microsoft.com/downloads) unter **Mac** auf **Herunterladen**.
2. Doppelklicken Sie auf die PKG-Datei.
3. Folgen Sie zum Durchführen der Installation den Anweisungen im Installations-Assistenten.
4. Teams werden im Ordner „/Programme“ installiert. Es handelt sich um eine computerweite Installation.

> [!NOTE]
> Während der Installation fordert die PKG-Datei den Benutzer zur Eingabe von Administratoranmeldeinformationen auf. Der Benutzer muss die Administratoranmeldeinformationen eingeben, unabhängig davon, ob er ein Administrator ist oder nicht.

Wenn ein Benutzer aktuell über eine DMG-Installation von Teams verfügt und sie durch die PKG-Installation ersetzen möchte, sollte der Benutzer:

1. Die Teams-App beenden.
2. Die Teams-App deinstallieren.
3. Die PKG-Datei installieren.

IT-Administratoren können die verwaltete Bereitstellung von Teams für die Verteilung der Installationsdateien auf allen Macs in ihrer Organisation verwenden, z. B. Jamf Pro.

> [!NOTE]
> Wenn Probleme beim Installieren der PKG-Datei auftreten, lassen Sie es uns wissen. Klicken Sie im Abschnitt **Feedback** am Ende dieses Artikels auf **Produktfeedback**.

### <a name="linux"></a>Linux

Benutzer können native Linux-Pakete im Format `.deb` und `.rpm` installieren.
Bei der Installation des deb-oder RPM-Pakets wird das Paket-Repository automatisch installiert.
- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams` 

Der Signaturschlüssel zum Aktivieren der automatischen Aktualisierung mithilfe des Paket-Managers des Systems wird automatisch installiert. Sie finden ihn aber auch unter: (https://packages.microsoft.com/keys/microsoft.asc). Microsoft Teams wird monatlich bereitgestellt und wenn das Repository ordnungsgemäß installiert wurde, sollte der System-Paket-Manager die automatische Aktualisierung auf die gleiche Weise wie andere Pakete im System handhaben.

> [!NOTE] 
> Wenn Sie einen Fehler gefunden haben, übermitteln Sie ihn mithilfe von `Report a Problem` aus dem Client. Informationen zu bekannten Problemen finden Sie unter [Support Teams in Ihrer Organisation](Known-issues.md).
> Für Support zu Teams für Linux können Sie den [Linux-Forum-Support-Kanal in Microsoft F&A](https://docs.microsoft.com/answers/topics/teams.html) verwenden. Achten Sie darauf, beim Posten von Fragen das `teams-linux`-Tag zu verwenden. 

#### <a name="install-teams-using-deb-package"></a>Installieren von Teams mithilfe des DEB-Pakets

1. Laden Sie das Paket unter https://aka.ms/getteams herunter.
2. Installieren Sie es mithilfe einer der folgenden Methoden:  
    - Öffnen Sie das entsprechende Paketverwaltungstool, und schließen Sie den selbstgeführten Installationsvorgang der Linux-App ab.
    - Wenn Ihnen Terminal gefällt, geben Sie Folgendes ein: `sudo apt install **teams download file**`

Sie können Teams über „Aktivitäten“ oder Terminal starten, indem Sie `teams` eingeben. 

#### <a name="install-teams-using-rpm-package"></a>Installieren von Teams mithilfe des RPM-Pakets

1. Laden Sie das Paket unter https://aka.ms/getteams herunter.
2. Installieren Sie es mithilfe einer der folgenden Methoden:
    - Öffnen Sie das entsprechende Paketverwaltungstool, und schließen Sie den selbstgeführten Installationsvorgang der Linux-App ab.
    - Wenn Ihnen Terminal gefällt, geben Sie Folgendes ein: `sudo yum install **teams download file**`

Sie können Teams über „Aktivitäten“ oder Terminal starten, indem Sie `teams` eingeben.

#### <a name="install-manually-from-the-command-line"></a>Manuelles Installieren über die Befehlszeile

Manuelles Installieren unter Debian- und Ubuntu-Distributionen:

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

Manuelles Installieren unter RHEL-, Fedora- und CentOS-basierten Distributionen:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

Alternativ können Sie yum anstelle von dnf verwenden:

```bash
yum check-update
sudo yum install teams
```

Manuelles Installieren unter openSUSE-basierten Distributionen:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a>Webclient 

Beim Webclient ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) handelt es sich um einen vollständig funktionsfähigen Client, der in einer Vielzahl von Browsern verwendet werden kann. Der Webclient unterstützt Anrufe und Besprechungen mit WebRTC, es ist also kein Plug-In oder Download erforderlich, um Teams in einem Webbrowser ausführen. Der Browser muss so konfiguriert sein, dass Drittanbietercookies zulässig sind. 

[!INCLUDE [browser-support](includes/browser-support.md)]

Der Webclient führt beim Herstellen einer Verbindung mit [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) eine Ermittlung der Browserversion durch. Wenn eine nicht unterstützte Browserversion erkannt wird, wird der Zugriff auf die Webschnittstelle blockiert, und dem Benutzer wird empfohlen, den Desktopclient oder die mobile App herunterzuladen.

## <a name="mobile-clients"></a>Mobile Clients

Die Microsoft Teams-Apps für Mobilgeräte stehen für Android und iOS zur Verfügung und sind auf mobile Benutzer ausgelegt, die an Chat-basierten Unterhaltungen teilnehmen. Außerdem ermöglichen sie Peer-to-Peer-Audioanrufe. Rufen Sie den entsprechenden Store für mobile Apps – Google Play oder Apple App Store – auf, um die Apps herunterzuladen. Die Windows Phone-App wurde am 20. Juli 2018 eingestellt und funktioniert möglicherweise nicht mehr. 

Hier erfahren Sie, wie Sie in China [Teams für Android abrufen](get-teams-android-in-china.md) können. 

Unterstützte mobile Plattformen für mobile Microsoft Teams-Apps:

-   **Android**: Der Support ist auf die letzten vier Hauptversionen von Android begrenzt. Wenn eine neue Hauptversion von Android veröffentlicht wird, werden die neue und die vorherigen drei Versionen offiziell unterstützt.

-   **iOS**: Der Support ist auf die beiden neuesten Hauptversionen von iOS beschränkt. Wenn eine neue Hauptversion von iOS veröffentlicht wird, werden die neue und die vorherigen drei Versionen offiziell unterstützt.

> [!NOTE]
> Die mobile Version muss der Öffentlichkeit zur Verfügung stehen, damit Teams wie erwartet funktioniert.

Mobile Apps werden nur über den App-Store der jeweiligen mobilen Plattform vertrieben und aktualisiert. Der Vertrieb der mobilen Apps über MDM oder Querladen wird von Microsoft nicht unterstützt. Sobald die mobile App auf einer unterstützten mobilen Plattform installiert wurde, wird die mobile Teams-App unterstützt, sofern die Version höchstens drei Monate jünger als die aktuelle Version ist.


| | | |
|---------|---------|---------|
|![Symbol, das einen Entscheidungspunkt darstellt](media/Get_clients_for_Microsoft_Teams_image4.png)      |Entscheidungspunkt         |Gelten Einschränkungen, die Benutzer daran hindern, den entsprechenden Microsoft Teams-Client auf ihren Geräten zu installieren?         |
|![Ein Symbol, das die nächsten Schritte darstellt](media/Get_clients_for_Microsoft_Teams_image5.png)     |Nächste Schritte         |Wenn Ihre Organisation Softwareinstallationen einschränkt, stellen Sie sicher, dass dieser Prozess mit Microsoft Teams kompatibel ist. Hinweis: Administratorrechte sind zum Installieren von Clients auf einem PC nicht erforderlich, auf einem Mac jedoch sind sie erforderlich.         |

## <a name="client-update-management"></a>Verwaltung von Clientupdates

Clients werden aktuell vom Microsoft Teams-Dienst aktualisiert, ohne dass ein IT-Administrator eingreifen muss. Wenn ein Update verfügbar ist, wird der Client das Update automatisch herunterladen und wenn die App für einen bestimmten Zeitraum nicht verwendet wurde, beginnt der Updatevorgang.

## <a name="client-side-configurations"></a>Clientseitige Konfigurationen

Zurzeit sind keine unterstützten Optionen zum Konfigurieren des Clients durch den Mandantenadministrator, PowerShell, Gruppenrichtlinienobjekte oder die Registrierung verfügbar.

## <a name="notification-settings"></a>Benachrichtigungseinstellungen

Zurzeit sind keine Optionen verfügbar, mit denen IT-Administratoren clientseitige Benachrichtigungseinstellungen konfigurieren können. Alle Benachrichtigungsoptionen werden von den Benutzern festgelegt. Die folgende Abbildung zeigt die Standardclienteinstellungen.

![Screenshot der Benachrichtigungseinstellungen](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a>Beispiel für eine PowerShell-Skript-eingehende Firewall-Regel

Dieses Beispielskript, das auf Clientcomputern im Kontext eines Administratorkontos mit erweiterten Berechtigungen ausgeführt werden muss, erstellt eine neue eingehende Firewallregel für jeden Benutzerordner unter C:\Users. Wenn Teams diese Regel findet, kann sie verhindern, dass die Teams-Anwendung Benutzer zum Erstellen von Firewallregeln auffordert, wenn der Benutzer seinen ersten Aufruf über Teams tätigt. 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
