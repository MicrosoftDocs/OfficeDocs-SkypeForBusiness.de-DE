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
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Die traceroute-Tabelle enthält Routinginformationen aus anrufen. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 323f8160e7543c2fa08bebe9d1805355469acfd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294628"
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
   

