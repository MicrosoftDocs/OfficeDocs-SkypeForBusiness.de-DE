---
title: AppliedBandwidthSource-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: Die Tabelle AppliedBandwidthSource ist eine unterstützende Tabelle. Jeder Datensatz stellt eine Quelle dar.
ms.openlocfilehash: 875f6d105a2fef0bf710e57ec389bee4f2613c66
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811443"
---
# <a name="appliedbandwidthsource-table"></a>AppliedBandwidthSource-Tabelle
 
Die Tabelle AppliedBandwidthSource ist eine unterstützende Tabelle. Jeder Datensatz stellt eine Quelle dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die die Quelle kennzeichnet.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar (256)  <br/> |Eindeutigen  <br/> |Hierbei handelt es sich um die Quelle des verhängten Bandbreitenlimits. Es wird beschrieben, woher die Bandbreitengrenze stammt (beispielsweise "Richtlinienserver", "Server umwandeln" oder "Modalität").  <br/> |
   

