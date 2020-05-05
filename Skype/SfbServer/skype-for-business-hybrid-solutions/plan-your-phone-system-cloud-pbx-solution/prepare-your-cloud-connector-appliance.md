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
description: Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und die Verwendung mit dem Telefon System in Office 365 (Cloud PBX) vorbereiten.
ms.openlocfilehash: 21943dfd8b86bfeabb4cbd28b501b80a3f2b5c45
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779241"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Vorbereiten der Cloud Connector-Appliance

Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und die Verwendung mit dem Telefon System in Office 365 (Cloud PBX) vorbereiten.

In diesem Abschnitt wird beschrieben, wie Sie die Skype for Business Cloud Connector Edition-Installationsdateien abrufen, die Cloud Connector-Software installieren und Ihre Cloud Connector-Appliance für die Bereitstellung vorbereiten. Nachdem Sie alle Schritte in diesem Abschnitt abgeschlossen haben, sind Sie bereit, Cloud Connector für eine einzelne Website oder mehrere Standorte bereitzustellen. Wenn Sie über eine vorhandene Cloud Connector-Bereitstellung verfügen und noch nicht auf Cloud Connector, Version 2,1, aktualisiert haben, lesen Sie [Upgrade auf eine neue Version von Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft unterstützt die aktuelle Version von Cloud Connector Edition, Version 2,1. Wenn Sie die automatische Aktualisierung konfiguriert haben, wird Cloud Connector automatisch aktualisiert. Wenn Sie die manuelle Aktualisierung konfiguriert haben, müssen Sie innerhalb von 60 Tagen nach der Veröffentlichung auf Version 2,1 aktualisieren. Microsoft unterstützt die vorherige Version 60 Tage nach der Veröffentlichung von 2,1, damit Sie Zeit zum Upgrade erhalten. 

> [!NOTE]
> Für Cloud Connector, Version 2,1 und höher, muss die Host-Appliance .NET Framework 4.6.1 oder höher installiert haben. 

> [!IMPORTANT]
> Verwenden Sie für eine erfolgreiche Bereitstellung beim Ausführen der Cmdlets zum Konfigurieren Skype for Business Cloud Connector Edition immer dieselbe Konsolensitzung wie die, die Sie in gestartet haben. Vermeiden Sie während der Bereitstellung und Konfiguration das Wechseln zu anderen Sitzungen. 

> [!NOTE]
> Es gibt einige Schritte, die Sie nur für die erste Appliance in Ihrer Bereitstellung ausführen: Erstellen einer Freigabe für das Websiteverzeichnis, Herunterladen der Bits und Vorbereiten einer Virtual Hard Disk (VHDX)-Datei aus dem Windows Server-ISO-Image. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Laden Sie den Skype for Business Cloud Connector Edition-Installer herunter.

1. Laden Sie auf dem Hostserver, auf dem die Cloud Connector-VMS ausgeführt werden sollen [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller), die Installationsdateien herunter:. 

    > [!IMPORTANT]
    > Der Hostserver muss während der Installation von Cloud Connector auf das Internet zugreifen können, da während der Installation zusätzliche Dateien heruntergeladen werden. 

2. Führen Sie das Installationsprogramm aus, und übernehmen Sie die Standardwerte während der Installation.

3. Bestätigen Sie, dass die Installation erfolgreich abgeschlossen wurde.

## <a name="verify-the-installation-and-configure-the-environment"></a>Überprüfen der Installation und Konfigurieren der Umgebung

1. Öffnen Sie eine PowerShell-Konsole als Administrator, und vergewissern Sie sich, dass die Skype for Business Cloud Connector Edition-Cmdlets mit dem folgenden Cmdlet verfügbar sind:

   ```powershell
   Get-Command *-Cc*
   ```

    Der Befehl sollte eine Liste der Cmdlets für Skype for Business Cloud Connector Edition zurückgeben.

2. Die VHD-, SfBBits-und VERSIONINFO-Dateien werden im **Websiteverzeichnis**gespeichert.

    Sie können den Speicherort des **Websiteverzeichnisses** mit dem folgenden Cmdlet ermitteln:

   ```powershell
   Get-CcSiteDirectory
   ```

    Der Befehl sollte einen Speicherort in Ihrem Dateisystem zurückgeben. Bei dem Speicherort kann es sich um einen lokalen Ordner oder eine Dateifreigabe handeln. Der Standardspeicherort für das **Websiteverzeichnis** lautet:%USERPROFILE%\CloudConnector\SiteRoot. Der Standardspeicherort sollte in eine Dateifreigabe auf der ersten Appliance geändert werden, die an jedem Standort erstellt wurde.

    Der Speicherort, den Sie auswählen, muss wie folgt lauten:

   - Erstellt auf der ersten Appliance, die an jedem Standort erstellt wurde.

   - Ein freigegebener Ordner, auf den andere Hostserver (Appliances) am gleichen Standort zugreifen können.

     Um das **Websiteverzeichnis** auf einen anderen Speicherort als den Standardwert festzulegen, führen Sie das folgende Cmdlet aus:

   ```powershell
   Set-CcSiteDirectory <UNC File path>
   ```

    Wenn Sie hohe Verfügbarkeit für die Website bereitstellen, stellen Sie sicher, dass Sie das-Cmdlet ausführen, um das **Websiteverzeichnis** auf jedem Hostserver innerhalb des Standorts auf denselben Speicherort festzulegen.

    Wenn Sie sich anmelden und jede Appliance am Standort bereitstellen, stellen Sie sicher, dass Ihr aktuelles Anmeldekonto über den richtigen Zugriff auf das **Websiteverzeichnis**verfügt.

3. Das **Appliance-Verzeichnis** ist das lokale Arbeits Stammverzeichnis für Skype for Business Cloud Connector Edition und der Speicherort, an dem externe Zertifikate, Instanzen und Protokolle gespeichert werden. Der Standardspeicherort ist:%USERPROFILE%\CloudConnector\ApplianceRoot.

    Führen Sie das folgende Cmdlet aus, um den Speicherort des **Appliance-Verzeichnisses**zu ermitteln:

   ```powershell
   Get-CcApplianceDirectory
   ```

    Um das **Appliance-Verzeichnis** auf einen anderen Speicherort als den Standardwert festzulegen, führen Sie das folgende Cmdlet aus:

   ```powershell
   Set-CcApplianceDirectory <File path>
   ```

    Das Appliance-Verzeichnis sollte auf einen lokalen Ordner der Appliance festgelegt sein. Legen Sie das Appliance- **Verzeichnis** nur vor dem Start der Skype for Business Cloud Connector Edition-Bereitstellung fest. Wenn Sie Sie nach der Bereitstellung ändern, müssen Sie den Hostserver erneut bereitstellen.

    > [!IMPORTANT]
    > Der Pfad zum **Appliance-Verzeichnis** darf keine Leerzeichen enthalten.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Festlegen des Pfads für das Zertifikat für externe Edges

- Führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Datei namens auf das externe Edge-Zertifikat festzulegen. Beispiel: C:\certs\cce\ap.contoso.com.pfx. Das Zertifikat muss private Schlüssel enthalten.

  ```powershell
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Beachten Sie, dass der-target-Parameter für die Versionen 1.4.2 und höher spezifisch ist. 

    Geben Sie den vollständigen Pfad zum externen Zertifikat an, einschließlich des Datei namens. Das Zertifikat kann lokal oder in einer Dateifreigabe gespeichert werden. Wenn das Zertifikat in einem freigegebenen Ordner gespeichert ist, muss der freigegebene Ordner auf der ersten Appliance jedes Standorts erstellt werden und von anderen Appliances, die demselben Standort angehören, zugänglich sein. Dieses Cmdlet kopiert das externe Zertifikat in das **Appliance-Verzeichnis**.

    > [!IMPORTANT]
    > **Wenn Sie auf Cloud Connector, Version 1.4.2 oder höher, aktualisiert haben**, stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel und die vollständige Zertifikatkette einschließlich des Stammzertifizierungsstellen-Zertifikats und der Zwischenzertifizierungsstellen Zertifikate enthält. **Wenn Sie noch nicht auf Cloud Connector, Version 1.4.2, aktualisiert haben**, stellen Sie sicher, dass das vorbereitete externe Zertifikat private Schlüssel enthält. Dieses externe Zertifikat muss von einer Zertifizierungsstelle ausgestellt werden, die standardmäßig von Windows als vertrauenswürdig eingestuft wird.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Festlegen des Pfads für das externe PSTN-Gateway/SBC-Zertifikat

Wenn Sie TLS zwischen dem Vermittlungsserver und dem PSTN-Gateway/SBC verwenden, führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Datei namens auf das Gateway-Zertifikat festzulegen. Beispiel: C:\certs\cce\sbc.contoso.com.cer. Das Zertifikat muss die Stammzertifizierungsstelle und die zwischen Kette für das dem Gateway zugewiesene Zertifikat enthalten:

```powershell
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Beachten Sie, dass der-target-Parameter für die Versionen 1.4.2 und höher spezifisch ist. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Erstellen virtueller Switches in Hyper-V-Manager

1. Öffnen Sie den**Virtual Switch Manager**für **Hyper-V Manager** > , und wählen Sie **neuer virtueller Switch-Manager**aus.

2. Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der mit ihrer internen Netzwerkdomäne verbunden ist:

    Wählen Sie **Verwaltung Betriebssystem zulassen aus, um diesen Netzwerkadapter** für diesen virtuellen Switch freizugeben.

3. Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der an das Internet weitergeleitet wird:

    Deaktivieren Sie die Option Verwaltungsbetriebssystem für diesen virtuellen Switch **freigeben, um diesen Netzwerkadapter freizugeben** .

4. Legen Sie den Namen des Switches, der Ihr Umkreisnetzwerk mit ihrer internen Netzwerkdomäne verbindet, mit dem **SFB CCE Corpnet Switch**fest.

    Legen Sie den Namen des Switches fest, der Ihr Umkreisnetzwerk mit dem Internet- **Switch des SFB CCE**verbindet.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Aktualisieren der Konfigurationsdatei "cloudconnector. ini

Bereiten Sie die Datei "cloudconnector. ini mit den Informationen vor, die Sie unter [bestimmen der Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im Thema [Planen für Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) gesammelt haben.

Um die Datei zu aktualisieren, führen Sie zuerst das folgende Cmdlet aus, um die Beispielvorlage ("cloudconnector. Sample. ini) abzurufen:

```powershell
Export-CcConfigurationSampleFile
```

Die Beispielvorlage wird im Appliance- **Verzeichnis**gespeichert.

Nachdem Sie es mit den Werten für Ihre Umgebung aktualisiert haben, speichern Sie die Datei als "cloudconnector. ini im **Appliance-Verzeichnis**. Sie können **Get-CcApplianceDirectory** ausführen, um den Pfad zum **Appliance-Verzeichnis**zu ermitteln.

Berücksichtigen Sie beim Aktualisieren der INI-Datei Folgendes:

> [!NOTE]
> Nicht alle Werte für die. ini-Datei werden in diesem Abschnitt behandelt, sondern nur diejenigen, die eine besondere Überlegung haben. Eine vollständige Liste finden Sie im Abschnitt [bestimmen der Bereitstellungsparameter](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im Thema [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) . Weitere Informationen darüber, welche Werte für zusätzliche Appliances oder neue Websites geändert werden müssen, finden Sie unter [Single Site with High Availability (ha) im Vergleich zu Multi-Site-Bereitstellungen](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) im Thema [deploy multiple Sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **Sitename:** Der Standardwert ist **site1**. Sie müssen es vor der Bereitstellung von Cloud Connector aktualisieren, da das Cmdlet beim Ausführen von **Register-ccappliance "** zum Registrieren einer Appliance auf einem vorhandenen oder neuen Standort den Standort Sitename **verwendet, um zu** ermitteln, welche Website registriert werden soll.

     Wenn Sie die Appliance auf einem neuen Standort registrieren möchten, muss der Wert von **Sitename** eindeutig sein und sich von vorhandenen Websites unterscheiden. Wenn Sie die Appliance auf einem vorhandenen Standort registrieren möchten, muss der Wert für **Sitename** in. ini mit dem in der Konfiguration der Office 365 Organisation definierten Namen übereinstimmen. Wenn Sie eine Konfigurationsdatei von einer Website in eine andere kopieren, stellen Sie sicher, dass Sie den Wert **für Sitename für jeden** Standort entsprechend aktualisieren.

- **Servername:** Der Servername sollte nicht den Domänennamen enthalten und sollte auf 15 Zeichen reduziert werden.

- **Hardwaretyp:** Wenn Sie den Wert nicht auf NULL festlegen oder beibehalten, wird der Standardwert **Normal** verwendet. Verwenden Sie **Normal** , wenn Sie die größere Version von Cloud Connector zur Unterstützung von 500 gleichzeitigen Anrufen pro Hostcomputer bereitstellen möchten, wie unter [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)beschrieben. Verwenden Sie **mindestens** für eine kleinere Bereitstellung, die 50 gleichzeitige Anrufe unterstützt.

- **Virtuelle Switches für Internet/Corpnet/Verwaltung:**: Fügen Sie den Namen der virtuellen Switches hinzu, die Sie erstellt haben. Lassen Sie den Standardwert für den virtuellen Switch für die Verwaltung unverändert. Das Bereitstellungsskript erstellt den virtuellen Switch für die Verwaltung zu Beginn der Bereitstellung und löscht ihn, sobald die Bereitstellung abgeschlossen ist.

- **ManagementIPPrefix:** ManagementIPPrefix im Abschnitt "Netzwerk" muss ein anderes Subnetz als andere interne IPS sein. Wenn beispielsweise der Standardwert angezeigt wird, ist ManagementIPPrefix 192.168.213.0, während AD-IPAddress 192.168.0.238 ist.

    Die Bereitstellungsskripts erstellen einen Verwaltungsnetzwerkadapter auf jedem virtuellen Computer, weisen eine Verwaltungs-IP zu und verbinden ihn mit einem virtuellen Switch für die Verwaltung. Dadurch kann der Hostserver über dieses Verwaltungsnetzwerk eine Verbindung zu jedem virtuellen Computer herstellen und ihn verwalten. Der virtuelle Verwaltungs Switch wird gelöscht, wenn die Bereitstellung abgeschlossen ist.

- **Grundlegende VM-spezifische Konfigurationen:** Die Einstellungen in diesem Abschnitt müssen für das Cmdlet **Convert-CcIsoToVhdx** konfiguriert werden.

    Während der Vorbereitung des Basis-VM-Images wird die Basis-VM mit dem internen Netzwerk Switch verbunden. Die folgenden Einstellungen sind wichtig, damit die VM auf das Internet zugreifen kann:

  - Common BaseVMIP: die Corpnet-IP-Adresse, die der Basis-VM zugewiesen werden soll.

  - Netzwerk CorpnetDefaultGateway: das Standardgateway, das der Basis-VM zugewiesen wird.

  - Netzwerk CorpnetDNSIPAddress: die DNS-IP-Adresse, die der Basis-VM zugewiesen werden soll.

  - Netzwerk WSUSServer: die IP-Adresse des Windows Server-Update Diensts.

  - Netzwerk WSUSStatusServer: die IP-Adresse des Windows Server Update Service-Statusservers.

  - Netzwerk "Enablerefersupport": Dadurch wird definiert, ob SIP-Refer-Unterstützung für die trunk Konfiguration für Ihre IP/Nebenstellenanlage aktiviert oder deaktiviert ist.

- **Interne IPS:**

  - Stellen Sie sicher, dass Subnetzmaske CorpnetIPPrefixLength korrekt ist.

  - Stellen Sie sicher, dass für diese internen IPS keine IP-Konflikte vorhanden sind.

- **Externe IPS:**

  - Für Mr Public IP: Geben Sie entweder "externalmrips" für nicht-NAT oder ExternalMRPublicIPs für NAT an.

  - ExternalSIPIPs und "externalmrips" können identisch sein.

  - Stellen Sie sicher, dass Subnetzmaske InternetIPPrefixLength korrekt ist.

  - Stellen Sie sicher, dass es keine IP-Konflikte für diese externen IPS gibt.

- **Gateways**

  - Wenn Sie nur ein Gateway haben, entfernen Sie den Abschnitt für das sekundäre Gateway. Wenn Sie über mehr als zwei Gateways verfügen, erstellen Sie zusätzliche Abschnitte, indem Sie das vorhandene kopieren und einfügen und dann aktualisieren.

  - Stellen Sie sicher, dass die IP-Adresse und der Port der Gateways korrekt sind.

  - Um die PSTN-Gatewayebene ha zu unterstützen, lassen Sie das sekundäre Gateway, und fügen Sie alle zusätzlichen Gateways hinzu, die Sie verwenden werden. Sie können einen vorhandenen Eintrag kopieren und einfügen und ihn dann aktualisieren.

- Optional können Sie den LocalRoute-Wert aktualisieren, um ausgehende Rufnummern einzuschränken.

## <a name="download-the-bits-to-the-site-directory"></a>Laden Sie die Bits in das Websiteverzeichnis herunter.

Führen Sie das folgende Cmdlet aus, um die Bits-und Versions Informationsdateien in das **Websiteverzeichnis**herunterzuladen:

```powershell
Start-CcDownload
```

> [!NOTE]
> Sie müssen diesen Schritt nur für die erste Appliance ausführen. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Vorbereiten des virtuellen Basisdatenträgers (VHDX) aus der heruntergeladenen ISO-Datei

In diesem Schritt wird eine VHDX-Datei (Virtual Hard Disk) aus dem Windows Server 2012 ISO-Abbild vorbereitet. Die VHDX wird zum Erstellen virtueller Computer während der Bereitstellung verwendet. Ein temporärer virtueller Computer (Basis-VM) wird erstellt, und Windows Server 2012 werden aus der ISO-Datei installiert. Nachdem die VM erstellt wurde, werden einige erforderliche Komponenten installiert, und das neueste Windows-Update wird angewendet. Am Ende wird die Basis-VM generalisiert (Sysprep) und bereinigt, sodass nur die generierte virtuelle Datenträgerdatei bleibt.

> [!NOTE]
> Sie müssen diesen Schritt nur für die erste Appliance ausführen. 

Bevor Sie mit diesem Schritt fortfahren, stellen Sie sicher, dass der Corpnet-Schalter erstellt wird. Vergewissern Sie sich außerdem, dass die folgenden Einstellungen in der Datei "cloudconnector. ini ordnungsgemäß konfiguriert sind:

- Netzwerk CorpnetSwitchName

- Common BaseVMIP

- Netzwerk CorpnetIPPrefixLength

- Netzwerk CorpnetDefaultGateway

- Netzwerk CorpnetDNSIPAddress

Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um das ISO-Abbild auf eine virtuelle Festplatte (VHD) zu konvertieren:

```powershell
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Geben Sie den vollständigen Pfad einschließlich des Datei namens in das ISO-Abbild ein. Beispiel: C:\ISO\WindowsServer2012R2.ISO.

Die erstellte VHD-Datei wird im Ordner \Bits\VHD des **Websiteverzeichnisses** gespeichert. Sie können den Pfad zum **Websiteverzeichnis** abrufen, indem Sie das **Get-CcSiteDirectory-** Objekt durchführen.

> [!IMPORTANT]
> Standardmäßig sind Proxyeinstellungen nicht auf der Basis-VM konfiguriert. Wenn ein Proxy in Ihrer Netzwerkumgebung erforderlich ist, um den virtuellen Computer über Windows Update zu aktualisieren, sollten Sie den-PauseBeforeUpdate-Schalter bei der Ausführung von "Convert-CcIsoToVhdx" hinzufügen. Das Skript wird vor Windows Update angehalten, und Sie haben die Möglichkeit, einen Proxy für die VM manuell einzurichten. Nachdem der Proxy eingerichtet wurde und der VM auf das Internet zugreifen kann, können Sie das Skript fortsetzen, um die verbleibenden Schritte abzuschließen. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Erstellen von virtuellen Festplatten für eine Bereitstellung mit mehreren Standorten

Dies ist ein optionaler Schritt, der nur für Bereitstellungen mit mehreren Standorten gilt.

Wenn Sie eine Bereitstellung mit mehreren Standorten bereitstellen, müssen Sie die ISO nicht für jeden Standort in eine VHD konvertieren. Sie können die für die erste Website erstellte VHDX für einen zweiten Standort auf den Hostserver kopieren.

 Kopieren Sie die Datei an denselben Dateispeicherort ( **Standortverzeichnis** \Bits\VHD-Ordner) und denselben Dateinamen auf dem Hostserver für einen zusätzlichen Standort.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Festlegen der PowerShell-Ausführungsrichtlinie auf RemoteSigned

Für die bereitgestellten PowerShell-Skripts muss die Ausführungsrichtlinie auf RemoteSigned festgelegt werden. Um die aktuelle Einstellung anzuzeigen, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie dann das folgende Cmdlet aus:

```powershell
Get-ExecutionPolicy
```

Wenn er nicht auf "RemoteSigned" festgelegt ist, führen Sie das folgende Cmdlet aus, um es zu ändern:

```powershell
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Ändern der lokalen Gruppenrichtlinie auf dem Hostcomputer (Version 1.4.1 und früher)

> [!NOTE]
> Diese Aufgabe ist für Cloud Connector-Versionen 1.4.2 und höher nicht erforderlich. 

Das "cceservice"-Konto wird während der Skype for Business Cloud Connector Edition-Bereitstellung erstellt. Er führt den Cloud Connector-Verwaltungsdienst aus und erfordert die Berechtigung zum Deinstallieren von "cloudconnector. msi. Sie müssen die Gruppenrichtlinieneinstellung auf dem Cloud Connector-Hostcomputer ändern, um anzugeben, dass die Benutzerregistrierung nicht entladen werden soll, wenn sich der Benutzer abmeldet. Führen Sie die folgenden Schritte aus:

### <a name="to-change-the-group-policy-setting"></a>So ändern Sie die Gruppenrichtlinieneinstellung

1. Öffnen Sie den **Gruppenrichtlinien-Editor** , indem Sie gpedit. msc verwenden.

2. Navigieren Sie im **Gruppenrichtlinien-Editor**zu Administrative Vorlagen > System > User Profile, um die Benutzerregistrierung beim Abmelden des Benutzers nicht gewaltsam zu entladen >. 

3. Legen Sie den Wert auf **aktiviert**fest.

## <a name="set-up-your-office-365-organization"></a>Einrichten Ihrer Office 365 Organisation

Eine Office 365 Organisation mit Skype for Business Online-und Telefon System in Office 365 ist erforderlich. Stellen Sie sicher, dass Ihr Mandant eingerichtet und konfiguriert ist, bevor Sie versuchen, Cloud Connector zu verwenden.

Für einige Office 365-Setupschritte müssen Sie die mandantenfähige Remote-PowerShell (TRPS) verwenden, um Ihre Office 365 Organisation zu konfigurieren. **Diese sollte auf dem Hostserver installiert sein.** Sie können das Skype for Business Online Modul für PowerShell unter: [Skype for Business Online, Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366)herunterladen.

Erstellen Sie ein dediziertes Skype for Business Administratorkonto für die Online Verwaltung von Cloud Connector, beispielsweise CceOnlineManagmentAdministrator. Dieses Konto wird von Appliance zum Hinzufügen oder Entfernen von Appliance, aktivieren oder Deaktivieren des automatischen Betriebssystemupdates, aktivieren oder Deaktivieren der automatischen binären Aktualisierung verwendet. Legen Sie das Kennwort für dieses Konto so fest, dass es nie abläuft, damit Sie es nicht bei jedem Ablauf des Diensts ändern müssen.


