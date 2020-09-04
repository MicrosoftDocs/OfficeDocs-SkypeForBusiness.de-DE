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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: fa8aa499-1188-447e-bc30-89d1f5b198a7
description: Erfahren Sie mehr über die Bereitstellungeines einzelnen PSTN-Standorts in Cloud Connector Edition.
ms.openlocfilehash: 327fc4e687377f5f1338bea2f623b526511a2992
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358931"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Bereitstellen eines einzelnen Standorts in Cloud Connector
 
> [!Important]
> Die Cloud Connector-Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online zurückgezogen. Nachdem Ihre Organisation ein Upgrade auf Microsoft Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonie-Netzwerk mithilfe des [direkten Routings](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)mit Microsoft Teams verbinden.

Erfahren Sie mehr über die Bereitstellungeines einzelnen PSTN-Standorts in Cloud Connector Edition.
  
Sie können Skype for Business Cloud Connector Edition mit oder ohne Unterstützung für hohe Verfügbarkeit (ha) bereitstellen. Wenn Sie ha aktivieren möchten, müssen Sie zwei oder mehr Appliances innerhalb eines Standorts bereitstellen. Sie können eine vorhandene Appliance auch konvertieren, um ha zu unterstützen, nachdem Sie bereitgestellt wurde.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Bereitstellen der ersten Skype for Business Cloud Connector Edition-Appliance

Um die erste Appliance an einem Standort bereitzustellen, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um die Appliance zu registrieren:
  
```powershell
Register-CcAppliance
```

Befolgen Sie die Anweisungen, um den Namen und das Kennwort des mandantenadministrator Kontos anzugeben. Verwenden Sie das Konto, das Sie für die Online Verwaltung von Cloud Connector erstellt haben. Befolgen Sie außerdem die Anweisungen, um das Kennwort für das externe Zertifikat, das Administratorkennwort für den sicheren Modus, das Domänenadministratorkennwort und das VM-Administratorkennwort anzugeben. 
  
Befolgen Sie in Version 1.4.2 und früher auch die Anweisungen zum Bereitstellen des externen Zertifikats Kennworts, des Safe Mode-Administratorkennworts, des Domänenadministrator Kennworts und des VM-Administratorkennworts. 
  
Befolgen Sie in Version 2,0 und höher auch die Anweisungen, um das externe Zertifikat Kennwort, das "cceservice"-Kennwort und das CABackupFile-Kennwort anzugeben.
  
Öffnen Sie zum Starten der Installation eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Hinzufügen einer Appliance zu einer vorhandenen Website

Sie können einen vorhandenen Cloud Connector-Standort erweitern, um ha zu unterstützen, indem Sie dem Standort zusätzliche Appliances hinzufügen. 
  
1. Befolgen Sie die Schritte zum Vorbereiten Ihrer Cloud Connector-Appliance wie unter [prepare your Cloud Connector Appliance](prepare-your-cloud-connector-appliance.md)beschrieben. Beachten Sie, dass einige Schritte nur für die erste Appliance in Ihrer Bereitstellung erforderlich sind. Stellen Sie sicher, dass das Websiteverzeichnis vorhanden und für die ha-Unterstützung ordnungsgemäß konfiguriert ist.
    
2. Führen Sie das folgende Cmdlet nur auf dem neu hinzugefügten Hostserver aus, um die Topologieinformationen in Ihrer Microsoft 365-oder Office 365-Organisationskonfiguration zu aktualisieren. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet jeweils nacheinander auf jedem neu hinzugefügten Hostserver aus:
    
   ```powershell
   Register-CcAppliance
   ```

3. Aktualisieren Sie die Topologie auf vorhandenen Appliances, indem Sie das folgende Cmdlet auf jedem Hostserver ausführen. Führen Sie das Cmdlet nur für die vorhandenen Appliances aus.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Führen Sie das folgende Cmdlet nur auf neu hinzugefügten Hostservern aus. Führen Sie dieses Cmdlet nicht für die vorhandene Appliance aus. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet auf jedem neu hinzugefügten Hostserver nacheinander aus.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Wenn das Websiteverzeichnis auf einen lokalen Ordnerpfad festgelegt wurde, müssen Sie eine Dateifreigabe für diesen Ordner definieren und einen UNC-Pfad für das Websiteverzeichnis in der neuen Appliance verwenden. Sie können das erste Appliance-Websiteverzeichnis mit dem lokalen Pfad belassen oder es so ändern, dass der UNC-Pfad für die Freigabe in demselben Ordner verwendet wird. Wenn sich der Speicherort für das freigegebene Websiteverzeichnis ändert, müssen alle zuvor installierten Appliances deinstalliert und dann neu installiert werden. > wichtig: das Kennwort für das "cceservice"-Konto und das CABackupFile-Konto muss auf allen innerhalb des Standorts bereitgestellten Appliances identisch sein, damit die Appliances auf die Websiteverzeichnis Freigabe und die Sicherungsdatei der verschlüsselten Zertifizierungsstelle im Websiteverzeichnis zugreifen können. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Entfernen einer Appliance von einer vorhandenen Website

Wenn Sie eine Appliance aus einer vorhandenen Website entfernen möchten:
  
1. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, die Sie aus dem Standort entfernen möchten, um die Topologieinformationen in Ihrer Microsoft 365-oder Office 365-Organisationskonfiguration zu aktualisieren.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, aus denen Sie alle virtuellen Computer der Appliance entfernen möchten.
    
   ```powershell
   Uninstall-CcAppliance
   ```


