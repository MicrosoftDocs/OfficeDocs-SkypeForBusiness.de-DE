---
title: Tabelle "TraceRoute"
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
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831320"
---
# <a name="traceroute-table"></a>Tabelle "TraceRoute"
 
Die TraceRoute-Tabelle enthält Routinginformationen von Anrufen. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |Datum/Uhrzeit  <br/> |Primär, Fremd  <br/> |Datum und Uhrzeit des Beginns des Anrufs.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primär, Fremd  <br/> |Eindeutige ID, die zur Unterscheidung zwischen mehreren Anrufen verwendet wird, die möglicherweise zum gleichen Datum und zur gleichen Uhrzeit  begonnen haben.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primär, Fremd  <br/> |Stellt den Videozeilentyp dar, der bei dem Anruf verwendet wurde. Gültige Werte sind:  <br/> 0 – Audio  <br/> 1 – Video  <br/> 2 – Panoramavideo  <br/> 3 – Anwendungs-/Desktopfreigabe  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |Endpunkt, der den Anruf getätigt hat.  <br/> |
|**Hop** <br/> |int  <br/> ||Netzwerk-Hop/  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Fremd  <br/> |Eindeutige ID für die IP-Adresse. Informationen zu den IP-Adressen werden in der Tabelle ["IPAddress" gespeichert.](ipaddress.md)  <br/> |
|**RTT** <br/> |int  <br/> ||Paketumlaufzeit (Roundtrip time). Die Paketumlaufzeit misst die Zeit, die ein Sprachpaket benötigt, um zu seinem Ziel zu gelangen und eine Benachrichtigung über den Empfang zu senden.  <br/> |
   

