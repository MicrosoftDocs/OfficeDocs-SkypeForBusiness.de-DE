---
title: NetworkConnectionDetail-Tabelle
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
ms.openlocfilehash: 6d39d9e8432a20102d42cea649a51596ce2c1762
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833189"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail-Tabelle
 
Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |Tinyint  <br/> |Primary  <br/> |Eindeutiger Bezeichner für den Netzwerkverbindungstyp.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Eigen  <br/> |Netzwerkverbindungstyp, der NetworkConnectionDetailKey entspricht. Gültige Werte sind:  <br/> 0 – Wired  <br/> 1 – WiFi  <br/> 2 – Ethernet  <br/> 3 – MobileBB  <br/> 4 -- Sonstige  <br/> 5 –- Tunnel  <br/> |
   

