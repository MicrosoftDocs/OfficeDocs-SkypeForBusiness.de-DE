---
title: Conference-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Die Konferenz-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a>Conference-Tabelle
 
Die Konferenz-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen konferenzdatensatz identifiziert.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |eindeutige  <br/> |Konferenz-URI ist dies eine Konferenz ist, oder Dialogkennung, wenn dieser ist eine Peer-zu-Peer-Sitzung.  <br/> |
|**Prüfsumme** <br/> |int  <br/> |Index  <br/> |Prüfsumme der Konferenz-URI. Intern wird verwendet.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur zur internen Verwendung.  <br/> |
   

