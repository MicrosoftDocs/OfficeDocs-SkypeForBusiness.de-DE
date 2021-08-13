---
title: ErrorDef-Tabelle in Skype for Business Server 2015
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die auftreten können. Jeder Datensatz ist ein Fehlertyp.
ms.openlocfilehash: 428ce365de65be4d0bcd3776bfc069ffc9246fd869c54d819c6468f926c64351
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54344604"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>ErrorDef-Tabelle in Skype for Business Server 2015
 
In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die auftreten können. Jeder Datensatz ist ein Fehlertyp.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Errorid** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige ID-Nummer, die diesen Fehlertyp identifiziert.  <br/> |
|**ResponseCode** <br/> |Ganzzahl  <br/> | <br/> |Standard-SIP-Antwortcode, der diesem Fehler zugeordnet ist.  <br/> |
|**MsDiagId** <br/> |Ganzzahl  <br/> | <br/> |Microsoft-Diagnose-ID.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Ausländisch  <br/> |Der Anruftyp. Weitere Informationen finden Sie in der [CallType-Tabelle in Skype for Business Server 2015.](calltype.md) <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Typ der fehlgeschlagenen Anforderung.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Inhaltstyp der fehlgeschlagenen Anforderung.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

