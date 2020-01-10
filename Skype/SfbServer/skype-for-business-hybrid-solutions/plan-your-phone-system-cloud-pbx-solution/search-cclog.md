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
localization_priority: Normal
ms.assetid: bbae05f9-d8de-40dc-8968-d225dcde80e4
description: Das Cmdlet „Search-CcLog“ durchsucht die Listen für ein- und ausgehende Anrufe im Protokollverzeichnis der Skype for Business Cloud Connector Edition-Appliance.
ms.openlocfilehash: c248720931ef1c15d633c51bb6daa6c414631a18
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003235"
---
# <a name="search-cclog"></a>Search-CcLog
 
Das Cmdlet „Search-CcLog“ durchsucht die Listen für ein- und ausgehende Anrufe im Protokollverzeichnis der Skype for Business Cloud Connector Edition-Appliance.
  
```powershell
Search-CcLog [[-StartTime] <datetime>] [[-EndTime] <datetime>] [[-FileName] <string>]
```

## <a name="examples"></a>Beispiele
<a name="Examples"> </a>

### <a name="example-1"></a>Beispiel 1

Im folgenden Beispiel werden die Listen für ein- und ausgehende Anrufe im Protokollverzeichnis der Appliance mithilfe des Standarddateinamens durchsucht:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM"
```

### <a name="example-2"></a>Beispiel 2

Im nächsten Beispiel werden die Listen für ein- und ausgehende Anrufe mithilfe des angegebenen Dateipfads und Namens durchsucht:
  
```powershell
Search-CcLog -StartTime "8/31/2012 8:00AM" -EndTime "8/31/2012 6:00PM" -FileName "C:\Log\LogFile.log"
```

## <a name="detailed-description"></a>Detaillierte Beschreibung
<a name="DetailedDescription"> </a>

Das Cmdlet  Search-CsClsLogging bietet eine Befehlszeilenoption zum Durchsuchen der vom zentralisierten Protokollierungsdienst erstellten Protokolldateien.
  
## <a name="parameters"></a>Parameter
<a name="DetailedDescription"> </a>

|**Parameter**|**Erforderlich**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|:-----|
|StartTime  <br/> | Erforderlich <br/> |System.Datetime  <br/> |  Anfangszeitpunkt (Datum und Uhrzeit) für die zu durchsuchenden Protokolleinträge. Wird in der lokalen Zeitzone angegeben. <br/> |
|EndTime  <br/> |Erforderlich  <br/> |System.Datetime  <br/> |Endzeitpunkt (Datum und Uhrzeit) für die zu durchsuchenden Protokolleinträge. Wird in der lokalen Zeitzone angegeben.  <br/> |
|FileName  <br/> | Erforderlich  <br/> |System.String  <br/> |Gibt den vollständigen Pfad der Textdatei mit den Suchergebnissen an.  <br/> |
   
## <a name="input-types"></a>Eingabetypen
<a name="InputTypes"> </a>

Keine. Das Cmdlet „Search-CcLog“ akzeptiert keine Pipelineeingaben.
  
## <a name="return-types"></a>Rückgabetypen
<a name="ReturnTypes"> </a>

Keine
  
## <a name="see-also"></a>Siehe auch
<a name="ReturnTypes"> </a>

[Start-CcLogging](start-cclogging.md)
  
[Stop-CcLogging](stop-cclogging.md)
  

