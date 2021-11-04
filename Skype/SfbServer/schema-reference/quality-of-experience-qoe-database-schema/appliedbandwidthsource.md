---
title: AppliedBandwidthSource-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
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
ms.openlocfilehash: 772afa1ffe6ce34dc38676193825c0f2891d7bea
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761833"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource-Tabelle
 
Bei der AppliedBandwidthSource-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Quelle.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diese Quelle identifiziert.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Eigen  <br/> |Dies ist die Quelle der Bandbreitenbeschränkung, die angewendet wird. Es beschreibt, woher die Bandbreiteneinschränkung stammt (z. B. "Richtlinienserver", "TURN Server" oder "Modalität").  <br/> |
   

