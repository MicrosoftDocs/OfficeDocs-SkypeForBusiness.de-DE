---
title: Convert-CcIsoToVhdx
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
localization_priority: Normal
ms.assetid: 216abec2-d354-4ee3-9999-0a6b350a4a5f
description: Das cmdlet Convert-CcIsoToVhdx erstellt eine virtuelle Basisfestplattendatei (VHDX) mithilfe eines Kunden, der Windows Server 2012 R2-ISO-Datei bereitgestellt wird. Die VHDX-Datei wird während der Bereitstellung von Skype for Business Cloud Connector Edition verwendet.
ms.openlocfilehash: d168155c918ba1e8a3a576e543eed6693d0fb6faa5bd4fc23efd8c95b2b50fa1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349547"
---
# <a name="convert-ccisotovhdx"></a>Convert-CcIsoToVhdx
 
Das cmdlet Convert-CcIsoToVhdx erstellt eine virtuelle Basisfestplattendatei (VHDX) mithilfe eines Kunden, der Windows Server 2012 R2-ISO-Datei bereitgestellt wird. Die VHDX-Datei wird während der Bereitstellung von Skype for Business Cloud Connector Edition verwendet.
  
```powershell
Convert-CcIsoToVhdx [[-IsoFilePath] <string>] [-GeneralizeOnly] [-PauseBeforeUpdate]
```

## <a name="parameters"></a>Parameter

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|IsoFilePath  <br/> | Erforderlich <br/> |System.String  <br/> | Der Pfad zur Windows Server 2012 R2-ISO-Datei. <br/> |
|GeneralizeOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Wenn der Konvertierungsprozess während Windows Update fehlschlägt, können Sie versuchen, ein Netzwerk/Proxy zu konfigurieren und Windows manuell zu aktualisieren. Nach Abschluss der manuellen Arbeit können Sie dieses Cmdlet mit dem Parameter "-GeneralizeOnly" ausführen und die verbleibenden Aufträge abschließen.  <br/> |
|PauseBeforeUpdate  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Um Windows zu aktualisieren, ist möglicherweise eine manuelle Netzwerk-/Proxykonfiguration auf dem virtuellen Basiscomputer erforderlich. Der Konvertierungsprozess wird angehalten, bevor Windows aktualisiert wird, wenn dieser Parameter bereitgestellt wird. Nach Abschluss der manuellen Konfiguration können Sie den Vorgang fortsetzen.  <br/> |
   
## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird die VHDX-Basisdatei mithilfe einer Windows Server 2012 R2-ISO-Datei unter "C:\Windows_Server_2012_R2-EN-US-x64.ISO" vorbereitet: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" 
```

### <a name="example-2"></a>Beispiel 2

Wenn das cmdlet Convert-CcIsoToVhdx während Windows Update fehlschlägt, liegt dies wahrscheinlich an einer falschen Netzwerk-/Proxykonfiguration. Sie können die Anweisungen in der Fehlermeldung befolgen und sich beim virtuellen Basiscomputer anmelden, um das Problem zu beheben und Windows manuell zu aktualisieren. Führen Sie das Cmdlet nach Abschluss der manuellen Arbeit erneut mit dem Parameter "-GeneralizeOnly" aus, um die verbleibenden Aufträge abzuschließen: 
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -GeneralizeOnly
```

### <a name="example-3"></a>Beispiel 3

Wenn zum Aktualisieren Windows eine manuelle Konfiguration erforderlich ist, können Sie den Parameter "-PauseBeforeUpdate" verwenden. Mit diesem Parameter wird Cloud Connector vor dem Windows Updatevorgang angehalten. Anschließend können Sie die manuelle Konfiguration abschließen und den Konvertierungsprozess wie folgt fortsetzen:
  
```powershell
Convert-CcIsoToVhdx -IsoFilePath "C:\Windows_Server_2012_R2-EN-US-x64.ISO" -PauseBeforeUpdate 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das cmdlet Convert-CcIsoToVhdx erstellt zuerst eine Basis-VM, installiert einige grundlegende Komponenten, von denen Cloud Connector abhängt, und installiert dann Windows Updates. Schließlich wird der virtuelle Computer (sysprep) generalisiert, um eine VHDX-Basisdatei abzurufen, die von den virtuellen Computern einer Cloud Connector-Appliance verwendet wird. 
  
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Convert-CcIsoToVhdx akzeptiert keine weitergeleitete Eingabe. 
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

