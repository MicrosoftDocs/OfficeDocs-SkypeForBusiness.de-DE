---
title: TraceRoute-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Die traceroute-Tabelle enthält Routinginformationen aus anrufen. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805113"
---
# <a name="traceroute-table"></a>TraceRoute-Tabelle
 
Die traceroute-Tabelle enthält Routinginformationen aus anrufen. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primär, fremd  <br/> |Das Datum und die Uhrzeit, zu der der Anruf begonnen hat.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primär, fremd  <br/> |Eindeutiger Bezeichner, der verwendet wird, um zwischen mehreren Anrufen zu unterscheiden, die möglicherweise am gleichen Datum und zur gleichen Zeit begonnen haben.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primär, fremd  <br/> |Stellt den Typ der im Anruf verwendeten Videozeile dar. Gültige Werte sind:  <br/> 0-Audio  <br/> 1-Video  <br/> 2 – Panorama Video  <br/> 3 – Anwendung/Desktop Freigabe  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |Endpunkt, der den Anruf getätigt hat.  <br/> |
|**Hop** <br/> |int  <br/> ||Netzwerk-Hop/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Fremd  <br/> |Eindeutiger Bezeichner für die IP-Adresse. IP-Adressinformationen werden in der [IPAddress-Tabelle](ipaddress.md)gespeichert.  <br/> |
|**RTT** <br/> |int  <br/> ||Roundtrip-Zeit. Die Roundtrip-Zeit misst die Zeitdauer, die ein Sprachpaket benötigt, um sein Ziel zu erreichen, und sendet dann eine Benachrichtigung, dass es empfangen wurde.  <br/> |
   

