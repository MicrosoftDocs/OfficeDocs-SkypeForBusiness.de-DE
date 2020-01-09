---
title: PurgeSettings-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'Die Tabelle PurgeSettings enthält Informationen, die angeben, ob (und wann) veraltete Anruf Detaildatensätze automatisch aus der CDR-Datenbank gelöscht werden. Beachten Sie, dass Bereinigungs bezogene Informationen auch innerhalb des Skype for Business Server 2015 abgerufen werden können, indem Sie den folgenden Befehl ausführen:'
ms.openlocfilehash: fbbd7908446fdb042c8fdfa2f0c8bec2d83b24d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992915"
---
# <a name="purgesettings-table"></a>PurgeSettings-Tabelle
 
Die Tabelle PurgeSettings enthält Informationen, die angeben, ob (und wann) veraltete Anruf Detaildatensätze automatisch aus der CDR-Datenbank gelöscht werden. Beachten Sie, dass Bereinigungs bezogene Informationen auch innerhalb des Skype for Business Server 2015 abgerufen werden können, indem Sie den folgenden Befehl ausführen:
  
```PowerShell
Get-CsCdrConfiguration
```

Administratoren sollten die PurgeSettings-Tabelle schreibgeschützt behandeln: Änderungen an den Einstellungen für das Bereinigen des Anrufdetails sollten nur mithilfe der Cmdlets [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) oder [setCsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) erfolgen.
  
Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die Sammlung von CDR-Bereinigungseinstellungen.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Wenn Sie auf true (1) festgelegt ist, bereinigen Skype for Business Server 2015 in regelmäßigen Abständen veraltete Datensätze aus der CDR-Datenbank Das Bereinigen erfolgt täglich im Wälzer, der durch die Einstellung PurgeHour angegeben wird. Bei Festlegung auf "false" (0) werden Datensätze nicht automatisch aus der Datenbank bereinigt. Der Standardwert lautet „True“.  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||Gibt das Alter von CDR-Einträgen (in Tagen) an, die aus der Datenbank gelöscht werden: Wenn die Bereinigung aktiviert ist, werden CdR-Einträge, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert ist 60 Tage.  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||Gibt das Alter von Fehlerberichts Einträgen (in Tagen) an, die aus der Datenbank gelöscht werden: Wenn die Bereinigung aktiviert ist, werden Fehlerberichts Einträge, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert ist 60 Tage.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Gibt die lokale Tageszeit an, zu der eine Datenbankbereinigung durchgeführt wird. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Stunde des Tages angeben können: der Wert 10 (mit der Angabe von 10:00 Uhr) ist zulässig, aber der Wert 10:30 von 10,5 (mit der Angabe 10:30 Uhr) ist nicht zulässig. Der Standardwert lautet 2 (2:00 Uhr).  <br/> |
   

