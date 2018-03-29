---
title: Export-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Die Skype für Business Cloud Connector Edition-Konfiguration exportiert in einer lokalen Datei auf die Skype für Hostserver Business Cloud Connector Edition.
ms.openlocfilehash: dfabf5f486190b13acd18f0ffcf67f9b7e37052c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Die Skype für Business Cloud Connector Edition-Konfiguration exportiert in einer lokalen Datei auf die Skype für Hostserver Business Cloud Connector Edition.
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgende Beispiel wird den Parameter Path als einen vollständigen Dateipfad und Konfigurationen in dieser Datei exportiert.
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="Examples"> </a>

Das Cmdlet Export-CcConfiguration können Sie die Cloud Connectorkonfiguration in eine Datei in einem ausgewählten Pfad zu speichern. Mit diesem Befehl wurde in der Cloud Connector Edition, Version 2.0 eingeführt.
  
## <a name="parameters"></a>Parameter
<a name="Examples"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Path  <br/> |Erforderlich  <br/> |System.String  <br/> |Vollständigen Pfad, in dem die Cloud Connector Konfigurationen gespeichert werden.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="Examples"> </a>

Keine. Das Cmdlet Export-CcConfiguration akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="Examples"> </a>

Keine.
  
## <a name="see-also"></a>Siehe auch
<a name="Examples"> </a>

Import-CcConfiguration
  

