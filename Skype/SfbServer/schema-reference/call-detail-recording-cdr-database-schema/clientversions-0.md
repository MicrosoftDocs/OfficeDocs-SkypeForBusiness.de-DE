---
title: ClientVersions-Ansicht
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
description: In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und -versionen gespeichert, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht stellt eine Clientversion dar. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 051a4c475b70eb418bb7a4984f3100c1c3b6209a9028dfe3c522508cd6998a84
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303688"
---
# <a name="clientversions-view"></a>ClientVersions-Ansicht
 
In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und -versionen gespeichert, die an in der Datenbank aufgezeichneten Sitzungen teilgenommen haben. Jeder Datensatz in der Ansicht stellt eine Clientversion dar. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
> [!NOTE]
> Für bestimmte Spalten können mehrere Datensätze vorhanden sein. 
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**VersionId** <br/> |Ganzzahl  <br/> |Eindeutige Zahl, die den Clienttyp und die Clientversion identifiziert.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Stellt den Benutzer-Agent dar.  <br/> |
|**ClientType** <br/> |Ganzzahl  <br/> |Typ des Clients.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Kategorie, zu der der Client gehört. Beispielsweise gehört der Client Conferencing_Attendant_1.0 zur ClientCategory CAA.  <br/> |
   

