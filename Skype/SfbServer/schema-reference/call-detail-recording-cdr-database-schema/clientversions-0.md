---
title: ClientVersions-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und-Versionen gespeichert, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Ansicht stellt eine Client Version dar. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 845a6fdb88ba62273413d8e7ea50fb165f0f321c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296539"
---
# <a name="clientversions-view"></a>ClientVersions-Ansicht
 
In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und-Versionen gespeichert, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Ansicht stellt eine Client Version dar. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
> [!NOTE]
> Für bestimmte Spalten können mehrere Datensätze vorhanden sein. 
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|**VersionID** <br/> |int  <br/> |Eindeutige Nummer, die diesen Clienttyp und die Version identifiziert.  <br/> |
|**Version** <br/> |nvarchar(256)  <br/> |Stellt den Benutzer-Agent dar.  <br/> |
|**Clienttyp** <br/> |int  <br/> |Der Typ des Clients.  <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Die Kategorie, zu der der Client gehört. Beispielsweise gehört der Client conferencing_attendant_ 1.0 zum ClientCategory CAA.  <br/> |
   

