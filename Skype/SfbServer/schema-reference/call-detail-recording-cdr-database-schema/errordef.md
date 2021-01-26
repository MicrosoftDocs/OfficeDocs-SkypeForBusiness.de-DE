---
title: Tabelle "ErrorDef" in Skype for Business Server 2015
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
description: In der Tabelle "ErrorDef" werden Informationen zu jedem Fehlertyp, der auftreten kann, speichert. Jeder Datensatz ist ein Fehlertyp.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821725"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>Tabelle "ErrorDef" in Skype for Business Server 2015
 
In der Tabelle "ErrorDef" werden Informationen zu jedem Fehlertyp, der auftreten kann, speichert. Jeder Datensatz ist ein Fehlertyp.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID-Nummer, die diesen Fehlertyp identifiziert.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Standard-SIP-Antwortcode, der diesem Fehler zugeordnet ist.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft-Diagnose-ID.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Fremd  <br/> |Der Anruftyp. Weitere Informationen finden Sie in der [Tabelle "CallType" in Skype for Business Server 2015.](calltype.md) <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Typ der fehlgeschlagenen Anforderung.  <br/> Diese Daten können mit der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Inhaltstyp der fehlgeschlagenen Anforderung.  <br/> Diese Daten können mit der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

