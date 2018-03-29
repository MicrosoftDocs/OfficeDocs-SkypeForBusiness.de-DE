---
title: ErrorDef-Tabelle in Skype für Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef-Tabelle speichert Informationen zu jeder Art von Fehler, die auftreten können. Jeder Datensatz ist eine Art von Fehler.
ms.openlocfilehash: 4583e1130d257a99d075f2dec0dea80ee6b1390c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>ErrorDef-Tabelle in Skype für Business Server 2015
 
ErrorDef-Tabelle speichert Informationen zu jeder Art von Fehler, die auftreten können. Jeder Datensatz ist eine Art von Fehler.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Fehler-ID** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID-Nummer, die diesen Fehlertyp identifiziert.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |Standardmäßige SIP-Antwortcode diesem Fehler zugeordnet ist.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft-Diagnose-ID.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Fremdschlüssel  <br/> |Art des Anrufs. [CallType-Tabelle in Skype für Business Server 2015](calltype.md) Weitere Informationen finden Sie. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |Typ der erfolgreichen Anforderung.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Textformat konvertiert werden:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |Inhaltstyp der erfolgreichen Anforderung.  <br/> Diese Daten können mithilfe dieser Syntax in das Textformat in das Textformat konvertiert werden:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

