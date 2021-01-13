---
title: Microsoft Teams für Virtualized Desktop Infrastructure
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jmorrow
audience: admin
description: Erfahren Sie, wie Sie Microsoft Teams in einer Virtualized Desktop Infrastructure (VDI)-Umgebung ausführen.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 687726febc81a727c4f6da4824487672c602809e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820985"
---
# <a name="teams-for-virtualized-desktop-infrastructure"></a>Microsoft Teams für Virtualized Desktop Infrastructure

In diesem Artikel werden die Anforderungen und Einschränkungen für die Verwendung von Microsoft Teams in einer virtualisierten Umgebung beschrieben.

## <a name="what-is-vdi"></a>Was ist VDI?

Virtual Desktop Infrastructure (VDI) ist eine Virtualisierungstechnologie, die ein Desktopbetriebssystem und Anwendungen auf einem zentralen Server in einem Rechenzentrum hostet. Dies ermöglicht Benutzern eine vollständig personalisierte Desktoperfahrung mit einer vollständig sicheren und kompatiblen zentralen Quelle.

Microsoft Teams in einer virtualisierten Umgebung unterstützt Chat und Zusammenarbeit. Mit den Plattformen Windows Virtual Desktop,Mware und VMware werden auch Anruf- und Besprechungsfunktionen unterstützt.

Teams in einer virtualisierten Umgebung unterstützen mehrere Konfigurationen. Dazu gehören VDI-, dedizierte, freigegebene, persistente und nicht persistente Modi. Features befinden sich in fortlaufender Entwicklung und werden regelmäßig hinzugefügt, und die Funktionalität wird in den kommenden Monaten und Jahren erweitert.

Die Verwendung von Teams in einer virtualisierten Umgebung kann sich von der Verwendung von Teams in einer nicht virtualisierten Umgebung unterscheiden. Beispielsweise stehen einige erweiterte Features in einer virtualisierten Umgebung möglicherweise nicht zur Verfügung, und die Videoauflösung kann abweichen.

Befolgen Sie die Anweisungen in diesem Artikel, um eine optimale Benutzererfahrung zu gewährleisten.

> [!Note]
> Details zu Teams VDI auf verschiedenen Plattformen finden Sie unter ["Teams-Features nach Plattform".](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)

## <a name="teams-on-vdi-components"></a>Teams auf VDI-Komponenten

Die Verwendung von Teams in einer virtualisierten Umgebung erfordert die folgenden Komponenten.

- **Virtualisierungsbroker:** Der Ressourcen- und Verbindungs-Manager für den Virtualisierungsanbieter, z. B. Azure
- **Virtueller Desktop:** Der Stapel des virtuellen Computers (VM), auf dem Microsoft Teams ausgeführt wird
- **Thin Client:** Der Endpunkt, mit dem der Benutzer physisch verbunden ist
- **Teams-Desktop-App:** Die Teams-Desktop-Client-App

## <a name="teams-on-vdi-requirements"></a>Teams nach VDI-Anforderungen

### <a name="virtualization-provider-requirements"></a>Anforderungen des Virtualisierungsanbieters

Die Teams-Desktop-App wurde mit führenden Virtualisierungslösungsanbietern überprüft. Bei mehreren Anbietern von Marktlösungen empfehlen wir, dass Sie Ihren Virtualisierungslösungsanbieter konsultieren, um sicherzustellen, dass Sie die Mindestanforderungen erfüllen.
  
Derzeit ist Teams auf VDI mit Audio/Video (AV)-Optimierung mit Windows Virtual Desktop,Mware und VMware zertifiziert. Überprüfen Sie die Informationen in diesem Abschnitt, um sicherzustellen, dass alle Anforderungen an die ordnungsgemäße Funktionalität erfüllt sind.

### <a name="platforms-certified-for-teams"></a>Für Teams zertifizierte Plattformen

Die folgenden Plattformen bieten virtuelle Desktopinfrastrukturlösungen für Teams.

|Plattform|Lösung|
|----|---|
|![Das Logo, das Microsoft darstellt](media/microsoft-logo.png)| <a href="https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd" target="_blank">Virtueller Desktop von Windows</a> |
|![Das Logo zur Darstellung von Citrix](media/citrix-logo.png)| <a href="https://www.citrix.com/products/citrix-virtual-apps-and-desktops/" target="_blank">Virtuelle Apps und Desktops von Virtual Virtual Von Virtual</a> |
|![Das Logo, das VMware darstellt](media/vmware-logo.png)| <a href="https://www.vmware.com/products/horizon.html" target="_blank">VMware Horizon</a> |

### <a name="windows-virtual-desktop"></a>Virtueller Desktop von Windows

Der virtuelle Desktop von Windows bietet eine AV-Optimierung für Teams auf VDI-Computern. Weitere Informationen sowie zu den Anforderungen und zur Installation finden Sie unter "Verwenden von [Teams auf virtuellem Windows-Desktop".](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)

### <a name="citrix-virtual-apps-and-desktops-requirements"></a>Anforderungen an virtuelle Virtual Apps und Desktops von Virtual Virtual

Virtual Apps und Desktops (vor allem bekannt als XenApp und XenDesktop) bieten eine AV-Optimierung für Teams auf VDI-Computern. Mit virtuellen Virtual Apps und Desktops von Virtual Virtual Desktops unterstützt Teams auf VDI neben Chat und Zusammenarbeit auch Anruf- und Besprechungsfunktionen.

Sie können die neueste Version virtueller Virtual Apps und Desktops von Virtual Virtual Desktops auf [der Downloadwebsite für Citrix herunterladen.](https://www.citrix.com/downloads/citrix-virtual-apps-and-desktops/) (Sie müssen sich zuerst anmelden.) Die erforderlichen Komponenten werden standardmäßig in der [#A0 (Workspace App, CWA)](https://www.citrix.com/downloads/workspace-app/) und dem Virtual Delivery Agent (VDA) gebündelt. Sie müssen keine zusätzlichen Komponenten oder #A0 auf CWA oder VDA installieren.

Die neuesten Server- und Clientanforderungen finden Sie auf [dieser Website von Citrix.](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/multimedia/opt-ms-teams.html)

### <a name="vmware-horizon-workspace-and-desktop-requirements"></a>VMware Horizon Workspace- und Desktopanforderungen

VMware Horizon ist eine moderne Plattform für die sichere Bereitstellung virtueller Desktops und Apps in der Hybrid-Cloud. Um eine großartige Endbenutzererfahrung zu bieten, bietet VMware Horizon Medienoptimierung für Teams. Diese Optimierung verbessert die Gesamtproduktivität auf virtuellen Desktops und Apps und verbessert die Benutzerfreundlichkeit bei Anrufen und Besprechungen mit Teams.

Sie können die neueste Version von VMware Horizon von der Seite ["VMware Downloads"](https://my.vmware.com/web/vmware/downloads/#all_products) herunterladen. Die erforderlichen Komponenten für die Medienoptimierung sind standardmäßig Teil des Horizon Agent und des Horizon Clients, und es ist nicht erforderlich, ein zusätzliches Plug-In zu installieren, um das Optimierungsfeature für Teams zu verwenden.

Die neuesten Anforderungen und Anweisungen zum Konfigurieren der Medienoptimierung für Teams finden Sie auf [dieser VMware-Website.](https://docs.vmware.com/en/VMware-Horizon/2006/horizon-remote-desktop-features/GUID-F68FA7BB-B08F-4EFF-9BB1-1F9FC71F8214.html)

## <a name="install-or-update-the-teams-desktop-app-on-vdi"></a>Installieren oder Aktualisieren der Teams-Desktop-App auf VDI

Sie können die Teams-Desktop-App für VDI mithilfe einer Installation pro Computer oder mithilfe des MSI-Pakets pro Benutzer bereitstellen. Die Entscheidung über den zu verwendenden Ansatz hängt davon ab, ob Sie ein dauerhaftes oder nicht persistentes Setup und die zugehörigen Funktionalitätsanforderungen Ihrer Organisation verwenden.

Bei einem dedizierten beständigen Setup würde beides funktionieren. Für ein nicht persistentes Setup ist für Teams jedoch eine Installation pro Computer erforderlich, um effizient arbeiten zu können. Weitere Informationen finden [Sie im Abschnitt "Nicht persistentes Setup".](#non-persistent-setup)

Bei der Installation pro Computer werden automatische Updates deaktiviert. Dies bedeutet, dass Sie zum Aktualisieren der Teams-App die aktuelle Version deinstallieren müssen, um auf eine neuere Version zu aktualisieren. Bei der Installation pro Benutzer sind automatische Updates aktiviert. Für die meisten VDI-Bereitstellungen empfehlen wir die Bereitstellung von Teams mithilfe der Installation pro Computer.

Um auf die neueste Version von Teams zu aktualisieren, beginnen Sie mit dem Deinstallationsverfahren, gefolgt von der bereitstellung der neuesten Teams-Version.

Damit die Teams-AV-Optimierung in VDI-Umgebungen ordnungsgemäß funktioniert, muss der thine Clientendpunkt Zugriff auf das Internet haben. Wenn am Dünnen Clientendpunkt kein Internetzugriff verfügbar ist, ist der Optimierungsstart nicht erfolgreich. Dies bedeutet, dass sich der Benutzer in einem nicht optimierten Medienzustand befindet.

#### <a name="dedicated-persistent-setup"></a>Dediziertes persistentes Setup

In einem dedizierten beständigen Setup bleiben die Änderungen des lokalen Betriebssystems der Benutzer erhalten, nachdem sich die Benutzer abgemeldet haben. Für das dauerhafte Setup unterstützt Teams sowohl die Installation pro Benutzer als auch pro Computer.

Im Folgenden wird die empfohlene Mindestkonfiguration der VM bezeichnet.

|Parameter  |Betriebssystem der Arbeitsstation  |Serverbetriebssystem  |
|---------|---------|---------|
|vCPU   |    2 Kerne     |  4, 6 oder 8<br>Es ist wichtig, die zugrunde liegende Konfiguration für nicht uniform Memory Access (NUMA) zu verstehen und Ihre VMs entsprechend zu konfigurieren.     |
|RAM     |   4 GB      | 512 bis 1024 MB pro Benutzer        |
|Speicher    | 8 GB        | 40 bis 60 GB        |

#### <a name="non-persistent-setup"></a>Nicht persistentes Setup

In einem nicht persistenten Setup werden die Änderungen des lokalen Betriebssystems der Benutzer nach der Benutzer abmelden nicht beibehalten. Solche Setups sind häufig freigegebene Sitzungen mit mehreren Benutzern. Die Konfiguration der VM variiert je nach Anzahl der Benutzer und verfügbaren physischen Box-Ressourcen.

Für ein nicht persistentes Setup muss die Teams-Desktop-App pro Computer auf dem goldenen Bild installiert sein. (Weitere Informationen finden Sie im Abschnitt "Installieren oder Aktualisieren der [Teams-Desktop-App auf VDI".)](#install-or-update-the-teams-desktop-app-on-vdi) Dadurch wird ein effizientes Starten der Teams-App während einer Benutzersitzung sichergestellt.

Die Verwendung von Teams mit einem nicht persistenten Setup erfordert auch einen Profil-Zwischenspeicherungs-Manager für eine effiziente Teams-Runtime-Datensynchronisierung. Dadurch wird sichergestellt, dass die entsprechenden benutzerspezifischen Informationen (z. B. Benutzerdaten, Profil und Einstellungen) während der Benutzersitzung zwischengespeichert werden. Stellen Sie sicher, dass die Daten in diesen beiden Ordnern synchronisiert werden.  

- C:\Users\username\AppData\Local\Microsoft\IdentityCache (%localAppdata%\Microsoft\IdentityCache)
- C:\Benutzer\Benutzername\AppData\Roaming\Microsoft\Teams (%appdata%\Microsoft\Teams)

Es stehen eine Vielzahl von Lösungen für den Zwischenspeicherungs-Manager zur Verfügung. Beispiel: [FSLogix.](https://docs.microsoft.com/fslogix/overview) Spezifische Konfigurationsanweisungen erhalten Sie von Ihrem Caching-Manager-Anbieter.

##### <a name="teams-cached-content-exclusion-list-for-non-persistent-setup"></a>Liste zwischengespeicherter Inhaltsausschlüsse für nicht persistentes Setup in Teams

Schließen Sie Folgendes aus dem Ordner "Teams-Zwischenspeicherung", "%appdata%/Microsoft/Teams", aus. Wenn diese Elemente ausgeschlossen werden, verringern Sie die Größe des Zwischenspeicherns von Benutzern, um die nicht persistente Einrichtung weiter zu optimieren.

- TXT-Dateien
- Ordner "Medienstapel"
- meeting-addin\Cache (%appdata%\Microsoft\Teams\meeting-addin\Cache)

### <a name="microsoft-365-apps-for-enterprise-considerations"></a>Microsoft 365-Apps aus Unternehmensgründen

Beachten Sie Folgendes, wenn Sie Teams mit Microsoft 365-Apps für Unternehmen auf VDI bereitstellen.

#### <a name="new-deployments-of-teams-through-microsoft-365-apps-for-enterprise"></a>Neue Bereitstellungen von Teams über Microsoft 365-Apps für Unternehmen

Bevor Sie Teams über Microsoft 365-Apps für Unternehmen bereitstellen, müssen Sie zunächst alle bereits vorhandenen Teams-Apps deinstallieren, wenn sie über die Installation pro Computer bereitgestellt wurden.

Teams über Microsoft 365-Apps für Unternehmen wird pro Benutzer installiert. Weitere Informationen finden Sie im Abschnitt "Installieren oder Aktualisieren der [Teams-Desktop-App auf VDI".](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="teams-deployments-through-microsoft-365-apps-for-enterprise-updates"></a>Bereitstellungen von Microsoft Teams über Microsoft 365-Apps für Unternehmensupdates

Teams wird auch zu vorhandenen Installationen von Microsoft 365-Apps für Unternehmen hinzugefügt. Da Microsoft 365-Apps für Unternehmen Teams nur pro Benutzer installiert, lesen Sie den Abschnitt "Installieren oder Aktualisieren der [Teams-Desktop-App auf VDI".](#install-or-update-the-teams-desktop-app-on-vdi)

#### <a name="using-teams-with-per-machine-installation-and-microsoft-365-apps-for-enterprise"></a>Verwenden von Teams bei der Installation pro Computer und Microsoft 365-Apps für Unternehmen

Microsoft 365-Apps für Unternehmen unterstützt keine Computerinstallationen von Teams. Wenn Sie die Installation pro Computer verwenden möchten, müssen Sie Teams aus Microsoft 365-Apps für Unternehmen ausschließen. Weitere Informationen finden Sie in den Abschnitten "Bereitstellen [der Teams-Desktop-App](#deploy-the-teams-desktop-app-to-the-vm) auf der VM" und "Ausschließen der Bereitstellung von Teams über [Microsoft 365-Apps für Unternehmen".](#how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise)

#### <a name="how-to-exclude-teams-deployment-through-microsoft-365-apps-for-enterprise"></a>Ausschließen der Bereitstellung von Microsoft Teams über Microsoft 365-Apps für Unternehmen

Weitere Informationen zu Teams und Microsoft 365-Apps für Unternehmen finden Sie unter "Ausschließen von Teams aus neuen Installationen von [Microsoft 365-Apps](https://docs.microsoft.com/DeployOffice/teams-install#how-to-exclude-microsoft-teams-from-new-installations-of-office-365-proplus) für Unternehmen" und Verwenden von Gruppenrichtlinien zum Steuern der Installation von [Teams.](https://docs.microsoft.com/DeployOffice/teams-install#use-group-policy-to-control-the-installation-of-microsoft-teams)

### <a name="deploy-the-teams-desktop-app-to-the-vm"></a>Bereitstellen der Teams-Desktop-App auf der VM

1. Laden Sie das Teams-MSI-Paket, das Ihrem VDI -VM-Betriebssystem entspricht, über einen der folgenden Links herunter:

    - [32-Bit-Version](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)
    - [64-Bit-Version](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)

    > [!NOTE]
    > Links zum Herunterladen der MSI-Dateien finden Sie unter ["Installieren](msi-deployment.md) von Microsoft Teams mit Microsoft Endpoint Configuration Manager".

    Die mindestens erforderliche Version der Teams-Desktop-App ist Version 1.3.00.4461. (Der PSTN-Speicher wird in früheren Versionen nicht unterstützt.)

2. Installieren Sie MSI auf der VDI VM, indem Sie einen der folgenden Befehle ausführen:

    - Installation pro Benutzer (Standard)
  
        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSERS=1
        ```

        Bei diesem Prozess handelt es sich um die Standardinstallation, bei der Teams im Benutzerordner "%AppData%" installiert wird. An diesem Punkt ist die Einrichtung des „Golden Image“ abgeschlossen. Teams funktioniert bei der Installation pro Benutzer bei einem nicht persistenten Setup nicht ordnungsgemäß.

    - Installation pro Computer

        ```console
        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1 ALLUSERS=1
        ```

        Bei diesem Vorgang wird Teams in den Ordner "Program Files (x86)" unter einem 64-Bit-Betriebssystem und in den Ordner "Programme" unter einem 32-Bit-Betriebssystem installiert. An diesem Punkt ist die Einrichtung des „Golden Image“ abgeschlossen. Das Installieren von Teams pro Computer ist für nicht persistente Setups erforderlich.

        Bei der nächsten interaktiven Anmeldesitzung startet Teams und fordert Anmeldeinformationen an.

        > [!NOTE]
        > In diesen Beispielen wird auch der **Parameter ALLUSERS=1** verwendet. Wenn Sie diesen Parameter festlegen, wird das Installationsprogramm für die computerweite Installation von Teams unter "Programme und Features" in der Systemsteuerung sowie unter "Apps und Features" in den Windows-Einstellungen für alle Benutzer des Computers angezeigt. Alle Benutzer können Teams dann deinstallieren, wenn sie über Administratoranmeldeinformationen verfügen.
        Es ist wichtig, den Unterschied zwischen **ALLUSERS=1** und **ALLUSER=1 zu verstehen.** Der **Parameter ALLUSERS=1** kann in Nicht-VDI- und VDI-Umgebungen verwendet werden, während der **Parameter ALLUSER=1** nur in VDI-Umgebungen verwendet wird, um eine Installation pro Computer anzugeben.

3. Deinstallieren Sie die MSI von der VDI VM. Es gibt zwei Möglichkeiten zum Deinstallieren von Teams.

    - PowerShell-Skript: Sie können dieses [PowerShell-Skript](scripts/powershell-script-deployment-cleanup.md) verwenden, um Teams zu deinstallieren und den Ordner "Teams" für einen Benutzer zu entfernen. Führen Sie das Skript für jedes Benutzerprofil aus, in dem Teams auf dem Computer installiert wurde.
    - Befehlszeile: Führen Sie den folgenden Befehl aus.
  
      ```console
      msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>
      ```

      Bei diesem Vorgang wird Teams je nach Betriebssystemumgebung aus dem Ordner "Programmdateien" (x86) oder dem Ordner "Programmdateien" deinstalliert.

## <a name="teams-on-vdi-performance-considerations"></a>Überlegungen zur Leistung von Teams zu VDI

Es gibt eine Vielzahl virtualisierter Setupkonfigurationen, die jeweils einen anderen Optimierungsfokus haben. Eine Konfiguration kann sich z. B. auf die Benutzerdichte konzentrieren. Berücksichtigen Sie bei der Planung die folgenden Punkte, um das Setup basierend auf den Arbeitsauslastungsanforderungen Ihrer Organisation zu optimieren.

- Mindestanforderung: Einige Arbeitslasten erfordern möglicherweise ein Setup mit Ressourcen, die über den Mindestanforderungen liegen. Beispielsweise Workloads für Entwickler, die Anwendungen verwenden, die mehr Computerressourcen erfordern.
- Abhängigkeiten: Dazu gehören Abhängigkeiten von Infrastruktur, Arbeitsauslastung und andere Umgebungsaspekte außerhalb der Teams-Desktop-App.
- Deaktivierte Features für VDI: Teams deaktiviert GPU-intensive Features für VDI, wodurch eine vorübergehende Auslastung der CPU verbessert werden kann. Die folgenden Features sind deaktiviert:
    - Teams-CSS-Animation
    - Giphy auto-start

## <a name="teams-on-vdi-with-calling-and-meetings"></a>Teams auf VDI mit Anrufen und Besprechungen

Zusätzlich zu Chat und Zusammenarbeit steht Teams für VDI mit Anrufen und Besprechungen auf unterstützten Virtualisierungsanbieterplattformen zur Verfügung. Unterstützte Features basieren auf der Implementierung des WebRTC-Medienstapels und des Virtualisierungsanbieters. Das folgende Diagramm bietet eine Übersicht über die Architektur.

![Diagramm, das Teams in der Architektur von VDI zeigt](media/teams-on-vdi-architecture.png)

> [!IMPORTANT]
> Wenn Sie Derzeit Teams ohne AV-Optimierung in VDI ausführen und Features verwenden, die für die Optimierung noch nicht unterstützt werden (z. B. "Steuerung übernehmen" bei der App-Freigabe), müssen Sie Richtlinien für Virtualisierungsanbieter festlegen, um die Umleitung von Teams zu deaktivieren. Dies bedeutet, dass Die Mediensitzungen in Teams nicht optimiert werden. Schritte zum Festlegen von Richtlinien zum Deaktivieren der Teams-Umleitung erhalten Sie von Ihrem Virtualisierungsanbieter.

### <a name="network-requirements"></a>Netzwerkanforderungen

Wir empfehlen, Ihre Umgebung auszuwerten, um mögliche Risiken und Anforderungen zu erkennen, die sich auf Ihre gesamte Cloud-Sprach- und Videobereitstellung beeinflussen können. Verwenden Sie [das Bewertungstool für das Skype for](https://www.microsoft.com/download/details.aspx?id=53885) Business-Netzwerk, um zu testen, ob Ihr Netzwerk für Teams bereit ist.

Weitere Informationen zum Vorbereiten Ihres Netzwerks für Teams finden Sie unter "Vorbereiten des Netzwerks Ihrer Organisation [für Teams".](prepare-network.md)

### <a name="migrate-from-skype-for-business-on-vdi-to-teams-on-vdi"></a>Migrieren von Skype for Business auf VDI zu Teams auf VDI

Wenn Sie neben den Unterschieden zwischen den beiden Anwendungen auch VDI von Skype for Business über VDI zu Teams auf VDI migrieren, gibt es einige Unterschiede, wenn VDI ebenfalls implementiert wird. Einige Funktionen, die derzeit in Teams VDI nicht unterstützt werden, die sich in Skype for Business VDI befinden, sind die folgenden:

- Plattformübergreifende Richtlinie zum Deaktivieren einiger AV-Features in VDI
- Übernehmen und Übernehmen der Steuerung bei der Freigabe von Apps
- Bildschirmfreigabe über Chat ohne Audio
- Gleichzeitiges Senden und Empfangen von Videos und Bildschirmfreigaben

### <a name="teams-on-chrome-browser-versus-teams-desktop-app-for-vdi"></a>Teams im Browser Chrome im Vergleich zur Teams-Desktop-App für VDI

Teams im Browser Chrome ersetzt die Teams-Desktop-App nicht durch VDI und AV-Optimierung. Die Chat- und Zusammenarbeitserfahrung funktioniert wie erwartet. Wenn Medien benötigt werden, gibt es einige Benutzeroberflächen, die den Erwartungen der Benutzer im Browser Chrome möglicherweise nicht entsprechen:

- Die Audio- und Videostreamingerfahrung ist möglicherweise nicht optimal. Bei Benutzern kann es zu Verzögerungen oder einer verringerten Qualität kommen.
- Geräteeinstellungen sind in den Browsereinstellungen nicht verfügbar.
- Die Geräteverwaltung erfolgt über den Browser und erfordert mehrere Einstellungen in den Einstellungen der Browserwebsite.
- Geräteeinstellungen müssen möglicherweise auch in der Windows-Geräteverwaltung festgelegt werden.

## <a name="teams-on-vdi-with-chat-and-collaboration"></a>Teams auf VDI mit Chat und Zusammenarbeit

Wenn Ihre Organisation nur Chat- und Zusammenarbeitsfeatures in Teams verwenden möchte, können Sie Richtlinien auf Benutzerebene festlegen, um die Anruf- und Besprechungsfunktionen in Teams zu deaktivieren. 

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Festlegen von Richtlinien zum Deaktivieren von Anruf- und Besprechungsfunktionen

Sie können Richtlinien über das Microsoft Teams Admin Center oder PowerShell festlegen. Es kann einige Zeit (einige Stunden) dauern, bis die Richtlinienänderungen weitervererbt wurden. Wenn die Änderungen für ein bestimmtes Konto nicht sofort zu sehen sind, versuchen Sie es in ein paar Stunden erneut.

[**Anrufrichtlinien:**](teams-calling-policy.md)Teams enthält die integrierte Anrufrichtlinie "Anruf unter Ungernerufe", in der alle Anruffunktionen deaktiviert sind. Weisen Sie die Richtlinie "DisallowCalling" allen Benutzern in Ihrer Organisation zu, die Teams in einer virtualisierten Umgebung verwenden.

[**Besprechungsrichtlinien:**](meeting-policies-in-teams.md)Teams enthält die integrierte AllOff-Besprechungsrichtlinie, in der alle Besprechungsfeatures deaktiviert sind. Weisen Sie die "AllOff"-Richtlinie allen Benutzern in Ihrer Organisation zu, die Teams in einer virtualisierten Umgebung verwenden.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Zuweisen von Richtlinien über das Microsoft Teams Admin Center

So weisen Sie einem Benutzer die Anrufrichtlinie "DisallowCalling Calling" und die Besprechungsrichtlinie "AllOff" zu:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Benutzer".**
2. Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.
3. Gehen Sie folgendermaßen vor:
    1.  Klicken **Sie unter "Anrufrichtlinie"** auf **"DisallowCalling".**
    2.  Klicken **Sie unter "Besprechungsrichtlinie"** auf **"AllOff".**
4. Klicken Sie auf **Anwenden**.

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken Sie am oberen Rand der Tabelle auf &#x2713; (Häkchen).
3. Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu der Richtlinie, die Sie zuweisen möchten. Beispiel:
    - Wechseln Sie zu **den** Sprachanrufrichtlinien, und klicken Sie dann auf  >   **"DisallowCalling".**
    - Wechseln Sie zu **Den**  >  **Besprechungsrichtlinien** für Besprechungen, und klicken Sie dann **auf "AllOff".**
2. Wählen Sie **Nutzer verwalten** aus.
3. Suchen Sie im Bereich **Nutzer verwalten** anhand des Anzeigenamens oder des Nutzernamens nach dem Nutzer, wählen Sie den Namen und dann **Hinzufügen** aus. Wiederholen Sie diesen Schritt für jeden Nutzer, den Sie hinzufügen möchten.
4. Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.

#### <a name="assign-policies-using-powershell"></a>Zuweisen von Richtlinien mithilfe von PowerShell

Das folgende Beispiel zeigt, wie Sie einem Benutzer mithilfe von [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) die Richtlinie "DisallowCalling calling" zuweisen.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Anrufrichtlinien finden Sie unter [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

Das folgende Beispiel zeigt, wie Sie die [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) verwenden, um einem Benutzer die Besprechungsrichtlinie "AllOff" zuzuordnen.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Besprechungsrichtlinien finden Sie unter [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="migrate-teams-on-vdi-with-chat-and-collaboration-to-optimize-teams-with-calling-and-meetings"></a>Migrieren von Teams auf VDI mit Chat und Zusammenarbeit, um Teams mit Anrufen und Besprechungen zu optimieren

Wenn Sie über eine Implementierung von Teams auf VDI mit Chat und Zusammenarbeit verfügen, in der Sie Richtlinien auf Benutzerebene zum Deaktivieren von Anruf- und Besprechungsfunktionen festgelegt hatten und Sie mit der Optimierung der AV zu Teams migrieren, müssen Sie Richtlinien festlegen, um die Anruf- und Besprechungsfunktionen für diese Teams für VDI-Benutzer zu aktivieren.

### <a name="set-policies-to-turn-on-calling-and-meeting-functionality"></a>Festlegen von Richtlinien zum Aktivieren von Anruf- und Besprechungsfunktionen

Über das Microsoft Teams Admin Center oder PowerShell können Sie Anruf- und Besprechungsrichtlinien für Ihre Benutzer festlegen und zuweisen. Es kann einige Zeit (einige Stunden) dauern, bis Richtlinienänderungen weitervererbt wurden. Wenn die Änderungen für ein bestimmtes Konto nicht sofort zu sehen sind, versuchen Sie es nach ein paar Stunden erneut.

[**Anrufrichtlinien:**](teams-calling-policy.md)Anrufrichtlinien in Teams steuern, welche Anruffunktionen für Benutzer verfügbar sind. Teams enthält die integrierte Anrufrichtlinie "AllowCalling", in der alle Anruffunktionen aktiviert sind. Weisen Sie die Richtlinie "AllowCalling" zu, um alle Anruffeatures zu aktivieren. Oder erstellen Sie eine benutzerdefinierte Anrufrichtlinie, um die von Ihnen geforderten Anruffeatures zu aktivieren und sie Benutzern zuzuordnen. 

[**Besprechungsrichtlinien:**](meeting-policies-in-teams.md)Besprechungsrichtlinien in Teams steuern die Arten von Besprechungen, die Benutzer erstellen können, und die Features, die für Besprechungsteilnehmer verfügbar sind, die von Benutzern in Ihrer Organisation geplant werden. Teams enthält die integrierte AllOn-Besprechungsrichtlinie, in der alle Besprechungsfeatures aktiviert sind. Um alle Besprechungsfeatures zu aktivieren, weisen Sie die "AllOn"-Richtlinie zu. Oder erstellen Sie eine benutzerdefinierte Besprechungsrichtlinie, um die von Ihnen wollenen Besprechungsfeatures zu aktivieren und sie Benutzern zuzuordnen.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Zuweisen von Richtlinien über das Microsoft Teams Admin Center

So weisen Sie einem Benutzer die Anrufrichtlinie für AllowCalling und die Besprechungsrichtlinie "AllOn" zu:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu **"Benutzer".**
2. Wählen Sie den Nutzer aus, indem Sie links neben den Nutzernamen klicken, und klicken Sie dann auf **Einstellungen bearbeiten**.
3. Gehen Sie folgendermaßen vor:
    1.  Klicken **Sie unter "Anrufrichtlinie"** auf **"AllowCalling".**
    2.  Klicken **Sie unter "Besprechungsrichtlinie"** auf **"AllOn".**
4. Klicken Sie auf **Anwenden**.

So weisen Sie mehreren Benutzern gleichzeitig eine Richtlinie zu

1. Wechseln Sie in der linken Navigation des Microsoft Teams Admin Center zu **Benutzer**, und suchen Sie dann nach den gewünschten Benutzern, oder filtern Sie die Ansicht, um die gewünschten Benutzer anzuzeigen.
2. Wählen Sie in der Spalte **&#x2713;** (Häkchen) die Benutzer aus. Um alle Benutzer auszuwählen, klicken **Sie&#x2713;** (Häkchen) am Anfang der Tabelle.
3. Klicken Sie auf **Einstellungen bearbeiten**, nehmen Sie die gewünschten Änderungen vor, und klicken Sie dann auf **Übernehmen**.

Sie können auch die folgenden Schritte ausführen:

1. Wechseln Sie in der linken Navigationsleiste des Microsoft Teams Admin Centers zu der Richtlinie, die Sie zuweisen möchten. Beispiel:
    - Wechseln Sie zu **den**  >  **Sprachanrufrichtlinien,** und klicken Sie dann **auf "AllowCalling".**
    - Wechseln Sie zu **den**  >  **Besprechungsrichtlinien** für Besprechungen, und klicken Sie dann **auf "AllOn".**
2. Wählen Sie **Nutzer verwalten** aus.
3. Suchen Sie im Bereich **Nutzer verwalten** anhand des Anzeigenamens oder des Nutzernamens nach dem Nutzer, wählen Sie den Namen und dann **Hinzufügen** aus. Wiederholen Sie diesen Schritt für jeden Nutzer, den Sie hinzufügen möchten.
4. Wenn Sie alle gewünschten Benutzer hinzugefügt haben, klicken Sie auf **Speichern**.

#### <a name="assign-policies-using-powershell"></a>Zuweisen von Richtlinien mithilfe von PowerShell

Im folgenden Beispiel wird veranschaulicht, wie Sie einem Benutzer mithilfe von [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) die Richtlinie zum Aufrufen von AllowCalling zuweisen.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName AllowCalling -Identity "user email id"
```

Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Anrufrichtlinien finden Sie unter [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

Das folgende Beispiel zeigt, wie Sie einem Benutzer mithilfe von [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) die Besprechungsrichtlinie "AllOn" zuweisen.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOn -Identity "user email id"
```

Weitere Informationen zur Verwendung von PowerShell zum Verwalten von Besprechungsrichtlinien finden Sie unter [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)

## <a name="control-fallback-mode-in-teams"></a>Steuern des Fallbackmodus in Teams

Wenn Benutzer eine Verbindung von einem nicht unterstützten Endpunkt aus herstellen, befinden sich die Benutzer im Fallbackmodus, in dem AV nicht optimiert ist. Sie können den Fallbackmodus deaktivieren oder aktivieren, indem Sie einen der folgenden Registrierungs-DWORD-Werte festlegen:

- HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Teams\DisableFallback
- HKEY_CURRENT_USER\SOFTWARE\Microsoft\Office\Teams\DisableFallback

Um den Fallbackmodus zu deaktivieren, legen Sie den Wert auf **1 .** Um nur Audio zu aktivieren, legen Sie den Wert auf **2 .** Wenn der Wert nicht vorhanden oder auf **0 (Null)** festgelegt ist, ist der Fallbackmodus aktiviert.

Dieses Feature ist in Teams Version 1.3.00.13565 und höher verfügbar.

## <a name="known-issues-and-limitations"></a>Bekannte Probleme und Einschränkungen

### <a name="client-deployment-installation-and-setup"></a>Clientbereitstellung, -installation und -einrichtung

- Bei der Installation pro Computer wird Teams für VDI nicht automatisch so aktualisiert, wie es nicht mit VDI -Teams-Clients erfolgt. Sie müssen das Vm-Bild aktualisieren, indem Sie eine neue MSI installieren, wie im Abschnitt "Installieren oder Aktualisieren der Teams-Desktop-App [auf VDI"](#install-or-update-the-teams-desktop-app-on-vdi) beschrieben. Sie müssen die aktuelle Version deinstallieren, um auf eine neuere Version zu aktualisieren.
- Teams sollten entweder pro Benutzer oder pro Computer bereitgestellt werden. Die Bereitstellung von Teams für gleichzeitige Bereitstellungen pro Benutzer und Computer wird nicht unterstützt. Wenn Sie entweder von einem Computer oder einem Benutzer zu einem dieser Modi migrieren möchten, führen Sie die Deinstallation aus, und stellen Sie sie in beiden Modus erneut zur Verfügung.
- Windows Virtual Desktop und VMware unterstützen derzeit keine MacOS- und Linux-basierten Clients.
- Zu diesem Zeitpunkt unterstützt Citrix keine MacOs-Clients.
- "Citrix" unterstützt nicht die Verwendung expliziter HTTP-Proxys, die für einen Endpunkt definiert sind.

### <a name="calling-and-meetings"></a>Anrufe und Besprechungen

Die folgenden Anruf- und Besprechungsfeatures werden nicht unterstützt:

- Erweiterte Notfalldienste
- HID-Schaltflächen und -LED-Steuerelemente zwischen der App und den Geräten von Teams
- Weichschärfen und Effekte für den Hintergrund
- Produzenten- und Moderatorrollen von Übertragungen und Liveereignisen
- Location-Based Routing (LBR)
- Anruf parken
- Anrufwarteschleife
- Audio-/Computersound des gemeinsam genutzten Systems
- Medienumgehung für direkte Weiterleitung

> [!NOTE]
> Wir arbeiten daran, Anruf- und Besprechungsfeatures hinzufügen, die derzeit nur in Nicht-VDI-Umgebungen verfügbar sind. Dazu können weitere Administratorsteuerelemente für die Qualität, zusätzliche Szenarien für die Bildschirmfreigabe und erweiterte Features gehören, die kürzlich zu Teams hinzugefügt wurden. Wenden Sie sich an Ihren Teams-Mitarbeiter, um mehr über anstehende Features zu erfahren.

Im Folgenden sind bekannte Probleme und Einschränkungen für Anrufe und Besprechungen bekannt:

- Interoperabilität mit Skype for Business ist auf Audioanrufe beschränkt. es gibt keine Videomodalität.
- In Besprechungen oder Gruppenanrufen wird nur ein einzelner eingehender Videostream unterstützt. Wenn mehrere Personen Video senden, wird zu einem bestimmten Zeitpunkt nur das Video des dominanten Sprechers angezeigt.
- Die Auflösung des eingehenden und ausgehenden Videostreams ist auf eine Auflösung von 720p beschränkt. Dies ist eine WebRTC-Einschränkung.
- Es wird nur ein Videodatenstrom von einer eingehenden Kamera oder einem Stream für Bildschirmfreigaben unterstützt. Bei einer eingehenden Bildschirmfreigabe wird diese Bildschirmfreigabe anstelle des Videos des dominanten Sprechers angezeigt.
- Teams wechselt nicht zur Verwendung des letzten Audiogeräts, das ein Benutzer ausgewählt hat, wenn das Gerät getrennt und dann erneut verbunden wurde.
- Ausgehende Bildschirmfreigabe:
    - Die Anwendungsfreigabe wird nicht unterstützt.
- Übernehmen Sie die Steuerung, und übernehmen Sie die Kontrolle:
    - Wird während einer Bildschirmfreigabe- oder Anwendungsfreigabesitzung nicht unterstützt.
    - Wird während einer PowerPoint-Freigabesitzung unterstützt.
- Einschränkungen für Ausschließliches Arbeiten mit Workspace
    - Bei der Bildschirmfreigabe in einem Setup mit mehreren Monitoren wird nur der Hauptmonitor freigegeben.
    - Die Skalierung mit hohem #A0 unter CWA wird nicht unterstützt.

Bekannte Probleme in Teams, die nicht mit VDI in Zusammenhang stehen, finden Sie unter ["Support Teams in Ihrer Organisation".](Known-issues.md)

## <a name="troubleshooting"></a>Problembehandlung

### <a name="troubleshoot-citrix-components"></a>Behandeln von Problemen mit Den Komponenten von "Universelle Software"

#### <a name="teams-crashes-or-the-teams-sign-in-screen-is-blank"></a>Teams stürzt ab oder der Anmeldebildschirm von Teams ist leer

Dies ist ein bekanntes Problem mit den Versionen 1906 und 1909 von Citrix VDA. Um dieses Problem zu beheben, fügen Sie den folgenden Registrierungs-DWORD-Wert hinzu, und legen Sie ihn auf 204 (hexadezimal) festgelegt.

HKEY_LOCAL_MACHINE\SOFTWARE\Citrix\CtxHook\AppInit_Dlls\SfrHook\Teams.exe

Starten Sie VDA dann neu. Weitere Informationen finden Sie in diesem Supportartikel zu Diesem Artikel zu Richtlinien für Den Support von Citrix: [Problembehandlung bei der HDX-Optimierung für Teams.](https://support.citrix.com/article/CTX253754)

## <a name="related-topics"></a>Verwandte Themen

- [Installieren von Microsoft Teams mithilfe eines MSI-Pakets](msi-deployment.md)
- [Übersicht über PowerShell für Microsoft Teams](teams-powershell-overview.md)
- [Verwenden von Microsoft Teams auf dem virtuellen Desktop von Windows](https://docs.microsoft.com/azure/virtual-desktop/teams-on-wvd)
