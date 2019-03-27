---
title: Start-CcDownload
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/8/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Das Cmdlet Start-CcDownload downloads der Skype für Business Cloud Connector Edition Bits und MSI-Datei synchron.
ms.openlocfilehash: cc157825df75a4534422cb0a2fd07abb0ae0daea
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893838"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Das Cmdlet Start-CcDownload downloads der Skype für Business Cloud Connector Edition Bits und MSI-Datei synchron.
  
Mit der Cloud Connector, Version 2.0 und höher können Sie auch den DownloadBitsOnly-Parameter angeben.
  
```
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird lädt die Cloud Connector Bits und MSI-Datei synchron aus der Downloadsite für die öffentliche Cloud Connector:
  
```
Start-CcDownload
```

### <a name="example-2"></a>Beispiel 2

Im nächste Beispiel lädt die Cloud Connector Bits und MSI-Datei synchron aus einer privaten Download-Website:
  
```
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Beispiel 3

Im dritte Beispiel lädt die Cloud Connector Bits und MSI-Datei synchron aus einer privaten Download-Website.
  
```
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn in der Download-Website eine neue Version verfügbar ist, stellt Start CcDownload herunterladen und installieren Sie die MSI-Datei von der Downloadsite und Laden Sie die Cloud Connector Bits synchron. Wenn keine neue Version der MSI-Datei vorhanden ist, wird Start CcDownload nur die Cloud Connector Bits herunterladen. Wenn die Bits Cloud Connector bereits heruntergeladen werden, wird die Start-CcDownload nicht ausgeführt.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Optional  <br/> |System.String  <br/> | Die vollständige URL einer bestimmten Version von Cloud-Connector in der privaten Downloadsite. Verwenden Sie diesen Parameter mit Bedacht – achten, welche Version von Cloud-Connector Sie herunterladen bekannt sind. <br/> |
|DownloadBitsOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Überspringen Sie den Schritt zum Herunterladen und Installieren von MSI von Download-Website, nur die Cloud Connector Bits herunterladen.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet Start-CcDownload akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine 
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

