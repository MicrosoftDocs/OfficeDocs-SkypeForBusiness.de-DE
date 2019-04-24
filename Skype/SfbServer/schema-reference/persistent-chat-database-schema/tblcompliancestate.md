---
title: tblComplianceState
ms.reviewer: ''
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
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212635"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
TblComplianceState enthält poolweite Informationen zum kompatibilitätszustand.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |Bigint, nicht null  <br/> |ID des letzten verarbeiteten kompatibilitätsereignisses.  <br/> |
|activeServerID  <br/> |Int, nicht null  <br/> |Die Einhaltung von Bestimmungen gedrückt halten die exklusive Sperre für die Datenbank oder -1, wenn keine ID.  <br/> |
|lockExpirationTime  <br/> |datetime2, nicht null  <br/> |Sperren Sie Ablaufzeit (wenn ActiveServerID nicht-1 ist).  <br/> |
   

