---
title: IPAddress-Tabelle
ms.reviewer: null
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
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: 'In der Tabelle "IPAddress" werden IP-Adressen den eindeutigen IDs der IP-Adressen zugeordnet, die an anderer Stelle in der QoE-Datenbank verwendet werden. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.'
---

# <a name="ipaddress-table"></a>IPAddress-Tabelle
 
In der Tabelle "IPAddress" werden IP-Adressen den eindeutigen IDs der IP-Adressen zugeordnet, die an anderer Stelle in der QoE-Datenbank verwendet werden. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |Eindeutige ID der angegebenen IP-Adresse.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Eigen  <br/> |Eindeutige IP-Adresse (z. B. 189.168.1.1), die "derm IpAddressKey" zugeordnet ist. Dies kann entweder eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
   

