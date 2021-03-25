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
ms.openlocfilehash: fea78c6b1b6ba3b2e644fef71d78b94aa3a244b7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109131"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Upgrade auf eine neue Version von Cloud Connector

> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)
 
Erfahren Sie mehr über das Upgrade Ihrer Cloud Connector Edition-Bereitstellung.
  
Wenn Sie ein Onlineverwaltungs-Mandantenkonto eingerichtet haben und automatische Updates aktiviert haben, wird Ihre vorhandene Bereitstellung von Skype for Business Cloud Connector Edition automatisch auf die neuere Version aktualisiert – entsprechend der Konfiguration des Zeitfensters für automatische Updates. Sie können auch ein manuelles Upgrade durchführen. 
  
Cloud Connector Edition Versionen 1.4.1 und höher führen standardmäßig automatische Updates durch. Informationen zum manuellen Upgrade auf die neueste Version (2.1) finden Sie unter [Upgrade a single site to a new version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) later in this topic.
  
Für das automatische Update muss der Cloud Connector-Dienst ausgeführt werden. In den folgenden Schritten wird der Prozess für automatische Updates beschrieben:
  
- Der automatische Updatevorgang wird entsprechend dem Zeitplan ausgeführt, den Sie für automatische Updates konfiguriert haben.
    
- Aktualisierungsaufgaben des Betriebssystems
    
  - Überprüfen und Herunterladen von Betriebssystemupdates auf alle Cloud Connector-VMs. 
    
  - Installieren und aktualisieren Sie alle VMs des Cloud Connector nach und nach, und starten Sie sie neu.
    
  - Überprüfen Sie nach dem Neustart der virtuellen Computer des CloudConnector, ob ein weiterer Neustart erforderlich ist.
    
  - Nachdem die virtuellen Computer des Cloudconnector erfolgreich gepatcht wurden, wiederholen Sie den Vorgang für den Cloud Connector-Hostcomputer.
    
  - Nachdem der Cloud Connector-Hostcomputer erfolgreich gestartet wurde, werden alle ausstehenden Betriebssystemupdateaufgaben abgeschlossen.
    
- Cloud Connector-Updateaufgaben
    
  - Laden Sie die Versionsdatei von der Downloadwebsite herunter, und überprüfen Sie sie.
    
  - Laden Sie die MSI-Datei der neuen Version herunter. 
    
  - Deinstallieren Sie die alte #A0 installieren Sie die neue msi-Datei.
    
  - Laden Sie die neue Version von Skype for Business-Bits herunter.
    
  - Registrieren Sie die Appliance, indem Sie Register-CcAppliance aufrufen.
    
  - Installieren Sie die neue Cloud Connector-Version.
    
  - Entleeren Sie die alte Appliance, und wechseln Sie die Netzwerkverbindung zur neuen Appliance.
    
> [!NOTE]
>  Wenn Cloud Connector auf einen neuen Build aktualisiert wird, werden Cloud Connector-Cmdlets möglicherweise nicht aktualisiert. Dies kann z. B. passieren, wenn ein PowerShell-Fenster geöffnet bleibt, während die automatische Aktualisierung erfolgt. Zum Laden der aktualisierten Cmdlets können Sie einen der folgenden Schritte ausführen:> Schließen sie PowerShell auf der Cloud Connector-Appliance, und öffnen Sie dann PowerShell.> Oder führen Sie Import-Module CloudConnector -Force aus.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Upgrade einer einzelnen Website auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Wenn sich am Standort, den Sie aktualisieren möchten, nur eine Appliance befindet, gehen Sie wie folgt vor:
  
1. Deinstallieren Sie die vorhandene Cloud Connector-Version unter Programme und Features **\> der \> Systemsteuerung.**
    
2. Installieren Sie die neue Version von CloudConnector.msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller) von .
    
3. Vergewissern Sie sich, dass CloudConnector.ini für die zu installierende Version und alle erforderlichen Werte für Ihre Umgebung aktualisiert haben. Sie können die INI-Datei aus einer früheren Version nicht verwenden. Wenn Sie ein Upgrade von Cloud Connector durchführen, lesen Sie das Thema [Prepare your Cloud Connector appliance,](prepare-your-cloud-connector-appliance.md) und stellen Sie sicher, dass SiteName und EnableReferSupport auf den richtigen Wert in der datei CloudConnector.ini sind.
    
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

Wenn sich mehrere Appliances am Standort befindet, führen Sie die vorherigen Schritte aus, um die einzelnen Appliances nach dem anderen zu aktualisieren.
  
Wenn Sie Domänenadministrator, Virtueller Computeradministrator, Administrator für den abgesicherten Modus und Mandantenadministratorinformationen aktualisieren möchten, können Sie das Cmdlet mit dem  _Parameter UpdateAllCredentials_ ausführen, um alle Anmeldeinformationen zurückzusetzen:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Wenn Sie dann mit dem Upgrade auf eine neue Version beginnen, werden Sie zur Eingabe der neuen Anmeldeinformationen heraufgestuft. 
  
Wenn Sie nur Ihre Mandantenadministratoranmeldeinformationen zurücksetzen möchten, führen Sie das folgende Cmdlet aus:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Upgrade mehrerer Websites auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Führen Sie die Schritte für das Upgrade eines einzelnen Standorts durch, und aktualisieren Sie jeweils einen Standort für jeden Standort in Ihrer Bereitstellung. Stellen Sie nach dem Upgrade der einzelnen Website [sicher,](validate-your-cloud-connector-deployment.md) und überprüfen Sie die Cloud Connector-Bereitstellung.
