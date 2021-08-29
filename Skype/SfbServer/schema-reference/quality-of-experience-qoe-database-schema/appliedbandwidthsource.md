---
title: AppliedBandwidthSource-Tabelle
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
ms.localizationpriority: medium
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Bei der AppliedBandwidthSource-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Quelle.
ms.openlocfilehash: 2daa4d35d11c000503fa83c79963df14886f50cd
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58633469"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource-Tabelle
 
Bei der AppliedBandwidthSource-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Quelle.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Quelle identifiziert.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Eigen  <br/> |Dies ist die Quelle der Bandbreitenbeschränkung, die angewendet wird. Es beschreibt, woher die Bandbreiteneinschränkung stammt (z. B. "Richtlinienserver", "TURN Server" oder "Modalität").  <br/> |
   

