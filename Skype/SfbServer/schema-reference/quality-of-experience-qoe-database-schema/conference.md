---
title: Conference-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Die Konferenz-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.
ms.openlocfilehash: 0914e98aed4aea16e5301ccae454e925663454a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920166"
---
# <a name="conference-table"></a>Conference-Tabelle
 
Die Konferenz-Tabelle ist eine Tabelle. Jeder Datensatz steht für eine Konferenz oder Peer-zu-Peer-Sitzung.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die diesen konferenzdatensatz identifiziert.  <br/> |
|**ConfURI** <br/> |nvarchar(450)  <br/> |eindeutige  <br/> |Konferenz-URI ist dies eine Konferenz ist, oder Dialogkennung, wenn dieser ist eine Peer-zu-Peer-Sitzung.  <br/> |
|**Prüfsumme** <br/> |int  <br/> |Index  <br/> |Prüfsumme der Konferenz-URI. Intern wird verwendet.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Nur zur internen Verwendung.  <br/> |
   

