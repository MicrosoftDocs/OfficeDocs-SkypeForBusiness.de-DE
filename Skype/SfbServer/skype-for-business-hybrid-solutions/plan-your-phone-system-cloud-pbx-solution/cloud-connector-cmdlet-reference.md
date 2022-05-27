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
ms.openlocfilehash: efe4a048e939b6491acc93b7ccd4717ffc9aca8b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676167"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cmdlet-Referenz für Cloud Connector

> [!Important]
> Cloud Connector Edition wird zusammen mit Skype for Business Online am 31. Juli 2021 eingestellt. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams mit [Direct Routing](/MicrosoftTeams/direct-routing-landing-page) verbinden.

In der folgenden Tabelle sind die Skype for Business Cloud Connector Edition Cmdlets mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgeführt.
  
> [!NOTE]
> Sie müssen alle Cmdlets auf dem Cloud Connector-Hostcomputer ausführen, und Sie müssen die PowerShell-Sitzung als Administrator ausführen. 
  
|Cmdlet-Name**|Beschreibung|
|---|---|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <p> Version 1.4.2 und höher|Sichert den Zertifizierungsstellendienst in einer Datei und speichert sie im Ca-Ordner unter dem Websitefreigabeverzeichnis.|
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md)|Erstellt eine virtuelle Basisfestplattendatei (VHDX) mithilfe eines vom Kunden bereitgestellten Windows Server 2012 R2 ISO-Datei. Die VHDX-Datei wird während der Bereitstellung vonCloud Connector verwendet.|
|[Enter-CcUpdate](enter-ccupdate.md)|Bereitet den Cloud Connector-Hostserver für den Updateprozess vor, indem er in den Wartungsmodus versetzt wird. Das Gerät ist "entleert"; Das heißt, alle vorhandenen Anrufe werden abgeschlossen, neue Anrufe werden jedoch abgelehnt.|
|[Exit-CcUpdate](exit-ccupdate.md)|Beendet den Updatewartungsmodus auf dem Cloud Connector-Hostserver.|
|[Export-CcConfiguration](export-ccconfiguration.md)|Exportiert eine Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition Hostserver.|
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md)|Exportiert eine Cloud Connector-Beispielkonfigurationsdatei (.ini) in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei ändern und umbenennen, die für Ihre Bereitstellung verwendet werden soll.|
|[Export-CcRootCertificate](export-ccrootcertificate.md) <p> Version 1.4.2 und höher|Exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Cloud Connector-Hostserver.|
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md)|Ruft das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver ab. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.|
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md)|Zeigt das aktuelle Verzeichnis an, in dem Protokolle für eine Cloud Connector-Appliance gespeichert werden.|
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <p> Version 2.1 und höher|Stellt Diagnoseinformationen für die Cloud Connector-Appliance bereit.|
|[Get-CcCredential](get-cccredential.md)|Gibt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung zurück.|
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md)|Gibt den Pfad der externen Zertifikatdatei für die Cloud Connector-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.|
|[Get-CcSiteDirectory](get-ccsitedirectory.md)|Zeigt das aktuelle Verzeichnis an, in dem Konfigurationsdateien auf Standortebene gespeichert werden. Der Ordner enthält die Basis-VHD- und Cloud Connector-Installationsdateien. Dieser Ordner sollte für alle anderen Appliances eines Cloud Connector-Standorts freigegeben werden.|
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md)|Zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Standortebene für Cloud Connector gespeichert sind.|
|[Get-CcVersion](get-ccversion.md) <p> Version 2.0 und höher|Gibt die Version der Cloud Connector-Instanz zurück. Get-CCVersion können nur auf dem Hostcomputer von Cloud Connector verwendet werden.|
|[Import-CcConfiguration](import-ccconfiguration.md) <p> Version 2.0 und höher|Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.|
|[Install-CcAppliance](install-ccappliance.md)|Installiert die Cloud Connector-Appliance – einschließlich der virtuellen Computer AD, Central Management Store, Mediation Server und Edge Server – auf dem Hostserver.|
|[Publish-CcAppliance](publish-ccappliance.md)|Ruft Informationen zur hohen Verfügbarkeit aus der Onlinemandantenkonfiguration ab und veröffentlicht sie in der Cloud Connector-Appliance auf dem Hostserver.|
|[Register-CcAppliance](register-ccappliance.md)|Registriert Appliance-Informationen an einem PSTN-Standort in einer Onlinemandantenkonfiguration. Eine Appliance muss registriert werden, bevor sie vom Cloud Connector-Verwaltungsdienst bereitgestellt und verwaltet werden kann.|
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <p> Version 1.4.2 und höher|Entfernt die Sicherungsdatei des Zertifizierungsstellendiensts "\<SiteRootDirectory\>\CA\SfB CCE Root.p12" im Ca-Ordner unter dem Websitefreigabeverzeichnis für Cloud Connector.|
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <p> Version 1.4.2 und höher|Entfernt legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.|
|[Renew-CcCACertificate](renew-cccacertificate.md) <p> Nur Version 1.4.2|Installiert den Zertifizierungsstellendienst-AD-Server erneut, um ein neues Stammzertifizierungsstellenzertifikat zu erstellen.|
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <p> Nur Version 1.4.2|Erneuert die Zertifikate für Cloud Connector, wenn sie bald ablaufen oder bereits abgelaufen sind.|
|[Reset-CcCACertificate](reset-cccacertificate.md) <p> Version 1.4.2 und höher|Setzt die Server der Zertifizierungsstelle zurück, um ein neues Zertifikat der Zertifizierungsstelle zu installieren.|
|[Restore-CcCredentials](restore-cccredentials.md) <p> Version 2.1 und höher|Bereinigt Anmeldeinformationen und fordert Sie auf, alle für die aktuelle Cloud Connector-Bereitstellung verwendeten Anmeldeinformationen erneut einzugeben.|
|[Search-CcLog](search-cclog.md)|Durchsucht die Protokolle für eingehende und ausgehende Anrufe im Protokollverzeichnis der Cloud Connector-Appliance.|
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md)|Legt das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver fest. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.|
|[Set-CcCredential](set-cccredential.md)|Legt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung fest.|
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md)|Gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder Edgeserver gespeichert ist.|
|[Set-CcSiteDirectory](set-ccsitedirectory.md)|Legt das Verzeichnis fest, in dem Konfigurationsdateien auf Standortebene für Cloud Connector gespeichert werden. Der Ordner enthält die Basis-VHD- und Cloud Connector-Konfigurationsdateien.|
|[Start-CcDownload](start-ccdownload.md)|Lädt die Cloud Connector-Bits und die MSI-Datei synchron herunter.|
|[Start-CcLogging](start-cclogging.md)|Generiert das Protokoll für eingehende und ausgehende Anrufe für eine Cloud Connector-Appliance.|
|[Stop-CcLogging](stop-cclogging.md)|Beendet das Generieren des Protokolls für eingehende und ausgehende Anrufe für eine Cloud Connector-Appliance.|
|[Switch-CcVersion](switch-ccversion.md)|Trennt die ausgeführte Appliance und wechselt zu einer neu bereitgestellten Oder Sicherungsanwendung.|
|[Uninstall-CcAppliance](uninstall-ccappliance.md)|Deinstalliert die ausgeführte Cloud Connector-Appliance vom Hostserver.|
|[Unregister-CcAppliance](unregister-ccappliance.md)|Hebt die Registrierung der aktuellen Cloud Connector-Appliance von einem PSTN-Standort in der Onlinemandantenkonfiguration auf.|
|[Update-CcCACertificate](update-cccacertificate.md) <p> Version 2.0 und höher|Installiert den Zertifizierungsstellendienst-AD-Server erneut, um ein neues Stammzertifizierungsstellenzertifikat zu erstellen.|
|[Update-CcServerCertificate](update-ccservercertificate.md) <p> Version 2.0 und höher|Erneuert die Zertifikate für Cloud Connector, wenn sie bald ablaufen oder bereits abgelaufen sind.|
