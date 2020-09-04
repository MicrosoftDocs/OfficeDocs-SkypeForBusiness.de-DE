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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Erfahren Sie mehr über das Upgrade Ihrer Cloud Connector Edition-Bereitstellung.
ms.openlocfilehash: dc9473dbf605f00df76daa1a88a29c7d5ed65fd8
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359291"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Upgrade auf eine neue Version von Cloud Connector

> [!Important]
> Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen. Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.
 
Erfahren Sie mehr über das Upgrade Ihrer Cloud Connector Edition-Bereitstellung.
  
Wenn Sie ein Online Verwaltungs Mandantenkonto eingerichtet und automatische Updates aktiviert haben, wird Ihre vorhandene Bereitstellung von Skype for Business Cloud Connector Edition automatisch auf die neuere Version aktualisiert – entsprechend der Konfiguration für das Zeitfenster für die automatische Aktualisierung. Sie können auch ein Manuelles Upgrade durchführen. 
  
Cloud Connector Edition-Versionen 1.4.1 und höher führen standardmäßig automatische Updates aus. Wenn Sie manuell auf die neueste Version (2,1) aktualisieren möchten, finden Sie weitere Informationen unter [Upgrade an Single Site to a New Version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) weiter unten in diesem Thema.
  
Für die automatische Aktualisierung muss der Cloud Connector-Dienst aktiv sein. In den folgenden Schritten wird der Prozess für automatische Updates beschrieben:
  
- Der automatische Updateprozess wird entsprechend dem Zeitplan ausgeführt, den Sie für automatische Updates konfiguriert haben.
    
- Betriebssystem-Updateaufgaben
    
  - Überprüfen und Herunterladen von Betriebssystemupdates auf alle Cloud Connector-VMS. 
    
  - Installieren und aktualisieren Sie alle Cloud Connector-VMS nacheinander, und starten Sie neu.
    
  - Überprüfen Sie nach dem Neustart des Cloud Connector-VMS, ob ein anderer Neustart erforderlich ist.
    
  - Nachdem die Cloud Connector-VMS erfolgreich gepatcht wurden, wiederholen Sie den Vorgang für den Cloud Connector-Hostcomputer.
    
  - Nachdem der Cloud Connector-Hostcomputer erfolgreich gestartet wurde, sind alle ausstehenden Betriebssystem-Updateaufgaben abgeschlossen.
    
- Cloud Connector-Aktualisierungsaufgaben
    
  - Laden Sie die Versionsdatei von der Download Website herunter, und überprüfen Sie Sie.
    
  - Laden Sie die neue Version der MSI-Datei herunter. 
    
  - Deinstallieren Sie die alte MSI-Datei; Installieren Sie die neue MSI-Datei.
    
  - Laden Sie die neue Version von Skype for Business Bits herunter.
    
  - Registrieren Sie die Appliance durch Aufrufen von Register-ccappliance ".
    
  - Installieren Sie die neue Cloud Connector-Version.
    
  - Entleeren Sie die alte Appliance, und wechseln Sie die Netzwerkverbindung zur neuen Appliance.
    
> [!NOTE]
>  Wenn Cloud Connector für einen neuen Build aktualisiert wird, werden die Cloud Connector-Cmdlets möglicherweise nicht aktualisiert. Dies kann beispielsweise der Fall sein, wenn ein PowerShell-Fenster geöffnet bleibt, während die automatische Aktualisierung erfolgt. Führen Sie einen der folgenden Schritte aus, um die aktualisierten Cmdlets zu laden: > close PowerShell in der Cloud Connector-Appliance, und öffnen Sie dann PowerShell. > oder können Sie Import-Module "cloudconnector-Force ausführen.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Aktualisieren einer einzelnen Website auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Wenn es nur eine Appliance am Standort gibt, die Sie aktualisieren möchten, gehen Sie wie folgt vor:
  
1. Deinstallieren Sie die vorhandene Cloud Connector-Version in den Programmen ** \> \> und Funktionen der System**Steuerung.
    
2. Installieren Sie die neue Version von CloudConnector.msi von [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) .
    
3. Vergewissern Sie sich, dass Sie über die CloudConnector.ini Datei für die Version verfügen, die Sie installieren, und dass Sie alle erforderlichen Werte für Ihre Umgebung aktualisiert haben. Sie können die INI-Datei nicht aus einer früheren Version verwenden. Wenn Sie Cloud Connector aktualisieren, lesen Sie das Thema [prepare your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md) , und stellen Sie sicher, dass Sitename und "enablerefersupport" auf den korrekten Wert in der Datei CloudConnector.ini festgelegt sind.
    
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

Wenn sich mehr als eine Appliance am Standort befindet, führen Sie die oben beschriebenen Schritte aus, um die einzelnen Appliances nacheinander zu aktualisieren.
  
Wenn Sie die Anmeldeinformationen des Domänenadministrators, des Administrators virtueller Computer, des Administrators und des Mandanten für den sicheren Modus aktualisieren möchten, können Sie das Cmdlet mit dem Parameter  _UpdateAllCredentials_ ausführen, um alle Anmeldeinformationen zurückzusetzen:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Wenn Sie dann mit dem Upgrade auf eine neue Version beginnen, werden Sie zur Eingabe der neuen Anmeldeinformationen heraufgestuft. 
  
Wenn Sie nur Ihre mandantenadministrator-Anmeldeinformationen zurücksetzen möchten, führen Sie das folgende Cmdlet aus:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Aktualisieren mehrerer Websites auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Befolgen Sie die Schritte für das Upgrade eines einzelnen Standorts, und aktualisieren Sie jeweils einen Standort für jeden Standort in Ihrer Bereitstellung. Stellen Sie sicher, dass [Ihre Cloud Connector-Bereitstellung](validate-your-cloud-connector-deployment.md) nach dem Upgrade jeder Website überprüft wird.
  

