---
title: Beziehen von Clients für Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: high
search.appverid: MET150
description: Erfahren Sie, wie Sie die verschiedenen Clients installieren, die für Microsoft Teams auf PCs, Macs und mobilen Geräten verfügbar sind.
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b922607955d8b825006217bd2fe333eaadbc1ce
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556566"
---
# <a name="get-clients-for-microsoft-teams"></a>Beziehen von Clients für Microsoft Teams

> [!TIP]
> **Möchten Sie Teams auf Ihrem PC, Mac oder mobilen Gerät installieren?** Sehen Sie sich [Installieren des Teams-Clients](https://go.microsoft.com/fwlink/?linkid=855754) an.

Microsoft Teams kann auf PCs, Macs und mobilen Geräten installiert und auch über einen Webbrowser aufgerufen werden. Die meisten Endbenutzer können mit der Verwendung von Teams beginnen, indem Sie einfach [den Client installieren](https://go.microsoft.com/fwlink/?linkid=855754). Nach der Installation des Teams-Clients müssen sie sich lediglich mit ihrem Benutzernamen und Kennwort anmelden.

Wenn Sie ein IT-Experte sind und mehr über die Teams-Installationserfahrung und deren Anforderungen erfahren möchten, wählen Sie in diesem Artikel ein Clientbetriebssystem aus, um weitere Informationen zu erhalten.

Mehr über die Funktionen jedes Clients auf verschiedenen Plattformen erfahren Sie unter [Teams-Funktionen nach Plattform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).

## <a name="desktop-clients"></a>Desktopclients

Der Teams-Desktopclient ist als eigenständige Anwendung und als Teil von [Microsoft 365 Apps for Enterprise](/deployoffice/teams-install) für die folgenden Betriebssysteme verfügbar:

- 32-Bit- und 64-Bit-Versionen von Windows (8.1 oder höher)
- ARM64 für Windows 10 auf ARM
- Windows Server (2012 R2 oder höher)
- macOS
- Linux (in den Formaten `.deb` und `.rpm`)
- Chrome-Betriebssystem (Weitere Informationen finden Sie unter [Verwendung von Microsoft Office auf einem Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad))

Desktopclients können von Endbenutzern von [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) direkt heruntergeladen und installiert werden, sofern sie über die entsprechenden lokalen Berechtigungen verfügen. Administratorberechtigungen sind zum Installieren des Teams-Clients auf einem Windows-PC nicht erforderlich, auf einem Mac jedoch schon.

IT-Experten können ihre bevorzugte Methode für die Verteilung der Installationsdateien an die Computer in ihrer Organisation auswählen. Einige Beispiele hierfür sind Microsoft Endpoint Configuration Manager (Windows) oder Jamf Pro (macOS). Für weitere Informationen zum Verteilen von Teams lesen Sie Folgendes.

- **Windows** [Installieren von Teams mit dem Microsoft Endpoint Configuration Manager](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> Die Verteilung des Clients über diese Mechanismen ist nur für die anfängliche Installation von Teams-Clients gedacht und nicht für zukünftige Updates. Informationen zum Teams-Updateprozess finden Sie unter [Teams-Updateprozess](teams-client-update.md).

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> Schauen Sie sich die folgende Sitzung mit Informationen zu den Vorteilen des Windows-Desktopclient sowie zum Planen und Bereitstellen der Lösung an: [Windows-Desktopclient für Teams](https://aka.ms/teams-clients)

Teams unter Windows bietet herunterladbare MSI-Installationsprogramme in [32-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)-, [64-Bit](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)- und [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)-Architekturen. Die x86-Architektur (32 Bit oder 64 Bit) von Microsoft Teams ist unabhängig von der Architektur der installierten Windows- und Office-Version. Wir empfehlen die 64-Bit-Version von Teams auf 64-Bit-Systemen.

Teams erfordert .NET Framework 4.5 oder höher. Wenn .NET Framework 4.5 oder höher nicht installiert ist, bietet Ihnen das Teams-Installationsprogramm die Installation an.

Der Windows-Client wird im Ordner AppData bereitgestellt, der sich im Profil des Benutzers befindet. Die Bereitstellung im lokalen Profil des Benutzers ermöglicht die Installation des Clients, ohne dass erhöhte Berechtigungen erforderlich sind. Der Windows-Client nutzt die folgenden Speicherorte:

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

Wenn Benutzer erstmals mit dem Teams-Client einen Anruf einleiten, sehen sie möglicherweise eine Warnung mit den Einstellungen der Windows-Firewall, in der sie aufgefordert werden, die Kommunikation zuzulassen. Die Benutzer können angewiesen werden, diese Meldung zu ignorieren, da der Anruf auch dann funktioniert, wenn die Warnung geschlossen wird.

![Screenshot des Dialogfelds „Windows-Sicherheitshinweis“.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Die Konfiguration der Windows-Firewall wird auch dann geändert, wenn die Eingabeaufforderung durch Auswählen von „Abbrechen“ geschlossen wird. Zwei eingehende Regeln für „teams.exe“ werden mit der Aktion „Zulassen“ für die Protokolle TCP und UDP erstellt.

Wenn Sie verhindern möchten, dass Benutzer von Teams aufgefordert werden, Firewallregeln zu erstellen, wenn sie ihre ersten Anrufe über Teams machen, verwenden Sie das PowerShell-Beispielskript in [Beispielskript – PowerShell-Skript für Microsoft Teams-Firewall](client-firewall-script.md).

### <a name="mac"></a>[Mac](#tab/Mac)

Mac-Benutzer können Teams mit einer PKG-Installationsdatei für macOS-Computer installieren. Administratorzugriff ist erforderlich, um den Mac-Client zu installieren. Der macOS-Client wird im Ordner „/Programme“ installiert.

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

IT-Experten können eine verwaltete Bereitstellungslösung wie beispielsweise Jamf Pro verwenden, um die Teams-Installationsdateien an alle Macs in ihrer Organisation zu verteilen.

### <a name="linux"></a>[Linux](#tab/Linux)

Unter Linux versuchen Paketmanager wie `apt` und `yum` alle Anforderungen für Sie zu installieren. Wenn dies nicht gelingt, müssen Sie die bekannten Anforderungen installieren, bevor Sie Teams unter Linux installieren.

Benutzer können native Linux-Pakete im Format `.deb` und `.rpm` installieren. Bei der Installation des DEB- oder RPM-Pakets wird das Paketrepository automatisch installiert.

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

Der Signaturschlüssel zum Aktivieren der automatischen Aktualisierung mithilfe des Paket-Managers des Systems wird automatisch installiert. Sie finden ihn aber auch unter: <https://packages.microsoft.com/keys/microsoft.asc>. Teams wird monatlich bereitgestellt, und wenn das Repository ordnungsgemäß installiert wurde, sollte der System-Paket-Manager die automatische Aktualisierung auf die gleiche Weise wie andere Pakete im System handhaben.

#### <a name="install-teams-using-deb-package"></a>Installieren von Teams mithilfe des DEB-Pakets

1. Laden Sie das Paket unter <https://aka.ms/getteams> herunter.
2. Installieren Sie es mithilfe einer der folgenden Methoden:
    - Öffnen Sie das entsprechende Paketverwaltungstool, und schließen Sie den selbstgeführten Installationsvorgang der Linux-App ab.
    - Wenn Ihnen Terminal gefällt, geben Sie Folgendes ein: `sudo dpkg -i **teams download file**`

Sie können Teams über „Aktivitäten“ oder Terminal starten, indem Sie `teams` eingeben.

#### <a name="install-teams-using-rpm-package"></a>Installieren von Teams mithilfe des RPM-Pakets

1. Laden Sie das Paket unter <https://aka.ms/getteams> herunter.
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

---

## <a name="mobile-clients"></a>Mobile Clients

Die mobilen Teams-Apps sind für Android und iOS verfügbar und richten sich an Benutzer, die sich unterwegs an chatbasierten Unterhaltungen beteiligen möchten, und sie ermöglichen Peer-zu-Peer-Audioanrufe. Sie finden die mobilen Apps in den jeweiligen mobilen Stores Google Play und dem Apple App Store.

Unterstützte mobile Plattformen für Teams-Apps für Mobilgeräte sind die Folgenden:

- **Android**: Der Support ist auf die letzten vier Hauptversionen von Android begrenzt. Wenn eine neue Hauptversion von Android veröffentlicht wird, werden die neue und die vorherigen drei Versionen offiziell unterstützt.

- **iOS**: Der Support ist auf die beiden neuesten Hauptversionen von iOS beschränkt. Wenn eine neue Hauptversion von iOS veröffentlicht wird, werden die neue und die vorherigen drei Versionen offiziell unterstützt.

> [!NOTE]
> Die mobile Version muss der Öffentlichkeit zur Verfügung stehen, damit Teams wie erwartet funktioniert.

Mobile Apps werden nur über den App-Store der jeweiligen mobilen Plattform vertrieben und aktualisiert. Der Vertrieb der mobilen Apps über MDM oder Querladen wird von Microsoft nicht unterstützt. Sobald die mobile App auf einer unterstützten mobilen Plattform installiert wurde, wird die mobile Teams-App unterstützt, sofern die Version höchstens drei Monate jünger als die aktuelle Version ist.

Wenn Sie sich in China befinden, können Sie Teams aus den folgenden App-Stores installieren:

- **Xiaomi** <https://aka.ms/TeamsXiaomi>
- **Huawei** <https://aka.ms/TeamsHuawei>
- **Oppo** Suchen Sie im Oppo-Store nach „Teams“
- **Baidu** <https://aka.ms/teams_baidu_direct_dl>

## <a name="browser-client"></a>Browserclient

Der Browserclient ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) ist ein vollständiger, funktionsfähiger Client, der in einer Vielzahl von Browsern verwendet werden kann. Der Browserclient unterstützt Anrufe und Besprechungen mit webRTC, es ist also kein Plug-In oder Download erforderlich, um Teams in einem Browser auszuführen. Der Browser muss so konfiguriert sein, dass Drittanbietercookies zulässig sind.

[!INCLUDE [browser-support](includes/browser-support.md)]

Der Browserclient führt beim Herstellen der Verbindung mit [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) eine Erkennung der Browserversion durch. Wenn eine nicht unterstützte Browserversion erkannt wird, wird der Zugriff auf die Browserschnittstelle blockiert, und dem Benutzer wird empfohlen, den Desktopclient oder die mobile App herunterzuladen.
