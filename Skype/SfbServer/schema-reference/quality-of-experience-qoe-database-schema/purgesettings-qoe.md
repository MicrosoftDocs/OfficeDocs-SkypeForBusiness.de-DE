---
title: PurgeSettings-Tabelle (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'Die PurgeSettings-Tabelle enthält Informationen, die angeben, ob (und wann) veraltete Quality of Experience-Datensätze automatisch aus der QoE-Datenbank gelöscht werden. Beachten Sie, dass Bereinigungs bezogene Informationen auch innerhalb der Skype for Business Server-Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:'
ms.openlocfilehash: dab1b2ffeab5882d0e459d7957b2817e780fc3a4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807333"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings-Tabelle (QoE)
 
Die PurgeSettings-Tabelle enthält Informationen, die angeben, ob (und wann) veraltete Quality of Experience-Datensätze automatisch aus der QoE-Datenbank gelöscht werden. Beachten Sie, dass Bereinigungs bezogene Informationen auch innerhalb der Skype for Business Server-Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:
  
```PowerShell
Get-CsQoEConfiguration
```

Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die Sammlung von QoE-Bereinigungseinstellungen.  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||Bei Festlegung auf true (1) bereinigen Microsoft lync Server 2013 in regelmäßigen Abständen veraltete Datensätze aus der QoE-Datenbank. Das Bereinigen erfolgt täglich im Wälzer, der durch die Einstellung PurgeHour angegeben wird. Bei Festlegung auf "false" (0) werden Datensätze nicht automatisch aus der Datenbank bereinigt. Der Standardwert lautet „True“.  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||Gibt das Alter von QoE-Datensätzen (in Tagen) an, die aus der Datenbank gelöscht werden: Wenn die Bereinigung aktiviert ist, werden QoE-Datensätze, die älter als dieser Wert sind, aus der Datenbank entfernt. Der Standardwert ist 60 Tage.  <br/> |
|**PurgeHour** <br/> |int  <br/> ||Gibt die lokale Tageszeit an, zu der eine Datenbankbereinigung durchgeführt wird. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Stunde des Tages angeben können: der Wert 10 (mit der Angabe von 10:00 Uhr) ist zulässig, aber der Wert 10:30 von 10,5 (mit der Angabe 10:30 Uhr) ist nicht zulässig. Der Standardwert ist 1 (1:00 am). Gibt die lokale Tageszeit an, zu der eine Datenbankbereinigung durchgeführt wird. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie nur die Stunde des Tages angeben können: der Wert 10 (mit der Angabe von 10:00 Uhr) ist zulässig, aber der Wert 10:30 von 10,5 (mit der Angabe 10:30 Uhr) ist nicht zulässig. Der Standardwert ist 1 (1:00 am).  <br/> |
   

