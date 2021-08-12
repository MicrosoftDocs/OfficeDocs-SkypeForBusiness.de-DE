---
title: TraceRoute-Tabelle
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Die TraceRoute-Tabelle enthält Routinginformationen von Anrufen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: f08b3cf1e007d9ba2258db1d4db86e9af160a8c9286bc75e27ab9c0ea8ece441
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322927"
---
# <a name="traceroute-table"></a>TraceRoute-Tabelle
 
Die TraceRoute-Tabelle enthält Routinginformationen von Anrufen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Datum und Uhrzeit des Beginns des Anrufs.  <br/> |
|**SessionSeq** <br/> |Ganzzahl  <br/> |Primär, Fremd  <br/> |Eindeutige ID, die zur Unterscheidung zwischen mehreren Anrufen verwendet wird, die möglicherweise zum gleichen Datum und zur gleichen Uhrzeit  begonnen haben.  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |Primär, Fremd  <br/> |Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:  <br/> 0 – Audio  <br/> 1 – Video  <br/> 2 – Panoramavideo  <br/> 3 – Anwendungs-/Desktopfreigabe  <br/> |
|**FromCaller** <br/> |Bit  <br/> |Primary  <br/> |Endpunkt, der den Anruf getätigt hat.  <br/> |
|**Hop** <br/> |Ganzzahl  <br/> ||Netzwerk-Hop/  <br/> |
|**IPAddressKey** <br/> |Ganzzahl  <br/> |Ausländisch  <br/> |Eindeutige ID für die IP-Adresse. IP-Adressinformationen werden in der [IPAddress-Tabelle](ipaddress.md)gespeichert.  <br/> |
|**Rtt** <br/> |Ganzzahl  <br/> ||Paketumlaufzeit (Roundtrip time). Die Paketumlaufzeit misst die Zeit, die ein Sprachpaket benötigt, um zu seinem Ziel zu gelangen und eine Benachrichtigung über den Empfang zu senden.  <br/> |
   

