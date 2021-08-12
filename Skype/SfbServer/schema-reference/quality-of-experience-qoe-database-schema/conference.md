---
title: Konferenztabelle
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Bei der Conference-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.
ms.openlocfilehash: 6dfe60a28e8279f7b4c469c61cddc28912db261eedf4754588de4bd8f5852728
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309154"
---
# <a name="conference-table"></a>Konferenztabelle
 
Bei der Conference-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |Ganzzahl  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Konferenzdatensatz identifiziert.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |Einzigartige  <br/> |Konferenz-URI, falls dies eine Konferenz ist, oder Dialogkennung, wenn dies eine Peer-zu-Peer-Sitzung ist.  <br/> |
|**Prüfsumme** <br/> |Ganzzahl  <br/> |Index  <br/> |Prüfsumme der Konferenz-URI. Für interne Zwecke.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Ausschließlich für interne Zwecke.  <br/> |
   

