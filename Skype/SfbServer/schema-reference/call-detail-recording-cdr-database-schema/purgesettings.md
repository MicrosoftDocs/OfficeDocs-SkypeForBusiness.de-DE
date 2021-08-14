---
title: PurgeSettings-Tabelle
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
description: 'Die Tabelle "PurgeSettings" enthält Informationen, mit denen angegeben wird, ob (und wann) veraltete Kommunikationsdatensätze automatisch aus der KDS-Datenbank gelöscht werden. Beachten Sie, dass Löschinformationen auch innerhalb der Skype for Business Server 2015 abgerufen werden können, indem Sie den folgenden Befehl ausführen:'
ms.openlocfilehash: 80e8e19a8df9a6f597967a71430686fd399d9bb2e8647989a410845af5b66e0e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343209"
---
# <a name="purgesettings-table"></a>PurgeSettings-Tabelle
 
Die Tabelle "PurgeSettings" enthält Informationen, mit denen angegeben wird, ob (und wann) veraltete Kommunikationsdatensätze automatisch aus der KDS-Datenbank gelöscht werden. Beachten Sie, dass Löschinformationen auch innerhalb der Skype for Business Server 2015 abgerufen werden können, indem Sie den folgenden Befehl ausführen:
  
```PowerShell
Get-CsCdrConfiguration
```

Administratoren sollten die PurgeSettings-Tabelle als schreibgeschützt behandeln: Änderungen an den Einstellungen für die Bereinigung von Kommunikationsdatensätzen sollten nur mithilfe der Cmdlets [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) oder [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) vorgenommen werden.
  
Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Bezeichnung für die Sammlung der KDS-Löscheinstellungen.  <br/> |
|**EnablePurge** <br/> |Bit  <br/> ||Bei Festlegung auf True (1) löscht Skype for Business Server 2015 regelmäßig veraltete Datensätze aus der KDS-Datenbank. Die Löschung erfolgt täglich zu der durch die Einstellung "PurgeHour" festgelegten Zeit. Wenn die Einstellung auf "False" (0) festgelegt ist, werden die Datensätze nicht automatisch aus der Datenbank gelöscht. Der Standardwert lautet "True".  <br/> |
|**KeepCallDetailForDays** <br/> |Ganzzahl  <br/> ||Gibt das Alter von KDS-Datensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden KDS-Datensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.  <br/> |
|**KeepErrorReportForDays** <br/> |Ganzzahl  <br/> ||Gibt das Alter von Fehlerberichtsdatensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: wenn das Löschen aktiviert ist, werden Fehlerberichtsdatensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert lautet 60 Tage.  <br/> |
|**PurgeHour** <br/> |Ganzzahl  <br/> ||Gibt die lokale Tageszeit an, zu der die Datenbanklöschung erfolgt. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Tagesstunden angeben können: der Wert 10 (für 10:00 Uhr) ist zwar zulässig, aber der Wert 10:30 oder 10.5 (für 10:30 Uhr) ist unzulässig. Der Standardwert lautet 2 (2:00 Uhr).  <br/> |
