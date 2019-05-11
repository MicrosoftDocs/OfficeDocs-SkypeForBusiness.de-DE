---
title: UserAgent-Ansicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: UserAgent-Ansicht speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 942093ece5706115cc4e90171c09df8a8a169b09
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907024"
---
# <a name="useragent-view"></a>UserAgent-Ansicht
 
UserAgent-Ansicht speichert Informationen über die Benutzeragents, die an Sitzungen beteiligt waren, die Datensätze in der Datenbank verfügen. Diese Ansicht wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Eindeutige Zahl, die diesen Benutzer-Agent identifiziert.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Benutzeragenten-Zeichenfolge.  <br/> |
|UAType  <br/> |smallint  <br/> |Typ des Benutzer-Agent. Finden Sie weitere Details der [UserAgent-Tabelle](useragent.md) . <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Die Kategorie, der Benutzer-Agent gehört. Der Benutzer-Agent Conferencing_Attendant_1.0 beispielsweise die UACategory CAA gehört.  <br/> |
   

