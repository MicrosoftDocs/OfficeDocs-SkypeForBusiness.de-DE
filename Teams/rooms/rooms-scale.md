---
title: Bereitstellen Microsoft Teams-Räume mithilfe von Microsoft Endpoint Configuration Manager
author: dstrome
ms.author: dstrome
ms.reviewer: Turgayo
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection:
- M365-collaboration
description: Erfahren Sie, wie sie Microsoft Teams-Räume Bereitstellungen in großem Maßstab mithilfe von Microsoft Endpoint Configuration Manager.
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
ms.openlocfilehash: 27cd37df8516973ddf9fbe6401a1e4c21ce01e0a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731574"
---
# <a name="deploy-microsoft-teams-rooms-by-using-microsoft-endpoint-configuration-manager"></a>Bereitstellen Microsoft Teams-Räume mithilfe von Microsoft Endpoint Configuration Manager

Dieser Artikel enthält alle erforderlichen Informationen zum Erstellen Ihrer Microsoft Teams-Räume mithilfe von Microsoft Endpoint Configuration Manager.

Mit den einfach zu verwendende Methoden, die von Configuration Manager bereitgestellt werden, können Sie das Betriebssystem und andere Anwendungen auf mehreren Zielgeräten bereitstellen.

Verwenden Sie den unten dargestellten Ansatz, um Sie durch die Konfiguration des Konfigurations-Managers zu führen, und passen Sie die Beispielpakete und Skripts an, die in diesem Leitfaden für Ihre Organisation bereitgestellt werden.

![Microsoft Teams-Räume mit Configuration Manager.](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Diese Lösung wurde nur mit Surface Pro-basierten Bereitstellungen getestet. Befolgen Sie die Richtlinien des Herstellers für Konfigurationen, die nicht auf einem Surface Pro.

## <a name="validate-prerequisites"></a>Überprüfen der Voraussetzungen

Wenn Sie Microsoft Teams-Räume Configuration Manager bereitstellen möchten, stellen Sie sicher, dass Sie die folgenden Voraussetzungen und Anforderungen erfüllen.

### <a name="microsoft-endpoint-configuration-manager-requirements"></a>Microsoft Endpoint Configuration Manager Anforderungen

-   Microsoft Endpoint Configuration Manager-Version muss mindestens 1706 sein. Wir empfehlen die Verwendung von 1710 oder höher. Unter [Support für Windows 10 in Configuration Manager](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) finden Sie Informationen zu den Windows 10, die Configuration Manager unterstützt.

-   Es muss eine Windows Assessment and Deployment Kit (ADK) für Windows 10 installiert sein. Sehen Sie sich die Versionen des [Windows 10 ADK](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-adk) an, die Sie mit verschiedenen Versionen von Configuration Manager verwenden können, und stellen Sie sicher, dass Ihre Bereitstellung die richtige Version enthält.

-   Den Websitesystemservern muss die Verteilungspunktrolle zugewiesen worden sein, und die Startbilder sollten für die [PXE-Unterstützung (Preboot Execution Environment)](/configmgr/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) aktiviert sein, um über das Netzwerk initiierte Bereitstellungen zu ermöglichen. Wenn die PXE-Unterstützung nicht aktiviert ist, können Sie [startbare](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) Medien für Ihre Bereitstellungen verwenden.

-   Ein Netzwerkzugriffskonto muss für die Unterstützung neuer Computerbereitstellungsszenarien (bare Metal) konfiguriert werden. Weitere Informationen zur Konfiguration eines Netzwerkzugriffskontos finden Sie unter In [Configuration Manager verwendete Konten.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

-   Wir empfehlen, die [Multicastunterstützung](/configmgr/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)zu aktivieren, wenn Sie wahrscheinlich das gleiche Microsoft Teams-Räume-Bild in mehreren Einheiten gleichzeitig bereitstellen.

### <a name="networking-requirements"></a>Netzwerkanforderungen

-   Ihr Netzwerk sollte über einen DHCP-Server (Dynamic Host Configuration Protocol) verfügen, der für die automatische VERTEILUNG von IP-Adressen an die Subnetze konfiguriert ist, in Microsoft Teams-Räume ihre Einheiten bereitgestellt werden.

    > [!NOTE]
    > Die Dauer des DHCP-Leasens muss auf einen Wert festgelegt werden, der länger als die Dauer der Bildbereitstellung ist. Andernfalls kann die Bereitstellung fehlschlagen.

-   Ihr Netzwerk, einschließlich Switchen und virtueller LANs (VIRTUAL LANs, VIRTUAL LANs), sollte für die Unterstützung von PXE konfiguriert sein. Weitere Informationen zur IP-Hilfs- und PXE-Konfiguration finden Sie bei Ihrem Netzwerkanbieter. Alternativ können Sie [startbare](/configmgr/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) Medien für Ihre Bereitstellungen verwenden, wenn die PXE-Unterstützung nicht aktiviert ist.

    > [!NOTE]
    > Für Surface Pro wird das Starten über das Netzwerk (PXE-Boot) nur unterstützt, wenn Sie einen Ethernet-Adapter oder eine Dockingstation von Microsoft verwenden. Ethernet-Adapter von Drittanbietern unterstützen keinen PXE-Start mit Surface Pro. Weitere [Informationen finden Sie unter Ethernet-Adapter und Surface-Bereitstellung.](/surface/ethernet-adapters-and-surface-device-deployment)

## <a name="configure-microsoft-endpoint-configuration-manager-for-operating-system-deployment"></a>Konfigurieren Microsoft Endpoint Configuration Manager für die Bereitstellung des Betriebssystems

In diesem Artikel wird davon ausgegangen, dass Sie bereits über eine fehlerfreie Configuration Manager-Bereitstellung verfügen, und es werden nicht alle Schritte beschrieben, die erforderlich sind, um Configuration Manager von Grund auf neu zu implementieren und zu konfigurieren. Die [Dokumentation und der Konfigurationsleitfade](/configmgr/) auf der Microsoft Endpoint Configuration Manager sind eine großartige Ressource. wir empfehlen Ihnen, mit diesen Ressourcen zu beginnen, wenn Sie Configuration Manager noch nicht bereitgestellt haben.

Überprüfen Sie mithilfe der folgenden Anweisungen, ob die Betriebssystembereitstellungsfeatures ordnungsgemäß konfiguriert sind.

### <a name="validate-and-upgrade-configuration-manager"></a>Überprüfen und Aktualisieren von Configuration Manager

1.  Wechseln Sie in der  Configuration Manager-Konsole zu \> **Verwaltungsupdates und Wartung**.

2.  Überprüfen Sie den installierten Build und die anwendbaren Updates, die noch nicht installiert wurden.

3.  Überprüfen [Sie den Support für Windows 10 in Configuration Manager.](/configmgr/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) Wenn Sie ein Upgrade Ihrer Bereitstellung durchführen müssen, wählen Sie das Update aus, das Sie installieren möchten, und wählen Sie dann **Herunterladen aus.**

4.  Wählen Sie nach Abschluss des Downloads das Update und dann **Updatepaket installieren aus.**

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Konfigurieren von Verteilungspunkten zur Unterstützung von PXE und Multicast

1.  Wechseln Sie in der  Konfigurations-Manager-Konsole zu \> **Administrationsverteilungspunkte**.

2.  Wählen Sie den Verteilungspunktserver aus, der die Microsoft Teams-Räume wird, und wählen Sie dann Eigenschaften **aus.**

3.  Wählen Sie die **Registerkarte PXE** aus, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:
    -   Aktivieren der PXE-Unterstützung für Clients
    -   Zulassen, dass dieser Verteilungspunkt auf eingehende PXE-Anforderungen reagiert
    -   Unterstützung für unbekannten Computer aktivieren

4.  *Optional:* Um die Multicastunterstützung zu aktivieren, wählen Sie die **Registerkarte Multicast** aus, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:
    -   Aktivieren von Multicast zum gleichzeitigen Senden von Daten an mehrere Clients
    -   Konfigurieren des UDP-Portbereichs entsprechend der Empfehlung Ihres Netzwerkteams

### <a name="configure-the-network-access-account"></a>Konfigurieren des Netzwerkzugriffskontos

1.  Wechseln Sie in der Konfigurations-Manager-Konsole zu **Konfigurationswebsites** für \>  \> Verwaltungswebsites , und wählen Sie dann die Website aus.

2.  Wählen **Sie** Einstellungen Gruppe Websitekomponenten-Softwareverteilung  \> **konfigurieren aus.**

3.  Wählen Sie die **Registerkarte Netzwerkzugriffskonto** aus. Richten Sie ein oder mehrere Konten ein, und wählen Sie dann **OK aus.**

> [!NOTE]
> Für die Konten sind keine besonderen  Rechte erforderlich, außer der Zugriff auf diesen Computer über das Netzwerk direkt auf dem Verteilungspunktserver. Ein generisches Domänenbenutzerkonto ist geeignet. Weitere Informationen finden Sie unter [In Configuration Manager verwendete Konten.](/configmgr/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA)

### <a name="configure-a-boot-image"></a>Konfigurieren eines Startbilds

1.  Wechseln Sie in der Konfigurations-Manager-Konsole zu **Startbilder** für \> **das Betriebssystem der Softwarebibliothek.** \> 

2.  Wählen **Sie Startbild (x64)** und dann Eigenschaften **aus.**

3.  Wählen Sie die **Registerkarte Datenquelle** aus, und aktivieren Sie Deploy this boot image from **the PXE-enabled distribution point**.

4.  Wählen Sie die **Registerkarte Optionale Komponenten** aus, um erforderliche Komponenten zu installieren:

    1.  Wählen Sie das Sternsymbol aus, und suchen Sie nach **HTML (WinPE-HTA).**

    2.  Wählen **Sie OK** aus, um dem Startbild HTML-Anwendungsunterstützung hinzuzufügen.

5.  *Optional:* Um die Bereitstellungserfahrung anzupassen, wählen Sie die **Registerkarte Anpassung** aus.
    -   Aktivieren **Sie die Befehlsunterstützung (nur Test),** wenn Sie während der Bereitstellung Zugriff auf eine Eingabeaufforderung haben möchten. Wenn dies aktiviert ist, können Sie eine Eingabeaufforderung starten, indem Sie während der Bereitstellung **jederzeit F8** auswählen.
    -   Sie können auch ein benutzerdefiniertes Hintergrundbild angeben, das während der Bereitstellung angezeigt werden soll. Aktivieren Sie zum Festlegen eines Bilds **Die benutzerdefinierte Hintergrundbilddatei (UNC-Pfad) angeben,** und wählen Sie den Hintergrund aus.

6.  Wenn Sie dazu aufgefordert werden, wählen Sie **Ja aus,** und verteilen Sie das aktualisierte Startbild an Ihre Verteilungspunkte.

Weitere Informationen finden Sie unter [Verwalten von Startbildern mit Configuration Manager.](/configmgr/osd/get-started/manage-boot-images)

> [!NOTE]
> Sie können startbare USB-Medien erstellen, um tasksequenzbasierte Konfigurations-Manager-Bereitstellungen für Umgebungen zu initiieren, die keine PXE-Unterstützung bieten. Die startbaren Medien enthalten nur das Startbild, optionale Vorabstartbefehle und die erforderlichen Dateien sowie binäre Binärdateien für den Konfigurations-Manager, um das Starten in Windows PE und das Herstellen einer Verbindung mit Configuration Manager für den restlichen Bereitstellungsprozess zu unterstützen. Weitere Informationen finden Sie unter [Erstellen startbarer Medien.](/configmgr/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)

## <a name="create-configuration-manager-packages"></a>Erstellen von Konfigurations-Manager-Paketen

> [!IMPORTANT]
> Die erforderliche Betriebssystemversion für jede SRS-Installer-Version ändert sich bei jeder MSI-Version. Um die beste Betriebssystemversion für eine bestimmte MSI zu ermitteln, führen Sie das Konsoleneinrichtungsskript einmal aus. Weitere Informationen finden Sie unter [Bereitstellen Microsoft Teams-Räume mithilfe von Microsoft Endpoint Configuration Manager.](rooms-scale.md)

Configuration Manager erfordert eine Reihe von Paketen zum Bereitstellen und Konfigurieren der Microsoft Teams-Räume Einheiten.

Sie müssen die folgenden Pakete erstellen und konfigurieren und sie dann an die Configuration Manager-Websitesysteme verteilen, denen die Serverrolle "Verteilungspunkt" zugewiesen wurde.

| **Paketname**                     | **Typ**               | **Beschreibung**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 – SRS-Anwendungspaket     | Softwarepaket       | Paket für das Microsoft Teams-Räume-Bereitstellungskits                                      |
| SRS v2 – Sysprep-Paket             | Softwarepaket       | Paket für den benutzerdefinierten Unattended.xml zum Konfigurieren Microsoft Teams-Räume Einheiten            |
| SRS v2 – Set-SRSComputerName Package | Softwarepaket       | Paket für die HTML-Anwendung (HTA), um während der Bereitstellung einen Computernamen zuzuordnen    |
| SRS v2 – Konfigurieren des SRS-Setups         | Softwarepaket       | Paket zum Konfigurieren der Bereitstellung der Microsoft Teams-Räume-App                          |
| SRS v2 – Os Updates Package          | Softwarepaket       | Paket zum Bereitstellen obligatorischer Betriebssystemupdates                                      |
| SRS v2 – Stammzertifikatpaket    | Softwarepaket       | Optional – Paket zum Bereitstellen des Stammzertifikats (nicht erforderlich für Einheiten, die einer Domäne beigetreten sind)  |
| SRS v2 – Microsoft Monitoring Agent Package | Softwarepaket       | Optional – Paket zum Bereitstellen und Konfigurieren des Agents der Microsoft Operations Management Suite|
| SRS v2 – WinPE-Hintergrundpaket    | Softwarepaket       | Paket für das benutzerdefinierte Hintergrundbild zur Verwendung mit Startbildern                           |
| Windows 10 Enterprise                | Betriebssystemabbild | Paket für die Installationsdatei des Betriebssystems (install.wim)                          |
| Surface Pro                          | Treiberpaket         | Paket für die Gerätetreiber und Firmware für Microsoft Surface Pro                     |
| Surface Pro 4                        | Treiberpaket         | Paket für die Gerätetreiber und Firmware für Microsoft Surface Pro 4                   |

Weitere Informationen finden Sie unter [Pakete und Programme in Configuration Manager.](/configmgr/apps/deploy-use/packages-and-programs)

### <a name="create-folders-for-the-package-source-files"></a>Erstellen von Ordnern für die Paketquellendateien

Im Konfigurations-Manager müssen die Paketquellendateien bei der ersten Erstellten und Aktualisierung in einer bestimmten Ordnerstruktur organisiert sein.

Erstellen Sie die folgende Ordnerstruktur auf der Microsoft Endpoint Configuration Manager Der Zentraladministration oder der primären Website oder auf einer Serverfreigabe, die Sie zum Hosten von Paketquellendateien verwenden:

-   SRS v2 – Microsoft Monitoring Agent Package
-   SRS v2 – Os Updates Package
-   SRS v2 – Stammzertifikatpaket
-   SRS v2 – Set-SRSComputerName Package
-   SRS v2 – SRS-Anwendungspaket
-   SRS v2 – Konfigurieren des SRS-Setups
-   SRS v2 – Sysprep-Paket
-   Treiber
    -   Surface Pro
    -   Surface Pro 4
-   Betriebssysteme
    -   Windows 10 Enterprise

> [!TIP]
> Sie können [auch](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) die ZIP-Datei herunterladen und verwenden, die die Ordnerstruktur für die Pakete, die Skripts, die Sie verwenden müssen, und die Tasksequenz-Vorlage enthält, die Sie importieren müssen.

### <a name="create-the-monitoring-agent-package"></a>Erstellen des Überwachungs-Agent-Pakets

1. Laden Sie den Monitoring-Agent von <https://go.microsoft.com/fwlink/?LinkId=828603> herunter.

2. Extrahieren Sie das Paket in den **Ordner SRS v2 – Microsoft Monitoring Agent Package,** indem Sie ein Eingabeaufforderungsfenster öffnen undMMASetup-AMD64.exe **/C:** an der Eingabeaufforderung eingeben.

3. Wechseln Sie in der  Konfigurations-Manager-Konsole zu \> **Anwendungsverwaltungspakete** der \> Softwarebibliothek, und wählen Sie dann Paket **erstellen aus.**

4. Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:

   - Name:<strong>SRS v2 - Microsoft Monitoring Agent Package</strong>

   - Hersteller:<strong>Microsoft Corporation</strong>

   - Version:<strong>8.1.11081.0</strong> (geben Sie die Version der heruntergeladenen Installationsdatei ein)

   - Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 - Microsoft Monitoring Agent Package** ein, und wählen Sie weiter **aus.**

5. Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

6. Überprüfen Sie **die Seite Einstellungen bestätigen,** und wählen Sie dann Weiter **aus.**

7. Wählen Sie **Schließen aus.**

### <a name="create-the-operating-system-updates-package"></a>Erstellen des Updatespakets für das Betriebssystem

1. Erstellen Sie **im Ordner SRS v2 – Os Updates Package** ein neues PowerShell-Skript namens **Install-SRSv2-OS-Updates.ps1.**

2. Kopieren Sie das folgende Skript in das **Install-SRSv2-OS-Updates.ps1** Skript. Alternativ können Sie das Skript Install-SRSv2-OS-Updates.ps1 hier [herunterladen.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
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
3. Laden Sie die obligatorische Windows Updatepakete in denselben Ordner herunter.
   > [!NOTE]
   > Zum Zeitpunkt der Veröffentlichung dieses Artikels war nur [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) erforderlich. Aktivieren [Sie Konfigurieren Microsoft Teams-Räume -Konsole,](console.md)um festzustellen, ob andere Updates erforderlich sind.

4. Wechseln Sie in der  Konfigurations-Manager-Konsole zu \> **Anwendungsverwaltungspakete** der \> Softwarebibliothek, und wählen Sie dann Paket **erstellen aus.**

5. Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:
   -   Name: **SRS v2 – Os Updates Package**
   -   Hersteller: **Microsoft Corporation**
   -   Version: **1.0.0**
   -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 - Os Updates Package** ein, und wählen Sie dann Weiter **aus.**

6. Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

7. Überprüfen Sie **die Seite Einstellungen bestätigen,** und wählen Sie dann Weiter **aus.**

8. Wählen Sie **Schließen aus.**

### <a name="create-the-root-certificate-package-optional"></a>Erstellen des Stammzertifikatpakets (optional)

Sie erstellen dieses Paket, um das Stammzertifikat für Geräte zu verteilen, die nicht einer Active Directory-Domäne beigetreten sind. Erstellen Sie dieses Paket nur, wenn die beiden folgenden Bedingungen zu gelten:
-   Ihre Bereitstellung umfasst lokales Lync oder Skype for Business Server.
-   Microsoft Teams-Räume Einheiten sind so konfiguriert, dass sie in einer Arbeitsgruppe anstatt in einem Domänenmitglied arbeiten.

1.  Kopieren Sie das Stammzertifikat in **den Ordner SRS v2 – Stammzertifikatpaket.**

2.  Wechseln Sie in der  Konfigurations-Manager-Konsole zu \> **Anwendungsverwaltungspakete** der \> Softwarebibliothek, und wählen Sie dann Paket **erstellen aus.**

3.  Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:
    -   Name: **SRS v2 – Stammzertifikatpaket**
    -   Hersteller: *Name Ihrer Organisation*
    -   Version: **1.0.0**
    -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 –** Stammzertifikatpaket ein, und wählen Sie dann **Weiter aus.**

4.  Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

5.  Überprüfen Sie **die Seite Einstellungen bestätigen,** und wählen Sie dann Weiter **aus.**

6.  Wählen Sie **Schließen aus.**

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Erstellen des Microsoft Teams-Räume-Bereitstellungskits

1.  Laden Sie die neueste Version des Microsoft Teams-Räume **Von** <https://go.microsoft.com/fwlink/?linkid=851168> herunter, und installieren Sie es auf einer Arbeitsstation.

2.  Kopieren Sie den Inhalt aus **C: \\ Program Files (x86) \\ Skype Room System Deployment Kit** in den Ordner **SRS v2 – SRS Application Package.**

3.  Wechseln Sie in der  Konfigurations-Manager-Konsole zu \> **Anwendungsverwaltungspakete** der \> Softwarebibliothek, und wählen Sie dann Paket **erstellen aus.**

4.  Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:
    -   Name: **SRS v2 – SRS-Anwendungspaket**
    -   Hersteller: **Microsoft Corporation**
    -   Version: **3.1.104.0** (geben Sie die Version der heruntergeladenen Installationsdatei ein)
    -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 – SRS-Anwendungspaket** ein, und wählen Sie dann **Weiter aus.**
5.  Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

6.  Überprüfen Sie **die Seite Einstellungen bestätigen,** und wählen Sie dann Weiter **aus.**

7.  Wählen Sie **Schließen aus.**

### <a name="create-the-computer-name-assignment-package"></a>Erstellen des Namenszuweisungspakets für den Computer

1.  Erstellen Sie **im Ordner SRS v2 – Set-SRSComputerName Paket** eine neue HTML-Anwendung mit dem Namen **Set-SRSComputerName.hta.**

2.  Kopieren Sie das folgende Skript in die **Datei Set-SRSComputerName.hta.** Alternativ können Sie die Datei Set-SRSComputerName.hta von hier [herunterladen.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
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
3.  Wechseln Sie in der  Konfigurations-Manager-Konsole zu \> **Anwendungsverwaltungspakete** der \> Softwarebibliothek, und wählen Sie dann Paket **erstellen aus.**

4.  Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:

    -   Name: **SRS v2 – Set-SRSComputerName Package**

    -   Hersteller: **Microsoft Corporation**

    -   Version: **1.0.0**

    -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 - Set-SRSComputerName Package** ein, und wählen Sie dann Weiter **aus.**

5.  Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

6.  Überprüfen Sie **die Seite Einstellungen bestätigen,** und wählen Sie dann Weiter **aus.**

7.  Wählen Sie **Schließen aus.**

### <a name="create-the-sysprep-package"></a>Erstellen des Sysprep-Pakets

1. Erstellen Sie **im Ordner SRS v2 – Sysprep-Paket** eine neue XML-Datei namens **Unattend.xml.**

2. Kopieren Sie den folgenden Text in die **Unattend.xml** Datei. Alternativ können Sie die Datei Unattend.xml von hier [herunterladen.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)
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
3. Wechseln Sie in der  Konfigurations-Manager-Konsole zu \> **Anwendungsverwaltungspakete** der \> Softwarebibliothek, und wählen Sie dann Paket **erstellen aus.**

4. Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:
   -   Name: **SRS v2 – Sysprep-Paket**
   -   Hersteller: **Microsoft Corporation**
   -   Version: **1.0.0**
   -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 – Sysprep-Paket** ein, und wählen Sie dann **Weiter aus.**
5. Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

6. Überprüfen Sie **die Seite Einstellungen bestätigen,** und wählen Sie dann Weiter **aus.**

7. Wählen Sie **Schließen aus.**

### <a name="create-the-windows-10-enterprise-package"></a>Erstellen des Windows 10 Enterprise Pakets

1.  Rufen Sie Windows 10 Enterprise x64-Medien ab, und kopieren Sie die Datei **install.wim** in den Ordner **Windows 10 Enterprise \\** Betriebssysteme.

2.  Wechseln Sie in der Konfigurations-Manager-Konsole zu Betriebssystemimages der **Softwarebibliothek,** \>  \> und wählen Sie **dann Betriebssystemabbild hinzufügen aus.**

3.  Geben Sie den Pfad zu der Datei **"install.wim"** an, die Sie gerade kopiert haben, und wählen Sie dann **Weiter aus.**

4.  Aktualisieren Sie **das Feld "Version"** so, dass es der Buildnummer des Windows 10 Enterprise, und wählen Sie dann Weiter **aus.**

5.  Überprüfen Sie die **Seite Details,** und wählen Sie dann **Weiter aus.**

6.  Wählen Sie **Schließen aus.**

Weitere Informationen finden Sie unter [Verwalten von Betriebssystembildern mit Configuration Manager.](/configmgr/osd/get-started/manage-operating-system-images)

### <a name="create-surface-pro-device-driver-packages"></a>Erstellen Surface Pro Gerätetreiberpaketen

Microsoft Teams-Räume wird sowohl für Surface Pro als Surface Pro 4. Sie müssen ein Treiberpaket für jedes Surface Pro in Ihrer Umgebung erstellen.

> [!IMPORTANT]
> Die Treiber müssen mit dem Windows 10 Enterprise und der Version Microsoft Teams-Räume Bereitstellungskits kompatibel sein. Weitere Informationen finden Sie unter [Herunterladen der neuesten Firmware und Treiber für Surface-Geräte](/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) und Konfigurieren einer [Konsole.](console.md)

1.  Laden Sie die neuesten Treiber und Firmware herunter.
    -   Weitere Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Weitere Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extrahieren Sie den heruntergeladenen Treiber und die Firmware. Öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie an der Eingabeaufforderung einen der folgenden Befehle ein:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\Drivers\Surface Pro 4"`

3.  Wechseln Sie in der Konfigurations-Manager-Konsole zu Betriebssystemtreiber der **Softwarebibliothek,** \>  \> und wählen Sie dann **Treiber importieren aus.**

4.  Wählen Sie Alle Treiber im folgenden Netzwerkpfad **(UNC)** importieren aus, wählen Sie den Quellordner aus (z. B. C: _Sources Treiber Surface Pro), und wählen Sie dann \\ \\ Weiter \\ **aus.**

5.  Wählen Sie **auf der Seite Details für** die importierten Treiber angeben alle aufgeführten Treiber aus, und wählen Sie dann Diese Treiber aktivieren und Computer deren Installation zulassen **aus.**

6.  Wählen **Sie Kategorien** aus, erstellen Sie eine neue Kategorie, die dem Surface-Modell entspricht, wählen Sie **OK** und dann Weiter **aus.**

7.  Wählen Sie **Neues Paket aus.**

8.  Geben Sie den Paketnamen an, der dem Surface Pro-Modell entspricht, geben Sie einen Ordnerpfad ein, in dem die Treiberpaketdateien gespeichert werden, wählen Sie **OK** aus, und wählen Sie dann **Weiter aus.**

9.  Stellen Sie **auf der Startseite** der Startbilder sicher, dass keine Startbilder ausgewählt sind, und wählen Sie dann Weiter **aus.**

10. Wählen Sie **Schließen aus.**

11. Wechseln Sie **zu Betriebssystemtreiber** der Softwarebibliothek, wählen Sie Ordner erstellen Ordner aus, und geben Sie einen Ordnernamen ein, der dem Surface Pro, für das Sie die Treiber gerade \>  \> importiert haben. **\>**

12. Verschieben Sie alle importierten Treiber in den neu erstellten Ordner, um die Navigation und die Bedienung zu vereinfachen.

> [!NOTE]
> Wiederholen Sie die gleichen Schritte für Surface Pro, die Sie möglicherweise verwenden. Weitere Informationen finden Sie unter [Verwalten von Treibern in Configuration Manager.](/configmgr/osd/get-started/manage-drivers)

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Erstellen Microsoft Teams-Räume Konfigurationspakets

1.  Wechseln Sie in der  Konfigurations-Manager-Konsole zu \> **Anwendungsverwaltungspakete** der \> Softwarebibliothek, und wählen Sie dann Paket **erstellen aus.**

2.  Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:

    -   Name: **SRS v2 – Konfigurieren des SRS-Setuppakets**

    -   Hersteller: **Microsoft Corporation**

    -   Version: **1.0.0**

    -   Aktivieren Sie **das Kontrollkästchen** Dieses Paket enthält Quelldateien, geben Sie den Pfad zum Ordner **SRS v2 - Configure SRS Setup** ein, und wählen Sie dann **Weiter aus.**

3.  Wählen **Sie Kein Programm erstellen** und dann Weiter **aus.**

4.  Überprüfen Sie **die Seite Einstellungen bestätigen,** und wählen Sie dann Weiter **aus.**

5.  Wählen Sie **Schließen aus.**



## <a name="distribute-configuration-manager-packages"></a>Verteilen von Configuration Manager-Paketen

Alle Pakete müssen auf die Server verteilt werden, denen in der Configuration Manager-Hierarchie die Rolle des Verteilungspunkts zugewiesen wurde. Führen Sie die folgenden Anweisungen aus, um die Paketverteilung zu initiieren.

1.  Verteilen sie Softwarepakete.

    1.  Wechseln Sie in der  Konfigurations-Manager-Konsole zu \> **Anwendungsverwaltungspakete** für die \> **Softwarebibliothek.** Wählen Sie alle Softwarepakete aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen aus.**

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann Weiter **aus.**

    3.  Fügen Sie alle Verteilungspunktserver (oder Verteilerpunktgruppen, je nach Ihrer Configuration Manager-Hierarchie) zur Liste hinzu, und wählen Sie dann **Weiter aus.**

    4.  Wählen **Sie Weiter** und dann Schließen **aus.**

2.  Verteilen sie Treiberpakete.

    1.  Wechseln Sie in der Konfigurations-Manager-Konsole zu **Treiberpakete** für \> **Betriebssystempakete** der \> **Softwarebibliothek.** Wählen Sie alle Treiberpakete aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen aus.**

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann Weiter **aus.**

    3.  Fügen Sie alle Verteilungspunktserver (oder Verteilerpunktgruppen, je nach Ihrer Configuration Manager-Hierarchie) zur Liste hinzu, und wählen Sie dann **Weiter aus.**

    4.  Wählen **Sie Weiter** und dann Schließen **aus.**

3.  Verteilen von Betriebssystempaketen

    1.  Wechseln Sie in der Konfigurations-Manager-Konsole zu Betriebssystembilder der **Softwarebibliothek** \>  \> . Wählen Sie alle Betriebssystembilder aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen aus.**

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann Weiter **aus.**

    3.  Fügen Sie alle Verteilungspunktserver (oder Verteilerpunktgruppen, je nach Ihrer Configuration Manager-Hierarchie) zur Liste hinzu, und wählen Sie dann **Weiter aus.**

    4.  Wählen **Sie Weiter** und dann Schließen **aus.**

> [!NOTE]
> Die Paketverteilung kann je nach Paketgröße, Configuration Manager-Hierarchie, Anzahl der Verteilerpunktserver und in Ihrem Netzwerk verfügbare Bandbreite einige Zeit dauern.
> 
> Alle Pakete müssen verteilt werden, bevor Sie mit der Bereitstellung einer Paketeinheit Microsoft Teams-Räume können.
> 
> Sie können den Status Ihrer Paketverteilung in der Configuration Manager-Konsole überprüfen, indem Sie **zu Inhaltsstatus** der Überwachung \> **des Verteilungsstatus** \> **gehen.**

## <a name="configuration-manager-task-sequences"></a>Tasksequenzen im Konfigurations-Manager

Sie verwenden Tasksequenzen mit Configuration Manager, um die Schritte zum Bereitstellen eines Betriebssystemabbilds auf einem Zielcomputer zu automatisieren. Um eine Microsoft Teams-Räume-Einheit automatisch bereitstellen zu können, erstellen Sie eine Tasksequenz, die auf das Startbild verweist, das zum Starten des Zielcomputers Microsoft Teams-Räume verwendet wird, auf das Windows 10 Enterprise-Betriebssystemabbild, das Sie installieren möchten, sowie auf andere zusätzliche Inhalte wie andere Anwendungen oder Softwareupdates.

### <a name="import-the-sample-task-sequence"></a>Importieren der Beispiel-Aufgabensequenz

Sie können eine Beispiel-Aufgabensequenz herunterladen und problemlos importieren und an Ihre Anforderungen anpassen.

1.  [**Laden Sie**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) die Beispiel-Aufgabensequenz herunter, und kopieren Sie die heruntergeladene ZIP-Datei an einen freigegebenen Speicherort.
2.  Wechseln Sie in der Konfigurations-Manager-Konsole zu Tasksequenzen von Betriebssystemen der **Software-Bibliothek,** \>  \> und wählen Sie Dann **Tasksequenz importieren aus.**

3.  Wählen **Sie Durchsuchen** aus, wechseln Sie zum Speicherort des freigegebenen Ordners, den Sie in Schritt 1 verwendet haben, wählen Sie die Microsoft Teams-Räume-Bereitstellungsdatei **(EN-US)** .zipaus, und wählen Sie dann **Weiter aus.**

4.  Legen **Sie Aktion** auf Neu **erstellen**, und wählen Sie dann **Weiter aus.**

5.  Bestätigen Sie die Einstellungen, und wählen Sie dann **Weiter aus.**

6.  Wählen Sie **Schließen aus.**

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Überprüfen Sie, ob die Referenzpakete ordnungsgemäß mit den einzelnen Tasksequenzschritten verknüpft sind.

1. Wählen Sie die importierte Aufgabensequenz und dann Bearbeiten **aus.**

    Der Tasksequenz-Editor wird geöffnet und zeigt jede Schrittabfolge an, die Sie zum Bereitstellen und Konfigurieren einer Microsoft Teams-Räume müssen.

2. Führen Sie die einzelnen Schritte durch, und führen Sie die empfohlenen Updates aus:

   1. **Neustarten in Windows PE:** Dieser Schritt wird neu gestartet und startet den Computer dann in Windows PXE. Für diesen Schritt sind keine Änderungen erforderlich.

   2. **Partition Disk 0 – UEFI:** Mit diesem Schritt wird die Datenträgerkonfiguration zurückgesetzt und Partitionen basierend auf den konfigurierten Einstellungen erstellt. Wir empfehlen, dass Sie keine Änderungen an diesem Schritt vornehmen.

   3. **Festlegen des SRS-Computernamens:** Dieser Schritt enthält eine HTML-Anwendung zum Bereitstellen einer UI zum Festlegen eines Computernamens für die Microsoft Teams-Räume-Einheit während der Bereitstellung.
      -  Dies ist ein optionaler Schritt, der jedoch nur deaktiviert werden kann, wenn Sie die Computerbenennung über einen alternativen Prozess verwalten möchten.
      -  Vergewissern Sie sich, dass das **Paket SRS v2 – Set-SRSComputerName** ausgewählt ist. Falls nicht, navigieren Sie zu dem Paket, und wählen Sie es aus.

   4. **Betriebssystem anwenden:** Dieser Schritt gibt das Betriebssystemabbild an, das bereitgestellt werden soll, und die unbeaufsichtigte Sysprep-Antwortdatei, die verwendet werden soll.
      -  Vergewissern Sie sich, dass Windows 10 Enterprise richtige Betriebssystemabbilddatei ausgewählt ist.
      -  Vergewissern Sie sich, dass Die Option Unbeaufsichtigte Antwortdatei oder **Sysprep-Antwortdatei** für eine benutzerdefinierte Installation verwenden aktiviert ist und **das SRS v2 - Sysprep-Paket** ausgewählt ist. Stellen Sie außerdem sicher, **dass** Dateiname auf **unattend.xml** ist.

   5. **Anwenden Windows Einstellungen:** Dieser Schritt sammelt Informationen zur Windows Installation.
      -  Stellen Sie Lizenzierungs- und Registrierungsinformationen einschließlich Product Key, Kennwort für ein lokales Administratorkonto und Zeitzone (je nach Ihren Anforderungen) zur Verfügung.

   6. **Anwenden von Einstellungen:** In diesem Schritt können Sie eine Arbeitsgruppe oder einen Active Directory-Domänennamen und eine Organisationseinheit angeben.
      > [!NOTE]
      > Unter [Skype Überlegungen](domain-joining-considerations.md) zur Teilnahme an Raumsystemdomäne finden Sie empfohlene Aktionen, die Sie beim Bereitstellen von Microsoft Teams-Räume-Einheiten als Mitglieder einer Actve-Verzeichnisdomäne ausführen müssen.
   7. **Anwenden von Treibern:** Dieser Schritt und seine Unterschritte werden verwendet, um entsprechende Gerätetreiber und Firmware basierend auf Ihrem Surface Pro bereitstellen. Aktualisieren Sie jeden Schritt, um das relevante Treiberpaket anzugeben, das dieser Bereitstellung zugeordnet ist.
      -   Jedes Treiberpaket ist so konfiguriert, dass Windows Management Instrumentation (WMI)-Filter verwendet werden, um relevante Treiber und Firmware basierend auf der Surface Pro und dem Modell bereitstellen zu können.
      -   Es wird dringend empfohlen, die Konfiguration dieser Treiber nicht zu ändern, da die Bereitstellung sonst fehlschlagen könnte.

   8. **Einrichten Windows und Konfigurations-Manager:** Mit diesem Schritt wird der Configuration Manager-Client bereitgestellt und konfiguriert. Aktualisieren Sie diesen Schritt, um das integrierte Configuration Manager-Clientpaket anzugeben.

   9. **Stammzertifikat installieren:** Dieser Schritt verteilt das Stammzertifikat für Geräte, die nicht der Domäne beigetreten sind, und ist daher optional und standardmäßig deaktiviert.
      -   Aktivieren Sie diesen Schritt, wenn Sie ein Stammzertifikat in den Stammeinheiten Microsoft Teams-Räume müssen.
      -   Wenn Sie diesen Schritt ausführen müssen, vergewissern Sie sich, dass **srS v2 –** Stammzertifikatpaket und **64-Bit-Dateisystemumleitung** deaktivieren ausgewählt sind.

   10. **Installieren und Konfigurieren des Überwachungs-Agents:** Mit diesem Schritt wird die 64-Bit-Version des Microsoft Azure Monitor-Agents installiert und der Agent für die Verbindung mit Ihrem Log Analytics-Arbeitsbereich konfiguriert.
       -   Dieser Schritt ist standardmäßig deaktiviert. Aktivieren Sie diesen Schritt nur, wenn Sie den Überwachungs-Agent verwenden möchten, um den Status Ihrer Microsoft Teams-Räume überwachen.
       -   Bearbeiten Sie diesen Schritt, und aktualisieren Sie die Befehlszeilenparameter, um Ihre **Arbeitsbereichs-ID und** den **Arbeitsbereichsschlüssel anzugeben.**
       -   Weitere Informationen zum Beziehen der Arbeitsbereichs-ID der Operations Management Suite und des Primärschlüssels finden Sie unter Konfigurieren von Testgeräten für [Azure Monitoring.](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring)
       -   Vergewissern Sie sich, **dass die SRS v2 Microsoft Monitoring Agent Package** und Disable **64-Bit-Dateisystemumleitung** ausgewählt sind.
       -   Weitere Informationen zum Überwachen des Status Ihrer Microsoft Teams-Räume-Bereitstellung finden Sie unter Planen der Microsoft Teams-Räume-Verwaltung mit [Azure Monitor](azure-monitor-plan.md), Bereitstellen der Microsoft Teams-Räume-Verwaltung mit [Azure Monitor](azure-monitor-deploy.md) und Verwalten von Microsoft Teams-Räume-Geräten mit Azure [Monitor.](azure-monitor-manage.md)

   11. **Kopieren von SRS v2-Konfigurationsdateien:** Mit diesem Schritt werden die erforderlichen Setup- und Konfigurationsdateien aus dem Microsoft Teams-Räume-Bereitstellungskit auf die lokale Festplatte kopiert. Für diesen Schritt ist keine Anpassung erforderlich.
       -   Vergewissern Sie sich, **dass die Anwendungen SRS v2 – SRS-Anwendungspaket** und **64-Bit-Umleitung des 64-Bit-Dateisystems** deaktivieren ausgewählt sind.

   12. **Install-SRSv2-OS-Updates:** Mit diesem Schritt werden alle erforderlichen Betriebssystemupdates bereitgestellt, die für die Bereitstellung Microsoft Teams-Räume sind. Gehen Sie folgendermaßen vor:
       -   Aktivieren [Sie Konfigurieren Microsoft Teams-Räume,](console.md) um zu sehen, welche Updates erforderlich sind.
       -   Stellen Sie sicher, **dass Ihr SRS v2 – Os Updates-Paket** alle erforderlichen Updates enthält.
       -   Vergewissern Sie sich, **dass srS v2 – Os Updates Package** ausgewählt ist.
       -   Vergewissern Sie sich, dass die PowerShell-Ausführungsrichtlinie auf Umgehen **festgelegt ist.**

   13. **Computer neu** starten: Mit diesem Schritt wird der Computer nach der Installation der obligatorischen Betriebssystemupdates neu gestartet. Für diesen Schritt ist keine Anpassung erforderlich.

   14. **Konfigurieren Windows** Komponenten: In diesem Schritt werden die erforderlichen Features Windows konfiguriert. Für diesen Schritt ist keine Anpassung erforderlich.

   15. **Computer neu** starten: Mit diesem Schritt wird der Computer neu gestartet, Windows die Features der Windows-Installation konfiguriert sind. Für diesen Schritt ist keine Anpassung erforderlich.

   16. **Lokale Skype** hinzufügen: Mit diesem Schritt wird das lokale Skype-Konto erstellt, das zum automatischen Anmelden bei Windows und Starten der Anwendung Microsoft Teams-Räume wird. Diesem Schritt ist kein Softwarepaket zugeordnet, und es ist keine Anpassung erforderlich.

   17. **Einrichten und Konfigurieren der SRS-Anwendung:** Mit diesem Schritt wird Microsoft Teams-Räume Installation der Anwendung für den nächsten Start des Betriebssystems konfiguriert.
       -   Vergewissern Sie sich, **dass srS v2 – SRS-Setuppaket** konfigurieren und **64-Bit-Umleitung des 64-Bit-Dateisystems** deaktivieren ausgewählt sind.

> [!IMPORTANT]
> Es ist sehr wichtig, dass die Aufgabenabfolgeschritte in der angegebenen Reihenfolge angegeben werden. Wenn Sie die Reihenfolge der Schritte ändern oder zusätzliche Schritte konfigurieren, kann dies die Bereitstellung unter Umständen nicht mehr in Ordnung machen.
>
> **Das Einrichten und Konfigurieren von SRS-Anwendungsschritten** muss der letzte Schritt in der Tasksequenz sein, andernfalls tritt bei der Bereitstellung möglicherweise ein Fehler auf.

### <a name="create-deployment-for-the-task-sequence"></a>Erstellen einer Bereitstellung für die Tasksequenz

1. Wählen Sie die Tasksequenz und dann Bereitstellen **aus.**

2. Wählen Sie **Durchsuchen** aus, um die Zielsammlung für die Bereitstellung auszuwählen.

3. Wählen **Sie Alle unbekannten Computer** und dann OK **aus.**

4. Wählen Sie **Weiter aus.**

5. Wählen **Sie in** der **Dropdownliste Zweck** die Option Verfügbar aus.

6. Wählen Sie in der Liste Für die folgende Liste verfügbar **machen** die Option Nur Medien und **PXE** und dann Weiter **aus.**
   > [!WARNING]
   > Es ist sehr wichtig, **dass Purpose** auf Verfügbar **festgelegt ist.** Stellen Sie sicher, dass **für Zweck** **NICHT** der Erforderliche festgelegt **ist.** Stellen Sie außerdem sicher, dass Sie unter Verfügbar machen für den folgenden die Option Nur Medien und **PXE** **auswählen.**
   >
   > Wenn Sie diese Werte auf etwas anderes festlegen, erhalten möglicherweise alle Computer das Microsoft Teams-Räume Bereitstellungsabbild, wenn sie gestartet werden.
7. Geben Sie keinen Zeitplan an, und wählen Sie **Weiter aus.**

8. Ändern Sie nichts  im Abschnitt "Benutzerfreundlichkeit", und wählen Sie Weiter **aus.**

9. Ändern Sie nichts  im Abschnitt Benachrichtigungen, und wählen Sie **Weiter aus.**

10. Ändern Sie nichts im Abschnitt **Verteilungspunkte,** und wählen Sie **Weiter aus.**

11. Bestätigen Sie die Einstellungen, und wählen Sie dann **Weiter aus.**

12. Wählen Sie **Schließen aus.**

**Überprüfen der Lösung und Behandeln von Problemen**

Nachdem Sie die Microsoft Endpoint Configuration Manager-Aufgabenabfolgen abgeschlossen haben, müssen Sie einen Testlauf ausführen, um zu überprüfen, ob die Tasksequenz ihre Einheiten bereitstellen und Microsoft Teams-Räume konfigurieren kann.

1.  Verbinden Testgerät mit dem verkabelten Netzwerk verbinden, indem Sie einen der unterstützten Ethernet-Adapter oder die Surface-Docking-Station verwenden. Wenn die PXE-Startfunktionen für Ihre Umgebung nicht konfiguriert wurden, können Sie [](/configmgr/osd/deploy-use/create-bootable-media) das zuvor erstellte Startabbild auf dem USB-Flashlaufwerk verwenden, um über USB zu starten und eine Verbindung mit Configuration Manager herzustellen.

2.  Greifen Sie auf die Firmware zu, und starten Sie den PXE-Start:

    1.  Stellen Sie sicher, dass das Surface-Gerät ausgeschaltet ist.

    2.  Halten Sie die Schaltfläche **Lautstärke erhöhen** gedrückt.

    3.  Drücken Sie die **Ein/Aus-Taste, und** lassen Sie sie los.

    4.  Lassen Sie die Taste "Lautstärke erhöhen" los, nachdem das **Gerät** gestartet wurde.

    5.  Wählen Sie **Startkonfiguration aus.**

    6.  Führen Sie einen der folgenden Schritte aus:

        -   Wählen **Sie PXE-Start** aus, und ziehen Sie ihn an den Oberen Rand der Liste. Alternativ können Sie auf dem Netzwerkadapter nach links wischen, um das Gerät sofort zu starten. Dies wirkt sich nicht auf die Startreihenfolge aus.
        -   Wählen Sie das USB-Speicherlaufwerk mit den Startmedien aus.

3.  Wählen **Sie Beenden** und dann Jetzt neu starten **aus.**

4.  Wenn Sie dazu aufgefordert werden, wählen **Sie Die EINGABETASTE** für den Netzwerkstartdienst aus.

5.  Windows PE wird in den Arbeitsspeicher geladen, und der Tasksequenz-Assistent wird gestartet. Wählen Sie **Weiter aus,** um fortzufahren.

6.  Wählen Sie die zuvor importierte Vorgangsreihenfolge aus, und wählen Sie dann Weiter **aus.**

7.  Nachdem die Datenträgerkonfiguration angewendet wurde, werden Sie aufgefordert, einen Computernamen für das Gerät anzugeben. Auf der Benutzeroberfläche wird ein empfohlener Computername basierend auf der Seriennummer des Surface Pro angezeigt. Sie können entweder den vorgeschlagenen Namen übernehmen oder einen neuen Namen angeben. Folgen Sie den Anweisungen auf dem Bildschirm für die Namenszuweisung des Computers. Wenn Sie Annehmen **auswählen,** beginnt die Bereitstellung.

8.  Der restliche Bereitstellungsprozess erfolgt automatisch und fordert keine weiteren Benutzereingaben an.

9.  Nachdem die Konfiguration des Geräts mit der Tasksequenz der Bereitstellung abgeschlossen ist, wird der folgende Konfigurationsbildschirm angezeigt, in dem Sie zum Konfigurieren der Einstellungen Microsoft Teams-Räume werden.

    ![Bildschirm für die Ersteinrichtung Microsoft Teams-Räume Anwendung.](../media/room-systems-scale-image2.png)

10.  Schließen Sie die Surface Pro an die Microsoft Teams-Räume an, und konfigurieren Sie die Anwendungseinstellungen.

11.  Überprüfen Sie, ob die in der Microsoft Teams-Räume [aufgeführten](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) Funktionen auf dem bereitgestellten Gerät funktionieren.


Um Probleme bei einer fehlgeschlagenen Installation zu beheben, überprüfen Sie die **Datei SMSTS.log,** in der alle Schritte protokolliert werden, die in einer Konfigurations-Manager-Tasksequenz ausgeführt wurden.

Die Datei SMSTS.log wird je nach Phase des Erstellungsprozesses in einem von mehreren Pfaden gespeichert. Überprüfen Sie die folgende Tabelle, um den Pfad zur Datei SMSTS.log zu identifizieren.


| **Bereitstellungsphase**                                                            | **Task sequence log path**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE vor HDD-Format                                                        | X: \\ Windows \\ Temp \\ smstslog \\ smsts.log             |
| WinPE nach HDD-Format                                                         | C: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log    |
| Bereitgestelltes Betriebssystem vor der Installation des Configuration Manager-Agents | c: \\ _SMSTaskSequence \\ Logs \\ Smstslog \\ smsts.log    |
| Betriebssystem und bereitgestellter Configuration Manager-Agent                   | %windir% \\ System32 \\ ccm \\ logs \\ Smstslog \\ smsts.log |
| Ausführung der Tasksequenz abgeschlossen                                                | %windir% \\ System32 \\ ccm \\ logs \\ smsts.log           |

> [!TIP]
> Sie können **während der Tasksequenz** jederzeit F8 auswählen, um eine Befehlskonsole zu öffnen, und dann Zugriff auf die Datei SMSTS.log erhalten.

Zur Behebung von PXE-Startproblemen überprüfen Sie die beiden für PXE-Aktionen spezifischen Protokolldateien auf dem Konfigurations-Manager-Server:

-   **Pxecontrol.log**, befindet sich im Verzeichnis mit den Configuration Manager-Installationsprotokollen

-   **Smspxe.log**, befindet sich im Verzeichnis mit den MP-Protokollen (Configuration Manager Management Point)

Eine vollständige Liste der Protokolldateien, die Sie zur weiteren Problembehandlung ihrer Configuration Manager-Installation verwenden können, finden Sie in der Referenz Microsoft Endpoint Configuration Manager [Protokolldatei](/configmgr/core/plan-design/hierarchy/log-files).
