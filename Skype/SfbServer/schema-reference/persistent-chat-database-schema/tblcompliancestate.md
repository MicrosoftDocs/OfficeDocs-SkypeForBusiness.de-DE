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
description: tblComplianceState enthält poolweite Compliancestatusinformationen.
ms.openlocfilehash: c9027068550b4320e1e7d170ee23b6cb6e060d6162583132f927c720c09d6ebe
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315421"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState enthält poolweite Compliancestatusinformationen.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, nicht NULL  <br/> |ID des letzten verarbeiteten Complianceereignisses.  <br/> |
|activeServerID  <br/> |int, nicht NULL  <br/> |ID des Complianceservers, der die exklusive Sperre für die Datenbank besitzt, oder -1, wenn keines vorhanden ist.  <br/> |
|lockExpirationTime  <br/> |datetime2, not null  <br/> |Ablaufzeit sperren (wenn activeServerID nicht -1 ist).  <br/> |
   

