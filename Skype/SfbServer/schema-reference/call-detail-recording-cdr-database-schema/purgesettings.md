---
title: PurgeSettings-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'PurgeSettings-Tabelle enthält Informationen, die angibt, ob (und wann) veraltete kommunikationsdatensätze automatisch aus der CDR-Datenbank gelöscht. Beachten Sie, dass Bereinigung-bezogene Informationen ebenfalls innerhalb der Skype für Business Server 2015 gewonnen werden kann mithilfe des folgenden Befehls:'
ms.openlocfilehash: a28ac592fb1d5d2001e7f297f37fdc1938f25643
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table"></a>PurgeSettings-Tabelle
 
PurgeSettings-Tabelle enthält Informationen, die angibt, ob (und wann) veraltete kommunikationsdatensätze automatisch aus der CDR-Datenbank gelöscht. Beachten Sie, dass Bereinigung-bezogene Informationen ebenfalls innerhalb der Skype für Business Server 2015 gewonnen werden kann mithilfe des folgenden Befehls:
  
```
Get-CsCdrConfiguration
```

Administratoren sollten der Tabelle "PurgeSettings" schreibgeschützt behandeln: Änderungen an den löscheinstellungen für Anrufdetails sollten nur mit den Cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) oder [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) vorgenommen werden.
  
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die Sammlung der KDS-löscheinstellungen.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Bei Festlegung auf True (1) Skype für Business Server 2015 in regelmäßigen Abständen endgültig gelöscht werden, veraltete Datensätze aus der CDR-Datenbank. Bereinigung wird täglich um die durch die Einstellung der PurgeHour Tome stattfinden. Wenn es sich bei Festlegung auf False (0), klicken Sie dann Datensätze nicht automatisch aus der Datenbank gelöscht. Der Standardwert lautet „True“.  <br/> |
|**"Keepcalldetailfordays"** <br/> |int  <br/> ||Gibt das Alter der CDR-Datensätze (in Tagen), die aus der Datenbank gelöscht werden: Wenn der Löschvorgang aktiviert ist, CDR-Datensätzen, die älter sind als dieser Wert aus der Datenbank entfernt. Der Standardwert beträgt 60 Tage.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Gibt das Alter der Fehler Bericht Datensätze (in Tagen), die aus der Datenbank gelöscht werden: Wenn der Löschvorgang aktiviert ist, werden Fehler Bericht Datensätze älter sind als dieser Wert aus der Datenbank entfernt. Der Standardwert beträgt 60 Tage.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Gibt die lokale Uhrzeit bei der Datenbank stattfinden soll. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Stunde des Tages angeben können: ein Wert von 10 (das angibt, 10:00 Uhr) ist zulässig, aber der Wert 10:30 10.5 (das angibt, 10:30 Uhr) ist nicht zulässig. Der Standardwert lautet 2 (2:00 Uhr).  <br/> |
   

