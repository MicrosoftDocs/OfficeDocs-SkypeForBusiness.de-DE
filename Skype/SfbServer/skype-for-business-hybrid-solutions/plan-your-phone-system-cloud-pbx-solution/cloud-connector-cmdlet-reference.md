---
title: Cmdlet-Referenz für Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: In der folgenden Tabelle sind die Skype for Business Cloud Connector Edition Cmdlets mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgeführt.
ms.openlocfilehash: 19fc33912075e7737a4fa7fc242e74dd1de92289
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583729"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cmdlet-Referenz für Cloud Connector
 
> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

In der folgenden Tabelle sind die Skype for Business Cloud Connector Edition Cmdlets mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgeführt.
  
> [!NOTE]
> Sie müssen alle Cmdlets auf dem Cloud Connector-Hostcomputer ausführen und die PowerShell-Sitzung als Administrator ausführen. 
  
|**Name des Cmdlets**|**Beschreibung**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Version 1.4.2 und höher  <br/> |Sichert den Zertifizierungsstellendienst in einer Datei und speichert ihn im Ca-Ordner unter dem Websitefreigabeverzeichnis.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Erstellt eine virtuelle Basisfestplattendatei (VHDX) mithilfe einer vom Kunden bereitgestellten Windows Server 2012 R2-ISO-Datei. Die VHDX-Datei wird während der Bereitstellung von Cloud Connector verwendet.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Bereitet den Cloud Connector-Hostserver auf den Updateprozess vor, indem er in den Wartungsmodus versetzt wird. Die Appliance ist "entleert"; d. h., alle vorhandenen Anrufe werden abgeschlossen, neue Anrufe werden jedoch abgelehnt.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Beendet den Updatewartungsmodus auf dem Cloud Connector-Hostserver.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Exportiert eine Skype for Business Cloud Connector Edition Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition Hostserver. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exportiert eine Cloud Connector-Beispielkonfigurationsdatei (.ini) in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die für Ihre Bereitstellung zu verwendende Datei ändern und umbenennen.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Version 1.4.2 und höher  <br/> |Exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Cloud Connector-Hostserver.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Ruft das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver ab. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem Protokolle für eine Cloud Connector-Appliance gespeichert werden.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Version 2.1 und höher  <br/> |Stellt Diagnoseinformationen für die Cloud Connector-Appliance bereit.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Gibt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung zurück.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Gibt den Pfad der externen Zertifikatdatei für die Cloud Connector-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem Konfigurationsdateien auf Standortebene gespeichert sind. Der Ordner enthält die Basisinstallationsdateien für VHD und Cloud Connector. Dieser Ordner sollte für alle anderen Appliances eines Cloud Connector-Standorts freigegeben werden.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Standortebene für Cloud Connector gespeichert sind.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Version 2.0 und höher  <br/> |Gibt die Version der Cloud Connector-Instanz zurück. Get-CCVersion können nur auf dem Hostcomputer von Cloud Connector verwendet werden.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Version 2.0 und höher  <br/> |Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installiert die Cloud Connector-Appliance , einschließlich der virtuellen Computer AD, der zentralen Verwaltung Store, des Vermittlungsservers und des Edgeservers, auf dem Hostserver.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Ruft Informationen zur hohen Verfügbarkeit aus der Onlinemandantenkonfiguration ab und veröffentlicht sie in der Cloud Connector-Appliance auf dem Hostserver. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registriert Appliance-Informationen an einem PSTN-Standort in einer Onlinemandantenkonfiguration. Eine Appliance muss registriert werden, bevor sie vom Cloud Connector-Verwaltungsdienst bereitgestellt und verwaltet werden kann. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt die Sicherungsdatei des Zertifizierungsstellendiensts " \<SiteRootDirectory\> \CA\SfB CCE Root.p12" im Ca-Ordner unter dem Standortfreigabeverzeichnis für Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt Legacyserverzertifikate für die zentrale Verwaltung Store, den Vermittlungsserver und den Edgeserver, nachdem Sie die Cmdlets "Renew-CcCACertificate" oder "Renew CcServerCertificate" ausgeführt haben.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Nur Version 1.4.2  <br/> |Installiert den AD-Server des Zertifizierungsstellendiensts neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Nur Version 1.4.2  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn sie in Kürze ablaufen oder bereits abgelaufen sind.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Version 1.4.2 und höher  <br/> |Setzt die Zertifizierungsstellenserver zurück, um ein neues Zertifizierungsstellenzertifikat zu installieren.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Version 2.1 und höher  <br/> |Bereinigt Anmeldeinformationen und fordert Sie auf, alle für die aktuelle Cloud Connector-Bereitstellung verwendeten Anmeldeinformationen erneut einzugeben.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Durchsucht die Protokolle für ein- und ausgehende Anrufe im Protokollverzeichnis der Cloud Connector-Appliance.  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Legt das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver fest. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Legt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung fest.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder Edgeserver gespeichert ist.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Legt das Verzeichnis fest, in dem Konfigurationsdateien auf Standortebene für Cloud Connector gespeichert werden. Der Ordner enthält die Basis-VHD- und Cloud Connector-Konfigurationsdateien.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Lädt die Cloud Connector-Bits und die MSI-Datei synchron herunter.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Generiert das Protokoll für ein- und ausgehende Anrufe für eine Cloud Connector-Appliance.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Beendet die Generierung des Protokolls für ein- und ausgehende Anrufe für eine Cloud Connector-Appliance.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Trennt die ausgeführte Appliance und wechselt zu einer neu bereitgestellten oder Sicherungsanwendung.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Deinstalliert die ausgeführte Cloud Connector-Appliance vom Hostserver.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Hebt die Registrierung der aktuellen Cloud Connector-Appliance an einem PSTN-Standort in der Onlinemandantenkonfiguration auf.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Version 2.0 und höher  <br/> |Installiert den AD-Server des Zertifizierungsstellendiensts neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Version 2.0 und höher  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn sie in Kürze ablaufen oder bereits abgelaufen sind.  <br/> |
