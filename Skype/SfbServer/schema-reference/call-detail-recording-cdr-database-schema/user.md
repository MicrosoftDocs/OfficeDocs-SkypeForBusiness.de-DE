---
title: Benutzeransicht
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Die Benutzeransicht speichert Informationen zu Benutzern, die an anrufen oder Sitzungen beteiligt waren, die Datensätze in der Datenbank aufweisen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
ms.openlocfilehash: 2fe0ba4748a776a8f17065a3c5db21d34bd6340d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295741"
---
# <a name="user-view"></a>Benutzeransicht
 
Die Benutzeransicht speichert Informationen zu Benutzern, die an anrufen oder Sitzungen beteiligt waren, die Datensätze in der Datenbank aufweisen. Diese Ansicht wurde in Microsoft lync Server 2013 eingeführt.
  
|**Spalte**|**Datentyp**|**Details**|
|:-----|:-----|:-----|
|UserID  <br/> |int  <br/> |Eindeutige Nummer, die diesen Benutzer kennzeichnet.  <br/> |
|UserUri  <br/> |nvarchar (450)  <br/> |Der URI des Benutzers.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Mandant des Benutzers. Weitere Informationen finden Sie in der [Tabelle Mandanten](tenants.md) . <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Der Typ des Benutzer-URIs. Weitere Informationen finden Sie in der [UriTypes-Tabelle](uritypes.md) . <br/> |
   

