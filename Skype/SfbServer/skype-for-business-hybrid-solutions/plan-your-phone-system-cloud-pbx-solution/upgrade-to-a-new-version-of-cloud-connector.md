---
title: Upgrade auf eine neue Version von Cloud Connector
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
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Erfahren Sie, wie Sie Ihre Cloud Connector Edition-Bereitstellung aktualisieren.
ms.openlocfilehash: 3398fcdf9437a496cf5f4fb94f0fb92dc6a1da42
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58588427"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Upgrade auf eine neue Version von Cloud Connector

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.
 
Erfahren Sie, wie Sie Ihre Cloud Connector Edition-Bereitstellung aktualisieren.
  
Wenn Sie ein Onlineverwaltungsmandantenkonto eingerichtet und automatische Updates aktiviert haben, wird Ihre vorhandene Bereitstellung von Skype for Business Cloud Connector Edition automatisch auf die neuere Version aktualisiert – entsprechend ihrer Automatischen Updatezeitfensterkonfiguration. Sie können auch ein manuelles Upgrade durchführen. 
  
Cloud Connector Edition, Version 1.4.1 und höher, führt standardmäßig automatische Updates durch. Wenn Sie manuell auf die neueste Version (2.1) aktualisieren möchten, finden Sie weitere Informationen unter [Upgrade einer einzelnen Website auf eine neue Version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) weiter unten in diesem Thema.
  
Für die automatische Aktualisierung muss der Cloud Connector-Dienst ausgeführt werden. In den folgenden Schritten wird der Prozess für automatische Updates beschrieben:
  
- Der Prozess der automatischen Aktualisierung wird gemäß dem Zeitplan ausgeführt, den Sie für automatische Updates konfiguriert haben.
    
- Updateaufgaben des Betriebssystems
    
  - Überprüfen und herunterladen Sie Betriebssystemupdates für alle Cloud Connector-VMs. 
    
  - Installieren und aktualisieren Sie alle Virtuellen Cloud Connector-Computer nacheinander, und starten Sie sie neu.
    
  - Überprüfen Sie nach dem Neustart des Cloud Connector-VMs, ob ein weiterer Neustart erforderlich ist.
    
  - Nachdem die Cloud Connector-VMs erfolgreich gepatcht wurden, wiederholen Sie den Vorgang für den Cloud Connector-Hostcomputer.
    
  - Nachdem der Cloud Connector-Hostcomputer erfolgreich gestartet wurde, werden alle ausstehenden Updateaufgaben des Betriebssystems abgeschlossen.
    
- Cloud Connector-Updateaufgaben
    
  - Laden Sie die Versionsdatei von der Downloadwebsite herunter, und überprüfen Sie sie.
    
  - Laden Sie die neue Version .msi Datei herunter. 
    
  - Deinstallieren Sie die alte MSI-Datei. installieren Sie die neue MSI-Datei.
    
  - Laden Sie die neue Version von Skype for Business Bits herunter.
    
  - Registrieren Sie die Appliance, indem Sie Register-CcAppliance aufrufen.
    
  - Installieren Sie die neue Cloud Connector-Version.
    
  - Entleeren Sie die alte Appliance, und wechseln Sie die Netzwerkverbindung zur neuen Appliance.
    
> [!NOTE]
>  Wenn Cloud Connector auf einen neuen Build aktualisiert wird, werden Cloud Connector-Cmdlets möglicherweise nicht aktualisiert. Dies kann beispielsweise passieren, wenn ein PowerShell-Fenster geöffnet bleibt, während die automatische Aktualisierung erfolgt. Zum Laden der aktualisierten Cmdlets können Sie einen der folgenden Schritte ausführen: > PowerShell in der Cloud Connector-Appliance schließen und dann PowerShell.> erneut öffnen oder Import-Module CloudConnector -Force ausführen.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Upgrade einer einzelnen Website auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Wenn nur eine Appliance an dem Standort vorhanden ist, den Sie aktualisieren möchten, gehen Sie wie folgt vor:
  
1. Deinstallieren Sie die vorhandene Cloud Connector-Version in **den \> Systemsteuerungsprogrammen und \> -features.**
    
2. Installieren Sie die neue Version von CloudConnector.msi von [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Vergewissern Sie sich, dass Sie über die datei CloudConnector.ini für die Version verfügen, die Sie installieren, und dass Sie alle erforderlichen Werte für Ihre Umgebung aktualisiert haben. Sie können die .ini Datei aus einer vorherigen Version nicht verwenden. Wenn Sie Cloud Connector aktualisieren, lesen Sie bitte das Thema ["Vorbereiten ihrer Cloud Connector-Appliance",](prepare-your-cloud-connector-appliance.md) und stellen Sie sicher, dass "SiteName" und "EnableReferSupport" auf den richtigen Wert in der CloudConnector.ini-Datei festgelegt sind.
    
4. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um die aktuelle Appliance zu registrieren:
    
   ```powershell
   Register-CcAppliance
   ```

5. Führen Sie das folgende Cmdlet aus, um die neueste Version herunterzuladen:
    
   ```powershell
   Start-CcDownload
   ```

6. Führen Sie das folgende Cmdlet aus, um die Installation zu starten: 
    
   ```powershell
   Install-CcAppliance -Upgrade
   ```

7. Führen Sie das folgende Cmdlet aus, um die neue Bereitstellung zu aktivieren und die vorherige Version zu deaktivieren:
    
   ```powershell
   Switch-CcVersion
   ```

Wenn sich mehrere Appliances am Standort befinden, führen Sie die vorherigen Schritte aus, um die einzelnen Appliances nacheinander zu aktualisieren.
  
Wenn Sie die Anmeldeinformationen für Domänenadministrator, Virtuelle Computer, Tresor modusadministrator und Mandantenadministrator aktualisieren möchten, können Sie das Cmdlet mit dem _Parameter "UpdateAllCredentials"_ ausführen, um alle Anmeldeinformationen zurückzusetzen:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Wenn Sie dann mit dem Upgrade auf eine neue Version beginnen, werden Sie höhergestuft, um die neuen Anmeldeinformationen einzugeben. 
  
Wenn Sie nur Ihre Mandantenadministratoranmeldeinformationen zurücksetzen möchten, führen Sie das folgende Cmdlet aus:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Upgrade mehrerer Websites auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Führen Sie die Schritte zum Aktualisieren eines einzelnen Standorts aus, und aktualisieren Sie jeweils einen Standort für jeden Standort in Ihrer Bereitstellung. Stellen Sie sicher, dass [Ihre Cloud Connector-Bereitstellung](validate-your-cloud-connector-deployment.md) nach dem Upgrade der einzelnen Standorte überprüft wird.
