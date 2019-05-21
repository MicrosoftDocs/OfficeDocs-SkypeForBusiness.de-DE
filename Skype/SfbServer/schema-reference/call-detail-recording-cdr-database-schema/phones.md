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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Die Tabelle Telefone ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295944"
---
# <a name="phones-table"></a>Phones-Tabelle
 
Die Tabelle Telefone ist eine unterstützende Tabelle. Jeder Datensatz in der Tabelle speichert Informationen zu einer Telefonnummer, die an VoIP-Anrufen beteiligt ist, die Datensätze in der Datenbank aufweisen.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**Telefonnummer** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die dieses Telefon kennzeichnet.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |Telefonnummer.  <br/> |
|**NextUpdateTS** <br/> |DateTime  <br/> ||Zeitstempel (nur für interne Nutzung).  <br/> Dieses Feld wurde in Microsoft lync Server 2013 eingeführt.  <br/> |
   

