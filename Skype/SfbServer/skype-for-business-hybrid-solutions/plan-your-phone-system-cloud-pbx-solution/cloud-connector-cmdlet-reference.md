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
description: In der folgenden Tabelle werden die Cmdlets von Skype for Business Cloud Connector Edition mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgelistet.
ms.openlocfilehash: c82d81fe19af7c0f305ce18e0bbce83f944b5d73
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803715"
---
# <a name="cloud-connector-cmdlet-reference"></a>Cloud Connector cmdlet reference
 
In der folgenden Tabelle werden die Cmdlets von Skype for Business Cloud Connector Edition mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgelistet.
  
> [!NOTE]
> Sie müssen alle Cmdlets auf dem Cloud Connector-Hostcomputer ausführen, und Sie müssen die PowerShell-Sitzung als Administrator ausführen. 
  
|**Cmdlet-Name**|**Beschreibung**|
|:-----|:-----|
|[Backup-CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Version 1.4.2 und höher  <br/> |Sichert den Zertifizierungsstellendienst in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Erstellt eine Datei einer virtuellen Basisfestplatte (VHDX) und verwendet dazu eine vom Kunden bereitgestellte ISO-Datei von Windows Server 2012 R2. Die VHDX-Datei wird bei der Bereitstellung von Cloud Connector verwendet.   <br/> |
|[Enter-CcUpdate](enter-ccupdate.md) <br/> |Bereitet den Cloud Connector-Hostserver für den Updateprozess vor, indem er in den Wartungsmodus versetzt wird. Die Appliance wird "entleert"; Das bedeutet, dass alle vorhandenen Anrufe abgeschlossen sind, aber neue Anrufe abgelehnt werden.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Beendet den Update Wartungsmodus auf dem Cloud Connector-Hostserver.  <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> |  Exportiert eine Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition-Hostserver. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Exportiert eine Beispielkonfigurationsdatei (. ini) für eine Cloud Connector in das Appliance-Verzeichnis einer Cloud Connector-Appliance. Sie können die Datei für Ihre Bereitstellung ändern und umbenennen.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Version 1.4.2 und höher   <br/> |Exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Cloud Connector-Hostserver.  <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Ruft das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.  <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis, in dem die Protokolle für eine Cloud Connector-Appliance gespeichert sind.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Version 2,1 und höher  <br/> |Enthält Diagnoseinformationen für die Cloud Connector-Appliance.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Gibt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung zurück.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Gibt den Pfad der externen Zertifikatsdatei für die Cloud Connector-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem die Konfigurationsdateien auf Standortebene gespeichert werden. Der Ordner enthält die Basis-VHD-und Cloud Connector-Installationsdateien. Dieser Ordner sollte für alle anderen Appliances einer Cloud Connector-Website freigegeben werden.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis, in dem die Protokolle auf Websiteebene für Cloud Connector gespeichert sind.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Version 2.0 und höher  <br/> |Gibt die Version einer Cloud Connector-Instanz zurück. „Get-CCVersion“ kann nur auf dem Cloud Connector-Hostcomputer verwendet werden.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Version 2.0 und höher  <br/> |Importiert die Skype for Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf den Cloud Connector-Hostserver.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installiert die Cloud Connector-Appliance, einschließlich der virtuellen Computer für AD, Central Management Store, Mediation Server und Edgeserver, auf dem Host Server.  <br/> |
|[Publish-CcAppliance](publish-ccappliance.md) <br/> | Ruft Informationen zur höheren Verfügbarkeit aus der Online Mandanten Konfiguration ab und veröffentlicht Sie in der Cloud Connector-Appliance auf dem Hostserver. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registriert Appliance-Informationen für einen PSTN-Standort in einer Onlinemandantenkonfiguration. Eine Appliance muss registriert sein, bevor Sie vom Cloud Connector-Verwaltungsdienst bereitgestellt und verwaltet werden kann. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt die Zertifizierungsstellen-Dienst Sicherungs\<Datei\>"SiteRootDirectory \CA\SfB CCE root. p12" im Ordner "Zertifizierungsstelle" unter dem Website Freigabeverzeichnis für Cloud Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt ältere Serverzertifikate aus dem zentralen Verwaltungsspeicher, vom Vermittlungsserver und vom Edgeserver, nachdem Sie das Cmdlet „Renew-CcCACertificate“ oder „Renew CcServerCertificate“ ausgeführt haben.  <br/> |
|[Renew-CcCACertificate](renew-cccacertificate.md) <br/> Nur Version 1.4.2  <br/> |Installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.  <br/> |
|[Renew-CcServerCertificate](renew-ccservercertificate.md) <br/> Nur Version 1.4.2  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn diese in Kürze ablaufen oder bereits abgelaufen sind.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Version 1.4.2 und höher  <br/> |Setzt die Zertifizierungsstellenserver zurück, um ein neues Zertifizierungsstellenzertifikat zu installieren.  <br/> |
|[Restore-CcCredentials](restore-cccredentials.md) <br/> Version 2,1 und höher  <br/> |Bereinigt die Anmeldeinformationen und fordert Sie auf, alle für die aktuelle Cloud Connector-Bereitstellung verwendeten Anmeldeinformationen erneut einzugeben.  <br/> |
|[Search-CcLog](search-cclog.md) <br/> |Durchsucht die eingehenden und ausgehenden Anrufprotokolle im Protokollverzeichnis der Cloud Connector-Appliance  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Legt das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver fest. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Legt die Anmeldeinformationen für die aktuelle Cloud Connector-Bereitstellung fest.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder den Edgeserver gespeichert ist.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Websiteebene für Cloud Connector gespeichert werden. Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Downloadet die Bits und die MSI-Datei für Cloud-Connectors synchron.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Generiert das eingehende und ausgehende Anrufprotokoll für eine Cloud Connector-Appliance.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Beendet das Generieren des eingehenden und ausgehenden Anrufprotokolls für eine Cloud Connector-Appliance.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Trennt die Verbindung der ausgeführten Appliance und wechselt zu einer neu bereitgestellten Appliance oder Sicherungsappliance.   <br/> |
|[Uninstall-CcAppliance](uninstall-ccappliance.md) <br/> |Deinstalliert die ausgeführte Cloud Connector-Appliance vom Hostserver.  <br/> |
|[Unregister-CcAppliance](unregister-ccappliance.md) <br/> |Hebt die Registrierung der aktuellen Cloud Connector-Appliance von einer PSTN-Website in der Konfiguration des Online Mandanten auf.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Version 2.0 und höher  <br/> |Installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Version 2.0 und höher  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn diese in Kürze ablaufen oder bereits abgelaufen sind.  <br/> |
   

