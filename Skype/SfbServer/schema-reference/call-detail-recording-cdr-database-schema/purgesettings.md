---
title: Tabelle "PurgeSettings"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'Die Tabelle "PurgeSettings" enthält Informationen, mit denen angegeben wird, ob (und wann) veraltete Kommunikationsdatensätze automatisch aus der KDS-Datenbank gelöscht werden. Beachten Sie, dass Bereinigungsinformationen auch aus Skype for Business Server 2015 durch Ausführen des folgenden Befehls bezogen werden können:'
ms.openlocfilehash: c90c36dc91eaaac6fe38c6eea8e2a5617264e200
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823165"
---
# <a name="purgesettings-table"></a>Tabelle "PurgeSettings"
 
Die Tabelle "PurgeSettings" enthält Informationen, mit denen angegeben wird, ob (und wann) veraltete Kommunikationsdatensätze automatisch aus der KDS-Datenbank gelöscht werden. Beachten Sie, dass Bereinigungsinformationen auch aus Skype for Business Server 2015 durch Ausführen des folgenden Befehls bezogen werden können:
  
```PowerShell
Get-CsCdrConfiguration
```

Administratoren sollten die Tabelle "PurgeSettings" als schreibgeschützt behandeln: Änderungen an den Bereinigungseinstellungen für Anrufdetails sollten nur mit den Cmdlets ["New-CsCdrConfiguration"](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) oder ["Set-CsCdrConfiguration"](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) vorgenommen werden.
  
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Primary  <br/> |Eindeutige Bezeichnung für die Sammlung der KDS-Löscheinstellungen.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Bei "True" (1) werden in Skype for Business Server 2015 regelmäßig veraltete Datensätze aus der Datenbank für die Aufzeichnung von Aufzeichnungen gelöscht. Die Löschung erfolgt täglich zu der durch die Einstellung "PurgeHour" festgelegten Zeit. Wenn die Einstellung auf "False" (0) festgelegt ist, werden die Datensätze nicht automatisch aus der Datenbank gelöscht. Der Standardwert lautet "True".  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Gibt das Alter von KDS-Datensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden KDS-Datensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Gibt das Alter von Fehlerberichtsdatensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden Fehlerberichtsdatensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Gibt die lokale Tageszeit an, zu der die Datenbanklöschung erfolgt. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Tagesstunden angeben können: der Wert 10 (für 10:00 Uhr) ist zwar zulässig, aber der Wert 10:30 oder 10.5 (für 10:30 Uhr) ist unzulässig. Der Standardwert lautet 2 (2:00 Uhr).  <br/> |
   

