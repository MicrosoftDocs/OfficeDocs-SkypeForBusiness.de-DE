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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 6eacfa99-9759-4c13-aca3-8992c2ff2710
description: Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und Verwendung mit dem Telefon System in Office 365 (Cloud PBX) vorbereiten.
ms.openlocfilehash: f2140eb0be25ba0b6935f389e5ae7b27bfc37359
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286999"
---
# <a name="prepare-your-cloud-connector-appliance"></a>Vorbereiten der Cloud Connector-Appliance

Erfahren Sie, wie Sie Ihre Cloud Connector-Appliance für die Bereitstellung und Verwendung mit dem Telefon System in Office 365 (Cloud PBX) vorbereiten.

In diesem Abschnitt wird beschrieben, wie Sie die Installationsdateien für Skype for Business Cloud Connector Edition abrufen, Cloud Connector-Software installieren und Ihre Cloud Connector-Appliance auf die Bereitstellung vorbereiten. Wenn Sie alle Schritte in diesem Abschnitt abgeschlossen haben, sind Sie bereit, Cloud Connector für einen einzelnen Standort oder für mehrere Standorte bereitzustellen. Wenn Sie über eine vorhandene Cloud Connector-Bereitstellung verfügen und noch nicht auf Cloud Connector, Version 2,1, aktualisiert haben, lesen Sie [Upgrade auf eine neue Version von Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).

> [!NOTE]
> Microsoft unterstützt die aktuelle Version von Cloud Connector Edition, Version 2,1. Wenn Sie automatische Updates konfiguriert haben, wird Cloud Connector automatisch aktualisiert. Wenn Sie die manuelle Aktualisierung konfiguriert haben, müssen Sie innerhalb von 60 Tagen nach der Veröffentlichung auf Version 2,1 aktualisieren. Microsoft unterstützt die vorherige Version 60 Tage nach der Veröffentlichung von 2,1, um Ihnen Zeit für ein Upgrade zu bieten. 

> [!NOTE]
> Für Cloud Connector Version 2,1 und höher muss die Host-Appliance .NET Framework 4.6.1 oder höher installiert haben. 

> [!IMPORTANT]
> Für eine erfolgreiche Bereitstellung verwenden Sie beim Ausführen der Cmdlets zum Konfigurieren von Skype for Business Cloud Connector Edition immer dieselbe Konsolensitzung wie die, in der Sie begonnen haben. Vermeiden Sie es während der Bereitstellung und Konfiguration, zwischen verschiedenen Sitzungen zu wechseln. 

> [!NOTE]
> Es gibt einige Schritte, die Sie nur für die erste Appliance in der Bereitstellung ausführen: Erstellen einer Freigabe für das Standortverzeichnis, Herunterladen der Bits und Vorbereiten einer VHDX-Datei (Virtual Hard Disk, virtuelle Festplatte) anhand des ISO-Images von Windows Server. 

## <a name="download-the-skype-for-business-cloud-connector-edition-installer"></a>Herunterladen des Installationsprogramms für Skype for Business Cloud Connector Edition

1. Laden Sie auf dem Hostserver, auf dem der Cloud Connector VMS ausgeführt wird, die [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)Installationsdateien herunter:. 

    > [!IMPORTANT]
    > Der Hostserver muss in der Lage sein, während der Installation von Cloud Connector eine Internetverbindung herzustellen, da während der Installation zusätzliche Dateien heruntergeladen werden. 

2. Führen Sie das Installationsprogramm aus und akzeptieren Sie während der Installation die Standardwerte.

3. Bestätigen Sie, dass die Installation erfolgreich abgeschlossen wurde.

## <a name="verify-the-installation-and-configure-the-environment"></a>Überprüfen der Installation und Konfigurieren der Umgebung

1. Öffnen Sie eine PowerShell-Konsole als Administrator, und stellen Sie sicher, dass die Skype for Business Cloud Connector Edition-Cmdlets mit dem folgenden Cmdlet verfügbar sind:

   ```
   Get-Command *-Cc*
   ```

    Der Befehl sollte eine Liste der Cmdlets für Skype for Business Cloud Connector Edition zurückgeben.

2. Die VHDs, SfBBits und VersionInfo-Dateien werden im **Websiteverzeichnis** gespeichert.

    Den Speicherort des **Websiteverzeichnisses** können Sie mit dem folgenden Cmdlet ermitteln:

   ```
   Get-CcSiteDirectory
   ```

    Der Befehl sollte einen Speicherort in Ihrem Dateisystem zurückgeben. Bei dem Speicherort kann es sich um einen lokalen Ordner oder um eine Dateifreigabe handeln. Der Standardspeicherort für das **Websiteverzeichnis** lautet „%USERPROFILE%\CloudConnector\SiteRoot“. Der Standardspeicherort sollte in der ersten für jeden Standort erstellten Appliance in eine Dateifreigabe geändert werden.

    Für den ausgewählten Speicherort muss Folgendes gelten:

   - Er wurde in der ersten an jedem Standort erstellten Appliance erstellt.

   - Es handelt sich um einen freigegebenen Ordner, auf den andere Hostserver (Appliances) am gleichen Standort zugreifen können.

     Um das **Websiteverzeichnis** auf einen anderen Speicherort als den Standard festzulegen, führen Sie das folgende Cmdlet aus:

   ```
   Set-CcSiteDirectory <UNC File path>
   ```

    Wenn Sie Hochverfügbarkeit (HA) für den Standort bereitstellen, vergewissern Sie sich, dass Sie das Cmdlet zum Festlegen des **Websiteverzeichnisses** auf den gleichen Speicherort auf jedem Hostserver innerhalb des Standorts ausführen.

    Wenn Sie sich anmelden und jede Appliance auf der Website bereitstellen, stellen Sie sicher, dass das aktuelle Anmeldekonto über den richtigen Zugriff auf das **Websiteverzeichnis**verfügt.

3. Das **Appliance-Verzeichnis** ist das lokal arbeitende Stammverzeichnis für Skype for Business Cloud Connector Edition und der Speicherort, an dem externe Zertifikate, Instanzen und Protokolle gespeichert werden. Der Standardspeicherort ist: %USERPROFILE%\CloudConnector\ApplianceRoot.

    Um den Speicherort des **Appliance-Verzeichnisses** zu suchen, führen Sie das folgende Cmdlet aus:

   ```
   Get-CcApplianceDirectory
   ```

    Um das **Appliance-Verzeichnis** auf einen anderen Speicherort als den Standard festzulegen, führen Sie das folgende Cmdlet aus:

   ```
   Set-CcApplianceDirectory <File path>
   ```

    Als Appliance-Verzeichnis sollte ein lokaler Ordner in der Appliance festgelegt sein. Sie sollten das Appliance- **Verzeichnis** nur einrichten, bevor Sie die Bereitstellung von Skype for Business Cloud Connector Edition starten. Wenn Sie das Verzeichnis nach der Bereitstellung ändern, müssen Sie den Hostserver erneut bereitstellen.

    > [!IMPORTANT]
    > Der Pfad zum **Appliance-Verzeichnis** darf keine Leerzeichen enthalten.

## <a name="set-the-path-for-the-external-edge-certificate"></a>Festlegen des Pfads für das externe Zertifikat des Edges

- Führen Sie das folgende Cmdlet aus, um den Pfad einschließlich des Dateinamens zum externen Zertifikat des Edges festzulegen. Beispiel: „C:\certs\cce\ap.contoso.com.pfx“. Das Zertifikat muss private Schlüssel enthalten.

  ```
  Set-CcExternalCertificateFilePath -Path <Full path to External certificate, including file name> -Target EdgeServer
  ```

    > [!NOTE]
    > Beachten Sie, dass der Parameter „-Target“ speziell für Version 1.4.2 und höher gilt. 

    Geben Sie den vollständigen Pfad einschließlich Dateinamen zum externen Zertifikat an. Das Zertifikat kann lokal oder in einer Dateifreigabe gespeichert werden. Wenn das Zertifikat in einem freigegebenen Ordner gespeichert ist, muss der freigegebene Ordner auf der ersten Appliance jeder Website erstellt werden und muss von anderen Appliances, die derselben Website angehören, zugänglich sein. Dieses Cmdlet kopiert das externe Zertifikat in das **Appliance-Verzeichnis**.

    > [!IMPORTANT]
    > **Wenn Sie auf Cloud Connector, Version 1.4.2 oder höher, aktualisiert haben**, stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel sowie die vollständige Zertifikatkette einschließlich des Zertifikats der Stammzertifizierungsstelle und der Zertifikate der Zwischenzertifizierungsstellen enthält. **Wenn Sie noch NICHT auf Cloud Connector, Version 1.4.2, aktualisiert haben**, stellen Sie sicher, dass Ihr vorbereitetes externes Zertifikat private Schlüssel enthält. Dieses externe Zertifikat muss von einer Zertifizierungsstelle ausgestellt sein, der Windows standardmäßig vertraut.

## <a name="set-the-path-for-the-external-pstn-gatewaysbc-certificate"></a>Festlegen des Pfads für das externe Zertifikat des PSTN-Gateways/SBC

Wenn Sie zwischen dem Vermittlungsserver und dem PSTN-Gateway/SBC TLS verwenden, führen Sie das folgende Cmdlet aus, um den Pfad (einschließlich des Dateinamens) zum Gatewayzertifikat festzulegen. Beispiel: C:\certs\cce\sbc.contoso.com.cer. Das Zertifikat muss die Stammzertifizierungsstelle und die Zwischenkette für das Zertifikat enthalten, das dem Gateway zugewiesen ist:

```
Set-CcExternalCertificateFilePath -Path <Full path to gateway certificate, including file name> -Target MediationServer 
```

> [!NOTE]
> Beachten Sie, dass der Parameter „-Target“ speziell für Version 1.4.2 und höher gilt. 

## <a name="create-virtual-switches-in-hyper-v-manager"></a>Erstellen von virtuellen Switches in Hyper-V-Manager

1. Öffnen Sie den **Hyper-V Manager** > **Virtual Switch Manager**, und wählen Sie **neuer virtueller Switch-Manager**aus.

2. Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physischen Netzwerkadapter, der mit Ihrer internen Netzwerkdomäne verbunden ist:

    Wählen Sie **Gemeinsames Verwenden dieses Netzwerkadapters für das Verwaltungsbetriebssystem zulassen** für diesen virtuellen Switch aus.

3. Erstellen Sie einen externen virtuellen Switch, und binden Sie ihn an den physikalischen Netzwerkadapter, der an das Internet weitergeleitet wird:

    Deaktivieren Sie für diesen virtuellen Switch die Option **Management-Betriebssystem zulassen, um diesen Netzwerkadapter freizugeben** .

4. Legen Sie den Namen des Schalters fest, der Ihr Umkreisnetzwerk mit Ihrem internen Netzwerkdomänen- **SFB CCE Corpnet-Switch**verbindet.

    Legen Sie den Namen des Schalters fest, der Ihr Umkreisnetzwerk mit dem Internet- **Switch des SFB CCE**verbindet.

## <a name="update-the-cloudconnectorini-configuration-file"></a>Aktualisieren der Konfigurationsdatei „CloudConnector.ini“

Bereiten Sie die Datei CloudConnector. ini unter Verwendung der Informationen vor, die Sie unter [Ermitteln von Bereitstellungs Parametern](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im Thema [Planen von Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) gesammelt haben.

Führen Sie zum Aktualisieren der Datei zunächst das folgende Cmdlet aus, um die Beispielvorlage (CloudConnector.Sample.ini) zu erhalten:

```
Export-CcConfigurationSampleFile
```

Die Beispielvorlage wird im **Appliance-Verzeichnis** gespeichert.

Nachdem Sie sie mit den Werten für Ihre Umgebung aktualisiert haben, speichern Sie die Datei als „CloudConnector.ini“ im **Appliance-Verzeichnis**. Sie können **Get-CcApplianceDirectory** ausführen, um den Pfad zum **Appliance-Verzeichnis** zu ermitteln.

Beachten Sie Folgendes beim Aktualisieren der INI-Datei:

> [!NOTE]
> In diesem Abschnitt werden nicht alle Werte für die INI-Datei besprochen, sondern nur die wichtigsten. Eine vollständige Liste finden Sie im Abschnitt [Festlegen von Bereitstellungs Parametern](plan-skype-for-business-cloud-connector-edition.md#BKMK_SiteParams) im Thema Planen von [Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md) . Weitere Informationen zu den Werten, die Sie für zusätzliche Appliances oder neue Standorte ändern müssen, finden Sie unter [Bereitstellung eines einzelnen Standort mit hoher Verfügbarkeit im Vergleich zur Bereitstellung mehrerer Standorte](deploy-multiple-sites-in-cloud-connector.md#BKMK_SingleSitecomparedtomulti-site) im Thema [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 

- **SiteName:** Der Standardwert lautet **Site1**. Sie müssen ihn aktualisieren, bevor Sie Cloud Connector bereitstellen können. Der Grund: Wenn Sie **Register-CcAppliance** ausführen, um eine Appliance an einem vorhandenen oder neuen Standort zu registrieren, bestimmt das Cmdlet anhand von **SiteName**, welcher Standort registriert werden soll.

     Wenn Sie die Appliance an einem neuen Standort registrieren möchten, muss der Wert für **SiteName** eindeutig sein und sich von dem für vorhandene Standorte unterscheiden. Wenn Sie die Appliance auf einer vorhandenen Website registrieren möchten, muss der Wert für **Sitename** in der INI-Datei mit dem in Ihrer Office 365-Mandanten Konfiguration definierten Namen übereinstimmen. Wenn Sie eine Konfigurationsdatei von einem Standort an einen anderen kopieren, stellen Sie sicher, dass Sie den Wert für **SiteName** für jeden Standort entsprechend aktualisieren.

- **ServerName:** Der Servername sollte nicht den Domänennamen enthalten und ist auf 15 Zeichen begrenzt. 

- **Hardwaretyp:** Wenn Sie den Wert nicht auf NULL festlegen oder belassen, wird der Standardwert **Normal** verwendet. Verwenden Sie **Normal** , wenn Sie die größere Version von Cloud Connector zur Unterstützung von 500-gleichzeitigen Anrufen pro Hostcomputer planen, wie in [Plan für Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)beschrieben. Verwenden Sie **Minimum** für eine kleinere Bereitstellung, die 50 gleichzeitige Anrufe unterstützt.

- **Virtuelle Switches für Internet/Unternehmensnetzwerk/Verwaltung**: Fügen Sie die Namen der virtuellen Switches hinzu, die Sie erstellt haben. Für den virtuellen Switch für die Verwaltung behalten Sie den Standardwert bei. Das Bereitstellungsskript erstellt den virtuellen Switch für die Verwaltung zu Beginn der Bereitstellung und löscht ihn, sobald die Bereitstellung abgeschlossen ist.

- **ManagementIPPrefix:** „ManagementIPPrefix“ im Netzwerkabschnitt muss ein anderes Subnetz als das der anderen internen IPs sein. Beispiel: Der Standardwert für „ManagementIPPrefix“ lautet 192.168.213.0, während die AD-IP-Adresse 192.168.0.238 lautet.

    Die Bereitstellungsskripts erstellen auf jedem virtuellen Computer einen Verwaltungs-Netzwerkadapter, weisen eine Verwaltungs-IP zu und verbinden diese mit einem virtuellen Switch für die Verwaltung. Dadurch kann der Hostserver über dieses Verwaltungsnetzwerk eine Verbindung zu jedem virtuellen Computer herstellen und diesen verwalten. Der virtuelle Switch für die Verwaltung wird gelöscht, nachdem die Bereitstellung abgeschlossen ist.

- **Spezifische Konfigurationen für die Basis-VM:** Die Einstellungen in diesem Abschnitt müssen für das Cmdlet **Convert-CcIsoToVhdx** konfiguriert werden.

    Während der Vorbereitung des Basis-VM-Images wird die Basis-VM mit dem internen Netzwerkswitch verbunden. Die folgenden Einstellungen sind entscheidend, damit die VM auf das Internet zugreifen kann:

  - [Common]BaseVMIP: die IP-Adresse des Unternehmensnetzwerks, die dem virtuellen Basiscomputer zugewiesen wird.

  - [Network]CorpnetDefaultGateway: das Standard-Gateway, das dem virtuellen Basiscomputer zugewiesen wird.

  - [Network]CorpnetDNSIPAddress: die DNS-IP-Adresse, die dem virtuellen Basiscomputer zugewiesen wird.

  - [Network]WSUSServer: die IP-Adresse des Windows Server Update Service.

  - [Network]WSUSStatusServer: die IP-Adresse des Statusservers für den Windows Server Update Service.

  - „[Network]EnableReferSupport“: Damit wird definiert, ob SIP REFER-Unterstützung in der Trunk-Konfiguration Ihrer IP-PBX aktiviert oder deaktiviert ist.

- **Interne IPs:**

  - Stellen Sie sicher, dass die Subnetzmaske CorpnetIPPrefixLength korrekt ist.

  - Stellen Sie sicher, dass für diese internen IPS keine IP-Konflikte vorhanden sind.

- **Externe IPs:**

  - Für Mr Public IP: Geben Sie entweder ExternalMRIPs für nicht-NAT oder ExternalMRPublicIPs für NAT an.

  - ExternalSIPIPs und ExternalMRIPs können identisch sein.

  - Stellen Sie sicher, dass die Subnetzmaske InternetIPPrefixLength korrekt ist.

  - Stellen Sie sicher, dass für diese externen IPS keine IP-Konflikte vorhanden sind.

- **Gateways:**

  - Wenn Sie nur ein Gateway haben, entfernen Sie den Abschnitt für das sekundäre Gateway. Bei mehr als zwei Gateways erstellen Sie zusätzliche Abschnitte, indem Sie den vorhandenen Abschnitt kopieren und einfügen und ihn dann aktualisieren.

  - Stellen Sie sicher, dass die IP-Adresse und der Port des bzw. der Gateways korrekt sind.

  - Um HA auf PSTN-Gateway-Ebene zu unterstützen, belassen Sie die sekundären Gateways, und fügen Sie alle weiteren Gateways hinzu, die Sie verwenden möchten. Sie können einen vorhandenen Eintrag kopieren und einfügen und dann aktualisieren.

- Optional können Sie den LocalRoute-Wert aktualisieren, um ausgehende Rufnummern zu begrenzen.

## <a name="download-the-bits-to-the-site-directory"></a>Laden Sie die Bits in das Websiteverzeichnis herunter.

Führen Sie das folgende Cmdlet aus, um die Bits und Versionsinformationsdateien in das **Websiteverzeichnis** herunterzuladen:

```
Start-CcDownload
```

> [!NOTE]
> Diesen Schritt müssen Sie nur für die erste Appliance ausführen. 

## <a name="prepare-base-virtual-disk-vhdx-from-the-downloaded-iso-file"></a>Vorbereiten des virtuellen Basisdatenträgers (VHDX) anhand der heruntergeladenen ISO-Datei

In diesem Schritt wird eine virtuelle Festplattendatei (VHDX) vom Windows Server 2012 ISO-Image vorbereitet. Die VHDX wird zum Erstellen der virtuellen Computer während der Bereitstellung verwendet. Ein temporärer virtueller Computer (Basis-VM) wird erstellt, und Windows Server 2012 wird aus der ISO-Datei installiert. Nach Erstellen des virtuellen Computers werden einige erforderliche Komponenten installiert und das neueste Windows-Update angewendet. Zum Abschluss wird der virtuelle Basiscomputer generalisiert (sysprep) und bereinigt, sodass nur die generierte virtuelle Festplattendatei zurückbleibt.

> [!NOTE]
> Diesen Schritt müssen Sie nur für die erste Appliance ausführen. 

Bevor Sie mit diesem Schritt fortfahren, vergewissern Sie sich, dass der Switch für das Unternehmensnetzwerk erstellt wurde. Bestätigen Sie auch, dass die folgenden Einstellungen in der Datei „CloudConnector.ini“ richtig konfiguriert sind:

- [Network]CorpnetSwitchName

- [Common]BaseVMIP

- [Network]CorpnetIPPrefixLength

- [Network]CorpnetDefaultGateway

- [Network]CorpnetDNSIPAddress

Starten Sie eine PowerShell-Konsole als Administrator und führen Sie das folgende Cmdlet aus, um das ISO-Image in eine virtuelle Festplatte (VHD) zu konvertieren:

```
Convert-CcIsoToVhdx -IsoFilePath <Windows ISO File Path, including file name>
```

Geben Sie den vollständigen Pfad einschließlich Dateinamen zum ISO-Image an. Beispiel: C:\ISO\WindowsServer2012R2.iso.

Die erstellte VHD-Datei wird im Ordner \Bits\VHD des **Websiteverzeichnisses** gespeichert. Sie können den Pfad zum **Websiteverzeichnis** abrufen, indem Sie **Get-CcSiteDirectory** ausführen.

> [!IMPORTANT]
> Standardmäßig sind auf dem virtuellen Basiscomputer keine Proxyeinstellungen konfiguriert. Wenn in Ihrer Netzwerkumgebung ein Proxy erforderlich ist, um den virtuellen Computer über Windows Update zu aktualisieren, sollten Sie beim Ausführen von "Convert-CcIsoToVhdx" den Schalter-PauseBeforeUpdate hinzufügen. Das Skript wird vor Windows Update angehalten, und Sie haben die Möglichkeit, Proxy auf dem virtuellen Computer manuell einzurichten. Nachdem der Proxy eingerichtet ist und der VM auf das Internet zugreifen kann, können Sie das Skript wieder aufnehmen und die verbleibenden Schritte ausführen. 

### <a name="create-vhds-for-a-multi-site-deployment"></a>Erstellen von VHDs für eine Bereitstellung mit mehreren Standorten

Dieser optionale Schritt ist nur auf Bereitstellungen mit mehreren Standorten anwendbar.

Wenn Sie eine Bereitstellung mit mehreren Standorten bereitstellen, ist es nicht erforderlich, das ISO für jeden Standort in VHD zu konvertieren. Sie können die für den ersten Standort erstellte VHDX für einen zweiten Standort auf den Hostserver kopieren.

 Kopieren Sie die Datei auf dem Hostserver für eine weitere Website in den gleichen Dateispeicherort (Ordner " **Websiteverzeichnis** \Bits\VHD") und mit demselben Dateinamen.

## <a name="set-the-powershell-execution-policy-to-remotesigned"></a>Festlegen der PowerShell-Ausführungsrichtlinie auf „RemoteSigned“

Für die bereitgestellten PowerShell-Skripts muss die Ausführungsrichtlinie auf „RemoteSigned“ festgelegt werden. Um die aktuelle Einstellung anzuzeigen, öffnen Sie eine PowerShell-Konsole als Administrator und führen Sie dann das folgende Cmdlet aus:

```
Get-ExecutionPolicy
```

Wenn die Einstellung nicht „RemoteSigned“ lautet, führen Sie das folgende Cmdlet aus, um sie zu ändern:

```
Set-ExecutionPolicy RemoteSigned
```

## <a name="change-local-group-policy-on-the-host-machine-versions-141-and-earlier"></a>Ändern lokaler Gruppenrichtlinien auf dem Hostcomputer (Version 1.4.1 und niedriger)

> [!NOTE]
> Diese Aufgabe ist für Cloud Connector, Version 1.4.2 und höher, nicht erforderlich. 

Das Konto „CceService“ wird bei der Bereitstellung von Skype for Business Cloud Connector Edition erstellt. Sie führt den Cloud Connector-Verwaltungsdienst aus und erfordert die Berechtigung zum Deinstallieren von cloudconnector. msi. Sie müssen die Gruppenrichtlinieneinstellung auf dem Cloud Connector-Hostcomputer ändern, um anzugeben, dass die Benutzerregistrierung bei der Abmeldung des Benutzers nicht entladen werden soll. Führen Sie die folgenden Schritte aus:

### <a name="to-change-the-group-policy-setting"></a>So ändern Sie die Gruppenrichtlinie

1. Öffnen Sie den **Gruppenrichtlinien-Editor** , indem Sie "gpedit. msc" ausführen.

2. Navigieren Sie im **Gruppenrichtlinien-Editor** zu „Administrative Vorlagen > System > UserProfile“ und zur Option, das Entladen der Benutzerregistrierung bei Abmelden des Benutzers nicht zu erzwingen.  

3. Setzen Sie den Wert auf **Enabled**.

## <a name="set-up-your-office-365-tenant"></a>Einrichten des Office 365-Mandanten

Ein Office 365-Mandant mit Skype for Business Online und Telefon System in Office 365 ist erforderlich. Stellen Sie sicher, dass Ihr Mandant eingerichtet und konfiguriert ist, bevor Sie versuchen, Cloud Connector zu verwenden.

Bei einigen Setupschritten von Office 365 müssen Sie die Mandanten-Remote-PowerShell (TRPS) verwenden, um Ihren Office 365-Mandanten zu konfigurieren. **Die Installation sollte auf dem Hostserver erfolgen.** Sie können das Skype for Business Online-Modul für PowerShell von: [Skype for Business Online, Windows PowerShell-Modul](https://www.microsoft.com/en-us/download/details.aspx?id=39366)herunterladen.

Erstellen Sie ein dediziertes Skype for Business-Administratorkonto für die Cloud Connector Online-Verwaltung, beispielsweise CceOnlineManagmentAdministrator. Dieses Konto wird von der Appliance verwendet, um eine Appliance hinzuzufügen oder zu entfernen, automatische Betriebssystemaktualisierung zu aktivieren oder zu deaktivieren oder automatische Binärdateiaktualisierung zu aktivieren oder zu deaktivieren. Legen Sie das Kennwort für dieses Konto so fest, dass es nie abläuft, damit Sie es nicht jedes Mal für den Dienst ändern müssen, wenn es abläuft.


