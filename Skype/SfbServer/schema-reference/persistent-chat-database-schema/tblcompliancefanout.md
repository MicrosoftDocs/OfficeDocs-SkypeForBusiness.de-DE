---
title: tblComplianceFanout
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: TblComplianceFanout enthält alle Server, die ein kompatibilitätsereignis verarbeitet.
ms.openlocfilehash: f9141a6f7144c20d8039756387a889cc25cc8f50
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
TblComplianceFanout enthält alle Server, die ein kompatibilitätsereignis verarbeitet.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |Ereignis-ID  <br/> |
|fanoutServerID  <br/> |int  <br/> |Serveridentität (entsprechend zur tblServerIdentity.serverID-Tabelle).  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|fanoutEventID  <br/> |Fremdschlüssel mit Abfrage der tblComplianceData.cmplEventID-Tabelle.  <br/> |
   

