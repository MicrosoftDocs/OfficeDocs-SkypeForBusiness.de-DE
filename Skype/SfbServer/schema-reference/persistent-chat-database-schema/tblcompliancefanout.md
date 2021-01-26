---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: "\"tblComplianceFanout\" enthält alle Server, die ein Kompatibilitätsereignis verarbeitet haben."
ms.openlocfilehash: 75e232cd464a2199b490e555c0fab79ded119c94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809795"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
"tblComplianceFanout" enthält alle Server, die ein Kompatibilitätsereignis verarbeitet haben.
  
**Columns**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |Ereignis-ID  <br/> |
|fanoutServerID  <br/> |int  <br/> |Serveridentität (entsprechend der Tabelle "tblServerIdentity.serverID").  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|fanoutEventID  <br/> |Fremdschlüssel mit Nachschlageschlüssel in der Tabelle "tblComplianceData.cmplEventID".  <br/> |
   

