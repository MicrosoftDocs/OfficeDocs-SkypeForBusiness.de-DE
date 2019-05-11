---
title: NetworkConnectionDetail-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindung-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: a7095000cc996f2a6430ffcaf8411a2891872938
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919991"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail-Tabelle
 
NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungstypen den Netzwerk Verbindung-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Eindeutiger Bezeichner für den Netzwerkverbindungstyp.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)-Wert  <br/> |Eindeutige  <br/> |Typ der Netzwerkverbindung, die die NetworkConnectionDetailKey entspricht. Gültige Werte sind:  <br/> 0 – verkabelt  <br/> 1--WiFi  <br/> 2--Ethernet  <br/> 3 – MobileBB  <br/> 4 – andere  <br/> 5 – tunnel  <br/> |
   

