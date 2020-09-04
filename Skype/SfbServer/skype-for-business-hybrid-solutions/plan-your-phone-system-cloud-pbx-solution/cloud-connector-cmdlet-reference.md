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
description: In der folgenden Tabelle sind die Cmdlets für die Skype for Business Cloud Connector Edition mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgeführt.
ms.openlocfilehash: 8d33cd8c493c3acc165661e5af80625e773e2d0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359051"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cmdlet-Referenz für Cloud Connector
 
> [!Important]
> Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen. Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

In der folgenden Tabelle sind die Cmdlets für die Skype for Business Cloud Connector Edition mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgeführt.
  
> [!NOTE]
> Sie müssen alle Cmdlets auf dem Cloud Connector-Hostcomputer ausführen, und Sie müssen die PowerShell-Sitzung als Administrator ausführen. 
  
|**Name des Cmdlets**|**Beschreibung**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Version 1.4.2 und höher  <br/> |Sichert den Zertifizierungsstellendienst in einer Datei und speichert ihn im Ordner "Zertifizierungsstelle" unter dem Website Freigabeverzeichnis.     <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Erstellt eine virtuelle Basisfestplatte (VHDX) mit einer vom Kunden bereitgestellten Windows Server 2012 R2-ISO-Datei. Die VHDX-Datei wird während des Deployment-ofCloud-Konnektors verwendet.  <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Bereitet den Cloud Connector-Hostserver für den Updateprozess vor, indem er ihn in den Wartungsmodus versetzen lässt. Die Appliance wird "entleert"; Das heißt, alle vorhandenen Anrufe werden abgeschlossen, aber neue Anrufe werden abgelehnt.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Beendet den Aktualisierungs Wartungsmodus auf dem Cloud Connector-Hostserver.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> | Exportiert eine Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition-Hostserver. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exportiert eine Cloud Connector-Beispielkonfigurationsdatei (INI-Datei) in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei ändern und umbenennen, die für Ihre Bereitstellung verwendet werden soll.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Version 1.4.2 und höher  <br/> |Exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Cloud Connector-Hostserver.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Ruft das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver ab. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem Protokolle für eine Cloud Connector-Appliance gespeichert werden..  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Version 2,1 und höher  <br/> |Enthält Diagnoseinformationen für die Cloud Connector-Appliance.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Gibt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung zurück.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Gibt den Pfad der externen Zertifikatdatei für die Cloud Connector-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem Konfigurationsdateien auf Websiteebene gespeichert werden. Der Ordner enthält die Basis-VHD-und Cloud Connector-Installationsdateien. Dieser Ordner sollte für alle anderen Appliances einer Cloud Connector-Website freigegeben werden.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem die Protokolle auf Standortebene für Cloud Connector gespeichert werden.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Version 2,0 und höher  <br/> |Gibt die Version der Cloud Connector-Instanz zurück. Get-CCVersion kann nur auf dem Hostcomputer von Cloud Connector verwendet werden.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Version 2,0 und höher  <br/> |Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installiert die Cloud Connector-Appliance, einschließlich der virtuellen Computer für AD, zentraler Verwaltungsspeicher, Vermittlungsserver und Edgeserver auf dem Host Server.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Ruft Informationen zur hohen Verfügbarkeit aus der Online Mandanten Konfiguration ab und veröffentlicht Sie in der Cloud Connector-Appliance auf dem Hostserver. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registriert Appliance-Informationen an einem PSTN-Standort in einer Online Mandanten Konfiguration. Eine Appliance muss registriert werden, bevor Sie vom Cloud Connector-Verwaltungsdienst bereitgestellt und verwaltet werden kann. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt die Sicherungsdatei des Zertifizierungsstellendiensts " \<SiteRootDirectory\> \CA\SfB CCE root. p12" im Ordner "Zertifizierungsstelle" unter dem Standortfreigabe Verzeichnis für Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt Legacy Serverzertifikate auf dem zentraler Verwaltungsspeicher, Vermittlungsserver und Edgeserver, nachdem Sie die Cmdlets "Renew-cccacertificate" "oder" Renew ccservercertificate "" ausgeführt haben.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Nur Version 1.4.2  <br/> |Installiert den Ad-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Nur Version 1.4.2  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn Sie fast ablaufen oder bereits abgelaufen sind.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Version 1.4.2 und höher  <br/> |Setzt die Zertifizierungsstellenserver zurück, um ein neues Zertifikat Zertifizierungsstellenzertifikat zu installieren.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Version 2,1 und höher  <br/> |Bereinigt die Anmeldeinformationen und fordert Sie auf, alle Anmeldeinformationen erneut einzugeben, die für die aktuelle Cloud Connector-Bereitstellung verwendet werden.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Durchsucht die Protokolle für ein-und ausgehende Anrufe im Cloud Connector Appliance-Protokollverzeichnis.  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Legt das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver fest. Alle Bereitstellungsdateien werden in diesem Verzeichnis gespeichert.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Legt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung fest.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder Edgeserver gespeichert wird.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Cloud Connector gespeichert werden. Der Ordner enthält die Basis-VHD-und Cloud Connector-Konfigurationsdateien.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Lädt die Cloud Connector-Bits und die MSI-Datei synchron herunter.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Generiert das Protokoll für ein-und ausgehende Anrufe für eine Cloud Connector-Appliance.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Beendet das Generieren der eingehenden und ausgehenden Anrufprotokolle für eine Cloud Connector-Appliance.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Trennt die Verbindung der ausgeführten Appliance und wechselt zu einer neu bereitgestellten oder Sicherungs-Appliance.  <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Deinstalliert die laufende Cloud Connector-Appliance vom Hostserver.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Hebt die Registrierung der aktuellen Cloud Connector-Appliance von einem PSTN-Standort in der Online Mandanten Konfiguration auf.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Version 2,0 und höher  <br/> |Installiert den Ad-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Version 2,0 und höher  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn Sie fast ablaufen oder bereits abgelaufen sind.  <br/> |
   

