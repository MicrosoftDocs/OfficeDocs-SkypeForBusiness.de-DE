---
title: Phones-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen über eine Rufnummer beteiligt VoIP-Anrufe, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: ba13a059e043cf2a18c41c28dce1a2a54e694b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930616"
---
# <a name="phones-table"></a>Phones-Tabelle
 
Phones-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen über eine Rufnummer beteiligt VoIP-Anrufe, die Datensätze in der Datenbank verfügen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die dieses Telefon identifiziert.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Telefonnummer.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Zeitstempel (nur zur internen Verwendung).  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

