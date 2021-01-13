---
title: Tabelle "AppliedBandwidthSource"
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Bei der AppliedBandwidthSource-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Quelle.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831405"
---
# <a name="appliedbandwidthsource-table"></a>Tabelle "AppliedBandwidthSource"
 
Bei der AppliedBandwidthSource-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Quelle.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Quelle identifiziert.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Eigen  <br/> |Dies ist die Quelle der Bandbreitengrenze, die auferlegt wird. Sie beschreibt, woher die Bandbreitenbeschränkung kommt (z. B. "Policy Server", "TURN Server" oder "Modality").  <br/> |
   

