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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19338a34-1bfb-4787-b057-5e34a333711d
description: Das Cmdlet Start-CcDownload lädt die Skype for Business Cloud Connector Edition Bits und die MSI-Datei synchron herunter.
ms.openlocfilehash: 0447c75ac3e6df79a20d2c87b664bfb92cf7124fc7253c839a88fad1b335eaec
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351914"
---
# <a name="start-ccdownload"></a>Start-CcDownload
 
Das Cmdlet Start-CcDownload lädt die Skype for Business Cloud Connector Edition Bits und die MSI-Datei synchron herunter.
  
Mit Cloud Connector, Version 2.0 und höher, können Sie auch den DownloadBitsOnly-Parameter angeben.
  
```powershell
Start-CcDownload [[-DownloadUrlRoot] <string>] [-DownloadBitsOnly]  [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Cloud Connector-Bits und die MSI-Datei synchron von der öffentlichen Cloud Connector-Downloadwebsite heruntergeladen:
  
```powershell
Start-CcDownload
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Cloud Connector-Bits und die MSI-Datei synchron von einer privaten Downloadwebsite heruntergeladen:
  
```powershell
Start-CcDownload -DownloadUrlRoot "http://downloadserver/cloudconnector/latest"
```

### <a name="example-3"></a>Beispiel 3

Im dritten Beispiel werden die Cloud Connector-Bits und die MSI-Datei synchron von einer privaten Downloadwebsite heruntergeladen.
  
```powershell
Start-CcDownload -DownloadBitsOnly
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Wenn auf der Downloadwebsite eine neue Version verfügbar ist, werden Start-CcDownload die MSI-Datei von der Downloadwebsite herunterladen und installieren und dann die Cloud Connector-Bits synchron herunterladen. Wenn keine neue Version der MSI-Datei vorhanden ist, lädt Start-CcDownload nur die Cloud Connector-Bits herunter. Wenn die Cloud Connector-Bits bereits heruntergeladen wurden, wird Start-CcDownload nicht ausgeführt.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|DownloadUrlRoot  <br/> | Optional <br/> |System.String  <br/> | Die vollständige URL einer bestimmten Version von Cloud Connector auf der privaten Downloadwebsite. Verwenden Sie diesen Parameter mit Vorsicht – achten Sie darauf, dass Sie wissen, welche Version von Cloud Connector Sie herunterladen. <br/> |
|DownloadBitsOnly  <br/> |Optional  <br/> |System.Management.Automation.SwitchParameter  <br/> |Überspringen Sie den Schritt, um MSI von der Downloadwebsite herunterzuladen und zu installieren, und laden Sie nur die Cloud Connector-Bits herunter.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Start-CcDownload akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

Keine
  

