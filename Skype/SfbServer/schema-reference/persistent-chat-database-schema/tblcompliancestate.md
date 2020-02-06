---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState enthält Informationen zum Kompatibilitätszustand des Pools.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814633"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState enthält Informationen zum Kompatibilitätszustand des Pools.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, nicht NULL  <br/> |Die ID des letzten verarbeiteten Compliance-Ereignisses.  <br/> |
|activeServerID  <br/> |int, nicht NULL  <br/> |Die ID des Kompatibilitätsservers, auf dem die exklusive Sperre für die Datenbank gespeichert ist, oder-1, wenn kein.  <br/> |
|lockExpirationTime  <br/> |datetime2, nicht NULL  <br/> |Ablaufzeit Sperren (wenn activeServerID nicht-1 ist).  <br/> |
   

