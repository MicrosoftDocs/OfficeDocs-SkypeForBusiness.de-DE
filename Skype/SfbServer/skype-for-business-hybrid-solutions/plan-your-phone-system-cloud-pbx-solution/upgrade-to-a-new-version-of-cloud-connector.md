---
title: Aktualisieren auf eine neue Version von Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Hier erfahren Sie, wie Sie Ihre Cloud Connector Edition-Bereitstellung aktualisieren.
ms.openlocfilehash: c340b7325c95d25212c9c1f77f9379a25708cea8
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002045"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Upgrade to a new version of Cloud Connector
 
Hier erfahren Sie, wie Sie Ihre Cloud Connector Edition-Bereitstellung aktualisieren.
  
Wenn Sie ein Mandantenkonto für die Onlineverwaltung eingerichtet und automatische Aktualisierungen aktiviert haben, wird Ihre vorhandene Bereitstellung von Skype for Business Cloud Connector Edition entsprechend Ihrer Zeitfensterkonfiguration für automatische Updates automatisch auf die neuere Version aktualisiert. Sie können auch manuelle Upgrades ausführen.  
  
Cloud Connector Edition-Versionen 1.4.1 und höher führen standardmäßig automatische Updates aus. Wenn Sie manuell auf die neueste Version (2,1) aktualisieren möchten, lesen Sie [Aktualisieren einer einzelnen Website auf eine neue Version](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) weiter unten in diesem Thema.
  
Für die automatische Aktualisierung muss der Cloud Connector-Dienst ausgeführt werden. In den folgenden Schritten wird der Prozess für automatische Updates beschrieben:
  
- Der Prozess für automatische Updates wird gemäß dem Zeitplan ausgeführt, den Sie für automatische Updates konfiguriert haben.
    
- Tasks für Betriebssystemupdates
    
  - Überprüfen und Herunterladen von Betriebssystemupdates auf alle Cloud Connector-VMS 
    
  - Installieren und aktualisieren Sie alle VMs des Cloud Connectors nacheinander, und starten Sie den Computer neu.
    
  - Überprüfen Sie nach dem Neustart des Cloud Connector VMS, ob ein weiterer Neustart erforderlich ist.
    
  - Nachdem der Cloud Connector VMS erfolgreich gepatcht wurde, wiederholen Sie den Vorgang für den Cloud Connector-Hostcomputer.
    
  - Nachdem der Cloud Connector-Hostcomputer erfolgreich gestartet wurde, sind alle ausstehenden Betriebssystem Aktualisierungsaufgaben abgeschlossen.
    
- Aktualisierungsaufgaben für Cloud Connectors
    
  - Die Versionsdatei wird von der Downloadwebsite heruntergeladen und überprüft.
    
  - Die neue Version der MSI-Datei wird heruntergeladen.  
    
  - Deinstallieren Sie die alte MSI-Datei. Installieren Sie die neue MSI-Datei.
    
  - Laden Sie die neue Version von Skype for Business-Bits herunter.
    
  - Die Appliance wird durch Aufrufen von „Register-CcAppliance“ registriert.
    
  - Installieren Sie die neue Cloud Connector-Version.
    
  - Die alte Appliance wird ausgeglichen, und die Netzwerkverbindung wird auf die neue Appliance umgeschaltet.
    
> [!NOTE]
>  Wenn der Cloud Connector in einem neuen Build aktualisiert wird, werden die Cmdlets für Cloud Connector möglicherweise nicht aktualisiert. Dies kann beispielsweise vorkommen, wenn ein PowerShell-Fenster geöffnet bleibt, während die automatische Aktualisierung erfolgt. Um die aktualisierten Cmdlets zu laden, führen Sie einen der folgenden Schritte aus: #a0 schließen Sie PowerShell auf der Cloud Connector-Appliance, und öffnen Sie dann PowerShell. #a1, oder führen Sie Import-Module CloudConnector-Force aus.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Aktualisieren eines einzelnen Standorts auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Wenn der zu aktualisierende Standort nur eine Appliance umfasst, gehen Sie wie folgt vor:
  
1. Deinstallieren Sie die vorhandene Cloud Connector-Version unter Programme **und Funktionen der System \> \> **Steuerung.
    
2. Installieren Sie die neue Version von CloudConnector. msi [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller)aus.
    
3. Vergewissern Sie sich, dass Sie über die Datei „CloudConnector.ini“ für die zu installierende Version verfügen und dass Sie alle erforderlichen Werte für Ihre Umgebung aktualisiert haben. Die INI-Datei einer früheren Version kann nicht verwendet werden. Wenn Sie Cloud Connector aktualisieren, lesen Sie das Thema Vorbereiten der [Cloud Connector-Appliance](prepare-your-cloud-connector-appliance.md) , und stellen Sie sicher, dass Sitename und EnableReferSupport auf den richtigen Wert in der Datei CloudConnector. ini eingestellt sind.
    
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

Wenn sich mehr als eine Appliance am Standort befindet, führen Sie die obigen Schritte aus, um die einzelnen Appliances nacheinander zu aktualisieren.
  
Wenn Sie den Domänenadministrator, den Administrator für virtuelle Computer, den Administrator für den abgesicherten Modus und die Administratoranmeldeinformationen für Mandanten aktualisieren möchten, können Sie das Cmdlet mit dem _UpdateAllCredentials_ -Parameter ausführen, um alle Anmeldeinformationen zurückzusetzen:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

Wenn Sie dann mit dem Upgrade auf eine neue Version beginnen, werden Sie aufgefordert, die neuen Anmeldeinformationen einzugeben.  
  
Wenn Sie nur die Anmeldeinformationen des Mandantenadministrators zurücksetzen möchten, führen Sie das folgende Cmdlet aus:
  
```powershell
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Upgrade von mehreren Standorten auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Führen Sie die Schritte für das Upgrade eines einzelnen Standorts nacheinander für jeden Standort in Ihrer Bereitstellung aus. Führen Sie nach dem Upgrade jedes Standorts unbedingt den Schritt [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) aus.
  

