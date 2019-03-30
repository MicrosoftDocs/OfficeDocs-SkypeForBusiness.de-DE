---
title: Bereitstellen von Microsoft-Teams Chatrooms mithilfe von System Center Configuration Manager
author: jambirk
ms.author: jambirk
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: Lesen Sie dieses Thema zu erfahren Sie mehr über die Bereitstellung von Microsoft-Teams Räume unter umfangreiche Bereitstellungen.
ms.openlocfilehash: fe6ffee0c6ab86496204ab4e17b86cc84a70a2a7
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013036"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a>Bereitstellen von Microsoft-Teams Chatrooms mithilfe von System Center Configuration Manager

In diesem Artikel erhalten Sie alle erforderliche Informationen zur Bereitstellung Ihrer Microsoft Teams Chatrooms erstellen mithilfe von System Center Configuration Manager.

Mit den Methoden leicht zu bedienende zur Verfügung gestellt von System Center Configuration Manager können Sie das Betriebssystem und andere Anwendungen für mehrere Geräte bereitstellen.

Verwenden Sie den unten dargestellten, durch die Konfiguration der Konfigurations-Manager, leiten Ansatz, und passen Sie die Beispielpaketen und der Bedarf für Ihre Organisation in dieser Anleitung bereitgestellten Skripts.

![Microsoft-Teams Chatrooms Bereitstellungsprozess von Configuration Manager](../../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Diese Lösung wurde mit Surface Pro basierenden Bereitstellungen nur getestet. Folgen Sie den Hersteller Richtlinien für Konfigurationen, die nicht auf Surface Pro basieren.

## <a name="validate-prerequisites"></a>Überprüfen Sie die Komponenten

Um Microsoft Teams Chatrooms mit Configuration Manager bereitstellen, stellen Sie sicher, dass die folgenden Voraussetzungen und Anforderungen erfüllt.

### <a name="system-center-configuration-manager-requirements"></a>System Center Configuration Manager-Anforderungen

-   System Center Configuration Manager Version muss mindestens 1706 oder höher. Es wird empfohlen, 1710 oder höher verwenden. Checken Sie [Unterstützung für Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) , um Informationen zu den Windows-10-Versionen zu erhalten, der Konfigurations-Manager unterstützt.

-   Eine unterstützte Version von Windows Assessment and Deployment Kit (ADK) für Windows 10 muss installiert sein. Finden Sie unter den Versionen von [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) , die Sie mit verschiedenen Versionen von Configuration Manager verwenden können, und stellen Sie sicher, dass Ihre Bereitstellung die richtige Version umfasst.

-   Die Servern des Systems müssen zugewiesen wurden die Verteilung Point-Rolle, und die Startabbilder beim für So aktivieren Sie Netzwerk initiierte Bereitstellungen [vor dem Start Unterstützung des PXE-Umgebung ()](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) aktiviert werden soll. Wenn PXE-Unterstützung nicht aktiviert ist, können Sie für die Bereitstellung [startbaren Medium](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) .

-   Ein Netzwerk für den Inhaltszugriff muss zur Unterstützung der neuen Computer (bare-Metal) Bereitstellungsszenarien konfiguriert werden. Mehr über die Konfiguration des ein Netzwerk für den Inhaltszugriff finden Sie unter [Verwalten von Konten Zugriff auf die Inhalte in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   Wir empfehlen, dass Sie [multicast-Support](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network), aktivieren, wenn Sie wahrscheinlich dasselbe Microsoft-Teams Chatrooms Bild für mehrere Einheiten zur selben Zeit bereitstellen werden.

### <a name="networking-requirements"></a>Netzwerkanforderungen

-   Ihr Netzwerk sollte einen Dynamic Host Configuration Protocol (DHCP)-Server, für die automatische Verteilung von IP-Adresse an die Subnetze, auf dem Microsoft-Teams Chatrooms Einheiten bereitgestellt wird, konfiguriert haben.

    > [!NOTE]
    > Die DHCP-Lease muss auf einen anderen Wert länger als die Dauer der Bild-Bereitstellung festgelegt werden. Andernfalls kann die Bereitstellung fehlschlagen.

-   Im Netzwerk, einschließlich Switches und virtuelle LANs (VLANs), sollte so konfiguriert werden, dass PXE unterstützen. Hersteller Ihres für Weitere Informationen zur Konfiguration von IP-Hilfsprogramm und PXE finden Sie unter. Alternativ können Sie [startbaren Medien](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) für die Bereitstellung verwenden, wenn PXE-Unterstützung nicht aktiviert ist.

    > [!NOTE]
    > Für Surface Pro werden Geräte, über das Netzwerk (PXE-Start) starten nur unterstützt, wenn Sie einen Ethernet-Adapter oder Dockingstation von Microsoft verwenden. Drittanbieter-Ethernet-Adapter unterstützen nicht PXE-Start mit Surface Pro. Weitere Informationen finden Sie unter [Ethernet-Adapter und Fläche Bereitstellung](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a>Konfigurieren von System Center Configuration Manager für die Bereitstellung eines Betriebssystems

In diesem Artikel wird vorausgesetzt, Sie bereits ist eine fehlerfreie Bereitstellung von System Center Configuration Manager, und nicht Detail alle die erforderlichen Schritte zum Bereitstellen und Konfigurieren von Configuration Manager von Grund auf neu. Die [Dokumentation und die Konfiguration Anleitung](https://docs.microsoft.com/sccm/) für System Center Configuration Manager ist eine hervorragende Ressource. Es wird empfohlen, dass Sie mit diesen Ressourcen starten, wenn Sie noch Konfigurations-Manager bereitgestellt haben.

Gehen Sie folgendermaßen vor, um sicherzustellen, dass das Betriebssystem Bereitstellungsfeatures (OSD) ordnungsgemäß konfiguriert sind.

### <a name="validate-and-upgrade-configuration-manager"></a>Überprüfen und Aktualisieren von Configuration Manager

1.  Navigieren Sie in der Configuration Manager-Konsole zu **Administration** \> **Updates und Wartung**.

2.  Überprüfen der installierten Build und die anwendbaren Aktualisierungen, die noch nicht installiert wurden haben.

3.  Überprüfen Sie die [Unterstützung für Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client); Wenn Sie die Bereitstellung aktualisieren müssen, wählen Sie das Update installieren möchten, und wählen Sie dann **herunterladen**.

4.  Nachdem der Download abgeschlossen ist, wählen Sie das Update, und wählen Sie dann **Update Pack installieren**.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Konfigurieren von Verteilungspunkte PXE und Multicast-Unterstützung

1.  Navigieren Sie in der Configuration Manager-Konsole zu **Administration** \> **Verteilungspunkte**.

2.  Wählen Sie den Verteilung Point Server, der die Bereitstellung von Microsoft-Teams Räume dienen, und wählen Sie dann **Eigenschaften**aus.

3.  Wählen Sie die **PXE** -Registerkarte, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:
    -   Aktivieren der PXE-Unterstützung für clients
    -   Zulassen Sie dieser Verteilungspunkt auf eingehende PXE-Anfragen reagieren
    -   Aktivieren der Unterstützung von unbekannten computer

4.  *Optional:* Um multicast-Support zu aktivieren, wählen Sie die **Multicast** -Registerkarte, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:
    -   Aktivieren Sie Multicast zum Senden von Daten für mehrere Clients gleichzeitig
    -   Konfigurieren Sie den UDP-Port-Bereich gemäß den Anweisungen in Ihr Netzwerkteam Empfehlung

### <a name="configure-the-network-access-account"></a>Konfigurieren Sie das Netzwerk für den Inhaltszugriff

1.  Navigieren Sie in der Configuration Manager-Konsole zu **Administration** \> **Standortkonfiguration** \> **Websites**, und wählen Sie dann die Website.

2.  Wählen Sie in der Gruppe **Einstellungen** **Konfigurieren Websitekomponenten** \> **Software Distribution**.

3.  Wählen Sie die Registerkarte **Netzwerk für den Inhaltszugriff** festlegen, eine oder mehrere Konten, und wählen Sie dann **OK**aus.

> [!NOTE]
> Die Konten benötigen keine spezielle Rechte, mit Ausnahme der **auf diesen Computer über das Netzwerk** direkt auf dem Verteilergruppen Point-Server. Eine generische Domänenbenutzerkonto wird geeignet. Weitere Informationen finden Sie unter [Verwalten von Konten Zugriff auf die Inhalte in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Konfigurieren einer Boot-Bild

1.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssystem** \> **Boot Bilder**.

2.  Wählen Sie **Start-Image (x64)**, und wählen Sie dann **Eigenschaften**aus.

3.  Wählen Sie die Registerkarte **Datenquelle** aus, und aktivieren Sie **diese Boot-Abbild vom PXE-fähige Verteilungspunkt bereitstellen**.

4.  Wählen Sie die **Optionalen Komponenten** -Registerkarte, um die erforderlichen Komponenten zu installieren:

    1.  Wählen Sie Stern-Symbol, und suchen Sie nach **HTML (Windows PE-HTA)**

    2.  Wählen Sie **OK** , um die Unterstützung von HTML in dem Boot-Abbild hinzufügen aus.

5.  *Optional:* Zum Anpassen der Bereitstellung, wählen Sie die Registerkarte **Anpassung** .
    -   Aktivieren Sie **Befehl unterstützen (nur zu Testzwecken)** aus, wenn Sie während der Bereitstellung in einem Eingabeaufforderungsfenster zugreifen möchten. Wenn diese Option aktiviert ist, können Sie ein Eingabeaufforderungsfenster, indem Sie **F8** auswählen, können Sie jederzeit während der Bereitstellung starten.
    -   Sie können auch ein benutzerdefiniertes Hintergrundbild während der Bereitstellung anzuzeigende angeben. Aktivieren, um ein Bild festzulegen, **Geben Sie die benutzerdefinierten Hintergrund Image-Datei (UNC-Pfad** , und wählen Sie den Hintergrund.

6.  Wenn Sie aufgefordert werden, wählen Sie **Ja** aus, und verteilen Sie das aktualisierte Boot Image an Ihre Verteilungspunkte.

Weitere Informationen finden Sie unter [Manage Boot Bilder mit System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).

> [!NOTE]
> Sie können ein startbares USB-Medium um Konfigurations-Manager Task Sequence-basierten Bereitstellungen für Umgebungen zu initiieren, die keine PXE-Unterstützung verfügen erstellen. Das startbare Medium enthält nur Boot Image, optionale prestart Befehle und ihre erforderlichen Dateien und Binärdateien Konfigurations-Manager zur Unterstützung der mit Windows PE starten und eine Verbindung zu den Konfigurations-Manager für den Rest des Bereitstellungsprozesses. Weitere Informationen finden Sie unter [Erstellen eines startbaren Medium](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia).

## <a name="create-configuration-manager-packages"></a>Konfigurations-Manager-Pakete erstellen

Konfigurations-Manager erfordert eine Reihe von Paketen zum Bereitstellen und konfigurieren die Microsoft-Teams Chatrooms Einheiten.

Sie benötigen zum Erstellen und konfigurieren die folgenden Pakete, und klicken Sie dann den Konfigurations-Manager-Website-Systemen, die die Verteilung Point-Serverrolle zugewiesen wurden verteilen.

| **Paketname**                     | **Typ**               | **Beschreibung**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2 - Anwendungspaket SRS     | Softwarepaket       | Paket für das Microsoft-Teams Chatrooms Deployment kit                                      |
| SRS v2 - Sysprep-Paket             | Softwarepaket       | Paket für die benutzerdefinierte Unattended.xml Microsoft Teams Chatrooms Einheiten konfigurieren            |
| SRS v2 - Set-SRSComputerName-Paket | Softwarepaket       | Paket für die HTML-Anwendung (HTA) zuweisen einen Computernamen während der Bereitstellung    |
| SRS v2 - SRS Setup konfigurieren         | Softwarepaket       | Konfigurieren der Bereitstellung der Microsoft-Teams Chatrooms app-Paket                          |
| SRS v2 - aktualisiert OS Paket          | Softwarepaket       | Paket zum Bereitstellen von Updates obligatorisch Betriebssystem                                      |
| SRS v2 - Root Certificate-Paket    | Softwarepaket       | Optional - Pakets zum Bereitstellen von des Stammzertifikats (nicht für die Domäne eingebundener Einheiten erforderlich)  |
| SRS v2 - Microsoft Agent-Paket Monitoring | Softwarepaket       | Optional - Pakets zum Bereitstellen und Konfigurieren des Microsoft Operations Management Suite-Agents|
| SRS v2 - Paket mit Windows PE Hintergrund    | Softwarepaket       | Paket für das benutzerdefinierte Hintergrundbild zur Verwendung mit Boot-Bilder                           |
| Windows 10 Enterprise                | Betriebssystemabbilds | Paket für das Betriebssystem-Installationsdatei (install.wim)                          |
| Surface Pro                          | Treiberpakets         | Paket für das Gerätetreiber und Firmware für Microsoft Surface Pro                     |
| Surface Pro 4                        | Treiberpakets         | Paket für das Gerätetreiber und Firmware für Microsoft Surface Pro 4                   |

Weitere Informationen finden Sie unter [Pakete und Programme in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Erstellen Sie die Ordner für das Paket Quelldateien

Konfigurations-Manager erfordert die Quelldateien des Pakets in einer bestimmten Ordnerstruktur organisiert werden, wenn sie zuerst erstellt werden und wenn sie aktualisiert werden.

Erstellen Sie die folgende Ordnerstruktur, die Zentraladministrationswebsite für System Center Configuration Manager oder primärer oder auf eine Serverfreigabe Host Paket Quelldateien verwendeten:

-   SRS v2 - Microsoft Agent-Paket Monitoring
-   SRS v2 - aktualisiert OS Paket
-   SRS v2 - Root Certificate-Paket
-   SRS v2 - Set-SRSComputerName-Paket
-   SRS v2 - Anwendungspaket SRS
-   SRS v2 - SRS Setup konfigurieren
-   SRS v2 - Sysprep-Paket
-   Treiber
    -   Surface Pro
    -   Surface Pro 4
-   Betriebssysteme
    -   Windows 10 Enterprise

> [!TIP]
> Sie können auch [herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) und verwenden die Zipdatei, die enthält die Ordnerstruktur für die Pakete, die Skripts, die Sie verwenden müssen, und der Task Sequence Vorlage, die Sie importieren möchten.

### <a name="create-the-monitoring-agent-package"></a>Erstellen Sie das Monitoring-Agent-Paket

1. Laden Sie den Agent Überwachung von <https://go.microsoft.com/fwlink/?LinkId=828603>.

2. Extrahieren Sie das Paket in den Ordner **SRS v2 - Agent-Monitoring-Paket Microsoft** , indem Sie ein Eingabeaufforderungsfenster öffnen und **MMASetup-AMD64.exe/c:** an der Befehlszeile.

3. Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.

4. Geben Sie die folgenden Informationen, um das Paket zu erstellen:

   - Namen<strong>: SRS v2 - Monitoring-Agent-Paket Microsoft</strong>

   - Hersteller<strong>: Microsoft Corporation</strong>

   - Version<strong>: 8.1.11081.0</strong> (Geben Sie die Version der der heruntergeladenen Installationsdatei)

   - Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 - Agent-Monitoring-Paket Microsoft** , und wählen Sie dann auf **Weiter**.

5. **Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.

6. Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.

7. Wählen Sie **Schließen**aus.

### <a name="create-the-operating-system-updates-package"></a>Erstellen Sie das Betriebssystem Updates-Paket

1. In den Ordner **SRS v2 - Paket mit Updates OS** Erstellen eines neuen PowerShell-Skripts, die mit dem Namen **Install-SRSv2-OS-Updates.ps1**.

2. Kopieren Sie das folgende Skript in das Skript für **Install-SRSv2-OS-Updates.ps1** . Alternativ können Sie das Skript für Install-SRSv2-OS-Updates.ps1 [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.
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
3. Laden Sie die obligatorische Windows Update-Pakete in den gleichen Ordner.
   > [!NOTE]
   > Zum Zeitpunkt der Veröffentlichung des Artikels, war nur [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) erforderlich. Überprüfen Sie [Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md), um festzustellen, ob andere Updates erforderlich sind.

4. Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.

5. Geben Sie die folgenden Informationen, um das Paket zu erstellen:
   -   Name: **SRS v2 – OS Paket aktualisiert**
   -   Hersteller: **Microsoft Corporation**
   -   Version: **1.0.0**
   -   Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 - Paket mit OS Updates** , und wählen Sie dann auf **Weiter**.

6. **Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.

7. Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.

8. Wählen Sie **Schließen**aus.

### <a name="create-the-root-certificate-package-optional"></a>Erstellen Sie das Stamm-Zertifikat-Paket (optional)

Sie erstellen diese Package, um das Stammzertifikat für Geräte verteilen, die mit einer Active Directory-Domäne verknüpft werden, werden nicht aus. Erstellen Sie dieses Paket nur, wenn beide die folgenden Bedingungen gelten:
-   Ihre Bereitstellung umfasst lokalen Lync oder Skype für Business Server.
-   Microsoft-Teams Chatrooms Einheiten werden für die Verwendung in einer Arbeitsgruppe statt Mitglied einer Domäne konfiguriert.

1.  Kopieren Sie das Stammzertifikat, in den Ordner **SRS v2 – Root Certificate-Paket** .

2.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.

3.  Geben Sie die folgenden Informationen, um das Paket zu erstellen:
    -   Name: **SRS v2 – Root Certificate-Paket**
    -   Hersteller: *der Name Ihrer Organisation*
    -   Version: **1.0.0**
    -   Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 – Root Certificate-Paket** , und wählen Sie dann auf **Weiter**.

4.  **Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.

5.  Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.

6.  Wählen Sie **Schließen**aus.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Das Microsoft-Teams Chatrooms Kit Bereitstellungspaket erstellen

1.  Herunterladen der neuesten Version des **Microsoft-Teams Chatrooms Deployment Kit** von <https://go.microsoft.com/fwlink/?linkid=851168>, und installieren Sie es auf einer Arbeitsstation.

2.  Kopieren Sie den Inhalt von **C:\\Program Files (x86)\\Skype Raum System Deployment Kit** in den Ordner **SRS v2 - SRS Anwendungspaket** .

3.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.

4.  Geben Sie die folgenden Informationen, um das Paket zu erstellen:
    -   Name: **SRS v2 – SRS Anwendungspaket**
    -   Hersteller: **Microsoft Corporation**
    -   Version: **3.1.104.0** (Geben Sie die Version der der heruntergeladenen Installationsdatei)
    -   Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 – SRS Anwendungspaket** , und wählen Sie dann auf **Weiter**.
5.  **Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.

6.  Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.

7.  Wählen Sie **Schließen**aus.

### <a name="create-the-computer-name-assignment-package"></a>Erstellen Sie das Computer Namen Assignment-Paket

1.  Erstellen Sie eine neue HTML-Anwendung mit dem Namen **Set-SRSComputerName.hta** in den Ordner **SRS v2 - Set-SRSComputerName-Paket** .

2.  Kopieren Sie das folgende Skript in die **Set-SRSComputerName.hta** -Datei. Alternativ können Sie die Set-SRSComputerName.hta Datei [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.
    ```
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
3.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.

4.  Geben Sie die folgenden Informationen, um das Paket zu erstellen:

    -   Name: **SRS v2 - Set-SRSComputerName-Paket**

    -   Hersteller: **Microsoft Corporation**

    -   Version: **1.0.0**

    -   Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 - Set-SRSComputerName-Paket** , und wählen Sie dann auf **Weiter**.

5.  **Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.

6.  Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.

7.  Wählen Sie **Schließen**aus.

### <a name="create-the-sysprep-package"></a>Erstellen Sie das Sysprep-Paket

1. Erstellen Sie eine neue XML-Datei namens **Unattend.xml** in den Ordner **SRS v2 – Sysprep-Paket** .

2. Kopieren Sie den folgenden Text in der Datei **Unattend.xml** . Alternativ können Sie die Datei Unattend.xml [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)heruntergeladen werden.
   ```
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
3. Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.

4. Geben Sie die folgenden Informationen, um das Paket zu erstellen:
   -   Name: **SRS v2 - Sysprep-Paket**
   -   Hersteller: **Microsoft Corporation**
   -   Version: **1.0.0**
   -   Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 – Sysprep-Paket** , und wählen Sie dann auf **Weiter**.
5. **Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.

6. Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.

7. Wählen Sie **Schließen**aus.

### <a name="create-the-windows-10-enterprise-package"></a>Erstellen Sie das Windows-10-Enterprise-Paket

1.  Erhalten Sie eine Windows 10 Enterprise X64 Media, und kopieren Sie die Datei **install.wim** , um die **Betriebssysteme\\Windows 10 Enterprise** Ordner.

2.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **Betriebssystemabbilder**, und wählen Sie dann **Operating System Image hinzufügen**.

3.  Geben Sie den Pfad zu der **install.wim** -Datei, die Sie gerade kopiert haben, und wählen Sie dann auf **Weiter**.

4.  Aktualisieren Sie das Feld **Version** die Buildnummer des Bilds Windows 10 Enterprise entsprechend, und wählen Sie dann auf **Weiter**.

5.  Überprüfen Sie die Seite **Details** , und wählen Sie dann auf **Weiter**.

6.  Wählen Sie **Schließen**aus.

Weitere Informationen finden Sie unter [Manage Betriebssystem Bilder mit System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Erstellen Sie Surface Pro Gerät Treiberpakete.

Microsoft-Teams Chatrooms wird für Surface Pro und Surface Pro 4 unterstützt. Sie müssen ein Paket für jedes Surface Pro Modell zu erstellen, die Ihnen in Ihrer Umgebung.

> [!IMPORTANT]
> Die Treiber müssen mit der Windows-10-Enterprise-Build und die Microsoft-Teams Chatrooms Deployment Kit Version kompatibel sein. Weitere Informationen finden Sie unter [Laden Sie die neueste Firmware und Treiber für Fläche Geräte](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) und [Konfigurieren einer Konsole](console.md).

1.  Laden Sie die aktuellsten Treiber und Firmware.
    -   Für Surface Pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Für Surface Pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extrahieren Sie die heruntergeladene Treiber und Firmware. Öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie an der Befehlszeile einen der folgenden Befehle:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **-Treiber**, und wählen Sie dann **Import-Treiber**.

4.  Wählen Sie **alle Treiber in den folgenden Netzwerkpfad (UNC) zu importieren**, wählen Sie den Quellordner (z. B. C:\\_Sources\\Treiber\\Surface Pro), und wählen Sie dann auf **Weiter**.

5.  Klicken Sie auf der Seite **Geben Sie die Details für die importierten Treiber** wählen Sie alle aufgelisteten Treiber, und wählen Sie dann **diese Treiber aktivieren und ermöglichen Computern installieren**.

6.  Wählen Sie **Kategorien**, Erstellen einer neuen Kategorie, die einzelnen Details des Modells Fläche entspricht, wählen Sie **OK**aus, und wählen Sie dann auf **Weiter**.

7.  Wählen Sie **Neues Paket**aus.

8.  Geben Sie den Paketnamen an, der mit das Surface Pro Modell übereinstimmt, geben Sie einen Pfad zum Speichern von Paketdateien Treiber im, wählen Sie **OK**aus, und wählen Sie dann auf **Weiter**.

9.  Auf der Seite **Boot Bilder** stellen Sie sicher, dass keine Bilder Boot ausgewählt sind, und wählen Sie dann auf **Weiter**.

10. Wählen Sie **Schließen**aus.

11. Wechseln Sie zu **Software Library** \> **Betriebssysteme** \> - **Treiber**wählen **Ordner \> Ordner erstellen**, und geben Sie einen Ordnernamen, die einzelnen Details des Modells Surface Pro gesucht, die Sie gerade die Treiber für importiert.

12. Verschieben Sie alle importierten Treiber in den neu erstellten Ordner für einfachere Navigation und Vorgang.

> [!NOTE]
> Wiederholen Sie die gleichen Schritte für andere Surface Pro Modelle möglicherweise. Weitere Informationen finden Sie unter [Manage Treiber in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Microsoft-Teams, Räume Konfigurationspaket erstellen

1.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**, und wählen Sie dann **Paket erstellen**.

2.  Geben Sie die folgenden Informationen, um das Paket zu erstellen:

    -   Name: **SRS v2 - Setuppaket SRS konfigurieren**

    -   Hersteller: **Microsoft Corporation**

    -   Version: **1.0.0**

    -   Aktivieren Sie das Kontrollkästchen **Dieses Paket Quelldateien enthält** , geben Sie den Pfad zu dem Ordner **SRS v2 - SRS Setup konfigurieren** , und wählen Sie dann auf **Weiter**.

3.  **Erstellen Sie ein Programm nicht**aktivieren Sie, und wählen Sie dann auf **Weiter**.

4.  Überprüfen Sie die Seite **bestätigen Sie die Einstellungen** , und wählen Sie dann auf **Weiter**.

5.  Wählen Sie **Schließen**aus.



## <a name="distribute-configuration-manager-packages"></a>Verteilen von Configuration Manager-Paketen

Alle Pakete müssen an die Server verteilt werden, die die Verteilungspunktrolle in der Configuration Manager-Hierarchie zugewiesen wurden. Gehen Sie zum Paket Verteilung initiieren.

1.  Verteilen Sie Softwarepakete.

    1.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Anwendungsverwaltung** \> **Pakete**. Wählen Sie die Software-Pakete, die Sie verteilen möchten, und wählen Sie dann auf **Content verteilen**.

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann auf **Weiter**.

    3.  Die Liste alle Verteilung Point-Server (oder Punkt Verteilergruppen, je nach der Hierarchie der Konfigurations-Manager) hinzu, und wählen Sie dann auf **Weiter**.

    4.  Wählen Sie **Weiter**aus, und wählen Sie dann auf **Schließen**.

2.  Verteilen von Treiberpaketen.

    1.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **Treiberpakete**. Wählen Sie die Treiberpakete, die Sie verteilen möchten, und wählen Sie dann auf **Inhalt zu verteilen**.

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann auf **Weiter**.

    3.  Die Liste alle Verteilung Point-Server (oder Punkt Verteilergruppen, je nach der Hierarchie der Konfigurations-Manager) hinzu, und wählen Sie dann auf **Weiter**.

    4.  Wählen Sie **Weiter**aus, und wählen Sie dann auf **Schließen**.

3.  Verteilen Sie Betriebssystem-Pakete.

    1.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **Betriebssystemabbilder**. Wählen Sie alle Betriebssystemabbilder, die Sie verteilen möchten, und wählen Sie dann auf **Inhalt zu verteilen**.

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann auf **Weiter**.

    3.  Die Liste alle Verteilung Point-Server (oder Punkt Verteilergruppen, je nach der Hierarchie der Konfigurations-Manager) hinzu, und wählen Sie dann auf **Weiter**.

    4.  Wählen Sie **Weiter**aus, und wählen Sie dann auf **Schließen**.

> [!NOTE]
> Paket Verteilung kann je nach der Größe der Verteilungspakete, Konfigurations-Manager-Hierarchie, Anzahl der Verteilung Point Server und die Bandbreite in Ihrem Netzwerk verfügbar einige Zeit dauern.
> 
> Bevor Sie eine Einheit Microsoft Teams Chatrooms bereitstellen können, müssen alle Pakete verteilt werden.
> 
> Sie können den Status Ihrer Paket Verteilung in der Configuration Manager-Konsole auf **Überwachung** überprüfen \> **Verteilungsstatus** \> **Status des Inhalts**.

## <a name="configuration-manager-task-sequences"></a>Konfigurations-Manager Task sequences

Mit System Center Configuration Manager verwenden Sie Task Sequences, um die Schritte zur Bereitstellung eines Betriebssystemabbilds auf einem Zielcomputer zu automatisieren. Zum Bereitstellen von Microsoft-Teams Chatrooms Einheit automatisiert zu erstellen Sie eine Aufgabensequenz, die zum Starten der Zielcomputer Microsoft Teams Chatrooms, die Windows-10-Enterprise-Betriebssystemabbilds, die Sie installieren möchten und andere Boot-Abbild verweist Weitere zusätzliche Inhalte wie andere Anwendungen oder Softwareupdates.

### <a name="import-the-sample-task-sequence"></a>Importieren Sie die Beispiel Aufgabensequenz

Sie können herunterladen und auf einfache Weise importieren eine Beispiel-Aufgabensequenz und entsprechend Ihren Anforderungen anpassen.

1.  [**Herunterladen**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) der Aufgabensequenz Sample, und kopieren Sie die heruntergeladene Zip-Datei an einen freigegebenen Speicherort.
2.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Betriebssysteme** \> **Task Sequences**, und wählen Sie dann **Import Task Sequence**.

3.  Wählen Sie **Durchsuchen**, wechseln Sie auf den Speicherort des freigegebenen Ordners, den Sie in Schritt 1 verwendet haben, wählen Sie die **Microsoft-Teams Chatrooms Bereitstellung (EN-US) ZIP** -Datei, und wählen Sie dann auf **Weiter**.

4.  Legen Sie die **Aktion** auf **Neu erstellen**, und wählen Sie dann auf **Weiter**.

5.  Bestätigen Sie die Einstellungen, und wählen Sie dann auf **Weiter**.

6.  Wählen Sie **Schließen**aus.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Überprüfen Sie, dass die Pakete Verweis ordnungsgemäß mit jedem Task Sequence Schritt verknüpft sind.

1. Wählen Sie die importierten Aufgabensequenz aus, und wählen Sie dann auf **Bearbeiten**.

    Den Task Sequence Editor wird geöffnet und zeigt jede sequenziellen Schritt, die Sie benötigen zum Bereitstellen und konfigurieren eine Microsoft-Teams Chatrooms Einheit.

2. Durch die einzelnen Schritte durchlaufen Sie, und schließen Sie die empfohlenen Updates:

   1. **In Windows PE neu starten**: Dieser Schritt wird neu gestartet, und klicken Sie dann in Windows PXE startet den Computer. In diesem Schritt muss werden nicht geändert.

   2. **Partition Datenträger 0 – UEFI**: in diesem Schritt löscht die Datenträgerkonfiguration und Partitionen basierend auf den konfigurierten Einstellungen erstellt. Es wird empfohlen, dass Sie keine Änderungen an diesen Schritt vorgenommen.

   3. **SRS Computername festgelegt**: Dieser Schritt umfasst das eine HTML-Anwendung eine Benutzeroberfläche zum Festlegen von eines Computernamen für die Microsoft-Teams Chatrooms Einheit während der Bereitstellung bereitstellen.
      -  Dies ist ein optionaler Schritt, aber es kann nur deaktiviert werden, wenn Sie über ein alternativer Prozess die Benennung von Computern verwalten möchten.
      -  Stellen Sie sicher, dass das Paket **SRS v2 - Set-SRSComputerName** ausgewählt ist. Falls nicht, suchen Sie das Paket, und wählen Sie sie aus.

   4. **Betriebssystem anwenden**: in diesem Schritt gibt an, das Betriebssystemabbild bereitgestellt werden und die unbeaufsichtigte Sysprep Antwortdatei verwendet.
      -  Stellen Sie sicher, dass die richtige Windows 10 Enterprise Operating System Image-Datei ausgewählt ist.
      -  Stellen Sie sicher, dass die **Verwendung einer unbeaufsichtigten oder Sysprep-Antwortdatei für eine benutzerdefinierte Installation** ist aktiviert, und der **SRS v2 - Sysprep-Paket** aktiviert ist. Außerdem sicherstellen Sie, dass **Dateinamen** **unattend.xml**festgelegt ist.

   5. **Windows-Einstellungen gelten**: in diesem Schritt erfasst Informationen über die Windows-Installation.
      -  Enthalten Sie Lizenzierung und Registrierung Informationen, einschließlich der Produktschlüssel, Kennworts eines lokalen Administratorkontos und Zeitzone (je nach Ihren Anforderungen).

   6. **Netzwerkeinstellungen anwenden**: in diesem Schritt können Sie einer Arbeitsgruppe oder Name der Active Directory-Domäne und Organisationseinheit angeben.
      > [!NOTE]
      > Empfohlene Schritte, die Sie bei der Bereitstellung von Microsoft-Teams Chatrooms Einheiten als Mitglied einer Domäne ADSI Directory durchführen müssen, finden Sie unter [Skype Raum System Domäne beitreten Considerations](domain-joining-considerations.md) .
   7. **Treiber anwenden:** Dieser Schritt und seine Unterschritte dienen zum entsprechenden Gerätetreiber und Firmware basierend auf dem Surface Pro Modell haben Sie bereitstellen. Aktualisieren Sie jeden Schritt zum Angeben des entsprechenden Treiberpakets dieser Bereitstellung zugeordnet.
      -   Jedes Paket Nutzung der Windows-Verwaltungsinstrumentation (WMI) Filter zum Bereitstellen von relevanten Treiber konfiguriert und Firmware basierend auf dem Surface Pro Marke und das Modell.
      -   Es wird dringend empfohlen, dass Sie die Konfiguration dieser Treiber nicht ändern, andernfalls Bereitstellung fehlschlagen.

   8. **Einrichten von Windows und Konfigurations-Manager**: in diesem Schritt bereitstellen und konfigurieren Sie den Konfigurations-Manager-Client. Aktualisieren Sie diesen Schritt, um die integrierten Konfigurations-Manager-Client-Paket angeben.

   9. **Stammzertifikat installieren**: in diesem Schritt das Stammzertifikat für Geräte nicht in die Domäne eingebundener verteilt und daher ist optional und standardmäßig deaktiviert.
      -   Aktivieren Sie diesen Schritt, wenn Sie ein Stammzertifikat der Einheiten von Microsoft-Teams Chatrooms bereitstellen müssen.
      -   Wenn Sie benötigen, um diesen Schritt ausführen, stellen Sie sicher, dass der **SRS v2 – Root Certificate-Paket** und **Deaktivieren von 64-Bit-Datei System Umleitung** ausgewählt sind.

   10. **Installieren und Konfigurieren der Überwachung Agent**: in diesem Schritt installiert die 64-Bit-Version von der Microsoft Azure Monitor-Agent und den Verbindung mit den Arbeitsbereich Protokoll Analytics-Agent konfiguriert.
       -   Dieser Schritt ist standardmäßig deaktiviert. Aktivieren Sie diesen Schritt nur aus, wenn der Agent Monitoring verwenden Sie zum Überwachen der Integrität der Microsoft-Teams Räume-Einheiten werden soll.
       -   Bearbeiten Sie diesen Schritt und aktualisieren Sie die Befehlszeilenparameter, um das **Workspace-ID** und den **Arbeitsbereich Schlüssel**anzugeben.
       -   Weitere Informationen zum Beziehen der Vorgänge Management Suite Workspace-ID und den Primärschlüssel finden Sie unter [Configure Geräte für die Überwachung von Azure testen](azure-monitor.md#configure-test-devices-for-azure-monitoring) .
       -   Stellen Sie sicher, dass der **SRS v2 – Microsoft Monitoring Agent-Paket** und **Deaktivieren von 64-Bit-Datei System Umleitung** ausgewählt sind.
       -   Weitere Informationen zum Überwachen der Integrität Ihrer Bereitstellung von Microsoft-Teams Chatrooms finden Sie unter [Planen von Microsoft Teams Chatrooms Verwaltung mit Azure Monitor](../../plan-your-deployment/clients-and-devices/azure-monitor.md), [Deploy Microsoft-Teams, Räume mit Azure Monitor](azure-monitor.md) und [verwalten Microsoft Teams Chatrooms Geräte mit Azure Monitor](../../manage/skype-room-systems-v2/azure-monitor.md).

   11. **Kopie SRS v2 Konfigurationsdateien**: Dieser Schritt kopiert die erforderlichen Dateien von Setup und Konfiguration aus dem Microsoft Teams Chatrooms Deployment Kit in der lokalen Festplatte. Keine Anpassung ist für diesen Schritt erforderlich.
       -   Stellen Sie sicher, dass der **SRS v2 – SRS Anwendungspaket** und **Deaktivieren von 64-Bit-Datei System Umleitung** ausgewählt sind.

   12. **Install-SRSv2-OS-Updates**: in diesem Schritt wird alle obligatorisch mit der Bereitstellung von Microsoft-Teams Chatrooms erforderlichen Betriebssystemupdates bereitgestellt. Gehen Sie wie folgt vor:
       -   Überprüfen Sie [Konfigurieren einer Microsoft-Teams Räume-Konsole](console.md) , um herauszufinden, welche Updates erforderlich sind.
       -   Stellen Sie sicher, dass Ihre **SRS v2 – Paket mit OS Updates** alle erforderlichen Updates enthält.
       -   Stellen Sie sicher, dass der **SRS v2 – Paket mit OS Updates** aktiviert ist.
       -   Stellen Sie sicher, dass die PowerShell-Ausführungsrichtlinie **umgehen**festgelegt ist.

   13. **Computer neu starten**: Dieser Schritt startet den Computer neu, nachdem die obligatorische Betriebssystemupdates installiert worden sind. Keine Anpassung ist für diesen Schritt erforderlich.

   14. **Konfigurieren der Windows-Komponenten**: in diesem Schritt werden die erforderlichen Windows-Features konfiguriert. Keine Anpassung ist für diesen Schritt erforderlich.

   15. **Computer neu starten**: Dieser Schritt startet den Computer neu, nachdem die Windows-Features konfiguriert werden. Keine Anpassung ist für diesen Schritt erforderlich.

   16. **Skype-Benutzer**: Bei diesem Schritt wird das lokale Skype-Konto verwendet, um automatisch bei Windows anmelden, und starten Sie die Anwendung Microsoft-Teams Chatrooms. Dieser Schritt keine Softwarepaket zugeordnet haben, und keine Anpassung für die es erforderlich ist.

   17. **Festlegen einrichten und Konfigurieren der SRS Anwendung**: in diesem Schritt Microsoft Teams Chatrooms die Installation der Anwendung für den nächsten Start des Betriebssystems konfiguriert.
       -   Stellen Sie sicher, dass der **SRS v2 – SRS Setuppaket konfigurieren** und **Deaktivieren von 64-Bit-Datei System Umleitung** ausgewählt sind.

> [!IMPORTANT]
> Es ist sehr wichtig, dass die Task Sequence Schritte in der angegebenen Reihenfolge sein müssen. Ändern der Reihenfolge der Schritte aus, oder konfigurieren zusätzliche Schritte möglicherweise die Bereitstellung aufgehoben.
>
> **Festlegen einrichten und Konfigurieren der SRS Anwendung** Schritt muss der letzte Schritt in der Aufgabensequenz, andernfalls die Bereitstellung kann fehlschlagen.

### <a name="create-deployment-for-the-task-sequence"></a>Bereitstellung für die Abfolge der Vorgänge erstellen

1. Wählen Sie die Abfolge der Vorgänge aus, und wählen Sie dann auf **Bereitstellen**.

2. Wählen Sie auf **Durchsuchen** , um für die Bereitstellung Zielsammlung auszuwählen.

3. Wählen Sie **Alle unbekannten Computern** aus, und wählen Sie dann auf **OK**.

4. Wählen Sie **Weiter**aus.

5. Wählen Sie aus der Dropdownliste **Zweck** **verfügbar** .

6. Wählen Sie **nur Medien und PXE** in der Liste **die folgenden zur Verfügung stellen** , und wählen Sie dann auf **Weiter**.
   > [!WARNING]
   > Es ist sehr wichtig, dass **Zweck** auf **verfügbar**festgelegt ist. Stellen Sie sicher, dass der **Zweck** **nicht** auf **erforderlich**festgelegt ist. Stellen Sie außerdem sicher, dass Sie in **der folgenden zur Verfügung stellen** **nur Medien und PXE** auswählen.
   >
   > Festlegen von diese Werte auf einen anderen Suchbegriff möglicherweise alle Computer mit dem Microsoft-Teams Chatrooms Bereitstellungsabbild Wenn gestartet wird.
7. Geben Sie eine beliebige Zeitplan keine, und wählen Sie **Weiter**aus.

8. Ändern Sie alles innerhalb des Abschnitts der **Benutzeroberfläche** nicht, und wählen Sie **Weiter**aus.

9. Ändern Sie alles innerhalb des Abschnitts **Benachrichtigungen** nicht, und wählen Sie **Weiter**aus.

10. Ändern Sie alles innerhalb des Abschnitts **Verteilungspunkte** nicht, und wählen Sie **Weiter**aus.

11. Bestätigen Sie die Einstellungen, und wählen Sie dann auf **Weiter**.

12. Wählen Sie **Schließen**aus.

<a name="validate-and-troubleshoot-the-solution"></a>Überprüfen Sie und Problembehandlung bei der Lösung
--------------------------------------

Nachdem Sie die System Center Configuration Manager Task Sequences abgeschlossen haben, müssen Sie führen Sie einen Test ausführen, um zu überprüfen, ob die Abfolge der Vorgänge kann bereitstellen und Konfigurieren von Microsoft-Teams Chatrooms Einheiten.

1.  Verbinden Sie das Testgerät mit dem Kabelnetzwerk mithilfe einer der unterstützten Ethernet-Adapter oder mit der Fläche andocken. Wenn PXE-Boot-Funktionalität für Ihre Umgebung nicht konfiguriert wurde, können Sie das Boot-Abbild auf die USB flash-Laufwerk [das Sie zuvor erstellt](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) von USB starten und eine Verbindung herstellen zu Configuration Manager.

2.  Zugriff auf die Firmware und initiieren Sie PXE-Start:

    1.  Stellen Sie sicher, dass das Gerät Fläche ausgeschaltet wird.

    2.  Drücken Sie und halten Sie die **Lautstärke** .

    3.  Drücken und **halten** .

    4.  Nachdem das Gerät beginnt mit starten, lassen Sie die **Lautstärke** los.

    5.  Wählen Sie die **Startkonfiguration**.

    6.  Führen Sie einen der folgenden Schritte aus:

        -   Wählen Sie **PXE-Start**, und ziehen Sie es an den Anfang der Liste. Alternativ können Sie führen Sie links auf den Netzwerkadapter, das Gerät sofort zu starten. Dies wird nicht die Startreihenfolge auswirken.
        -   Wählen Sie das USB-Laufwerk, das die Startmedien enthält.

3.  Wählen Sie **Beenden**, und wählen Sie dann auf **Jetzt neu starten**.

4.  Wenn Sie aufgefordert werden, wählen Sie **Enter** für Startdienst Netzwerk.

5.  Windows PE wird in den Arbeitsspeicher geladen, und der Task Sequence-Assistent wird gestartet. Wählen Sie auf **Weiter** .

6.  Wählen Sie die Abfolge der Vorgänge, die Sie zuvor importiert haben, und wählen Sie dann auf **Weiter**.

7.  Nachdem die Datenträgerkonfiguration angewendet wird, werden Sie aufgefordert, einen Computernamen für das Gerät angeben. Die Benutzeroberfläche wird eine empfohlene Computername basierend auf die Seriennummer des Geräts Surface Pro angezeigt. Sie können entweder den vorgeschlagenen Namen übernehmen oder geben Sie einen neuen Anwendungspool. Befolgen Sie die Anweisungen auf dem Bildschirm Zuordnung Name ein. Wenn Sie **annehmen**auswählen, beginnt mit die Bereitstellung.

8.  Der Rest des Bereitstellungsprozesses erfolgt automatisch und nicht für jede weitere Benutzereingaben bitten.

9.  Nach Abschluss die Bereitstellungsreihenfolge für die Aufgabe Konfigurieren des Geräts sehen Sie die folgenden Konfigurationsbildschirm, die Sie zum Konfigurieren der Einstellungen für die Microsoft-Teams Chatrooms aufgefordert werden.

    ![Anfängliche Setupbildschirm für Microsoft-Teams Chatrooms fest](../../media/room-systems-scale-image2.png)

10.  Schließen Sie in der Microsoft-Teams Chatrooms Konsole Surface Pro und konfigurieren Sie der Einstellungen für die.

11.  Überprüfen Sie, dass die Funktionen aufgeführt, die in der [Hilfe zu Microsoft-Teams Chatrooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) auf dem Gerät bereitgestellt werden.


Um eine fehlerhafte Installation zu beheben, überprüfen Sie **die Masterprotokolldatei, in dem alle Schritte in einer Configuration Manager-Aufgabensequenz ausgeführt protokolliert** .

Die Masterprotokolldatei wird auf eine Reihe von Pfaden, je nach der Phase des Buildprozesses gespeichert. Überprüfen Sie in der folgenden Tabelle, um den Pfad zu der Masterprotokolldatei zu ermitteln.


| **Bereitstellungsphase**                                                            | **Task Sequence Protokollpfad**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| Windows PE, bevor Sie HDD-format                                                        | X:\\Windows\\Temp\\Smstslog\\smsts.log             |
| Windows PE, nach HDD-format                                                         | C:\\_SMSTaskSequence\\Protokolle\\Smstslog\\smsts.log    |
| Betriebssystem bereitgestellt werden, bevor der Konfigurations-Manager-Agent installiert wurde | c:\\_SMSTaskSequence\\Protokolle\\Smstslog\\smsts.log    |
| Betriebssystem und den Konfigurations-Manager-Agent bereitgestellt                   | %windir%\\System32\\Ccm\\Protokolle\\Smstslog\\smsts.log |
| Task Sequence Ausführung abgeschlossen                                                | %windir%\\System32\\Ccm\\Protokolle\\smsts.log           |

> [!TIP]
> Sie können wählen **F8** können Sie jederzeit während der Aufgabensequenz, um eine Befehlskonsole zu öffnen, und klicken Sie dann erhalten Sie Zugriff auf die Masterprotokolldatei.

Überprüfen Sie um PXE Boot-Problemen, die zwei Protokolldateien auf dem Server-Konfigurations-Manager, die speziell für PXE-Aktionen sind:

-   **Pxecontrol.log**, befindet sich im Installationsverzeichnis Protokolle Konfigurations-Manager

-   **Smspxe.log**, befindet sich im Verzeichnis der Konfigurations-Manager-Management Point (VA) logs

Eine vollständige Liste der Protokolldateien, die Sie zum Diagnostizieren Sie Ihre Installations Konfigurations-Manager verwenden können, finden Sie unter [System Center Configuration Manager-Protokolldateien](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).
