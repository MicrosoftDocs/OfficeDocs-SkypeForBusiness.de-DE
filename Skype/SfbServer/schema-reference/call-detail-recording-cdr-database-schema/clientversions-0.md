---
title: Ansicht "ClientVersions"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: In der Ansicht "ClientVersions" werden Informationen zu den verschiedenen Clienttypen und Versionen gespeichert, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht stellt eine Clientversion dar. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813355"
---
# <a name="clientversions-view"></a>Ansicht "ClientVersions"
 
In der Ansicht "ClientVersions" werden Informationen zu den verschiedenen Clienttypen und Versionen gespeichert, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht stellt eine Clientversion dar. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Es können mehrere Datensätze für bestimmte Spalten enthalten sein. 
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Eindeutige Zahl, die den Clienttyp und die Clientversion identifiziert.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Stellt den Benutzer-Agent dar.  <br/> |
|**ClientType** <br/> |int  <br/> |Clienttyp.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Kategorie, zu der der Client gehört. Beispielsweise gehört der Client Conferencing_Attendant_1.0 zur ClientCategory CAA.  <br/> |
   

