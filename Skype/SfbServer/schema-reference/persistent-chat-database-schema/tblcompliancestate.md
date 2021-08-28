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
ms.localizationpriority: medium
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState enthält poolweite Compliancestatusinformationen.
ms.openlocfilehash: c96f43c27179d5dd933aeba7f1483be3e1f7ee7e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580399"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState enthält poolweite Compliancestatusinformationen.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, nicht NULL  <br/> |ID des letzten verarbeiteten Complianceereignisses.  <br/> |
|activeServerID  <br/> |int, nicht NULL  <br/> |ID des Complianceservers, der die exklusive Sperre für die Datenbank besitzt, oder -1, wenn keines vorhanden ist.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Ablaufzeit sperren (wenn activeServerID nicht -1 ist).  <br/> |
   

