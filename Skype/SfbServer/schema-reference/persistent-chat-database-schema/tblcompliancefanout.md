---
title: tblComplianceFanout
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
ms.assetid: f5d9f342-a7cb-4b54-baa6-e656256b75ad
description: tblComplianceFanout enthält alle Server, die ein Compliance-Ereignis verarbeitet haben.
ms.openlocfilehash: cdf455563ccfc971963144b9d4e848d5678cac80
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814653"
---
# <a name="tblcompliancefanout"></a>tblComplianceFanout
 
tblComplianceFanout enthält alle Server, die ein Compliance-Ereignis verarbeitet haben.
  
**Spalten**

|**Spalte**|**Typ**|**Beschreibung**|
|:-----|:-----|:-----|
|fanoutEventID  <br/> |int  <br/> |Ereignis-ID.  <br/> |
|fanoutServerID  <br/> |int  <br/> |Serveridentität (entsprechend der Tabelle "tblServerIdentity. Serverkennung").  <br/> |
   
**Schlüssel**

|**Spalte**|**Beschreibung**|
|:-----|:-----|
|fanoutEventID  <br/> |Fremdschlüssel mit Lookup in der tblComplianceData. cmplEventID-Tabelle.  <br/> |
   

