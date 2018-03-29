---
title: Cmdlet-Referenz für Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 072b4bdc-0f1e-4fce-a41e-5c60d24556d5
description: In der folgenden Tabelle werden die Cmdlets von Skype for Business Cloud Connector Edition mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgelistet.
ms.openlocfilehash: 5528b7ef5d2fe0ccfab680f2300b444f0532a059
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="cloud-connector-cmdlet-reference"></a>Cmdlet-Referenz für Cloud Connector
 
In der folgenden Tabelle werden die Cmdlets von Skype for Business Cloud Connector Edition mit einer kurzen Beschreibung und Links zu weiteren Informationen aufgelistet.
  
> [!NOTE]
> Sie müssen alle Cmdlets auf dem Cloud Connector-Hostcomputer ausführen, und Sie müssen die PowerShell-Sitzung als Administrator ausführen. 
  
|**Name des Cmdlets**|**Beschreibung**|
|:-----|:-----|
|[Sicherung CcCertificationAuthority](backup-cccertificationauthority.md) <br/> Version 1.4.2 und höher  <br/> |Sichert den Zertifizierungsstellendienst in einer Datei und speichert diese im Zertifizierungsstellenordner unter dem Freigabeverzeichnis des Standorts.      <br/> |
|[Convert-CcIsoToVhdx](convert-ccisotovhdx.md) <br/> |Erstellt eine Datei einer virtuellen Basisfestplatte (VHDX) und verwendet dazu eine vom Kunden bereitgestellte ISO-Datei von Windows Server 2012 R2. Die VHDX-Datei wird bei der Bereitstellung von Cloud Connector verwendet.   <br/> |
|[Geben Sie CcUpdate](enter-ccupdate.md) <br/> |Bereitet den Cloud Connector-Hostserver auf den Updateprozess vor, indem es ihn in den Wartungsmodus versetzt. Die Einheit ist "ein Ausgleich vorgenommen"; d. h., alle aktuellen Anrufe abgeschlossen werden, aber neue Aufrufe zurückgewiesen.  <br/> |
|[Exit-CcUpdate](exit-ccupdate.md) <br/> |Beendet den Wartungsmodus für das Update auf dem Cloud Connector-Hostserver.    <br/> |
|[Export-CcConfiguration](export-ccconfiguration.md) <br/> |  Exportiert eine Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition-Hostserver. <br/> |
|[Export-CcConfigurationSampleFile](export-ccconfigurationsamplefile.md) <br/> |Cloud-Connector Beispielkonfigurationsdatei (ini-) exportiert in das Verzeichnis Appliance einer Cloud-Connector Appliance. Sie können die Datei für Ihre Bereitstellung ändern und umbenennen.  <br/> |
|[Export-CcRootCertificate](export-ccrootcertificate.md) <br/> Version 1.4.2 und höher  <br/> |Exportiert das Zertifikat der Stammzertifizierungsstelle in eine lokale Datei auf dem Cloud Connector-Hostserver.   <br/> |
|[Get-CcApplianceDirectory](get-ccappliancedirectory.md) <br/> |Ruft das Arbeitsverzeichnis auf dem Cloud Connector-Hostserver ab. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.    <br/> |
|[Get-CcApplianceLogDirectory](get-ccappliancelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis, in dem die Protokolle für eine Cloud-Connector Appliance gespeichert werden.  <br/> |
|[Get-CcApplianceStatus](get-ccappliancestatus.md) <br/> Version 2.1 oder höher  <br/> |Diagnoseinformationen für die Cloud Connector Appliance enthält.  <br/> |
|[Get-CcCredential](get-cccredential.md) <br/> |Gibt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung zurück.  <br/> |
|[Get-CcExternalCertificateFilePath](get-ccexternalcertificatefilepath.md) <br/> |Gibt den Pfad der externen Zertifikatdatei für die Cloud Connector-Bereitstellung zurück. Der Benutzer bereitet dieses Zertifikat vor.  <br/> |
|[Get-CcSiteDirectory](get-ccsitedirectory.md) <br/> |Zeigt das aktuelle Verzeichnis an, in dem die Konfigurationsdateien auf Standortebene gespeichert werden. Der Ordner enthält die Basis VHD und Cloud-Connector-Installationsdateien. In diesem Ordner sollten für alle anderen Einheiten einer Cloud-Connector-Website freigegeben werden.  <br/> |
|[Get-CcSiteLogDirectory](get-ccsitelogdirectory.md) <br/> |Zeigt das aktuelle Verzeichnis, in dem die Website Ebene Protokolle für Cloud-Connector gespeichert sind.  <br/> |
|[Get-CcVersion](get-ccversion.md) <br/> Version 2.0 und höher  <br/> |Gibt die Version einer Cloud Connector-Instanz zurück. „Get-CCVersion“ kann nur auf dem Cloud Connector-Hostcomputer verwendet werden.  <br/> |
|[Import-CcConfiguration](import-ccconfiguration.md) <br/> Version 2.0 und höher  <br/> |Importiert die Skype für Business Cloud Connector Edition-Konfiguration aus einer lokalen Datei auf die Cloud Connector-Hostserver.  <br/> |
|[Install-CcAppliance](install-ccappliance.md) <br/> |Installiert die Cloud Connector Appliance – AD, einschließlich virtuellen Computer zentralen Verwaltungsspeichers, Vermittlungsserver und Edge-Server – auf dem Hostserver.  <br/> |
|[Veröffentlichen von CcAppliance](publish-ccappliance.md) <br/> | Hohe Verfügbarkeit aus der online-Mandantenkonfiguration abgerufen und an die Cloud Connector Appliance auf dem Hostserver veröffentlicht wird. <br/> |
|[Register-CcAppliance](register-ccappliance.md) <br/> | Registriert Appliance-Informationen für einen PSTN-Standort in einer Onlinemandantenkonfiguration. Eine Einheit muss registriert werden, bevor es bereitgestellt und der Cloud Connector-Verwaltungsdienst verwaltet werden kann. <br/> |
|[Remove-CcCertificationAuthorityFile](remove-cccertificationauthorityfile.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt die Sicherungsdatei Certification Authority Service "\<SiteRootDirectory\>\CA\SfB CCE Root.p12" im Ordner "Zertifizierungsstelle" unter Freigeben Websiteverzeichnis für Cloud-Connector.  <br/> |
|[Remove-CcLegacyServerCertificate](remove-cclegacyservercertificate.md) <br/> Version 1.4.2 und höher  <br/> |Entfernt ältere Serverzertifikate aus dem zentralen Verwaltungsspeicher, vom Vermittlungsserver und vom Edgeserver, nachdem Sie das Cmdlet „Renew-CcCACertificate“ oder „Renew CcServerCertificate“ ausgeführt haben.  <br/> |
|[Erneuern CcCACertificate](renew-cccacertificate.md) <br/> Nur Version 1.4.2  <br/> |Installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.  <br/> |
|[Erneuern CcServerCertificate](renew-ccservercertificate.md) <br/> Nur Version 1.4.2  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn diese in Kürze ablaufen oder bereits abgelaufen sind.  <br/> |
|[Reset-CcCACertificate](reset-cccacertificate.md) <br/> Version 1.4.2 und höher  <br/> |Setzt die Zertifizierungsstellenserver zurück, um ein neues Zertifizierungsstellenzertifikat zu installieren.  <br/> |
|[Wiederherstellung CcCredentials](restore-cccredentials.md) <br/> Version 2.1 oder höher  <br/> |Bereinigt die Anmeldeinformationen und werden Sie aufgefordert, die alle für die aktuelle Cloud Connector-Bereitstellung verwendeten Anmeldeinformationen erneut eingeben.  <br/> |
|[Suche CcLog](search-cclog.md) <br/> |Durchsucht die Listen für ein- und ausgehende Anrufe im Protokollverzeichnis der Cloud Connector-Appliance.  <br/> |
|[Set-CcApplianceDirectory](set-ccappliancedirectory.md) <br/> |Legt das Arbeitsverzeichnis auf dem Hostserver Cloud-Connector. In diesem Verzeichnis werden alle Bereitstellungsdateien gespeichert.  <br/> |
|[Set-CcCredential](set-cccredential.md) <br/> |Legt die Anmeldeinformationen der aktuellen Cloud Connector-Bereitstellung fest.  <br/> |
|[Set-CcExternalCertificateFilePath](set-ccexternalcertificatefilepath.md) <br/> |Gibt den Pfad an, in dem das Zertifikat für den Vermittlungsserver oder den Edgeserver gespeichert ist.  <br/> |
|[Set-CcSiteDirectory](set-ccsitedirectory.md) <br/> |Legt das Verzeichnis fest, in dem die Konfigurationsdateien auf Standortebene für Cloud Connector gespeichert werden. Der Ordner enthält die Konfigurationsdateien für die Basis-VHD und für Cloud Connector.  <br/> |
|[Start-CcDownload](start-ccdownload.md) <br/> |Die Cloud Connector Bits und MSI-Datei heruntergeladen synchron.  <br/> |
|[Start-CcLogging](start-cclogging.md) <br/> |Eingehende und ausgehende Anrufprotokoll für eine Cloud-Connector Appliance generiert.  <br/> |
|[Stop-CcLogging](stop-cclogging.md) <br/> |Stopps Generieren von eingehenden und ausgehenden Anrufen melden Sie sich für eine Cloud-Connector Einheit.  <br/> |
|[Switch-CcVersion](switch-ccversion.md) <br/> |Trennt die Verbindung der ausgeführten Appliance und wechselt zu einer neu bereitgestellten Appliance oder Sicherungsappliance.   <br/> |
|[Deinstallieren von CcAppliance](uninstall-ccappliance.md) <br/> |Deinstalliert die ausgeführte Cloud Connector Appliance aus den Hostserver.  <br/> |
|[Aufheben der Registrierung CcAppliance](unregister-ccappliance.md) <br/> |Hebt die Registrierung der aktuellen Cloud Connector Appliance aus einer PSTN-Website in der Konfiguration der online-Mandanten.  <br/> |
|[Update-CcCACertificate](update-cccacertificate.md) <br/> Version 2.0 und höher  <br/> |Installiert den AD-Server für den Zertifizierungsstellendienst neu, um ein neues Zertifikat der Stammzertifizierungsstelle zu erstellen.  <br/> |
|[Update-CcServerCertificate](update-ccservercertificate.md) <br/> Version 2.0 und höher  <br/> |Erneuert die Zertifikate für Cloud Connector, wenn diese in Kürze ablaufen oder bereits abgelaufen sind.  <br/> |
   

