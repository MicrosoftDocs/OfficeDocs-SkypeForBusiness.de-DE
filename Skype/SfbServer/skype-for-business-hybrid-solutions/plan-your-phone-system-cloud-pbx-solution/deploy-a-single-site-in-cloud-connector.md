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
description: Erfahren Sie mehr über die Bereitstellung eines einzelnen PSTN-Standorts in Cloud Connector Edition.
ms.openlocfilehash: 32c981b0f7de3d596dc25c3336000871db9fee65
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094833"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Bereitstellen eines einzelnen Standorts in Cloud Connector
 
> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online aus dem Dienst ausscheiden. Nachdem Ihr Unternehmen ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mithilfe von Direct Routing mit Teams [verbinden.](/MicrosoftTeams/direct-routing-landing-page)

Erfahren Sie mehr über die Bereitstellung eines einzelnen PSTN-Standorts in Cloud Connector Edition.
  
Sie können Skype for Business Cloud Connector Edition mit oder ohne Unterstützung für hohe Verfügbarkeit (High Availability, HA) bereitstellen. Wenn Sie HA aktivieren möchten, müssen Sie zwei oder mehr Appliances an einem Standort bereitstellen. Sie können auch eine vorhandene Appliance konvertieren, um ha zu unterstützen, nachdem sie bereitgestellt wurde.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Bereitstellen der ersten Skype for Business Cloud Connector Edition-Appliance

Öffnen Sie zum Bereitstellen der ersten Appliance an einem Standort eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um die Appliance zu registrieren:
  
```powershell
Register-CcAppliance
```

Befolgen Sie die Anweisungen, um den Namen und das Kennwort des Mandantenadministratorkontos zur Verfügung zu stellen. Verwenden Sie das Konto, das Sie für die Cloud Connector-Onlineverwaltung erstellt haben. Befolgen Sie außerdem die Anweisungen, um das externe Zertifikatkennwort, das Administratorkennwort für den abgesicherten Modus, das Domänenadministratorkennwort und das Kennwort für vm-Administratoren zur Verfügung zu stellen. 
  
Befolgen Sie in Version 1.4.2 und früher auch die Anweisungen, um das externe Zertifikatkennwort, das Administratorkennwort für den sicheren Modus, das Domänenadministratorkennwort und das Administratorkennwort des virtuellen Computers zur Verfügung zu stellen. 
  
Befolgen Sie in Version 2.0 und höher auch die Anweisungen zum Angeben des externen Zertifikatkennworts, des CceService-Kennworts und des CABackupFile-Kennworts.
  
Öffnen Sie zum Starten der Installation eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Hinzufügen einer Appliance zu einem vorhandenen Standort

Sie können eine vorhandene Cloud Connector-Website erweitern, um HA zu unterstützen, indem Sie dem Standort zusätzliche Appliances hinzufügen. 
  
1. Führen Sie die Schritte zum Vorbereiten Ihrer Cloud Connector-Appliance aus, wie unter [Prepare your Cloud Connector appliance beschrieben.](prepare-your-cloud-connector-appliance.md) Beachten Sie, dass einige Schritte nur für die erste Appliance in Ihrer Bereitstellung erforderlich sind. Vergewissern Sie sich, dass das Websiteverzeichnis vorhanden ist und ordnungsgemäß für die Unterstützung von Ha konfiguriert ist.
    
2. Führen Sie das folgende Cmdlet nur auf dem neu hinzugefügten Hostserver aus, um Topologieinformationen in Ihrer Microsoft 365- oder Office 365-Organisationskonfiguration zu aktualisieren. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet auf jedem neu hinzugefügten Hostserver nach und nach aus:
    
   ```powershell
   Register-CcAppliance
   ```

3. Aktualisieren Sie die Topologie für vorhandene Appliances, indem Sie auf jedem Hostserver das folgende Cmdlet ausführen. Führen Sie das Cmdlet nur auf den vorhandenen Appliances aus.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Führen Sie das folgende Cmdlet nur auf neu hinzugefügten Hostservern aus. Führen Sie dieses Cmdlet nicht auf der vorhandenen Appliance aus. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet auf jedem neu hinzugefügten Hostserver nach und nach aus.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Wenn das Websiteverzeichnis auf einen lokalen Ordnerpfad festgelegt wurde, müssen Sie eine Dateifreigabe für diesen Ordner definieren und einen UNC-Pfad für das Standortverzeichnis für die neue Appliance verwenden. Sie können das erste Appliance-Standortverzeichnis mit dem lokalen Pfad be lassen oder es ändern, um den UNC-Pfad für die Freigabe in denselben Ordner zu verwenden. Wenn sich der Speicherort für das freigegebene Standortverzeichnis ändert, müssen alle zuvor installierten Appliances deinstalliert und dann erneut installiert werden. > Wichtig: Das Kennwort für das CceService-Konto und das CABackupFile-Konto muss für alle appliances identisch sein, die innerhalb des Standorts bereitgestellt werden, damit die Appliances auf die Websiteverzeichnisfreigabe und die verschlüsselte Ca-Sicherungsdatei im Standortverzeichnis zugreifen können. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Entfernen einer Appliance von einem vorhandenen Standort

Wenn Sie eine Appliance von einem vorhandenen Standort entfernen möchten:
  
1. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, die Sie von der Website entfernen möchten, um die Topologieinformationen in Ihrer Microsoft 365- oder Office 365-Organisationskonfiguration zu aktualisieren.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, von denen Sie alle virtuellen Computer der Appliance entfernen möchten.
    
   ```powershell
   Uninstall-CcAppliance
   ```