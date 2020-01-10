---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Das Cmdlet "Start-CcDownload" lädt die Bits und die MSI-Datei von Skype for Business Cloud Connector Edition synchron herunter.
ms.openlocfilehash: 5c493862151a308208bf83e142421f3257e476e0
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003185"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Das Cmdlet "Start-CcDownload" lädt die Bits und die MSI-Datei von Skype for Business Cloud Connector Edition synchron herunter.
  
Mit Cloud Connector Version 2,0 und höher können Sie auch den DownloadBitsOnly-Parameter angeben.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Cloud Connector-Bits und die MSI-Datei synchron von der öffentlichen Download Website des Cloud Connectors heruntergeladen:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Cloud Connector-Bits und die MSI-Datei synchron von einer privaten Download Website heruntergeladen:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Beispiel 3

Im dritten Beispiel werden die Cloud Connector-Bits und die MSI-Datei synchron von einer privaten Download Website heruntergeladen.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn auf der Download Website eine neue Version verfügbar ist, wird die MSI-Datei von Start-CcDownload von der Download Website heruntergeladen und installiert, und die Cloud Connector-Bits werden dann synchron heruntergeladen. Wenn keine neue Version der MSI-Datei vorhanden ist, werden die Cloud Connector-Bits nur von Start-CcDownload heruntergeladen. Wenn die Cloud Connector-Bits bereits heruntergeladen wurden, wird Start-CcDownload nicht ausgeführt.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Optional  <br/> |System.String  <br/> | Die vollständige URL einer bestimmten Version von Cloud Connector auf der privaten Download Website. Verwenden Sie diesen Parameter mit Bedacht – stellen Sie sicher, dass Sie wissen, welche Version von Cloud Connector Sie herunterladen. <br/> |
|DownloadBitsOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Überspringen Sie den Schritt zum herunterladen und Installieren von MSI von der Download Website, laden Sie nur die Bits für die Cloud-Connectors herunter.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Start-CcDownload-Cmdlet akzeptiert keine Pipeline-Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

