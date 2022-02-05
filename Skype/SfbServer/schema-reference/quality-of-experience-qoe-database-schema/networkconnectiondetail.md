---
title: NetworkConnectionDetail-Tabelle
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
ms.assetid: b48cc9a6-5232-48b5-bd20-53b68229336b
description: 'Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.'
---

# <a name="networkconnectiondetail-table"></a>NetworkConnectionDetail-Tabelle
 
Die NetworkConnectionDetail-Tabelle ordnet Netzwerkverbindungs-IDs, die anderweitig in der Quality of Experience-Datenbank verwendet werden, Netzwerkverbindungstypen zu. Diese Tabelle wurde in Microsoft Lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**NetworkConnectionDetailKey** <br/> |Tinyint  <br/> |Primary  <br/> |Eindeutiger Bezeichner für den Netzwerkverbindungstyp.  <br/> |
|**NetworkConnectionDetail** <br/> |varchar(256)  <br/> |Eigen  <br/> |Netzwerkverbindungstyp, der NetworkConnectionDetailKey entspricht. Gültige Werte sind:  <br/> 0 – Wired  <br/> 1 – WiFi  <br/> 2 – Ethernet  <br/> 3 – MobileBB  <br/> 4 -- Sonstige  <br/> 5 –- Tunnel  <br/> |
   

