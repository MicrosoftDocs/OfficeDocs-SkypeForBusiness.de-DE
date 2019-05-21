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
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState enthält Informationen zum Kompatibilitätszustand des Pools.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295475"
---
# <a name="tblcompliancestate"></a>tblComplianceState
 
tblComplianceState enthält Informationen zum Kompatibilitätszustand des Pools.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|lastProcessedEntryID  <br/> |bigint, nicht NULL  <br/> |Die ID des letzten verarbeiteten Compliance-Ereignisses.  <br/> |
|activeServerID  <br/> |int, nicht NULL  <br/> |Die ID des Kompatibilitätsservers, auf dem die exklusive Sperre für die Datenbank gespeichert ist, oder-1, wenn kein.  <br/> |
|lockExpirationTime  <br/> |datetime2, nicht NULL  <br/> |Ablaufzeit Sperren (wenn activeServerID nicht-1 ist).  <br/> |
   

