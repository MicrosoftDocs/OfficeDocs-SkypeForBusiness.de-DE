---
title: AppliedBandwidthSource-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 10dbe69533fe26ba156c270f003fb11ab56e5179
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856432"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource-Tabelle
 
Bei der AppliedBandwidthSource-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Quelle.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Quelle identifiziert.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Eigen  <br/> |Dies ist die Quelle der Bandbreitenbeschränkung, die angewendet wird. Es beschreibt, woher die Bandbreiteneinschränkung stammt (z. B. "Richtlinienserver", "TURN Server" oder "Modalität").  <br/> |
   

