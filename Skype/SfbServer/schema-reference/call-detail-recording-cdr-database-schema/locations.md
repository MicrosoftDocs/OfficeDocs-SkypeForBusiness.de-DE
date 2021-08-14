---
title: Tabelle "Speicherorte" in Skype for Business Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Jeder Datensatz stellt den Verweis auf einen Standort in einem Notruf (z. B. ein E9-1-1-Anruf) dar.
ms.openlocfilehash: 887c9c7198272fa2087399c0ccf67e37ae890dc90a322eb17bcff16688808080
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343229"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a>Tabelle "Speicherorte" in Skype for Business Server 2015
 
Jeder Datensatz stellt den Verweis auf einen Standort in einem Notruf (z. B. ein E9-1-1-Anruf) dar.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Zeitpunkt der Sitzungsanforderung. Wird zusammen mit **SessionIdSeq** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |Ganzzahl  <br/> |Primär, Fremd  <br/> |ID zur Identifikation der Sitzung. Wird zusammen mit **SessionIdTime** verwendet, um eine Sitzung eindeutig zu identifizieren. Weitere Informationen finden Sie in der [Dialogs-Tabelle in Skype for Business Server 2015.](dialogs.md) <br/> |
|**Standort** <br/> |nvarchar(max)  <br/> ||Standort des Notrufs.  <br/> |
   

