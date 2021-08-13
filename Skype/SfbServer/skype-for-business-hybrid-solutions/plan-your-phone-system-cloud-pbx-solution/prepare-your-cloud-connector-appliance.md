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
description: Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und Verwendung mit Telefonsystem (Cloud PBX) vorbereiten.
ms.openlocfilehash: 58f9765f211a3961db8baf5929956feecf1eb4fd7e7744490cb21f1967dcb46f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340811"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Vorbereiten der Cloud Connector-Appliance

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und Verwendung mit Telefonsystem (Cloud PBX) vorbereiten.

In diesem Abschnitt wird beschrieben, wie Sie die Skype for Business Cloud Connector Edition Installationsdateien abrufen, Cloud Connector-Software installieren und Ihre Cloud Connector-Appliance für die Bereitstellung vorbereiten. Nachdem Sie alle Schritte in diesem Abschnitt abgeschlossen haben, können Sie Cloud Connector für einen einzelnen Standort oder mehrere Standorte bereitstellen. Wenn Sie über eine vorhandene Cloud Connector-Bereitstellung verfügen und noch kein Upgrade auf Cloud Connector, Version 2.1, durchgeführt haben, lesen Sie [das Upgrade auf eine neue Version von Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)

> [!NOTE]
> Microsoft unterstützt die aktuelle Version von Cloud Connector Edition, Version 2.1. Wenn Sie das automatische Update konfiguriert haben, wird Cloud Connector automatisch aktualisiert. Wenn Sie das manuelle Update konfiguriert haben, müssen Sie innerhalb von 60 Tagen nach der Veröffentlichung auf Version 2.1 aktualisieren. Microsoft unterstützt die vorherige Version 60 Tage nach der Veröffentlichung von 2.1, damit Sie Zeit zum Upgrade haben. 

> [!NOTE]
> Für Cloud Connector, Version 2.1 und höher, muss in der Host-Appliance .NET Framework 4.6.1 oder höher installiert sein. 

> [!IMPORTANT]
> Wenn Sie die Cmdlets zum Konfigurieren von Skype for Business Cloud Connector Edition ausführen, verwenden Sie für eine erfolgreiche Bereitstellung immer die gleiche Konsolensitzung wie die, in der Sie begonnen haben. Vermeiden Sie es, während der Bereitstellung und Konfiguration zu verschiedenen Sitzungen zu wechseln. 

> [!NOTE]
> Es gibt einige Schritte, die Sie nur für die erste Appliance in Ihrer Bereitstellung ausführen: Erstellen einer Freigabe für das Websiteverzeichnis, Herunterladen der Bits und Vorbereiten einer virtuellen Festplatte (VHDX)-Datei aus dem Windows Server-ISO-Image. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Laden Sie das installationsprogramm für Skype for Business Cloud Connector Edition herunter.

1. Laden Sie auf dem Hostserver, auf dem die Virtuellen Cloud Connector-Computer ausgeführt werden, die Installationsdateien herunter: [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) . 

    > [!IMPORTANT]
    > Der Hostserver muss während der Installation von Cloud Connector auf das Internet zugreifen können, da während der Installation zusätzliche Dateien heruntergeladen werden. 

2. Führen Sie das Installationsprogramm aus, und akzeptieren Sie die Standardwerte während der Installation.

3. Vergewissern Sie sich, dass die Installation erfolgreich abgeschlossen wurde.

## <a name="verify-the-installation-and-configure-the-environment"></a>Überprüfen der Installation und Konfigurieren der Umgebung

1. Öffnen Sie eine PowerShell-Konsole als Administrator, und vergewissern Sie sich, dass die Skype for Business Cloud Connector Edition Cmdlets mit dem folgenden Cmdlet verfügbar sind:

   ```powershell
   Get-Command *-Cc*
   ```

    Der Befehl sollte eine Liste der Cmdlets für Skype for Business Cloud Connector Edition zurückgeben.

2. Die VHDs-, SfBBits- und VersionInfo-Dateien werden im **Websiteverzeichnis** gespeichert.

    Den Speicherort des **Websiteverzeichnisses** finden Sie mit dem folgenden Cmdlet:

   ```powershell
   Get-CcSiteDirectory
   ```

    Der Befehl sollte einen Speicherort in Ihrem Dateisystem zurückgeben. Der Speicherort kann ein lokaler Ordner oder eine Dateifreigabe sein. Der Standardspeicherort für das **Websiteverzeichnis** lautet: %USERPROFILE%\CloudConnector\SiteRoot. Der Standardspeicherort sollte in eine Dateifreigabe in der ersten Appliance geändert werden, die an jedem Standort erstellt wurde.

    Der von Ihnen ausgewählte Speicherort muss folgendermaßen sein:

   - Erstellt in der ersten Appliance, die an jedem Standort erstellt wurde.

   - Ein freigegebener Ordner, auf den von den anderen Hostservern (Appliances) am selben Standort zugegriffen werden kann.

     Führen Sie das folgende Cmdlet aus, um das **Websiteverzeichnis** auf einen anderen Speicherort als den Standard festzulegen:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Wenn Sie hohe Verfügbarkeit (Ha) für den Standort bereitstellen, stellen Sie sicher, dass Sie das Cmdlet ausführen, um das **Standortverzeichnis** auf den gleichen Speicherort auf jedem Hostserver innerhalb des Standorts festzulegen.

    Wenn Sie sich anmelden und jede Appliance am Standort bereitstellen, stellen Sie sicher, dass Ihr aktuelles Anmeldekonto über den richtigen Zugriff auf das **Standortverzeichnis** verfügt.

3. Das **Appliance-Verzeichnis** ist das lokale Arbeitsstammverzeichnis für Skype for Business Cloud Connector Edition und der Speicherort, an dem externe Zertifikate, Instanzen und Protokolle gespeichert werden. Der Standardspeicherort lautet: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Führen Sie das folgende Cmdlet aus, um den Speicherort des **Appliance-Verzeichnisses** zu finden:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Führen Sie das folgende Cmdlet aus, um das **Appliance-Verzeichnis** auf einen anderen Speicherort als den Standard festzulegen:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    Das Appliance-Verzeichnis sollte auf einen lokalen Ordner in der Appliance festgelegt werden. Sie sollten das **Appliance-Verzeichnis** nur festlegen, bevor Sie mit der Skype for Business Cloud Connector Edition Bereitstellung beginnen. Wenn Sie es nach der Bereitstellung ändern, müssen Sie den Hostserver erneut bereitstellen.

    > [!IMPORTANT]
    > Der Pfad zum **Appliance-Verzeichnis** darf keine Leerzeichen enthalten.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Festlegen des Pfads für das externe Edgezertifikat

- Führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Dateinamens für das externe Edgezertifikat festzulegen. Beispiel: C:\certs\cce\ap.contoso.com.pfx. Das Zertifikat muss private Schlüssel enthalten.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Beachten Sie, dass der Parameter "-Target" für die Versionen 1.4.2 und höher spezifisch ist. 

    Geben Sie den vollständigen Pfad zum externen Zertifikat einschließlich des Dateinamens an. Das Zertifikat kann lokal oder auf einer Dateifreigabe gespeichert werden. Wenn das Zertifikat in einem freigegebenen Ordner gespeichert ist, muss der freigegebene Ordner in der ersten Appliance jedes Standorts erstellt werden und für andere Appliances, die zu demselben Standort gehören, zugänglich sein. Dieses Cmdlet kopiert das externe Zertifikat in das **Appliance-Verzeichnis.**

    > [!IMPORTANT]
    > **Wenn Sie auf Cloud Connector Version 1.4.2 oder höher aktualisiert haben,** stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel und die vollständige Zertifikatkette enthält, einschließlich des Stammzertifizierungsstellenzertifikats und der Zertifikate der Zwischenzertifizierungsstelle. **Wenn Sie noch NICHT auf Cloud Connector Version 1.4.2 aktualisiert haben,** stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel enthält. Dieses externe Zertifikat muss von einer Zertifizierungsstelle ausgestellt werden, die standardmäßig von Windows als vertrauenswürdig eingestuft wird.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Festlegen des Pfads für das externe PSTN-Gateway/SBC-Zertifikat

Wenn Sie TLS zwischen dem Vermittlungsserver und dem PSTN-Gateway/SBC verwenden, führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Dateinamens für das Gatewayzertifikat festzulegen. Beispiel: C:\certs\cce\sbc.contoso.com.cer. Das Zertifikat muss die Stammzertifizierungsstelle und die Zwischenkette für das dem Gateway zugewiesene Zertifikat enthalten:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Beachten Sie, dass der Parameter "-Target" für die Versionen 1.4.2 und höher spezifisch ist. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Erstellen virtueller Switches im Hyper-V-Manager

1. Öffnen Sie **den Virtuellen Switch-Manager des Hyper-V-Managers,**  >  und wählen Sie **"Neuer virtueller Switch-Manager" aus.**

2. Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der mit Ihrer internen Netzwerkdomäne verbunden ist:

    Wählen Sie **"Verwaltungsbetriebssystem zulassen" aus, um diesen Netzwerkadapter** für diesen virtuellen Switch freizugeben.

3. Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der an das Internet weitergeleitet wird:

    Deaktivieren Sie die Option **"Verwaltungsbetriebssystem zulassen", um diesen Netzwerkadapter** für diesen virtuellen Switch freizugeben.

4. Legen Sie den Namen des Switches fest, der Ihr Umkreisnetzwerk mit Ihrer internen Netzwerkdomäne **SfB CCE Corpnet Switch** verbindet.

    Legen Sie den Namen des Switches fest, der Ihr Umkreisnetzwerk mit dem Internet **SfB CCE Internet Switch** verbindet.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Aktualisieren der CloudConnector.ini-Konfigurationsdatei

Bereiten Sie die CloudConnector.ini-Datei mithilfe der Informationen vor, die Sie im Thema ["Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) ermitteln" im Thema ["Plan for Skype for Business Cloud Connector Edition"](plan-skype-for-business-cloud-connector-edition.md) gesammelt haben.

Führen Sie zum Aktualisieren der Datei zunächst das folgende Cmdlet aus, um die Beispielvorlage (CloudConnector.Sample.ini) abzurufen:

```powershell
Export-CcConfigurationSampleFile
```

Die Beispielvorlage wird im **Appliance-Verzeichnis** gespeichert.

Nachdem Sie sie mit den Werten für Ihre Umgebung aktualisiert haben, speichern Sie die Datei als CloudConnector.ini im **Appliance-Verzeichnis.** Sie können **Get-CcApplianceDirectory** ausführen, um den Pfad zum **Appliance-Verzeichnis** zu bestimmen.

Berücksichtigen Sie beim Aktualisieren der .ini Datei Folgendes:

> [!NOTE]
> Nicht alle Werte für die .ini-Datei werden in diesem Abschnitt behandelt, es werden hier nur die Werte behandelt, die eine besondere Überlegung haben. Eine vollständige Liste finden Sie im Abschnitt "Ermitteln von [Bereitstellungsparametern"](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im Thema ["Plan for Skype for Business Cloud Connector Edition".](plan-skype-for-business-cloud-connector-edition.md) Weitere Informationen dazu, welche Werte für zusätzliche Appliances oder neue Standorte geändert werden müssen, finden Sie unter ["Einzelner Standort mit hoher Verfügbarkeit (Ha) im Vergleich zu Bereitstellungen mit mehreren Standorten"](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) im Thema ["Bereitstellen mehrerer Standorte in Cloud Connector".](deploy-multiple-sites-in-cloud-connector.md) 

- **SiteName:** Der Standardwert ist **Site1**. Sie müssen ihn aktualisieren, bevor Sie Cloud Connector bereitstellen. Wenn Sie **"Register-CcAppliance"** ausführen, um eine Appliance an einem vorhandenen oder neuen Standort zu registrieren, verwendet das Cmdlet **"SiteName",** um zu bestimmen, welcher Standort registriert werden soll.

     Wenn Sie die Appliance an einem neuen Standort registrieren möchten, muss der Wert von **SiteName** eindeutig sein und sich von den vorhandenen Standorten unterscheiden. Wenn Sie die Appliance an einem vorhandenen Standort registrieren möchten, muss der Wert für **SiteName** in .ini Datei mit dem in ihrer Microsoft 365- oder Office 365 Organisationskonfiguration definierten Namen übereinstimmen. Wenn Sie eine Konfigurationsdatei von einem Standort zu einem anderen kopieren, stellen Sie sicher, dass Sie den Wert für **SiteName** für jeden Standort entsprechend aktualisieren.

- **ServerName:** Der Servername sollte nicht den Domänennamen enthalten und auf 15 Zeichen beschränkt sein.

- **HardwareType:** Wenn Sie den Wert nicht auf NULL festlegen oder belassen, wird der Standardwert **"Normal"** verwendet. Verwenden Sie **"Normal",** wenn Sie die größere Version von Cloud Connector bereitstellen möchten, um 500 gleichzeitige Anrufe pro Hostcomputer zu unterstützen, wie unter ["Plan for Skype for Business Cloud Connector Edition"](plan-skype-for-business-cloud-connector-edition.md)beschrieben. Verwenden Sie **"Minimum"** für eine kleinere Bereitstellung, die 50 gleichzeitige Anrufe unterstützt.

- Virtuelle Switches für **Internet/Corpnet/Management:** Fügen Sie den Namen der virtuellen Switches hinzu, die Sie erstellt haben. Behalten Sie für den virtuellen Switch für die Verwaltung den Standardwert bei. Das Bereitstellungsskript erstellt den virtuellen Verwaltungsschalter zu Beginn der Bereitstellung und löscht ihn, wenn die Bereitstellung abgeschlossen ist.

- **ManagementIPPrefix:** ManagementIPPrefix im Netzwerkabschnitt muss ein anderes Subnetz als andere interne IPs sein. Wie beispielsweise der Standardwert zeigt, ist ManagementIPPrefix 192.168.213.0, während AD IPAddress 192.168.0.238 ist.

    Die Bereitstellungsskripts erstellen einen Verwaltungsnetzwerkadapter auf jedem virtuellen Computer, weisen eine Verwaltungs-IP zu und verbinden sie mit einem virtuellen Switch für die Verwaltung. Dadurch kann der Hostserver eine Verbindung mit jedem virtuellen Computer herstellen und über dieses Verwaltungsnetzwerk verwalten. Der virtuelle Verwaltungsschalter wird gelöscht, wenn die Bereitstellung abgeschlossen ist.

- **Spezifische Konfigurationen für virtuelle Basiscomputer:** Einstellungen in diesem Abschnitt müssen für das Cmdlet **"Convert-CcIsoToVhdx"** konfiguriert werden.

    Während der Vorbereitung des Basis-VM-Images wird die Basis-VM mit dem internen Netzwerkschalter verbunden. Die folgenden Einstellungen sind wichtig, damit der virtuelle Computer auf das Internet zugreifen kann:

  - [Allgemein] BaseVMIP: die IP-Adresse des Unternehmensnetzwerks, die der Basis-VM zugewiesen werden soll.

  - [Netzwerk] CorpnetDefaultGateway: das Standardgateway, das der Basis-VM zugewiesen werden soll.

  - [Netzwerk] CorpnetDNSIPAddress: die DNS-IP-Adresse, die der Basis-VM zugewiesen werden soll.

  - [Netzwerk] WSUSServer: die IP-Adresse von Windows Server Update Service.

  - [Netzwerk] WSUSStatusServer: die IP-Adresse Windows Server Update Service-Statusservers.

  - [Netzwerk] EnableReferSupport: Dadurch wird definiert, ob die SIP REFER-Unterstützung für die Trunkkonfiguration für Ihre IP-/Nebenstellenanlage aktiviert oder deaktiviert ist.

- **Interne IPs:**

  - Stellen Sie sicher, dass die Subnetzmaske CorpnetIPPrefixLength korrekt ist.

  - Stellen Sie sicher, dass keine IP-Konflikte für diese internen IP-Adressen vorliegen.

- **Externe IPs:**

  - Für öffentliche MR-IP: Geben Sie entweder ExternalMRIPs für Nicht-NAT oder ExternalMRPublicIPs für NAT an.

  - ExternalSIPIPs und ExternalMRIPs können identisch sein.

  - Stellen Sie sicher, dass die Subnetzmaske InternetIPPrefixLength korrekt ist.

  - Stellen Sie sicher, dass keine IP-Konflikte für diese externen IPs vorhanden sind.

- **Gateways:**

  - Wenn Sie nur über ein Gateway verfügen, entfernen Sie den Abschnitt für das sekundäre Gateway. Wenn Sie über mehr als zwei Gateways verfügen, erstellen Sie zusätzliche Abschnitte, indem Sie das vorhandene kopieren und einfügen und dann aktualisieren.

  - Stellen Sie sicher, dass die IP-Adresse und der Port der Gateways korrekt sind.

  - Um HA auf PSTN-Gatewayebene zu unterstützen, belassen Sie das sekundäre Gateway, und fügen Sie alle zusätzlichen Gateways hinzu, die Sie verwenden werden. Sie können einen vorhandenen Eintrag kopieren und einfügen und ihn dann aktualisieren.

- Optional können Sie den LocalRoute-Wert aktualisieren, um ausgehende Anrufnummern einzuschränken.

## <a name="download-the-bits-to-the-site-directory"></a>Herunterladen der Bits in das Websiteverzeichnis

Führen Sie das folgende Cmdlet aus, um die Bits und Versionsinformationsdateien in das **Websiteverzeichnis** herunterzuladen:

```powershell
Start-CcDownload
```

> [!NOTE]
> Sie müssen diesen Schritt nur für die erste Appliance ausführen. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Vorbereiten des virtuellen Basisdatenträgers (VHDX) aus der heruntergeladenen ISO-Datei

In diesem Schritt wird eine VHDX-Datei (Virtual Hard Disk) aus dem Windows Server 2012 ISO-Image vorbereitet. Die VHDX wird verwendet, um während der Bereitstellung virtuelle Computer zu erstellen. Ein temporärer virtueller Computer (Basis-VM) wird erstellt, und Windows Server 2012 wird aus der ISO-Datei installiert. Nachdem der virtuelle Computer erstellt wurde, werden einige erforderliche Komponenten installiert, und das neueste Windows Update wird angewendet. Am Ende wird der virtuelle Basiscomputer generalisiert (sysprep) und bereinigt, sodass nur die generierte virtuelle Datenträgerdatei übrig bleibt.

> [!NOTE]
> Sie müssen diesen Schritt nur für die erste Appliance ausführen. 

Bevor Sie mit diesem Schritt fortfahren, stellen Sie sicher, dass der Corpnet-Switch erstellt wird. Vergewissern Sie sich außerdem, dass die folgenden Einstellungen in der datei CloudConnector.ini ordnungsgemäß konfiguriert sind:

- [Netzwerk] CorpnetSwitchName

- [Allgemein] BaseVMIP

- [Netzwerk] CorpnetIPPrefixLength

- [Netzwerk] CorpnetDefaultGateway

- [Netzwerk] CorpnetDNSIPAddress

Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um das ISO-Image in eine virtuelle Festplatte (VHD) zu konvertieren:

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Geben Sie den vollständigen Pfad einschließlich des Dateinamens zum ISO-Image an. Beispiel: C:\ISO\WindowsServer2012R2.iso.

Die erstellte VHD-Datei wird im **Ordner "Site Directory** \Bits\VHD" gespeichert. Sie können den Pfad zum **Websiteverzeichnis** abrufen, indem **Sie get-CcSiteDirectory** ausführen.

> [!IMPORTANT]
> Standardmäßig sind Proxyeinstellungen auf der Basis-VM nicht konfiguriert. Wenn ein Proxy in Ihrer Netzwerkumgebung erforderlich ist, um den virtuellen Computer über Windows Update zu aktualisieren, sollten Sie den Switch "-PauseBeforeUpdate" hinzufügen, wenn Sie "Convert-CcIsoToVhdx" ausführen. Das Skript wird vor Windows Update angehalten, und Sie haben die Möglichkeit, den Proxy auf dem virtuellen Computer manuell einzurichten. Nachdem der Proxy eingerichtet wurde und der virtuelle Computer auf das Internet zugreifen kann, können Sie das Skript fortsetzen, um die verbleibenden Schritte auszuführen. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Erstellen von VHDs für eine Bereitstellung mit mehreren Standorten

Dies ist ein optionaler Schritt, der nur für Bereitstellungen mit mehreren Standorten gilt.

Wenn Sie eine Bereitstellung mit mehreren Standorten bereitstellen, müssen Sie die ISO nicht für jeden Standort in eine VHD konvertieren. Sie können die für den ersten Standort erstellte VHDX auf den Hostserver für einen zweiten Standort kopieren.

 Kopieren Sie die Datei an den gleichen Dateispeicherort ( **Standortverzeichnis** \Bits\VHD-Ordner) und mit demselben Dateinamen auf dem Hostserver für eine zusätzliche Website.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Festlegen der PowerShell-Ausführungsrichtlinie auf "RemoteSigned"

Die bereitgestellten PowerShell-Skripts erfordern, dass die Ausführungsrichtlinie auf RemoteSigned festgelegt wird. Um die aktuelle Einstellung anzuzeigen, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie dann das folgende Cmdlet aus:

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

Das CceService-Konto wird während der Skype for Business Cloud Connector Edition Bereitstellung erstellt. Es führt den Cloud Connector-Verwaltungsdienst aus und erfordert die Berechtigung zum Deinstallieren des cloudconnector.msi. Sie müssen die Gruppenrichtlinieneinstellung auf dem Cloud Connector-Hostcomputer ändern, um anzugeben, dass die Benutzerregistrierung nicht entladen werden soll, wenn sich der Benutzer abmeldet. Führen Sie die folgenden Schritte aus:

### <a name="to-change-the-group-policy-setting"></a>So ändern Sie die Gruppenrichtlinieneinstellung

1. Öffnen Sie den **Gruppenrichtlinien-Editor,** indem Sie "gpedit.msc" ausführen.

2. Navigieren Sie im **Gruppenrichtlinien-Editor** zu administrativen Vorlagen > System > UserProfile > Entladen Sie die Benutzerregistrierung bei der Benutzeranmeldung nicht erzwungen. 

3. Legen Sie den Wert auf **"Enabled"** fest.

## <a name="set-up-your-microsoft-365-or-office-365-organization"></a>Einrichten Ihrer Microsoft 365 oder Office 365 Organisation

Eine Microsoft 365 oder Office 365 Organisation mit Skype for Business Online und Telefonsystem ist erforderlich. Stellen Sie sicher, dass Ihr Mandant eingerichtet und konfiguriert ist, bevor Sie versuchen, Cloud Connector zu verwenden.

Einige Microsoft 365- und Office 365 Einrichtungsschritte erfordern, dass Sie Mandanten-Remote-PowerShell (TRPS) verwenden, um Ihre Microsoft 365 oder Office 365 Organisation zu konfigurieren. **Diese sollte auf dem Hostserver installiert werden.** Sie können das Skype for Business Online-Modul für PowerShell von: [Skype for Business Online, Windows PowerShell-Modul](https://www.microsoft.com/download/details.aspx?id=39366)herunterladen.

Erstellen Sie ein dediziertes Skype for Business Administratorkonto für die Cloud Connector Online-Verwaltung, z. B. CceOnlineManagmentAdministrator. Dieses Konto wird von appliance verwendet, um Appliance hinzuzufügen oder zu entfernen, automatische Betriebssystemupdates zu aktivieren oder zu deaktivieren, automatische binäre Updates zu aktivieren oder zu deaktivieren. Legen Sie fest, dass das Kennwort für dieses Konto nie abläuft, sodass Sie es nicht jedes Mal ändern müssen, wenn es abläuft.