---
title: Export-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3775bd6-682c-4f62-aafc-974fe3a65c61
description: Exportiert die Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition-Hostserver.
ms.openlocfilehash: 7548b2fba602364d98c7540607660ccc57710654
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287419"
---
# <a name="export-ccconfiguration"></a>Export-CcConfiguration
 
Exportiert die Skype for Business Cloud Connector Edition-Konfiguration in eine lokale Datei auf dem Skype for Business Cloud Connector Edition-Hostserver.
  
```
Export-CcConfiguration [-Path] <String> [<CommonParameters>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel wird der path-Parameter als vollständiger Dateipfad festgelegt und Konfigurationen in diese Datei exportiert.
  
```
Export-CcConfiguration -Path "C:\test\CloudConnector.ini" 
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="Examples"> </a>

Mit dem Cmdlet Export-CcConfiguration können Sie die Cloud Connector-Konfiguration in einer Datei in einem ausgewählten Pfad speichern. Dieser Befehl wurde in Cloud Connector Edition, Version 2,0, eingeführt.
  
## <a name="parameters"></a>Parameter
<a name="Examples"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
| Path  <br/> |Erforderlich  <br/> |System.String  <br/> |Vollständiger Dateipfad, in dem die Cloud Connector-Konfigurationen gespeichert werden.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="Examples"> </a>

Keine. Das Cmdlet "Export-CcConfiguration" akzeptiert keine Pipeline-Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="Examples"> </a>

Keine.
  
## <a name="see-also"></a>Siehe auch
<a name="Examples"> </a>

Import-CcConfiguration
  

