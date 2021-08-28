---
title: Phones-Tabelle
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
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Die Phones-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist und Datensätze in der Datenbank enthält.
ms.openlocfilehash: 37adaaa1885d91c84ee657c422b19debad294c01
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584859"
---
# <a name="phones-table"></a>Phones-Tabelle
 
Die Phones-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist und Datensätze in der Datenbank enthält.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die dieses Telefon identifiziert.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Telefon Zahl.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Zeitstempel (nur für interne Verwendung).  <br/> Dieses Feld wurde in Microsoft Lync Server 2013 eingeführt.  <br/> |
   

