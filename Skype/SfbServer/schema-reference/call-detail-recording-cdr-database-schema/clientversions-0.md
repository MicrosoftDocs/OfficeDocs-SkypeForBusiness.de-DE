---
title: ClientVersions-Ansicht
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und -versionen gespeichert, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht stellt eine Clientversion dar. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 7e44806e817c6010bb9d14ff2f29c118ac9a290b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854189"
---
# <a name="clientversions-view"></a>ClientVersions-Ansicht
 
In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und -versionen gespeichert, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht stellt eine Clientversion dar. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Für bestimmte Spalten können mehrere Datensätze vorhanden sein. 
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Eindeutige Zahl, die den Clienttyp und die Clientversion identifiziert.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Stellt den Benutzer-Agent dar.  <br/> |
|**ClientType** <br/> |int  <br/> |Typ des Clients.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Kategorie, zu der der Client gehört. Beispielsweise gehört der Client Conferencing_Attendant_1.0 zur ClientCategory CAA.  <br/> |
   

