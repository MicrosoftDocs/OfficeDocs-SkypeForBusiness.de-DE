---
title: IPAddress-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: Die IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294922"
---
# <a name="ipaddress-table"></a>IPAddress-Tabelle
 
Die IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress Bezeichnern zu, die an anderer Stelle in der Datenbank für die Qualität der Erfahrung verwendet werden. Diese Tabelle wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die angegebene IP-Adresse.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Eindeutigen  <br/> |Eindeutige IP-Adresse (beispielsweise 189.168.1.1), die dem IpAddressKey zugeordnet ist. Hierbei kann es sich entweder um eine IPv4-oder eine IPv6-Adresse handeln.  <br/> |
   

