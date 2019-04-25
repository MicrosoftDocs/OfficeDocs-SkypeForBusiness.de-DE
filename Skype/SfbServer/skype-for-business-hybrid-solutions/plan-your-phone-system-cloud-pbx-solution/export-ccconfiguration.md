---
title: Export-CcConfiguration
ms.reviewer: ''
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
ms.openlocfilehash: 8afca55e6727c84c579957de9e2010e84a72fb15
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234056"
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
  

