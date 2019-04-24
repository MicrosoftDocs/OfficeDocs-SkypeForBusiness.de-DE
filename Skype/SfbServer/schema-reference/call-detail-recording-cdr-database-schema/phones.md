---
title: Phones-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen über eine Rufnummer beteiligt VoIP-Anrufe, die Datensätze in der Datenbank verfügen.
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212887"
---
# <a name="phones-table"></a>Phones-Tabelle
 
Phones-Tabelle ist eine Tabelle. Jeder Datensatz in der Tabelle speichert Informationen über eine Rufnummer beteiligt VoIP-Anrufe, die Datensätze in der Datenbank verfügen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Zahl, die dieses Telefon identifiziert.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Telefonnummer.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Zeitstempel (nur zur internen Verwendung).  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

