---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: "\"tblComplianceState\" enthält Informationen zum poolweiten Kompatibilitätsstatus."
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809725"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
"tblComplianceState" enthält Informationen zum poolweiten Kompatibilitätsstatus.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, nicht NULL  <br/> |ID des zuletzt verarbeiteten Kompatibilitätsereigniss.  <br/> |
|activeServerID  <br/> |int, nicht NULL  <br/> |ID des Kompatibilitätsservers, der die exklusive Sperre für die Datenbank enthält, oder -1, wenn keine vorhanden ist.  <br/> |
|lockExpirationTime  <br/> |datetime2, nicht NULL  <br/> |Sperrablaufzeit (wenn activeServerID nicht -1 ist).  <br/> |
   

