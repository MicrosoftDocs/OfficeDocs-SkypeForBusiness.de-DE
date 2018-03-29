---
title: tblComplianceState
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: TblComplianceState enthält poolweite Informationen zum kompatibilitätszustand.
ms.openlocfilehash: e46db9c73f4489ade9bbed90f0061567fd14af1d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
TblComplianceState enthält poolweite Informationen zum kompatibilitätszustand.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |Bigint, nicht null  <br/> |ID des letzten verarbeiteten kompatibilitätsereignisses.  <br/> |
|activeServerID  <br/> |Int, nicht null  <br/> |Die Einhaltung von Bestimmungen gedrückt halten die exklusive Sperre für die Datenbank oder -1, wenn keine ID.  <br/> |
|lockExpirationTime  <br/> |datetime2, nicht null  <br/> |Sperren Sie Ablaufzeit (wenn ActiveServerID nicht-1 ist).  <br/> |
   

