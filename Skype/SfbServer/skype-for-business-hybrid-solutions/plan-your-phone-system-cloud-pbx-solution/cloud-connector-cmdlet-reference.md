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
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: In der folgenden Tabelle sind die Skype for Business Cloud Connector Edition-Cmdlets mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgeführt.
ms.openlocfilehash: 3739518dd8ddcd17bce8108228d0d643ebaa79a4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092933"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cmdlet-Referenz für Cloud Connector
 
> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

In der folgenden Tabelle sind die Skype for Business Cloud Connector Edition-Cmdlets mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgeführt.
  
> [!NOTE]
> Sie müssen alle Cmdlets auf dem Cloud Connector-Hostcomputer ausführen und die PowerShell-Sitzung als Administrator ausführen. 
  
|**Name des Cmdlets**|**Beschreibung**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Version 1.4.2 und höher  <br/> |Sichert den Zertifizierungsstellendienst in einer Datei und speichert ihn im Ordner der Zertifizierungsstelle unter dem Websitefreigabeverzeichnis.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Erstellt eine virtuelle Basis-Festplattendatei (VHDX) unter Verwendung einer vom Kunden bereitgestellten Windows Server 2012 R2-ISO-Datei. Die VHDX-Datei wird während der Bereitstellung vonCloud Connector verwendet.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Bereitet den Cloud Connector-Hostserver auf den Updatevorgang vor, indem er in den Wartungsmodus versetzt wird. Die Appliance ist "entleert". Das heißt, alle vorhandenen Anrufe werden abgeschlossen, neue Anrufe werden jedoch abgelehnt.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Beendet den Updatewartungsmodus auf dem Cloud Connector-Hostserver.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Exportiert eine Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition-Hostserver. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exportiert eine Cloud Connector-Beispielkonfigurationsdatei (.ini) in das Applianceverzeichnis einer Cloud Connector-Appliance. Sie können die Für Die Bereitstellung zu verwendende Datei ändern und umbenennen.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Version 1.4.2 und höher  <br/> |Exportiert das Stammzertifizierungsstellenzertifikat in eine lokale Datei auf dem Cloud Connector-Hostserver.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Ruft das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver ab. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem Protokolle für eine Cloud Connector-Appliance gespeichert werden.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Version 2.1 und höher  <br/> |Stellt Diagnoseinformationen für die Cloud Connector-Appliance zur Verfügung.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Gibt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung zurück.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Gibt den pfad der externen Zertifikatdatei für die Cloud Connector-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem Konfigurationsdateien auf Standortebene gespeichert werden. Der Ordner enthält die Basis-VHD- und Cloud Connector-Installationsdateien. Dieser Ordner sollte für alle anderen Appliances einer Cloud Connector-Website freigegeben werden.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Websiteebene für Cloud Connector gespeichert werden.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Version 2.0 und höher  <br/> |Gibt die Version in der Cloud Connector-Instanz zurück. Get-CCVersion kann nur auf dem Hostcomputer von Cloud Connector verwendet werden.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Version 2.0 und höher  <br/> |Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installiert die Cloud Connector-Appliance – einschließlich des virtuellen AD-, zentralen Verwaltungsspeichers, Vermittlungsservers und Edgeservers – auf dem Hostserver.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Ruft Hochverfügbarkeitsinformationen aus der Konfiguration des Online-Mandanten ab und veröffentlicht sie in der Cloud Connector-Appliance auf dem Hostserver. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registriert Applianceinformationen an einem PSTN-Standort in einer Online-Mandantenkonfiguration. Eine Appliance muss registriert werden, bevor sie vom Cloud Connector-Verwaltungsdienst bereitgestellt und verwaltet werden kann. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt die Sicherungsdatei des Zertifizierungsstellendiensts \<SiteRootDirectory\> "\CA\SfB CCE Root.p12" im Ordner der Zertifizierungsstelle unter dem Websitefreigabeverzeichnis für Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt legacy server certificates on the Central Management Store, Mediation Server, and Edge Server after you execute the Renew-CcCACertificate or Renew CcServerCertificate cmdlets.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Nur Version 1.4.2  <br/> |Installiert den Zertifizierungsstellendienst AD Server erneut, um ein neues Stammzertifizierungsstellenzertifikat zu erstellen.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Nur Version 1.4.2  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn sie bald ablaufen oder bereits abgelaufen sind.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Version 1.4.2 und höher  <br/> |Setzt die Zertifizierungsstelleserver zurück, um ein neues Zertifizierungsstellezertifikat zu installieren.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Version 2.1 und höher  <br/> |Bereinigt Anmeldeinformationen und fordert Sie auf, alle anmeldeinformationen erneut ein, die für die aktuelle Cloud Connector-Bereitstellung verwendet werden.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Durchsucht die Protokolle eingehender und ausgehender Anrufe im Protokollverzeichnis der Cloud Connector-Appliance  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Legt das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver fest. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Legt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung fest.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder edgeserver gespeichert wird  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Legt das Verzeichnis fest, in dem Konfigurationsdateien auf Standortebene für Cloud Connector gespeichert werden. Der Ordner enthält die Basis-VHD- und Cloud Connector-Konfigurationsdateien.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Lädt die Cloud Connector-Bits und die MSI-Datei synchron herunter.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Generiert das eingehende und ausgehende Anrufprotokoll für eine Cloud Connector-Appliance.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Beendet die Generierung des eingehenden und ausgehenden Anrufprotokolls für eine Cloud Connector-Appliance.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Trennt die ausgeführte Appliance und wechselt zu einer neu bereitgestellten oder Sicherungs-Appliance.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Deinstalliert die ausgeführte Cloud Connector-Appliance vom Hostserver.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Entfernt die Registrierung der aktuellen Cloud Connector-Appliance von einem PSTN-Standort in der Online-Mandantenkonfiguration.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Version 2.0 und höher  <br/> |Installiert den Zertifizierungsstellendienst AD Server erneut, um ein neues Stammzertifizierungsstellenzertifikat zu erstellen.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Version 2.0 und höher  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn sie bald ablaufen oder bereits abgelaufen sind.  <br/> |
