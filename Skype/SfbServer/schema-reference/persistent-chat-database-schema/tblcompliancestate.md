---
title: tblComplianceState
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
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState enthält poolweite Compliancestatusinformationen.
ms.openlocfilehash: 6b7f2af97ab25fc7ad2320921941cc7b1828aa1e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746521"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState enthält poolweite Compliancestatusinformationen.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, nicht NULL  <br/> |ID des letzten verarbeiteten Complianceereignisses.  <br/> |
|activeServerID  <br/> |int, nicht NULL  <br/> |ID des Complianceservers, der die exklusive Sperre für die Datenbank besitzt, oder -1, wenn keines vorhanden ist.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Ablaufzeit sperren (wenn activeServerID nicht -1 ist).  <br/> |
   

