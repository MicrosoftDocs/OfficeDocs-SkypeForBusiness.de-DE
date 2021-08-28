---
title: Pooltabelle
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
ms.assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
description: Bei der Pool-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der Informationen über die verschiedenen Front-End-Pools gespeichert sind. Jeder Datensatz in der Tabelle steht für einen Pool.
ms.openlocfilehash: 058bda36020b739388dec63b063402d8891663ee
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626417"
---
# <a name="pool-table"></a>Pooltabelle
 
Bei der Pool-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird und in der Informationen über die verschiedenen Front-End-Pools gespeichert sind. Jeder Datensatz in der Tabelle steht für einen Pool.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PoolKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Pool identifiziert.  <br/> |
|**PoolName** <br/> |nvarchar(256)  <br/> |Eigen  <br/> |Pool-FQDN  <br/> |
   

