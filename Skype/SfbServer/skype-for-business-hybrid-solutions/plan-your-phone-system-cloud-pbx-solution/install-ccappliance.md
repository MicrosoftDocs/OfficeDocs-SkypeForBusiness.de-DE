---
title: Install-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 'Das Cmdlet „Install-CcAppliance“ installiert die Skype for Business Cloud Connector Edition-Appliance (einschließlich der virtuellen Maschinen für AD, den zentralen Verwaltungsspeicher, den Vermittlungsserver und den Edgeserver) auf dem Hostserver. '
ms.openlocfilehash: 01c689c4a4639c12292d59def6b698281f402299
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287272"
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

Im folgenden Beispiel wird eine neue Cloud Connector-Appliance auf dem Hostserver installiert:
  
```
Install-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im folgenden Beispiel wird Cloud Connector auf die neueste Version aktualisiert:
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Beispiel 3

Im folgenden Beispiel werden alle auf dem Hostserver zwischengespeicherten Cloud Connector-Anmeldeinformationen entfernt, der Benutzer wird aufgefordert, alle Anmeldeinformationen erneut anzugeben, und dann wird Cloud Connector installiert:
  
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

Im folgenden Beispiel werden Konfigurationsdateien für die einzelnen Bereitstellungsschritte auf dem Hostserver generiert. Konfigurationsdateien werden im \<Ordner ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig auf dem Hostserver gespeichert:
  
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
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet "Install-CcAppliance" wird verwendet, um den Cloud Connector für eine neue Appliance bereitzustellen oder um eine vorhandene Appliance auf die neueste Version zu aktualisieren.
  
Wenn Sie über eine neue Appliance verfügen, lesen Sie Vorbereiten Ihrer Umgebung für Cloud Connector zuerst, führen Sie das Cmdlet Register-CcAppliance aus, um die Appliance zu registrieren, und führen Sie dann das Cmdlet Install-CcAppliance aus. Weitere Informationen finden Sie unter [Bereitstelleneiner einzelnen Website in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und [Bereitstellen mehrerer Websites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md). 
  
Wenn Sie über eine vorhandene Bereitstellung von Cloud Connector verfügen und ein Upgrade durchführen möchten, folgen Sie den Anweisungen unter [Upgrade auf eine neue Version von Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |  Generiert Konfigurationsdateien für die einzelnen Bereitstellungsschritte. Dieser Parameter ist nur für die Problembehandlung vorgesehen.  <br/> |
|ShowStepsOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Zeigt nur die Namen der Bereitstellungsschritte an. Dieser Parameter ist nur für die Problembehandlung vorgesehen.  <br/> |
|SkipExistingObjects  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Dieser Parameter muss in Verbindung mit dem Parameter „Steps“ verwendet werden. Dieser Parameter ist nur für die Problembehandlung vorgesehen.  <br/> |
|Steps  <br/> |Optional  <br/> |System.Array  <br/> |Führt die Bereitstellungsschritte aus. Dieser Parameter ist nur für die Problembehandlung vorgesehen.  <br/> |
|Upgrade  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Aktualisiert eine vorhandene Cloud Connector-Installation auf die neueste Version.  <br/> |
|UpdateAllCredentials  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Entfernen Sie alle Anmeldeinformationen für den Cloud Connector im Cache. Fordert den Benutzer auf, für die Installation neue Anmeldeinformationen einzugeben.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Install-CcAppliance“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

