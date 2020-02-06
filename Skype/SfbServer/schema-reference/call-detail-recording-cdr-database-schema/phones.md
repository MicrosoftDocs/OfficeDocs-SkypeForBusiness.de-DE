---
title: Phones-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Die Tabelle Telefone ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815003"
---
# <a name="phones-table"></a>Phones-Tabelle
 
Die Tabelle Telefone ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Telefonnummer** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die dieses Telefon kennzeichnet.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Telefonnummer.  <br/> |
|**NextUpdateTS** <br/> |DateTime  <br/> ||Zeitstempel (nur für interne Nutzung).  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
   

