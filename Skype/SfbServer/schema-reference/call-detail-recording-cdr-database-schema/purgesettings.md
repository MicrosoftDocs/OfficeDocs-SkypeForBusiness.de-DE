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
description: 'Die Tabelle "PurgeSettings" enthält Informationen, mit denen angegeben wird, ob (und wann) veraltete Kommunikationsdatensätze automatisch aus der KDS-Datenbank gelöscht werden. Beachten Sie, dass Informationen zum Löschen auch über Skype for Business Server 2015 bezogen werden können, indem Sie den folgenden Befehl ausführen:'
ms.openlocfilehash: 2e834f64ca5500f8d8bab1d89fb263d2708fa60c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098661"
---
# <a name="purgesettings-table"></a>Tabelle "PurgeSettings"
 
Die Tabelle "PurgeSettings" enthält Informationen, mit denen angegeben wird, ob (und wann) veraltete Kommunikationsdatensätze automatisch aus der KDS-Datenbank gelöscht werden. Beachten Sie, dass Informationen zum Löschen auch über Skype for Business Server 2015 bezogen werden können, indem Sie den folgenden Befehl ausführen:
  
```PowerShell
Get-CsCdrConfiguration
```

Administratoren sollten die Tabelle PurgeSettings als schreibgeschützt behandeln: Änderungen an den Bereinigungseinstellungen für Anrufdetails sollten nur mit den [Cmdlets New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) oder [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) vorgenommen werden.
  
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |Eindeutige Bezeichnung für die Sammlung der KDS-Löscheinstellungen.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Bei True (1) werden in Skype for Business Server 2015 regelmäßig veraltete Datensätze aus der CDR-Datenbank gelöscht. Die Löschung erfolgt täglich zu der durch die Einstellung "PurgeHour" festgelegten Zeit. Wenn die Einstellung auf "False" (0) festgelegt ist, werden die Datensätze nicht automatisch aus der Datenbank gelöscht. Der Standardwert lautet "True".  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Gibt das Alter von KDS-Datensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden KDS-Datensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Gibt das Alter von Fehlerberichtsdatensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden Fehlerberichtsdatensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Gibt die lokale Tageszeit an, zu der die Datenbanklöschung erfolgt. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Tagesstunden angeben können: der Wert 10 (für 10:00 Uhr) ist zwar zulässig, aber der Wert 10:30 oder 10.5 (für 10:30 Uhr) ist unzulässig. Der Standardwert lautet 2 (2:00 Uhr).  <br/> |
