---
title: Install-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 'Das Cmdlet „Install-CcAppliance“ installiert die Skype for Business Cloud Connector Edition-Appliance (einschließlich der virtuellen Maschinen für AD, den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver) auf dem Hostserver. '
ms.openlocfilehash: d35a102f7d3ade7b64bcf43388eaf03dc455c27b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569987"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Das Cmdlet „Install-CcAppliance“ installiert die Skype for Business Cloud Connector Edition-Appliance (einschließlich der virtuellen Maschinen für AD, den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver) auf dem Hostserver.  
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgende Beispiel wird eine neue Cloud-Connector Appliance auf dem Hostserver installiert:
  
```
Install-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im folgende Beispiel werden Cloud Connector auf die neueste Version aktualisiert:
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Beispiel 3

Das folgende Beispiel entfernt alle Cloud Connector Anmeldeinformationen Cache auf dem Hostserver fordert den Benutzer an allen Anmeldeinformationen erneut, und installiert dann Cloud Connector:
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Beispiel 4

Im folgenden Beispiel werden alle Bereitstellungsschritte in der PowerShell-Konsole angezeigt:
  
```
Install-CcAppliance -ShowStepsOnly
```

Der Parameter „-ShowStepsOnly“ ist nur für die Problembehandlung vorgesehen.
  
### <a name="example-5"></a>Beispiel 5

Im folgenden Beispiel werden Konfigurationsdateien für die einzelnen Bereitstellungsschritte auf dem Hostserver generiert. Konfigurationsdateien gespeichert, die \<ApplianceRoot\>\Instances\\< Version\>-Default\ExportedConfig-Ordner auf dem Hostserver:
  
```
Install-CcAppliance -PrepareOnly
```

Um den Appliance-Stamm zu ermitteln, führen Sie das Cmdlet „Get-CcApplianceDirectory“ aus.  
  
### <a name="example-6"></a>Beispiel 6

Im folgenden Beispiel führt Cloud Connector die Bereitstellungsschritte 1, 2 und 3 aus, um virtuelle Switches zu erstellen, eine virtuelle AD-Maschine zu erstellen und den Domänendienst auf dem AD-Server zu installieren. Bereits ausgeführte Schritte werden übersprungen:
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Der Parameter „SkipExistingObjects“ muss in Verbindung mit dem Parameter „Steps“ verwendet werden.
  
> [!NOTE]
> Der Parameter „Steps“ ist nur für die Problembehandlung vorgesehen. Verwenden Sie diesen Parameter nicht, um eine Appliance bereitzustellen oder eine verwendete Appliance zu aktualisieren. 
  
Um die Bereitstellungsschritte zu ermitteln, führen Sie den folgenden Befehl aus:
  
Install-CcAppliance - ShowStepsOnly
  
## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet Install-CcAppliance wird zum Bereitstellen von Cloud-Connector für eine neue Appliance oder eines Upgrades eine vorhandene Appliance auf die neueste Version verwendet.
  
Wenn Sie eine neue Appliance haben, müssen Sie unbedingt finden Sie unter Prepare Ihrer Umgebung für Cloud-Connector zunächst, führen Sie das Cmdlet Register-CcAppliance zum Registrieren der Appliance, und führen Sie das Cmdlet Install-CcAppliance. Weitere Informationen finden Sie unter [Bereitstellen einer einzelnen Website in der Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [mehrere Standorte in der Cloud Connector bereitstellen](deploy-multiple-sites-in-cloud-connector.md). 
  
Wenn Sie eine vorhandene Bereitstellung von Cloud-Connector verfügen, und Sie aktualisieren möchten, führen Sie die Anweisungen in das [Upgrade auf eine neue Version von Cloud-Connector](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |  Generiert Konfigurationsdateien für die einzelnen Bereitstellungsschritte. Dieser Parameter ist nur für die Problembehandlung vorgesehen.  <br/> |
|ShowStepsOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Zeigt nur die Namen der Bereitstellungsschritte an. Dieser Parameter ist nur für die Problembehandlung vorgesehen.  <br/> |
|SkipExistingObjects  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Dieser Parameter muss in Verbindung mit dem Parameter „Steps“ verwendet werden. Dieser Parameter ist nur für die Problembehandlung vorgesehen.  <br/> |
|Steps  <br/> |Optional  <br/> |System.Array  <br/> |Führt die Bereitstellungsschritte aus. Dieser Parameter ist nur für die Problembehandlung vorgesehen.  <br/> |
|Upgrade  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Aktualisiert eine vorhandene Cloud Connector-Installation auf die neueste Version.  <br/> |
|UpdateAllCredentials  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Entfernen Sie alle Cloud Connector Anmeldeinformationen im Cache. Fordert den Benutzer auf, für die Installation neue Anmeldeinformationen einzugeben.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Install-CcAppliance“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Veröffentlichen von CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Aufheben der Registrierung CcAppliance](unregister-ccappliance.md)
  
[Deinstallieren von CcAppliance](uninstall-ccappliance.md)
  

