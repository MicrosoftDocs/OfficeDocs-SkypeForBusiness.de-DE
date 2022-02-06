---
title: tblComplianceFanout
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: 'tblComplianceFanout enthält alle Server, die ein Complianceereignis verarbeitet haben.'
---

# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout enthält alle Server, die ein Complianceereignis verarbeitet haben.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |Ereignis-ID  <br/> |
|fanoutServerID  <br/> |int  <br/> |Serveridentität (entspricht der Tabelle "tblServerIdentity.serverID").  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|fanoutEventID  <br/> |Fremdschlüssel mit Nachschlagevorgang in der Tabelle "tblComplianceData.cmplEventID".  <br/> |
   

