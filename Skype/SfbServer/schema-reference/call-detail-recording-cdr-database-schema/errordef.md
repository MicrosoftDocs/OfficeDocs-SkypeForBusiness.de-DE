---
title: ErrorDef-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die auftreten können. Jeder Datensatz ist eine Art von Fehler.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296280"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>ErrorDef-Tabelle in Skype for Business Server 2015
 
In der ErrorDef-Tabelle werden Informationen zu den einzelnen Fehlertypen gespeichert, die auftreten können. Jeder Datensatz ist eine Art von Fehler.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ErrorID** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID-Nummer, die diese Art von Fehler kennzeichnet.  <br/> |
|**Response Code** <br/> |int  <br/> | <br/> |Standard mäßiger SIP-Antwortcode, der diesem Fehler zugeordnet ist.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft-Diagnose-ID.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |Fremd  <br/> |Der Typ des Anrufs. Weitere Informationen finden Sie in der Tabelle "CallType" [in Skype for Business Server 2015](calltype.md) . <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |Der Typ der fehlgeschlagenen Anforderung.  <br/> Diese Daten können mithilfe der folgenden Syntax in das Text Format konvertiert werden:  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |Inhaltstyp der fehlgeschlagenen Anforderung.  <br/> Diese Daten können mithilfe dieser Syntax in das Text Format konvertiert werden:  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

