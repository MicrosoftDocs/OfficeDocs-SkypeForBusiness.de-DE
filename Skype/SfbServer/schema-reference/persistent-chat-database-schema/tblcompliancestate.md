---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 96b603ac859664163339a9c5628bdec394881657
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854010"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState enthält poolweite Compliancestatusinformationen.
  
**Columns**

|**Spalte**|**Type**|**Beschreibung**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, nicht NULL  <br/> |ID des letzten verarbeiteten Complianceereignisses.  <br/> |
|activeServerID  <br/> |int, nicht NULL  <br/> |ID des Complianceservers, der die exklusive Sperre für die Datenbank besitzt, oder -1, wenn keines vorhanden ist.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Ablaufzeit sperren (wenn activeServerID nicht -1 ist).  <br/> |
   

