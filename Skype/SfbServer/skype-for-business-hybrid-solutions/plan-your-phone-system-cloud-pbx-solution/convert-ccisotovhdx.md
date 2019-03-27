---
title: Convert-CcIsoToVhdx
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Das Cmdlet „Convert-CcIsoToVhdx“ erstellt eine Datei einer virtuellen Basisfestplatte (VHDX) und verwendet dazu eine vom Kunden bereitgestellte ISO-Datei von Windows Server 2012 R2. Die VHDX-Datei wird bei der Bereitstellung von Skype for Business Cloud Connector Edition verwendet.
ms.openlocfilehash: 181d1af762d1f8c9c8f3e65a4411b317ab36ce4a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898487"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Das Cmdlet „Convert-CcIsoToVhdx“ erstellt eine Datei einer virtuellen Basisfestplatte (VHDX) und verwendet dazu eine vom Kunden bereitgestellte ISO-Datei von Windows Server 2012 R2. Die VHDX-Datei wird bei der Bereitstellung von Skype for Business Cloud Connector Edition verwendet.
  
```
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Parameter

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Erforderlich <br/> |System.String  <br/> |  Der Pfad zur ISO-Datei von Windows Server 2012 R2  <br/> |
|GeneralizeOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Wenn der Konvertierungsprozess beim Update von Windows fehlschlägt, können Sie versuchen, das Netzwerk und einen Proxy zu konfigurieren und Windows manuell zu aktualisieren. Wenn die manuellen Aufgaben abgeschlossen sind, können Sie dieses Cmdlet mit dem Parameter „-GeneralizeOnly“ ausführen. Dadurch werden die verbleibenden Aufträge ausgeführt.   <br/> |
|PauseBeforeUpdate  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Um Windows zu aktualisieren, müssen Sie möglicherweise die Netzwerk-/Proxykonfiguration in der Basis-VM manuell anpassen. Wenn dieser Parameter angegeben ist, wird der Konvertierungsprozess vor dem Update von Windows angehalten. Nach Abschluss der manuellen Konfiguration können Sie den Prozess fortsetzen.   <br/> |
   
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die VHDX-Basisdatei mithilfe einer ISO-Datei von Windows Server 2012 R2 unter „C:\Windows_Server_2012_R2-EN-US-x64.ISO“ vorbereitet:  
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Beispiel 2

Wenn das Cmdlet Convert-CcIsoToVhdx während ein Fehler auftritt Windows update, ist es wahrscheinlich aufgrund von falschen Netzwerk-Proxy-Konfiguration. Sie können die Anweisungen in der Fehlermeldung befolgen und sich bei der Basis-VM anmelden, um das Problem zu beheben und Windows manuell zu aktualisieren. Wenn die manuellen Aufgaben abgeschlossen sind, führen Sie das Cmdlet erneut mit dem Parameter „-GeneralizeOnly“ aus, um die verbleibenden Aufträge auszuführen: 
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Beispiel 3

Wenn für das Update von Windows eine manuelle Konfiguration notwendig ist, können Sie den Parameter „-PauseBeforeUpdate“ verwenden. Mit diesem Parameter wird Cloud Connector anhalten, bevor der Prozess für die Windows update. Dann können Sie die manuelle Konfiguration vornehmen und den Konvertierungsprozess wie folgt fortsetzen:
  
```
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Convert-CcIsoToVhdx-Cmdlet erstellt eine Base, die VM zuerst einige grundlegenden Komponenten installiert, Cloud-Connector hängt von, und klicken Sie dann Windows-Updates installiert. Schließlich verallgemeinert er den virtuellen Computer (Sysprep) um einen Basiskalender VHDX Datei abzurufen, die von den virtuellen Computern einer Cloud-Connector Appliance verwendet werden. 
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Convert-CcIsoToVhdx“ akzeptiert keine Pipelineeingaben.  
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

