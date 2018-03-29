---
title: PurgeSettings-Tabelle (QoE)
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'PurgeSettings-Tabelle enthält Informationen, die angibt, ob (und wann) veraltete Quality of Experience-Einträge werden automatisch aus der QoE-Datenbank gelöscht werden. Beachten Sie, dass Bereinigung-bezogene Informationen ebenfalls innerhalb der Skype für Business Server-Verwaltungsshell gewonnen werden kann mithilfe des folgenden Befehls:'
ms.openlocfilehash: 1acccbd796e20f099df895260cb34f9597718cdd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings-Tabelle (QoE)
 
PurgeSettings-Tabelle enthält Informationen, die angibt, ob (und wann) veraltete Quality of Experience-Einträge werden automatisch aus der QoE-Datenbank gelöscht werden. Beachten Sie, dass Bereinigung-bezogene Informationen ebenfalls innerhalb der Skype für Business Server-Verwaltungsshell gewonnen werden kann mithilfe des folgenden Befehls:
  
```
Get-CsQoEConfiguration
```

Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die Auflistung von QoE-löscheinstellungen.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Bei Festlegung auf "true" (1) Microsoft Lync Server 2013 in regelmäßigen Abständen veraltete Einträge aus der QoE-Datenbank endgültig gelöscht werden. Bereinigung wird täglich um die durch die Einstellung der PurgeHour Tome stattfinden. Wenn es sich bei Festlegung auf False (0), klicken Sie dann Datensätze nicht automatisch aus der Datenbank gelöscht. Der Standardwert lautet „True“.  <br/> |
|**"Keepqoedatafordays"** <br/> |int  <br/> ||Gibt das Alter der QoE-Datensätze (in Tagen), die aus der Datenbank gelöscht werden: Wenn der Löschvorgang aktiviert ist, QoE-Datensätze, die älter sind als dieser Wert aus der Datenbank entfernt. Der Standardwert beträgt 60 Tage.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Gibt die lokale Uhrzeit bei der Datenbank stattfinden soll. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Stunde des Tages angeben können: ein Wert von 10 (das angibt, 10:00 Uhr) ist zulässig, aber der Wert 10:30 10.5 (das angibt, 10:30 Uhr) ist nicht zulässig. Der Standardwert ist 1 (1:00 Uhr). Gibt die lokale Uhrzeit bei der Datenbank stattfinden soll. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Stunde des Tages angeben können: ein Wert von 10 (das angibt, 10:00 Uhr) ist zulässig, aber der Wert 10:30 10.5 (das angibt, 10:30 Uhr) ist nicht zulässig. Der Standardwert ist 1 (1:00 Uhr).  <br/> |
   

