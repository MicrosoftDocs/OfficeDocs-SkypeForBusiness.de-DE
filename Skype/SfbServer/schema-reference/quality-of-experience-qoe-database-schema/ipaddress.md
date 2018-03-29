---
title: IPAddress-Tabelle
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a>IPAddress-Tabelle
 
IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die angegebene IP-Adresse.  <br/> |
|**IP-Adresse** <br/> |varchar(50)  <br/> |Eindeutige  <br/> |Eindeutige IP-Adresse (beispielsweise 189.168.1.1), der die IpAddressKey zugeordnet ist. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
   

