---
title: Bereitstellen eines einzelnen Standorts in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Informationen zum Bereitstelleneiner einzelnen PSTN-Website in Cloud Connector Edition.
ms.openlocfilehash: a2cc8933276bc85b19ee79559ca4bcf9e88a079f
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001025"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Deploy a single site in Cloud Connector
 
Informationen zum Bereitstelleneiner einzelnen PSTN-Website in Cloud Connector Edition.
  
Sie können die Skype for Business Cloud Connector Edition mit oder ohne Support für hohe Verfügbarkeit (ha) bereitstellen. Wenn Sie hohe Verfügbarkeit aktivieren möchten, müssen Sie mindestens zwei Appliances an einem Standort bereitstellen. Sie können auch eine vorhandene Appliance nach der Bereitstellung konvertieren, um hohe Verfügbarkeit zu unterstützen.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Bereitstellen der ersten Skype for Business Cloud Connector Edition-Appliance

Um die erste Appliance in einer Site bereitzustellen, öffnen Sie eine PowerShell-Konsole als Administrator. Führen Sie das folgende Cmdlet aus, um die Appliance zu registrieren:
  
```powershell
Register-CcAppliance
```

Befolgen Sie die Anweisungen zum Angeben des Namens und des Kennworts des Administratorkontos für den Mandanten. Verwenden Sie das Konto, das Sie für die Onlineverwaltung von Cloud Connector erstellt haben. Geben Sie außerdem gemäß den Anweisungen das Kennwort des externen Zertifikats, das Administratorkennwort für den abgesicherten Modus, das Kennwort des Domänenadministrators und das Kennwort des VM-Administrators an.  
  
Befolgen Sie in Version 1.4.2 und älteren Versionen auch die Anweisungen zum Bereitstellen des externen Zertifikats Kennworts, des Sicherheitsmodus-Administratorkennworts, des Domänenadministrator Kennworts und des VM-Administratorkennworts. 
  
Befolgen Sie in Version 2,0 und höher die Anweisungen zum Bereitstellen des externen Zertifikats Kennworts, des CceService-Kennworts und des CABackupFile-Kennworts.
  
Um die Installation zu starten, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Hinzufügen einer Appliance zu einer vorhandenen Site

Sie können eine vorhandene Cloud Connector-Website zur Unterstützung von ha erweitern, indem Sie der Website weitere Appliances hinzufügen. 
  
1. Führen Sie die Schritte zum Vorbereiten Ihrer Cloud Connector-Appliance wie in [Vorbereiten der Cloud Connector-Appliance](prepare-your-cloud-connector-appliance.md)beschrieben aus. Beachten Sie, dass einige Schritte nur für die erste Appliance in der Bereitstellung erforderlich sind. Vergewissern Sie sich, dass das Standortverzeichnis vorhanden ist und dass es richtig für die Unterstützung von hoher Verfügbarkeit konfiguriert ist.
    
2. Führen Sie das folgende Cmdlet nur auf dem neu hinzugefügten Hostserver aus, um die Topologieinformationen in der Konfiguration Ihres Office 365-Mandanten zu aktualisieren. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet nacheinander auf jedem der neu hinzugefügten Hostserver aus:
    
   ```powershell
   Register-CcAppliance
   ```

3. Aktualisieren Sie die Topologie in vorhandenen Appliances, indem Sie das folgende Cmdlet auf jedem Hostserver ausführen. Führen Sie das Cmdlet nur in den vorhandenen Appliances aus.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Führen Sie das folgende Cmdlet nur auf neu hinzugefügten Hostservern aus. Führen Sie es nicht in der vorhandenen Appliance aus. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet nacheinander auf jedem der neu hinzugefügten Hostserver aus:
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Wenn das Standortverzeichnis auf einen lokalen Ordnerpfad festgelegt ist, müssen Sie eine Dateifreigabe für diesen Ordner definieren und für das Standortverzeichnis in der neuen Appliance einen UNC-Pfad verwenden. Sie können für das Standortverzeichnis der ersten Appliance den lokalen Pfad beibehalten oder es so ändern, dass der UNC-Pfad für die Freigabe des gleichen Ordners verwendet wird. Wenn sich der Speicherort für das freigegebene Standortverzeichnis ändert, müssen alle bereits installierten Appliances deinstalliert und dann erneut installiert werden. > wichtig: das Kennwort für das CceService-Konto und das CABackupFile-Konto müssen auf allen innerhalb der Website bereitgestellten Appliances identisch sein, damit die Appliances auf die Websiteverzeichnis Freigabe und die Sicherungsdatei der verschlüsselten ca im Websiteverzeichnis zugreifen können. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Entfernen einer Appliance aus einer vorhandenen Site

Wenn Sie eine Appliance aus einer vorhandenen Site entfernen möchten, gehen Sie so vor:
  
1. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, die Sie aus dem Standort entfernen möchten, um die Topologieinformationen in der Konfiguration Ihres Office 365-Mandanten zu aktualisieren.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, von denen Sie alle virtuellen Maschinen der Appliance entfernen möchten.
    
   ```powershell
   Uninstall-CcAppliance
   ```


