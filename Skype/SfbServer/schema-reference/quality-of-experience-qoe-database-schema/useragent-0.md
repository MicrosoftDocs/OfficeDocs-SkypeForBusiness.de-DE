---
title: UserAgent-Ansicht
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent-Ansicht speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 8df1d45ed1272a886a440aded79a9c4e04c1bae8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-view"></a>UserAgent-Ansicht
 
UserAgent-Ansicht speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Benutzeragenten-Zeichenfolge.  <br/> |
|UAType  <br/> |smallint  <br/> |Typ des Benutzer-Agent. Finden Sie weitere Details der [UserAgent-Tabelle](useragent.md) . <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Die Kategorie, der Benutzer-Agent gehört. Der Benutzer-Agent Conferencing_Attendant_1.0 beispielsweise die UACategory CAA gehört.  <br/> |
   

