---
title: AppliedBandwidthSource-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: c886c5179d40063c1325bea3167e06ae7fe37666
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411508"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource-Tabelle
 
Bei der AppliedBandwidthSource-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Quelle.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Quelle identifiziert.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Eigen  <br/> |Dies ist die Quelle der Bandbreitenbeschränkung, die angewendet wird. Es beschreibt, woher die Bandbreiteneinschränkung stammt (z. B. "Richtlinienserver", "TURN Server" oder "Modalität").  <br/> |
   

