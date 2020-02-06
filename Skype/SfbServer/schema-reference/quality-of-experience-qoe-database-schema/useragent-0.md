---
title: UserAgent-Ansicht
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: Die UserAgent-Ansicht speichert Informationen zu den Benutzer-Agents, die an Sitzungen teilgenommen haben, die Datensätze in der Datenbank aufweisen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 76ac99b1fdadbeb6817b36483f4fe5762db47333
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805083"
---
# <a name="useragent-view"></a>UserAgent-Ansicht
 
Die UserAgent-Ansicht speichert Informationen zu den Benutzer-Agents, die an Sitzungen teilgenommen haben, die Datensätze in der Datenbank aufweisen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Eindeutige Nummer, die diesen Benutzer-Agent kennzeichnet.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Benutzer-Agent-Zeichenfolge.  <br/> |
|UAType  <br/> |smallint  <br/> |Der Typ des Benutzer-Agents. Weitere Informationen finden Sie in der [userAgent-Tabelle](useragent.md) . <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |Die Kategorie, zu der der Benutzer-Agent gehört. Beispielsweise gehört der Benutzer-Agent Conferencing_Attendant_1 .0 zu UACategory CAA.  <br/> |
   

