---
title: Bereitstellen eines einzelnen Standorts in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Informationen Sie zu eine einzelne PSTN-Website in der Cloud Connector Edition bereitstellen.
ms.openlocfilehash: 667637fdf7dd42df64c4fdf9aca6b20931da188d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881141"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Deploy a single site in Cloud Connector
 
Informationen Sie zu eine einzelne PSTN-Website in der Cloud Connector Edition bereitstellen.
  
Sie können mit oder ohne Unterstützung von hoher Verfügbarkeit (HA) Skype für Business Cloud Connector Edition bereitstellen. Wenn Sie hohe Verfügbarkeit aktivieren möchten, müssen Sie mindestens zwei Appliances an einem Standort bereitstellen. Sie können auch eine vorhandene Appliance nach der Bereitstellung konvertieren, um hohe Verfügbarkeit zu unterstützen.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Bereitstellen der ersten Skype for Business Cloud Connector Edition-Appliance

Um die erste Appliance in einer Site bereitzustellen, öffnen Sie eine PowerShell-Konsole als Administrator. Führen Sie das folgende Cmdlet aus, um die Appliance zu registrieren:
  
```
Register-CcAppliance
```

Befolgen Sie die Anweisungen zum Angeben des Namens und des Kennworts des Administratorkontos für den Mandanten. Verwenden Sie das Konto, das Sie für die Onlineverwaltung von Cloud Connector erstellt haben. Geben Sie außerdem gemäß den Anweisungen das Kennwort des externen Zertifikats, das Administratorkennwort für den abgesicherten Modus, das Kennwort des Domänenadministrators und das Kennwort des VM-Administrators an.  
  
In Version 1.4.2 und früher auch befolgen Sie die Anweisungen, die externe Zertifikatkennwort, Administratorkennwort abgesicherten Modus, Admin Domänenkennwort und VM Administratorkennwort bereitzustellen. 
  
In Version 2.0 und höher, auch führen Sie die Anweisungen, um die externe Zertifikatkennwort, CceService Kennwort und Kennwort CABackupFile bieten.
  
Um die Installation zu starten, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus:
  
```
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Hinzufügen einer Appliance zu einer vorhandenen Site

Sie können eine vorhandene Website Cloud Connector zur Unterstützung der HA durch Hinzufügen von zusätzlichen Einheiten für die Website erweitern. 
  
1. Führen Sie die Schritten zur Vorbereitung Ihrer Appliance Cloud Connector, wie beschrieben unter [Vorbereiten der Appliance Cloud-Connector](prepare-your-cloud-connector-appliance.md)ein. Beachten Sie, dass einige Schritte nur für die erste Appliance in der Bereitstellung erforderlich sind. Vergewissern Sie sich, dass das Standortverzeichnis vorhanden ist und dass es richtig für die Unterstützung von hoher Verfügbarkeit konfiguriert ist.
    
2. Führen Sie das folgende Cmdlet nur auf dem neu hinzugefügten Hostserver aus, um die Topologieinformationen in der Konfiguration Ihres Office 365-Mandanten zu aktualisieren. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet nacheinander auf jedem der neu hinzugefügten Hostserver aus:
    
   ```
   Register-CcAppliance
   ```

3. Aktualisieren Sie die Topologie in vorhandenen Appliances, indem Sie das folgende Cmdlet auf jedem Hostserver ausführen. Führen Sie das Cmdlet nur in den vorhandenen Appliances aus.
    
   ```
   Publish-CcAppliance
   ```

4. Führen Sie das folgende Cmdlet nur auf neu hinzugefügten Hostservern aus. Führen Sie es nicht in der vorhandenen Appliance aus. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet nacheinander auf jedem der neu hinzugefügten Hostserver aus:
    
   ```
   Install-CcAppliance
   ```

> [!NOTE]
> Wenn das Standortverzeichnis auf einen lokalen Ordnerpfad festgelegt ist, müssen Sie eine Dateifreigabe für diesen Ordner definieren und für das Standortverzeichnis in der neuen Appliance einen UNC-Pfad verwenden. Sie können für das Standortverzeichnis der ersten Appliance den lokalen Pfad beibehalten oder es so ändern, dass der UNC-Pfad für die Freigabe des gleichen Ordners verwendet wird. Wenn sich der Speicherort für das freigegebene Standortverzeichnis ändert, müssen alle bereits installierten Appliances deinstalliert und dann erneut installiert werden. > wichtig: das Kennwort für das Konto CceService und das CABackupFile Konto muss auf allen Einheiten, die innerhalb der Website bereitgestellt, damit die Appliances die Site Directory Freigabe als auch die verschlüsselte Zertifizierungsstelle Sicherungsdatei im Websiteverzeichnis zugreifen können. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Entfernen einer Appliance aus einer vorhandenen Site

Wenn Sie eine Appliance aus einer vorhandenen Site entfernen möchten, gehen Sie so vor:
  
1. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, die Sie aus dem Standort entfernen möchten, um die Topologieinformationen in der Konfiguration Ihres Office 365-Mandanten zu aktualisieren.
    
   ```
   Unregister-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, von denen Sie alle virtuellen Maschinen der Appliance entfernen möchten.
    
   ```
   Uninstall-CcAppliance
   ```


