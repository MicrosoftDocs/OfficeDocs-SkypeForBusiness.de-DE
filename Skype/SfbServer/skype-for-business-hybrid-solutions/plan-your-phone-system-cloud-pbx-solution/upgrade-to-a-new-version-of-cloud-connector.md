---
title: Aktualisieren auf eine neue Version von Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: efbe25f2-faf5-41c7-8c95-dbc4a835a4a8
description: Informationen Sie zum Aktualisieren der Cloud Connector Edition-bereitstellungs.
ms.openlocfilehash: c0946cf26181df81327412c2dc0efc227b5a5586
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370627"
---
# <a name="upgrade-to-a-new-version-of-cloud-connector"></a>Aktualisieren auf eine neue Version von Cloud Connector
 
Informationen Sie zum Aktualisieren der Cloud Connector Edition-bereitstellungs.
  
Wenn Sie ein Mandantenkonto für die Onlineverwaltung eingerichtet und automatische Aktualisierungen aktiviert haben, wird Ihre vorhandene Bereitstellung von Skype for Business Cloud Connector Edition entsprechend Ihrer Zeitfensterkonfiguration für automatische Updates automatisch auf die neuere Version aktualisiert. Sie können auch manuelle Upgrades ausführen.  
  
Cloud-Connector Edition Versionen 1.4.1, und führen Sie automatische Updates weiter unten in der Standardeinstellung. Wenn Sie auf die neueste Version (2.1) manuell aktualisieren möchten, finden Sie weiter unten in diesem Thema [eine einzelne Website zu einer neuen Version zu aktualisieren](upgrade-to-a-new-version-of-cloud-connector.md#BKMK_Upgrade) .
  
Automatische Updates ist erforderlich, dass der Connector Cloud-Dienst ausgeführt wird. In den folgenden Schritten wird der Prozess für automatische Updates beschrieben:
  
- Der Prozess für automatische Updates wird gemäß dem Zeitplan ausgeführt, den Sie für automatische Updates konfiguriert haben.
    
- Tasks für Betriebssystemupdates
    
  - Überprüfen und Betriebssystemupdates auf alle Cloud Connector VMs herunterladen. 
    
  - Installieren Sie und aktualisieren Sie alle Cloud Connector VMs nacheinander und starten.
    
  - Nach dem Neustart der Cloud Connector VMs überprüfen Sie, um festzustellen, ob eine andere Neustart erforderlich ist.
    
  - Nach der Cloud Connector VMs haben wurde erfolgreich gepatcht, wiederholen Sie den Vorgang für die Cloud Connector-Hostcomputer.
    
  - Nach der Hostcomputer Cloud Connector erfolgreich Mal gestartet wird, werden alle ausstehenden Betriebssystem Update Aufgaben abgeschlossen.
    
- Cloud-Connector Updateaufgaben
    
  - Die Versionsdatei wird von der Downloadwebsite heruntergeladen und überprüft.
    
  - Die neue Version der MSI-Datei wird heruntergeladen.  
    
  - Deinstallieren Sie die alte MSI-Datei. Installieren Sie die neue MSI-Datei.
    
  - Laden Sie die neue Version von Skype für Business Bits.
    
  - Die Appliance wird durch Aufrufen von „Register-CcAppliance“ registriert.
    
  - Installieren Sie die neue Cloud-Connector-Version.
    
  - Die alte Appliance wird ausgeglichen, und die Netzwerkverbindung wird auf die neue Appliance umgeschaltet.
    
> [!NOTE]
>  Wenn Cloud Connector auf einen neuen Build aktualisiert, möglicherweise Cloud Connector-Cmdlets nicht aktualisiert werden. Dies kann beispielsweise auftreten, wenn ein PowerShell-Fenster geöffnet bleibt, während der automatischen Aktualisierung. Um die aktualisierten Cmdlets zu laden, führen Sie entweder die folgenden Schritte: > Schließen PowerShell auf die Cloud Connector Appliance, und klicken Sie dann erneut öffnen Sie PowerShell. > oder Sie können die Import-Module CloudConnector ausführen-Force.
  
## <a name="upgrade-a-single-site-to-a-new-version"></a>Aktualisieren eines einzelnen Standorts auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Wenn der zu aktualisierende Standort nur eine Appliance umfasst, gehen Sie wie folgt vor:
  
1. Deinstallieren Sie die vorhandene Cloud Connector-Version in **Control Panel \> Programme \> Programme und Funktionen**.
    
2. Installieren der neue Version von CloudConnector.msi von [https://aka.ms/CloudConnectorInstaller](https://aka.ms/CloudConnectorInstaller).
    
3. Vergewissern Sie sich, dass Sie über die Datei „CloudConnector.ini“ für die zu installierende Version verfügen und dass Sie alle erforderlichen Werte für Ihre Umgebung aktualisiert haben. Die INI-Datei einer früheren Version kann nicht verwendet werden. Wenn Sie Cloud Connector aktualisieren, finden Sie zum Thema [Vorbereiten Ihrer Appliance Cloud Connector](prepare-your-cloud-connector-appliance.md) , und stellen Sie sicher, dass SiteName und "enablerefersupport" in der Datei CloudConnector.ini auf den richtigen Wert festgelegt sind.
    
4. Starten Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um die aktuelle Appliance zu registrieren:
    
   ```
   Register-CcAppliance
   ```

5. Führen Sie das folgende Cmdlet aus, um die neueste Version herunterzuladen:
    
   ```
   Start-CcDownload
   ```

6. Führen Sie das folgende Cmdlet aus, um die Installation zu starten:  
    
   ```
   Install-CcAppliance -Upgrade
   ```

7. Führen Sie das folgende Cmdlet aus, um die neue Bereitstellung zu aktivieren und die vorherige Version zu deaktivieren:
    
   ```
   Switch-CcVersion
   ```

Wenn sich mehr als eine Appliance am Standort befindet, führen Sie die obigen Schritte aus, um die einzelnen Appliances nacheinander zu aktualisieren.
  
Wenn Sie Domänenadministrator, Administrator des virtuellen Computers, abgesicherten Modus Administrator und Administratoranmeldeinformationen Mandanten aktualisieren möchten, können Sie mit dem Parameter _UpdateAllCredentials_ Zurücksetzen alle Anmeldeinformationen mit dem Cmdlet ausführen:
  
```
Install-CcAppliance -UpdateAllCredentials
```

Wenn Sie dann mit dem Upgrade auf eine neue Version beginnen, werden Sie aufgefordert, die neuen Anmeldeinformationen einzugeben.  
  
Wenn Sie nur die Anmeldeinformationen des Mandantenadministrators zurücksetzen möchten, führen Sie das folgende Cmdlet aus:
  
```
Set-CcCredential -AccountType TenantAdmin
```

## <a name="upgrade-multiple-sites-to-a-new-version"></a>Upgrade von mehreren Standorten auf eine neue Version
<a name="BKMK_Upgrade"> </a>

Führen Sie die Schritte für das Upgrade eines einzelnen Standorts nacheinander für jeden Standort in Ihrer Bereitstellung aus. Führen Sie nach dem Upgrade jedes Standorts unbedingt den Schritt [Validate your Cloud Connector deployment](validate-your-cloud-connector-deployment.md) aus.
  

