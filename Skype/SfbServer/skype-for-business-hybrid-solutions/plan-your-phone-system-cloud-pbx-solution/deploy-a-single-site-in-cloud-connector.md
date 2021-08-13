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
ms.openlocfilehash: 52c10b8c5e386f72415ce5a379b68b0b469f825f5cf52be9b225f28dcf8232b6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298125"
---
# <a name="deploy-a-single-site-in-cloud-connector"></a>Bereitstellen eines einzelnen Standorts in Cloud Connector
 
> [!Important]
> Cloud Connector Edition wird am 31. Juli 2021 zusammen mit Skype for Business Online eingestellt. Nachdem Ihre Organisation ein Upgrade auf Teams durchgeführt hat, erfahren Sie, wie Sie Ihr lokales Telefonienetzwerk mit Teams über [Direct Routing](/MicrosoftTeams/direct-routing-landing-page)verbinden.

Erfahren Sie mehr über die Bereitstellung eines einzelnen PSTN-Standorts in Cloud Connector Edition.
  
Sie können Skype for Business Cloud Connector Edition mit oder ohne Unterstützung für hohe Verfügbarkeit (High Availability, HA) bereitstellen. Wenn Sie HA aktivieren möchten, müssen Sie zwei oder mehr Appliances an einem Standort bereitstellen. Sie können auch eine vorhandene Appliance konvertieren, um HA nach der Bereitstellung zu unterstützen.
  
## <a name="deploy-the-first-skype-for-business-cloud-connector-edition-appliance"></a>Bereitstellen der ersten Skype for Business Cloud Connector Edition Appliance

Um die erste Appliance an einem Standort bereitzustellen, öffnen Sie eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus, um die Appliance zu registrieren:
  
```powershell
Register-CcAppliance
```

Befolgen Sie die Anweisungen, um den Namen und das Kennwort des Mandantenadministratorkontos anzugeben. Verwenden Sie das Konto, das Sie für die Cloud Connector Online-Verwaltung erstellt haben. Befolgen Sie außerdem die Anweisungen, um das Kennwort für das externe Zertifikat, das Administratorkennwort für den abgesicherten Modus, das Kennwort des Domänenadministrators und das Vm-Administratorkennwort bereitzustellen. 
  
Befolgen Sie in Version 1.4.2 und früheren Versionen auch die Anweisungen, um das Kennwort für das externe Zertifikat, das Administratorkennwort für den abgesicherten Modus, das Kennwort des Domänenadministrators und das Vm-Administratorkennwort bereitzustellen. 
  
Befolgen Sie in Version 2.0 und höher auch die Anweisungen zum Bereitstellen des externen Zertifikatkennworts, des CceService-Kennworts und des CABackupFile-Kennworts.
  
Öffnen Sie zum Starten der Installation eine PowerShell-Konsole als Administrator, und führen Sie das folgende Cmdlet aus:
  
```powershell
Install-CcAppliance
```

## <a name="add-an-appliance-to-an-existing-site"></a>Hinzufügen einer Appliance zu einem vorhandenen Standort

Sie können einen vorhandenen Cloud Connector-Standort erweitern, um HA zu unterstützen, indem Sie dem Standort zusätzliche Appliances hinzufügen. 
  
1. Führen Sie die Schritte aus, um Ihre Cloud Connector-Appliance wie unter ["Vorbereiten ihrer Cloud Connector-Appliance"](prepare-your-cloud-connector-appliance.md)beschrieben vorzubereiten. Beachten Sie, dass einige Schritte nur für die erste Appliance in Ihrer Bereitstellung erforderlich sind. Vergewissern Sie sich, dass das Standortverzeichnis vorhanden ist und ordnungsgemäß für ha-Unterstützung konfiguriert ist.
    
2. Führen Sie das folgende Cmdlet nur auf dem neu hinzugefügten Hostserver aus, um Topologieinformationen in Ihrer Microsoft 365 oder Office 365 Organisationskonfiguration zu aktualisieren. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet nacheinander auf jedem neu hinzugefügten Hostserver aus:
    
   ```powershell
   Register-CcAppliance
   ```

3. Aktualisieren Sie die Topologie in vorhandenen Appliances, indem Sie das folgende Cmdlet auf jedem Hostserver ausführen. Führen Sie das Cmdlet nur in den vorhandenen Appliances aus.
    
   ```powershell
   Publish-CcAppliance
   ```

4. Führen Sie das folgende Cmdlet nur auf neu hinzugefügten Hostservern aus. Führen Sie dieses Cmdlet nicht in der vorhandenen Appliance aus. Wenn Sie mehrere Appliances gleichzeitig hinzufügen möchten, führen Sie das Cmdlet nacheinander auf jedem neu hinzugefügten Hostserver aus.
    
   ```powershell
   Install-CcAppliance
   ```

> [!NOTE]
> Wenn das Websiteverzeichnis auf einen lokalen Ordnerpfad festgelegt wurde, müssen Sie eine Dateifreigabe für diesen Ordner definieren und einen UNC-Pfad für das Websiteverzeichnis in der neuen Appliance verwenden. Sie können das Verzeichnis des ersten Appliance-Standorts mit dem lokalen Pfad belassen oder ihn so ändern, dass der UNC-Pfad für die Freigabe für denselben Ordner verwendet wird. Wenn sich der Speicherort des freigegebenen Standortverzeichnisses ändert, müssen alle zuvor installierten Appliances deinstalliert und dann neu installiert werden. > Wichtig: Das Kennwort für das CceService-Konto und das CABackupFile-Konto muss für alle Appliances, die innerhalb des Standorts bereitgestellt werden, identisch sein, damit die Appliances auf die Standortverzeichnisfreigabe und die verschlüsselte CA-Sicherungsdatei im Standortverzeichnis zugreifen können. 
  
## <a name="remove-an-appliance-from-an-existing-site"></a>Entfernen einer Appliance von einem vorhandenen Standort

Wenn Sie eine Appliance von einem vorhandenen Standort entfernen möchten:
  
1. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, die Sie vom Standort entfernen möchten, um die Topologieinformationen in Ihrer Microsoft 365 oder Office 365 Organisationskonfiguration zu aktualisieren.
    
   ```powershell
   Unregister-CcAppliance
   ```

2. Führen Sie das folgende Cmdlet nur auf den Hostservern aus, von denen Sie alle virtuellen Computer der Appliance entfernen möchten.
    
   ```powershell
   Uninstall-CcAppliance
   ```