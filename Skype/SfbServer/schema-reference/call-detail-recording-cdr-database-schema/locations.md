---
title: Tabelle "Standorte" in Skype for Business Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Jeder Datensatz stellt den Verweis auf einen Standort in einem Notruf (z. B. ein E9-1-1-Anruf) dar.
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821515"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Tabelle "Standorte" in Skype for Business Server 2015
 
Jeder Datensatz stellt den Verweis auf einen Standort in einem Notruf (z. B. ein E9-1-1-Anruf) dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Tabelle "Dialogfelder" in Skype for Business Server 2015.](dialogs.md) <br/> |
|**Ort** <br/> |nvarchar(max)  <br/> ||Standort des Notrufs.  <br/> |
   

