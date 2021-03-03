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
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802785"
---
# <a name="conference-table"></a>Konferenztabelle
 
Bei der Conference-Tabelle handelt es sich um eine Tabelle, auf die verwiesen wird. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen Konferenzdatensatz identifiziert.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |unique  <br/> |Konferenz-URI, falls dies eine Konferenz ist, oder Dialogkennung, wenn dies eine Peer-zu-Peer-Sitzung ist.  <br/> |
|**Prüfsumme** <br/> |int  <br/> |Index  <br/> |Prüfsumme der Konferenz-URI. Für interne Zwecke.  <br/> |
|**NextUpdateTS** <br/> |Datum/Uhrzeit  <br/> ||Ausschließlich für interne Zwecke.  <br/> |
   

