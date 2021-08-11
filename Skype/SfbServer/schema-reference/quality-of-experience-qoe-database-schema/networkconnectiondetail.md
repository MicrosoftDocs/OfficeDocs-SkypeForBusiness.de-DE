---
title: NetworkConnectionDetail-Tabelle
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
ms.openlocfilehash: d1aa430f821233fcbf89f166bf76d3d8fadf76a9f7401ce5c9009629fccea70a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306696"
---
# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail-Tabelle
 
Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |Tinyint  <br/> |Primary  <br/> |Eindeutiger Bezeichner für den Netzwerkverbindungstyp.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Eigen  <br/> |Netzwerkverbindungstyp, der NetworkConnectionDetailKey entspricht. Gültige Werte sind:  <br/> 0 – Wired  <br/> 1 – WiFi  <br/> 2 – Ethernet  <br/> 3 – MobileBB  <br/> 4 -- Sonstige  <br/> 5 –- Tunnel  <br/> |
   

