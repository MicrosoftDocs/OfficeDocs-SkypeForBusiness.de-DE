---
title: Search-CcLog
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/20/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: Das Cmdlet Search-CcLog durchsucht die Protokolle für ein- und ausgehende Anrufe im Protokollverzeichnis der Skype for Business Cloud Connector Edition Appliance.
ms.openlocfilehash: b96e0bea7c8a7ac9d3a12c135c828440eea9fb32
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58618691"
---
# <a name="search-cclog"></a>Search-CcLog
 
Das Cmdlet Search-CcLog durchsucht die Protokolle für ein- und ausgehende Anrufe im Protokollverzeichnis der Skype for Business Cloud Connector Edition Appliance.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Protokolle für ein- und ausgehende Anrufe im Appliance-Protokollverzeichnis mithilfe des Standarddateinamens durchsucht:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Protokolle für ein- und ausgehende Anrufe mithilfe des angegebenen Dateipfads und -namens durchsucht:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet "Search-CsClsLogging" bietet eine Befehlszeilenoption zum Durchsuchen der vom zentralisierten Protokollierungsdienst erstellten Protokolldateien.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Required**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Erforderlich <br/> |System.Datetime  <br/> | Anfangsdatum und -uhrzeit für die zu durchsuchenden Protokolleinträge. Angegeben in der lokalen Zeitzone. <br/> |
|EndTime  <br/> |Erforderlich  <br/> |System.Datetime  <br/> |Enddatum und -uhrzeit für die zu durchsuchenden Protokolleinträge. Angegeben in der lokalen Zeitzone.  <br/> |
|FileName  <br/> |Erforderlich  <br/> |System.String  <br/> |Gibt den vollständigen Pfad der Textdatei an, die die Suchergebnisse enthält.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das cmdlet Search-CcLog akzeptiert keine weitergeleitete Eingabe.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

