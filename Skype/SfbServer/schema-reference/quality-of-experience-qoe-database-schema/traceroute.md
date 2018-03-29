---
title: TraceRoute-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute-Tabelle enthält die Routinginformationen aus aufrufen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: e8796b164bd6a0f2809025b784ada9d12dda449b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="traceroute-table"></a>TraceRoute-Tabelle
 
TraceRoute-Tabelle enthält die Routinginformationen aus aufrufen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primär, Fremd  <br/> |Datum und Uhrzeit des Beginns des Anrufs.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |Eindeutige ID zur Unterscheidung zwischen mehreren anrufen, die an demselben Tag und zur gleichen Zeit möglicherweise begonnen haben.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primär, Fremd  <br/> |Stellt die Art der video an, die in den Anruf verwendet. Zulässige Werte:  <br/> 0 – audio  <br/> 1 - video  <br/> 2 – panoramavideo  <br/> 3 - Anwendung/Desktop freigeben  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |Endpunkt, der den Anruf ausgeführt hat.  <br/> |
|**Nächster Hop** <br/> |int  <br/> ||Netzwerk-Hop /  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Fremdschlüssel  <br/> |Eindeutiger Bezeichner für die IP-Adresse. Informationen zur IP-Adresse wird in der [IPAddress-Tabelle](ipaddress.md)gespeichert.  <br/> |
|**ZEIT** <br/> |int  <br/> ||Roundtripzeit. Die Roundtripzeit misst die benötigte Zeit für ein VoIP-Paket an das Ziel zu erreichen, und senden Sie Back-Benachrichtigung, dass sie empfangen wurde.  <br/> |
   

