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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: In der ClientVersions-Ansicht werden Informationen zu den verschiedenen Clienttypen und-Versionen gespeichert, die an Sitzungen teilgenommen haben, die in der Datenbank aufgezeichnet wurden. Jeder Datensatz in der Ansicht stellt eine Client Version dar. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815413"
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
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Die Kategorie, zu der der Client gehört. Beispielsweise gehört der Client Conferencing_Attendant_1 .0 zu ClientCategory CAA.  <br/> |
   

