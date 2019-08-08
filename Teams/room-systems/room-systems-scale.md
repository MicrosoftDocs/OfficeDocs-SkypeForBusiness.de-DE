---
title: Bereitstellen von Microsoft Teams-Räumen mithilfe von System Center Configuration Manager
author: lanachin
ms.author: v-lanac
ms.reviewer: Turgayo
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 678689e4-d547-499b-be64-7d8f16dd8668
ms.collection: M365-voice
description: Lesen Sie dieses Thema, um Informationen zum Bereitstellen von Microsoft Teams-Räumen in umfangreichen Bereitstellungen zu erhalten.
ms.openlocfilehash: 48a2ddbed8ca5909ca527f7db872c6fa74737610
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243421"
---
# <a name="deploy-microsoft-teams-rooms-by-using-system-center-configuration-manager"></a>Bereitstellen von Microsoft Teams-Räumen mithilfe von System Center Configuration Manager

Dieser Artikel enthält alle erforderlichen Informationen zum Erstellen Ihrer Microsoft Teams rooms-Bereitstellungen mithilfe von System Center Configuration Manager.

Mit den einfach zu verwendenden Methoden, die von System Center Configuration Manager bereitgestellt werden, können Sie das Betriebs System und andere Anwendungen auf mehreren Zielgeräten bereitstellen.

Verwenden Sie den unten dargestellten Ansatz, der Sie durch Ihre Configuration Manager-Konfiguration führt, und passen Sie die Beispielpakete und Skripts an, die in diesem Leitfaden nach Bedarf für Ihre Organisation bereitgestellt werden.

![Bereitstellungsprozess für Microsoft Teams rooms mithilfe von Configuration Manager](../media/room-systems-scale-image1.png)

> [!IMPORTANT]
> Diese Lösung wurde nur mit Surface pro-basierten Bereitstellungen getestet. Befolgen Sie die Richtlinien des Herstellers für Konfigurationen, die nicht auf Surface pro basieren.

## <a name="validate-prerequisites"></a>Überprüfen von Voraussetzungen

Stellen Sie zum Bereitstellen von Microsoft Teams-Räumen mit Configuration Manager sicher, dass Sie die folgenden Voraussetzungen und Anforderungen erfüllen.

### <a name="system-center-configuration-manager-requirements"></a>System Center-Konfigurations-Manager-Anforderungen

-   Die System Center Configuration Manager-Version muss mindestens 1706 oder höher sein. Wir empfehlen die Verwendung von 1710 oder höher. Schauen Sie sich die [Unterstützung für Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) an, um mehr über die Windows 10-Versionen zu erfahren, die von Configuration Manager unterstützt werden.

-   Es muss eine unterstützte Version von Windows Assessment und Deployment Kit (ADK) für Windows 10 installiert sein. Sehen Sie sich die Versionen von [Windows 10 ADK](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-adk) an, die Sie in verschiedenen Versionen von Configuration Manager verwenden können, und stellen Sie sicher, dass Ihre Bereitstellung die richtige Version enthält.

-   Den Standortsystemservern muss die Verteilungspunktrolle zugewiesen worden sein, und die Startabbilder sollten für [PXE-Unterstützung (Preboot Execution Environment)](https://docs.microsoft.com/sccm/osd/deploy-use/use-pxe-to-deploy-windows-over-the-network) aktiviert werden, um Netzwerk initiierte Bereitstellungen zu ermöglichen. Wenn die PXE-Unterstützung nicht aktiviert ist, können Sie für Ihre Bereitstellungen [startfähige Medien](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) verwenden.

-   Ein Netzwerkzugriffskonto muss so konfiguriert sein, dass es neue Bereitstellungsszenarien für Computer (Bare Metal) unterstützt. Wenn Sie mehr über die Konfiguration eines Netzwerkzugriffskontos erfahren möchten, lesen Sie [Verwalten von Konten für den Zugriff auf Inhalte in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

-   Wir empfehlen, dass Sie die [Multicastunterstützung](https://docs.microsoft.com/sccm/osd/deploy-use/use-multicast-to-deploy-windows-over-the-network)aktivieren, wenn Sie wahrscheinlich dasselbe Microsoft Teams rooms-Bild gleichzeitig auf mehreren Geräten bereitstellen.

### <a name="networking-requirements"></a>Netzwerkanforderungen

-   Ihr Netzwerk sollte über einen DHCP-Server (Dynamic Host Configuration Protocol) verfügen, der für die automatische IP-Adress Verteilung an die Subnetze konfiguriert ist, in denen die Microsoft Teams rooms-Einheiten bereitgestellt werden.

    > [!NOTE]
    > Die DHCP-Leasingdauer muss auf einen Wert gesetzt werden, der länger als die Dauer der Bild Bereitstellung ist. Andernfalls schlägt die Bereitstellung möglicherweise fehl.

-   Ihr Netzwerk, einschließlich Switches und virtuellen LANs (VLANs), sollte so konfiguriert werden, dass es PXE unterstützt. Weitere Informationen zur IP-Helper-und PXE-Konfiguration finden Sie bei Ihrem Netzwerkanbieter. Wenn die PXE-Unterstützung nicht aktiviert ist, können Sie auch [startfähige Medien](https://docs.microsoft.com/sccm/osd/deploy-use/use-bootable-media-to-deploy-windows-over-the-network) für Ihre Bereitstellungen verwenden.

    > [!NOTE]
    > Bei Surface pro-Geräten wird das Booten vom Netzwerk (PXE-Start) nur unterstützt, wenn Sie einen Ethernet-Adapter oder eine Docking-Station von Microsoft verwenden. Ethernet-Adapter von Drittanbietern unterstützen keinen PXE-Start mit Surface pro. Weitere Informationen finden Sie unter [Ethernet-Adapter und Surface-Bereitstellung](https://docs.microsoft.com/surface/ethernet-adapters-and-surface-device-deployment) .

## <a name="configure-system-center-configuration-manager-for-operating-system-deployment"></a>Konfigurieren von System Center Configuration Manager für die Betriebs System Bereitstellung

In diesem Artikel wird davon ausgegangen, dass Sie bereits über eine gesunde System Center Configuration Manager-Bereitstellung verfügen und nicht alle erforderlichen Schritte zum Bereitstellen und Konfigurieren von Configuration Manager von Grund auf detailliert ausführen. Die [Dokumentation und die Konfigurationsanleitungen](https://docs.microsoft.com/sccm/) im System Center Configuration Manager sind eine hervorragende Ressource; Wenn Sie Configuration Manager noch nicht bereitgestellt haben, empfehlen wir, mit diesen Ressourcen zu beginnen.

Verwenden Sie die folgenden Anweisungen, um zu überprüfen, ob die OSD-Features (Operating System Deployment) ordnungsgemäß konfiguriert sind.

### <a name="validate-and-upgrade-configuration-manager"></a>Überprüfen und Aktualisieren des Konfigurations-Managers

1.  Wechseln Sie in der Configuration Manager-Konsole zu **Administrator** \> **Updates und-Wartung**.

2.  Überprüfen Sie den installierten Build und die anwendbaren Updates, die noch nicht installiert wurden.

3.  Überprüfen des [Supports für Windows 10 in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/configs/support-for-windows-10#windows-10-as-a-client) Wenn Sie Ihre Bereitstellung aktualisieren müssen, wählen Sie das Update aus, das Sie installieren möchten, und wählen Sie dann **herunterladen**aus.

4.  Nachdem der Download abgeschlossen ist, wählen Sie das Update aus, und wählen Sie dann **Update Pack installieren**aus.

### <a name="configure-distribution-points-to-support-pxe-and-multicast"></a>Konfigurieren von Verteilungspunkten zur Unterstützung von PXE und Multicast

1.  Wechseln Sie in der Configuration Manager-Konsole zu **Verwaltungs** \> **Verteilungspunkten**.

2.  Wählen Sie den Verteilungspunktserver aus, der für die Bereitstellung von Microsoft Teams rooms dient, und wählen Sie dann **Eigenschaften**aus.

3.  Wählen Sie die Registerkarte **PXE** aus, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:
    -   Aktivieren der PXE-Unterstützung für Clients
    -   Diesem Verteilungspunkt gestatten, auf eingehende PXE-Anforderungen zu reagieren
    -   Unterstützung für unbekannte Computer aktivieren

4.  *Optional:* Wenn Sie die Multicastunterstützung aktivieren möchten, wählen Sie die Registerkarte **Multicast** aus, und stellen Sie sicher, dass die folgenden Einstellungen aktiviert sind:
    -   Aktivieren von Multicast zum gleichzeitigen Senden von Daten an mehrere Clients
    -   Konfigurieren des UDP-Portbereichs gemäß den Empfehlungen Ihres Netzwerkteams

### <a name="configure-the-network-access-account"></a>Konfigurieren des Netzwerkzugriffskontos

1.  Wechseln Sie in der Configuration Manager-Konsole zu den **Verwaltungs** \> **Website-Konfigurations** \> **Websites**, und wählen Sie dann die Website aus.

2.  Wählen Sie in der Gruppe **Einstellungen** die Option **Software Verteilung**für **Websitekomponenten** \> konfigurieren aus.

3.  Wählen Sie die Registerkarte **Netzwerkzugriffskonto** aus. richten Sie mindestens ein Konto ein, und wählen Sie dann **OK**aus.

> [!NOTE]
> Die Konten benötigen keine besonderen Rechte, mit Ausnahme des **Zugriffs auf diesen Computer vom Netzwerk aus** direkt auf dem Verteilungspunktserver. Ein generisches Domänenbenutzerkonto ist angemessen. Weitere Informationen finden Sie unter [Verwalten von Konten für den Zugriff auf Inhalte in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/manage-accounts-to-access-content#bkmk_NAA).

### <a name="configure-a-boot-image"></a>Konfigurieren eines Startabbilds

1.  Wechseln Sie in der Configuration Manager-Konsole zu den **Start**Abbildern des **Software Bibliothek** \> - **Betriebssystems** \> .

2.  Wählen Sie **Startabbild (x64)** aus, und wählen Sie dann **Eigenschaften**aus.

3.  Wählen Sie die Registerkarte **Datenquelle** aus, und aktivieren Sie **Dieses Startabbild auf dem PXE-fähigen Verteilungspunkt bereitstellen**.

4.  Wählen Sie die Registerkarte **optionale Komponenten** aus, um erforderliche Komponenten zu installieren:

    1.  Wählen Sie das Stern Symbol aus, und suchen Sie nach **HTML (WinPE-HTA)** .

    2.  Wählen Sie **OK** aus, um dem Startabbild HTML-Anwendungsunterstützung hinzuzufügen.

5.  *Optional:* Um die Bereitstellungsumgebung anzupassen, wählen Sie die Registerkarte **Anpassung** aus.
    -   Aktivieren Sie die **Befehlsunterstützung (nur testen)** , wenn Sie während der Bereitstellung auf eine Eingabeaufforderung zugreifen möchten. Wenn diese Option aktiviert ist, können Sie eine Eingabeaufforderung starten, indem Sie **F8** zu einem beliebigen Zeitpunkt während der Bereitstellung auswählen.
    -   Sie können auch ein benutzerdefiniertes Hintergrundbild angeben, das während der Bereitstellung angezeigt werden soll. Wenn Sie ein Bild festlegen möchten, aktivieren **Sie die Option geben Sie die benutzerdefinierte Hintergrund Bilddatei an (UNC-Pfad** , und wählen Sie den Hintergrund aus.

6.  Wenn Sie dazu aufgefordert werden, wählen Sie **Ja** aus, und verteilen Sie das aktualisierte Startabbild an Ihre Verteilungspunkte.

Weitere Informationen finden Sie unter [Verwalten von Startabbildern mit System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-boot-images).

> [!NOTE]
> Sie können ein startbares USB-Medium erstellen, um auf Tasksequenz basierte Configuration Manager-Bereitstellungen für Umgebungen zu initiieren, die keine PXE-Unterstützung haben. Das startbare Medium enthält nur das Startabbild, optionale prestart-Befehle und die erforderlichen Dateien sowie Configuration Manager-Binärdateien, um das Booten in Windows PE zu unterstützen und die Verbindung mit Configuration Manager für den restlichen Bereitstellungsprozess herzustellen. Weitere Informationen finden Sie unter [Erstellen von Start](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media#BKMK_CreateBootableMedia)baren Medien.

## <a name="create-configuration-manager-packages"></a>Erstellen von Configuration Manager-Paketen

> [!IMPORTANT]
> Die erforderliche Betriebssystemversion für jede Version des SRS-Installationsprogramms ändert sich mit jeder MSI-Version. Wenn Sie die beste Version des Betriebssystems für eine bestimmte MSI-Datei ermitteln möchten, führen Sie das Setupskript für die Konsole einmal aus. Weitere Informationen finden Sie unter [Bereitstellen von Microsoft Teams-Räumen mithilfe von System Center Configuration Manager](room-systems-scale.md).

Configuration Manager erfordert eine Reihe von Paketen zum Bereitstellen und Konfigurieren der Microsoft Teams rooms-Einheiten.

Sie müssen die folgenden Pakete erstellen und konfigurieren und dann an die Configuration Manager-Standortsysteme verteilen, denen die Verteilungspunkt-Serverrolle zugewiesen wurde.

| **Paket Name**                     | **Typ**               | **Beschreibung**                                                                           |
|--------------------------------------|------------------------|-------------------------------------------------------------------------------------------|
| SRS v2-SRS-Anwendungspaket     | Software Paket       | Paket für das Microsoft Teams Room Deployment Kit                                      |
| SRS v2 – Sysprep-Paket             | Software Paket       | Paket für die benutzerdefinierte unbeaufsichtigte XML-Datei zum Konfigurieren von Microsoft Teams-Zimmereinheiten            |
| SRS v2-Set-SRSComputerName-Paket | Software Paket       | Paket für die HTML-Anwendung (HTA), um während der Bereitstellung einen Computernamen zuzuweisen    |
| SRS v2 – Konfigurieren des SRS-Setups         | Software Paket       | Paket zum Konfigurieren der Bereitstellung der Microsoft Teams rooms-App                          |
| SRS v2-Betriebssystem Updates-Paket          | Software Paket       | Paket zum Bereitstellen obligatorischer Betriebssystemupdates                                      |
| SRS v2-Stammzertifikat Paket    | Software Paket       | Optional – Paket zum Bereitstellen des Stammzertifikats (nicht erforderlich für Domänen verbundene Einheiten)  |
| SRS V2 – Paket für Microsoft-Überwachungs-Agents | Software Paket       | Optional – Paket zum Bereitstellen und Konfigurieren des Microsoft Operations Management Suite-Agents|
| SRS v2 – WinPE-Hintergrund Paket    | Software Paket       | Paket für das benutzerdefinierte Hintergrundbild, das für Start Bilder verwendet werden soll                           |
| Windows 10 Enterprise                | Betriebssystemabbild | Paket für die Installationsdatei des Betriebssystems (install. wim)                          |
| Surface pro                          | Treiberpaket         | Paket für die Gerätetreiber und Firmware für Microsoft Surface pro                     |
| Surface pro 4                        | Treiberpaket         | Paket für die Gerätetreiber und Firmware für Microsoft Surface pro 4                   |

Weitere Informationen finden Sie unter [Pakete und Programme in System Center Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/packages-and-programs).

### <a name="create-folders-for-the-package-source-files"></a>Erstellen von Ordnern für die Paketquelldateien

Configuration Manager erfordert, dass Paketquelldateien in einer bestimmten Ordnerstruktur organisiert werden, wenn Sie zum ersten Mal erstellt und aktualisiert werden.

Erstellen Sie die folgende Ordnerstruktur auf der System Center Configuration Manager-Website für die Zentraladministration oder auf der primären Website oder auf einer Serverfreigabe, die Sie zum Hosten von Paketquelldateien verwenden:

-   SRS V2 – Paket für Microsoft-Überwachungs-Agents
-   SRS v2-Betriebssystem Updates-Paket
-   SRS v2-Stammzertifikat Paket
-   SRS v2-Set-SRSComputerName-Paket
-   SRS v2-SRS-Anwendungspaket
-   SRS v2 – Konfigurieren des SRS-Setups
-   SRS v2 – Sysprep-Paket
-   Treiber
    -   Surface pro
    -   Surface pro 4
-   Betriebssysteme
    -   Windows 10 Enterprise

> [!TIP]
> Sie können auch die ZIP-Datei [herunterladen](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) und verwenden, die die Ordnerstruktur für die Pakete, die erforderlichen Skripts und die zu verwendende Tasksequenz Vorlage enthält, die Sie importieren müssen.

### <a name="create-the-monitoring-agent-package"></a>Erstellen des Überwachungs-Agent-Pakets

1. Laden Sie den Überwachungs- <https://go.microsoft.com/fwlink/?LinkId=828603>Agent von herunter.

2. Extrahieren Sie das Paket in den Ordner **SRS v2-Microsoft-Überwachungs-Agent-Paket** , indem Sie ein Eingabeaufforderungsfenster öffnen und **MMASetup-amd64. exe/c:** an der Eingabeaufforderung eingeben.

3. Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.

4. Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:

   - Name<strong>: SRS V2 – Paket für Microsoft-Überwachungs-Agents</strong>

   - Hersteller<strong>: Microsoft Corporation</strong>

   - Version<strong>: 8.1.11081.0</strong> (geben Sie die Version der heruntergeladenen Installationsdatei ein)

   - Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-Microsoft-Überwachungs-Agent-Paket** Ordner ein, und wählen Sie dann **weiter**aus.

5. Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.

6. Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.

7. Wählen Sie **Schließen**aus.

### <a name="create-the-operating-system-updates-package"></a>Erstellen des Betriebssystemupdates-Pakets

1. Erstellen Sie im Ordner **SRS v2-OS Updates Package** ein neues PowerShell-Skript mit dem Namen **install-SRSv2-OS-Updates. ps1**.

2. Kopieren Sie das Skript unten in das **install-SRSv2-OS-Updates. ps1** -Skript. Alternativ können Sie das install-SRSv2-OS-Updates. ps1-Skript [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.
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
   > Zu dem Zeitpunkt, zu dem dieser Artikel veröffentlicht wurde, war nur [KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu) erforderlich. Aktivieren Sie das Kontrollkästchen [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md), um festzustellen, ob andere Updates erforderlich sind.

4. Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.

5. Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:
   -   Name: **SRS v2 – Betriebssystem Updates-Paket**
   -   Hersteller: **Microsoft Corporation**
   -   Version: **1.0.0**
   -   Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-OS-Updatepaket** Ordner ein, und wählen Sie dann **weiter**aus.

6. Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.

7. Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.

8. Wählen Sie **Schließen**aus.

### <a name="create-the-root-certificate-package-optional"></a>Erstellen des Stammzertifikat Pakets (optional)

Sie erstellen dieses Paket, um das Stammzertifikat für Geräte zu verteilen, die nicht mit einer Active Directory-Domäne verbunden werden. Erstellen Sie dieses Paket nur, wenn die folgenden Bedingungen zutreffen:
-   Ihre Bereitstellung umfasst lokales lync oder Skype for Business Server.
-   Microsoft Teams rooms-Einheiten sind so konfiguriert, dass Sie in einer Arbeitsgruppe statt in einem Domänenmitglied funktionieren.

1.  Kopieren Sie das Stammzertifikat in den Ordner **SRS v2 – Stammzertifikat Paket** .

2.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.

3.  Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:
    -   Name: **SRS v2 – Stammzertifikat Paket**
    -   Hersteller: *Name Ihrer Organisation*
    -   Version: **1.0.0**
    -   Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum Ordner **SRS v2 – Stammzertifikat Paket** ein, und wählen Sie dann **weiter**aus.

4.  Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.

5.  Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.

6.  Wählen Sie **Schließen**aus.

### <a name="create-the-microsoft-teams-rooms-deployment-kit-package"></a>Erstellen des Microsoft Teams Room Deployment Kit-Pakets

1.  Laden Sie die neueste Version des **Microsoft Teams rooms Deployment Kit** von <https://go.microsoft.com/fwlink/?linkid=851168>herunter, und installieren Sie Sie auf einer Workstation.

2.  Kopieren Sie den Inhalt von **C\\: Program Files (x86\\) Skype Room System Deployment Kit** in den Ordner **SRS v2-SRS-Anwendungspaket** .

3.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.

4.  Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:
    -   Name: **SRS v2 – SRS-Anwendungspaket**
    -   Hersteller: **Microsoft Corporation**
    -   Version: **3.1.104.0** (geben Sie die Version der heruntergeladenen Installationsdatei ein)
    -   Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-SRS-Anwendungspaket** Ordner ein, und wählen Sie dann **weiter**aus.
5.  Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.

6.  Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.

7.  Wählen Sie **Schließen**aus.

### <a name="create-the-computer-name-assignment-package"></a>Erstellen des Aufgabenpakets "Computername"

1.  Erstellen Sie im **Paketordner SRS v2-Set-SRSComputerName** eine neue HTML-Anwendung mit dem Namen **Set-SRSComputerName. HTA** .

2.  Kopieren Sie das folgende Skript in die **Set-SRSComputerName. HTA** -Datei. Alternativ können Sie die Set-SRSComputerName. HTA-Datei [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.
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
3.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.

4.  Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:

    -   Name: **SRS v2-Set-SRSComputerName-Paket**

    -   Hersteller: **Microsoft Corporation**

    -   Version: **1.0.0**

    -   Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-Set-SRSComputerName-Paket** Ordner ein, und wählen Sie dann **weiter**aus.

5.  Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.

6.  Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.

7.  Wählen Sie **Schließen**aus.

### <a name="create-the-sysprep-package"></a>Erstellen des Sysprep-Pakets

1. Erstellen Sie im Ordner **SRS v2 – Sysprep-Paket** eine neue XML-Datei mit dem Namen Unattend **. XML** .

2. Kopieren Sie den folgenden Text in die Datei **Unattend. XML** . Alternativ können Sie die Datei "Unattend. xml" [hier](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true)herunterladen.
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
3. Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.

4. Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:
   -   Name: **SRS v2 – Sysprep-Paket**
   -   Hersteller: **Microsoft Corporation**
   -   Version: **1.0.0**
   -   Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum Ordner **SRS v2 – Sysprep-Paket** ein, und wählen Sie dann **weiter**aus.
5. Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.

6. Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.

7. Wählen Sie **Schließen**aus.

### <a name="create-the-windows-10-enterprise-package"></a>Erstellen des Windows 10 Enterprise-Pakets

1.  Besorgen Sie sich ein Windows 10 Enterprise x64-Medium, und kopieren Sie die Datei " **install. wim** " in den **\\Windows 10 Enterprise** -Ordner der Betriebssysteme.

2.  Wechseln Sie in der Configuration Manager-Konsole zu den Betriebs **System**Abbildern der **Software Bibliothek** \> **** \> , und wählen Sie dann **Betriebssystemabbild hinzufügen**aus.

3.  Geben Sie den Pfad zu der soeben kopierten **install. wim** -Datei an, und wählen Sie dann **weiter**aus.

4.  Aktualisieren Sie das Feld **Version** so, dass es der Buildnummer des Windows 10 Enterprise-Bilds entspricht, und wählen Sie dann **weiter**aus.

5.  Überprüfen Sie die Seite **Details** , und wählen Sie dann **weiter**aus.

6.  Wählen Sie **Schließen**aus.

Weitere Informationen finden Sie unter [Verwalten von Betriebssystemabbildern mit System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-operating-system-images).

### <a name="create-surface-pro-device-driver-packages"></a>Erstellen von Surface pro-Gerätetreiberpaketen

Microsoft Teams Rooms wird sowohl für Surface pro als auch Surface pro 4 unterstützt. Sie müssen für jedes Surface pro-Modell, das Sie in Ihrer Umgebung haben, ein Treiberpaket erstellen.

> [!IMPORTANT]
> Die Treiber müssen mit dem Windows 10 Enterprise Build und der Microsoft Teams Room Deployment Kit-Version kompatibel sein. Weitere Informationen finden Sie unter [herunterladen der neuesten Firmware und Treiber für Surface-Geräte](https://docs.microsoft.com/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices) und [Konfigurieren einer Konsole](console.md).

1.  Laden Sie die neuesten Treiber und Firmware herunter.
    -   Für Surface pro:<https://www.microsoft.com/download/details.aspx?id=55484>
    -   Für Surface pro 4:<https://www.microsoft.com/download/details.aspx?id=49498>

2.  Extrahieren Sie den heruntergeladenen Treiber und die Firmware. Öffnen Sie ein Eingabeaufforderungsfenster, und geben Sie an der Eingabeaufforderung einen der folgenden Befehle ein:
    -   `msiexec /a C:\SurfacePro_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro"`
    -   `msiexec /a C:\SurfacePro4_Win10.msi /passive TARGETDIR="C:\_Sources\\Drivers\Surface Pro 4"`

3.  Wechseln Sie in der Configuration Manager-Konsole zu den Treibern der **Software Bibliothek** \> - **Betriebssysteme** \> ****, und wählen Sie dann **Treiber importieren**aus.

4.  Wählen Sie **alle Treiber importieren im folgenden Netzwerkpfad (UNC)** aus, wählen Sie den Quellordner aus (beispielsweise\\C\\:\\_Sources Driver Surface pro), und wählen Sie dann **weiter**aus.

5.  Wählen Sie auf der Seite **Geben Sie die Details für die importierten Treiber** an alle aufgeführten Treiber aus, und wählen Sie dann **Diese Treiber aktivieren aus, und ermöglichen Sie es Computern, Sie zu installieren**.

6.  Wählen Sie **Kategorien**aus, erstellen Sie eine neue Kategorie, die dem Oberflächenmodell entspricht, wählen Sie **OK**aus, und wählen Sie dann **weiter**aus.

7.  Wählen Sie **neues Paket**aus.

8.  Geben Sie den Paketnamen an, der dem Surface pro-Modell entspricht, geben Sie einen Ordnerpfad zum Speichern der Treiberpaketdateien ein, wählen Sie **OK**aus, und wählen Sie dann **weiter**aus.

9.  Stellen Sie sicher, dass auf der Seite **Start Bilder** keine Startabbilder ausgewählt sind, und wählen Sie dann **weiter**aus.

10. Wählen Sie **Schließen**aus.

11. Wechseln Sie zu den Treibern der **Software Bibliothek** \> - **Betriebssysteme** \> ****, wählen Sie Ordner ** \> erstellen**aus, und geben Sie einen Ordnernamen ein, der dem Surface pro-Modell entspricht, für das Sie die Treiber gerade importiert haben.

12. Verschieben Sie alle importierten Treiber in den neu erstellten Ordner, um die Navigation und den Vorgang zu vereinfachen.

> [!NOTE]
> Wiederholen Sie diese Schritte für andere Surface pro-Modelle, die Sie möglicherweise haben. Weitere Informationen finden Sie unter [Verwalten von Treibern in System Center Configuration Manager](https://docs.microsoft.com/sccm/osd/get-started/manage-drivers).

### <a name="create-microsoft-teams-rooms-configuration-package"></a>Konfigurationspaket "Microsoft Teams-Chatrooms erstellen"

1.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**, und wählen Sie dann **Paket erstellen**aus.

2.  Geben Sie die folgenden Informationen ein, um das Paket zu erstellen:

    -   Name: **SRS v2 – Konfigurieren des SRS-Setup Pakets**

    -   Hersteller: **Microsoft Corporation**

    -   Version: **1.0.0**

    -   Aktivieren Sie das Kontrollkästchen **Dieses Paket enthält Quelldateien** , geben Sie den Pfad zum **SRS v2-Setup-** Ordner ein, und wählen Sie dann **weiter**aus.

3.  Wählen Sie **Programm nicht erstellen**aus, und wählen Sie dann **weiter**aus.

4.  Überprüfen Sie die Seite **Einstellungen bestätigen** , und wählen Sie dann **weiter**aus.

5.  Wählen Sie **Schließen**aus.



## <a name="distribute-configuration-manager-packages"></a>Verteilen von Configuration Manager-Paketen

Alle Pakete müssen an die Server verteilt werden, denen die Verteilungspunktrolle in der Configuration Manager-Hierarchie zugewiesen wurde. Führen Sie die folgenden Anweisungen aus, um die Paketverteilung zu initiieren.

1.  Softwarepakete verteilen.

    1.  Wechseln Sie in der Configuration Manager-Konsole zu **Software Library** \> **Application Management** \> **Packages**. Wählen Sie alle Softwarepakete aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen**aus.

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann **weiter**aus.

    3.  Fügen Sie der Liste alle Verteilungspunktserver (oder Verteilungspunktgruppen, je nach Ihrer Configuration Manager-Hierarchie) hinzu, und wählen Sie dann **weiter**aus.

    4.  Wählen Sie **weiter**aus, und wählen Sie dann **Schließen**aus.

2.  Treiberpakete verteilen.

    1.  Wechseln Sie in der Configuration Manager-Konsole zu den **Treiberpaketen**für **Software Bibliothek** \> - **Betriebssysteme** \> . Wählen Sie alle Treiberpakete aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen**aus.

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann **weiter**aus.

    3.  Fügen Sie der Liste alle Verteilungspunktserver (oder Verteilungspunktgruppen, je nach Ihrer Configuration Manager-Hierarchie) hinzu, und wählen Sie dann **weiter**aus.

    4.  Wählen Sie **weiter**aus, und wählen Sie dann **Schließen**aus.

3.  Verteilen von Betriebssystempaketen

    1.  Wechseln Sie in der Configuration Manager-Konsole zu den **** \> **Betriebssystem**Abbildern der **Software Bibliothek** \> . Wählen Sie alle Betriebssystem Bilder aus, die Sie verteilen möchten, und wählen Sie dann **Inhalt verteilen**aus.

    2.  Überprüfen Sie die Liste der Pakete, und wählen Sie dann **weiter**aus.

    3.  Fügen Sie der Liste alle Verteilungspunktserver (oder Verteilungspunktgruppen, je nach Ihrer Configuration Manager-Hierarchie) hinzu, und wählen Sie dann **weiter**aus.

    4.  Wählen Sie **weiter**aus, und wählen Sie dann **Schließen**aus.

> [!NOTE]
> Die Paketverteilung kann abhängig von der Paketgröße, der Configuration Manager-Hierarchie, der Anzahl der Verteilungspunktserver und der in Ihrem Netzwerk verfügbaren Bandbreite einige Zeit in Anspruch nehmen.
> 
> Alle Pakete müssen verteilt werden, bevor Sie mit der Bereitstellung einer Microsoft Teams rooms-Einheit beginnen können.
> 
> Sie können den Status Ihrer Paketverteilung in der Configuration Manager-Konsole überprüfen, indem **** \> Sie auf den **Inhaltsstatus**des **Verteilungsstatus** \> überwachen wechseln.

## <a name="configuration-manager-task-sequences"></a>Tasksequenzen für Configuration Manager

Sie verwenden Tasksequenzen mit System Center Configuration Manager, um die Schritte zum Bereitstellen eines Betriebs System Abbilds auf einem Zielcomputer zu automatisieren. Wenn Sie eine Microsoft Teams rooms-Einheit auf automatisierte Weise bereitstellen möchten, erstellen Sie eine Tasksequenz, die auf das Startabbild verweist, das zum Starten des Microsoft Teams Room-Zielcomputers, des Windows 10 Enterprise-Betriebssystemabbilds, das Sie installieren möchten, und allen andere zusätzliche Inhalte wie andere Anwendungen oder Softwareupdates.

### <a name="import-the-sample-task-sequence"></a>Importieren der Beispiel Tasksequenz

Sie können eine Beispiel Tasksequenz herunterladen und auf einfache Weise importieren und an Ihre Anforderungen anpassen.

1.  [**Laden**](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/Skype-Room-Systems-v2/SRS-v2-Configuration-Manager-Files.zip?raw=true) Sie die Beispiel Tasksequenz herunter, und kopieren Sie die heruntergeladene ZIP-Datei an einen freigegebenen Speicherort.
2.  Wechseln Sie in der Configuration Manager-Konsole zu den **Tasksequenzen** **Software Library** \> **Operating Systems** \> , und wählen Sie dann **Tasksequenz importieren**aus.

3.  Wählen Sie **Durchsuchen**aus, wechseln Sie zum Speicherort des freigegebenen Ordners, den Sie in Schritt 1 verwendet haben, wählen Sie die **Microsoft Teams Room Deployment (en-US). zip** -Datei aus, und wählen Sie dann **weiter**aus.

4.  Legen Sie **Aktion** auf **neu erstellen**, und wählen Sie dann **weiter**aus.

5.  Bestätigen Sie die Einstellungen, und wählen Sie dann **weiter**aus.

6.  Wählen Sie **Schließen**aus.

### <a name="validate-that-the-reference-packages-are-correctly-linked-to-each-task-sequence-step"></a>Überprüfen Sie, ob die Verweis Pakete ordnungsgemäß mit jedem Tasksequenzschritt verknüpft sind.

1. Wählen Sie die importierte Tasksequenz aus, und wählen Sie dann **Bearbeiten**aus.

    Der Task Sequenz-Editor wird geöffnet und zeigt jeden sequenziellen Schritt an, den Sie für die Bereitstellung und Konfiguration einer Microsoft Teams rooms-Einheit benötigen.

2. Durchlaufen Sie die einzelnen Schritte, und führen Sie die empfohlenen Updates aus:

   1. **Neustart in Windows PE**: dieser Schritt wird neu gestartet und dann der Computer in Windows PXE gestartet. Für diesen Schritt sind keine Änderungen erforderlich.

   2. **Partition Disk 0 – UEFI**: dieser Schritt löscht die Datenträgerkonfiguration und erstellt Partitionen basierend auf den konfigurierten Einstellungen. Wir empfehlen, dass Sie an diesem Schritt keine Änderungen vornehmen.

   3. **SRS-Computer Name einrichten**: dieser Schritt umfasst eine HTML-Anwendung, um eine Benutzeroberfläche bereitzustellen, um einen Computer Namen für die Einheit Microsoft Teams rooms während der Bereitstellung zu definieren.
      -  Dies ist ein optionaler Schritt, der aber nur deaktiviert werden kann, wenn Sie die Computer Namensgebung in einem anderen Prozess verwalten möchten.
      -  Überprüfen Sie, ob das Paket **SRS v2-Set-SRSComputerName** ausgewählt ist. Wenn dies nicht der Fall ist, wechseln Sie zum Paket, und wählen Sie es aus.

   4. **Betriebssystem anwenden**: dieser Schritt gibt das Betriebssystemabbild an, das bereitgestellt werden soll, und die zu verwendende Antwortdatei für die unbeaufsichtigte Sysprep.
      -  Überprüfen Sie, ob die richtige Abbilddatei für das Windows 10 Enterprise-Betriebssystem ausgewählt ist.
      -  Stellen Sie sicher, dass die **Verwendung einer Antwortdatei für eine unbeaufsichtigte oder Sysprep für eine benutzerdefinierte Installation** aktiviert ist und das **SRS v2-Sysprep-Paket** ausgewählt ist. Stellen Sie außerdem sicher, dass der **Dateiname** auf **Unattend. XML**festgesetzt ist.

   5. **Windows-Einstellungen übernehmen**: dieser Schritt sammelt Informationen zur Windows-Installation.
      -  Stellen Sie Lizenzierungs-und Registrierungsinformationen bereit, einschließlich des Product Keys, des Kennworts für das lokale Administratorkonto und der Zeitzone (je nach Ihren Anforderungen).

   6. **Netzwerkeinstellungen übernehmen**: mit diesem Schritt können Sie eine Arbeitsgruppe oder einen Active Directory-Domänennamen und eine Organisationseinheit angeben.
      > [!NOTE]
      > Informationen zu empfohlenen Aktionen, die Sie beim Bereitstellen von Microsoft Teams rooms-Einheiten als Mitglieder einer Actve-Verzeichnisdomäne ausführen müssen, finden Sie unter [Überlegungen zu Skype Room System Domain Joining](domain-joining-considerations.md) .
   7. **Anwenden von Treibern:** Dieser Schritt und seine unter Schritte werden verwendet, um anwendbare Gerätetreiber und Firmware basierend auf dem von Ihnen verwendeten Surface pro-Modell bereitzustellen. Aktualisieren Sie die einzelnen Schritte, um das entsprechende Treiberpaket anzugeben, das dieser Bereitstellung zugeordnet ist.
      -   Jedes Treiberpaket ist so konfiguriert, dass es die Windows-Verwaltungsinstrumentation (WMI)-Filter nutzt, um relevante Treiber und Firmware basierend auf dem Surface pro-Hersteller und-Modell bereitzustellen.
      -   Wir empfehlen dringend, dass Sie die Konfiguration dieser Treiber nicht ändern, da die Bereitstellung andernfalls möglicherweise fehlschlägt.

   8. **Einrichten von Windows und Configuration Manager**: dieser Schritt stellt den Configuration Manager-Client bereit und konfiguriert ihn. Aktualisieren Sie diesen Schritt, um das integrierte Configuration Manager-Client Paket anzugeben.

   9. **Installieren des Stammzertifikats**: mit diesem Schritt wird das Stammzertifikat für nicht-Domänen verbundene Geräte verteilt und ist daher standardmäßig optional und deaktiviert.
      -   Aktivieren Sie diesen Schritt, wenn Sie ein Stammzertifikat für die Microsoft Teams-Zimmereinheiten bereitstellen müssen.
      -   Wenn Sie diesen Schritt ausführen müssen, stellen Sie sicher, dass das **SRS v2 – Stammzertifikat Paket** und die Deaktivierung der **64-Bit-Dateisystem Umleitung** ausgewählt sind.

   10. **Installieren und Konfigurieren des Überwachungs-Agents**: mit diesem Schritt wird die 64-Bit-Version des Microsoft Azure Monitor-Agents installiert und der Agent so konfiguriert, dass eine Verbindung mit Ihrem Protokollanalyse Arbeitsbereich hergestellt wird.
       -   Dieser Schritt ist standardmäßig deaktiviert. Aktivieren Sie diesen Schritt nur, wenn Sie den Überwachungs-Agent verwenden möchten, um den Status Ihrer Microsoft Teams-Zimmereinheiten zu überwachen.
       -   Bearbeiten Sie diesen Schritt, und aktualisieren Sie die Befehlszeilenparameter, um die **Arbeitsbereichs-ID** und den **Arbeitsbereichs Schlüssel**anzugeben.
       -   Weitere Informationen zum Abrufen der Arbeitsbereichs-ID der Operations Management Suite und des Primärschlüssels finden Sie unter [Konfigurieren von Testgeräten für die Azure-Überwachung](azure-monitor-deploy.md#configure-test-devices-for-azure-monitoring) .
       -   Vergewissern Sie sich, dass das **SRS v2 – Microsoft Monitoring Agent-Paket** und die Deaktivierung der **64-Bit-Dateisystem Umleitung** ausgewählt sind.
       -   Weitere Informationen zum Überwachen der Integrität Ihrer Microsoft Teams rooms-Bereitstellung finden Sie unter [Planen der Microsoft Teams rooms-Verwaltung mit Azure Monitor](azure-monitor-plan.md), [Bereitstellen der Microsoft Teams rooms-Verwaltung mit Azure Monitor](azure-monitor-deploy.md) und [Verwalten von Microsoft Teams Räume Geräte mit Azure Monitor](azure-monitor-manage.md).

   11. **Kopieren von SRS v2-Konfigurationsdateien**: dieser Schritt kopiert die erforderlichen Setup-und Konfigurationsdateien aus dem Microsoft Teams rooms Deployment Kit auf die lokale Festplatte. Für diesen Schritt sind keine Anpassungen erforderlich.
       -   Vergewissern Sie sich, dass das **SRS v2-SRS-Anwendungspaket** und die Deaktivierung der **64-Bit-Dateisystem Umleitung** ausgewählt sind.

   12. **Installieren-SRSv2-OS-Updates**: in diesem Schritt werden alle obligatorischen Betriebssystemupdates bereitgestellt, die für die Microsoft Teams rooms-Bereitstellung erforderlich sind. Gehen Sie wie folgt vor:
       -   Aktivieren Sie das Kontrollkästchen [Konfigurieren einer Microsoft Teams rooms-Konsole](console.md) , um festzustellen, welche Updates erforderlich sind.
       -   Überprüfen Sie, ob Ihr **SRS v2 – OS-Updatepaket** alle erforderlichen Updates enthält.
       -   Überprüfen Sie, ob das **Paket SRS v2 – Betriebssystem Updates** ausgewählt ist.
       -   Überprüfen Sie, ob die PowerShell-Ausführungsrichtlinie auf **Bypass**festgesetzt ist.

   13. **Computer neu starten**: mit diesem Schritt wird der Computer neu gestartet, nachdem die obligatorischen Betriebssystemupdates installiert wurden. Für diesen Schritt sind keine Anpassungen erforderlich.

   14. **Konfigurieren von Windows-Komponenten**: in diesem Schritt werden die erforderlichen Windows-Features konfiguriert. Für diesen Schritt sind keine Anpassungen erforderlich.

   15. **Computer neu starten**: mit diesem Schritt wird der Computer neu gestartet, nachdem die Windows-Features konfiguriert wurden. Für diesen Schritt sind keine Anpassungen erforderlich.

   16. **Lokalen Skype-Nutzer hinzufügen**: mit diesem Schritt wird das lokale Skype-Konto erstellt, das für die automatische Anmeldung bei Windows und das Starten der Microsoft Teams rooms-Anwendung verwendet wird. Diesem Schritt ist kein Softwarepaket zugeordnet, und es ist keine Anpassung erforderlich.

   17. **Einrichten und Konfigurieren von SRS-Anwendungen**: dieser Schritt konfiguriert die Anwendungsinstallation von Microsoft Teams rooms für den nächsten Start des Betriebssystems.
       -   Vergewissern Sie sich, dass das SRS **v2 – Setup-Paket** für die SRS-Konfiguration und die **64-Bit-Dateisystem Umleitung deaktiviert** sind.

> [!IMPORTANT]
> Es ist sehr wichtig, dass die Tasksequenzschritte in der angegebenen Reihenfolge ausgeführt werden müssen. Wenn Sie die Reihenfolge der Schritte ändern oder zusätzliche Schritte konfigurieren, kann dies die Bereitstellung unterbrechen.
>
> Das **Einrichten und Konfigurieren des SRS-Anwendungs** Schritts muss der letzte Schritt in der Tasksequenz sein, da andernfalls möglicherweise die Bereitstellung fehlschlägt.

### <a name="create-deployment-for-the-task-sequence"></a>Erstellen einer Bereitstellung für die Tasksequenz

1. Wählen Sie die Tasksequenz aus, und wählen Sie **Bereitstellen**aus.

2. Wählen Sie **Durchsuchen** aus, um die Zielsammlung für die Bereitstellung auszuwählen.

3. Wählen Sie **alle unbekannten Computer** aus, und wählen Sie dann **OK**aus.

4. Wählen Sie **weiter**aus.

5. Wählen Sie in der **** Dropdownliste Purpose **available (verfügbar** ) aus.

6. Wählen Sie **nur Medien und PXE** in der Liste in der **folgenden Liste verfügbar machen** aus, und wählen Sie dann **weiter**aus.
   > [!WARNING]
   > Es ist sehr wichtig, **** dass Purpose auf **available**festgesetzt ist. Stellen Sie sicher, dass der **Zweck** **nicht** auf **erforderlich**festgesetzt ist. Stellen Sie außerdem sicher, dass Sie **nur Medien und PXE** in der **folgenden verfügbar machen**auswählen.
   >
   > Wenn diese Werte auf etwas anderes festgelegt werden, kann dies dazu führen, dass alle Computer beim Booten das Bereitstellungs Bild von Microsoft Teams rooms erhalten.
7. Geben Sie keinen Zeitplan an, und wählen Sie **weiter**aus.

8. Ändern Sie im Abschnitt **Benutzerfreundlichkeit** nichts, und wählen Sie **weiter**aus.

9. Ändern Sie im Abschnitt **Benachrichtigungen** nichts, und wählen Sie **weiter**aus.

10. Ändern Sie im Abschnitt Verteilungs **Punkte** nichts, und wählen Sie **weiter**aus.

11. Bestätigen Sie die Einstellungen, und wählen Sie dann **weiter**aus.

12. Wählen Sie **Schließen**aus.

<a name="validate-and-troubleshoot-the-solution"></a>Überprüfen und Problembehandlung der Lösung
--------------------------------------

Nachdem Sie die Tasksequenzen des System Center Configuration Manager abgeschlossen haben, müssen Sie einen Testlauf durchführen, um zu überprüfen, ob die Tasksequenz Microsoft Teams-Zimmereinheiten bereitstellen und konfigurieren kann.

1.  Verbinden Sie das Test Gerät mit dem kabelgebundenen Netzwerk, indem Sie einen der unterstützten Ethernet-Adapter verwenden oder die Surface-Docking-Station verwenden. Wenn die PXE-Start Funktionalität für Ihre Umgebung nicht konfiguriert wurde, können Sie das Startabbild auf dem USB-Stick verwenden, den [Sie zuvor erstellt](https://docs.microsoft.com/sccm/osd/deploy-use/create-bootable-media) haben, um von USB zu booten und mit Configuration Manager zu verbinden.

2.  Zugreifen auf die Firmware und Initiieren des PXE-Starts:

    1.  Stellen Sie sicher, dass das Surface-Gerät ausgeschaltet ist.

    2.  Drücken Sie die **Lautstärke** Taste und halten Sie sie gedrückt.

    3.  Drücken Sie die **Power** -Taste, und lassen Sie sie los.

    4.  Nachdem das Gerät gestartet wurde, lassen Sie die **Lautstärke** Taste los.

    5.  Wählen Sie **Startkonfiguration**aus.

    6.  Führen Sie einen der folgenden Schritte aus:

        -   Wählen Sie **PXE-Start**aus, und ziehen Sie den Mauszeiger an den Anfang der Liste. Sie können aber auch nach links auf dem Netzwerkadapter wischen, um sofort auf das Gerät zu booten. Dies wirkt sich nicht auf die Startreihenfolge aus.
        -   Wählen Sie das USB-Flashlaufwerk aus, das die Startmedien enthält.

3.  Wählen Sie **Beenden**und dann **jetzt neu starten**aus.

4.  Wenn Sie dazu aufgefordert werden, wählen Sie für den Netzwerkstart Dienst **Enter** aus.

5.  Windows PE wird in den Arbeitsspeicher geladen, und der Task Sequenz-Assistent wird gestartet. Wählen Sie **weiter** aus, um fortzufahren.

6.  Wählen Sie die zuvor importierte Tasksequenz aus, und wählen Sie dann **weiter**aus.

7.  Nachdem die Datenträgerkonfiguration angewendet wurde, werden Sie aufgefordert, einen Computernamen für das Gerät anzugeben. Auf der Benutzeroberfläche wird ein empfohlener Computername basierend auf der Seriennummer des Surface pro-Geräts angezeigt. Sie können entweder den vorgeschlagenen Namen akzeptieren oder einen neuen Namen angeben. Folgen Sie den Anweisungen auf dem Bildschirm Computername-Zuordnung. Wenn Sie **annehmen**auswählen, beginnt die Bereitstellung.

8.  Der restliche Bereitstellungsprozess ist automatisch und fordert keine weitere Benutzereingabe.

9.  Nachdem die Bereitstellungstasksequenz die Konfiguration des Geräts abgeschlossen hat, wird der folgende Konfigurationsbildschirm angezeigt, in dem Sie aufgefordert werden, die Anwendungseinstellungen für Microsoft Teams Rooms zu konfigurieren.

    ![Bildschirm ' Initial Setup ' für die Microsoft Teams rooms-Anwendung](../media/room-systems-scale-image2.png)

10.  Schließen Sie das Surface pro an die Microsoft Teams rooms-Konsole an, und konfigurieren Sie die Anwendungseinstellungen.

11.  Überprüfen Sie, ob die in [Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2) -Chatrooms aufgeführten Funktionen auf dem bereitgestellten Gerät funktionieren.


Wenn Sie eine fehlerhafte Installation beheben möchten, überprüfen Sie die Datei **"smsts. log** , in der alle in einer Configuration Manager-Tasksequenz ausgeführten Schritte protokolliert werden.

Die Datei "" smsts. log "wird je nach Phase des Buildprozesses in einer Reihe von Pfaden gespeichert. Überprüfen Sie die folgende Tabelle, um den Pfad zur Datei "" smsts. log "zu identifizieren.


| **Bereitstellungsphase**                                                            | **Task Sequenzprotokoll Pfad**                         |
|---------------------------------------------------------------------------------|----------------------------------------------------|
| WinPE, vor dem Festplattenformat                                                        | X:\\Windows\\Temp\\smstslog\\"smsts. log             |
| WinPE, nach Festplattenformat                                                         | C:\\_SMSTaskSequence\\Logs\\Smstslog\\"smsts. log    |
| Betriebssystem, das vor der Installation des Configuration Manager-Agents bereitgestellt wurde | c:\\_SMSTaskSequence\\Logs\\Smstslog\\"smsts. log    |
| Betriebssystem und bereitgestellter Configuration Manager-Agent                   | % windir%\\System32\\ccm\\-\\Protokolle\\Smstslog "smsts. log |
| Ausführung der Task Sequenz abgeschlossen                                                | % windir%\\System32\\ccm\\-\\Protokolle "smsts. log           |

> [!TIP]
> Sie können **F8** während der Tasksequenz zu einem beliebigen Zeitpunkt auswählen, um eine Befehlskonsole zu öffnen, und dann Zugriff auf die Datei "" smsts. log "erhalten.

Wenn Sie Probleme mit dem PXE-Start beheben möchten, überprüfen Sie die beiden Protokolldateien auf dem Configuration Manager-Server, die für PXE-Aktionen spezifisch sind:

-   **Pxecontrol. log**, befindet sich im Configuration Manager-Installationsprotokoll Verzeichnis

-   **"SMSPXE. log**, befindet sich im Configuration Manager-Verwaltungspunkt (MP)-Protokollverzeichnis

Eine vollständige Liste der Protokolldateien, die Sie zur weiteren Problembehandlung bei der Installation von Configuration Manager verwenden können, finden Sie unter [Protokolldateien in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).
