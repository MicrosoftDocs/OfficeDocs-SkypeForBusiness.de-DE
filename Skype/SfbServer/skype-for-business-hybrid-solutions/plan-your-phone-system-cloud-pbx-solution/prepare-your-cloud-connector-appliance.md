---
title: Vorbereiten der Cloud Connector-Appliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und Verwendung mit dem Telefonsystem (Cloud PBX) vorbereiten.
ms.openlocfilehash: 536e9b98520e4274e00d43d57224267f5b824dc9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092633"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Vorbereiten der Cloud Connector-Appliance

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und Verwendung mit dem Telefonsystem (Cloud PBX) vorbereiten.

In diesem Abschnitt wird beschrieben, wie Sie die Skype for Business Cloud Connector Edition-Installationsdateien erhalten, Cloud Connector-Software installieren und Ihre Cloud Connector-Appliance auf die Bereitstellung vorbereiten. Nachdem Sie alle Schritte in diesem Abschnitt abgeschlossen haben, können Sie Cloud Connector für einen einzelnen Standort oder mehrere Websites bereitstellen. Wenn Sie über eine vorhandene Cloud Connector-Bereitstellung verfügen und noch kein Upgrade auf Cloud Connector, Version 2.1, durchgeführt haben, lesen Sie Upgrade auf eine [neue Version von Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft unterstützt die aktuelle Version von Cloud Connector Edition, Version 2.1. Wenn Sie das automatische Update konfiguriert haben, wird Cloud Connector automatisch aktualisiert. Wenn Sie ein manuelles Update konfiguriert haben, müssen Sie innerhalb von 60 Tagen nach der Veröffentlichung auf Version 2.1 aktualisieren. Microsoft unterstützt die vorherige Version für 60 Tage nach der Version von 2.1, um Ihnen Zeit zum Upgrade zu geben. 

> [!NOTE]
> Für Cloud Connector, Version 2.1 und höher, muss die Host appliance .NET Framework 4.6.1 oder höher installiert sein. 

> [!IMPORTANT]
> Wenn Sie die Cmdlets zum Konfigurieren von Skype for Business Cloud Connector Edition ausführen, verwenden Sie für eine erfolgreiche Bereitstellung immer dieselbe Konsolensitzung wie die, in der Sie begonnen haben. Vermeiden Sie, während der Bereitstellung und Konfiguration zu verschiedenen Sitzungen zu wechseln. 

> [!NOTE]
> Es gibt einige Schritte, die Sie nur für die erste Appliance in Ihrer Bereitstellung ausführen: Erstellen einer Freigabe für das Standortverzeichnis, Herunterladen der Bits und Vorbereiten einer Virtuellen Festplatte (VHDX)-Datei aus dem Windows Server-ISO-Image. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Herunterladen des Skype for Business Cloud Connector Edition-Installers

1. Laden Sie auf dem Hostserver, auf dem die VMs des CloudConnector ausgeführt werden, die Installationsdateien herunter: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 

    > [!IMPORTANT]
    > Der Hostserver muss während der Installation von Cloud Connector auf das Internet zugreifen können, da während der Installation zusätzliche Dateien heruntergeladen werden. 

2. Führen Sie das Installationsprogramm aus, und akzeptieren Sie die Standardwerte während der Installation.

3. Vergewissern Sie sich, dass die Installation erfolgreich abgeschlossen wurde.

## <a name="verify-the-installation-and-configure-the-environment"></a>Überprüfen der Installation und Konfigurieren der Umgebung

1. Öffnen Sie eine PowerShell-Konsole als Administrator, und vergewissern Sie sich, dass die Skype for Business Cloud Connector Edition-Cmdlets mit dem folgenden Cmdlet verfügbar sind:

   ```powershell
   Get-Command *-Cc*
   ```

    Der Befehl sollte eine Liste der Cmdlets für Skype for Business Cloud Connector Edition zurückgeben.

2. Die Dateien VHDs, SfBBits und VersionInfo werden im **Websiteverzeichnis gespeichert.**

    Sie finden den Speicherort des **Websiteverzeichnisses** mit dem folgenden Cmdlet:

   ```powershell
   Get-CcSiteDirectory
   ```

    Der Befehl sollte einen Speicherort im Dateisystem zurückgeben. Der Speicherort kann ein lokaler Ordner oder eine Dateifreigabe sein. Der Standardspeicherort für **das Standortverzeichnis** ist: %USERPROFILE%\CloudConnector\SiteRoot. Der Standardspeicherort sollte in eine Dateifreigabe für die erste Appliance geändert werden, die an jedem Standort erstellt wurde.

    Der ausgewählte Speicherort muss sein:

   - Erstellt auf der ersten Appliance, die an jedem Standort erstellt wurde.

   - Ein freigegebener Ordner, auf den die anderen Hostserver (Appliances) am gleichen Standort zugreifen können.

     Führen Sie das folgende **Cmdlet** aus, um das Standortverzeichnis auf einen anderen Speicherort als den Standardspeicherort zu setzen:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Wenn Sie hohe Verfügbarkeit (High Availability, HA) für den Standort bereitstellen,  stellen Sie sicher, dass Sie das Cmdlet ausführen, um das Standortverzeichnis auf jedem Hostserver innerhalb des Standorts auf denselben Speicherort zu setzen.

    Stellen Sie beim Anmelden und Bereitstellen jeder Appliance am Standort sicher, dass Ihr aktuelles Anmeldekonto über den richtigen Zugriff auf das **Websiteverzeichnis verfügt.**

3. Das **Appliance-Verzeichnis** ist das lokale Arbeitsstammverzeichnis für Skype for Business Cloud Connector Edition und der Speicherort, an dem externe Zertifikate, Instanzen und Protokolle gespeichert werden. Der Standardspeicherort ist: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Führen Sie das folgende Cmdlet aus, um den Speicherort des **Appliance-Verzeichnisses** zu finden:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Führen Sie das folgende **Cmdlet** aus, um das Appliance Directory auf einen anderen Speicherort als den Standardspeicherort zu setzen:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    Das Appliance-Verzeichnis sollte auf einen lokalen Ordner auf der Appliance festgelegt werden. Sie sollten das Appliance **Directory nur festlegen,** bevor Sie die Skype for Business Cloud Connector Edition-Bereitstellung starten. Wenn Sie dies nach der Bereitstellung ändern, müssen Sie den Hostserver erneut bereitstellen.

    > [!IMPORTANT]
    > Der Pfad zum **Appliance Directory** darf keine Leerzeichen enthalten.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Festlegen des Pfads für das externe Edgezertifikat

- Führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Dateinamens auf das externe Edgezertifikat zu setzen. Beispiel: C:\certs\cce\ap.contoso.com.pfx. Das Zertifikat muss private Schlüssel enthalten.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Beachten Sie, dass der -Target-Parameter für die Versionen 1.4.2 und höher spezifisch ist. 

    Geben Sie den vollständigen Pfad zum externen Zertifikat an, einschließlich des Dateinamens. Das Zertifikat kann lokal oder in einer Dateifreigabe gespeichert werden. Wenn das Zertifikat in einem freigegebenen Ordner gespeichert ist, muss der freigegebene Ordner auf der ersten Appliance jedes Standorts erstellt werden und von anderen Appliances, die zum gleichen Standort gehören, zugänglich sein. Dieses Cmdlet kopiert das externe Zertifikat in das **Appliance Directory**.

    > [!IMPORTANT]
    > Wenn Sie auf **Cloud Connector Version 1.4.2** oder höher aktualisiert haben, stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel und die vollständige Zertifikatkette enthält, einschließlich des Stammzertifizierungsstellenzertifikats und der Zwischenzertifizierungsstellenzertifikate. **Wenn Sie noch nicht auf Cloud Connector Version 1.4.2** aktualisiert haben, stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel enthält. Dieses externe Zertifikat muss von einer Zertifizierungsstelle ausgestellt werden, die standardmäßig von Windows als vertrauenswürdig eingestuft wird.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Festlegen des Pfads für das externe PSTN-Gateway/SBC-Zertifikat

Wenn Sie TLS zwischen dem Vermittlungsserver und dem PSTN-Gateway/SBC verwenden, führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Dateinamens zum Gatewayzertifikat zu legen. Beispiel: C:\certs\cce\sbc.contoso.com.cer. Das Zertifikat muss die Stammzertifizierungsstelle und die Zwischenkette für das dem Gateway zugewiesene Zertifikat enthalten:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Beachten Sie, dass der -Target-Parameter für die Versionen 1.4.2 und höher spezifisch ist. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Erstellen virtueller Switches im Hyper-V-Manager

1. Öffnen **Sie Hyper-V Manager** Virtual Switch  >  **Manager,** und wählen Sie New Virtual Switch Manager **aus.**

2. Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der mit Ihrer internen Netzwerkdomäne verbunden ist:

    Wählen **Sie Verwaltungsbetriebssystem zulassen aus, um diesen Netzwerkadapter für** diesen virtuellen Switch zu verwenden.

3. Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der an das Internet geroutet wird:

    De-select **Allow management operating system to share this network adapter** for this virtual switch.

4. Legen Sie den Namen des Switches fest, der Ihr Umkreisnetzwerk mit Ihrer internen Netzwerkdomäne **SfB CCE Corpnet Switch verbindet.**

    Legen Sie den Namen des Switches fest, der Ihr Umkreisnetzwerk mit dem Internet **SfB CCE Internet Switch verbindet.**

## <a name="update-the-cloudconnectorini-configuration-file"></a>Aktualisieren der CloudConnector.ini Konfigurationsdatei

Bereiten Sie die CloudConnector.ini mithilfe der Informationen vor, die Sie unter [Bestimmen](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) von Bereitstellungsparametern im [Thema Plan for Skype for Business Cloud Connector Edition gesammelt](plan-skype-for-business-cloud-connector-edition.md) haben.

Führen Sie zum Aktualisieren der Datei zunächst das folgende Cmdlet aus, um die Beispielvorlage (CloudConnector.Sample.ini):

```powershell
Export-CcConfigurationSampleFile
```

Die Beispielvorlage wird im Appliance **Directory gespeichert.**

Nachdem Sie sie mit den Werten für Ihre Umgebung aktualisiert haben, speichern Sie die Datei CloudConnector.ini im **Appliance Directory**. Sie können **Get-CcApplianceDirectory ausführen,** um den Pfad zum **Appliance Directory zu bestimmen.**

Berücksichtigen Sie beim Aktualisieren der INI-Datei Folgendes:

> [!NOTE]
> In diesem Abschnitt werden nicht alle Werte für die Ini-Datei behandelt, sondern nur die Werte, die besondere Beachtung finden. Eine vollständige Liste finden Sie im Abschnitt Bestimmen von [Bereitstellungsparametern](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im [Thema Plan for Skype for Business Cloud Connector Edition.](plan-skype-for-business-cloud-connector-edition.md) Weitere Informationen dazu, welche Werte für zusätzliche Appliances oder neue Standorte geändert werden müssen, finden Sie unter [Single site with High Availability (HA)](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) im Vergleich zu Bereitstellungen mit mehreren Standorten im Thema Deploy multiple sites in Cloud [Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** Der Standardwert ist **Site1**. Sie müssen es vor der Bereitstellung von Cloud Connector aktualisieren, da das Cmdlet beim Ausführen von **Register-CcAppliance** zum Registrieren einer Appliance an einem vorhandenen oder neuen Standort **SiteName** verwendet, um zu bestimmen, welcher Standort registriert werden soll.

     Wenn Sie die Appliance an einem neuen Standort registrieren möchten, muss der Wert von **SiteName** eindeutig sein und sich von den vorhandenen Websites unterscheiden. Wenn Sie die Appliance bei einem vorhandenen Standort registrieren möchten, muss der Wert für **SiteName** in der Ini-Datei mit dem namen übereinstimmen, der in Ihrer Microsoft 365- oder Office 365-Organisationskonfiguration definiert ist. Wenn Sie eine Konfigurationsdatei von einem Standort in einen anderen kopieren, müssen Sie den Wert für **SiteName** für jede Website entsprechend aktualisieren.

- **ServerName:** Der Servername sollte den Domänennamen nicht enthalten und auf 15 Zeichen beschränkt sein.

- **HardwareType:** Wenn Sie den Wert nicht auf Null festlegen oder lassen, wird der Standardwert **Normal** verwendet. Verwenden **Sie Normal,** wenn Sie die größere Version von Cloud Connector bereitstellen möchten, um 500 gleichzeitige Anrufe pro Hostcomputer zu unterstützen, wie unter [Plan for Skype for Business Cloud Connector Edition beschrieben.](plan-skype-for-business-cloud-connector-edition.md) Verwenden **Sie Minimum** für eine kleinere Bereitstellung, die 50 gleichzeitige Anrufe unterstützt.

- **Virtuelle Internet-/Corpnet-/Management-Switches:**: Fügen Sie den Namen der virtuellen Switches hinzu, die Sie erstellt haben. Lassen Sie für den virtuellen Verwaltungsschalter den Standardwert. Das Bereitstellungsskript erstellt den virtuellen Verwaltungsschalter zu Beginn der Bereitstellung und löscht ihn, wenn die Bereitstellung abgeschlossen ist.

- **ManagementIPPrefix:** ManagementIPPrefix im Abschnitt Netzwerk muss ein anderes Subnetz als andere interne IPs sein. Wie der Standardwert zeigt, ist ManagementIPPrefix beispielsweise 192.168.213.0, während AD IPAddress den Wert 192.168.0.238 hat.

    Die Bereitstellungsskripts erstellen auf jedem virtuellen Computer einen Verwaltungsnetzwerkadapter, weisen eine Verwaltungs-IP zu und verbinden ihn mit einem virtuellen Verwaltungsschalter. Dadurch kann der Hostserver über dieses Verwaltungsnetzwerk eine Verbindung mit jedem virtuellen Computer herstellen und diese verwalten. Der virtuelle Verwaltungsschalter wird nach Abschluss der Bereitstellung gelöscht.

- **Basis-VM-spezifische Konfigurationen:** Die Einstellungen in diesem Abschnitt müssen für das **Cmdlet Convert-CcIsoToVhdx** konfiguriert werden.

    Während der Vorbereitung des Basis-VM-Images wird der Basis-VM mit dem internen Netzwerkschalter verbunden. Die folgenden Einstellungen sind wichtig, damit der virtuelle Computer auf das Internet zugreifen kann:

  - [Common] BaseVMIP: die corpnet-IP-Adresse, die dem Basis-VM zugewiesen werden soll.

  - [Netzwerk] CorpnetDefaultGateway: das Standardgateway, das dem Basis-VM zugewiesen werden soll.

  - [Netzwerk] CorpnetDNSIPAddress: die DNS-IP-Adresse, die dem Basis-VM zugewiesen werden soll.

  - [Netzwerk] WSUSServer: die IP-Adresse des Windows Server Update Service.

  - [Netzwerk] WSUSStatusServer: die IP-Adresse des Windows Server Update Service-Statusservers.

  - [Netzwerk] EnableReferSupport: Dadurch wird definiert, ob die SIP -REFER-Unterstützung für die Trunkkonfiguration für Ihre IP/PBX aktiviert oder deaktiviert ist.

- **Interne IPs:**

  - Stellen Sie sicher, dass die Subnetzmaske CorpnetIPPrefixLength richtig ist.

  - Stellen Sie sicher, dass für diese internen IPs keine IP-Konflikte auftreten.

- **Externe IPs:**

  - Für öffentliche MR-IP: Geben Sie entweder ExternalMRIPs für Nicht-NAT oder ExternalMRPublicIPs für NAT an.

  - ExternalSIPIPs und ExternalMRIPs können identisch sein.

  - Stellen Sie sicher, dass die Subnetzmaske InternetIPPrefixLength richtig ist.

  - Stellen Sie sicher, dass für diese externen IPs keine IP-Konflikte auftreten.

- **Gateways:**

  - Wenn Sie nur über ein Gateway verfügen, entfernen Sie den Abschnitt für das sekundäre Gateway. Wenn Sie über mehr als zwei Gateways verfügen, erstellen Sie zusätzliche Abschnitte, indem Sie das vorhandene kopieren und einfügen und dann aktualisieren.

  - Stellen Sie sicher, dass die IP-Adresse und der Port der Gateways korrekt sind.

  - Verlassen Sie das sekundäre Gateway, und fügen Sie alle zusätzlichen Gateways hinzu, die Sie verwenden werden, um die HA auf PSTN-Gatewayebene zu unterstützen. Sie können einen vorhandenen Eintrag kopieren und einfügen und dann aktualisieren.

- Optional können Sie den LocalRoute-Wert aktualisieren, um ausgehende Telefonnummern einzuschränken.

## <a name="download-the-bits-to-the-site-directory"></a>Herunterladen der Bits in das Websiteverzeichnis

Führen Sie das folgende Cmdlet aus, um die Bits- und Versionsinformationsdateien in das **Websiteverzeichnis herunterzuladen:**

```powershell
Start-CcDownload
```

> [!NOTE]
> Sie müssen diesen Schritt nur für die erste Appliance ausführen. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Vorbereiten des virtuellen Basisdatenträgers (VHDX) aus der heruntergeladenen ISO-Datei

In diesem Schritt wird eine Virtuelle Festplatte (VHDX) aus dem Windows Server 2012 vorbereitet. Der VHDX wird zum Erstellen virtueller Computer während der Bereitstellung verwendet. Ein temporärer virtueller Computer (Basis-VM) wird erstellt, und Windows Server 2012 wird aus der ISO-Datei installiert. Nachdem der virtuelle Computer erstellt wurde, werden einige erforderliche Komponenten installiert, und das neueste Windows-Update wird angewendet. Am Ende wird die Basis-VM generalisiert (sysprep) und bereinigt, und es bleibt nur die generierte virtuelle Datenträgerdatei.

> [!NOTE]
> Sie müssen diesen Schritt nur für die erste Appliance ausführen. 

Bevor Sie mit diesem Schritt fortfahren, stellen Sie sicher, dass der Switch corpnet erstellt wird. Vergewissern Sie sich außerdem, dass die folgenden Einstellungen in der Datei CloudConnector.ini sind:

- [Netzwerk] CorpnetSwitchName

- [Common] BaseVMIP

- [Netzwerk] CorpnetIPPrefixLength

- [Netzwerk] CorpnetDefaultGateway

- [Netzwerk] CorpnetDNSIPAddress

Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um das ISO-Image auf eine virtuelle Festplatte (VHD) zu konvertieren:

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Geben Sie den vollständigen Pfad einschließlich des Dateinamens zum ISO-Image an. Beispiel: C:\ISO\WindowsServer2012R2.iso.

Die erstellte VHD-Datei wird im Ordner **Websiteverzeichnis** \Bits\VHD gespeichert. Sie können den Pfad zum **Standortverzeichnis durch** Ausführen von **Get-CcSiteDirectory erhalten.**

> [!IMPORTANT]
> Proxyeinstellungen sind standardmäßig nicht auf der Basis-VM konfiguriert. Wenn in Ihrer Netzwerkumgebung ein Proxy zum Aktualisieren des virtuellen Computers über Windows Update erforderlich ist, sollten Sie die Option -PauseBeforeUpdate hinzufügen, wenn Sie "Convert-CcIsoToVhdx" ausführen. Das Skript hält vor Windows Update an, und Sie haben die Möglichkeit, den Proxy auf dem virtuellen Computer manuell einrichten. Nachdem der Proxy eingerichtet wurde und der virtuelle Computer auf das Internet zugreifen kann, können Sie das Skript fortsetzen, um die verbleibenden Schritte auszuführen. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Erstellen von VHDs für eine Bereitstellung mit mehreren Standorten

Dies ist ein optionaler Schritt, der nur für Bereitstellungen mit mehreren Standort gilt.

Wenn Sie eine Bereitstellung mit mehreren Standort bereitstellen, müssen Sie die ISO nicht für jeden Standort in eine VHD konvertieren. Sie können die für den ersten Standort erstellte VHDX auf den Hostserver für einen zweiten Standort kopieren.

 Kopieren Sie die Datei an denselben Dateispeicherort ( **Ordner Websiteverzeichnis** \Bits\VHD) und mit demselben Dateinamen auf dem Hostserver für einen zusätzlichen Standort.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Festlegen der PowerShell-Ausführungsrichtlinie auf RemoteSigned

Für die bereitgestellten PowerShell-Skripts muss die Ausführungsrichtlinie auf RemoteSigned festgelegt werden. Um die aktuelle Einstellung zu sehen, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie dann das folgende Cmdlet aus:

```powershell
Get-ExecutionPolicy
```

Wenn sie nicht auf "RemoteSigned" festgelegt ist, führen Sie das folgende Cmdlet aus, um es zu ändern:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Ändern der lokalen Gruppenrichtlinie auf dem Hostcomputer (Versionen 1.4.1 und früher)

> [!NOTE]
> Diese Aufgabe ist für Cloud Connector, Version 1.4.2 und höher, nicht erforderlich. 

Das CceService-Konto wird während der Skype for Business Cloud Connector Edition-Bereitstellung erstellt. Er führt den Cloud Connector Management Service aus und erfordert die Berechtigung zum Deinstallieren cloudconnector.msi. Sie müssen die Gruppenrichtlinieneinstellung auf dem Cloud Connector-Hostcomputer ändern, um anzugeben, dass die Benutzerregistrierung nicht entladen werden soll, wenn sich der Benutzer abmeldet. Führen Sie die folgenden Schritte aus:

### <a name="to-change-the-group-policy-setting"></a>So ändern Sie die Gruppenrichtlinieneinstellung

1. Öffnen Sie **den Gruppenrichtlinien-Editor,** indem Sie gpedit.msc ausführen.

2. Navigieren Sie **im** Gruppenrichtlinien-Editor zu Administrative Vorlagen > System > UserProfile > Laden Sie die Benutzerregistrierung bei der Benutzeranmeldung nicht erzwingen. 

3. Legen Sie den Wert auf **Enabled .**

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Einrichten Ihrer Microsoft 365- oder Office 365-Organisation

Eine Microsoft 365- oder Office 365-Organisation mit Skype for Business Online und Telefonsystem ist erforderlich. Stellen Sie sicher, dass Ihr Mandant eingerichtet und konfiguriert ist, bevor Sie versuchen, Cloud Connector zu verwenden.

Bei einigen Microsoft 365- und Office 365-Setupschritten müssen Sie Die Mandanten-Remote-PowerShell (TRPS) verwenden, um Ihre Microsoft 365- oder Office 365-Organisation zu konfigurieren. **Dies sollte auf dem Hostserver installiert werden.** Sie können das Skype for Business Online-Modul für PowerShell unter: [Skype for Business Online, Windows PowerShell herunterladen.](https://www.microsoft.com/download/details.aspx?id=39366)

Erstellen Sie ein dediziertes Skype for Business-Administratorkonto für die Cloud Connector-Onlineverwaltung, z. B. CceOnlineManagmentAdministrator. Dieses Konto wird von appliance verwendet, um Appliance hinzuzufügen oder zu entfernen, automatische Betriebssystemaktualisierungen zu aktivieren oder zu deaktivieren, automatische binäre Updates zu aktivieren oder zu deaktivieren. Legen Sie das Kennwort für dieses Konto so fest, dass es nie abläuft, sodass Sie es nicht jedes Mal ändern müssen, wenn es abläuft.