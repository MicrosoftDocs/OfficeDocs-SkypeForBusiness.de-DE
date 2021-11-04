---
title: Gateways-Tabelle in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: Die Gateways-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gateway, das an PSTN-Anrufen (Public Switched Telephone Network) beteiligt ist, die Datensätze in der Datenbank haben.
ms.openlocfilehash: 35b552239d272f47d1f21c0940620dda4e6f075d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777755"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a>Gateways-Tabelle in Skype for Business Server 2015
 
Die Gateways-Tabelle ist eine Unterstützende Tabelle. Jeder Datensatz speichert Informationen zu einem Gateway, das an PSTN-Anrufen (Public Switched Telephone Network) beteiligt ist, die Datensätze in der Datenbank haben.
  
|**Spalte**|**Datentyp**|**Schlüssel/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**GatewayId** <br/> |int  <br/> |Primary  <br/> |Eindeutige Nummer, die dieses Gateway identifiziert.  <br/> |
|**Gateway** <br/> |nvarchar(256)  <br/> | <br/> |Gatewayname.  <br/> |
   

