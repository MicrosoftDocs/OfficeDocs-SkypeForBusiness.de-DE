---
title: Bereitstellen von Microsoft Teams Rooms mit Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Erfahren Sie mehr über die Bereitstellung von Microsoft Teams Rooms in großen Bereitstellungen mit Microsoft Endpoint Configuration Manager.
no-loc:
- Microsoft
- Microsoft Corporation
- Microsoft Teams Rooms
- Microsoft Teams Room
- System Center
- Configuration Manager
- Windows
- Surface
- Surface Pro
- Windows PE
- Windows 10
- Windows 10 Enterprise
- Azure
- Azure Monitor
- Log Analytics
- Operations Management Suite
ms.openlocfilehash: e755a369d3f8aa11d5346c2e5cda9cc84285dc7b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117403"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Bereitstellen von Microsoft Teams Rooms mithilfe von Microsoft Endpoint Configuration Manager

Dieser Artikel enthält alle erforderlichen Informationen zum Erstellen Ihrer Microsoft Teams Rooms-Bereitstellungen mithilfe von Microsoft Endpoint Configuration Manager.

Mit den einfach zu verwendende Methoden, die von Configuration Manager bereitgestellt werden, können Sie das Betriebssystem und andere Anwendungen auf mehreren Zielgeräten bereitstellen.

Verwenden Sie den nachstehend dargestellten Ansatz, um Sie durch Ihre Configuration Manager-Konfiguration zu führen und die Beispielpakete und Skripts anzupassen, die in diesem Leitfaden für Ihre Organisation bereitgestellt werden.

![Bereitstellungsprozess für Microsoft Teams Rooms mit Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Diese Lösung wurde nur mit Surface Pro-basierten Bereitstellungen getestet. Befolgen Sie die Richtlinien des Herstellers für Konfigurationen, die nicht auf Surface Pro.

## <a name="validate-prerequisites"></a>Überprüfen von Voraussetzungen

Wenn Sie Microsoft Teams Rooms mit Configuration Manager bereitstellen möchten, stellen Sie sicher, dass Sie die folgenden Voraussetzungen und Anforderungen erfüllen.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Anforderungen von Microsoft Endpoint Configuration Manager

-   Die Version von Microsoft Endpoint Configuration Manager muss mindestens 1706 sein. Wir empfehlen die Verwendung von 1710 oder höher. Informationen zu den von Configuration Manager unterstützten Windows 10-Versionen finden Sie unter Support für [Windows 10 in Configuration Manager.](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client)

-   Eine unterstützte Version des Windows Assessment and Deployment Kit (ADK) für Windows 10 muss installiert werden. Sehen Sie sich die Versionen von [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) an, die Sie mit verschiedenen Versionen von Configuration Manager verwenden können, und stellen Sie sicher, dass Ihre Bereitstellung die richtige Version enthält.

-   Den Websitesystemservern muss die Verteilungspunktrolle zugewiesen worden sein, und die Startbilder sollten für die Unterstützung der Vorabausführungsumgebung [(PXE)](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) aktiviert sein, um netzwerkintehiert Bereitstellungen zu ermöglichen. Wenn die PXE-Unterstützung nicht aktiviert ist, können Sie [startbare](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) Medien für Ihre Bereitstellungen verwenden.

-   Ein Netzwerkzugriffskonto muss für die Unterstützung neuer Computerbereitstellungsszenarien (Bare Metal) konfiguriert sein. Weitere Informationen zur Konfiguration eines Netzwerkzugriffskontos finden Sie unter [Konten, die in Configuration Manager verwendet werden.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

-   Wir empfehlen, die [Multicastunterstützung zu aktivieren,](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)wenn Sie wahrscheinlich dasselbe Microsoft Teams Rooms-Bild für mehrere Einheiten gleichzeitig bereitstellen.

### <a name="networking-requirements"></a>Netzwerkanforderungen

-   Ihr Netzwerk sollte über einen DHCP-Server (Dynamic Host Configuration Protocol) verfügen, der für die automatische Verteilung von IP-Adressen an die Subnetze konfiguriert ist, in denen Microsoft Teams Rooms-Einheiten bereitgestellt werden.

    > [!NOTE]
    > Die Dauer des DHCP-Leases muss auf einen Wert festgelegt werden, der länger als die Dauer der Bildbereitstellung ist. Andernfalls kann die Bereitstellung fehlschlagen.

-   Ihr Netzwerk, einschließlich Switches und virtuelleN LANs (VLANs), sollte für die Unterstützung von PXE konfiguriert werden. Weitere Informationen zur IP-Hilfs- und PXE-Konfiguration finden Sie bei Ihrem Netzwerkanbieter. Alternativ können Sie [startbare Medien](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) für Ihre Bereitstellungen verwenden, wenn die PXE-Unterstützung nicht aktiviert ist.

    > [!NOTE]
    > Bei Surface Pro wird das Starten vom Netzwerk (PXE-Start) nur unterstützt, wenn Sie einen Ethernetadapter oder eine Dockingstation von Microsoft verwenden. Ethernetadapter von Drittanbietern unterstützen keinen PXE-Start mit Surface Pro. Weitere [Informationen finden Sie unter Ethernetadapter und Surface-Bereitstellung.](/surface/ethernet-adapters-and-surface-device-deployment)

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Konfigurieren von Microsoft Endpoint Configuration Manager für die Betriebssystembereitstellung

In diesem Artikel wird davon ausgegangen, dass Sie bereits über eine fehlerfreie Configuration Manager-Bereitstellung verfügen, und es werden nicht alle Schritte erläutert, die zum Bereitstellen und Konfigurieren von Configuration Manager von Grund auf erforderlich sind. Die [Dokumentation und die Konfigurationsleitfäden](/configmgr/) im Microsoft Endpoint Configuration Manager sind eine großartige Ressource. Wir empfehlen Ihnen, mit diesen Ressourcen zu beginnen, wenn Sie Configuration Manager noch nicht bereitgestellt haben.

Verwenden Sie die folgenden Anweisungen, um zu überprüfen, ob die Betriebssystembereitstellungsfeatures (OSD) ordnungsgemäß konfiguriert sind.

### <a name="validate-and-upgrade-configuration-manager"></a>Überprüfen und Aktualisieren von Configuration Manager

1.  Wechseln Sie in der Configuration Manager-Konsole zu  \> **Administrationsupdates und -wartung**.

2.  Überprüfen Sie den installierten Build und die anwendbaren Updates, die noch nicht installiert wurden.

3.  Überprüfen [Sie den Support für Windows 10 in Configuration Manager.](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) Wenn Sie ein Upgrade Ihrer Bereitstellung durchführen müssen, wählen Sie das Update aus, das Sie installieren möchten, und wählen Sie dann **Herunterladen aus.**

4.  Nachdem der Download abgeschlossen ist, wählen Sie das Update und dann **Updatepaket installieren aus.**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Konfigurieren von Verteilungspunkten zur Unterstützung von PXE und Multicast

1.  Wechseln Sie in der  Configuration Manager-Konsole zu \> **Verwaltungsverteilungspunkte**.

2.  Wählen Sie den Verteilungspunktserver aus, der die Bereitstellung von Microsoft Teams Rooms dient, und wählen Sie dann Eigenschaften **aus.**

3.  Wählen Sie **die Registerkarte PXE** aus, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:
    -   Aktivieren der PXE-Unterstützung für Clients
    -   Zulassen, dass dieser Verteilungspunkt auf eingehende PXE-Anforderungen antwortet
    -   Aktivieren der Unterstützung unbekannter Computer

4.  *Optional:* Um die Multicastunterstützung zu aktivieren, wählen Sie die **Registerkarte Multicast** aus, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:
    -   Aktivieren von Multicast zum gleichzeitigen Senden von Daten an mehrere Clients
    -   Konfigurieren des UDP-Portbereichs entsprechend der Empfehlung Ihres Netzwerkteams

### <a name="configure-the-network-access-account"></a>Konfigurieren des Netzwerkzugriffskontos

1.  Wechseln Sie in der  Configuration Manager-Konsole zu Verwaltungswebsitekonfigurationswebsites, \>  \> und wählen Sie dann die Website aus.

2.  Wählen Sie **in der** Gruppe Einstellungen die Option **Softwareverteilung für** \> **Websitekomponenten konfigurieren aus.**

3.  Wählen Sie die **Registerkarte Netzwerkzugriffskonto** aus. Richten Sie ein oder mehrere Konten ein, und wählen Sie dann **OK aus.**

> [!NOTE]
> Die Konten benötigen keine speziellen Rechte, mit Ausnahme des Zugriffs auf diesen Computer aus dem Netzwerk **direkt** auf dem Verteilungspunktserver. Ein generisches Domänenbenutzerkonto ist geeignet. Weitere Informationen finden Sie unter [Konten, die in Configuration Manager verwendet werden.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

### <a name="configure-a-boot-image"></a>Konfigurieren eines Startabbilds

1.  Wechseln Sie in der  Configuration Manager-Konsole zu \> **Startbilder für das Betriebssystem der** \> **Softwarebibliothek.**

2.  Wählen **Sie Startbild (x64)** und dann Eigenschaften **aus.**

3.  Wählen Sie **die Registerkarte Datenquelle** aus, und aktivieren Sie Bereitstellen dieses Startabbilds über den **PXE-fähigen Verteilungspunkt.**

4.  Wählen Sie die **Registerkarte Optionale Komponenten** aus, um erforderliche Komponenten zu installieren:

    1.  Wählen Sie das Sternsymbol aus, und suchen Sie nach **HTML (WinPE-HTA)**

    2.  Wählen **Sie OK** aus, um dem Startbild die Unterstützung der HTML-Anwendung hinzuzufügen.

5.  *Optional:* Um die Bereitstellungserfahrung anzupassen, wählen Sie die Registerkarte **Anpassung** aus.
    -   Aktivieren **Sie die Befehlsunterstützung (nur** Tests), wenn Sie während der Bereitstellung Zugriff auf eine Eingabeaufforderung haben möchten. Wenn dies aktiviert ist, können Sie eine Eingabeaufforderung starten, indem Sie während der Bereitstellung jederzeit **F8** auswählen.
    -   Sie können auch ein benutzerdefiniertes Hintergrundbild angeben, das während der Bereitstellung angezeigt werden soll. Wenn Sie ein Bild festlegen möchten, aktivieren Sie Angeben der benutzerdefinierten **Hintergrundbilddatei (UNC-Pfad),** und wählen Sie den Hintergrund aus.

6.  Wenn Sie gefragt werden, wählen Sie **Ja** aus, und verteilen Sie das aktualisierte Startbild an Ihre Verteilungspunkte.

Weitere Informationen finden Sie unter [Verwalten von Startbildern mit Configuration Manager.](/configmgr/osd/get-started/manage-boot-images)

> [!NOTE]
> Sie können ein startbares USB-Medium erstellen, um konfigurations-manager-basierte Bereitstellungen für Umgebungen zu initiieren, die keine PXE-Unterstützung haben. Die startbaren Medien enthalten nur das Startabbild, optionale Vorabstartbefehle und deren erforderliche Dateien sowie Configuration Manager-Binärdateien, um das Starten in Windows PE und das Herstellen einer Verbindung mit Configuration Manager für den rest des Bereitstellungsprozesses zu unterstützen. Weitere Informationen finden Sie unter [Erstellen startbarer Medien.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)

## <a name="create-configuration-manager-packages"></a>Erstellen von Configuration Manager-Paketen

> [!IMPORTANT]
> Die erforderliche Betriebssystemversion für jede SRS-Installationsprogrammversion wird mit jeder MSI-Version geändert. Um die beste Betriebssystemversion für ein bestimmtes MSI zu ermitteln, führen Sie das Konsoleneinrichtungsskript einmal aus. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mithilfe von Microsoft Endpoint Configuration Manager](rooms-scale.md).

Configuration Manager erfordert eine Reihe von Paketen zum Bereitstellen und Konfigurieren der Microsoft Teams Rooms-Einheiten.

Sie müssen die folgenden Pakete erstellen und konfigurieren und diese dann an die Configuration Manager-Websitesysteme verteilen, denen die Verteilungspunktserverrolle zugewiesen wurde.

| **Paketname**                     | **Typ**               | **Beschreibung**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 – SRS-Anwendungspaket     | Softwarepaket       | Paket für das Bereitstellungskit für Microsoft Teams Rooms                                      |
| SRS v2 – Sysprep-Paket             | Softwarepaket       | Paket für die benutzerdefinierten Unattended.xml zum Konfigurieren von Microsoft Teams Rooms-Einheiten            |
| SRS v2 – Set-SRSComputerName Package | Softwarepaket       | Paket für die HTML-Anwendung (HTA), um während der Bereitstellung einen Computernamen zuzuordnen    |
| SRS v2 – Konfigurieren von SRS Setup         | Softwarepaket       | Paket zum Konfigurieren der Bereitstellung der Microsoft Teams Rooms-App                          |
| SRS v2 – Os Updates Package          | Softwarepaket       | Paket zum Bereitstellen obligatorischer Betriebssystemupdates                                      |
| SRS v2 – Stammzertifikatpaket    | Softwarepaket       | Optional – Paket zum Bereitstellen des Stammzertifikats (nicht erforderlich für mit der Domäne verbundene Einheiten)  |
| SRS v2 – Microsoft Monitoring Agent Package | Softwarepaket       | Optional – Paket zum Bereitstellen und Konfigurieren des Microsoft Operations Management Suite-Agents|
| SRS v2 – WinPE-Hintergrundpaket    | Softwarepaket       | Paket für das benutzerdefinierte Hintergrundbild zur Verwendung mit Startbildern                           |
| Windows 10 Enterprise                | Betriebssystemabbild | Paket für die Installationsdatei des Betriebssystems (install.wim)                          |
| Surface Pro                          | Treiberpaket         | Paket für die Gerätetreiber und Firmware für Microsoft Surface Pro                     |
| Surface Pro 4                        | Treiberpaket         | Paket für die Gerätetreiber und Firmware für Microsoft Surface Pro 4                   |

Weitere Informationen finden Sie unter [Pakete und Programme in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Erstellen von Ordnern für die Paketquellendateien

Configuration Manager erfordert, dass Paketquellendateien in einer bestimmten Ordnerstruktur organisiert werden, wenn sie zum ersten Mal erstellt und aktualisiert werden.

Erstellen Sie die folgende Ordnerstruktur auf der Zentraladministrationswebsite oder primären Website von Microsoft Endpoint Configuration Manager oder auf einer Serverfreigabe, die Sie zum Hosten von Paketquellendateien verwenden:

-   SRS v2 – Microsoft Monitoring Agent Package
-   SRS v2 – Os Updates Package
-   SRS v2 – Stammzertifikatpaket
-   SRS v2 – Set-SRSComputerName Package
-   SRS v2 – SRS-Anwendungspaket
-   SRS v2 – Konfigurieren von SRS Setup
-   SRS v2 – Sysprep-Paket
-   Treiber
    -   Surface Pro
    -   Surface Pro 4
-   Betriebssysteme
    -   Windows 10 Enterprise

> [!TIP]
> Sie können [auch](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) die ZIP-Datei herunterladen und verwenden, die die Ordnerstruktur für die Pakete, die zu verwendenden Skripts und die Tasksequenzvorlage enthält, die Sie importieren müssen.

### <a name="create-the-monitoring-agent-package"></a>Erstellen des Überwachungs-Agent-Pakets

1. Laden Sie den Überwachungs-Agent von <https://go.microsoft.com/fwlink/?LinkId=828603> herunter.

2. Extrahieren Sie das Paket in den Ordner **SRS v2 – Microsoft Monitoring Agent Package,** indem Sie ein Eingabeaufforderungsfenster öffnen undMMASetup-AMD64.exe **/C:**     an der Eingabeaufforderung eingeben.

3. Wechseln Sie in der Configuration Manager-Konsole zu Anwendungsverwaltungspakete für **Softwarebibliotheken,** und \>  \> wählen Sie dann **Paket erstellen aus.**

4. Geben Sie die folgenden Informationen zum Erstellen des Pakets ein:

   - Name<strong>: SRS v2 – Microsoft Monitoring Agent Package</strong>

   - Hersteller:<strong>Microsoft Corporation</strong>

   - Version:<strong>8.1.11081.0</strong> (geben Sie die Version der heruntergeladenen Installationsdatei ein)

   - Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 - Microsoft Monitoring Agent Package** ein, und wählen Sie dann Weiter **aus.**

5. Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

6. Überprüfen Sie die **Seite Einstellungen bestätigen,** und wählen Sie dann **Weiter aus.**

7. Wählen Sie **Schließen aus.**

### <a name="create-the-operating-system-updates-package"></a>Erstellen des Updatespakets für das Betriebssystem

1. Erstellen Sie **im Ordner SRS v2 - OS Updates Package** ein neues PowerShell-Skript namens **Install-SRSv2-OS-Updates.ps1.**

2. Kopieren Sie das skript unten in das **Install-SRSv2-OS-Updates.ps1** Skript. Alternativ können Sie das Skript Install-SRSv2-OS-Updates.ps1 hier [herunterladen.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```
   # Install-SRSv2-OS-Updates.ps1
   $strPath = split-path -parent $MyInvocation.MyCommand.Definition
   $total = gci $strPath *.msu | measure | Select-Object -expand Count
   $i = 0
   gci $strPath *.msu | ForEach-Object {
     $i++
     WUSA ""$_.FullName /quiet /norestart""
     Write-Progress -activity "Applying Mandatory Updates" -status "Installing
     $_ .. $i of $total" -percentComplete (($i / $total) * 100)
     Wait-Process -name wusa
   }
   ```
3. Laden Sie die obligatorischen Windows Update-Pakete in denselben Ordner herunter.
   > [!NOTE]
   > Zum Zeitpunkt der Veröffentlichung dieses Artikels war nur [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) erforderlich. Aktivieren [Sie Konfigurieren einer Microsoft Teams Rooms-Konsole,](console.md)um festzustellen, ob weitere Updates erforderlich sind.

4. Wechseln Sie in der Configuration Manager-Konsole zu Anwendungsverwaltungspakete für **Softwarebibliotheken,** und \>  \> wählen Sie dann **Paket erstellen aus.**

5. Geben Sie die folgenden Informationen zum Erstellen des Pakets ein:
   -   Name: **SRS v2 – Os Updates Package**
   -   Hersteller: **Microsoft Corporation**
   -   Version: **1.0.0**
   -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 - OS Updates Package** ein, und wählen Sie dann Weiter **aus.**

6. Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

7. Überprüfen Sie die **Seite Einstellungen bestätigen,** und wählen Sie dann **Weiter aus.**

8. Wählen Sie **Schließen aus.**

### <a name="create-the-root-certificate-package-optional"></a>Erstellen des Stammzertifikatpakets (optional)

Sie erstellen dieses Paket, um das Stammzertifikat für Geräte zu verteilen, die nicht mit einer Active Directory-Domäne verbunden werden. Erstellen Sie dieses Paket nur, wenn beide der folgenden Bedingungen gelten:
-   Ihre Bereitstellung umfasst lokale Lync oder Skype for Business Server.
-   Microsoft Teams Rooms-Einheiten sind für die Arbeit in einer Arbeitsgruppe anstelle eines Domänenmitglieds konfiguriert.

1.  Kopieren Sie das Stammzertifikat in den **Ordner SRS v2 – Stammzertifikatpaket.**

2.  Wechseln Sie in der Configuration Manager-Konsole zu Anwendungsverwaltungspakete für **Softwarebibliotheken,** und \>  \> wählen Sie dann **Paket erstellen aus.**

3.  Geben Sie die folgenden Informationen zum Erstellen des Pakets ein:
    -   Name: **SRS v2 – Stammzertifikatpaket**
    -   Hersteller: *Name Ihrer Organisation*
    -   Version: **1.0.0**
    -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum **Ordner SRS v2 – Stammzertifikatpaket** ein, und wählen Sie dann Weiter **aus.**

4.  Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

5.  Überprüfen Sie die **Seite Einstellungen bestätigen,** und wählen Sie dann **Weiter aus.**

6.  Wählen Sie **Schließen aus.**

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Erstellen des Bereitstellungskitpakets für Microsoft Teams Rooms

1.  Laden Sie die neueste Version des **Bereitstellungskits für Microsoft Teams Rooms** von <https://go.microsoft.com/fwlink/?linkid=851168> herunter, und installieren Sie es auf einer Arbeitsstation.

2.  Kopieren Sie den Inhalt aus **C: \\ Program Files (x86) \\ Skype Room System Deployment Kit** in den Ordner **SRS v2 - SRS Application Package.**

3.  Wechseln Sie in der Configuration Manager-Konsole zu Anwendungsverwaltungspakete für **Softwarebibliotheken,** und \>  \> wählen Sie dann **Paket erstellen aus.**

4.  Geben Sie die folgenden Informationen zum Erstellen des Pakets ein:
    -   Name: **SRS v2 – SRS-Anwendungspaket**
    -   Hersteller: **Microsoft Corporation**
    -   Version: **3.1.104.0** (geben Sie die Version der heruntergeladenen Installationsdatei ein)
    -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 – SRS Application Package** ein, und wählen Sie dann Weiter **aus.**
5.  Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

6.  Überprüfen Sie die **Seite Einstellungen bestätigen,** und wählen Sie dann **Weiter aus.**

7.  Wählen Sie **Schließen aus.**

### <a name="create-the-computer-name-assignment-package"></a>Erstellen des Aufgabenpakets für Computernamen

1.  Erstellen Sie **im Ordner SRS v2 - Set-SRSComputerName Package** eine neue HTML-Anwendung mit dem Namen **Set-SRSComputerName.hta** .

2.  Kopieren Sie das folgende Skript in die **Datei Set-SRSComputerName.hta.** Alternativ können Sie die Datei Set-SRSComputerName.hta hier [herunterladen.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
    ```HTML
    <!DOCTYPE HTML>
    <html>
    <head>
    <title>Set SRS Computer Name</title>
    <HTA:APPLICATION
      APPLICATIONNAME="Set SRS Computer Name"
      ID="SetSRSComputerName"
      VERSION="1.0"
      SCROLL="no"
      SINGLEINSTANCE="yes"
      WINDOWSTATE="maximize"
      MaximizeButton="no"
      MinimizeButton="no"
      SysMenu="no"
      ShowInTaskbar="no"
      Caption="no"
      />
    <style type="text/css">
    body {
        background-color: #fdfeff;
        color: darkblue;
        font-family: Calibri;
        font-size: 12pt;
        margin: 4em 3em;
    }
    </style>
    </head>
    <script language="VBScript">
    Public strNewComputerName
    Sub GenerateComputerName()
        strComputer = "."
        Set objWMIService = GetObject("winmgmts:\\" & strComputer & "\root\cimv2")
        Set colItems = objWMIService.ExecQuery("Select * from Win32_BIOS",,48)
        For Each objItem in colItems
            strSerialNumber = objItem.SerialNumber
        Next
        strNewComputerName = "SRS-"  & right(replace(strSerialNumber, "-","") ,10)
        TextArea1.innerHTML = "The serial number of the device: " & strSerialNumber
        strHTMLText = strHTMLText & "<br> Computer name to be assigned: <font color = red>" & strNewComputerName & "</font>"
        strHTMLText = strHTMLText & "<br><br> Click Accept to use this as the computer name and continue deployment, or Change to set a new name."
        strHTMLText = strHTMLText & "<p><input type=""button"" value=""Accept"" name = ""Accept_Button"" onclick=""SetComputerName"" />"
        strHTMLText = strHTMLText & " <input type=""button"" value=""Change"" name = ""Change_Button"" onclick=""ChangeComputerName"" />"
        TextArea2.innerHTML = strHTMLText
    End Sub

    Sub SetComputerName()
        dim result
        result = MsgBox("Computer Name to be assigned: " & strNewComputerName &vbcrlf & "Are you sure you want to continue?", 36)
        If (result = vbYes) then
            SET env = CreateObject("Microsoft.SMS.TSEnvironment")
            env("OSDComputerName") = strNewComputerName
            self.close
        elseif (result = vbNo) then
            Window_OnLoad
        End If
    End Sub

    Sub UpdateComputerName()
        strNewComputerName = newcomputername.value
        if len(trim(strNewComputerName)) = 0 then
            MsgBox "Computer name cannot be empty." &vbcrlf & "Update and try again.",16
            exit sub
        end if
        SetComputerName
    End Sub

    Sub ChangeComputerName()
        TextArea2.innerHTML = "<p>Type the new computer name and click Accept:  <input type=""text"" name=""newcomputername"" value =" & strNewComputerName & " />"
        TextArea2.innerHTML = TextArea2.innerHTML & "<br><input type=""button"" value=""Update"" name = ""Update_Button"" onclick=""UpdateComputerName"" />"
    End Sub

    Sub Window_OnLoad
        Set oTSProgressUI = CreateObject("Microsoft.SMS.TsProgressUI")
        oTSProgressUI.CloseProgressDialog
        GenerateComputerName
    End Sub
    </script>

    <body>
    <span id = "TextArea1"></span>
    <span id = "TextArea2">
    </span>
    </body>
    </html>

    ```
3.  Wechseln Sie in der Configuration Manager-Konsole zu Anwendungsverwaltungspakete für **Softwarebibliotheken,** und \>  \> wählen Sie dann **Paket erstellen aus.**

4.  Geben Sie die folgenden Informationen zum Erstellen des Pakets ein:

    -   Name: **SRS v2 – Set-SRSComputerName Package**

    -   Hersteller: **Microsoft Corporation**

    -   Version: **1.0.0**

    -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 - Set-SRSComputerName Paket** ein, und wählen Sie dann Weiter **aus.**

5.  Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

6.  Überprüfen Sie die **Seite Einstellungen bestätigen,** und wählen Sie dann **Weiter aus.**

7.  Wählen Sie **Schließen aus.**

### <a name="create-the-sysprep-package"></a>Erstellen des Sysprep-Pakets

1. Erstellen Sie **im Ordner SRS v2 – Sysprep Package** eine neue XML-Datei mit dem Namen **Unattend.xml.**

2. Kopieren Sie den folgenden Text in die **Unattend.xml** Datei. Alternativ können Sie die Datei Unattend.xml hier [herunterladen.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
   ```XML
   <?xml version="1.0" encoding="utf-8"?>
   <unattend xmlns="urn:schemas-microsoft-com:unattend">
   <settings pass="specialize">
       <component name="Microsoft-Windows-Embedded-BootExp" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="NonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <DisableBootMenu>1</DisableBootMenu>
           <DisplayDisabled>1</DisplayDisabled>
       </component>
       <component name="Microsoft-Windows-powercpl" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <PreferredPlan>8c5e7fda-e8bf-4a96-9a85-a6e23a8c635c</PreferredPlan>
       </component>
   </settings>
   <settings pass="oobeSystem">
       <component name="Microsoft-Windows-Shell-Setup" processorArchitecture="amd64" publicKeyToken="31bf3856ad364e35" language="neutral" versionScope="nonSxS" xmlns:wcm="https://schemas.microsoft.com/WMIConfig/2002/State" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
           <OOBE>
               <HideEULAPage>true</HideEULAPage>
               <HideLocalAccountScreen>true</HideLocalAccountScreen>
               <HideOEMRegistrationScreen>true</HideOEMRegistrationScreen>
               <HideOnlineAccountScreens>true</HideOnlineAccountScreens>
               <HideWirelessSetupInOOBE>true</HideWirelessSetupInOOBE>
               <SkipMachineOOBE>true</SkipMachineOOBE>
               <SkipUserOOBE>true</SkipUserOOBE>
               <ProtectYourPC>1</ProtectYourPC>
           </OOBE>
           <AutoLogon>
               <Enabled>true</Enabled>
               <Username>Skype</Username>
               <Password>
                   <Value>UABhAHMAcwB3AG8AcgBkAA==</Value>
                   <PlainText>false</PlainText>
               </Password>
           </AutoLogon>
           <UserAccounts>
               <LocalAccounts>
                   <LocalAccount wcm:action="add">
                       <Password>
                           <Value>cwBmAGIAUABhAHMAcwB3AG8AcgBkAA==</Value>
                           <PlainText>false</PlainText>
                       </Password>
                       <Name>Admin</Name>
                       <Group>Administrators</Group>
                       <DisplayName>Administrator</DisplayName>
                       <Description>Administrator</Description>
                   </LocalAccount>
               </LocalAccounts>
           </UserAccounts>
       </component>
   </settings>
   <cpi:offlineImage cpi:source="wim:h:/install.wim#Windows 10 Enterprise" xmlns:cpi="urn:schemas-microsoft-com:cpi" />
   </unattend>
   ```
3. Wechseln Sie in der Configuration Manager-Konsole zu Anwendungsverwaltungspakete für **Softwarebibliotheken,** und \>  \> wählen Sie dann **Paket erstellen aus.**

4. Geben Sie die folgenden Informationen zum Erstellen des Pakets ein:
   -   Name: **SRS v2 - Sysprep Package**
   -   Hersteller: **Microsoft Corporation**
   -   Version: **1.0.0**
   -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 – Sysprep-Paket** ein, und wählen Sie dann **Weiter aus.**
5. Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

6. Überprüfen Sie die **Seite Einstellungen bestätigen,** und wählen Sie dann **Weiter aus.**

7. Wählen Sie **Schließen aus.**

### <a name="create-the-windows-10-enterprise-package"></a>Erstellen des Windows 10 Enterprise-Pakets

1.  Rufen Sie ein Windows 10 Enterprise x64-Medium ab, und kopieren Sie die **Datei install.wim** in den **Windows \\ 10 Enterprise-Ordner für Betriebssysteme.**

2.  Wechseln Sie in der Configuration Manager-Konsole zu Betriebssystemabbilder der **Softwarebibliothek,** und wählen Sie \>  \>  **dann Betriebssystemabbild hinzufügen aus.**

3.  Geben Sie den Pfad der gerade kopierten **install.wim-Datei** an, und wählen Sie dann **Weiter aus.**

4.  Aktualisieren Sie **das Feld Version,** um der Buildnummer des Windows 10 Enterprise-Bilds zu entsprechen, und wählen Sie dann **Weiter aus.**

5.  Überprüfen Sie die **Seite Details,** und wählen Sie dann **Weiter aus.**

6.  Wählen Sie **Schließen aus.**

Weitere Informationen finden Sie unter [Verwalten von Betriebssystembildern mit Configuration Manager](/configmgr/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Erstellen Surface Pro Gerätetreiberpakete

Microsoft Teams Rooms wird sowohl für Surface Pro als auch Surface Pro 4 unterstützt. Sie müssen ein Treiberpaket für jedes Surface Pro in Ihrer Umgebung erstellen.

> [!IMPORTANT]
> Die Treiber müssen mit dem Windows 10 Enterprise-Build und der Microsoft Teams Rooms-Bereitstellungskitversion kompatibel sein. Weitere Informationen finden Sie unter [Herunterladen der neuesten Firmware und Treiber für Surface-Geräte](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) und Konfigurieren einer [Konsole.](console.md)

1.  Laden Sie die neuesten Treiber und Firmware herunter.
    -   Für Surface Pro: <https://www.microsoft.com/download/details.aspx?id=55484>
    -   Für Surface Pro 4: <https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extrahieren Sie den heruntergeladenen Treiber und die Firmware. Öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie an der Eingabeaufforderung einen der folgenden Befehle ein:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  Wechseln Sie in der Configuration Manager-Konsole zu **Treiber** für Betriebssysteme der \>  \> Softwarebibliothek, und wählen Sie **Treiber importieren aus.**

4.  Wählen Sie Alle Treiber im folgenden Netzwerkpfad **(UNC)** importieren aus, wählen Sie den Quellordner aus (z. B. C: _Sources Treiber Surface Pro), und wählen Sie dann \\ \\ Weiter \\ **aus.**

5.  Wählen Sie **auf der Seite Details für** die importierten Treiber angeben alle aufgelisteten Treiber aus, und wählen Sie dann Diese Treiber aktivieren aus, und erlauben Sie Computern, sie zu **installieren.**

6.  Wählen **Sie Kategorien** aus, erstellen Sie eine neue Kategorie, die dem Surface-Modell entspricht, wählen Sie **OK** und dann **Weiter aus.**

7.  Wählen **Sie Neues Paket aus.**

8.  Geben Sie den Paketnamen an, der dem Surface Pro entspricht, geben Sie einen Ordnerpfad ein, in dem die Treiberpaketdateien gespeichert werden, wählen Sie **OK** und dann **Weiter aus.**

9.  Stellen Sie **auf der** Seite Startbilder sicher, dass keine Startbilder ausgewählt sind, und wählen Sie dann **Weiter aus.**

10. Wählen Sie **Schließen aus.**

11. Wechseln Sie **zu Treiber** für Betriebssysteme der Softwarebibliothek, wählen Sie Ordner erstellen Ordner aus, und geben Sie einen Ordnernamen ein, der dem Surface Pro entspricht, für das Sie die Treiber gerade \>  \> importiert haben. **\>**

12. Verschieben Sie alle importierten Treiber in den neu erstellten Ordner, um die Navigation und Bedienung zu vereinfachen.

> [!NOTE]
> Wiederholen Sie die gleichen Schritte für andere Surface Pro, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Verwalten von Treibern in Configuration Manager](/configmgr/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Erstellen eines Microsoft Teams Rooms-Konfigurationspakets

1.  Wechseln Sie in der Configuration Manager-Konsole zu Anwendungsverwaltungspakete für **Softwarebibliotheken,** und \>  \> wählen Sie dann **Paket erstellen aus.**

2.  Geben Sie die folgenden Informationen zum Erstellen des Pakets ein:

    -   Name: **SRS v2 – Konfigurieren des SRS-Setuppakets**

    -   Hersteller: **Microsoft Corporation**

    -   Version: **1.0.0**

    -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum **Ordner SRS v2 - Konfigurieren von SRS Setup** ein, und wählen Sie dann Weiter **aus.**

3.  Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

4.  Überprüfen Sie die **Seite Einstellungen bestätigen,** und wählen Sie dann **Weiter aus.**

5.  Wählen Sie **Schließen aus.**



## <a name="distribute-configuration-manager-packages"></a>Verteilen von Configuration Manager-Paketen

Alle Pakete müssen an die Server verteilt werden, denen die Verteilungspunktrolle in der Configuration Manager-Hierarchie zugewiesen wurde. Befolgen Sie die nachstehenden Anweisungen, um die Paketverteilung zu initiieren.

1.  Verteilen Sie Softwarepakete.

    1.  Wechseln Sie in der  Configuration Manager-Konsole zu \> **Anwendungsverwaltungspakete für** \> **Softwarebibliotheken.** Wählen Sie alle Softwarepakete aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen aus.**

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann **Weiter aus.**

    3.  Fügen Sie der Liste alle Verteilungspunktserver (oder Verteilerpunktgruppen, je nach Configuration Manager-Hierarchie) hinzu, und wählen Sie dann **Weiter aus.**

    4.  Wählen **Sie Weiter** und dann Schließen **aus.**

2.  Verteilen Sie Treiberpakete.

    1.  Wechseln Sie in der Configuration Manager-Konsole zu **Treiberpakete** für \> **Betriebssysteme** der \> **Softwarebibliothek.** Wählen Sie alle Treiberpakete aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen aus.**

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann **Weiter aus.**

    3.  Fügen Sie der Liste alle Verteilungspunktserver (oder Verteilerpunktgruppen, je nach Configuration Manager-Hierarchie) hinzu, und wählen Sie dann **Weiter aus.**

    4.  Wählen **Sie Weiter** und dann Schließen **aus.**

3.  Verteilen sie Betriebssystempakete.

    1.  Wechseln Sie in der Configuration Manager-Konsole zu **Betriebssystemabbilder** der \>  \> Softwarebibliothek. Wählen Sie alle Betriebssystembilder aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen aus.**

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann **Weiter aus.**

    3.  Fügen Sie der Liste alle Verteilungspunktserver (oder Verteilerpunktgruppen, je nach Configuration Manager-Hierarchie) hinzu, und wählen Sie dann **Weiter aus.**

    4.  Wählen **Sie Weiter** und dann Schließen **aus.**

> [!NOTE]
> Die Paketverteilung kann je nach Paketgröße, Configuration Manager-Hierarchie, Anzahl der Verteilungspunktserver und der im Netzwerk verfügbaren Bandbreite einige Zeit dauern.
> 
> Alle Pakete müssen verteilt werden, bevor Sie mit der Bereitstellung einer Microsoft Teams Rooms-Einheit beginnen können.
> 
> Sie können den Status Ihrer Paketverteilung in der Configuration Manager-Konsole überprüfen, indem Sie **den Inhaltsstatus des** \> **Verteilungsstatus** \> **überwachen.**

## <a name="configuration-manager-task-sequences"></a>Tasksequenzen von Configuration Manager

Sie verwenden Tasksequenzen mit Configuration Manager, um die Schritte zum Bereitstellen eines Betriebssystemabbilds auf einem Zielcomputer zu automatisieren. Um eine Microsoft Teams Rooms-Einheit automatisiert bereitstellen zu können, erstellen Sie eine Tasksequenz, die auf das Startabbild verweist, das zum Starten des Zielcomputers Microsoft Teams Rooms verwendet wird, das Windows 10 Enterprise-Betriebssystemabbild, das Sie installieren möchten, und alle anderen zusätzlichen Inhalte, z. B. andere Anwendungen oder Softwareupdates.

### <a name="import-the-sample-task-sequence"></a>Importieren der Beispielaufgabessequenz

Sie können eine Beispiel-Tasksequenz herunterladen und auf einfache Weise importieren und an Ihre Anforderungen anpassen.

1.  [**Laden Sie**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) die Beispielaufgabe herunter, und kopieren Sie die heruntergeladene ZIP-Datei an einen freigegebenen Speicherort.
2.  Wechseln Sie in der Configuration Manager-Konsole zu Tasksequenzen der **Softwarebibliothek** für Betriebssysteme, und \>  \> wählen Sie **Tasksequenz importieren aus.**

3.  Wählen **Sie Durchsuchen** aus, wechseln Sie zu dem speicherort für freigegebene Ordner, den Sie in Schritt 1 verwendet haben, wählen Sie die Microsoft Teams Rooms Deployment **(EN-US).zip-Datei** und dann Weiter **aus.**

4.  Legen **Sie Aktion** auf Neu **erstellen** und dann Weiter **aus.**

5.  Bestätigen Sie die Einstellungen, und wählen Sie dann **Weiter aus.**

6.  Wählen Sie **Schließen aus.**

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Überprüfen Sie, ob die Referenzpakete ordnungsgemäß mit jedem Vorgangssequenzschritt verknüpft sind.

1. Wählen Sie die importierte Tasksequenz und dann **Bearbeiten aus.**

    Der Aufgabensequenz-Editor wird geöffnet und zeigt jeden sequenziellen Schritt an, den Sie zum Bereitstellen und Konfigurieren einer Microsoft Teams Rooms-Einheit benötigen.

2. Führen Sie die einzelnen Schritte durch, und führen Sie die empfohlenen Updates aus:

   1. **Neustart in Windows PE:** Dieser Schritt wird neu gestartet und startet den Computer dann in Windows PXE. Für diesen Schritt sind keine Änderungen erforderlich.

   2. **Partition Disk 0 – UEFI**: Mit diesem Schritt wird die Datenträgerkonfiguration zurückgesetzt und Partitionen basierend auf den konfigurierten Einstellungen erstellt. Wir empfehlen, dass Sie keine Änderungen an diesem Schritt vornehmen.

   3. **Festlegen des SRS-Computernamens:** Dieser Schritt enthält eine HTML-Anwendung, mit der eine UI zum Festlegen eines Computernamens für die Microsoft Teams Rooms-Einheit während der Bereitstellung zur Verfügung steht.
      -  Dies ist ein optionaler Schritt, kann aber nur deaktiviert werden, wenn Sie die Computerbenennung über einen alternativen Prozess verwalten möchten.
      -  Vergewissern Sie **sich, dass das SrS v2 - Set-SRSComputerName-Paket** ausgewählt ist. Wenn nicht, navigieren Sie zum Paket, und wählen Sie es aus.

   4. **Betriebssystem anwenden:** Dieser Schritt gibt das zu bereitstellende Betriebssystemabbild und die unbeaufsichtigte Sysprep-Antwortdatei an, die verwendet werden soll.
      -  Vergewissern Sie sich, dass die richtige Windows 10 Enterprise-Abbilddatei ausgewählt ist.
      -  Vergewissern Sie sich, dass Die Verwendung einer unbeaufsichtigten Oder **Sysprep-Antwortdatei** für eine benutzerdefinierte Installation aktiviert ist und das **SRS v2 - Sysprep-Paket** ausgewählt ist. Stellen Sie außerdem sicher, **dass** dateiname auf **unattend.xml.**

   5. **Anwenden von Windows-Einstellungen:** In diesem Schritt werden Informationen zur Windows-Installation gesammelt.
      -  Stellen Sie Lizenzierungs- und Registrierungsinformationen wie product key, local administrator account password und zeitzone (je nach Ihren Anforderungen) zur Verfügung.

   6. **Netzwerkeinstellungen anwenden:** In diesem Schritt können Sie eine Arbeitsgruppe oder einen Active Directory-Domänennamen und eine Organisationseinheit angeben.
      > [!NOTE]
      > Unter [Skype Room System domain joining considerations](domain-joining-considerations.md) for recommended actions you need to take in deploying Microsoft Teams Rooms units as members of an Actve Directory domain.
   7. **Anwenden von Treibern:** Dieser Schritt und seine Unterschritte werden verwendet, um entsprechende Gerätetreiber und Firmware basierend auf dem verwendeten Surface Pro bereitstellen. Aktualisieren Sie jeden Schritt, um das relevante Treiberpaket anzugeben, das dieser Bereitstellung zugeordnet ist.
      -   Jedes Treiberpaket ist so konfiguriert, dass WMI-Filter (Windows Management Instrumentation) verwendet werden, um relevante Treiber und Firmware basierend auf Surface Pro und Modell bereitstellen zu können.
      -   Es wird dringend empfohlen, die Konfiguration dieser Treiber nicht zu ändern, da andernfalls die Bereitstellung fehlschlagen kann.

   8. **Einrichten von Windows und Configuration Manager:** In diesem Schritt wird der Configuration Manager-Client bereitgestellt und konfiguriert. Aktualisieren Sie diesen Schritt, um das integrierte Configuration Manager-Clientpaket anzugeben.

   9. **Stammzertifikat installieren:** Dieser Schritt verteilt das Stammzertifikat für Nicht-Domänen-angeschlossene Geräte und ist daher optional und standardmäßig deaktiviert.
      -   Aktivieren Sie diesen Schritt, wenn Sie ein Stammzertifikat für die Microsoft Teams Rooms-Einheiten bereitstellen müssen.
      -   Wenn Sie diesen Schritt ausführen müssen, vergewissern Sie sich, dass das **SRS v2 - Stammzertifikatpaket** und die Umleitung des **64-Bit-Dateisystems** deaktivieren ausgewählt sind.

   10. **Installieren und Konfigurieren des Überwachungs-Agents:** In diesem Schritt wird die 64-Bit-Version des Microsoft Azure Monitor-Agents installiert und der Agent so konfiguriert, dass er eine Verbindung mit Ihrem Log Analytics-Arbeitsbereich herstellen kann.
       -   Dieser Schritt ist standardmäßig deaktiviert. Aktivieren Sie diesen Schritt nur, wenn Sie den Monitoring Agent verwenden möchten, um den Status Ihrer Microsoft Teams Rooms-Einheiten zu überwachen.
       -   Bearbeiten Sie diesen Schritt, und aktualisieren Sie die Befehlszeilenparameter, um Ihre **Arbeitsbereichs-ID und** **Arbeitsbereichsschlüssel anzugeben.**
       -   Weitere Informationen zum Abrufen der Operations Management Suite Workspace ID und des Primärschlüssels finden Sie unter Konfigurieren von Testgeräten für [Azure Monitoring.](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)
       -   Vergewissern Sie sich, **dass das SRS v2 – Microsoft Monitoring Agent Package** und Die Umleitung des **64-Bit-Dateisystems** deaktivieren ausgewählt sind.
       -   Weitere Informationen zum Überwachen der Integrität Ihrer Microsoft Teams Rooms-Bereitstellung finden Sie unter Planen der Verwaltung von Microsoft Teams-Räumen mit [Azure Monitor,](azure-monitor-plan.md)Bereitstellen der Verwaltung von [Microsoft Teams-Räumen](azure-monitor-deploy.md) mit Azure Monitor und Verwalten von Microsoft Teams Rooms-Geräten mit [Azure Monitor.](azure-monitor-manage.md)

   11. **Kopieren von SRS v2-Konfigurationsdateien:** In diesem Schritt werden die erforderlichen Setup- und Konfigurationsdateien aus dem Microsoft Teams Rooms-Bereitstellungskit auf die lokale Festplatte kopiert. Für diesen Schritt ist keine Anpassung erforderlich.
       -   Vergewissern Sie **sich, dass das SRS v2 – SRS-Anwendungspaket** und die Umleitung des **64-Bit-Dateisystems** deaktivieren ausgewählt sind.

   12. **Install-SRSv2-OS-Updates:** In diesem Schritt werden alle obligatorischen Betriebssystemupdates bereitgestellt, die für die Bereitstellung von Microsoft Teams Rooms erforderlich sind. Gehen Sie folgendermaßen vor:
       -   Aktivieren [Sie Konfigurieren einer Microsoft Teams Rooms-Konsole,](console.md) um zu sehen, welche Updates erforderlich sind.
       -   Vergewissern Sie **sich, dass Ihr SRS v2 – OS-Updates-Paket** alle erforderlichen Updates enthält.
       -   Vergewissern Sie **sich, dass das SRS v2 – OS-Updates-Paket** ausgewählt ist.
       -   Vergewissern Sie sich, dass die PowerShell-Ausführungsrichtlinie auf **Umgehen festgelegt ist.**

   13. **Computer neu** starten: In diesem Schritt wird der Computer neu gestartet, nachdem die obligatorischen Betriebssystemupdates installiert wurden. Für diesen Schritt ist keine Anpassung erforderlich.

   14. **Konfigurieren von Windows-Komponenten:** In diesem Schritt werden die erforderlichen Windows-Features konfiguriert. Für diesen Schritt ist keine Anpassung erforderlich.

   15. **Computer neu** starten: In diesem Schritt wird der Computer neu gestartet, nachdem die Windows-Features konfiguriert wurden. Für diesen Schritt ist keine Anpassung erforderlich.

   16. **Lokaler Skype-Benutzer** hinzufügen: Mit diesem Schritt wird das lokale Skype-Konto erstellt, mit dem sie sich automatisch bei Windows anmelden und die Microsoft Teams Rooms-Anwendung starten. Diesem Schritt ist kein Softwarepaket zugeordnet, und es ist keine Anpassung erforderlich.

   17. **Einrichten und Konfigurieren der SRS-Anwendung:** In diesem Schritt wird die Microsoft Teams Rooms-Anwendungsinstallation für den nächsten Start des Betriebssystems konfiguriert.
       -   Vergewissern Sie **sich, dass srS v2 – Konfigurieren des SRS-Setuppakets** und Deaktivieren der **64-Bit-Dateisystemumleitung** ausgewählt sind.

> [!IMPORTANT]
> Es ist sehr wichtig, dass die Vorgangssequenzschritte in der angegebenen Reihenfolge ausgeführt werden. Wenn Sie die Reihenfolge der Schritte ändern oder zusätzliche Schritte konfigurieren, kann die Bereitstellung möglicherweise nicht mehr erforderlich sein.
>
> **Der Schritt zum Einrichten und Konfigurieren der SRS-Anwendung** muss der letzte Schritt in der Tasksequenz sein, andernfalls kann die Bereitstellung fehlschlagen.

### <a name="create-deployment-for-the-task-sequence"></a>Erstellen der Bereitstellung für die Tasksequenz

1. Wählen Sie die Tasksequenz und dann Bereitstellen **aus.**

2. Wählen **Sie Durchsuchen** aus, um die Zielsammlung für die Bereitstellung auszuwählen.

3. Wählen **Sie Alle unbekannten Computer** und dann OK **aus.**

4. Wählen Sie **Weiter aus.**

5. Wählen **Sie in der** **Dropdownliste Zweck** die Option Verfügbar aus.

6. Wählen Sie in der Liste  Verfügbar für die folgende Liste nur Medien und **PXE** und dann Weiter **aus.**
   > [!WARNING]
   > Es ist sehr wichtig, **dass "Zweck"** auf Verfügbar **festgelegt ist.** Stellen Sie sicher, dass **der Zweck** **NICHT** auf Erforderlich **festgelegt ist.** Stellen Sie außerdem sicher, dass Sie im Folgenden die Optionen Nur Medien und **PXE** **auswählen.**
   >
   > Wenn Sie diese Werte auf etwas anderes festlegen, wird möglicherweise auf allen Computern das Bereitstellungsbild für Microsoft Teams Rooms angezeigt, wenn sie gestartet werden.
7. Geben Sie keinen Zeitplan an, und wählen Sie **Weiter aus.**

8. Ändern Sie nichts im Abschnitt **Benutzererfahrung,** und wählen Sie **Weiter aus.**

9. Ändern Sie im Abschnitt **Benachrichtigungen nichts,** und wählen Sie **Weiter aus.**

10. Ändern Sie nichts im Abschnitt **Verteilungspunkte,** und wählen Sie **Weiter aus.**

11. Bestätigen Sie die Einstellungen, und wählen Sie dann **Weiter aus.**

12. Wählen Sie **Schließen aus.**

<a name="validate-and-troubleshoot-the-solution"></a>Überprüfen und Behandeln von Problemen mit der Lösung
--------------------------------------

Nachdem Sie die Microsoft Endpoint Configuration Manager-Tasksequenzen abgeschlossen haben, müssen Sie einen Testlauf ausführen, um zu überprüfen, ob die Tasksequenz Microsoft Teams Rooms-Einheiten bereitstellen und konfigurieren kann.

1.  Verbinden Sie das Testgerät mit dem verkabelten Netzwerk, indem Sie einen der unterstützten Ethernetadapter oder das Surface-Dock verwenden. Wenn die PXE-Startfunktionalität nicht für Ihre Umgebung konfiguriert wurde, können Sie [](/configmgr/osd/deploy-use/create-bootable-media) das Startabbild auf dem zuvor erstellten USB-Flashlaufwerk verwenden, um von USB zu starten und eine Verbindung mit Configuration Manager herzustellen.

2.  Greifen Sie auf die Firmware zu, und starten Sie den PXE-Start:

    1.  Stellen Sie sicher, dass das Surface-Gerät ausgeschaltet ist.

    2.  Halten Sie die Schaltfläche **Lautstärke nach oben** gedrückt.

    3.  Drücken Sie die Schaltfläche **Power, und** lassen Sie sie los.

    4.  Nachdem das Gerät gestartet wurde, lassen Sie die **Schaltfläche "Volume Up"** los.

    5.  Wählen **Sie Startkonfiguration aus.**

    6.  Führen Sie einen der folgenden Schritte aus:

        -   Wählen **Sie PXE-Start** aus, und ziehen Sie ihn an den oberen Rand der Liste. Alternativ können Sie auf dem Netzwerkadapter nach links wischen, um das Gerät sofort zu starten. Dies wirkt sich nicht auf die Startreihenfolge aus.
        -   Wählen Sie das USB-Flashlaufwerk aus, das die Startmedien enthält.

3.  Wählen **Sie Beenden** und dann Jetzt neu starten **aus.**

4.  Wenn Sie dazu aufgefordert werden, wählen **Sie Für** Netzwerkstartdienst eingeben aus.

5.  Windows PE wird in den Arbeitsspeicher geladen, und der Tasksequenz-Assistent wird gestartet. Wählen **Sie Weiter aus,** um den Schritt fortzufahren.

6.  Wählen Sie die zuvor importierte Tasksequenz und dann Weiter **aus.**

7.  Nachdem die Datenträgerkonfiguration angewendet wurde, werden Sie aufgefordert, einen Computernamen für das Gerät anzugeben. Die Benutzeroberfläche zeigt einen empfohlenen Computernamen basierend auf der Seriennummer des Surface Pro an. Sie können entweder den vorgeschlagenen Namen annehmen oder einen neuen Namen angeben. Folgen Sie den Anweisungen auf dem Computernamenszuordnungsbildschirm. Wenn Sie Annehmen **auswählen,** beginnt die Bereitstellung.

8.  Der rest des Bereitstellungsprozesses erfolgt automatisch und fordert keine weiteren Benutzereingaben an.

9.  Nachdem die Bereitstellungsaufgabe die Konfiguration des Geräts abgeschlossen hat, wird der folgende Konfigurationsbildschirm angezeigt, in dem Sie zum Konfigurieren der Microsoft Teams Rooms-Anwendungseinstellungen gefragt werden.

    ![Ersteinrichtungsbildschirm für die Microsoft Teams Rooms-Anwendung](../media/room-systems-scale-image2.png)

10.  Schließen Sie die Surface Pro an die Microsoft Teams Rooms-Konsole an, und konfigurieren Sie die Anwendungseinstellungen.

11.  Überprüfen Sie, ob die in [der Microsoft Teams Rooms-Hilfe aufgeführten](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) Funktionen auf dem bereitgestellten Gerät funktionieren.


Um eine fehlgeschlagene Installation zu beheben, überprüfen Sie die **DATEI SMSTS.log,** in der alle schritte protokolliert werden, die in einer Configuration Manager-Tasksequenz ausgeführt werden.

Die Datei "SMSTS.log" wird je nach Phase des Buildprozesses auf einem von mehreren Pfaden gespeichert. Überprüfen Sie die folgende Tabelle, um den Pfad zur DATEI SMSTS.log zu identifizieren.


| **Bereitstellungsphase**                                                            | **Vorgangssequenzprotokollpfad**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE vor dem HDD-Format                                                        | X: \\ Windows \\ Temp \\ smstslog \\ smsts.log             |
| WinPE nach HDD-Format                                                         | C: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log    |
| Betriebssystem bereitgestellt, bevor der Configuration Manager-Agent installiert wurde | c: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log    |
| Betriebssystem und bereitgestellter Configuration Manager-Agent                   | %windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smsts.log |
| Ausführung der Tasksequenz abgeschlossen                                                | %windir% \\ System32 \\ ccm \\ protokolliert \\ smsts.log           |

> [!TIP]
> Sie können während der **Tasksequenz jederzeit F8** auswählen, um eine Befehlskonsole zu öffnen, und dann Zugriff auf die DATEI SMSTS.log erhalten.

Um Probleme mit dem PXE-Start zu beheben, überprüfen Sie die beiden Protokolldateien auf dem Configuration Manager-Server, die spezifisch für PXE-Aktionen sind:

-   **Pxecontrol.log**, befindet sich im Installationsverzeichnis von Configuration Manager

-   **Smspxe.log**, befindet sich im Verzeichnis der Configuration Manager Management Point (MP)-Protokolle.

Eine vollständige Liste der Protokolldateien, die Sie zur weiteren Problembehandlung Ihrer Configuration Manager-Installation verwenden können, finden Sie unter Microsoft Endpoint Configuration Manager [Log File Reference](/configmgr/core/plan-design/hierarchy/log-files).