---
title: IPAddress-Tabelle
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: d7d3b5f9192c2385836f42f9c430da5b99752892
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920033"
---
# <a name="ipaddress-table"></a>IPAddress-Tabelle
 
IPAddress-Tabelle ordnet IP-Adressen den eindeutigen IP-Adress-IDs, die anderswo in der Quality of Experience-Datenbank verwendet. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**IPAddressKey** <br/> |int  <br/> |Primary  <br/> |Eindeutiger Bezeichner für die angegebene IP-Adresse.  <br/> |
|**IPAddress** <br/> |varchar(50)  <br/> |Eindeutige  <br/> |Eindeutige IP-Adresse (beispielsweise 189.168.1.1), der die IpAddressKey zugeordnet ist. Dies kann eine IPv4- oder eine IPv6-Adresse sein.  <br/> |
   

