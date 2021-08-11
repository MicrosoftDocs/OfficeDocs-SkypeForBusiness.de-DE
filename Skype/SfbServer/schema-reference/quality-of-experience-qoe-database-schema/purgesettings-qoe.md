---
title: PurgeSettings-Tabelle (QoE)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'Die PurgeSettings-Tabelle enthält Informationen, die angeben, ob (und wann) veraltete QoE-Datensätze automatisch aus der QoE-Datenbank gelöscht werden. Beachten Sie, dass Löschinformationen auch in der Skype for Business Server Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:'
ms.openlocfilehash: a07b8916cbc4cd2e0073cb11a02fe149a7849f17f9b5f69ad20460d0f19274ad
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306646"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings-Tabelle (QoE)
 
Die PurgeSettings-Tabelle enthält Informationen, die angeben, ob (und wann) veraltete QoE-Datensätze automatisch aus der QoE-Datenbank gelöscht werden. Beachten Sie, dass Löschinformationen auch in der Skype for Business Server Verwaltungsshell abgerufen werden können, indem Sie den folgenden Befehl ausführen:
  
```PowerShell
Get-CsQoEConfiguration
```

Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die Auflistung der QoS-Löscheinstellungen.  <br/> |
|**EnablePurge** <br/> |Bit  <br/> ||Bei Festlegung auf True (1) löscht Microsoft Lync Server 2013 regelmäßig veraltete Datensätze aus der QoE-Datenbank. Die Löschung erfolgt täglich zu der durch die Einstellung "PurgeHour" festgelegten Zeit. Wenn die Einstellung auf "False" (0) festgelegt ist, werden die Datensätze nicht automatisch aus der Datenbank gelöscht. Der Standardwert lautet "True".  <br/> |
|**KeepQoEDataForDays** <br/> |Ganzzahl  <br/> ||Gibt das Alter der QoE-Datensätze (in Tagen) an, die aus der Datenbank gelöscht werden sollen: wenn das Löschen aktiviert ist, werden QoE-Datensätze, die älter als dieser Wert sind, aus der Datenbank gelöscht. Der Standardwert lautet 60 Tage.  <br/> |
|**PurgeHour** <br/> |Ganzzahl  <br/> ||Gibt die lokale Uhrzeit an, zu der der Löschvorgang in der Datenbank stattfindet. Die Uhrzeit wird im 24-Stunden-Format angegeben, wobei Mitternacht (12:00 AM) durch 0 und 11:00 PM durch 23 dargestellt wird. Beachten Sie, dass Sie als Zeitpunkt nur volle Stunden angegeben können: ein Wert von 10 (10:00) ist zulässig, aber ein Wert von 10:30 oder 10,5 (10:30) ist nicht zulässig. Der Standardwert ist 1 (1:00 AM).  <br/> |
   

