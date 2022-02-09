---
title: TraceRoute-Tabelle
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Die TraceRoute-Tabelle enthält Routinginformationen von Anrufen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 2f29d5c46d963cb456386e846d765032be8d5cae
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411498"
---
# <a name="traceroute-table"></a>TraceRoute-Tabelle
 
Die TraceRoute-Tabelle enthält Routinginformationen von Anrufen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Datum und Uhrzeit des Beginns des Anrufs.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |Eindeutige ID, die zur Unterscheidung zwischen mehreren Anrufen verwendet wird, die möglicherweise zum gleichen Datum und zur gleichen Uhrzeit  begonnen haben.  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |Primär, Fremd  <br/> |Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:  <br/> 0 – Audio  <br/> 1 – Video  <br/> 2 – Panoramavideo  <br/> 3 – Anwendungs-/Desktopfreigabe  <br/> |
|**FromCaller** <br/> |Bit  <br/> |Primary  <br/> |Endpunkt, der den Anruf getätigt hat.  <br/> |
|**Hop** <br/> |int  <br/> ||Netzwerk-Hop/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Ausländisch  <br/> |Eindeutige ID für die IP-Adresse. IP-Adressinformationen werden in der [IPAddress-Tabelle](ipaddress.md) gespeichert.  <br/> |
|**RTT** <br/> |int  <br/> ||Paketumlaufzeit (Roundtrip time). Die Paketumlaufzeit misst die Zeit, die ein Sprachpaket benötigt, um zu seinem Ziel zu gelangen und eine Benachrichtigung über den Empfang zu senden.  <br/> |
   

