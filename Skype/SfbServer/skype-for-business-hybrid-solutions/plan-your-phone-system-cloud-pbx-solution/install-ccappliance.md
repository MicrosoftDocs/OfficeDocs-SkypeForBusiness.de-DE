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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: Das Cmdlet Install-CcAppliance installiert die Skype for Business Cloud Connector Edition Appliance – einschließlich der virtuellen Computer AD, der zentralen Verwaltung Store, des Vermittlungsservers und des Edgeservers – auf dem Hostserver.
ms.openlocfilehash: 0ed13282039b84975bea3e26f5ae1d7f79122a11
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635839"
---
# <a name="install-ccappliance"></a>Install-CcAppliance
 
Das Cmdlet Install-CcAppliance installiert die Skype for Business Cloud Connector Edition Appliance – einschließlich der virtuellen Computer AD, der zentralen Verwaltung Store, des Vermittlungsservers und des Edgeservers – auf dem Hostserver. 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird eine neue Cloud Connector-Appliance auf dem Hostserver installiert:
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a>Beispiel 2

Im folgenden Beispiel wird Cloud Connector auf die neueste Version aktualisiert:
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a>Beispiel 3

Im folgenden Beispiel werden alle auf dem Hostserver zwischengespeicherten Cloud Connector-Anmeldeinformationen entfernt, der Benutzer aufgefordert, alle Anmeldeinformationen erneut anzugeben, und anschließend Wird Cloud Connector installiert:
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a>Beispiel 4

Im folgenden Beispiel werden alle Bereitstellungsschritte in der PowerShell-Konsole angezeigt:
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

Der Parameter "-ShowStepsOnly" dient nur zur Problembehandlung.
  
### <a name="example-5"></a>Beispiel 5

Im folgenden Beispiel werden Konfigurationsdateien für jeden Bereitstellungsschritt auf dem Hostserver generiert. Konfigurationsdateien werden im \<ApplianceRoot\> Ordner "\Instances \\<Version \> -default\ExportedConfig" auf dem Hostserver gespeichert:
  
```powershell
Install-CcAppliance -PrepareOnly
```

Führen Sie das Cmdlet Get-CcApplianceDirectory aus, um den Appliance-Stamm zu ermitteln. 
  
### <a name="example-6"></a>Beispiel 6

Im folgenden Beispiel führt Cloud Connector die Bereitstellungsschritte 1, 2 und 3 aus, um virtuelle Switches zu erstellen, einen virtuellen AD-Computer zu erstellen und den Domänendienst auf dem AD-Server zu installieren. Er überspringt den Schritt, wenn der Schritt bereits ausgeführt wurde:
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

Der Parameter "SkipExistingObjects" muss in Verbindung mit dem Parameter "Steps" verwendet werden.
  
> [!NOTE]
> Der Parameter "Steps" dient nur zur Problembehandlung. Verwenden Sie diesen Parameter nicht zum Bereitstellen einer Appliance oder zum Upgrade einer appliance, die in Betrieb ist. 
  
Führen Sie den folgenden Befehl aus, um die Schritte der Bereitstellung zu ermitteln:
  
Install-CcAppliance -ShowStepsOnly
  
## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet Install-CcAppliance wird verwendet, um Cloud Connector in einer neuen Appliance bereitzustellen oder um eine vorhandene Appliance auf die neueste Version zu aktualisieren.
  
Wenn Sie über eine neue Appliance verfügen, lesen Sie zuerst "Vorbereiten der Umgebung für Cloud Connector", führen Sie das Cmdlet Register-CcAppliance aus, um die Appliance zu registrieren, und führen Sie dann das cmdlet Install-CcAppliance aus. Weitere Informationen finden Sie unter [Bereitstellen eines einzelnen Standorts in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) und Bereitstellen mehrerer Standorte in Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md) 
  
Wenn Sie über eine vorhandene Bereitstellung von Cloud Connector verfügen und ein Upgrade durchführen möchten, befolgen Sie die Anweisungen unter [Upgrade auf eine neue Version von Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|PrepareOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> | Generieren Sie Konfigurationsdateien für jeden Bereitstellungsschritt. Dieser Parameter dient nur zur Problembehandlung. <br/> |
|ShowStepsOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Zeigt nur die Namen der Bereitstellungsschritte an. Dieser Parameter dient nur zur Problembehandlung.  <br/> |
|SkipExistingObjects  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Dieser Parameter muss in Verbindung mit dem Parameter "Steps" verwendet werden. Dieser Parameter dient nur zur Problembehandlung.  <br/> |
|Schritte  <br/> |Optional  <br/> |System.Array  <br/> |Führen Sie die Bereitstellungsschritte aus. Dieser Parameter dient nur zur Problembehandlung.  <br/> |
|Upgraden  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Aktualisieren Sie vorhandenen Cloud Connector auf die neueste Version.  <br/> |
|UpdateAllCredentials  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Entfernen Sie alle Cloud Connector-Anmeldeinformationen im Cache. Fordert den Benutzer auf, neue Anmeldeinformationen für die Installation anzugeben.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Install-CcAppliance akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Publish-CcAppliance](publish-ccappliance.md)
  
[Register-CcAppliance](register-ccappliance.md)
  
[Unregister-CcAppliance](unregister-ccappliance.md)
  
[Uninstall-CcAppliance](uninstall-ccappliance.md)
  

