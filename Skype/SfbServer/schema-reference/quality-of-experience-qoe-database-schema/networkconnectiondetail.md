---
title: Tabelle "NetworkConnectionDetail"
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 2e03e7935370e71a8070ed1882f61ac5480f312e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806305"
---
# <a name="networkconnectiondetail-table"></a>Tabelle "NetworkConnectionDetail"
 
Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |tinyint  <br/> |Primary  <br/> |Eindeutiger Bezeichner für den Netzwerkverbindungstyp.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Eigen  <br/> |Netzwerkverbindungstyp, der NetworkConnectionDetailKey entspricht. Gültige Werte sind:  <br/> 0 – Wired  <br/> 1 – WiFi  <br/> 2 – Ethernet  <br/> 3 – MobileBB  <br/> 4 -- Sonstige  <br/> 5 -- Tunnel  <br/> |
   

