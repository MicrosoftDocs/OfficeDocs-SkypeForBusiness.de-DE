---
title: ErrorDef-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die auftreten können. Jeder Datensatz ist ein Fehlertyp.
ms.openlocfilehash: c4480df63b081fc264334ffeb7031c54de887875
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743881"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>ErrorDef-Tabelle in Skype for Business Server 2015
 
In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die auftreten können. Jeder Datensatz ist ein Fehlertyp.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Errorid** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID-Nummer, die diesen Fehlertyp identifiziert.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Standard-SIP-Antwortcode, der diesem Fehler zugeordnet ist.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft-Diagnose-ID.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Ausländisch  <br/> |Der Anruftyp. Weitere Informationen finden Sie in der [CallType-Tabelle in Skype for Business Server 2015.](calltype.md) <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Typ der fehlgeschlagenen Anforderung.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Inhaltstyp der fehlgeschlagenen Anforderung.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

